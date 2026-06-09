# IsServiceSid(ushort const *)

- ea: `0x180003380`
- end: `0x180003407`
- name: `?IsServiceSid@@YAHPEBG@Z`
- size: `135`
- prototype: `_BOOL8 __fastcall(LPCWCH lpString1)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000246c`
- `0x180002ad0`
- `0x18000965c`
- `0x180013bc0`
- `0x180013d50`

## callees

- `0x180003380`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800033ed`

## pseudocode

```c
_BOOL8 __fastcall IsServiceSid(LPCWCH lpString1)
{
  return CompareStringOrdinal(lpString1, -1, L"S-1-5-18", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"S-1-5-19", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"S-1-5-20", -1, 1) == 2;
}

```

## disassembly

```asm
0x180003380  push    rbx
0x180003382  sub     rsp, 30h
0x180003386  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000338c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180003394  mov     edx, r9d; cchCount1
0x180003397  lea     r8, String2; "S-1-5-18"
0x18000339e  mov     rbx, rcx
0x1800033a1  call    cs:__imp_CompareStringOrdinal
0x1800033a7  cmp     eax, 2
0x1800033aa  jz      short loc_180003400
0x1800033ac  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800033b2  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800033ba  mov     edx, r9d; cchCount1
0x1800033bd  lea     r8, aS1519; "S-1-5-19"
0x1800033c4  mov     rcx, rbx; lpString1
0x1800033c7  call    cs:__imp_CompareStringOrdinal
0x1800033cd  cmp     eax, 2
0x1800033d0  jz      short loc_180003400
0x1800033d2  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800033d8  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800033e0  mov     edx, r9d; cchCount1
0x1800033e3  lea     r8, aS1520; "S-1-5-20"
0x1800033ea  mov     rcx, rbx; lpString1
0x1800033ed  call    cs:__imp_CompareStringOrdinal
0x1800033f3  cmp     eax, 2
0x1800033f6  jz      short loc_180003400
0x1800033f8  xor     eax, eax
0x1800033fa  add     rsp, 30h
0x1800033fe  pop     rbx
0x1800033ff  retn
0x180003400  mov     eax, 1
0x180003405  jmp     short loc_1800033FA
```
