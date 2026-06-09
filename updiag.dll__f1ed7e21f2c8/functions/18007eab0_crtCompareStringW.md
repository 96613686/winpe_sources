# __crtCompareStringW

- ea: `0x18007eab0`
- end: `0x18007eb6f`
- name: `__crtCompareStringW`
- size: `191`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180024580`

## callees

- `0x18007eab0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007eb3b`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007eb3b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007ead8`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007eafb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007ead8`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18007eafb`

## pseudocode

```c
int __fastcall _crtCompareStringW(LPCWSTR lpLocaleName, __int64 a2, const wchar_t *a3, int a4, wchar_t *Source, int a6)
{
  int v6; // ebx
  int cchCount2; // eax
  int result; // eax
  int v11; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = wcsnlen(a3, a4);
  cchCount2 = a6;
  if ( a6 > 0 )
    cchCount2 = wcsnlen(Source, a6);
  if ( v6 && cchCount2 )
    return CompareStringEx(lpLocaleName, 0x1000u, a3, v6, Source, cchCount2, 0, 0, 0);
  v11 = v6 - cchCount2;
  result = ((v11 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v11 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x18007eab0  mov     [rsp+arg_0], rbx
0x18007eab5  mov     [rsp+arg_8], rbp
0x18007eaba  mov     [rsp+arg_10], rsi
0x18007eabf  push    rdi
0x18007eac0  sub     rsp, 50h
0x18007eac4  movsxd  rbx, r9d
0x18007eac7  mov     rsi, r8
0x18007eaca  mov     rbp, rcx
0x18007eacd  test    r9d, r9d
0x18007ead0  jle     short loc_18007EAE1
0x18007ead2  mov     rdx, rbx; MaxCount
0x18007ead5  mov     rcx, r8; Source
0x18007ead8  call    cs:__imp_wcsnlen
0x18007eade  mov     rbx, rax
0x18007eae1  movsxd  rax, [rsp+58h+arg_28]
0x18007eae9  mov     rdi, [rsp+58h+Source]
0x18007eaf1  test    eax, eax
0x18007eaf3  jle     short loc_18007EB01
0x18007eaf5  mov     rdx, rax; MaxCount
0x18007eaf8  mov     rcx, rdi; Source
0x18007eafb  call    cs:__imp_wcsnlen
0x18007eb01  test    ebx, ebx
0x18007eb03  jz      short loc_18007EB43
0x18007eb05  test    eax, eax
0x18007eb07  jz      short loc_18007EB43
0x18007eb09  mov     [rsp+58h+lParam], 0; lParam
0x18007eb12  mov     r9d, ebx; cchCount1
0x18007eb15  mov     [rsp+58h+lpReserved], 0; lpReserved
0x18007eb1e  mov     r8, rsi; lpString1
0x18007eb21  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x18007eb2a  mov     edx, 1000h; dwCmpFlags
0x18007eb2f  mov     [rsp+58h+cchCount2], eax; cchCount2
0x18007eb33  mov     rcx, rbp; lpLocaleName
0x18007eb36  mov     [rsp+58h+lpString2], rdi; lpString2
0x18007eb3b  call    cs:__imp_CompareStringEx
0x18007eb41  jmp     short loc_18007EB5A
0x18007eb43  sub     ebx, eax
0x18007eb45  mov     ecx, 2
0x18007eb4a  mov     eax, ebx
0x18007eb4c  sar     eax, 1Fh
0x18007eb4f  and     eax, 0FFFFFFFEh
0x18007eb52  add     eax, 3
0x18007eb55  test    ebx, ebx
0x18007eb57  cmovz   eax, ecx
0x18007eb5a  mov     rbx, [rsp+58h+arg_0]
0x18007eb5f  mov     rbp, [rsp+58h+arg_8]
0x18007eb64  mov     rsi, [rsp+58h+arg_10]
0x18007eb69  add     rsp, 50h
0x18007eb6d  pop     rdi
0x18007eb6e  retn
```
