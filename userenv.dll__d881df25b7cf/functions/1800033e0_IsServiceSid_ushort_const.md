# IsServiceSid(ushort const *)

- ea: `0x1800033e0`
- end: `0x18000347a`
- name: `?IsServiceSid@@YAHPEBG@Z`
- size: `154`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002a40`
- `0x180004968`
- `0x180009f74`
- `0x180014c70`
- `0x180014e30`

## callees

- `0x1800033e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003401`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000342d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003459`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003401`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000342d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003459`

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
0x1800033e0  push    rbx
0x1800033e2  sub     rsp, 30h
0x1800033e6  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800033ec  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800033f4  mov     edx, r9d; cchCount1
0x1800033f7  lea     r8, String2; "S-1-5-18"
0x1800033fe  mov     rbx, rcx
0x180003401  call    cs:__imp_CompareStringOrdinal
0x180003408  nop     dword ptr [rax+rax+00h]
0x18000340d  cmp     eax, 2
0x180003410  jz      short loc_180003473
0x180003412  mov     r9d, 0FFFFFFFFh; cchCount2
0x180003418  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180003420  mov     edx, r9d; cchCount1
0x180003423  lea     r8, aS1519; "S-1-5-19"
0x18000342a  mov     rcx, rbx; lpString1
0x18000342d  call    cs:__imp_CompareStringOrdinal
0x180003434  nop     dword ptr [rax+rax+00h]
0x180003439  cmp     eax, 2
0x18000343c  jz      short loc_180003473
0x18000343e  mov     r9d, 0FFFFFFFFh; cchCount2
0x180003444  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000344c  mov     edx, r9d; cchCount1
0x18000344f  lea     r8, aS1520; "S-1-5-20"
0x180003456  mov     rcx, rbx; lpString1
0x180003459  call    cs:__imp_CompareStringOrdinal
0x180003460  nop     dword ptr [rax+rax+00h]
0x180003465  cmp     eax, 2
0x180003468  jz      short loc_180003473
0x18000346a  xor     eax, eax
0x18000346c  add     rsp, 30h
0x180003470  pop     rbx
0x180003471  retn
0x180003473  mov     eax, 1
0x180003478  jmp     short loc_18000346C
```
