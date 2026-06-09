# HTTP2ChannelDataOriginator::FreeObject(void)

- ea: `0x18000a6e0`
- end: `0x18000a70e`
- name: `?FreeObject@HTTP2ChannelDataOriginator@@UEAAXXZ`
- size: `46`
- prototype: `void __fastcall(HTTP2ChannelDataOriginator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a6e0`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a707`

## pseudocode

```c
void __fastcall HTTP2ChannelDataOriginator::FreeObject(HTTP2ChannelDataOriginator *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 1);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x18000a6e0  push    rbx
0x18000a6e2  sub     rsp, 20h
0x18000a6e6  mov     rbx, rcx
0x18000a6e9  mov     rcx, [rcx+8]
0x18000a6ed  test    rcx, rcx
0x18000a6f0  jz      short loc_18000A6FE
0x18000a6f2  mov     rax, [rcx]
0x18000a6f5  mov     rax, [rax+38h]
0x18000a6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fe  lea     rcx, [rbx+40h]
0x18000a702  add     rsp, 20h
0x18000a706  pop     rbx
0x18000a707  jmp     cs:__imp_RtlDeleteCriticalSection
```
