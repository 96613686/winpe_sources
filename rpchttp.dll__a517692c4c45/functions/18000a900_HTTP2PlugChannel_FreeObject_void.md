# HTTP2PlugChannel::FreeObject(void)

- ea: `0x18000a900`
- end: `0x18000a92e`
- name: `?FreeObject@HTTP2PlugChannel@@UEAAXXZ`
- size: `46`
- prototype: `void __fastcall(HTTP2PlugChannel *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a900`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a927`

## pseudocode

```c
void __fastcall HTTP2PlugChannel::FreeObject(HTTP2PlugChannel *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x18000a900  push    rbx
0x18000a902  sub     rsp, 20h
0x18000a906  mov     rbx, rcx
0x18000a909  mov     rcx, [rcx+8]
0x18000a90d  test    rcx, rcx
0x18000a910  jz      short loc_18000A91E
0x18000a912  mov     rax, [rcx]
0x18000a915  mov     rax, [rax+38h]
0x18000a919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a91e  lea     rcx, [rbx+38h]
0x18000a922  add     rsp, 20h
0x18000a926  pop     rbx
0x18000a927  jmp     cs:__imp_RtlDeleteCriticalSection
```
