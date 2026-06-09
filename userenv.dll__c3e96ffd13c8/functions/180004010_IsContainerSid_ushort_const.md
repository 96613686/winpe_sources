# IsContainerSid(ushort const *)

- ea: `0x180004010`
- end: `0x18000406e`
- name: `?IsContainerSid@@YAHPEBG@Z`
- size: `94`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180004010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004034`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004054`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004034`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004054`

## pseudocode

```c
__int64 __fastcall IsContainerSid(LPCWCH lpString1)
{
  unsigned int v1; // ebx

  v1 = 1;
  if ( CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-1", -1, 1) != 2 )
    return CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-2", -1, 1) == 2;
  return v1;
}

```

## disassembly

```asm
0x180004010  mov     [rsp+arg_0], rbx
0x180004015  push    rdi
0x180004016  sub     rsp, 30h
0x18000401a  or      r9d, 0FFFFFFFFh; cchCount2
0x18000401e  lea     r8, aS159321; "S-1-5-93-2-1"
0x180004025  mov     ebx, 1
0x18000402a  or      edx, r9d; cchCount1
0x18000402d  mov     rdi, rcx
0x180004030  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180004034  call    cs:__imp_CompareStringOrdinal
0x18000403a  cmp     eax, 2
0x18000403d  jz      short loc_180004061
0x18000403f  or      r9d, 0FFFFFFFFh; cchCount2
0x180004043  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180004047  or      edx, r9d; cchCount1
0x18000404a  lea     r8, aS159322; "S-1-5-93-2-2"
0x180004051  mov     rcx, rdi; lpString1
0x180004054  call    cs:__imp_CompareStringOrdinal
0x18000405a  cmp     eax, 2
0x18000405d  jz      short loc_180004061
0x18000405f  xor     ebx, ebx
0x180004061  mov     eax, ebx
0x180004063  mov     rbx, [rsp+38h+arg_0]
0x180004068  add     rsp, 30h
0x18000406c  pop     rdi
0x18000406d  retn
```
