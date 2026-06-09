# CKnownGroups::_IsGroupInGroupList(ushort const *,_LOCALGROUP_USERS_INFO_0 *,ulong)

- ea: `0x1800117ec`
- end: `0x180011838`
- name: `?_IsGroupInGroupList@CKnownGroups@@AEBA_NPEBGPEAU_LOCALGROUP_USERS_INFO_0@@K@Z`
- size: `76`
- prototype: `bool(CKnownGroups *__hidden this, const unsigned __int16 *, struct _LOCALGROUP_USERS_INFO_0 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010b88`

## callees

- `0x1800117ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001181c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001181c`

## pseudocode

```c
char __fastcall CKnownGroups::_IsGroupInGroupList(
        CKnownGroups *this,
        const unsigned __int16 *a2,
        struct _LOCALGROUP_USERS_INFO_0 *a3,
        unsigned int a4)
{
  char result; // al
  __int64 i; // rbx

  result = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringOrdinal(a3[i].lgrui0_name, -1, a2, -1, 1) == 2 )
      return 1;
    result = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800117ec  push    rbx
0x1800117ee  push    rbp
0x1800117ef  push    rsi
0x1800117f0  push    rdi
0x1800117f1  sub     rsp, 38h
0x1800117f5  xor     al, al
0x1800117f7  mov     edi, r9d
0x1800117fa  xor     ebx, ebx
0x1800117fc  mov     rsi, r8
0x1800117ff  mov     rbp, rdx
0x180011802  cmp     ebx, edi
0x180011804  jnb     short loc_18001182F
0x180011806  mov     rcx, [rsi+rbx*8]; lpString1
0x18001180a  or      r9d, 0FFFFFFFFh; cchCount2
0x18001180e  or      edx, r9d; cchCount1
0x180011811  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180011819  mov     r8, rbp; lpString2
0x18001181c  call    cs:__imp_CompareStringOrdinal
0x180011822  cmp     eax, 2
0x180011825  jz      short loc_18001182D
0x180011827  xor     al, al
0x180011829  inc     ebx
0x18001182b  jmp     short loc_180011802
0x18001182d  mov     al, 1
0x18001182f  add     rsp, 38h
0x180011833  pop     rdi
0x180011834  pop     rsi
0x180011835  pop     rbp
0x180011836  pop     rbx
0x180011837  retn
```
