FROM eclipse-temurin:21

WORKDIR /app

RUN wget -q https://github.com/zoujiaqing/registration-service/archive/refs/heads/main.zip && \
        jar xf main.zip && \
        mv registration-service-main registration-service && \
        chmod -R +777 registration-service && \
        rm main.zip

WORKDIR /app/registration-service

# Downloads all the dependencies required and bundles it into the image
RUN ./mvnw install -DskipTests -Dmicronaut.environments=dev

CMD ./mvnw clean mn:run -Dmicronaut.environments=dev
