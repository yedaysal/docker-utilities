FROM jenkins/inbound-agent:latest-jdk11

ENV JNLP_PROTOCOL_OPTS=-Dorg.jenkinsci.remoting.engine.JnlpProtocol3.disabled=false
ENV JAVA_OPTS -XX:-UsePerfData
ENV NODE_PATH=/usr/lib/node_modules

# Change to root user
USER root

# Install Node.js, install Playwright, install Playwright dependencies, install Playwright browsers
RUN curl -fsSL https://deb.nodesource.com/setup_21.x | bash - && apt-get install -y nodejs && npm install -g @playwright/test@1.41.2 @types/node@20.11.16 && npx playwright install-deps && apt clean && npx playwright install
