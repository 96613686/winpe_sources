# HTTP2ProxyServerSideChannel::HTTP2ProxyServerSideChannel(HTTP2VirtualConnection *,BASE_CONNECTION *,int)

- ea: `0x180002a40`
- end: `0x180002a84`
- name: `??0HTTP2ProxyServerSideChannel@@QEAA@PEAVHTTP2VirtualConnection@@PEAVBASE_CONNECTION@@H@Z`
- size: `68`
- prototype: `HTTP2ProxyServerSideChannel *__fastcall(HTTP2ProxyServerSideChannel *__hidden this, struct HTTP2VirtualConnection *, struct BASE_CONNECTION *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180004714`
- `0x180004cf8`

## callees

- `0x180002360`

## pseudocode

```c
HTTP2ProxyServerSideChannel *__fastcall HTTP2ProxyServerSideChannel::HTTP2ProxyServerSideChannel(
        HTTP2ProxyServerSideChannel *this,
        struct HTTP2VirtualConnection *a2,
        struct BASE_CONNECTION *a3)
{
  int v5; // r11d
  HTTP2ProxyServerSideChannel *result; // rax
  __int64 v7; // r10

  HTTP2Channel::HTTP2Channel(this, 1);
  *((_DWORD *)this + 20) = v5;
  *(_QWORD *)this = &HTTP2ProxyServerSideChannel::`vftable';
  result = this;
  *((_QWORD *)this + 6) = v7;
  *((_QWORD *)this + 9) = a3;
  return result;
}

```

## disassembly

```asm
0x180002a40  mov     [rsp+arg_0], rbx
0x180002a45  push    rdi
0x180002a46  sub     rsp, 20h
0x180002a4a  mov     r10, rdx
0x180002a4d  mov     r11d, r9d
0x180002a50  mov     edx, 1; int
0x180002a55  mov     rdi, r8
0x180002a58  mov     rbx, rcx
0x180002a5b  call    ??0HTTP2Channel@@QEAA@H@Z; HTTP2Channel::HTTP2Channel(int)
0x180002a60  lea     rdx, ??_7HTTP2ProxyServerSideChannel@@6B@; const HTTP2ProxyServerSideChannel::`vftable'
0x180002a67  mov     [rbx+50h], r11d
0x180002a6b  mov     [rbx], rdx
0x180002a6e  mov     rax, rbx
0x180002a71  mov     [rbx+30h], r10
0x180002a75  mov     [rbx+48h], rdi
0x180002a79  mov     rbx, [rsp+28h+arg_0]
0x180002a7e  add     rsp, 20h
0x180002a82  pop     rdi
0x180002a83  retn
```
