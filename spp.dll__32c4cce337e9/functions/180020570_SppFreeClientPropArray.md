# SppFreeClientPropArray

- ea: `0x180020570`
- end: `0x1800205cb`
- name: `SppFreeClientPropArray`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057e0`
- `0x180017dfc`

## callees

- `0x180020570`
- `0x1800346c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205ae`

## pseudocode

```c
void __fastcall SppFreeClientPropArray(unsigned int a1, LPVOID *a2)
{
  __int64 i; // rdi

  if ( a2 && *a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
      Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)((char *)*a2 + 48 * i));
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180020570  test    rdx, rdx
0x180020573  jz      short locret_1800205CA
0x180020575  mov     [rsp+arg_0], rbx
0x18002057a  mov     [rsp+arg_8], rsi
0x18002057f  push    rdi
0x180020580  sub     rsp, 20h
0x180020584  cmp     qword ptr [rdx], 0
0x180020588  mov     rbx, rdx
0x18002058b  mov     esi, ecx
0x18002058d  jz      short loc_1800205BB
0x18002058f  xor     edi, edi
0x180020591  test    ecx, ecx
0x180020593  jz      short loc_1800205AB
0x180020595  lea     rcx, [rdi+rdi*2]
0x180020599  shl     rcx, 4
0x18002059d  add     rcx, [rbx]; struct _SPP_CLIENT_PROP *
0x1800205a0  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x1800205a5  inc     edi
0x1800205a7  cmp     edi, esi
0x1800205a9  jb      short loc_180020595
0x1800205ab  mov     rcx, [rbx]; pv
0x1800205ae  call    cs:__imp_CoTaskMemFree
0x1800205b4  mov     qword ptr [rbx], 0
0x1800205bb  mov     rbx, [rsp+28h+arg_0]
0x1800205c0  mov     rsi, [rsp+28h+arg_8]
0x1800205c5  add     rsp, 20h
0x1800205c9  pop     rdi
0x1800205ca  retn
```
