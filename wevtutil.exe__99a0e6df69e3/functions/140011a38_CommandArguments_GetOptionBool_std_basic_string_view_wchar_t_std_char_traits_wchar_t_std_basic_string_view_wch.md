# CommandArguments::GetOptionBool(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,bool &)

- ea: `0x140011a38`
- end: `0x140011bb6`
- name: `?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z`
- size: `382`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011f60`
- `0x14001b75c`
- `0x14001c6b0`
- `0x14001cfd0`
- `0x140026a90`
- `0x1400271f0`
- `0x1400274f0`

## callees

- `0x140010450`
- `0x140011904`
- `0x140011a38`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140011ac9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140011afd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140011ac9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140011afd`

## pseudocode

```c
char __fastcall CommandArguments::GetOptionBool(_QWORD *a1, __int128 *a2, __int128 *a3, __int64 a4, _BYTE *a5)
{
  __int128 v5; // xmm1
  __int64 v7; // rbx
  char result; // al
  char v9; // di
  const WCHAR *v10; // rsi
  const WCHAR *v11; // rcx
  const wchar_t *Src; // rbx
  const char *bIgnoreCase; // [rsp+20h] [rbp-78h]
  __int128 v14; // [rsp+40h] [rbp-58h] BYREF
  __int128 v15; // [rsp+50h] [rbp-48h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+8h] BYREF

  v5 = *a2;
  v14 = *a3;
  v15 = v5;
  CommandArguments::GetOption(a1, &v17, &v15, &v14);
  v7 = v17;
  if ( v17 == *a1 )
  {
    *a5 = 0;
    return 0;
  }
  else
  {
    v9 = 0;
    if ( !*(_BYTE *)(v17 + 64)
      || ((v10 = (const WCHAR *)(v17 + 72), *(_QWORD *)(v17 + 96) <= 7u)
        ? (v11 = (const WCHAR *)(v17 + 72))
        : (v11 = *(const WCHAR **)v10),
          CompareStringOrdinal(v11, *(_DWORD *)(v17 + 88), L"true", 4, 1) == 2) )
    {
      v9 = 1;
    }
    else
    {
      if ( *(_QWORD *)(v7 + 96) > 7u )
        v10 = *(const WCHAR **)v10;
      if ( CompareStringOrdinal(v10, *(_DWORD *)(v7 + 88), L"false", 5, 1) != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
        }
        Src = (const wchar_t *)(v7 + 32);
        if ( *((_QWORD *)Src + 3) > 7u )
          Src = *(const wchar_t **)Src;
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, bIgnoreCase, 157, 0xBu, Src);
        throw (EvtException *)pExceptionObject;
      }
    }
    result = v9;
    *a5 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140011a38  mov     rax, rsp
0x140011a3b  mov     [rax+10h], rbx
0x140011a3f  mov     [rax+18h], rsi
0x140011a43  push    rdi
0x140011a44  sub     rsp, 90h
0x140011a4b  movaps  xmm0, xmmword ptr [r8]
0x140011a4f  lea     r9, [rax-58h]
0x140011a53  movaps  xmm1, xmmword ptr [rdx]
0x140011a56  lea     r8, [rax-48h]
0x140011a5a  lea     rdx, [rax+8]
0x140011a5e  movdqa  xmmword ptr [rax-58h], xmm0
0x140011a63  movdqa  xmmword ptr [rax-48h], xmm1
0x140011a68  mov     rdi, rcx
0x140011a6b  call    ?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::GetOption(std::wstring_view,std::wstring_view)
0x140011a70  mov     rbx, [rsp+98h+arg_0]
0x140011a78  cmp     rbx, [rdi]
0x140011a7b  jnz     short loc_140011A91
0x140011a7d  mov     rax, [rsp+98h+arg_20]
0x140011a85  xor     edi, edi
0x140011a87  mov     [rax], dil
0x140011a8a  xor     al, al
0x140011a8c  jmp     loc_140011BA1
0x140011a91  xor     dil, dil
0x140011a94  cmp     [rbx+40h], dil
0x140011a98  jz      loc_140011B90
0x140011a9e  lea     rsi, [rbx+48h]
0x140011aa2  cmp     qword ptr [rsi+18h], 7
0x140011aa7  jbe     short loc_140011AAE
0x140011aa9  mov     rcx, [rsi]
0x140011aac  jmp     short loc_140011AB1
0x140011aae  mov     rcx, rsi; lpString1
0x140011ab1  mov     edx, [rbx+58h]; cchCount1
0x140011ab4  lea     r8, aTrue; "true"
0x140011abb  mov     r9d, 4; cchCount2
0x140011ac1  mov     dword ptr [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x140011ac9  call    cs:__imp_CompareStringOrdinal
0x140011acf  cmp     eax, 2
0x140011ad2  jz      loc_140011B90
0x140011ad8  cmp     qword ptr [rsi+18h], 7
0x140011add  jbe     short loc_140011AE2
0x140011adf  mov     rsi, [rsi]
0x140011ae2  mov     edx, [rbx+58h]; cchCount1
0x140011ae5  lea     r8, aFalse; "false"
0x140011aec  mov     r9d, 5; cchCount2
0x140011af2  mov     dword ptr [rsp+98h+bIgnoreCase], 1; char *
0x140011afa  mov     rcx, rsi; lpString1
0x140011afd  call    cs:__imp_CompareStringOrdinal
0x140011b03  cmp     eax, 2
0x140011b06  jz      loc_140011B93
0x140011b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b13  lea     rax, WPP_GLOBAL_Control
0x140011b1a  mov     edi, 57h ; 'W'
0x140011b1f  cmp     rcx, rax
0x140011b22  jz      short loc_140011B49
0x140011b24  test    dword ptr [rcx+1Ch], 400000h
0x140011b2b  jz      short loc_140011B49
0x140011b2d  cmp     byte ptr [rcx+19h], 2
0x140011b31  jb      short loc_140011B49
0x140011b33  mov     rcx, [rcx+10h]
0x140011b37  lea     edx, [rdi-46h]
0x140011b3a  mov     r9d, edi
0x140011b3d  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x140011b44  call    WPP_SF_d
0x140011b49  add     rbx, 20h ; ' '
0x140011b4d  cmp     qword ptr [rbx+18h], 7
0x140011b52  jbe     short loc_140011B57
0x140011b54  mov     rbx, [rbx]
0x140011b57  mov     [rsp+98h+Src], rbx; Src
0x140011b5c  lea     rcx, [rsp+98h+pExceptionObject]; this
0x140011b61  mov     [rsp+98h+var_68], 0Bh; unsigned int
0x140011b69  xor     r9d, r9d; unsigned int
0x140011b6c  xor     r8d, r8d; unsigned int
0x140011b6f  mov     [rsp+98h+var_70], 9Dh; int
0x140011b77  mov     edx, edi; unsigned int
0x140011b79  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140011b7e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140011b85  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x140011b8a  call    _CxxThrowException_0
0x140011b90  mov     dil, 1
0x140011b93  mov     rcx, [rsp+98h+arg_20]
0x140011b9b  mov     al, dil
0x140011b9e  mov     byte ptr [rcx], 1
0x140011ba1  lea     r11, [rsp+98h+var_8]
0x140011ba9  mov     rbx, [r11+18h]
0x140011bad  mov     rsi, [r11+20h]
0x140011bb1  mov     rsp, r11
0x140011bb4  pop     rdi
0x140011bb5  retn
```
