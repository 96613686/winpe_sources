# CompatCacheDeleteFusionState

- ea: `0x180006b08`
- end: `0x180006b8d`
- name: `CompatCacheDeleteFusionState`
- size: `133`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002d40`

## callees

- `0x180006b08`
- `0x180006ccd`
- `0x180008010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180006b38`
- `ntdll!RtlInitUnicodeStringEx` at `0x180006b38`

## pseudocode

```c
NTSTATUS __fastcall CompatCacheDeleteFusionState(PCWSTR SourceString, __int64 a2)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  _BYTE v6[272]; // [rsp+20h] [rbp-198h] BYREF
  int v7; // [rsp+130h] [rbp-88h]
  __int64 v8; // [rsp+148h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+150h] [rbp-68h] BYREF

  memset_0(v6, 0, 0x188u);
  result = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( result >= 0 )
  {
    v5 = 0;
    v7 = 32;
    if ( a2 != -1 )
      v5 = a2;
    v8 = v5;
    return ((__int64 (__fastcall *)(__int64, _BYTE *))g_CompatCacheServiceApi)(1, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180006b08  mov     [rsp+arg_0], rbx
0x180006b0d  push    rdi
0x180006b0e  sub     rsp, 1B0h
0x180006b15  mov     rdi, rdx
0x180006b18  mov     rbx, rcx
0x180006b1b  xor     edx, edx; Val
0x180006b1d  lea     rcx, [rsp+1B8h+var_198]; void *
0x180006b22  mov     r8d, 188h; Size
0x180006b28  call    memset_0
0x180006b2d  mov     rdx, rbx; SourceString
0x180006b30  lea     rcx, [rsp+1B8h+DestinationString]; DestinationString
0x180006b38  call    cs:__imp_RtlInitUnicodeStringEx
0x180006b3f  nop     dword ptr [rax+rax+00h]
0x180006b44  test    eax, eax
0x180006b46  js      short loc_180006B7B
0x180006b48  xor     eax, eax
0x180006b4a  mov     [rsp+1B8h+var_88], 20h ; ' '
0x180006b55  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180006b59  lea     rdx, [rsp+1B8h+var_198]
0x180006b5e  mov     ecx, 1
0x180006b63  cmovnz  rax, rdi
0x180006b67  mov     [rsp+1B8h+var_70], rax
0x180006b6f  mov     rax, cs:g_CompatCacheServiceApi
0x180006b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7b  mov     rbx, [rsp+1B8h+arg_0]
0x180006b83  add     rsp, 1B0h
0x180006b8a  pop     rdi
0x180006b8b  retn
```
