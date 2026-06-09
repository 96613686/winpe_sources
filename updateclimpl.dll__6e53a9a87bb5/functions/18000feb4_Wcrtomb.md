# _Wcrtomb

- ea: `0x18000feb4`
- end: `0x18000ff54`
- name: `_Wcrtomb`
- size: `160`
- prototype: `int __cdecl(char *, wchar_t, mbstate_t *, const _Cvtvec *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a760`
- `0x18000a7f0`
- `0x18000de30`
- `0x18000df80`

## callees

- `0x18000feb4`
- `0x18001018c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ff2d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ff2d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
int __cdecl Wcrtomb(char *lpMultiByteStr, wchar_t a2, mbstate_t *a3, const _Cvtvec *a4)
{
  bool v4; // zf
  int result; // eax
  WCHAR WideCharStr; // [rsp+40h] [rbp-48h] BYREF
  BOOL UsedDefaultChar; // [rsp+48h] [rbp-40h] BYREF
  __int128 v8; // [rsp+50h] [rbp-38h]
  __int128 v9; // [rsp+60h] [rbp-28h]
  __int64 v10; // [rsp+70h] [rbp-18h]
  int v11; // [rsp+78h] [rbp-10h]

  v4 = a4->_Isclocale == 0;
  WideCharStr = a2;
  if ( !v4 )
  {
    if ( a2 <= 0xFFu )
    {
      *lpMultiByteStr = a2;
      return 1;
    }
    goto LABEL_6;
  }
  UsedDefaultChar = 0;
  v10 = 0;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  result = WideCharToMultiByte(a4->_Page, 0, &WideCharStr, 1, lpMultiByteStr, a4->_Mbcurmax, 0, &UsedDefaultChar);
  if ( !result || UsedDefaultChar )
  {
LABEL_6:
    *(_DWORD *)o__errno_0((__int64)lpMultiByteStr, a2, (__int64)a3, (__int64)a4) = 42;
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x18000feb4  sub     rsp, 88h
0x18000febb  cmp     dword ptr [r9+8], 0
0x18000fec0  mov     r10, r9
0x18000fec3  mov     [rsp+88h+WideCharStr], dx
0x18000fec8  jz      short loc_18000FEDD
0x18000feca  mov     eax, 0FFh
0x18000fecf  cmp     dx, ax
0x18000fed2  ja      short loc_18000FF3E
0x18000fed4  mov     [rcx], dl
0x18000fed6  mov     eax, 1
0x18000fedb  jmp     short loc_18000FF4C
0x18000fedd  xor     eax, eax
0x18000fedf  mov     [rsp+88h+UsedDefaultChar], 0
0x18000fee7  mov     [rsp+88h+var_18], rax
0x18000feec  lea     r8, [rsp+88h+WideCharStr]; lpWideCharStr
0x18000fef1  mov     [rsp+88h+var_10], eax
0x18000fef5  xorps   xmm0, xmm0
0x18000fef8  lea     rax, [rsp+88h+UsedDefaultChar]
0x18000fefd  xor     edx, edx; dwFlags
0x18000feff  mov     [rsp+88h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18000ff04  movups  [rsp+88h+var_38], xmm0
0x18000ff09  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x18000ff12  movups  [rsp+88h+var_28], xmm0
0x18000ff17  mov     eax, [r9+4]
0x18000ff1b  mov     r9d, 1; cchWideChar
0x18000ff21  mov     [rsp+88h+cbMultiByte], eax; cbMultiByte
0x18000ff25  mov     [rsp+88h+lpMultiByteStr], rcx; lpMultiByteStr
0x18000ff2a  mov     ecx, [r10]; CodePage
0x18000ff2d  call    cs:__imp_WideCharToMultiByte
0x18000ff33  test    eax, eax
0x18000ff35  jz      short loc_18000FF3E
0x18000ff37  cmp     [rsp+88h+UsedDefaultChar], 0
0x18000ff3c  jz      short loc_18000FF4C
0x18000ff3e  call    _o__errno_0
0x18000ff43  mov     dword ptr [rax], 2Ah ; '*'
0x18000ff49  or      eax, 0FFFFFFFFh
0x18000ff4c  add     rsp, 88h
0x18000ff53  retn
```
