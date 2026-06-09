# CNTFSSecurity::MapGeneric(_GUID const *,uchar *,ulong *)

- ea: `0x180007630`
- end: `0x180007661`
- name: `?MapGeneric@CNTFSSecurity@@UEAAJPEBU_GUID@@PEAEPEAK@Z`
- size: `49`
- prototype: `__int64 __fastcall(CNTFSSecurity *this, const struct _GUID *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007630`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000764f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000764f`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::MapGeneric(
        CNTFSSecurity *this,
        const struct _GUID *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  if ( !a4 )
    return 2147500035LL;
  MapGenericMask(a4, &NTFSMap);
  *a4 &= ~0x100000u;
  return 0;
}

```

## disassembly

```asm
0x180007630  push    rbx
0x180007632  sub     rsp, 20h
0x180007636  mov     rbx, r9
0x180007639  test    r9, r9
0x18000763c  jnz     short loc_180007645
0x18000763e  mov     eax, 80004003h
0x180007643  jmp     short loc_18000765B
0x180007645  lea     rdx, ?NTFSMap@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000764c  mov     rcx, rbx; AccessMask
0x18000764f  call    cs:__imp_MapGenericMask
0x180007655  btr     dword ptr [rbx], 14h
0x180007659  xor     eax, eax
0x18000765b  add     rsp, 20h
0x18000765f  pop     rbx
0x180007660  retn
```
