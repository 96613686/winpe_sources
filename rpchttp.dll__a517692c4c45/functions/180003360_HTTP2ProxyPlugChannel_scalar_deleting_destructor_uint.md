# HTTP2ProxyPlugChannel::`scalar deleting destructor'(uint)

- ea: `0x180003360`
- end: `0x180003395`
- name: `??_GHTTP2ProxyPlugChannel@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(HTTP2ProxyPlugChannel *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003360`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180003373`
- `ntdll!RtlDeleteCriticalSection` at `0x180003373`
- `RPCRT4!I_RpcFree` at `0x180003381`
- `RPCRT4!I_RpcFree` at `0x180003381`

## pseudocode

```c
HTTP2ProxyPlugChannel *__fastcall HTTP2ProxyPlugChannel::`scalar deleting destructor'(
        HTTP2ProxyPlugChannel *this,
        char a2)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 56));
  if ( (a2 & 1) != 0 )
    I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x180003360  mov     [rsp+arg_0], rbx
0x180003365  push    rdi
0x180003366  sub     rsp, 20h
0x18000336a  mov     rdi, rcx
0x18000336d  mov     ebx, edx
0x18000336f  add     rcx, 38h ; '8'; CriticalSection
0x180003373  call    cs:__imp_RtlDeleteCriticalSection
0x180003379  test    bl, 1
0x18000337c  jz      short loc_180003387
0x18000337e  mov     rcx, rdi; Object
0x180003381  call    cs:__imp_I_RpcFree
0x180003387  mov     rbx, [rsp+28h+arg_0]
0x18000338c  mov     rax, rdi
0x18000338f  add     rsp, 20h
0x180003393  pop     rdi
0x180003394  retn
```
