# CommandArguments::ValidateOptions(utl::span<wchar_t const *,-1>)

- ea: `0x14000ebbc`
- end: `0x14000eeac`
- name: `?ValidateOptions@CommandArguments@@QEBAXV?$span@PEB_W$0?0@utl@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001c6b0`
- `0x14001cfd0`
- `0x140024c5c`
- `0x140025af0`
- `0x1400271f0`
- `0x1400274f0`
- `0x140027e70`

## callees

- `0x14000d868`
- `0x14000ebbc`
- `0x140010450`
- `0x140022cec`
- `0x140028908`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000ec1e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000ec1e`

## pseudocode

```c
void __fastcall CommandArguments::ValidateOptions(__int64 ***a1, __int64 a2)
{
  __int64 *v3; // rbx
  LPCWCH *v4; // rdi
  const wchar_t *Src; // r14
  __int64 v6; // rsi
  const WCHAR *v7; // r8
  __int64 **v8; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  const char *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v15[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v16[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v17[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v18[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v19[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v20[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v21[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v22[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v24[16]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v25[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v26[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v27[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE pExceptionObject[96]; // [rsp+140h] [rbp+40h] BYREF

  v3 = **a1;
  while ( !*((_BYTE *)v3 + 25) )
  {
    v4 = *(LPCWCH **)a2;
    Src = (const wchar_t *)(v3 + 4);
    v6 = *(_QWORD *)a2 + 8LL * *(_QWORD *)(a2 + 8);
    while ( v4 != (LPCWCH *)v6 )
    {
      if ( (unsigned __int64)v3[7] <= 7 )
        v7 = (const WCHAR *)(v3 + 4);
      else
        v7 = *(const WCHAR **)Src;
      if ( CompareStringOrdinal(*v4, -1, v7, -1, 1) == 2 )
        goto LABEL_15;
      ++v4;
    }
    v13[1] = 3;
    v13[0] = L"uni";
    v14[1] = 7;
    v14[0] = L"unicode";
    v12 = *(_OWORD *)std::wstring::operator std::wstring_view(v3 + 4, v23);
    if ( !(unsigned __int8)MatchCommandName(&v12, v14, v13) )
    {
      v15[1] = 1;
      v15[0] = L"r";
      v16[1] = 6;
      v16[0] = L"remote";
      v12 = *(_OWORD *)std::wstring::operator std::wstring_view(v3 + 4, v24);
      if ( !(unsigned __int8)MatchCommandName(&v12, v16, v15) )
      {
        v17[1] = 1;
        v17[0] = L"u";
        v18[1] = 8;
        v18[0] = L"username";
        v12 = *(_OWORD *)std::wstring::operator std::wstring_view(v3 + 4, v25);
        if ( !(unsigned __int8)MatchCommandName(&v12, v18, v17) )
        {
          v19[1] = 1;
          v19[0] = L"p";
          v20[1] = 8;
          v20[0] = L"password";
          v12 = *(_OWORD *)std::wstring::operator std::wstring_view(v3 + 4, v26);
          if ( !(unsigned __int8)MatchCommandName(&v12, v20, v19) )
          {
            v21[1] = 1;
            v21[0] = L"a";
            v22[1] = 14;
            v22[0] = L"Authentication";
            v12 = *(_OWORD *)std::wstring::operator std::wstring_view(v3 + 4, v27);
            if ( !(unsigned __int8)MatchCommandName(&v12, v22, v21) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids, 87);
              }
              if ( (unsigned __int64)v3[7] > 7 )
                Src = *(const wchar_t **)Src;
              EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, bIgnoreCase, 199, 0xCu, Src);
              throw (EvtException *)pExceptionObject;
            }
          }
        }
      }
    }
LABEL_15:
    v8 = (__int64 **)v3[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v3 = i;
      v3 = i;
    }
    else
    {
      v3 = (__int64 *)v3[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
}

```

## disassembly

```asm
0x14000ebbc  push    rbp
0x14000ebbe  push    rbx
0x14000ebbf  push    rsi
0x14000ebc0  push    rdi
0x14000ebc1  push    r13
0x14000ebc3  push    r14
0x14000ebc5  push    r15
0x14000ebc7  lea     rbp, [rsp-70h]
0x14000ebcc  sub     rsp, 170h
0x14000ebd3  mov     rbx, [rcx]
0x14000ebd6  mov     r15, rdx
0x14000ebd9  mov     r13d, 1
0x14000ebdf  mov     rbx, [rbx]
0x14000ebe2  cmp     byte ptr [rbx+19h], 0
0x14000ebe6  jnz     loc_14000EE9A
0x14000ebec  mov     rdi, [r15]
0x14000ebef  lea     r14, [rbx+20h]
0x14000ebf3  mov     rax, [r15+8]
0x14000ebf7  lea     rsi, [rdi+rax*8]
0x14000ebfb  cmp     rdi, rsi
0x14000ebfe  jz      short loc_14000EC33
0x14000ec00  cmp     qword ptr [r14+18h], 7
0x14000ec05  jbe     short loc_14000EC0C
0x14000ec07  mov     r8, [r14]
0x14000ec0a  jmp     short loc_14000EC0F
0x14000ec0c  mov     r8, r14; lpString2
0x14000ec0f  mov     rcx, [rdi]; lpString1
0x14000ec12  or      r9d, 0FFFFFFFFh; cchCount2
0x14000ec16  or      edx, r9d; cchCount1
0x14000ec19  mov     dword ptr [rsp+1A0h+bIgnoreCase], r13d; bIgnoreCase
0x14000ec1e  call    cs:__imp_CompareStringOrdinal
0x14000ec24  cmp     eax, 2
0x14000ec27  jz      loc_14000EDCD
0x14000ec2d  add     rdi, 8
0x14000ec31  jmp     short loc_14000EBFB
0x14000ec33  lea     rax, aUni; "uni"
0x14000ec3a  mov     [rsp+1A0h+var_148], 3
0x14000ec43  mov     [rsp+1A0h+var_150], rax
0x14000ec48  lea     rdx, [rbp+0A0h+var_B0]
0x14000ec4c  lea     rax, aUnicode; "unicode"
0x14000ec53  mov     [rsp+1A0h+var_138], 7
0x14000ec5c  mov     rcx, r14
0x14000ec5f  mov     [rsp+1A0h+var_140], rax
0x14000ec64  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000ec69  lea     r8, [rsp+1A0h+var_150]
0x14000ec6e  lea     rdx, [rsp+1A0h+var_140]
0x14000ec73  lea     rcx, [rsp+1A0h+var_160]
0x14000ec78  movups  xmm0, xmmword ptr [rax]
0x14000ec7b  movdqu  [rsp+1A0h+var_160], xmm0
0x14000ec81  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000ec86  test    al, al
0x14000ec88  jnz     loc_14000EDCD
0x14000ec8e  lea     rax, aR; "r"
0x14000ec95  mov     [rsp+1A0h+var_128], r13
0x14000ec9a  mov     [rsp+1A0h+var_130], rax
0x14000ec9f  lea     rdx, [rbp+0A0h+var_A0]
0x14000eca3  lea     rax, aRemote; "remote"
0x14000ecaa  mov     [rbp+0A0h+var_118], 6
0x14000ecb2  mov     rcx, r14
0x14000ecb5  mov     [rbp+0A0h+var_120], rax
0x14000ecb9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000ecbe  lea     r8, [rsp+1A0h+var_130]
0x14000ecc3  lea     rdx, [rbp+0A0h+var_120]
0x14000ecc7  lea     rcx, [rsp+1A0h+var_160]
0x14000eccc  movups  xmm0, xmmword ptr [rax]
0x14000eccf  movdqu  [rsp+1A0h+var_160], xmm0
0x14000ecd5  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000ecda  test    al, al
0x14000ecdc  jnz     loc_14000EDCD
0x14000ece2  lea     rax, aU; "u"
0x14000ece9  mov     [rbp+0A0h+var_108], r13
0x14000eced  mov     [rbp+0A0h+var_110], rax
0x14000ecf1  lea     rdx, [rbp+0A0h+var_90]
0x14000ecf5  lea     rax, aUsername; "username"
0x14000ecfc  mov     [rbp+0A0h+var_F8], 8
0x14000ed04  mov     rcx, r14
0x14000ed07  mov     [rbp+0A0h+var_100], rax
0x14000ed0b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000ed10  lea     r8, [rbp+0A0h+var_110]
0x14000ed14  lea     rdx, [rbp+0A0h+var_100]
0x14000ed18  lea     rcx, [rsp+1A0h+var_160]
0x14000ed1d  movups  xmm0, xmmword ptr [rax]
0x14000ed20  movdqu  [rsp+1A0h+var_160], xmm0
0x14000ed26  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000ed2b  test    al, al
0x14000ed2d  jnz     loc_14000EDCD
0x14000ed33  lea     rax, aP; "p"
0x14000ed3a  mov     [rbp+0A0h+var_E8], r13
0x14000ed3e  mov     [rbp+0A0h+var_F0], rax
0x14000ed42  lea     rdx, [rbp+0A0h+var_80]
0x14000ed46  lea     rax, aPassword; "password"
0x14000ed4d  mov     [rbp+0A0h+var_D8], 8
0x14000ed55  mov     rcx, r14
0x14000ed58  mov     [rbp+0A0h+var_E0], rax
0x14000ed5c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000ed61  lea     r8, [rbp+0A0h+var_F0]
0x14000ed65  lea     rdx, [rbp+0A0h+var_E0]
0x14000ed69  lea     rcx, [rsp+1A0h+var_160]
0x14000ed6e  movups  xmm0, xmmword ptr [rax]
0x14000ed71  movdqu  [rsp+1A0h+var_160], xmm0
0x14000ed77  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000ed7c  test    al, al
0x14000ed7e  jnz     short loc_14000EDCD
0x14000ed80  lea     rax, aA; "a"
0x14000ed87  mov     [rbp+0A0h+var_C8], r13
0x14000ed8b  mov     [rbp+0A0h+var_D0], rax
0x14000ed8f  lea     rdx, [rbp+0A0h+var_70]
0x14000ed93  lea     rax, aAuthentication; "Authentication"
0x14000ed9a  mov     [rbp+0A0h+var_B8], 0Eh
0x14000eda2  mov     rcx, r14
0x14000eda5  mov     [rbp+0A0h+var_C0], rax
0x14000eda9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000edae  lea     r8, [rbp+0A0h+var_D0]
0x14000edb2  lea     rdx, [rbp+0A0h+var_C0]
0x14000edb6  lea     rcx, [rsp+1A0h+var_160]
0x14000edbb  movups  xmm0, xmmword ptr [rax]
0x14000edbe  movdqu  [rsp+1A0h+var_160], xmm0
0x14000edc4  call    ?MatchCommandName@@YA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@00@Z; MatchCommandName(std::wstring_view,std::wstring_view,std::wstring_view)
0x14000edc9  test    al, al
0x14000edcb  jz      short loc_14000EE1C
0x14000edcd  mov     rcx, [rbx+10h]
0x14000edd1  cmp     byte ptr [rcx+19h], 0
0x14000edd5  jz      short loc_14000EDF8
0x14000edd7  mov     rax, [rbx+8]
0x14000eddb  jmp     short loc_14000EDEA
0x14000eddd  cmp     rbx, [rax+10h]
0x14000ede1  jnz     short loc_14000EDF0
0x14000ede3  mov     rbx, rax
0x14000ede6  mov     rax, [rax+8]
0x14000edea  cmp     byte ptr [rax+19h], 0
0x14000edee  jz      short loc_14000EDDD
0x14000edf0  mov     rbx, rax
0x14000edf3  jmp     loc_14000EBE2
0x14000edf8  mov     rbx, rcx
0x14000edfb  mov     rcx, [rcx]
0x14000edfe  cmp     byte ptr [rcx+19h], 0
0x14000ee02  jnz     loc_14000EBE2
0x14000ee08  mov     rax, [rcx]
0x14000ee0b  mov     rbx, rcx
0x14000ee0e  mov     rcx, rax
0x14000ee11  cmp     byte ptr [rax+19h], 0
0x14000ee15  jz      short loc_14000EE08
0x14000ee17  jmp     loc_14000EBE2
0x14000ee1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee23  lea     rax, WPP_GLOBAL_Control
0x14000ee2a  mov     ebx, 57h ; 'W'
0x14000ee2f  cmp     rcx, rax
0x14000ee32  jz      short loc_14000EE59
0x14000ee34  test    dword ptr [rcx+1Ch], 400000h
0x14000ee3b  jz      short loc_14000EE59
0x14000ee3d  cmp     byte ptr [rcx+19h], 2
0x14000ee41  jb      short loc_14000EE59
0x14000ee43  mov     rcx, [rcx+10h]
0x14000ee47  lea     edx, [rbx-44h]
0x14000ee4a  mov     r9d, ebx
0x14000ee4d  lea     r8, WPP_1febe5f9a22d3f0baf040961cd9dcd00_Traceguids
0x14000ee54  call    WPP_SF_d
0x14000ee59  cmp     qword ptr [r14+18h], 7
0x14000ee5e  jbe     short loc_14000EE63
0x14000ee60  mov     r14, [r14]
0x14000ee63  mov     [rsp+1A0h+Src], r14; Src
0x14000ee68  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x14000ee6c  mov     [rsp+1A0h+var_170], 0Ch; unsigned int
0x14000ee74  xor     r9d, r9d; unsigned int
0x14000ee77  xor     r8d, r8d; unsigned int
0x14000ee7a  mov     [rsp+1A0h+var_178], 0C7h; int
0x14000ee82  mov     edx, ebx; unsigned int
0x14000ee84  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000ee89  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000ee90  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x14000ee94  call    _CxxThrowException_0
0x14000ee9a  add     rsp, 170h
0x14000eea1  pop     r15
0x14000eea3  pop     r14
0x14000eea5  pop     r13
0x14000eea7  pop     rdi
0x14000eea8  pop     rsi
0x14000eea9  pop     rbx
0x14000eeaa  pop     rbp
0x14000eeab  retn
```
