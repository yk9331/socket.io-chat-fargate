FROM public.ecr.aws/docker/library/node:lts AS build
WORKDIR /srv
ADD package.json .
RUN npm install

FROM public.ecr.aws/docker/library/node:lts-slim
COPY --from=build /srv .
ADD . .
EXPOSE 3000
CMD ["node", "./node_modules/.bin/mocha", "-b", "--exit"]
