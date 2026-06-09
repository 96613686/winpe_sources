# CBsString::FormatErrorCode(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *)

- ea: `0x18001f928`
- end: `0x18001f9e5`
- name: `?FormatErrorCode@CBsString@@QEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(CBsString *this, __int64, unsigned int, const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *, unsigned int, const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017330`

## callees

- `0x18001f8ec`
- `0x18001f928`
- `0x180020184`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9cd`

## pseudocode

```c
__int64 __fastcall CBsString::FormatErrorCode(
        CBsString *this,
        __int64 a2,
        unsigned int a3,
        const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *a4,
        unsigned int a5,
        const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *a6)
{
  int v6; // esi
  int ErrorText; // edi
  int v9; // eax
  unsigned int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+20h] [rbp-38h]
  const struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+28h] [rbp-30h]
  int v15; // [rsp+70h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  a6 = 0;
  v6 = a2;
  hMem = 0;
  v15 = 0;
  ErrorText = CBsString::_GetErrorText(
                this,
                a2,
                a3,
                a4,
                v11,
                v13,
                &v15,
                (unsigned __int16 **)&hMem,
                (unsigned __int16 **)&a6);
  if ( ErrorText >= 0 )
  {
    if ( v15 )
    {
      LODWORD(v14) = v15;
      LODWORD(v12) = v6;
      v9 = CBsString::Format(this, (wchar_t *)L"%s%s(0x%08X[0x%08X])", hMem, a6, v12, v14);
    }
    else
    {
      LODWORD(v12) = v6;
      v9 = CBsString::Format(this, (wchar_t *)L"%s%s(0x%08X)", hMem, a6, v12);
    }
    ErrorText = v9;
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)ErrorText;
}

```

## disassembly

```asm
0x18001f928  mov     r11, rsp
0x18001f92b  mov     [r11+8], rbp
0x18001f92f  mov     [r11+10h], rsi
0x18001f933  mov     [r11+20h], r9
0x18001f937  mov     [r11+18h], r8d
0x18001f93b  push    rdi
0x18001f93c  sub     rsp, 50h
0x18001f940  lea     rax, [r11+30h]
0x18001f944  mov     qword ptr [r11+30h], 0
0x18001f94c  mov     [r11-18h], rax
0x18001f950  mov     esi, edx
0x18001f952  lea     rax, [r11+20h]
0x18001f956  mov     qword ptr [r11+20h], 0
0x18001f95e  mov     [r11-20h], rax
0x18001f962  mov     rbp, rcx
0x18001f965  lea     rax, [r11+18h]
0x18001f969  mov     [rsp+58h+arg_10], 0
0x18001f971  mov     [r11-28h], rax
0x18001f975  call    ?_GetErrorText@CBsString@@AEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@PEAJPEAPEAG3@Z; CBsString::_GetErrorText(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *,long *,ushort * *,ushort * *)
0x18001f97a  mov     edi, eax
0x18001f97c  test    eax, eax
0x18001f97e  js      short loc_18001F9C0
0x18001f980  mov     eax, [rsp+58h+arg_10]
0x18001f984  mov     rcx, rbp; this
0x18001f987  mov     r9, [rsp+58h+arg_28]
0x18001f98f  mov     r8, [rsp+58h+hMem]
0x18001f994  test    eax, eax
0x18001f996  jnz     short loc_18001F9AA
0x18001f998  lea     rdx, aSS0x08x; "%s%s(0x%08X)"
0x18001f99f  mov     dword ptr [rsp+58h+var_38], esi
0x18001f9a3  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18001f9a8  jmp     short loc_18001F9BE
0x18001f9aa  mov     [rsp+58h+var_30], eax
0x18001f9ae  lea     rdx, aSS0x08x0x08x; "%s%s(0x%08X[0x%08X])"
0x18001f9b5  mov     dword ptr [rsp+58h+var_38], esi
0x18001f9b9  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18001f9be  mov     edi, eax
0x18001f9c0  cmp     [rsp+58h+hMem], 0
0x18001f9c6  jz      short loc_18001F9D3
0x18001f9c8  mov     rcx, [rsp+58h+hMem]; hMem
0x18001f9cd  call    cs:__imp_LocalFree
0x18001f9d3  mov     rbp, [rsp+58h+arg_0]
0x18001f9d8  mov     eax, edi
0x18001f9da  mov     rsi, [rsp+58h+arg_8]
0x18001f9df  add     rsp, 50h
0x18001f9e3  pop     rdi
0x18001f9e4  retn
```
