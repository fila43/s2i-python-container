FROM ubi7/python-27

USER 0
ADD app-src ./

RUN export PATH=$PATH:/opt/rh/python27/root/usr/bin/ && export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/opt/rh/python27/root/usr/lib64/ && pip install -U "pip==19.3.1" && \
	pip install -r requirements.txt && \
	python manage.py collectstatic --noinput && \
	python manage.py migrate

CMD python manage.py runserver 0.0.0.0:8080

