## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [ ] 1. Ознакомиться со ссылками учебного материала
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=DarthBarada # Устанавливаем значение переменной окружения GITHUB_USERNAME
$ export GIST_TOKEN=94f6b47430b12af896a72508a8272fc97d838b94 # Устанавливаем значение переменной окружения GIST_TOKEN
$ alias edit=nano # выбираем тип редактора
```

```ShellSession
$ mkdir -p DarthBarada/workspace # создаем папку DarthBarada с подкапкой workspace
$ cd DarthBarada/workspace # заходим в нее
$ pwd # выводим полный путь до неё
$ cd .. # заходим в директорию на 1 уровень выше
$ pwd # выводим полный путь до папки
```

```ShellSession # создаем в папке workspace папки tasks,projects,reports и заходим в workspace
$ mkdir -p workspace/tasks/ 
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```ShellSession
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz # скачиваем архив из интернета
$ tar -xf node-v6.11.5-linux-x64.tar.xz # распаковываем его
$ rm -rf node-v6.11.5-linux-x64.tar.xz # удаляем архив, но не папку
$ mv node-v6.11.5-linux-x64 node # переименовываем папку node-v6.11.5-linux-x64 в node
```

```ShellSession
$ ls node/bin # выводим содержимое папки node/bin
$ echo ${PATH} # выводим переменную среды
$ export PATH=${PATH}:`pwd`/node/bin #добавляем к ней путь до папки node/bin
$ echo ${PATH} # выводим переменную среды
$ mkdir scripts # создаем папку scripts
$ cat > scripts/activate<<EOF # создаем в папке scripts текстовый документ activate и добавляем в него код
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```

```ShellSession
$ npm install -g gistup # скачиваем gistup
$ ls node/bin # выводим содержимое папки node/bin
```

```ShellSession
$ cat > ~/.gistup.json <<EOF # редактируем файл gistup.json 
{
  "token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
$ export LAB_NUMBER=01 # Устанавливаем значение переменной окружения LAB_NUMBER
$ git clone https://github.com/tp-labs/lab01 tasks/lab01 # создаем копию из https://github.com/tp-labs/lab01 в директорию tasks/lab01
$ mkdir reports/lab01 # создаем папку reports/lab01
$ cp tasks/lab01/README.md reports/lab01/REPORT.md # копируем README.md из tasks/lab01 в reports/lab01
$ cd reports/lab01 # заходим в папку reports/lab01
$ edit REPORT.md # редактируем REPORT.md
$ gistup -m "lab01" # enter: yes↵ 
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
11. Найдите *топ10* самых "тяжёлых".

## Homework
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz # загружаем из интернета
...
$ tar boost_1_69_0.tar.gz # разархивируем
$ cd boost_1_69_0
~/boost_1_69_0$ find . -maxdepth 1 | wc # подсчитываем количство файлов в директории
     19      19     208
~/boost_1_69_0$ find . | wc # количество всех файлов
  66829   66832 3286647
~/boost_1_69_0$ find . -name "*.cpp" | wc # количество файлов с расширением ".cpp"
  13774   13774  647953
~/boost_1_69_0$ find . -name "*.cpp" -prune -o -print | wc # ищем все,кроме .cpp
  53055   53058 2638694
~/boost_1_69_0$ find . -name "any.hpp" -print # показывает путь до файлов с именем any.hpp
./boost/hana/fwd/any.hpp
./boost/hana/any.hpp
./boost/xpressive/detail/utility/any.hpp
./boost/spirit/home/support/algorithm/any.hpp
./boost/fusion/algorithm/query/any.hpp
./boost/fusion/algorithm/query/detail/any.hpp
./boost/fusion/include/any.hpp
./boost/proto/detail/any.hpp
./boost/type_erasure/any.hpp
./boost/any.hpp
~/boost_1_69_0$ find / -type f | grep -rl "boost::asio" # ищет файлы с последовательностью "boost::asio"
find: ‘/var/cache/apparmor/ea9ed67a.0’: Отказано в доступе
find: ‘/var/cache/private’: Отказано в доступе
find: ‘/var/cache/ldconfig’: Отказано в доступе
find: ‘/var/cache/apt/archives/partial’: Отказано в доступе
libs/fiber/examples/asio/autoecho.cpp
libs/fiber/examples/asio/round_robin.hpp
libs/fiber/examples/asio/ps/subscriber.cpp
libs/fiber/examples/asio/ps/server.cpp
libs/fiber/examples/asio/ps/publisher.cpp
libs/fiber/examples/asio/exchange.cpp
libs/fiber/doc/fibers.qbk
libs/fiber/doc/asio.qbk
libs/fiber/doc/integration.qbk
libs/fiber/doc/callbacks.qbk
libs/process/test/async_system_stackful.cpp
libs/process/test/async_system_stackless.cpp
libs/process/test/async_system_future.cpp
libs/process/test/on_exit3.cpp
libs/process/test/spawn_fail.cpp
libs/process/test/async_system_stackful_except.cpp
libs/process/test/system_test1.cpp
libs/process/test/system_test2.cpp
libs/process/test/bind_stdout_stderr.cpp
libs/process/test/spawn.cpp
libs/process/test/async_fut.cpp
libs/process/test/bind_stdout.cpp
libs/process/test/on_exit.cpp
libs/process/test/async_system_stackful_error.cpp
libs/process/test/async_system_fail.cpp
libs/process/test/bind_stdin.cpp
libs/process/test/async_pipe.cpp
libs/process/test/exit_code.cpp
libs/process/test/bind_stderr.cpp
libs/process/test/on_exit2.cpp
libs/process/test/wait.cpp
libs/process/test/async.cpp
libs/process/doc/extend.qbk
libs/process/doc/autodoc.xml
libs/process/doc/tutorial.qbk
libs/process/example/io.cpp
libs/process/example/async_io.cpp
libs/process/example/wait.cpp
libs/coroutine/doc/coro.qbk
libs/coroutine/doc/motivation.qbk
libs/coroutine/doc/html/coroutine/motivation.html
libs/thread/test/test_9303.cpp
libs/coroutine2/doc/coro.qbk
libs/coroutine2/doc/motivation.qbk
libs/log/doc/tmp/sinks_reference.xml
libs/log/src/syslog_backend.cpp
libs/beast/test/bench/buffers/bench_buffers.cpp
libs/beast/test/bench/wsload/wsload.cpp
libs/beast/test/bench/parser/bench_parser.cpp
libs/beast/test/bench/parser/nodejs_parser.hpp
libs/beast/test/extras/include/boost/beast/test/sig_wait.hpp
libs/beast/test/extras/include/boost/beast/test/yield_to.hpp
libs/beast/test/extras/include/boost/beast/test/websocket.hpp
libs/beast/test/doc/websocket_snippets.cpp
libs/beast/test/doc/core_examples.cpp
libs/beast/test/doc/http_examples.cpp
libs/beast/test/doc/exemplars.cpp
libs/beast/test/doc/http_snippets.cpp
libs/beast/test/doc/core_snippets.cpp
libs/beast/test/beast/websocket/accept.cpp
libs/beast/test/beast/websocket/handshake.cpp
libs/beast/test/beast/websocket/read1.cpp
libs/beast/test/beast/websocket/close.cpp
libs/beast/test/beast/websocket/doc_snippets.cpp
libs/beast/test/beast/websocket/stream.cpp
libs/beast/test/beast/websocket/ping.cpp
libs/beast/test/beast/websocket/read2.cpp
libs/beast/test/beast/websocket/test.hpp
libs/beast/test/beast/websocket/utf8_checker.cpp
libs/beast/test/beast/websocket/write.cpp
libs/beast/test/beast/experimental/flat_stream.cpp
libs/beast/test/beast/experimental/timeout_socket.cpp
libs/beast/test/beast/experimental/timeout_service.cpp
libs/beast/test/beast/experimental/icy_stream.cpp
libs/beast/test/beast/http/test_parser.hpp
libs/beast/test/beast/http/parser.cpp
libs/beast/test/beast/http/basic_parser.cpp
libs/beast/test/beast/http/message_fuzz.hpp
libs/beast/test/beast/http/read.cpp
libs/beast/test/beast/http/file_body.cpp
libs/beast/test/beast/http/serializer.cpp
libs/beast/test/beast/http/chunk_encode.cpp
libs/beast/test/beast/http/dynamic_body.cpp
libs/beast/test/beast/http/write.cpp
libs/beast/test/beast/http/span_body.cpp
libs/beast/test/beast/core/flat_buffer.cpp
libs/beast/test/beast/core/bind_handler.cpp
libs/beast/test/beast/core/buffers_suffix.cpp
libs/beast/test/beast/core/buffers_prefix.cpp
libs/beast/test/beast/core/buffers_adapter.cpp
libs/beast/test/beast/core/static_buffer.cpp
libs/beast/test/beast/core/multi_buffer.cpp
libs/beast/test/beast/core/buffers_cat.cpp
libs/beast/test/beast/core/flat_static_buffer.cpp
libs/beast/test/beast/core/buffer.cpp
libs/beast/test/beast/core/type_traits.cpp
libs/beast/test/beast/core/buffer_test.hpp
libs/beast/test/beast/core/buffered_read_stream.cpp
libs/beast/test/beast/core/read_size.cpp
libs/beast/CHANGELOG.md
libs/beast/doc/docca/include/docca/doxygen.xsl
libs/beast/doc/qbk/reference.qbk
libs/beast/doc/qbk/07_concepts/Streams.qbk
libs/beast/doc/qbk/07_concepts/DynamicBuffer.qbk
libs/beast/doc/qbk/00_main.qbk
libs/beast/doc/qbk/08_design/3_websocket_zaphoyd.qbk
libs/beast/doc/qbk/08_design/4_faq.qbk
libs/beast/doc/qbk/03_core/1_asio.qbk
libs/beast/doc/html/beast/using_io/example_detect_ssl.html
libs/beast/doc/html/beast/using_io/writing_composed_operations.html
libs/beast/doc/html/beast/more_examples/expect_100_continue_server.html
libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_read_some.html
libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_write_some.html
libs/beast/doc/html/beast/ref/boost__beast__http__error.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload1.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload3.html
libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload2.html
libs/beast/example/websocket/client/async/websocket_client_async.cpp
libs/beast/example/websocket/client/sync/websocket_client_sync.cpp
libs/beast/example/websocket/client/sync-ssl/websocket_client_sync_ssl.cpp
libs/beast/example/websocket/client/coro/websocket_client_coro.cpp
libs/beast/example/websocket/client/async-ssl/websocket_client_async_ssl.cpp
libs/beast/example/websocket/client/coro-ssl/websocket_client_coro_ssl.cpp
libs/beast/example/websocket/server/async/websocket_server_async.cpp
libs/beast/example/websocket/server/sync/websocket_server_sync.cpp
libs/beast/example/websocket/server/sync-ssl/websocket_server_sync_ssl.cpp
libs/beast/example/websocket/server/coro/websocket_server_coro.cpp
libs/beast/example/websocket/server/async-ssl/websocket_server_async_ssl.cpp
libs/beast/example/websocket/server/stackless/websocket_server_stackless.cpp
libs/beast/example/websocket/server/coro-ssl/websocket_server_coro_ssl.cpp
libs/beast/example/websocket/server/stackless-ssl/websocket_server_stackless_ssl.cpp
libs/beast/example/websocket/server/fast/websocket_server_fast.cpp
libs/beast/example/doc/http_examples.hpp
libs/beast/example/http/client/crawl/http_crawl.cpp
libs/beast/example/http/client/async/http_client_async.cpp
libs/beast/example/http/client/sync/http_client_sync.cpp
libs/beast/example/http/client/sync-ssl/http_client_sync_ssl.cpp
libs/beast/example/http/client/coro/http_client_coro.cpp
libs/beast/example/http/client/async-ssl/http_client_async_ssl.cpp
libs/beast/example/http/client/coro-ssl/http_client_coro_ssl.cpp
libs/beast/example/http/server/async/http_server_async.cpp
libs/beast/example/http/server/sync/http_server_sync.cpp
libs/beast/example/http/server/flex/http_server_flex.cpp
libs/beast/example/http/server/sync-ssl/http_server_sync_ssl.cpp
libs/beast/example/http/server/coro/http_server_coro.cpp
libs/beast/example/http/server/async-ssl/http_server_async_ssl.cpp
libs/beast/example/http/server/stackless/http_server_stackless.cpp
libs/beast/example/http/server/small/http_server_small.cpp
libs/beast/example/http/server/coro-ssl/http_server_coro_ssl.cpp
libs/beast/example/http/server/stackless-ssl/http_server_stackless_ssl.cpp
libs/beast/example/http/server/fast/http_server_fast.cpp
libs/beast/example/echo-op/echo_op.cpp
libs/beast/example/cppcon2018/net.hpp
libs/beast/example/common/server_certificate.hpp
libs/beast/example/common/session_alloc.hpp
libs/beast/example/common/detect_ssl.hpp
libs/beast/example/common/root_certificates.hpp
libs/beast/example/advanced/server-flex/advanced_server_flex.cpp
libs/beast/example/advanced/server/advanced_server.cpp
libs/phoenix/example/adapted_echo_server.cpp
libs/asio/test/windows/stream_handle.cpp
libs/asio/test/windows/overlapped_ptr.cpp
libs/asio/test/windows/random_access_handle.cpp
libs/asio/test/windows/object_handle.cpp
libs/asio/test/is_read_buffered.cpp
libs/asio/test/buffered_write_stream.cpp
libs/asio/test/buffers_iterator.cpp
libs/asio/test/generic/stream_protocol.cpp
libs/asio/test/generic/raw_protocol.cpp
libs/asio/test/generic/datagram_protocol.cpp
libs/asio/test/generic/seq_packet_protocol.cpp
libs/asio/test/coroutine.cpp
libs/asio/test/unit_test.hpp
libs/asio/test/use_future.cpp
libs/asio/test/streambuf.cpp
libs/asio/test/read_at.cpp
libs/asio/test/posix/stream_descriptor.cpp
libs/asio/test/ssl/stream.cpp
libs/asio/test/signal_set.cpp
libs/asio/test/read_until.cpp
libs/asio/test/write_at.cpp
libs/asio/test/buffer.cpp
libs/asio/test/local/stream_protocol.cpp
libs/asio/test/local/datagram_protocol.cpp
libs/asio/test/local/connect_pair.cpp
libs/asio/test/connect.cpp
libs/asio/test/socket_base.cpp
libs/asio/test/read.cpp
libs/asio/test/archetypes/deprecated_async_ops.hpp
libs/asio/test/archetypes/async_ops.hpp
libs/asio/test/buffered_read_stream.cpp
libs/asio/test/error.cpp
libs/asio/test/io_context.cpp
libs/asio/test/serial_port.cpp
libs/asio/test/ip/unicast.cpp
libs/asio/test/ip/host_name.cpp
libs/asio/test/ip/address_v6.cpp
libs/asio/test/ip/address.cpp
libs/asio/test/ip/multicast.cpp
libs/asio/test/ip/tcp.cpp
libs/asio/test/ip/network_v6.cpp
libs/asio/test/ip/icmp.cpp
libs/asio/test/ip/v6_only.cpp
libs/asio/test/ip/udp.cpp
libs/asio/test/ip/network_v4.cpp
libs/asio/test/ip/address_v4.cpp
libs/asio/test/strand.cpp
libs/asio/test/serial_port_base.cpp
libs/asio/test/latency/tcp_server.cpp
libs/asio/test/latency/udp_server.cpp
libs/asio/test/latency/tcp_client.cpp
libs/asio/test/latency/udp_client.cpp
libs/asio/test/system_timer.cpp
libs/asio/test/deadline_timer.cpp
libs/asio/test/buffered_stream.cpp
libs/asio/test/is_write_buffered.cpp
libs/asio/test/write.cpp
libs/asio/doc/reference.qbk
libs/asio/doc/examples.qbk
libs/asio/doc/reference.xsl
libs/asio/doc/tutorial.qbk
libs/asio/doc/using.qbk
libs/asio/doc/overview/basics.qbk
libs/asio/doc/overview/allocation.qbk
libs/asio/doc/overview/spawn.qbk
libs/asio/doc/overview/other_protocols.qbk
libs/asio/doc/overview/line_based.qbk
libs/asio/doc/overview/coroutines_ts.qbk
libs/asio/doc/overview/buffers.qbk
libs/asio/doc/overview/ssl.qbk
libs/asio/doc/overview/protocols.qbk
libs/asio/doc/overview/coroutine.qbk
libs/asio/doc/overview/posix.qbk
libs/asio/doc/overview/strands.qbk
libs/asio/doc/overview/signals.qbk
libs/asio/doc/overview/cpp2011.qbk
libs/asio/doc/requirements/ReadHandler.qbk
libs/asio/doc/requirements/SignalHandler.qbk
libs/asio/doc/requirements/ShutdownHandler.qbk
libs/asio/doc/requirements/MoveAcceptHandler.qbk
libs/asio/doc/requirements/ResolveHandler.qbk
libs/asio/doc/requirements/HandshakeHandler.qbk
libs/asio/doc/requirements/RangeConnectHandler.qbk
libs/asio/doc/requirements/WriteHandler.qbk
libs/asio/doc/requirements/IteratorConnectHandler.qbk
libs/asio/doc/requirements/AcceptHandler.qbk
libs/asio/doc/requirements/ConnectHandler.qbk
libs/asio/doc/requirements/BufferedHandshakeHandler.qbk
libs/asio/doc/requirements/ConstBufferSequence.qbk
libs/asio/doc/requirements/Handler.qbk
libs/asio/doc/requirements/WaitHandler.qbk
libs/asio/doc/requirements/MutableBufferSequence.qbk
libs/asio/example/cpp17/coroutines_ts/range_based_for.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/chat_server.cpp
libs/asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
libs/asio/example/cpp03/fork/process_per_connection.cpp
libs/asio/example/cpp03/fork/daemon.cpp
libs/asio/example/cpp03/windows/transmit_file.cpp
libs/asio/example/cpp03/spawn/echo_server.cpp
libs/asio/example/cpp03/spawn/parallel_grep.cpp
libs/asio/example/cpp03/chat/chat_server.cpp
libs/asio/example/cpp03/chat/chat_client.cpp
libs/asio/example/cpp03/chat/posix_chat_client.cpp
libs/asio/example/cpp03/invocation/prioritised_handlers.cpp
libs/asio/example/cpp03/timers/time_t_timer.cpp
libs/asio/example/cpp03/porthopper/protocol.hpp
libs/asio/example/cpp03/porthopper/client.cpp
libs/asio/example/cpp03/porthopper/server.cpp
libs/asio/example/cpp03/ssl/client.cpp
libs/asio/example/cpp03/ssl/server.cpp
libs/asio/example/cpp03/buffers/reference_counted.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp03/echo/async_udp_echo_server.cpp
libs/asio/example/cpp03/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp03/iostreams/daytime_client.cpp
libs/asio/example/cpp03/iostreams/http_client.cpp
libs/asio/example/cpp03/iostreams/daytime_server.cpp
libs/asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp03/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp03/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp03/timeouts/async_tcp_client.cpp
libs/asio/example/cpp03/timeouts/server.cpp
libs/asio/example/cpp03/icmp/ping.cpp
libs/asio/example/cpp03/icmp/ipv4_header.hpp
libs/asio/example/cpp03/socks4/sync_client.cpp
libs/asio/example/cpp03/socks4/socks4.hpp
libs/asio/example/cpp03/local/stream_server.cpp
libs/asio/example/cpp03/local/connect_pair.cpp
libs/asio/example/cpp03/local/iostream_client.cpp
libs/asio/example/cpp03/local/stream_client.cpp
libs/asio/example/cpp03/tutorial/daytime4/client.cpp
libs/asio/example/cpp03/tutorial/daytime3/server.cpp
libs/asio/example/cpp03/tutorial/daytime6/server.cpp
libs/asio/example/cpp03/tutorial/timer2/timer.cpp
libs/asio/example/cpp03/tutorial/daytime7/server.cpp
libs/asio/example/cpp03/tutorial/daytime1/client.cpp
libs/asio/example/cpp03/tutorial/timer5/timer.cpp
libs/asio/example/cpp03/tutorial/timer1/timer.cpp
libs/asio/example/cpp03/tutorial/timer_dox.txt
libs/asio/example/cpp03/tutorial/timer3/timer.cpp
libs/asio/example/cpp03/tutorial/timer4/timer.cpp
libs/asio/example/cpp03/tutorial/daytime2/server.cpp
libs/asio/example/cpp03/tutorial/daytime_dox.txt
libs/asio/example/cpp03/tutorial/daytime5/server.cpp
libs/asio/example/cpp03/serialization/client.cpp
libs/asio/example/cpp03/serialization/server.cpp
libs/asio/example/cpp03/serialization/connection.hpp
libs/asio/example/cpp03/http/server2/reply.cpp
libs/asio/example/cpp03/http/server2/reply.hpp
libs/asio/example/cpp03/http/server2/io_context_pool.cpp
libs/asio/example/cpp03/http/server2/server.cpp
libs/asio/example/cpp03/http/server2/server.hpp
libs/asio/example/cpp03/http/server2/connection.cpp
libs/asio/example/cpp03/http/server2/connection.hpp
libs/asio/example/cpp03/http/server2/io_context_pool.hpp
libs/asio/example/cpp03/http/server4/reply.cpp
libs/asio/example/cpp03/http/server4/reply.hpp
libs/asio/example/cpp03/http/server4/request_parser.hpp
libs/asio/example/cpp03/http/server4/main.cpp
libs/asio/example/cpp03/http/server4/server.cpp
libs/asio/example/cpp03/http/server4/server.hpp
libs/asio/example/cpp03/http/server3/reply.cpp
libs/asio/example/cpp03/http/server3/reply.hpp
libs/asio/example/cpp03/http/server3/server.cpp
libs/asio/example/cpp03/http/server3/server.hpp
libs/asio/example/cpp03/http/server3/connection.cpp
libs/asio/example/cpp03/http/server3/connection.hpp
libs/asio/example/cpp03/http/client/sync_client.cpp
libs/asio/example/cpp03/http/client/async_client.cpp
libs/asio/example/cpp03/http/server/reply.cpp
libs/asio/example/cpp03/http/server/reply.hpp
libs/asio/example/cpp03/http/server/server.cpp
libs/asio/example/cpp03/http/server/server.hpp
libs/asio/example/cpp03/http/server/connection.cpp
libs/asio/example/cpp03/http/server/connection.hpp
libs/asio/example/cpp03/multicast/sender.cpp
libs/asio/example/cpp03/multicast/receiver.cpp
libs/asio/example/cpp03/allocation/server.cpp
libs/asio/example/cpp03/nonblocking/third_party_lib.cpp
libs/asio/example/cpp03/services/daytime_client.cpp
libs/asio/example/cpp03/services/basic_logger.hpp
libs/asio/example/cpp03/services/logger_service.hpp
libs/asio/example/cpp03/services/logger_service.cpp
libs/asio/example/cpp11/fork/process_per_connection.cpp
libs/asio/example/cpp11/fork/daemon.cpp
libs/asio/example/cpp11/spawn/echo_server.cpp
libs/asio/example/cpp11/spawn/parallel_grep.cpp
libs/asio/example/cpp11/chat/chat_server.cpp
libs/asio/example/cpp11/chat/chat_client.cpp
libs/asio/example/cpp11/operations/composed_1.cpp
libs/asio/example/cpp11/operations/composed_2.cpp
libs/asio/example/cpp11/operations/composed_4.cpp
libs/asio/example/cpp11/operations/composed_3.cpp
libs/asio/example/cpp11/operations/composed_5.cpp
libs/asio/example/cpp11/invocation/prioritised_handlers.cpp
libs/asio/example/cpp11/futures/daytime_client.cpp
libs/asio/example/cpp11/executors/bank_account_1.cpp
libs/asio/example/cpp11/executors/actor.cpp
libs/asio/example/cpp11/executors/fork_join.cpp
libs/asio/example/cpp11/executors/bank_account_2.cpp
libs/asio/example/cpp11/executors/pipeline.cpp
libs/asio/example/cpp11/executors/priority_scheduler.cpp
libs/asio/example/cpp11/timers/time_t_timer.cpp
libs/asio/example/cpp11/ssl/client.cpp
libs/asio/example/cpp11/ssl/server.cpp
libs/asio/example/cpp11/buffers/reference_counted.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp11/echo/async_udp_echo_server.cpp
libs/asio/example/cpp11/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp11/iostreams/http_client.cpp
libs/asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp11/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp11/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp11/timeouts/async_tcp_client.cpp
libs/asio/example/cpp11/timeouts/server.cpp
libs/asio/example/cpp11/socks4/sync_client.cpp
libs/asio/example/cpp11/socks4/socks4.hpp
libs/asio/example/cpp11/local/stream_server.cpp
libs/asio/example/cpp11/local/connect_pair.cpp
libs/asio/example/cpp11/local/iostream_client.cpp
libs/asio/example/cpp11/local/stream_client.cpp
libs/asio/example/cpp11/http/server/reply.cpp
libs/asio/example/cpp11/http/server/reply.hpp
libs/asio/example/cpp11/http/server/server.cpp
libs/asio/example/cpp11/http/server/server.hpp
libs/asio/example/cpp11/http/server/connection.cpp
libs/asio/example/cpp11/http/server/connection.hpp
libs/asio/example/cpp11/multicast/sender.cpp
libs/asio/example/cpp11/multicast/receiver.cpp
libs/asio/example/cpp11/allocation/server.cpp
libs/asio/example/cpp11/nonblocking/third_party_lib.cpp
libs/asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
libs/asio/example/cpp11/handler_tracking/custom_tracking.hpp
doc/html/boost_process/extend.html
doc/html/boost_process/tutorial.html
doc/html/process/reference.html
doc/html/boost_asio/examples/cpp11_examples.html
doc/html/boost_asio/examples/cpp03_examples.html
doc/html/boost_asio/index.html
doc/html/boost_asio/tutorial/tutdaytime2.html
doc/html/boost_asio/tutorial/tuttimer1/src.html
doc/html/boost_asio/tutorial/tuttimer2/src.html
doc/html/boost_asio/tutorial/tuttimer5/src.html
doc/html/boost_asio/tutorial/tuttimer3/src.html
doc/html/boost_asio/tutorial/tutdaytime3/src.html
doc/html/boost_asio/tutorial/tuttimer5.html
doc/html/boost_asio/tutorial/tutdaytime6.html
doc/html/boost_asio/tutorial/tutdaytime1.html
doc/html/boost_asio/tutorial/tutdaytime4/src.html
doc/html/boost_asio/tutorial/tuttimer2.html
doc/html/boost_asio/tutorial/tuttimer4/src.html
doc/html/boost_asio/tutorial/tutdaytime1/src.html
doc/html/boost_asio/tutorial/tutdaytime4.html
doc/html/boost_asio/tutorial/tuttimer4.html
doc/html/boost_asio/tutorial/tutdaytime2/src.html
doc/html/boost_asio/tutorial/tutdaytime7.html
doc/html/boost_asio/tutorial/tutdaytime6/src.html
doc/html/boost_asio/tutorial/tutdaytime3.html
doc/html/boost_asio/tutorial/tutdaytime5.html
doc/html/boost_asio/tutorial/tutdaytime5/src.html
doc/html/boost_asio/tutorial/tuttimer1.html
doc/html/boost_asio/tutorial/tutdaytime7/src.html
doc/html/boost_asio/tutorial/tuttimer3.html
doc/html/boost_asio/example/cpp17/coroutines_ts/range_based_for.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/chat_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
doc/html/boost_asio/example/cpp03/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp03/fork/daemon.cpp
doc/html/boost_asio/example/cpp03/windows/transmit_file.cpp
doc/html/boost_asio/example/cpp03/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp03/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp03/chat/chat_server.cpp
doc/html/boost_asio/example/cpp03/chat/chat_client.cpp
doc/html/boost_asio/example/cpp03/chat/posix_chat_client.cpp
doc/html/boost_asio/example/cpp03/invocation/prioritised_handlers.cpp
doc/html/boost_asio/example/cpp03/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp03/porthopper/protocol.hpp
doc/html/boost_asio/example/cpp03/porthopper/client.cpp
doc/html/boost_asio/example/cpp03/porthopper/server.cpp
doc/html/boost_asio/example/cpp03/ssl/client.cpp
doc/html/boost_asio/example/cpp03/ssl/server.cpp
doc/html/boost_asio/example/cpp03/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_client.cpp
doc/html/boost_asio/example/cpp03/iostreams/http_client.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_server.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/server.cpp
doc/html/boost_asio/example/cpp03/icmp/ping.cpp
doc/html/boost_asio/example/cpp03/icmp/ipv4_header.hpp
doc/html/boost_asio/example/cpp03/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp03/socks4/socks4.hpp
doc/html/boost_asio/example/cpp03/local/stream_server.cpp
doc/html/boost_asio/example/cpp03/local/connect_pair.cpp
doc/html/boost_asio/example/cpp03/local/iostream_client.cpp
doc/html/boost_asio/example/cpp03/local/stream_client.cpp
doc/html/boost_asio/example/cpp03/serialization/client.cpp
doc/html/boost_asio/example/cpp03/serialization/server.cpp
doc/html/boost_asio/example/cpp03/serialization/connection.hpp
doc/html/boost_asio/example/cpp03/http/server2/reply.cpp
doc/html/boost_asio/example/cpp03/http/server2/reply.hpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.cpp
doc/html/boost_asio/example/cpp03/http/server2/server.cpp
doc/html/boost_asio/example/cpp03/http/server2/server.hpp
doc/html/boost_asio/example/cpp03/http/server2/connection.cpp
doc/html/boost_asio/example/cpp03/http/server2/connection.hpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.hpp
doc/html/boost_asio/example/cpp03/http/server4/reply.cpp
doc/html/boost_asio/example/cpp03/http/server4/reply.hpp
doc/html/boost_asio/example/cpp03/http/server4/request_parser.hpp
doc/html/boost_asio/example/cpp03/http/server4/main.cpp
doc/html/boost_asio/example/cpp03/http/server4/server.cpp
doc/html/boost_asio/example/cpp03/http/server4/server.hpp
doc/html/boost_asio/example/cpp03/http/server3/reply.cpp
doc/html/boost_asio/example/cpp03/http/server3/reply.hpp
doc/html/boost_asio/example/cpp03/http/server3/server.cpp
doc/html/boost_asio/example/cpp03/http/server3/server.hpp
doc/html/boost_asio/example/cpp03/http/server3/connection.cpp
doc/html/boost_asio/example/cpp03/http/server3/connection.hpp
doc/html/boost_asio/example/cpp03/http/client/sync_client.cpp
doc/html/boost_asio/example/cpp03/http/client/async_client.cpp
doc/html/boost_asio/example/cpp03/http/server/reply.cpp
doc/html/boost_asio/example/cpp03/http/server/reply.hpp
doc/html/boost_asio/example/cpp03/http/server/server.cpp
doc/html/boost_asio/example/cpp03/http/server/server.hpp
doc/html/boost_asio/example/cpp03/http/server/connection.cpp
doc/html/boost_asio/example/cpp03/http/server/connection.hpp
doc/html/boost_asio/example/cpp03/multicast/sender.cpp
doc/html/boost_asio/example/cpp03/multicast/receiver.cpp
doc/html/boost_asio/example/cpp03/allocation/server.cpp
doc/html/boost_asio/example/cpp03/nonblocking/third_party_lib.cpp
doc/html/boost_asio/example/cpp03/services/daytime_client.cpp
doc/html/boost_asio/example/cpp03/services/basic_logger.hpp
doc/html/boost_asio/example/cpp03/services/logger_service.hpp
doc/html/boost_asio/example/cpp03/services/logger_service.cpp
doc/html/boost_asio/example/cpp11/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp11/fork/daemon.cpp
doc/html/boost_asio/example/cpp11/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp11/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp11/chat/chat_server.cpp
doc/html/boost_asio/example/cpp11/chat/chat_client.cpp
doc/html/boost_asio/example/cpp11/operations/composed_1.cpp
doc/html/boost_asio/example/cpp11/operations/composed_2.cpp
doc/html/boost_asio/example/cpp11/operations/composed_4.cpp
doc/html/boost_asio/example/cpp11/operations/composed_3.cpp
doc/html/boost_asio/example/cpp11/operations/composed_5.cpp
doc/html/boost_asio/example/cpp11/invocation/prioritised_handlers.cpp
doc/html/boost_asio/example/cpp11/futures/daytime_client.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_1.cpp
doc/html/boost_asio/example/cpp11/executors/actor.cpp
doc/html/boost_asio/example/cpp11/executors/fork_join.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_2.cpp
doc/html/boost_asio/example/cpp11/executors/pipeline.cpp
doc/html/boost_asio/example/cpp11/executors/priority_scheduler.cpp
doc/html/boost_asio/example/cpp11/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp11/ssl/client.cpp
doc/html/boost_asio/example/cpp11/ssl/server.cpp
doc/html/boost_asio/example/cpp11/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/server.cpp
doc/html/boost_asio/example/cpp11/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp11/socks4/socks4.hpp
doc/html/boost_asio/example/cpp11/local/stream_server.cpp
doc/html/boost_asio/example/cpp11/local/connect_pair.cpp
doc/html/boost_asio/example/cpp11/local/iostream_client.cpp
doc/html/boost_asio/example/cpp11/local/stream_client.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.hpp
doc/html/boost_asio/example/cpp11/http/server/server.cpp
doc/html/boost_asio/example/cpp11/http/server/server.hpp
doc/html/boost_asio/example/cpp11/http/server/connection.cpp
doc/html/boost_asio/example/cpp11/http/server/connection.hpp
doc/html/boost_asio/example/cpp11/multicast/sender.cpp
doc/html/boost_asio/example/cpp11/multicast/receiver.cpp
doc/html/boost_asio/example/cpp11/allocation/server.cpp
doc/html/boost_asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/handler_tracking/custom_tracking.hpp
doc/html/boost_asio/reference/windows__overlapped_handle/get_io_service.html
doc/html/boost_asio/reference/windows__overlapped_handle/get_io_context.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload2.html
doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__overlapped_handle/close/overload1.html
doc/html/boost_asio/reference/windows__overlapped_handle/close/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer.html
doc/html/boost_asio/reference/placeholders__results.html
doc/html/boost_asio/reference/async_read/overload6.html
doc/html/boost_asio/reference/async_read/overload4.html
doc/html/boost_asio/reference/async_read/overload5.html
doc/html/boost_asio/reference/async_read/overload1.html
doc/html/boost_asio/reference/async_read/overload3.html
doc/html/boost_asio/reference/async_read/overload2.html
doc/html/boost_asio/reference/placeholders__signal_number.html
doc/html/boost_asio/reference/ip__v6_only.html
doc/html/boost_asio/reference/signal_set.html
doc/html/boost_asio/reference/MoveAcceptHandler.html
doc/html/boost_asio/reference/yield_context.html
doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_read_some.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_write_some.html
doc/html/boost_asio/reference/posix__stream_descriptor/get_io_service.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/release.html
doc/html/boost_asio/reference/posix__stream_descriptor/get_io_context.html
doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/read_some/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/write_some/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor.html
doc/html/boost_asio/reference/posix__stream_descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/async_wait.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__stream_descriptor/bytes_readable.html
doc/html/boost_asio/reference/buffer_size.html
doc/html/boost_asio/reference/buffered_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_stream/get_io_context.html
doc/html/boost_asio/reference/io_context__strand/get_io_service.html
doc/html/boost_asio/reference/io_context__strand/context.html
doc/html/boost_asio/reference/io_context__strand/strand.html
doc/html/boost_asio/reference/io_context__strand/get_io_context.html
doc/html/boost_asio/reference/spawn/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor.html
doc/html/boost_asio/reference/MutableBufferSequence.html
doc/html/boost_asio/reference/transfer_at_least.html
doc/html/boost_asio/reference/ip__unicast__hops.html
doc/html/boost_asio/reference/async_read_until.html
doc/html/boost_asio/reference/ResolveHandler.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_/value.html
doc/html/boost_asio/reference/ssl__stream.html
doc/html/boost_asio/reference/generic__datagram_protocol.html
doc/html/boost_asio/reference/async_connect/overload6.html
doc/html/boost_asio/reference/async_connect/overload4.html
doc/html/boost_asio/reference/async_connect/overload5.html
doc/html/boost_asio/reference/async_connect/overload1.html
doc/html/boost_asio/reference/async_connect/overload3.html
doc/html/boost_asio/reference/async_connect/overload2.html
doc/html/boost_asio/reference/windows__overlapped_ptr/reset/overload2.html
doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr/overload2.html
doc/html/boost_asio/reference/windows__overlapped_ptr/reset.html
doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_.html
doc/html/boost_asio/reference/WaitHandler.html
doc/html/boost_asio/reference/ShutdownHandler.html
doc/html/boost_asio/reference/BufferedHandshakeHandler.html
doc/html/boost_asio/reference/windows__object_handle/object_handle.html
doc/html/boost_asio/reference/windows__object_handle/get_io_service.html
doc/html/boost_asio/reference/windows__object_handle/get_io_context.html
doc/html/boost_asio/reference/windows__object_handle/object_handle/overload1.html
doc/html/boost_asio/reference/windows__object_handle/object_handle/overload2.html
doc/html/boost_asio/reference/windows__object_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__object_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__object_handle/close/overload1.html
doc/html/boost_asio/reference/windows__object_handle/close/overload2.html
doc/html/boost_asio/reference/windows__object_handle/async_wait.html
doc/html/boost_asio/reference/ReadHandler.html
doc/html/boost_asio/reference/AcceptHandler.html
doc/html/boost_asio/reference/mutable_buffers_1/value_type.html
doc/html/boost_asio/reference/io_context/add_service.html
doc/html/boost_asio/reference/io_context/make_service.html
doc/html/boost_asio/reference/io_context__work/get_io_service.html
doc/html/boost_asio/reference/io_context__work/work/overload1.html
doc/html/boost_asio/reference/io_context__work/get_io_context.html
doc/html/boost_asio/reference/io_context__work/work.html
doc/html/boost_asio/reference/transfer_exactly.html
doc/html/boost_asio/reference/error__addrinfo_category.html
doc/html/boost_asio/reference/transfer_all.html
doc/html/boost_asio/reference/ssl__error__stream_category.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_.html
doc/html/boost_asio/reference/local__stream_protocol/acceptor.html
doc/html/boost_asio/reference/dynamic_string_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_string_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/WriteHandler.html
doc/html/boost_asio/reference/ConstBufferSequence.html
doc/html/boost_asio/reference/basic_streambuf.html
doc/html/boost_asio/reference/HandshakeHandler.html
doc/html/boost_asio/reference/buffered_write_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_write_stream/get_io_context.html
doc/html/boost_asio/reference/const_buffer.html
doc/html/boost_asio/reference/posix__descriptor/io_control/overload1.html
doc/html/boost_asio/reference/posix__descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__descriptor/get_io_service.html
doc/html/boost_asio/reference/posix__descriptor/descriptor.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__descriptor/release.html
doc/html/boost_asio/reference/posix__descriptor/get_io_context.html
doc/html/boost_asio/reference/posix__descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__descriptor/descriptor/overload1.html
doc/html/boost_asio/reference/posix__descriptor/descriptor/overload2.html
doc/html/boost_asio/reference/posix__descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__descriptor/async_wait.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__descriptor/bytes_readable.html
doc/html/boost_asio/reference/basic_io_object/get_io_service.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object/overload1.html
doc/html/boost_asio/reference/basic_io_object/get_io_context.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object.html
doc/html/boost_asio/reference/basic_io_object/executor_type.html
doc/html/boost_asio/reference/serial_port/async_read_some.html
doc/html/boost_asio/reference/serial_port/async_write_some.html
doc/html/boost_asio/reference/serial_port/get_io_service.html
doc/html/boost_asio/reference/serial_port/serial_port/overload4.html
doc/html/boost_asio/reference/serial_port/serial_port/overload1.html
doc/html/boost_asio/reference/serial_port/serial_port/overload3.html
doc/html/boost_asio/reference/serial_port/serial_port/overload2.html
doc/html/boost_asio/reference/serial_port/get_io_context.html
doc/html/boost_asio/reference/serial_port/cancel/overload1.html
doc/html/boost_asio/reference/serial_port/cancel/overload2.html
doc/html/boost_asio/reference/serial_port/read_some/overload1.html
doc/html/boost_asio/reference/serial_port/serial_port.html
doc/html/boost_asio/reference/serial_port/write_some/overload1.html
doc/html/boost_asio/reference/serial_port/close/overload1.html
doc/html/boost_asio/reference/serial_port/close/overload2.html
doc/html/boost_asio/reference/basic_socket/keep_alive.html
doc/html/boost_asio/reference/basic_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_socket/async_connect.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/get_io_service.html
doc/html/boost_asio/reference/basic_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/do_not_route.html
doc/html/boost_asio/reference/basic_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload4.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload1.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload3.html
doc/html/boost_asio/reference/basic_socket/basic_socket/overload2.html
doc/html/boost_asio/reference/basic_socket/get_io_context.html
doc/html/boost_asio/reference/basic_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket/broadcast.html
doc/html/boost_asio/reference/basic_socket/reuse_address.html
doc/html/boost_asio/reference/basic_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_socket/debug.html
doc/html/boost_asio/reference/basic_socket/linger.html
doc/html/boost_asio/reference/basic_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket/release/overload1.html
doc/html/boost_asio/reference/basic_socket/release/overload2.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/basic_socket.html
doc/html/boost_asio/reference/basic_socket/open/overload1.html
doc/html/boost_asio/reference/basic_socket/open/overload2.html
doc/html/boost_asio/reference/basic_socket/close/overload1.html
doc/html/boost_asio/reference/basic_socket/close/overload2.html
doc/html/boost_asio/reference/basic_socket/async_wait.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket/get_option/overload2.html
doc/html/boost_asio/reference/socket_base/keep_alive.html
doc/html/boost_asio/reference/socket_base/send_buffer_size.html
doc/html/boost_asio/reference/socket_base/out_of_band_inline.html
doc/html/boost_asio/reference/socket_base/do_not_route.html
doc/html/boost_asio/reference/socket_base/send_low_watermark.html
doc/html/boost_asio/reference/socket_base/enable_connection_aborted.html
doc/html/boost_asio/reference/socket_base/broadcast.html
doc/html/boost_asio/reference/socket_base/reuse_address.html
doc/html/boost_asio/reference/socket_base/receive_buffer_size.html
doc/html/boost_asio/reference/socket_base/debug.html
doc/html/boost_asio/reference/socket_base/linger.html
doc/html/boost_asio/reference/socket_base/bytes_readable.html
doc/html/boost_asio/reference/socket_base/receive_low_watermark.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload1.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload2.html
doc/html/boost_asio/reference/ip__basic_endpoint/address.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload3.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload2.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_/value.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_/value.html
doc/html/boost_asio/reference/thread_pool.html
doc/html/boost_asio/reference/ip__multicast__leave_group.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/get_io_service.html
doc/html/boost_asio/reference/basic_deadline_timer/get_io_context.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/async_wait.html
doc/html/boost_asio/reference/async_write_at/overload4.html
doc/html/boost_asio/reference/async_write_at/overload1.html
doc/html/boost_asio/reference/async_write_at/overload3.html
doc/html/boost_asio/reference/async_write_at/overload2.html
doc/html/boost_asio/reference/error__ssl_category.html
doc/html/boost_asio/reference/error__netdb_category.html
doc/html/boost_asio/reference/basic_seq_packet_socket/keep_alive.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_connect.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_service.html
doc/html/boost_asio/reference/basic_seq_packet_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/do_not_route.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_context.html
doc/html/boost_asio/reference/basic_seq_packet_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_seq_packet_socket/broadcast.html
doc/html/boost_asio/reference/basic_seq_packet_socket/reuse_address.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_send.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload4.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/debug.html
doc/html/boost_asio/reference/basic_seq_packet_socket/linger.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_wait.html
doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload2.html
doc/html/boost_asio/reference/IteratorConnectHandler.html
doc/html/boost_asio/reference/experimental__detached_t.html
doc/html/boost_asio/reference/system_timer.html
doc/html/boost_asio/reference/buffer.html
doc/html/boost_asio/reference/connect/overload11.html
doc/html/boost_asio/reference/connect/overload10.html
doc/html/boost_asio/reference/connect/overload6.html
doc/html/boost_asio/reference/connect/overload4.html
doc/html/boost_asio/reference/connect/overload7.html
doc/html/boost_asio/reference/connect/overload9.html
doc/html/boost_asio/reference/connect/overload5.html
doc/html/boost_asio/reference/connect/overload1.html
doc/html/boost_asio/reference/connect/overload3.html
doc/html/boost_asio/reference/connect/overload8.html
doc/html/boost_asio/reference/connect/overload12.html
doc/html/boost_asio/reference/connect/overload2.html
doc/html/boost_asio/reference/high_resolution_timer.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_.html
doc/html/boost_asio/reference/ssl__rfc2818_verification.html
doc/html/boost_asio/reference/error__system_category.html
doc/html/boost_asio/reference/placeholders__bytes_transferred.html
doc/html/boost_asio/reference/thread_pool/add_service.html
doc/html/boost_asio/reference/thread_pool/make_service.html
doc/html/boost_asio/reference/null_buffers/value_type.html
doc/html/boost_asio/reference/windows__stream_handle/async_read_some.html
doc/html/boost_asio/reference/windows__stream_handle/async_write_some.html
doc/html/boost_asio/reference/windows__stream_handle/get_io_service.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle.html
doc/html/boost_asio/reference/windows__stream_handle/get_io_context.html
doc/html/boost_asio/reference/windows__stream_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__stream_handle/read_some/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/write_some/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/close/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/close/overload2.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload1.html
doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload2.html
doc/html/boost_asio/reference/SignalHandler.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_after.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_at/overload2.html
doc/html/boost_asio/reference/signal_set/signal_set.html
doc/html/boost_asio/reference/signal_set/get_io_service.html
doc/html/boost_asio/reference/signal_set/get_io_context.html
doc/html/boost_asio/reference/signal_set/cancel/overload1.html
doc/html/boost_asio/reference/signal_set/cancel/overload2.html
doc/html/boost_asio/reference/signal_set/signal_set/overload4.html
doc/html/boost_asio/reference/signal_set/signal_set/overload1.html
doc/html/boost_asio/reference/signal_set/signal_set/overload3.html
doc/html/boost_asio/reference/signal_set/signal_set/overload2.html
doc/html/boost_asio/reference/signal_set/async_wait.html
doc/html/boost_asio/reference/RangeConnectHandler.html
doc/html/boost_asio/reference/io_context__service/get_io_service.html
doc/html/boost_asio/reference/io_context__service/get_io_context.html
doc/html/boost_asio/reference/io_context__service/service.html
doc/html/boost_asio/reference/streambuf.html
doc/html/boost_asio/reference/ip__multicast__outbound_interface.html
doc/html/boost_asio/reference/io_service.html
doc/html/boost_asio/reference/async_completion/completion_handler_type.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_/value.html
doc/html/boost_asio/reference/ip__tcp/no_delay.html
doc/html/boost_asio/reference/ip__tcp/acceptor.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload3.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload2.html
doc/html/boost_asio/reference/ip__address/to_v4.html
doc/html/boost_asio/reference/ip__address/address/overload3.html
doc/html/boost_asio/reference/ip__address/address/overload2.html
doc/html/boost_asio/reference/ip__address/address.html
doc/html/boost_asio/reference/ip__address/operator_eq_.html
doc/html/boost_asio/reference/ip__address/to_v6.html
doc/html/boost_asio/reference/placeholders__iterator.html
doc/html/boost_asio/reference/basic_socket_acceptor/keep_alive.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_io_service.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept.html
doc/html/boost_asio/reference/basic_socket_acceptor/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept.html
doc/html/boost_asio/reference/basic_socket_acceptor/do_not_route.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_io_context.html
doc/html/boost_asio/reference/basic_socket_acceptor/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket_acceptor/broadcast.html
doc/html/boost_asio/reference/basic_socket_acceptor/reuse_address.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/listen/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/debug.html
doc/html/boost_asio/reference/basic_socket_acceptor/linger.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload11.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload10.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload7.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload9.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload8.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload12.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/close/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_wait.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/bytes_readable.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload2.html
doc/html/boost_asio/reference/execution_context/add_service.html
doc/html/boost_asio/reference/execution_context/make_service.html
doc/html/boost_asio/reference/spawn.html
doc/html/boost_asio/reference/ip__basic_resolver/get_io_service.html
doc/html/boost_asio/reference/ip__basic_resolver/cancel.html
doc/html/boost_asio/reference/ip__basic_resolver/get_io_context.html
doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver/overload1.html
doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload6.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload4.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload5.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload1.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload3.html
doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload2.html
doc/html/boost_asio/reference/buffer_cast.html
doc/html/boost_asio/reference/buffer_sequence_begin.html
doc/html/boost_asio/reference/basic_waitable_timer.html
doc/html/boost_asio/reference/async_read_until/overload6.html
doc/html/boost_asio/reference/async_read_until/overload4.html
doc/html/boost_asio/reference/async_read_until/overload7.html
doc/html/boost_asio/reference/async_read_until/overload5.html
doc/html/boost_asio/reference/async_read_until/overload1.html
doc/html/boost_asio/reference/async_read_until/overload3.html
doc/html/boost_asio/reference/async_read_until/overload8.html
doc/html/boost_asio/reference/async_read_until/overload2.html
doc/html/boost_asio/reference/write/overload10.html
doc/html/boost_asio/reference/write/overload6.html
doc/html/boost_asio/reference/write/overload9.html
doc/html/boost_asio/reference/write/overload5.html
doc/html/boost_asio/reference/write/overload1.html
doc/html/boost_asio/reference/write/overload3.html
doc/html/boost_asio/reference/write/overload2.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_/value.html
doc/html/boost_asio/reference/async_write/overload6.html
doc/html/boost_asio/reference/async_write/overload4.html
doc/html/boost_asio/reference/async_write/overload5.html
doc/html/boost_asio/reference/async_write/overload1.html
doc/html/boost_asio/reference/async_write/overload3.html
doc/html/boost_asio/reference/async_write/overload2.html
doc/html/boost_asio/reference/generic__stream_protocol.html
doc/html/boost_asio/reference/steady_timer.html
doc/html/boost_asio/reference/const_buffers_1/value_type.html
doc/html/boost_asio/reference/write_at/overload6.html
doc/html/boost_asio/reference/write_at/overload5.html
doc/html/boost_asio/reference/write_at/overload1.html
doc/html/boost_asio/reference/write_at/overload3.html
doc/html/boost_asio/reference/write_at/overload2.html
doc/html/boost_asio/reference/read_until/overload11.html
doc/html/boost_asio/reference/read_until/overload10.html
doc/html/boost_asio/reference/read_until/overload13.html
doc/html/boost_asio/reference/read_until/overload7.html
doc/html/boost_asio/reference/read_until/overload9.html
doc/html/boost_asio/reference/read_until/overload5.html
doc/html/boost_asio/reference/read_until/overload1.html
doc/html/boost_asio/reference/read_until/overload14.html
doc/html/boost_asio/reference/read_until/overload3.html
doc/html/boost_asio/reference/read_until/overload16.html
doc/html/boost_asio/reference/read_until/overload15.html
doc/html/boost_asio/reference/read_until/overload12.html
doc/html/boost_asio/reference/ip__multicast__hops.html
doc/html/boost_asio/reference/generic__raw_protocol.html
doc/html/boost_asio/reference/use_future_t.html
doc/html/boost_asio/reference/ssl__stream/get_io_service.html
doc/html/boost_asio/reference/ssl__stream/get_io_context.html
doc/html/boost_asio/reference/ssl__stream/native_handle.html
doc/html/boost_asio/reference/basic_stream_socket/keep_alive.html
doc/html/boost_asio/reference/basic_stream_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_read_some.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_connect.html
doc/html/boost_asio/reference/basic_stream_socket/async_write_some.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/get_io_service.html
doc/html/boost_asio/reference/basic_stream_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/do_not_route.html
doc/html/boost_asio/reference/basic_stream_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/get_io_context.html
doc/html/boost_asio/reference/basic_stream_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_stream_socket/broadcast.html
doc/html/boost_asio/reference/basic_stream_socket/reuse_address.html
doc/html/boost_asio/reference/basic_stream_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/read_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/write_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/debug.html
doc/html/boost_asio/reference/basic_stream_socket/linger.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload4.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_wait.html
doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/get_io_service.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/get_io_context.html
doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle.html
doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/read_some_at/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/async_read_some_at.html
doc/html/boost_asio/reference/windows__random_access_handle/write_some_at/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/close/overload1.html
doc/html/boost_asio/reference/windows__random_access_handle/close/overload2.html
doc/html/boost_asio/reference/windows__random_access_handle/async_write_some_at.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_.html
doc/html/boost_asio/reference/dynamic_vector_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_vector_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/buffer_copy.html
doc/html/boost_asio/reference/add_service.html
doc/html/boost_asio/reference/Handler.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/get_io_service.html
doc/html/boost_asio/reference/basic_waitable_timer/get_io_context.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_after.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/async_wait.html
doc/html/boost_asio/reference/buffered_read_stream/get_io_service.html
doc/html/boost_asio/reference/buffered_read_stream/get_io_context.html
doc/html/boost_asio/reference/deadline_timer.html
doc/html/boost_asio/reference/ip__multicast__join_group.html
doc/html/boost_asio/reference/io_context.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_.html
doc/html/boost_asio/reference/buffer_sequence_end.html
doc/html/boost_asio/reference/read/overload10.html
doc/html/boost_asio/reference/read/overload6.html
doc/html/boost_asio/reference/read/overload9.html
doc/html/boost_asio/reference/read/overload5.html
doc/html/boost_asio/reference/read/overload1.html
doc/html/boost_asio/reference/read/overload3.html
doc/html/boost_asio/reference/read/overload2.html
doc/html/boost_asio/reference/dynamic_buffer.html
doc/html/boost_asio/reference/read_until.html
doc/html/boost_asio/reference/ip__basic_resolver_query/hints.html
doc/html/boost_asio/reference/posix__descriptor_base/bytes_readable.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_.html
doc/html/boost_asio/reference/ConnectHandler.html
doc/html/boost_asio/reference/basic_raw_socket/keep_alive.html
doc/html/boost_asio/reference/basic_raw_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_connect.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/get_io_service.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/do_not_route.html
doc/html/boost_asio/reference/basic_raw_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/get_io_context.html
doc/html/boost_asio/reference/basic_raw_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_raw_socket/broadcast.html
doc/html/boost_asio/reference/basic_raw_socket/reuse_address.html
doc/html/boost_asio/reference/basic_raw_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/debug.html
doc/html/boost_asio/reference/basic_raw_socket/linger.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket.html
doc/html/boost_asio/reference/basic_raw_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload4.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/async_wait.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/keep_alive.html
doc/html/boost_asio/reference/basic_datagram_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_connect.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/get_io_service.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/do_not_route.html
doc/html/boost_asio/reference/basic_datagram_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/get_io_context.html
doc/html/boost_asio/reference/basic_datagram_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_datagram_socket/broadcast.html
doc/html/boost_asio/reference/basic_datagram_socket/reuse_address.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/debug.html
doc/html/boost_asio/reference/basic_datagram_socket/linger.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload4.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/async_wait.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload2.html
doc/html/boost_asio/reference/placeholders__endpoint.html
doc/html/boost_asio/reference/mutable_buffer.html
doc/html/boost_asio/reference/ip__multicast__enable_loopback.html
doc/html/boost_asio/reference/io_context__strand.html
doc/html/boost_asio/reference/async_read_at/overload4.html
doc/html/boost_asio/reference/async_read_at/overload1.html
doc/html/boost_asio/reference/async_read_at/overload3.html
doc/html/boost_asio/reference/async_read_at/overload2.html
doc/html/boost_asio/reference/basic_streambuf_ref/const_buffers_type.html
doc/html/boost_asio/reference/basic_streambuf_ref/mutable_buffers_type.html
doc/html/boost_asio/reference/read_at/overload6.html
doc/html/boost_asio/reference/read_at/overload5.html
doc/html/boost_asio/reference/read_at/overload1.html
doc/html/boost_asio/reference/read_at/overload3.html
doc/html/boost_asio/reference/read_at/overload2.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_after.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_at/overload2.html
doc/html/boost_asio/reference/error__misc_category.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_/value.html
doc/html/boost_asio/reference/system_context/add_service.html
doc/html/boost_asio/reference/system_context/make_service.html
doc/html/boost_asio/overview/posix/fork.html
doc/html/boost_asio/overview/posix/stream_descriptor.html
doc/html/boost_asio/overview/networking/protocols.html
doc/html/boost_asio/overview/networking/other_protocols.html
doc/html/boost_asio/overview/signals.html
doc/html/boost_asio/overview/cpp2011/futures.html
doc/html/boost_asio/overview/cpp2011/move_handlers.html
doc/html/boost_asio/overview/core/allocation.html
doc/html/boost_asio/overview/core/coroutines_ts.html
doc/html/boost_asio/overview/core/coroutine.html
doc/html/boost_asio/overview/core/line_based.html
doc/html/boost_asio/overview/core/spawn.html
doc/html/boost_asio/overview/core/strands.html
doc/html/boost_asio/overview/ssl.html
doc/html/boost_asio/net_ts.html
doc/html/boost/process/on_exit.html
doc/html/boost/process/spawn.html
doc/html/boost/process/async_pipe.html
doc/html/boost/process/std_in.html
doc/html/boost/process/std_out.html
boost/process/system.hpp
boost/process/io.hpp
boost/process/async_pipe.hpp
boost/process/spawn.hpp
boost/process/async_system.hpp
boost/process/async.hpp
boost/process/detail/windows/io_context_ref.hpp
boost/process/detail/windows/async_in.hpp
boost/process/detail/windows/async_pipe.hpp
boost/process/detail/windows/async_out.hpp
boost/process/detail/traits/async.hpp
boost/process/detail/posix/io_context_ref.hpp
boost/process/detail/posix/sigchld_service.hpp
boost/process/detail/posix/async_in.hpp
boost/process/detail/posix/async_pipe.hpp
boost/process/detail/posix/async_out.hpp
boost/process/detail/async_handler.hpp
boost/log/sinks/syslog_backend.hpp
boost/beast/websocket/stream.hpp
boost/beast/websocket/impl/ssl.ipp
boost/beast/websocket/impl/stream.ipp
boost/beast/websocket/impl/close.ipp
boost/beast/websocket/impl/read.ipp
boost/beast/websocket/impl/teardown.ipp
boost/beast/websocket/impl/handshake.ipp
boost/beast/websocket/impl/ping.ipp
boost/beast/websocket/impl/accept.ipp
boost/beast/websocket/impl/write.ipp
boost/beast/websocket/ssl.hpp
boost/beast/websocket/rfc6455.hpp
boost/beast/websocket/teardown.hpp
boost/beast/websocket/role.hpp
boost/beast/websocket/detail/pausation.hpp
boost/beast/websocket/detail/utf8_checker.hpp
boost/beast/websocket/detail/frame.hpp
boost/beast/websocket/detail/mask.hpp
boost/beast/websocket/detail/stream_base.hpp
boost/beast/experimental/test/stream.hpp
boost/beast/experimental/test/impl/stream.ipp
boost/beast/experimental/http/impl/icy_stream.ipp
boost/beast/experimental/http/icy_stream.hpp
boost/beast/experimental/core/timeout_socket.hpp
boost/beast/experimental/core/impl/timeout_socket.hpp
boost/beast/experimental/core/impl/timeout_service.ipp
boost/beast/experimental/core/impl/flat_stream.ipp
boost/beast/experimental/core/flat_stream.hpp
boost/beast/experimental/core/ssl_stream.hpp
boost/beast/experimental/core/timeout_service.hpp
boost/beast/experimental/core/detail/service_base.hpp
boost/beast/experimental/core/detail/impl/timeout_service.ipp
boost/beast/experimental/core/detail/flat_stream.hpp
boost/beast/experimental/core/detail/timeout_service.hpp
boost/beast/http/span_body.hpp
boost/beast/http/fields.hpp
boost/beast/http/type_traits.hpp
boost/beast/http/basic_dynamic_body.hpp
boost/beast/http/serializer.hpp
boost/beast/http/vector_body.hpp
boost/beast/http/basic_parser.hpp
boost/beast/http/string_body.hpp
boost/beast/http/basic_file_body.hpp
boost/beast/http/buffer_body.hpp
boost/beast/http/impl/serializer.ipp
boost/beast/http/impl/chunk_encode.ipp
boost/beast/http/impl/read.ipp
boost/beast/http/impl/fields.ipp
boost/beast/http/impl/file_body_win32.ipp
boost/beast/http/impl/basic_parser.ipp
boost/beast/http/impl/write.ipp
boost/beast/http/chunk_encode.hpp
boost/beast/http/write.hpp
boost/beast/http/error.hpp
boost/beast/http/empty_body.hpp
boost/beast/http/parser.hpp
boost/beast/http/read.hpp
boost/beast/http/detail/chunk_encode.hpp
boost/beast/core/type_traits.hpp
boost/beast/core/buffers_suffix.hpp
boost/beast/core/ostream.hpp
boost/beast/core/buffers_prefix.hpp
boost/beast/core/multi_buffer.hpp
boost/beast/core/impl/buffers_adapter.ipp
boost/beast/core/impl/buffers_prefix.ipp
boost/beast/core/impl/buffered_read_stream.ipp
boost/beast/core/impl/buffers_suffix.ipp
boost/beast/core/impl/multi_buffer.ipp
boost/beast/core/impl/buffers_cat.ipp
boost/beast/core/impl/static_buffer.ipp
boost/beast/core/impl/flat_static_buffer.ipp
boost/beast/core/impl/flat_buffer.ipp
boost/beast/core/impl/handler_ptr.ipp
boost/beast/core/impl/read_size.ipp
boost/beast/core/buffers_to_string.hpp
boost/beast/core/buffered_read_stream.hpp
boost/beast/core/static_buffer.hpp
boost/beast/core/bind_handler.hpp
boost/beast/core/flat_static_buffer.hpp
boost/beast/core/buffers_cat.hpp
boost/beast/core/buffers_adapter.hpp
boost/beast/core/flat_buffer.hpp
boost/beast/core/detail/type_traits.hpp
boost/beast/core/detail/buffers_ref.hpp
boost/beast/core/detail/bind_handler.hpp
boost/asio/basic_socket_acceptor.hpp
boost/asio/windows/basic_object_handle.hpp
boost/asio/windows/basic_handle.hpp
boost/asio/windows/stream_handle.hpp
boost/asio/windows/random_access_handle.hpp
boost/asio/windows/overlapped_handle.hpp
boost/asio/windows/random_access_handle_service.hpp
boost/asio/windows/stream_handle_service.hpp
boost/asio/windows/overlapped_ptr.hpp
boost/asio/windows/basic_stream_handle.hpp
boost/asio/windows/object_handle_service.hpp
boost/asio/windows/basic_random_access_handle.hpp
boost/asio/windows/object_handle.hpp
boost/asio/use_future.hpp
boost/asio/basic_raw_socket.hpp
boost/asio/waitable_timer_service.hpp
boost/asio/basic_deadline_timer.hpp
boost/asio/ts/netfwd.hpp
boost/asio/generic/seq_packet_protocol.hpp
boost/asio/generic/datagram_protocol.hpp
boost/asio/generic/raw_protocol.hpp
boost/asio/generic/stream_protocol.hpp
boost/asio/generic/basic_endpoint.hpp
boost/asio/generic/detail/endpoint.hpp
boost/asio/generic/detail/impl/endpoint.ipp
boost/asio/seq_packet_socket_service.hpp
boost/asio/io_context.hpp
boost/asio/executor.hpp
boost/asio/uses_executor.hpp
boost/asio/serial_port_service.hpp
boost/asio/posix/stream_descriptor.hpp
boost/asio/posix/basic_stream_descriptor.hpp
boost/asio/posix/stream_descriptor_service.hpp
boost/asio/posix/basic_descriptor.hpp
boost/asio/posix/descriptor.hpp
boost/asio/posix/descriptor_base.hpp
boost/asio/ssl/stream.hpp
boost/asio/ssl/impl/context.ipp
boost/asio/ssl/impl/context.hpp
boost/asio/ssl/impl/error.ipp
boost/asio/ssl/error.hpp
boost/asio/ssl/context.hpp
boost/asio/ssl/rfc2818_verification.hpp
boost/asio/ssl/context_base.hpp
boost/asio/ssl/stream_base.hpp
boost/asio/ssl/detail/io.hpp
boost/asio/ssl/detail/stream_core.hpp
boost/asio/ssl/detail/impl/openssl_init.ipp
boost/asio/ssl/detail/impl/engine.ipp
boost/asio/ssl/detail/openssl_init.hpp
boost/asio/ssl/detail/buffered_handshake_op.hpp
boost/asio/ssl/detail/engine.hpp
boost/asio/ssl/detail/read_op.hpp
boost/asio/ssl/detail/write_op.hpp
boost/asio/basic_serial_port.hpp
boost/asio/coroutine.hpp
boost/asio/socket_base.hpp
boost/asio/stream_socket_service.hpp
boost/asio/buffers_iterator.hpp
boost/asio/placeholders.hpp
boost/asio/serial_port.hpp
boost/asio/connect.hpp
boost/asio/basic_io_object.hpp
boost/asio/write_at.hpp
boost/asio/io_context_strand.hpp
boost/asio/local/connect_pair.hpp
boost/asio/local/datagram_protocol.hpp
boost/asio/local/stream_protocol.hpp
boost/asio/local/basic_endpoint.hpp
boost/asio/local/detail/endpoint.hpp
boost/asio/local/detail/impl/endpoint.ipp
boost/asio/experimental/impl/co_spawn.hpp
boost/asio/experimental/impl/detached.hpp
boost/asio/experimental/detached.hpp
boost/asio/impl/io_context.hpp
boost/asio/impl/execution_context.ipp
boost/asio/impl/connect.hpp
boost/asio/impl/write_at.hpp
boost/asio/impl/serial_port_base.ipp
boost/asio/impl/buffered_write_stream.hpp
boost/asio/impl/write.hpp
boost/asio/impl/buffered_read_stream.hpp
boost/asio/impl/read_until.hpp
boost/asio/impl/spawn.hpp
boost/asio/impl/io_context.ipp
boost/asio/impl/read_at.hpp
boost/asio/impl/read.hpp
boost/asio/basic_waitable_timer.hpp
boost/asio/basic_socket_iostream.hpp
boost/asio/execution_context.hpp
boost/asio/datagram_socket_service.hpp
boost/asio/basic_streambuf.hpp
boost/asio/basic_signal_set.hpp
boost/asio/completion_condition.hpp
boost/asio/handler_invoke_hook.hpp
boost/asio/buffered_write_stream.hpp
boost/asio/basic_socket_streambuf.hpp
boost/asio/write.hpp
boost/asio/error.hpp
boost/asio/is_executor.hpp
boost/asio/buffered_read_stream.hpp
boost/asio/buffer.hpp
boost/asio/read_until.hpp
boost/asio/basic_datagram_socket.hpp
boost/asio/spawn.hpp
boost/asio/basic_seq_packet_socket.hpp
boost/asio/raw_socket_service.hpp
boost/asio/thread_pool.hpp
boost/asio/basic_socket.hpp
boost/asio/async_result.hpp
boost/asio/ip/basic_resolver.hpp
boost/asio/ip/address.hpp
boost/asio/ip/basic_resolver_results.hpp
boost/asio/ip/multicast.hpp
boost/asio/ip/basic_resolver_query.hpp
boost/asio/ip/v6_only.hpp
boost/asio/ip/address_v4.hpp
boost/asio/ip/impl/address.hpp
boost/asio/ip/impl/host_name.ipp
boost/asio/ip/impl/address_v4.hpp
boost/asio/ip/impl/basic_endpoint.hpp
boost/asio/ip/impl/address.ipp
boost/asio/ip/impl/network_v4.ipp
boost/asio/ip/impl/address_v4.ipp
boost/asio/ip/impl/network_v6.ipp
boost/asio/ip/impl/address_v6.ipp
boost/asio/ip/impl/network_v4.hpp
boost/asio/ip/impl/network_v6.hpp
boost/asio/ip/impl/address_v6.hpp
boost/asio/ip/udp.hpp
boost/asio/ip/unicast.hpp
boost/asio/ip/basic_resolver_entry.hpp
boost/asio/ip/basic_resolver_iterator.hpp
boost/asio/ip/basic_endpoint.hpp
boost/asio/ip/tcp.hpp
boost/asio/ip/network_v4.hpp
boost/asio/ip/icmp.hpp
boost/asio/ip/network_v6.hpp
boost/asio/ip/address_v6.hpp
boost/asio/ip/resolver_service.hpp
boost/asio/ip/detail/socket_option.hpp
boost/asio/ip/detail/endpoint.hpp
boost/asio/ip/detail/impl/endpoint.ipp
boost/asio/read_at.hpp
boost/asio/signal_set_service.hpp
boost/asio/basic_stream_socket.hpp
boost/asio/read.hpp
boost/asio/socket_acceptor_service.hpp
boost/asio/deadline_timer_service.hpp
boost/asio/buffered_stream.hpp
boost/asio/signal_set.hpp
boost/asio/detail/winrt_timer_scheduler.hpp
boost/asio/detail/socket_option.hpp
boost/asio/detail/reactive_socket_recv_op.hpp
boost/asio/detail/win_iocp_socket_connect_op.hpp
boost/asio/detail/winapp_thread.hpp
boost/asio/detail/timer_queue.hpp
boost/asio/detail/reactive_wait_op.hpp
boost/asio/detail/reactive_socket_service_base.hpp
boost/asio/detail/posix_static_mutex.hpp
boost/asio/detail/win_iocp_overlapped_ptr.hpp
boost/asio/detail/win_iocp_socket_recvmsg_op.hpp
boost/asio/detail/reactive_serial_port_service.hpp
boost/asio/detail/winrt_ssocket_service.hpp
boost/asio/detail/epoll_reactor.hpp
boost/asio/detail/resolve_endpoint_op.hpp
boost/asio/detail/winrt_resolver_service.hpp
boost/asio/detail/win_object_handle_service.hpp
boost/asio/detail/select_reactor.hpp
boost/asio/detail/consuming_buffers.hpp
boost/asio/detail/reactive_socket_accept_op.hpp
boost/asio/detail/strand_service.hpp
boost/asio/detail/handler_alloc_helpers.hpp
boost/asio/detail/win_mutex.hpp
boost/asio/detail/signal_handler.hpp
boost/asio/detail/win_iocp_socket_service_base.hpp
boost/asio/detail/conditionally_enabled_event.hpp
boost/asio/detail/reactive_socket_send_op.hpp
boost/asio/detail/reactive_null_buffers_op.hpp
boost/asio/detail/wait_handler.hpp
boost/asio/detail/std_static_mutex.hpp
boost/asio/detail/handler_invoke_helpers.hpp
boost/asio/detail/win_iocp_handle_read_op.hpp
boost/asio/detail/reactive_socket_recvfrom_op.hpp
boost/asio/detail/handler_tracking.hpp
boost/asio/detail/buffered_stream_storage.hpp
boost/asio/detail/win_iocp_socket_accept_op.hpp
boost/asio/detail/dev_poll_reactor.hpp
boost/asio/detail/is_buffer_sequence.hpp
boost/asio/detail/thread_group.hpp
boost/asio/detail/null_thread.hpp
boost/asio/detail/reactor_op_queue.hpp
boost/asio/detail/winsock_init.hpp
boost/asio/detail/win_iocp_null_buffers_op.hpp
boost/asio/detail/impl/winrt_timer_scheduler.hpp
boost/asio/detail/impl/win_static_mutex.ipp
boost/asio/detail/impl/winrt_timer_scheduler.ipp
boost/asio/detail/impl/strand_service.ipp
boost/asio/detail/impl/strand_executor_service.ipp
boost/asio/detail/impl/kqueue_reactor.ipp
boost/asio/detail/impl/win_thread.ipp
boost/asio/detail/impl/handler_tracking.ipp
boost/asio/detail/impl/pipe_select_interrupter.ipp
boost/asio/detail/impl/resolver_service_base.ipp
boost/asio/detail/impl/service_registry.ipp
boost/asio/detail/impl/posix_thread.ipp
boost/asio/detail/impl/posix_mutex.ipp
boost/asio/detail/impl/select_reactor.hpp
boost/asio/detail/impl/win_iocp_socket_service_base.ipp
boost/asio/detail/impl/strand_service.hpp
boost/asio/detail/impl/throw_error.ipp
boost/asio/detail/impl/reactive_descriptor_service.ipp
boost/asio/detail/impl/eventfd_select_interrupter.ipp
boost/asio/detail/impl/posix_event.ipp
boost/asio/detail/impl/socket_ops.ipp
boost/asio/detail/impl/win_mutex.ipp
boost/asio/detail/impl/buffer_sequence_adapter.ipp
boost/asio/detail/impl/dev_poll_reactor.hpp
boost/asio/detail/impl/descriptor_ops.ipp
boost/asio/detail/impl/posix_tss_ptr.ipp
boost/asio/detail/impl/select_reactor.ipp
boost/asio/detail/impl/socket_select_interrupter.ipp
boost/asio/detail/impl/epoll_reactor.ipp
boost/asio/detail/impl/win_event.ipp
boost/asio/detail/impl/scheduler.ipp
boost/asio/detail/impl/win_iocp_serial_port_service.ipp
boost/asio/detail/impl/win_tss_ptr.ipp
boost/asio/detail/impl/reactive_socket_service_base.ipp
boost/asio/detail/impl/win_iocp_io_context.ipp
boost/asio/detail/impl/winrt_ssocket_service_base.ipp
boost/asio/detail/impl/win_object_handle_service.ipp
boost/asio/detail/impl/winsock_init.ipp
boost/asio/detail/impl/win_iocp_handle_service.ipp
boost/asio/detail/impl/dev_poll_reactor.ipp
boost/asio/detail/impl/signal_set_service.ipp
boost/asio/detail/impl/win_iocp_io_context.hpp
boost/asio/detail/impl/reactive_serial_port_service.ipp
boost/asio/detail/std_mutex.hpp
boost/asio/detail/resolve_query_op.hpp
boost/asio/detail/reactive_socket_sendto_op.hpp
boost/asio/detail/winrt_utils.hpp
boost/asio/detail/descriptor_ops.hpp
boost/asio/detail/win_iocp_serial_port_service.hpp
boost/asio/detail/service_registry.hpp
boost/asio/detail/null_reactor.hpp
boost/asio/detail/descriptor_write_op.hpp
boost/asio/detail/string_view.hpp
boost/asio/detail/buffer_sequence_adapter.hpp
boost/asio/detail/kqueue_reactor.hpp
boost/asio/detail/winrt_socket_connect_op.hpp
boost/asio/detail/win_iocp_socket_send_op.hpp
boost/asio/detail/winrt_resolve_op.hpp
boost/asio/detail/win_iocp_socket_recv_op.hpp
boost/asio/detail/win_iocp_socket_recvfrom_op.hpp
boost/asio/detail/conditionally_enabled_mutex.hpp
boost/asio/detail/null_mutex.hpp
boost/asio/detail/handler_cont_helpers.hpp
boost/asio/detail/resolver_service_base.hpp
boost/asio/detail/reactive_socket_service.hpp
boost/asio/detail/reactive_descriptor_service.hpp
boost/asio/detail/winrt_async_manager.hpp
boost/asio/detail/posix_mutex.hpp
boost/asio/detail/winrt_socket_recv_op.hpp
boost/asio/detail/noncopyable.hpp
boost/asio/detail/winrt_socket_send_op.hpp
boost/asio/detail/null_static_mutex.hpp
boost/asio/detail/wince_thread.hpp
boost/asio/detail/scheduler.hpp
boost/asio/detail/reactive_socket_connect_op.hpp
boost/asio/detail/signal_set_service.hpp
boost/asio/detail/completion_handler.hpp
boost/asio/detail/win_iocp_overlapped_op.hpp
boost/asio/detail/win_iocp_handle_write_op.hpp
boost/asio/detail/winrt_ssocket_service_base.hpp
boost/asio/detail/win_iocp_wait_op.hpp
boost/asio/detail/reactive_socket_recvmsg_op.hpp
boost/asio/detail/win_iocp_socket_service.hpp
boost/asio/detail/null_socket_service.hpp
boost/asio/detail/win_iocp_handle_service.hpp
boost/asio/detail/handler_type_requirements.hpp
boost/asio/detail/deadline_timer_service.hpp
boost/asio/detail/win_iocp_io_context.hpp
boost/asio/detail/win_static_mutex.hpp
boost/asio/detail/descriptor_read_op.hpp
boost/asio/detail/resolver_service.hpp
~/boost_1_69_0/tools/build$ sh bootstrap.sh # Компилируем boost
Bootstrapping the build engine with toolset gcc... 
~/boost_1_69_0/tools/build$ ./b2 install --prefix=~//boost-libs #компилируем в директорию boost/libs
...
~/boost_1_69_0/libs$ du -sh # сколько всего весит папка
444M
~/boost_1_69_0/libs$ du -sh * # выводим вес каждого файла
828K	accumulators
5,5M	algorithm
112K	align
112K	any
112K	array
6,9M	asio
172K	assert
344K	assign
272K	atomic
23M	beast
3,0M	bimap
744K	bind
1,4M	callable_traits
1,2M	chrono
644K	circular_buffer
28K	compatibility
5,0M	compute
444K	concept_check
3,7M	config
3,3M	container
368K	container_hash
2,1M	context
7,7M	contract
72K	conversion
1,5M	convert
1,1M	core
1,1M	coroutine
732K	coroutine2
192K	crc
2,0M	date_time
320K	detail
48K	disjoint_sets
484K	dll
244K	dynamic_bitset
632K	endian
1,3M	exception
6,3M	fiber
2,0M	filesystem
764K	flyweight
156K	foreach
240K	format
312K	function
484K	functional
544K	function_types
6,0M	fusion
22M	geometry
19M	gil
12M	graph
2,1M	graph_parallel
19M	hana
288K	heap
3,0M	hof
11M	icl
4,0K	index.html
376K	integer
2,9M	interprocess
3,3M	intrusive
96K	io
2,4M	iostreams
3,9M	iterator
4,0K	Jamfile.v2
444K	lambda
332K	lexical_cast
76K	libraries.htm
7,0M	locale
1,7M	local_function
200K	lockfree
11M	log
136K	logic
12K	maintainers.txt
78M	math
7,3M	metaparse
664K	move
1,3M	mp11
908K	mpi
6,4M	mpl
5,0M	msm
576K	multi_array
1,9M	multi_index
8,9M	multiprecision
9,4M	numeric
2,6M	optional
556K	parameter
112K	parameter_python
3,2M	phoenix
4,0K	platform_maintainers.txt
1,2M	poly_collection
6,8M	polygon
3,2M	pool
272K	predef
2,8M	preprocessor
632K	process
720K	program_options
224K	property_map
484K	property_tree
1,6M	proto
1,2M	ptr_container
6,3M	python
1,4M	qvm
1,5M	random
3,9M	range
432K	ratio
196K	rational
3,8M	regex
4,6M	safe_numerics
476K	scope_exit
2,3M	serialization
468K	signals2
1,9M	smart_ptr
5,9M	sort
18M	spirit
232K	stacktrace
2,1M	statechart
116K	static_assert
420K	system
9,0M	test
3,7M	thread
132K	throw_exception
196K	timer
156K	tokenizer
1,5M	tti
228K	tuple
752K	type_erasure
260K	type_index
176K	typeof
5,7M	type_traits
1,2M	units
1,2M	unordered
824K	utility
272K	uuid
484K	variant
3,6M	vmd
3,0M	wave
696K	winapi
988K	xpressive
896K	yap
~/boost_1_69_0/libs$ du -sh * |sort -n | head -n 10 # сортируем по размеру и выводим 10 самых тяжелых
1,1M	core
1,1M	coroutine
1,2M	chrono
1,2M	poly_collection
1,2M	ptr_container
1,2M	units
1,2M	unordered
1,3M	exception
1,3M	mp11
1,4M	callable_traits

```
Copyright (c) 2015-2019 The ISC Authors
```
