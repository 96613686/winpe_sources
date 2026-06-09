# CompatCacheDeleteFusionState

- ea: `0x180006a2c`
- end: `0x180006ab1`
- name: `CompatCacheDeleteFusionState`
- size: `133`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x180006a2c`
- `0x180006c13`
- `0x180007010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180006a5c`
- `ntdll!RtlInitUnicodeStringEx` at `0x180006a5c`

## pseudocode

```c
NTSTATUS __fastcall CompatCacheDeleteFusionState(PCWSTR SourceString, __int64 a2)
{
  NTSTATUS result; // eax
  _BYTE v5[272]; // [rsp+20h] [rbp-198h] BYREF
  int v6; // [rsp+130h] [rbp-88h]
  __int64 v7; // [rsp+148h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+150h] [rbp-68h] BYREF

  memset_0(v5, 0, 0x188u);
  result = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( result >= 0 )
  {
    v6 = 32;
    if ( a2 == -1 )
      a2 = 0;
    v7 = a2;
    return ((__int64 (__fastcall *)(__int64, _BYTE *))g_CompatCacheServiceApi)(1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180006a2c  mov     [rsp+arg_0], rbx
0x180006a31  push    rdi
0x180006a32  sub     rsp, 1B0h
0x180006a39  mov     rdi, rdx
0x180006a3c  mov     rbx, rcx
0x180006a3f  xor     edx, edx; Val
0x180006a41  lea     rcx, [rsp+1B8h+var_198]; void *
0x180006a46  mov     r8d, 188h; Size
0x180006a4c  call    memset_0
0x180006a51  mov     rdx, rbx; SourceString
0x180006a54  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x180006a5c  call    cs:__imp_RtlInitUnicodeStringEx
0x180006a63  nop     dword ptr [rax+rax+00h]
0x180006a68  xor     ecx, ecx
0x180006a6a  test    eax, eax
0x180006a6c  js      short loc_180006A9F
0x180006a6e  mov     rax, cs:g_CompatCacheServiceApi
0x180006a75  lea     rdx, [rsp+1B8h+var_198]
0x180006a7a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180006a7e  mov     [rsp+1B8h+var_88], 20h ; ' '
0x180006a89  cmovz   rdi, rcx
0x180006a8d  mov     ecx, 1
0x180006a92  mov     [rsp+1B8h+var_70], rdi
0x180006a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9f  mov     rbx, [rsp+1B8h+arg_0]
0x180006aa7  add     rsp, 1B0h
0x180006aae  pop     rdi
0x180006aaf  retn
```
