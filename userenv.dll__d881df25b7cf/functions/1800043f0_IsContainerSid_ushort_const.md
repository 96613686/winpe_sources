# IsContainerSid(ushort const *)

- ea: `0x1800043f0`
- end: `0x18000445b`
- name: `?IsContainerSid@@YAHPEBG@Z`
- size: `107`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a40`

## callees

- `0x1800043f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004414`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000443a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180004414`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000443a`

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
0x1800043f0  mov     [rsp+arg_0], rbx
0x1800043f5  push    rdi
0x1800043f6  sub     rsp, 30h
0x1800043fa  or      r9d, 0FFFFFFFFh; cchCount2
0x1800043fe  lea     r8, aS159321; "S-1-5-93-2-1"
0x180004405  mov     ebx, 1
0x18000440a  or      edx, r9d; cchCount1
0x18000440d  mov     rdi, rcx
0x180004410  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x180004414  call    cs:__imp_CompareStringOrdinal
0x18000441b  nop     dword ptr [rax+rax+00h]
0x180004420  cmp     eax, 2
0x180004423  jz      short loc_18000444D
0x180004425  or      r9d, 0FFFFFFFFh; cchCount2
0x180004429  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18000442d  or      edx, r9d; cchCount1
0x180004430  lea     r8, aS159322; "S-1-5-93-2-2"
0x180004437  mov     rcx, rdi; lpString1
0x18000443a  call    cs:__imp_CompareStringOrdinal
0x180004441  nop     dword ptr [rax+rax+00h]
0x180004446  cmp     eax, 2
0x180004449  jz      short loc_18000444D
0x18000444b  xor     ebx, ebx
0x18000444d  mov     eax, ebx
0x18000444f  mov     rbx, [rsp+38h+arg_0]
0x180004454  add     rsp, 30h
0x180004458  pop     rdi
0x180004459  retn
```
