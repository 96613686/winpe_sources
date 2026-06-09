# HTTP_WRAPPER::~HTTP_WRAPPER(void)

- ea: `0x180013084`
- end: `0x1800130b1`
- name: `??1HTTP_WRAPPER@@UEAA@XZ`
- size: `45`
- prototype: `void __fastcall(HTTP_WRAPPER *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012938`
- `0x180014564`
- `0x180015d90`

## callees

- `0x1800130b8`
- `0x180013140`

## pseudocode

```c
void __fastcall HTTP_WRAPPER::~HTTP_WRAPPER(HTTP_WRAPPER *this)
{
  *(_QWORD *)this = &HTTP_WRAPPER::`vftable';
  HTTP_WRAPPER::CloseControlChannel(this);
  HTTP_WRAPPER::Terminate(this);
  *((_DWORD *)this + 2) = 1484222568;
}

```

## disassembly

```asm
0x180013084  push    rbx
0x180013086  sub     rsp, 20h
0x18001308a  lea     rax, ??_7HTTP_WRAPPER@@6B@; const HTTP_WRAPPER::`vftable'
0x180013091  mov     rbx, rcx
0x180013094  mov     [rcx], rax
0x180013097  call    ?CloseControlChannel@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::CloseControlChannel(void)
0x18001309c  mov     rcx, rbx; this
0x18001309f  call    ?Terminate@HTTP_WRAPPER@@QEAAKXZ; HTTP_WRAPPER::Terminate(void)
0x1800130a4  mov     dword ptr [rbx+8], 58777068h
0x1800130ab  add     rsp, 20h
0x1800130af  pop     rbx
0x1800130b0  retn
```
