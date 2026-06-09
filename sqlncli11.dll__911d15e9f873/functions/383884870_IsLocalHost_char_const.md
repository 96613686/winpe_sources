# IsLocalHost(char const *)

- ea: `0x383884870`
- end: `0x383884906`
- name: `?IsLocalHost@@YA_NPEBD@Z`
- size: `150`
- prototype: `bool __fastcall(PCNZCH lpString2)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3838804e0`
- `0x38388f8a0`
- `0x383ad93c0`
- `0x383ad9860`

## callees

- `0x383884870`

## import_xrefs

- `MSVCR100!_stricmp_l` at `0x3838848a2`
- `MSVCR100!_stricmp_l` at `0x3838848b9`
- `MSVCR100!_stricmp_l` at `0x3838848a2`
- `MSVCR100!_stricmp_l` at `0x3838848b9`
- `KERNEL32!CompareStringA` at `0x3838848e5`
- `KERNEL32!CompareStringA` at `0x3838848e5`

## pseudocode

```c
bool __fastcall IsLocalHost(PCNZCH lpString2)
{
  return !strcmp(".", lpString2)
      || !_stricmp_l("(local)", lpString2, 0)
      || !_stricmp_l("localhost", lpString2, 0)
      || CompareStringA(0x800u, 0x20001u, gszComputerName, -1, lpString2, -1) == 2;
}

```

## disassembly

```asm
0x383884870  mov     [rsp+arg_0], rbx
0x383884875  mov     [rsp+arg_8], rsi
0x38388487a  push    rdi
0x38388487b  sub     rsp, 30h
0x38388487f  mov     rbx, rcx
0x383884882  mov     rdi, rcx
0x383884885  lea     rsi, asc_38387C770; "."
0x38388488c  mov     ecx, 2
0x383884891  repe cmpsb
0x383884893  jz      short loc_3838848F4
0x383884895  lea     rcx, aLocal; "(local)"
0x38388489c  xor     r8d, r8d; Locale
0x38388489f  mov     rdx, rbx; String2
0x3838848a2  call    cs:__imp__stricmp_l
0x3838848a8  test    eax, eax
0x3838848aa  jz      short loc_3838848F4
0x3838848ac  lea     rcx, aLocalhost; "localhost"
0x3838848b3  xor     r8d, r8d; Locale
0x3838848b6  mov     rdx, rbx; String2
0x3838848b9  call    cs:__imp__stricmp_l
0x3838848bf  test    eax, eax
0x3838848c1  jz      short loc_3838848F4
0x3838848c3  lea     r8, ?gszComputerName@@3PADA; lpString1
0x3838848ca  or      r9d, 0FFFFFFFFh; cchCount1
0x3838848ce  mov     edx, 20001h; dwCmpFlags
0x3838848d3  mov     ecx, 800h; Locale
0x3838848d8  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x3838848e0  mov     [rsp+38h+lpString2], rbx; lpString2
0x3838848e5  call    cs:__imp_CompareStringA
0x3838848eb  cmp     eax, 2
0x3838848ee  jnz     loc_3838F868F
0x3838848f4  mov     rbx, [rsp+38h+arg_0]
0x3838848f9  mov     rsi, [rsp+38h+arg_8]
0x3838848fe  mov     al, 1
0x383884900  add     rsp, 30h
0x383884904  pop     rdi
0x383884905  retn
0x3838f868f  xor     al, al
0x3838f8691  mov     rbx, [rsp+38h+arg_0]
0x3838f8696  mov     rsi, [rsp+38h+arg_8]
0x3838f869b  add     rsp, 30h
0x3838f869f  pop     rdi
0x3838f86a0  retn
```
