# WUStringContainsI(wchar_t const *,wchar_t const *)

- ea: `0x18000ad4c`
- end: `0x18000adff`
- name: `?WUStringContainsI@@YAHPEB_W0@Z`
- size: `179`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d9e8`

## callees

- `0x18000aa74`
- `0x18000ad4c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000adce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000adce`

## pseudocode

```c
__int64 __fastcall WUStringContainsI(PCNZWCH lpString1, const wchar_t *a2)
{
  unsigned __int64 v2; // rbx
  const WCHAR *v4; // rdi
  int cchCount2; // esi
  unsigned __int64 v6; // rbp
  unsigned __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 cchCount1; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v4 = lpString1;
  if ( !lpString1 )
    return 0xFFFFFFFFLL;
  if ( !a2 )
    return 0xFFFFFFFFLL;
  v8 = 0;
  cchCount1 = 0;
  if ( SusStrCchLen(lpString1, 0x7FFFFFFFu, &v8) < 0 )
    return 0xFFFFFFFFLL;
  if ( SusStrCchLen(a2, 0x7FFFFFFFu, &cchCount1) < 0 )
    return 0xFFFFFFFFLL;
  cchCount2 = cchCount1;
  if ( v8 < cchCount1 || !cchCount1 )
    return 0xFFFFFFFFLL;
  v6 = v8 - cchCount1;
  while ( CompareStringW(0x7Fu, 1u, v4, cchCount2, a2, cchCount2) != 2 )
  {
    ++v2;
    ++v4;
    if ( v2 > v6 )
      return 0xFFFFFFFFLL;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ad4c  mov     rax, rsp
0x18000ad4f  mov     [rax+10h], rbx
0x18000ad53  mov     [rax+20h], rbp
0x18000ad57  push    rsi
0x18000ad58  push    rdi
0x18000ad59  push    r14
0x18000ad5b  sub     rsp, 30h
0x18000ad5f  xor     ebx, ebx
0x18000ad61  mov     r14, rdx
0x18000ad64  mov     rdi, rcx
0x18000ad67  test    rcx, rcx
0x18000ad6a  jz      short loc_18000ADE5
0x18000ad6c  test    rdx, rdx
0x18000ad6f  jz      short loc_18000ADE5
0x18000ad71  mov     esi, 7FFFFFFFh
0x18000ad76  mov     [rax+8], rbx
0x18000ad7a  mov     edx, esi; unsigned __int64
0x18000ad7c  mov     [rax+18h], rbx
0x18000ad80  lea     r8, [rax+8]; unsigned __int64 *
0x18000ad84  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000ad89  test    eax, eax
0x18000ad8b  js      short loc_18000ADE5
0x18000ad8d  lea     r8, [rsp+48h+cchCount1]; unsigned __int64 *
0x18000ad92  mov     edx, esi; unsigned __int64
0x18000ad94  mov     rcx, r14; wchar_t *
0x18000ad97  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000ad9c  test    eax, eax
0x18000ad9e  js      short loc_18000ADE5
0x18000ada0  mov     rbp, [rsp+48h+arg_0]
0x18000ada5  mov     rsi, [rsp+48h+cchCount1]
0x18000adaa  cmp     rbp, rsi
0x18000adad  jb      short loc_18000ADE5
0x18000adaf  test    rsi, rsi
0x18000adb2  jz      short loc_18000ADE5
0x18000adb4  sub     rbp, rsi
0x18000adb7  mov     edx, 1; dwCmpFlags
0x18000adbc  mov     [rsp+48h+cchCount2], esi; cchCount2
0x18000adc0  mov     r9d, esi; cchCount1
0x18000adc3  mov     [rsp+48h+lpString2], r14; lpString2
0x18000adc8  mov     r8, rdi; lpString1
0x18000adcb  lea     ecx, [rdx+7Eh]; Locale
0x18000adce  call    cs:__imp_CompareStringW
0x18000add4  cmp     eax, 2
0x18000add7  jz      short loc_18000ADFB
0x18000add9  inc     rbx
0x18000addc  add     rdi, 2
0x18000ade0  cmp     rbx, rbp
0x18000ade3  jbe     short loc_18000ADB7
0x18000ade5  or      eax, 0FFFFFFFFh
0x18000ade8  mov     rbx, [rsp+48h+arg_8]
0x18000aded  mov     rbp, [rsp+48h+arg_18]
0x18000adf2  add     rsp, 30h
0x18000adf6  pop     r14
0x18000adf8  pop     rdi
0x18000adf9  pop     rsi
0x18000adfa  retn
0x18000adfb  mov     eax, ebx
0x18000adfd  jmp     short loc_18000ADE8
```
