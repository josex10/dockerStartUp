FROM node:16
    LABEL maitainer josebp.10@hotmail.com
    RUN git clone -q https://github.com/josex10/RH-BACKEND.git
    WORKDIR RH-BACKEND
    RUN npm install > /dev/null
    EXPOSE 8000
    CMD ["npm", "run", "start"]