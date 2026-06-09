# HTTP2WinHttpTransportChannel::`vector deleting destructor'(uint)

- ea: `0x180003690`
- end: `0x1800036c5`
- name: `??_EHTTP2WinHttpTransportChannel@@UEAAPEAXI@Z`
- size: `53`
- prototype: `void *__fastcall(HTTP2WinHttpTransportChannel *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003690`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800036a3`
- `ntdll!RtlDeleteCriticalSection` at `0x1800036a3`
- `RPCRT4!I_RpcFree` at `0x1800036b1`
- `RPCRT4!I_RpcFree` at `0x1800036b1`

## pseudocode

```c
HTTP2WinHttpTransportChannel *__fastcall HTTP2WinHttpTransportChannel::`vector deleting destructor'(
        HTTP2WinHttpTransportChannel *this,
        char a2)
{
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 104));
  if ( (a2 & 1) != 0 )
    I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x180003690  mov     [rsp+arg_0], rbx
0x180003695  push    rdi
0x180003696  sub     rsp, 20h
0x18000369a  mov     rdi, rcx
0x18000369d  mov     ebx, edx
0x18000369f  add     rcx, 68h ; 'h'; CriticalSection
0x1800036a3  call    cs:__imp_RtlDeleteCriticalSection
0x1800036a9  test    bl, 1
0x1800036ac  jz      short loc_1800036B7
0x1800036ae  mov     rcx, rdi; Object
0x1800036b1  call    cs:__imp_I_RpcFree
0x1800036b7  mov     rbx, [rsp+28h+arg_0]
0x1800036bc  mov     rax, rdi
0x1800036bf  add     rsp, 20h
0x1800036c3  pop     rdi
0x1800036c4  retn
```
