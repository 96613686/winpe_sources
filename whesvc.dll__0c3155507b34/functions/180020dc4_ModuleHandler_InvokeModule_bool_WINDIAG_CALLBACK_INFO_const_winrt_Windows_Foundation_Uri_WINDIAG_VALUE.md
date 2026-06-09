# ModuleHandler::InvokeModule(bool,_WINDIAG_CALLBACK_INFO const *,winrt::Windows::Foundation::Uri,_WINDIAG_VALUE *)

- ea: `0x180020dc4`
- end: `0x1800211a2`
- name: `?InvokeModule@ModuleHandler@@AEAAJ_NPEBU_WINDIAG_CALLBACK_INFO@@UUri@Foundation@Windows@winrt@@PEAU_WINDIAG_VALUE@@@Z`
- size: `990`
- prototype: `__int64 __fastcall(__int64, char, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x1800032e0`
- `0x180003e10`
- `0x180003e34`
- `0x1800066dc`
- `0x180009044`
- `0x180011578`
- `0x1800152f8`
- `0x180016754`
- `0x18001997c`
- `0x18001bfec`
- `0x18001c884`
- `0x180020dc4`
- `0x18002275c`
- `0x1800233d8`
- `0x180023efc`
- `0x1800255e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021089`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021090`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021097`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002109e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021089`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021090`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021097`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002109e`

## pseudocode

```c
__int64 __fastcall ModuleHandler::InvokeModule(__int64 a1, char a2, __int64 a3, _QWORD *a4)
{
  int v7; // r14d
  __int64 v8; // rcx
  bool v9; // si
  void *v10; // rdi
  int v11; // eax
  HANDLE ProcessHeap; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rcx
  int v15; // edi
  void *v16; // rsi
  int v17; // ecx
  HANDLE v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  bool v21; // si
  void *v22; // rdi
  int v23; // eax
  HANDLE v24; // rax
  __int64 v25; // rax
  const WCHAR *v26; // rcx
  void *v27; // rsi
  int v28; // ecx
  HANDLE v29; // rax
  const char *v30; // rdx
  char *v31; // rcx
  int started; // eax
  __int64 v33; // r9
  __int64 v34; // rdx
  __int64 v36; // [rsp+20h] [rbp-81h] BYREF
  __int64 v37; // [rsp+28h] [rbp-79h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-71h] BYREF
  LPVOID v39; // [rsp+38h] [rbp-69h] BYREF
  LPVOID v40; // [rsp+40h] [rbp-61h] BYREF
  LPVOID v41; // [rsp+48h] [rbp-59h] BYREF
  __int64 *v42; // [rsp+50h] [rbp-51h] BYREF
  int v43; // [rsp+58h] [rbp-49h]
  _QWORD *v44; // [rsp+60h] [rbp-41h]
  _BYTE v45[8]; // [rsp+68h] [rbp-39h] BYREF
  int v46; // [rsp+70h] [rbp-31h]
  char *Src[2]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v48; // [rsp+88h] [rbp-19h]
  unsigned __int64 v49; // [rsp+90h] [rbp-11h]
  char *v50[2]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v51; // [rsp+A8h] [rbp+7h]
  unsigned __int64 v52; // [rsp+B0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v44 = a4;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  v52 = 15;
  LOBYTE(v50[0]) = 0;
  *(_OWORD *)Src = 0;
  v48 = 0;
  v49 = 15;
  LOBYTE(Src[0]) = 0;
  winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(
    a4,
    &v37);
  v42 = &v37;
  v7 = 0;
  v43 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(
    &v37,
    v45);
  while ( 1 )
  {
    if ( v7 == v46 )
    {
      if ( v37 )
        winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v37);
      if ( v48 && v51 )
      {
        v30 = (const char *)v50;
        v31 = (char *)Src;
        if ( a2 )
        {
          if ( v52 > 0xF )
            v30 = v50[0];
          if ( v49 > 0xF )
            v31 = Src[0];
          v15 = QueueHeavyWindiagModuleWithUri(
                  v31,
                  v30,
                  *(void *const *)(*(_QWORD *)(a3 + 16) + 8LL),
                  *(_DWORD *)(*(_QWORD *)(a3 + 16) + 16LL));
          goto LABEL_73;
        }
        if ( v52 > 0xF )
          v30 = v50[0];
        if ( v49 > 0xF )
          v31 = Src[0];
        started = StartWindiagModuleWithUri(
                    v31,
                    v30,
                    *(void *const *)(*(_QWORD *)(a3 + 16) + 8LL),
                    *(_DWORD *)(*(_QWORD *)(a3 + 16) + 16LL));
        v15 = started;
        if ( started >= 0 )
        {
          v15 = 0;
          goto LABEL_73;
        }
        v33 = (unsigned int)started;
        v34 = 983;
      }
      else
      {
        v15 = -2147024809;
        v33 = 2147942487LL;
        v34 = 966;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
        (const char *)v33,
        v36);
      goto LABEL_73;
    }
    winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(&v42, &v36);
    v8 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(
                      &v36,
                      &lpMem);
    v9 = v8 && *(_DWORD *)(v8 + 4) == 3 && wmemcmp(*(const wchar_t **)(v8 + 16), L"mod", 3u) == 0;
    v10 = lpMem;
    if ( lpMem )
    {
      v11 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v10);
      }
      lpMem = 0;
    }
    if ( !v9 )
      break;
    v13 = winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(
            &v36,
            &v39);
    if ( *(_QWORD *)v13 )
      v14 = *(const WCHAR **)(*(_QWORD *)v13 + 16LL);
    else
      v14 = &WideCharStr;
    v15 = ConvertWideStringToUTF8String(v14, Src);
    v16 = v39;
    if ( v39 )
    {
      v17 = _InterlockedDecrement((volatile signed __int32 *)v39 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
      }
      else
      {
        v18 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v18, 0, v16);
      }
      v39 = 0;
    }
    if ( v15 < 0 )
    {
      v19 = 955;
      goto LABEL_23;
    }
LABEL_46:
    if ( v36 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v36);
    v43 = ++v7;
  }
  v20 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(
                     &v36,
                     &v40);
  v21 = v20 && *(_DWORD *)(v20 + 4) == 10 && wmemcmp(*(const wchar_t **)(v20 + 16), L"instanceid", 0xAu) == 0;
  v22 = v40;
  if ( v40 )
  {
    v23 = _InterlockedDecrement((volatile signed __int32 *)v40 + 6);
    if ( v23 )
    {
      if ( v23 < 0 )
        abort();
    }
    else
    {
      v24 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v24, 0, v22);
    }
    v40 = 0;
  }
  if ( !v21 )
    goto LABEL_46;
  v25 = winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(
          &v36,
          &v41);
  if ( *(_QWORD *)v25 )
    v26 = *(const WCHAR **)(*(_QWORD *)v25 + 16LL);
  else
    v26 = &WideCharStr;
  v15 = ConvertWideStringToUTF8String(v26, v50);
  v27 = v41;
  if ( v41 )
  {
    v28 = _InterlockedDecrement((volatile signed __int32 *)v41 + 6);
    if ( v28 )
    {
      if ( v28 < 0 )
        abort();
    }
    else
    {
      v29 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v29, 0, v27);
    }
    v41 = 0;
  }
  if ( v15 >= 0 )
    goto LABEL_46;
  v19 = 959;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
    (const char *)(unsigned int)v15,
    v36);
  if ( v36 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v36);
  if ( v37 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v37);
LABEL_73:
  std::string::~string(Src);
  std::string::~string(v50);
  if ( *a4 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a4);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180020dc4  mov     [rsp-8+arg_0], rbx
0x180020dc9  push    rbp
0x180020dca  push    rsi
0x180020dcb  push    rdi
0x180020dcc  push    r12
0x180020dce  push    r13
0x180020dd0  push    r14
0x180020dd2  push    r15
0x180020dd4  lea     rbp, [rsp-1Fh]
0x180020dd9  sub     rsp, 0C0h
0x180020de0  mov     rax, cs:__security_cookie
0x180020de7  xor     rax, rsp
0x180020dea  mov     [rbp+4Fh+var_38], rax
0x180020dee  mov     rbx, r9
0x180020df1  mov     r13, r8
0x180020df4  mov     r15b, dl
0x180020df7  mov     [rbp+4Fh+var_90], rbx
0x180020dfb  xorps   xmm0, xmm0
0x180020dfe  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x180020e02  xor     r12d, r12d
0x180020e05  mov     [rbp+4Fh+var_48], r12
0x180020e09  lea     edi, [r12+0Fh]
0x180020e0e  mov     [rbp+4Fh+var_40], rdi
0x180020e12  mov     byte ptr [rbp+4Fh+var_58], r12b
0x180020e16  movups  xmmword ptr [rbp+4Fh+Src], xmm0
0x180020e1a  mov     [rbp+4Fh+var_68], r12
0x180020e1e  mov     [rbp+4Fh+var_60], rdi
0x180020e22  mov     byte ptr [rbp+4Fh+Src], r12b
0x180020e26  lea     rdx, [rbp+4Fh+var_C8]
0x180020e2a  mov     rcx, r9
0x180020e2d  call    ?QueryParsed@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::QueryParsed(void)
0x180020e32  nop
0x180020e33  lea     rax, [rbp+4Fh+var_C8]
0x180020e37  mov     [rbp+4Fh+var_A0], rax
0x180020e3b  mov     r14d, r12d
0x180020e3e  mov     [rbp+4Fh+var_98], r12d
0x180020e42  lea     rdx, [rbp+4Fh+var_88]
0x180020e46  lea     rcx, [rbp+4Fh+var_C8]
0x180020e4a  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@UIWwwFormUrlDecoderEntry@234@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass,winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::end(void)
0x180020e4f  cmp     r14d, [rbp+4Fh+var_80]
0x180020e53  jz      loc_1800210AF
0x180020e59  lea     rdx, [rsp+0F0h+var_D0]
0x180020e5e  lea     rcx, [rbp+4Fh+var_A0]
0x180020e62  call    ??D?$fast_iterator@UIWwwFormUrlDecoderRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA?AUIWwwFormUrlDecoderEntry@Foundation@Windows@2@XZ; winrt::impl::fast_iterator<winrt::Windows::Foundation::IWwwFormUrlDecoderRuntimeClass>::operator*(void)
0x180020e67  nop
0x180020e68  lea     rdx, [rbp+4Fh+lpMem]
0x180020e6c  lea     rcx, [rsp+0F0h+var_D0]
0x180020e71  call    ?Name@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(void)
0x180020e76  mov     rcx, [rax]
0x180020e79  test    rcx, rcx
0x180020e7c  jz      short loc_180020EA0
0x180020e7e  mov     r8d, [rcx+4]; N
0x180020e82  cmp     r8, 3
0x180020e86  jnz     short loc_180020EA0
0x180020e88  lea     rdx, aMod; "mod"
0x180020e8f  mov     rcx, [rcx+10h]; S1
0x180020e93  call    wmemcmp
0x180020e98  test    eax, eax
0x180020e9a  setz    sil
0x180020e9e  jmp     short loc_180020EA3
0x180020ea0  mov     sil, r12b
0x180020ea3  mov     rdi, [rbp+4Fh+lpMem]
0x180020ea7  test    rdi, rdi
0x180020eaa  jz      short loc_180020EDA
0x180020eac  or      eax, 0FFFFFFFFh
0x180020eaf  lock xadd [rdi+18h], eax
0x180020eb4  sub     eax, 1
0x180020eb7  jnz     short loc_180020ECE
0x180020eb9  nop
0x180020eba  call    WINRT_IMPL_GetProcessHeap
0x180020ebf  mov     rcx, rax; hHeap
0x180020ec2  mov     r8, rdi; lpMem
0x180020ec5  xor     edx, edx; dwFlags
0x180020ec7  call    WINRT_IMPL_HeapFree
0x180020ecc  jmp     short loc_180020ED6
0x180020ece  test    eax, eax
0x180020ed0  js      loc_180021089
0x180020ed6  mov     [rbp+4Fh+lpMem], r12
0x180020eda  lea     rcx, [rsp+0F0h+var_D0]
0x180020edf  test    sil, sil
0x180020ee2  jz      loc_180020F94
0x180020ee8  lea     rdx, [rbp+4Fh+var_B8]
0x180020eec  call    ?Value@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(void)
0x180020ef1  nop
0x180020ef2  mov     rcx, [rax]
0x180020ef5  test    rcx, rcx
0x180020ef8  jz      short loc_180020F00
0x180020efa  mov     rcx, [rcx+10h]
0x180020efe  jmp     short loc_180020F07
0x180020f00  lea     rcx, WideCharStr; lpWideCharStr
0x180020f07  lea     rdx, [rbp+4Fh+Src]; Src
0x180020f0b  call    ?ConvertWideStringToUTF8String@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConvertWideStringToUTF8String(ushort const *,std::string &)
0x180020f10  mov     edi, eax
0x180020f12  mov     rsi, [rbp+4Fh+var_B8]
0x180020f16  test    rsi, rsi
0x180020f19  jz      short loc_180020F49
0x180020f1b  or      ecx, 0FFFFFFFFh
0x180020f1e  lock xadd [rsi+18h], ecx
0x180020f23  sub     ecx, 1
0x180020f26  jnz     short loc_180020F3D
0x180020f28  nop
0x180020f29  call    WINRT_IMPL_GetProcessHeap
0x180020f2e  mov     rcx, rax; hHeap
0x180020f31  mov     r8, rsi; lpMem
0x180020f34  xor     edx, edx; dwFlags
0x180020f36  call    WINRT_IMPL_HeapFree
0x180020f3b  jmp     short loc_180020F45
0x180020f3d  test    ecx, ecx
0x180020f3f  js      loc_180021090
0x180020f45  mov     [rbp+4Fh+var_B8], r12
0x180020f49  test    edi, edi
0x180020f4b  jns     loc_18002106C
0x180020f51  mov     edx, 3BBh; void *
0x180020f56  mov     r9d, edi; char *
0x180020f59  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180020f60  mov     rcx, [rbp+57h]; this
0x180020f64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f69  nop
0x180020f6a  cmp     [rsp+0F0h+var_D0], r12
0x180020f6f  jz      short loc_180020F7C
0x180020f71  lea     rcx, [rsp+0F0h+var_D0]
0x180020f76  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180020f7b  nop
0x180020f7c  cmp     [rbp+4Fh+var_C8], r12
0x180020f80  jz      loc_180021158
0x180020f86  lea     rcx, [rbp+4Fh+var_C8]
0x180020f8a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180020f8f  jmp     loc_180021158
0x180020f94  lea     rdx, [rbp+4Fh+var_B0]
0x180020f98  call    ?Name@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Name(void)
0x180020f9d  mov     rcx, [rax]
0x180020fa0  test    rcx, rcx
0x180020fa3  jz      short loc_180020FC7
0x180020fa5  mov     r8d, [rcx+4]; N
0x180020fa9  cmp     r8, 0Ah
0x180020fad  jnz     short loc_180020FC7
0x180020faf  lea     rdx, aInstanceid; "instanceid"
0x180020fb6  mov     rcx, [rcx+10h]; S1
0x180020fba  call    wmemcmp
0x180020fbf  test    eax, eax
0x180020fc1  setz    sil
0x180020fc5  jmp     short loc_180020FCA
0x180020fc7  mov     sil, r12b
0x180020fca  mov     rdi, [rbp+4Fh+var_B0]
0x180020fce  test    rdi, rdi
0x180020fd1  jz      short loc_180021001
0x180020fd3  or      eax, 0FFFFFFFFh
0x180020fd6  lock xadd [rdi+18h], eax
0x180020fdb  sub     eax, 1
0x180020fde  jnz     short loc_180020FF5
0x180020fe0  nop
0x180020fe1  call    WINRT_IMPL_GetProcessHeap
0x180020fe6  mov     rcx, rax; hHeap
0x180020fe9  mov     r8, rdi; lpMem
0x180020fec  xor     edx, edx; dwFlags
0x180020fee  call    WINRT_IMPL_HeapFree
0x180020ff3  jmp     short loc_180020FFD
0x180020ff5  test    eax, eax
0x180020ff7  js      loc_180021097
0x180020ffd  mov     [rbp+4Fh+var_B0], r12
0x180021001  test    sil, sil
0x180021004  jz      short loc_18002106C
0x180021006  lea     rdx, [rbp+4Fh+var_A8]
0x18002100a  lea     rcx, [rsp+0F0h+var_D0]
0x18002100f  call    ?Value@?$consume_Windows_Foundation_IWwwFormUrlDecoderEntry@UIWwwFormUrlDecoderEntry@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IWwwFormUrlDecoderEntry<winrt::Windows::Foundation::IWwwFormUrlDecoderEntry>::Value(void)
0x180021014  nop
0x180021015  mov     rcx, [rax]
0x180021018  test    rcx, rcx
0x18002101b  jz      short loc_180021023
0x18002101d  mov     rcx, [rcx+10h]
0x180021021  jmp     short loc_18002102A
0x180021023  lea     rcx, WideCharStr; lpWideCharStr
0x18002102a  lea     rdx, [rbp+4Fh+var_58]; Src
0x18002102e  call    ?ConvertWideStringToUTF8String@@YAJPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; ConvertWideStringToUTF8String(ushort const *,std::string &)
0x180021033  mov     edi, eax
0x180021035  mov     rsi, [rbp+4Fh+var_A8]
0x180021039  test    rsi, rsi
0x18002103c  jz      short loc_180021068
0x18002103e  or      ecx, 0FFFFFFFFh
0x180021041  lock xadd [rsi+18h], ecx
0x180021046  sub     ecx, 1
0x180021049  jnz     short loc_180021060
0x18002104b  nop
0x18002104c  call    WINRT_IMPL_GetProcessHeap
0x180021051  mov     rcx, rax; hHeap
0x180021054  mov     r8, rsi; lpMem
0x180021057  xor     edx, edx; dwFlags
0x180021059  call    WINRT_IMPL_HeapFree
0x18002105e  jmp     short loc_180021064
0x180021060  test    ecx, ecx
0x180021062  js      short loc_18002109E
0x180021064  mov     [rbp+4Fh+var_A8], r12
0x180021068  test    edi, edi
0x18002106a  js      short loc_1800210A5
0x18002106c  cmp     [rsp+0F0h+var_D0], r12
0x180021071  jz      short loc_18002107D
0x180021073  lea     rcx, [rsp+0F0h+var_D0]
0x180021078  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002107d  inc     r14d
0x180021080  mov     [rbp+4Fh+var_98], r14d
0x180021084  jmp     loc_180020E4F
0x180021089  call    cs:__imp_abort
0x180021090  call    cs:__imp_abort
0x180021097  call    cs:__imp_abort
0x18002109e  call    cs:__imp_abort
0x1800210a5  mov     edx, 3BFh
0x1800210aa  jmp     loc_180020F56
0x1800210af  cmp     [rbp+4Fh+var_C8], r12
0x1800210b3  jz      short loc_1800210BE
0x1800210b5  lea     rcx, [rbp+4Fh+var_C8]
0x1800210b9  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800210be  cmp     [rbp+4Fh+var_68], r12
0x1800210c2  jz      short loc_18002113A
0x1800210c4  cmp     [rbp+4Fh+var_48], r12
0x1800210c8  jz      short loc_18002113A
0x1800210ca  lea     rdx, [rbp+4Fh+var_58]
0x1800210ce  lea     rcx, [rbp+4Fh+Src]
0x1800210d2  test    r15b, r15b
0x1800210d5  jz      short loc_180021100
0x1800210d7  mov     rax, [r13+10h]
0x1800210db  cmp     [rbp+4Fh+var_40], 0Fh
0x1800210e0  cmova   rdx, [rbp+4Fh+var_58]; char *
0x1800210e5  cmp     [rbp+4Fh+var_60], 0Fh
0x1800210ea  cmova   rcx, [rbp+4Fh+Src]; char *
0x1800210ef  mov     r9d, [rax+10h]; unsigned int
0x1800210f3  mov     r8, [rax+8]; void *
0x1800210f7  call    ?QueueHeavyWindiagModuleWithUri@@YAJPEBD0QEAXK@Z; QueueHeavyWindiagModuleWithUri(char const *,char const *,void * const,ulong)
0x1800210fc  mov     edi, eax
0x1800210fe  jmp     short loc_180021158
0x180021100  cmp     [rbp+4Fh+var_40], 0Fh
0x180021105  cmova   rdx, [rbp+4Fh+var_58]; char *
0x18002110a  cmp     [rbp+4Fh+var_60], 0Fh
0x18002110f  cmova   rcx, [rbp+4Fh+Src]; char *
0x180021114  mov     r8, [r13+10h]
0x180021118  mov     r9d, [r8+10h]; unsigned int
0x18002111c  mov     r8, [r8+8]; void *
0x180021120  call    ?StartWindiagModuleWithUri@@YAJPEBD0QEAXK@Z; StartWindiagModuleWithUri(char const *,char const *,void * const,ulong)
0x180021125  mov     edi, eax
0x180021127  test    eax, eax
0x180021129  jns     short loc_180021135
0x18002112b  mov     r9d, eax
0x18002112e  mov     edx, 3D7h
0x180021133  jmp     short loc_180021147
0x180021135  mov     edi, r12d
0x180021138  jmp     short loc_180021158
0x18002113a  mov     edi, 80070057h
0x18002113f  mov     r9d, edi; char *
0x180021142  mov     edx, 3C6h; void *
0x180021147  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x18002114e  mov     rcx, [rbp+57h]; this
0x180021152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021157  nop
0x180021158  lea     rcx, [rbp+4Fh+Src]
0x18002115c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180021161  nop
0x180021162  lea     rcx, [rbp+4Fh+var_58]
0x180021166  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002116b  nop
0x18002116c  cmp     [rbx], r12
0x18002116f  jz      short loc_180021179
0x180021171  mov     rcx, rbx
0x180021174  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180021179  mov     eax, edi
0x18002117b  mov     rcx, [rbp+4Fh+var_38]
0x18002117f  xor     rcx, rsp; StackCookie
0x180021182  call    __security_check_cookie
0x180021187  mov     rbx, [rsp+0F0h+arg_0]
0x18002118f  add     rsp, 0C0h
0x180021196  pop     r15
0x180021198  pop     r14
0x18002119a  pop     r13
0x18002119c  pop     r12
0x18002119e  pop     rdi
0x18002119f  pop     rsi
0x1800211a0  pop     rbp
0x1800211a1  retn
```
