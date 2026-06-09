# WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)

- ea: `0x18000ac44`
- end: `0x18000acdb`
- name: `?WUCompareStringCchI@@YAHPEB_W0I@Z`
- size: `151`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ace4`
- `0x18000d9e8`
- `0x18000e530`

## callees

- `0x18000aa74`
- `0x18000ac44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000acc3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000acb6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000acb6`

## pseudocode

```c
int __fastcall WUCompareStringCchI(PCNZWCH lpString1, const wchar_t *a2, unsigned int a3)
{
  unsigned __int64 cchCount2; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 cchCount1; // [rsp+58h] [rbp+20h] BYREF

  if ( lpString1 )
  {
    if ( a2 )
    {
      cchCount1 = 0;
      cchCount2 = 0;
      if ( SusStrCchLen(lpString1, a3, &cchCount1) >= 0 && SusStrCchLen(a2, a3, &cchCount2) >= 0 )
        return CompareStringW(0x7Fu, 1u, lpString1, cchCount1, a2, cchCount2);
    }
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18000ac44  mov     rax, rsp
0x18000ac47  mov     [rax+10h], rbx
0x18000ac4b  mov     [rax+18h], rsi
0x18000ac4f  push    rdi
0x18000ac50  sub     rsp, 30h
0x18000ac54  mov     rbx, rdx
0x18000ac57  mov     rdi, rcx
0x18000ac5a  test    rcx, rcx
0x18000ac5d  jz      short loc_18000ACBE
0x18000ac5f  test    rdx, rdx
0x18000ac62  jz      short loc_18000ACBE
0x18000ac64  mov     esi, r8d
0x18000ac67  lea     r8, [rax+20h]; unsigned __int64 *
0x18000ac6b  mov     edx, esi; unsigned __int64
0x18000ac6d  mov     qword ptr [rax+20h], 0
0x18000ac75  mov     qword ptr [rax+8], 0
0x18000ac7d  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000ac82  test    eax, eax
0x18000ac84  js      short loc_18000ACBE
0x18000ac86  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x18000ac8b  mov     edx, esi; unsigned __int64
0x18000ac8d  mov     rcx, rbx; wchar_t *
0x18000ac90  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000ac95  test    eax, eax
0x18000ac97  js      short loc_18000ACBE
0x18000ac99  mov     eax, dword ptr [rsp+38h+arg_0]
0x18000ac9d  mov     edx, 1; dwCmpFlags
0x18000aca2  mov     r9d, dword ptr [rsp+38h+cchCount1]; cchCount1
0x18000aca7  mov     r8, rdi; lpString1
0x18000acaa  mov     [rsp+38h+cchCount2], eax; cchCount2
0x18000acae  mov     [rsp+38h+lpString2], rbx; lpString2
0x18000acb3  lea     ecx, [rdx+7Eh]; Locale
0x18000acb6  call    cs:__imp_CompareStringW
0x18000acbc  jmp     short loc_18000ACCB
0x18000acbe  mov     ecx, 57h ; 'W'; dwErrCode
0x18000acc3  call    cs:__imp_SetLastError
0x18000acc9  xor     eax, eax
0x18000accb  mov     rbx, [rsp+38h+arg_8]
0x18000acd0  mov     rsi, [rsp+38h+arg_10]
0x18000acd5  add     rsp, 30h
0x18000acd9  pop     rdi
0x18000acda  retn
```
