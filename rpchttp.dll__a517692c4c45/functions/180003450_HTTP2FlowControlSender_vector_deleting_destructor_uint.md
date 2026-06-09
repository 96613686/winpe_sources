# HTTP2FlowControlSender::`vector deleting destructor'(uint)

- ea: `0x180003450`
- end: `0x180003485`
- name: `??_EHTTP2FlowControlSender@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(HTTP2FlowControlSender *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003450`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180003463`
- `ntdll!RtlDeleteCriticalSection` at `0x180003463`
- `RPCRT4!I_RpcFree` at `0x180003471`
- `RPCRT4!I_RpcFree` at `0x180003471`

## pseudocode

```c
HTTP2FlowControlSender *__fastcall HTTP2FlowControlSender::`vector deleting destructor'(
        HTTP2FlowControlSender *this,
        char a2)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 48));
  if ( (a2 & 1) != 0 )
    I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x180003450  mov     [rsp+arg_0], rbx
0x180003455  push    rdi
0x180003456  sub     rsp, 20h
0x18000345a  mov     rdi, rcx
0x18000345d  mov     ebx, edx
0x18000345f  add     rcx, 30h ; '0'; CriticalSection
0x180003463  call    cs:__imp_RtlDeleteCriticalSection
0x180003469  test    bl, 1
0x18000346c  jz      short loc_180003477
0x18000346e  mov     rcx, rdi; Object
0x180003471  call    cs:__imp_I_RpcFree
0x180003477  mov     rbx, [rsp+28h+arg_0]
0x18000347c  mov     rax, rdi
0x18000347f  add     rsp, 20h
0x180003483  pop     rdi
0x180003484  retn
```
