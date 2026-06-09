# SecurityLogicControl::GetString(int,ushort const *)

- ea: `0x1800052cc`
- end: `0x1800054e9`
- name: `?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z`
- size: `541`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000592c`
- `0x180005cf4`
- `0x18000750c`

## callees

- `0x180001b90`
- `0x18000485c`
- `0x180004a1c`
- `0x180004aa4`
- `0x180004c48`
- `0x180004f20`
- `0x180005220`
- `0x1800052cc`
- `0x180005658`
- `0x1800061e4`
- `0x180006284`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800054b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800054b1`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800053ee`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800053ee`

## string_xrefs

- `0x18000534c`: `wscsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char **__fastcall SecurityLogicControl::GetString(char **a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rbx
  char **v5; // rsi
  HMODULE v6; // r14
  HMODULE Library; // rax
  int *v8; // r15
  __int64 v9; // rbx
  char *v11; // [rsp+20h] [rbp-268h] BYREF
  HMODULE v12; // [rsp+28h] [rbp-260h]
  unsigned __int16 *v13; // [rsp+30h] [rbp-258h] BYREF
  int v14; // [rsp+38h] [rbp-250h]
  char **v15; // [rsp+40h] [rbp-248h]
  WCHAR pszOutBuf[256]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  v5 = a1;
  v15 = a1;
  v13 = a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    byte_18000F684);
  v14 = 1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v11,
    byte_18000F684);
  v6 = 0;
  v12 = 0;
  if ( a2 == -1 )
    goto LABEL_21;
  try
  {
    if ( a2 - 200 > 0x63 )
    {
      if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                           &v11,
                           a2) )
        goto LABEL_28;
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"wscsvc.dll");
      v6 = Library;
      v12 = Library;
      if ( !Library
        || (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                           &v11,
                           Library,
                           a2) )
      {
        goto LABEL_28;
      }
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, byte_18000F684, 0);
  }
  catch ( ATL::CAtlException )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v11, byte_18000F684, 0);
    if ( v12 )
    {
      FreeLibrary(v12);
      v12 = 0;
    }
    v6 = v12;
    v5 = v15;
    v3 = v13;
  }
LABEL_28:
  if ( v3 && *v3 )
  {
    if ( SHLoadIndirectString(v3, pszOutBuf, 0xFFu, 0) >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v13,
        pszOutBuf);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((const wchar_t **)&v13);
      StringCchCopyW(pszOutBuf, 0xFFu, v13);
      ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
    }
    else
    {
      pszOutBuf[0] = 0;
    }
    try
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatMessageW(
        v5,
        v11,
        pszOutBuf);
    }
    catch ( ATL::CAtlException )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v15);
      v6 = v12;
      v5 = v15;
    }
  }
  else
  {
    v8 = (int *)(*v5 - 24);
    if ( v11 - 24 != (char *)v8 )
    {
      if ( v8[4] >= 0 && *((_QWORD *)v11 - 3) == *(_QWORD *)v8 )
      {
        v9 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v8);
        *v5 = (char *)(v9 + 24);
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v5, v11, *((_DWORD *)v11 - 4));
      }
    }
  }
  if ( v6 )
    FreeLibrary(v6);
LABEL_21:
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  return v5;
}

```

## disassembly

```asm
0x1800052cc  push    rbx
0x1800052ce  push    rsi
0x1800052cf  push    rdi
0x1800052d0  push    r14
0x1800052d2  push    r15
0x1800052d4  sub     rsp, 260h
0x1800052db  mov     rax, cs:__security_cookie
0x1800052e2  xor     rax, rsp
0x1800052e5  mov     [rsp+288h+var_38], rax
0x1800052ed  mov     rbx, r8
0x1800052f0  mov     r15d, edx
0x1800052f3  mov     rsi, rcx
0x1800052f6  mov     [rsp+288h+var_248], rcx
0x1800052fb  mov     [rsp+288h+var_258], rbx
0x180005300  mov     edi, 1
0x180005305  mov     [rsp+288h+var_250], edi
0x180005309  lea     rdx, byte_18000F684
0x180005310  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180005315  nop
0x180005316  mov     [rsp+288h+var_250], edi
0x18000531a  lea     rdx, byte_18000F684
0x180005321  lea     rcx, [rsp+288h+var_268]
0x180005326  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000532b  nop
0x18000532c  xor     edi, edi
0x18000532e  mov     r14d, edi
0x180005331  mov     [rsp+288h+var_260], rdi
0x180005336  cmp     r15d, 0FFFFFFFFh
0x18000533a  jz      loc_1800054B8
0x180005340  lea     eax, [r15-0C8h]
0x180005347  cmp     eax, 63h ; 'c'
0x18000534a  ja      short loc_18000538F
0x18000534c  lea     rcx, aWscsvcDll; "wscsvc.dll"
0x180005353  call    IsolationAwareLoadLibraryExW
0x180005358  mov     r14, rax
0x18000535b  mov     [rsp+288h+var_260], rax
0x180005360  test    rax, rax
0x180005363  jz      short loc_1800053B5
0x180005365  mov     r8d, r15d
0x180005368  mov     rdx, rax
0x18000536b  lea     rcx, [rsp+288h+var_268]
0x180005370  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x180005375  test    eax, eax
0x180005377  jnz     short loc_1800053B5
0x180005379  xor     r8d, r8d
0x18000537c  lea     rdx, byte_18000F684
0x180005383  lea     rcx, [rsp+288h+var_268]
0x180005388  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000538d  jmp     short loc_1800053B5
0x18000538f  mov     edx, r15d
0x180005392  lea     rcx, [rsp+288h+var_268]
0x180005397  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000539c  test    eax, eax
0x18000539e  jnz     short loc_1800053B5
0x1800053a0  xor     r8d, r8d
0x1800053a3  lea     rdx, byte_18000F684
0x1800053aa  lea     rcx, [rsp+288h+var_268]
0x1800053af  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800053b4  nop
0x1800053b5  jmp     short loc_1800053C8
0x1800053b7  xor     edi, edi
0x1800053b9  mov     r14, [rsp+288h+var_260]
0x1800053be  mov     rsi, [rsp+288h+var_248]
0x1800053c3  mov     rbx, [rsp+288h+var_258]
0x1800053c8  test    rbx, rbx
0x1800053cb  jz      loc_18000545C
0x1800053d1  cmp     [rbx], di
0x1800053d4  jz      loc_18000545C
0x1800053da  xor     r9d, r9d; ppvReserved
0x1800053dd  mov     r15d, 0FFh
0x1800053e3  mov     r8d, r15d; cchOutBuf
0x1800053e6  lea     rdx, [rsp+288h+pszOutBuf]; pszOutBuf
0x1800053eb  mov     rcx, rbx; pszSource
0x1800053ee  call    cs:__imp_SHLoadIndirectString
0x1800053f4  test    eax, eax
0x1800053f6  jns     short loc_1800053FF
0x1800053f8  mov     [rsp+288h+pszOutBuf], di
0x1800053fd  jmp     short loc_18000543B
0x1800053ff  lea     rdx, [rsp+288h+pszOutBuf]
0x180005404  lea     rcx, [rsp+288h+var_258]
0x180005409  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000540e  nop
0x18000540f  lea     rcx, [rsp+288h+var_258]
0x180005414  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180005419  mov     r8, [rsp+288h+var_258]; unsigned __int16 *
0x18000541e  mov     rdx, r15; unsigned __int64
0x180005421  lea     rcx, [rsp+288h+pszOutBuf]; unsigned __int16 *
0x180005426  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000542b  nop
0x18000542c  mov     rcx, [rsp+288h+var_258]
0x180005431  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005435  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000543a  nop
0x18000543b  lea     r8, [rsp+288h+pszOutBuf]
0x180005440  mov     rdx, [rsp+288h+var_268]
0x180005445  mov     rcx, rsi
0x180005448  call    ?FormatMessageW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatMessageW(ushort const *,...)
0x18000544d  nop
0x18000544e  jmp     short loc_1800054A9
0x180005450  mov     r14, [rsp+288h+var_260]
0x180005455  mov     rsi, [rsp+288h+var_248]
0x18000545a  jmp     short loc_1800054A9
0x18000545c  mov     rcx, [rsp+288h+var_268]
0x180005461  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180005465  mov     r15, [rsi]
0x180005468  add     r15, 0FFFFFFFFFFFFFFE8h
0x18000546c  cmp     rcx, r15
0x18000546f  jz      short loc_1800054A9
0x180005471  cmp     [r15+10h], edi
0x180005475  jl      short loc_180005498
0x180005477  mov     rax, [r15]
0x18000547a  cmp     [rcx], rax
0x18000547d  jnz     short loc_180005498
0x18000547f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180005484  mov     rbx, rax
0x180005487  mov     rcx, r15; this
0x18000548a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000548f  lea     rax, [rbx+18h]
0x180005493  mov     [rsi], rax
0x180005496  jmp     short loc_1800054A9
0x180005498  mov     rdx, [rsp+288h+var_268]
0x18000549d  mov     r8d, [rdx-10h]
0x1800054a1  mov     rcx, rsi
0x1800054a4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800054a9  test    r14, r14
0x1800054ac  jz      short loc_1800054B8
0x1800054ae  mov     rcx, r14; hLibModule
0x1800054b1  call    cs:__imp_FreeLibrary
0x1800054b7  nop
0x1800054b8  mov     rcx, [rsp+288h+var_268]
0x1800054bd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800054c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800054c6  nop
0x1800054c7  mov     rax, rsi
0x1800054ca  mov     rcx, [rsp+288h+var_38]
0x1800054d2  xor     rcx, rsp; StackCookie
0x1800054d5  call    __security_check_cookie
0x1800054da  add     rsp, 260h
0x1800054e1  pop     r15
0x1800054e3  pop     r14
0x1800054e5  pop     rdi
0x1800054e6  pop     rsi
0x1800054e7  pop     rbx
0x1800054e8  retn
```
