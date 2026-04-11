FROM maven:3.9.14

WORKDIR /app

COPY pom.xml .
COPY src ./src

RUN mvn clean package -DskipTests

# Fix: dynamic jar name
RUN mv target/*.jar shipping.jar

EXPOSE 8080

ENV CART_ENDPOINT=cart:8080 \
    DB_HOST=mysql

CMD ["java", "-jar", "shipping.jar"]

# added comments regarding the shipping
# FROM maven:3.9.14
# EXPOSE 8080
# WORKDIR /app
# COPY pom.xml .
# COPY src ./src
# RUN mvn clean package
# RUN mv target/shipping-1.0.jar shipping.jar
# ENV CART_ENDPOINT="cart:8080" \
    # DB_HOST="mysql"
# CMD ["java","-jar","shipping.jar"]
