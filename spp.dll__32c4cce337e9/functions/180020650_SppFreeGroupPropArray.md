# SppFreeGroupPropArray

- ea: `0x180020650`
- end: `0x1800206ab`
- name: `SppFreeGroupPropArray`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800057e0`

## callees

- `0x180020650`
- `0x1800349d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002068e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002068e`

## pseudocode

```c
void __fastcall SppFreeGroupPropArray(unsigned int a1, LPVOID *a2)
{
  __int64 i; // rdi

  if ( a2 && *a2 )
  {
    for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
      Free_SPP_GROUP_PROP((struct _SPP_GROUP_PROP *)((char *)*a2 + 144 * i));
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x180020650  test    rdx, rdx
0x180020653  jz      short locret_1800206AA
0x180020655  mov     [rsp+arg_0], rbx
0x18002065a  mov     [rsp+arg_8], rsi
0x18002065f  push    rdi
0x180020660  sub     rsp, 20h
0x180020664  cmp     qword ptr [rdx], 0
0x180020668  mov     rbx, rdx
0x18002066b  mov     esi, ecx
0x18002066d  jz      short loc_18002069B
0x18002066f  xor     edi, edi
0x180020671  test    ecx, ecx
0x180020673  jz      short loc_18002068B
0x180020675  lea     rcx, [rdi+rdi*8]
0x180020679  shl     rcx, 4
0x18002067d  add     rcx, [rbx]; struct _SPP_GROUP_PROP *
0x180020680  call    ?Free_SPP_GROUP_PROP@@YAXPEAU_SPP_GROUP_PROP@@@Z; Free_SPP_GROUP_PROP(_SPP_GROUP_PROP *)
0x180020685  inc     edi
0x180020687  cmp     edi, esi
0x180020689  jb      short loc_180020675
0x18002068b  mov     rcx, [rbx]; pv
0x18002068e  call    cs:__imp_CoTaskMemFree
0x180020694  mov     qword ptr [rbx], 0
0x18002069b  mov     rbx, [rsp+28h+arg_0]
0x1800206a0  mov     rsi, [rsp+28h+arg_8]
0x1800206a5  add     rsp, 20h
0x1800206a9  pop     rdi
0x1800206aa  retn
```
