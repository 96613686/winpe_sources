# HTTP2ChannelDataOriginator::`scalar deleting destructor'(uint)

- ea: `0x1800032e0`
- end: `0x180003315`
- name: `??_GHTTP2ChannelDataOriginator@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(HTTP2ChannelDataOriginator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800032e0`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800032f3`
- `ntdll!RtlDeleteCriticalSection` at `0x1800032f3`
- `RPCRT4!I_RpcFree` at `0x180003301`
- `RPCRT4!I_RpcFree` at `0x180003301`

## pseudocode

```c
HTTP2ChannelDataOriginator *__fastcall HTTP2ChannelDataOriginator::`scalar deleting destructor'(
        HTTP2ChannelDataOriginator *this,
        char a2)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 64));
  if ( (a2 & 1) != 0 )
    I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x1800032e0  mov     [rsp+arg_0], rbx
0x1800032e5  push    rdi
0x1800032e6  sub     rsp, 20h
0x1800032ea  mov     rdi, rcx
0x1800032ed  mov     ebx, edx
0x1800032ef  add     rcx, 40h ; '@'; CriticalSection
0x1800032f3  call    cs:__imp_RtlDeleteCriticalSection
0x1800032f9  test    bl, 1
0x1800032fc  jz      short loc_180003307
0x1800032fe  mov     rcx, rdi; Object
0x180003301  call    cs:__imp_I_RpcFree
0x180003307  mov     rbx, [rsp+28h+arg_0]
0x18000330c  mov     rax, rdi
0x18000330f  add     rsp, 20h
0x180003313  pop     rdi
0x180003314  retn
```
