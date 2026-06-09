# Windows::Internal::Notifications::AdaptiveNotification::RuntimeClassInitialize(HSTRING__ *,uchar *,uint)

- ea: `0x180023ba4`
- end: `0x180023e0e`
- name: `?RuntimeClassInitialize@AdaptiveNotification@Notifications@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAEI@Z`
- size: `618`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, HSTRING string, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bfa0`

## callees

- `0x1800070e8`
- `0x180018b78`
- `0x18001bce0`
- `0x18001bf44`
- `0x18001cb74`
- `0x18001dccc`
- `0x18001ff00`
- `0x18002030c`
- `0x1800230c8`
- `0x180023260`
- `0x1800235e4`
- `0x180023ba4`
- `0x180023e78`
- `0x1800244d4`

## import_xrefs

- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180023cd0`
- `msvcp_win!??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z` at `0x180023cd0`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180023c7d`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180023c7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180023c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::Notifications::AdaptiveNotification::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING string,
        unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v4; // r15
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 result; // rax
  HSTRING *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int128 *v14; // r8
  __int64 v15; // rax
  unsigned __int16 **v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-108h]
  _QWORD *v21; // [rsp+20h] [rbp-108h]
  int v22; // [rsp+20h] [rbp-108h]
  unsigned int v23; // [rsp+20h] [rbp-108h]
  unsigned __int16 *v24[3]; // [rsp+28h] [rbp-100h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-E8h]
  __int128 v26; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-D0h]
  unsigned __int64 v28; // [rsp+60h] [rbp-C8h]
  _QWORD v29[4]; // [rsp+70h] [rbp-B8h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v31[40]; // [rsp+B0h] [rbp-78h] BYREF
  __int16 v32; // [rsp+D8h] [rbp-50h]
  char v33; // [rsp+DAh] [rbp-4Eh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v4 = a4;
  if ( !string )
  {
    v8 = 19;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)v9,
      v20);
    return v9;
  }
  if ( !a3 )
  {
    v8 = 20;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 21;
    goto LABEL_3;
  }
  v11 = this + 9;
  if ( string != this[9] )
  {
    WindowsDeleteString(*v11);
    *v11 = 0;
    v9 = WindowsDuplicateString(string, v11);
    if ( (v9 & 0x80000000) != 0 )
    {
      v8 = 22;
      goto LABEL_4;
    }
  }
  v26 = 0;
  v27 = 0;
  v28 = 0;
  std::string::_Construct<1,char const *>(&v26, a3, v4);
  v29[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  v29[3] = std::locale::_Init(1);
  std::string::string(v30, v12, v13);
  std::wstring::wstring(v31);
  v32 = 0;
  v33 = 0;
  v21 = operator new(0x40u);
  std::codecvt<unsigned short,char,_Mbstatet>::codecvt<unsigned short,char,_Mbstatet>(v21, 0);
  *v21 = &std::codecvt_utf8_utf16<unsigned short,1114111,0>::`vftable';
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::_Init(
    v29,
    v21);
  v14 = &v26;
  if ( v28 > 0xF )
    v14 = (__int128 *)v26;
  v15 = -1;
  do
    ++v15;
  while ( *((_BYTE *)v14 + v15) );
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v29,
    v24,
    v14,
    (char *)v14 + v15,
    v21);
  v16 = v24;
  if ( v25 > 7 )
    LODWORD(v16) = v24[0];
  v22 = (int)v16;
  v17 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((Microsoft::WRL::Wrappers::HString *)(this + 10));
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v17,
      v22);
    std::wstring::~wstring(v24);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v29);
    std::string::~string(&v26);
    return v9;
  }
  v18 = (const unsigned __int16 *)v24;
  if ( v25 > 7 )
    v18 = v24[0];
  try
  {
    Windows::Internal::Notifications::AdaptiveNotification::ParseJsonPayload(
      (Windows::Internal::Notifications::AdaptiveNotification *)this,
      v18);
    std::wstring::~wstring(v24);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v29);
    std::string::~string(&v26);
    result = 0;
  }
  catch ( ... )
  {
    v23 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x23,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
            v19);
    std::wstring::~wstring(v24);
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v29);
    std::string::~string(&v26);
    return v23;
  }
  return result;
}

```

## disassembly

```asm
0x180023ba4  push    rbx
0x180023ba6  push    rsi
0x180023ba7  push    rdi
0x180023ba8  push    r14
0x180023baa  push    r15
0x180023bac  sub     rsp, 100h
0x180023bb3  mov     rax, cs:__security_cookie
0x180023bba  xor     rax, rsp
0x180023bbd  mov     [rsp+128h+var_38], rax
0x180023bc5  mov     r15d, r9d
0x180023bc8  mov     r14, r8
0x180023bcb  mov     rdi, rdx
0x180023bce  mov     rsi, rcx
0x180023bd1  test    rdx, rdx
0x180023bd4  jnz     short loc_180023BFC
0x180023bd6  lea     edx, [rdi+13h]; void *
0x180023bd9  mov     ebx, 80070057h
0x180023bde  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023be5  mov     r9d, ebx; char *
0x180023be8  mov     rcx, [rsp+128h]; this
0x180023bf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023bf5  mov     eax, ebx
0x180023bf7  jmp     loc_180023DEF
0x180023bfc  test    r14, r14
0x180023bff  jnz     short loc_180023C07
0x180023c01  lea     edx, [r14+14h]
0x180023c05  jmp     short loc_180023BD9
0x180023c07  test    r9d, r9d
0x180023c0a  jnz     short loc_180023C12
0x180023c0c  lea     edx, [r9+15h]
0x180023c10  jmp     short loc_180023BD9
0x180023c12  lea     rbx, [rcx+48h]
0x180023c16  cmp     rdi, [rbx]
0x180023c19  jz      short loc_180023C44
0x180023c1b  mov     rcx, [rbx]; string
0x180023c1e  call    cs:__imp_WindowsDeleteString
0x180023c24  mov     qword ptr [rbx], 0
0x180023c2b  mov     rdx, rbx; newString
0x180023c2e  mov     rcx, rdi; string
0x180023c31  call    cs:__imp_WindowsDuplicateString
0x180023c37  mov     ebx, eax
0x180023c39  test    eax, eax
0x180023c3b  jns     short loc_180023C44
0x180023c3d  mov     edx, 16h
0x180023c42  jmp     short loc_180023BDE
0x180023c44  xorps   xmm0, xmm0
0x180023c47  movups  [rsp+128h+var_E0], xmm0
0x180023c4c  mov     [rsp+128h+var_D0], 0
0x180023c55  mov     [rsp+128h+var_C8], 0
0x180023c5e  mov     r8, r15
0x180023c61  mov     rdx, r14
0x180023c64  lea     rcx, [rsp+128h+var_E0]
0x180023c69  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180023c6e  nop
0x180023c6f  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180023c76  mov     [rsp+128h+var_B8], rax
0x180023c7b  mov     cl, 1
0x180023c7d  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180023c83  mov     [rsp+128h+var_A0], rax
0x180023c8b  lea     rcx, [rsp+128h+var_98]
0x180023c93  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180023c98  nop
0x180023c99  lea     rcx, [rsp+128h+var_78]
0x180023ca1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023ca6  nop
0x180023ca7  mov     [rsp+128h+var_50], 0
0x180023cb1  mov     [rsp+128h+var_4E], 0
0x180023cb9  mov     ecx, 40h ; '@'; Size
0x180023cbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023cc3  mov     rbx, rax
0x180023cc6  mov     qword ptr [rsp+128h+var_108], rax
0x180023ccb  xor     edx, edx
0x180023ccd  mov     rcx, rax
0x180023cd0  call    cs:__imp_??0?$codecvt@GDU_Mbstatet@@@std@@QEAA@_K@Z; std::codecvt<ushort,char,_Mbstatet>::codecvt<ushort,char,_Mbstatet>(unsigned __int64)
0x180023cd6  lea     rax, ??_7?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@6B@; const std::codecvt_utf8_utf16<ushort,1114111,0>::`vftable'
0x180023cdd  mov     [rbx], rax
0x180023ce0  mov     rdx, rbx
0x180023ce3  lea     rcx, [rsp+128h+var_B8]
0x180023ce8  call    ?_Init@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@AEAAXPEBV?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::_Init(std::codecvt_utf8_utf16<ushort,1114111,0> const *)
0x180023ced  nop
0x180023cee  lea     r8, [rsp+128h+var_E0]
0x180023cf3  cmp     [rsp+128h+var_C8], 0Fh
0x180023cf9  cmova   r8, qword ptr [rsp+128h+var_E0]
0x180023cff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023d03  inc     rax
0x180023d06  cmp     byte ptr [r8+rax], 0
0x180023d0b  jnz     short loc_180023D03
0x180023d0d  lea     r9, [rax+r8]
0x180023d11  lea     rdx, [rsp+128h+var_100]
0x180023d16  lea     rcx, [rsp+128h+var_B8]
0x180023d1b  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180023d20  nop
0x180023d21  lea     rcx, [rsi+50h]; this
0x180023d25  lea     rax, [rsp+128h+var_100]
0x180023d2a  cmp     [rsp+128h+var_E8], 7
0x180023d30  cmova   rax, [rsp+128h+var_100]
0x180023d36  mov     qword ptr [rsp+128h+var_108], rax; int
0x180023d3b  lea     rdx, [rsp+128h+var_108]
0x180023d40  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180023d45  mov     ebx, eax
0x180023d47  test    eax, eax
0x180023d49  jns     short loc_180023D8D
0x180023d4b  mov     rcx, [rsp+128h]; this
0x180023d53  mov     r9d, eax; char *
0x180023d56  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023d5d  mov     edx, 1Ch; void *
0x180023d62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d67  nop
0x180023d68  lea     rcx, [rsp+128h+var_100]
0x180023d6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023d72  nop
0x180023d73  lea     rcx, [rsp+128h+var_B8]
0x180023d78  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180023d7d  nop
0x180023d7e  lea     rcx, [rsp+128h+var_E0]
0x180023d83  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180023d88  jmp     loc_180023BF5
0x180023d8d  lea     rdx, [rsp+128h+var_100]
0x180023d92  cmp     [rsp+128h+var_E8], 7
0x180023d98  cmova   rdx, [rsp+128h+var_100]; unsigned __int16 *
0x180023d9e  mov     rcx, rsi; this
0x180023da1  call    ?ParseJsonPayload@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::Notifications::AdaptiveNotification::ParseJsonPayload(ushort const *)
0x180023da6  nop
0x180023da7  lea     rcx, [rsp+128h+var_100]
0x180023dac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023db1  nop
0x180023db2  lea     rcx, [rsp+128h+var_B8]
0x180023db7  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180023dbc  nop
0x180023dbd  lea     rcx, [rsp+128h+var_E0]
0x180023dc2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180023dc7  xor     eax, eax
0x180023dc9  jmp     short loc_180023DEF
0x180023dcb  lea     rcx, [rsp+128h+var_100]
0x180023dd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023dd5  nop
0x180023dd6  lea     rcx, [rsp+128h+var_B8]
0x180023ddb  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180023de0  nop
0x180023de1  lea     rcx, [rsp+128h+var_E0]
0x180023de6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180023deb  mov     eax, [rsp+128h+var_108]
0x180023def  mov     rcx, [rsp+128h+var_38]
0x180023df7  xor     rcx, rsp; StackCookie
0x180023dfa  call    __security_check_cookie
0x180023dff  add     rsp, 100h
0x180023e06  pop     r15
0x180023e08  pop     r14
0x180023e0a  pop     rdi
0x180023e0b  pop     rsi
0x180023e0c  pop     rbx
0x180023e0d  retn
```
