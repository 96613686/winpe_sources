# CPrintSecurity::MapGeneric(_GUID const *,uchar *,ulong *)

- ea: `0x180008550`
- end: `0x1800085b9`
- name: `?MapGeneric@CPrintSecurity@@UEAAJPEBU_GUID@@PEAEPEAK@Z`
- size: `105`
- prototype: `__int64 __fastcall(CPrintSecurity *this, const struct _GUID *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008550`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008596`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180008596`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::MapGeneric(
        CPrintSecurity *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  struct _GENERIC_MAPPING *v5; // rbx

  if ( !a3 || !a4 )
    return 2147500035LL;
  *a3 &= ~2u;
  if ( (*a3 & 1) != 0 )
  {
    v5 = &JobMap;
    if ( (*a3 & 8) == 0 )
      v5 = &FullPrinterMap;
  }
  else
  {
    v5 = &PrinterMap;
  }
  MapGenericMask(a4, v5);
  *a4 &= v5->GenericAll | 0x1000000;
  return 0;
}

```

## disassembly

```asm
0x180008550  mov     [rsp+arg_0], rbx
0x180008555  push    rdi
0x180008556  sub     rsp, 20h
0x18000855a  mov     rdi, r9
0x18000855d  test    r8, r8
0x180008560  jz      short loc_1800085A9
0x180008562  test    r9, r9
0x180008565  jz      short loc_1800085A9
0x180008567  and     byte ptr [r8], 0FDh
0x18000856b  test    byte ptr [r8], 1
0x18000856f  jz      short loc_180008589
0x180008571  test    byte ptr [r8], 8
0x180008575  lea     rax, ?FullPrinterMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING FullPrinterMap
0x18000857c  lea     rbx, ?JobMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING JobMap
0x180008583  cmovz   rbx, rax
0x180008587  jmp     short loc_180008590
0x180008589  lea     rbx, ?PrinterMap@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING PrinterMap
0x180008590  mov     rdx, rbx; GenericMapping
0x180008593  mov     rcx, rdi; AccessMask
0x180008596  call    cs:__imp_MapGenericMask
0x18000859c  mov     eax, [rbx+0Ch]
0x18000859f  bts     eax, 18h
0x1800085a3  and     [rdi], eax
0x1800085a5  xor     eax, eax
0x1800085a7  jmp     short loc_1800085AE
0x1800085a9  mov     eax, 80004003h
0x1800085ae  mov     rbx, [rsp+28h+arg_0]
0x1800085b3  add     rsp, 20h
0x1800085b7  pop     rdi
0x1800085b8  retn
```
