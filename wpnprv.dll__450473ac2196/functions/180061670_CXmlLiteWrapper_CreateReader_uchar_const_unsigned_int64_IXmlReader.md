# CXmlLiteWrapper::CreateReader(uchar const *,unsigned __int64,IXmlReader * *)

- ea: `0x180061670`
- end: `0x1800619d5`
- name: `?CreateReader@CXmlLiteWrapper@@SAJPEBE_KPEAPEAUIXmlReader@@@Z`
- size: `869`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned __int64, struct IXmlReader **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d710`
- `0x18003deb4`
- `0x18003e6fc`
- `0x18003f0a0`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800613e4`
- `0x180061670`
- `0x1800619dc`
- `0x180096010`

## import_xrefs

- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x18006182d`
- `XmlLite!CreateXmlReaderInputWithEncodingCodePage` at `0x18006182d`

## string_xrefs

- `0x1800616e4`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x18006173b`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x1800617ca`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x180061869`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`
- `0x1800618e4`: `onecoreuap\base\diagnosis\platform\notifications\prov\trans\xmllitewrapper.cpp`

## pseudocode

```c
__int64 __fastcall CXmlLiteWrapper::CreateReader(
        const unsigned __int8 *a1,
        unsigned __int64 a2,
        struct IXmlReader **a3)
{
  PVOID v6; // rcx
  struct IXmlReader *v7; // rsi
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  int StreamForBuffer; // eax
  IUnknown *v12; // r14
  __int64 v13; // rdx
  HRESULT v14; // eax
  int inited; // eax
  int pwszBaseUri; // [rsp+20h] [rbp-20h]
  int pwszBaseUria; // [rsp+20h] [rbp-20h]
  IUnknown *pInputStream; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct IXmlReader *v21; // [rsp+70h] [rbp+30h] BYREF
  IXmlReaderInput *ppInput; // [rsp+88h] [rbp+48h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids);
  }
  v7 = 0;
  pInputStream = 0;
  v21 = 0;
  ppInput = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
      (const char *)0x80070057LL,
      pwszBaseUri);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v10 = 29;
LABEL_9:
      WPP_SF_d(v9[2], v10, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, 2147942487LL);
LABEL_46:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( a3 )
  {
    if ( *a3 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    *a3 = 0;
    StreamForBuffer = GetStreamForBuffer(a1, a2, (struct IStream **)&pInputStream);
    v12 = pInputStream;
    v8 = StreamForBuffer;
    if ( StreamForBuffer >= 0 )
    {
      v14 = CreateXmlReaderInputWithEncodingCodePage(pInputStream, 0, 0xFDE9u, 0, 0, &ppInput);
      v8 = v14;
      if ( v14 >= 0 )
      {
        inited = CreateAndInitXmlReader(ppInput, &v21);
        v8 = inited;
        if ( inited >= 0 )
        {
          *a3 = v21;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
              (unsigned int)inited);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
            (const char *)v8,
            pwszBaseUria);
          v9 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          {
            v7 = v21;
LABEL_44:
            if ( !v12 )
              goto LABEL_47;
            ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
            goto LABEL_46;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v8);
          v7 = v21;
        }
LABEL_43:
        v9 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
          (unsigned int)v14);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
        (const char *)v8,
        pwszBaseUria);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_44;
      v13 = 34;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids,
          (unsigned int)StreamForBuffer);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
        (const char *)v8,
        pwszBaseUri);
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_44;
      v13 = 32;
    }
    WPP_SF_d(v9[2], v13, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v8);
    goto LABEL_43;
  }
  v8 = -2147024809;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xB0,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\xmllitewrapper.cpp",
    (const char *)0x80070057LL,
    pwszBaseUri);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v10 = 30;
    goto LABEL_9;
  }
LABEL_47:
  if ( ppInput )
  {
    ((void (__fastcall *)(IXmlReaderInput *))ppInput->lpVtbl->Release)(ppInput);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    ppInput = 0;
  }
  if ( v7 )
  {
    ((void (__fastcall *)(struct IXmlReader *))v7->lpVtbl->Release)(v7);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 37, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180061670  mov     [rsp-28h+arg_8], rbx
0x180061675  mov     [rsp-28h+arg_10], rsi
0x18006167a  push    rbp
0x18006167b  push    rdi
0x18006167c  push    r12
0x18006167e  push    r13
0x180061680  push    r14
0x180061682  mov     rbp, rsp
0x180061685  sub     rsp, 40h
0x180061689  mov     rdi, r8
0x18006168c  mov     r14, rdx
0x18006168f  mov     rbx, rcx
0x180061692  mov     rcx, cs:WPP_GLOBAL_Control
0x180061699  lea     r12, WPP_GLOBAL_Control
0x1800616a0  lea     r13, WPP_6a50bd47d2f933c133a71650ffd97bab_Traceguids
0x1800616a7  cmp     rcx, r12
0x1800616aa  jz      short loc_1800616C9
0x1800616ac  test    byte ptr [rcx+1Ch], 4
0x1800616b0  jz      short loc_1800616C9
0x1800616b2  cmp     byte ptr [rcx+19h], 6
0x1800616b6  jb      short loc_1800616C9
0x1800616b8  mov     rcx, [rcx+10h]
0x1800616bc  mov     edx, 1Ch
0x1800616c1  mov     r8, r13
0x1800616c4  call    WPP_SF_
0x1800616c9  xor     esi, esi
0x1800616cb  mov     [rbp+pInputStream], 0
0x1800616d3  mov     [rbp+arg_0], rsi
0x1800616d7  mov     [rbp+arg_18], rsi
0x1800616db  test    rbx, rbx
0x1800616de  jnz     short loc_180061732
0x1800616e0  mov     rcx, [rbp+28h]; this
0x1800616e4  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800616eb  mov     r9d, 80070057h; char *
0x1800616f1  mov     edx, 0AFh; void *
0x1800616f6  mov     ebx, r9d
0x1800616f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800616fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180061705  cmp     rcx, r12
0x180061708  jz      loc_180061953
0x18006170e  test    byte ptr [rcx+1Ch], 80h
0x180061712  jz      loc_180061953
0x180061718  lea     edx, [rsi+1Dh]
0x18006171b  mov     rcx, [rcx+10h]
0x18006171f  mov     r9d, 80070057h
0x180061725  mov     r8, r13
0x180061728  call    WPP_SF_d
0x18006172d  jmp     loc_18006194C
0x180061732  test    rdi, rdi
0x180061735  jnz     short loc_180061774
0x180061737  mov     rcx, [rbp+28h]; this
0x18006173b  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061742  mov     r9d, 80070057h; char *
0x180061748  mov     edx, 0B0h; void *
0x18006174d  mov     ebx, r9d
0x180061750  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061755  mov     rcx, cs:WPP_GLOBAL_Control
0x18006175c  cmp     rcx, r12
0x18006175f  jz      loc_180061953
0x180061765  test    byte ptr [rcx+1Ch], 80h
0x180061769  jz      loc_180061953
0x18006176f  lea     edx, [rdi+1Eh]
0x180061772  jmp     short loc_18006171B
0x180061774  cmp     [rdi], rsi
0x180061777  jz      short loc_18006177E
0x180061779  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006177e  lea     r8, [rbp+pInputStream]; struct IStream **
0x180061782  mov     [rdi], rsi
0x180061785  mov     rdx, r14; unsigned __int64
0x180061788  mov     rcx, rbx; unsigned __int8 *
0x18006178b  call    ?GetStreamForBuffer@@YAJPEBE_KPEAPEAUIStream@@@Z; GetStreamForBuffer(uchar const *,unsigned __int64,IStream * *)
0x180061790  mov     r14, [rbp+pInputStream]
0x180061794  mov     ebx, eax
0x180061796  test    eax, eax
0x180061798  jns     short loc_180061811
0x18006179a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617a1  cmp     rcx, r12
0x1800617a4  jz      short loc_1800617C6
0x1800617a6  test    byte ptr [rcx+1Ch], 4
0x1800617aa  jz      short loc_1800617C6
0x1800617ac  cmp     byte ptr [rcx+19h], 2
0x1800617b0  jb      short loc_1800617C6
0x1800617b2  mov     rcx, [rcx+10h]
0x1800617b6  mov     edx, 1Fh
0x1800617bb  mov     r9d, eax
0x1800617be  mov     r8, r13
0x1800617c1  call    WPP_SF_d
0x1800617c6  mov     rcx, [rbp+28h]; this
0x1800617ca  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800617d1  mov     r9d, ebx; char *
0x1800617d4  mov     edx, 0BAh; void *
0x1800617d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800617de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617e5  cmp     rcx, r12
0x1800617e8  jz      loc_180061938
0x1800617ee  test    byte ptr [rcx+1Ch], 80h
0x1800617f2  jz      loc_180061938
0x1800617f8  mov     edx, 20h ; ' '
0x1800617fd  mov     rcx, [rcx+10h]
0x180061801  mov     r9d, ebx
0x180061804  mov     r8, r13
0x180061807  call    WPP_SF_d
0x18006180c  jmp     loc_180061931
0x180061811  lea     rax, [rbp+arg_18]
0x180061815  xor     r9d, r9d; fEncodingHint
0x180061818  mov     [rsp+40h+ppInput], rax; ppInput
0x18006181d  xor     edx, edx; pMalloc
0x18006181f  mov     r8d, 0FDE9h; nEncodingCodePage
0x180061825  mov     [rsp+40h+pwszBaseUri], rsi; int
0x18006182a  mov     rcx, r14; pInputStream
0x18006182d  call    cs:__imp_CreateXmlReaderInputWithEncodingCodePage
0x180061833  mov     ebx, eax
0x180061835  test    eax, eax
0x180061837  jns     short loc_1800618A1
0x180061839  mov     rcx, cs:WPP_GLOBAL_Control
0x180061840  cmp     rcx, r12
0x180061843  jz      short loc_180061865
0x180061845  test    byte ptr [rcx+1Ch], 4
0x180061849  jz      short loc_180061865
0x18006184b  cmp     byte ptr [rcx+19h], 2
0x18006184f  jb      short loc_180061865
0x180061851  mov     rcx, [rcx+10h]
0x180061855  mov     edx, 21h ; '!'
0x18006185a  mov     r9d, eax
0x18006185d  mov     r8, r13
0x180061860  call    WPP_SF_d
0x180061865  mov     rcx, [rbp+28h]; this
0x180061869  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180061870  mov     r9d, ebx; char *
0x180061873  mov     edx, 0C3h; void *
0x180061878  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006187d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061884  cmp     rcx, r12
0x180061887  jz      loc_180061938
0x18006188d  test    byte ptr [rcx+1Ch], 80h
0x180061891  jz      loc_180061938
0x180061897  mov     edx, 22h ; '"'
0x18006189c  jmp     loc_1800617FD
0x1800618a1  mov     rcx, [rbp+arg_18]; struct IUnknown *
0x1800618a5  lea     rdx, [rbp+arg_0]; struct IXmlReader **
0x1800618a9  call    ?CreateAndInitXmlReader@@YAJPEAUIUnknown@@PEAPEAUIXmlReader@@@Z; CreateAndInitXmlReader(IUnknown *,IXmlReader * *)
0x1800618ae  mov     ebx, eax
0x1800618b0  test    eax, eax
0x1800618b2  jns     short loc_18006192A
0x1800618b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618bb  cmp     rcx, r12
0x1800618be  jz      short loc_1800618E0
0x1800618c0  test    byte ptr [rcx+1Ch], 4
0x1800618c4  jz      short loc_1800618E0
0x1800618c6  cmp     byte ptr [rcx+19h], 2
0x1800618ca  jb      short loc_1800618E0
0x1800618cc  mov     rcx, [rcx+10h]
0x1800618d0  mov     edx, 23h ; '#'
0x1800618d5  mov     r9d, eax
0x1800618d8  mov     r8, r13
0x1800618db  call    WPP_SF_d
0x1800618e0  mov     rcx, [rbp+28h]; this
0x1800618e4  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800618eb  mov     r9d, ebx; char *
0x1800618ee  mov     edx, 0C7h; void *
0x1800618f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800618f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800618ff  cmp     rcx, r12
0x180061902  jz      short loc_180061924
0x180061904  test    byte ptr [rcx+1Ch], 80h
0x180061908  jz      short loc_180061924
0x18006190a  mov     rcx, [rcx+10h]
0x18006190e  mov     edx, 24h ; '$'
0x180061913  mov     r9d, ebx
0x180061916  mov     r8, r13
0x180061919  call    WPP_SF_d
0x18006191e  mov     rsi, [rbp+arg_0]
0x180061922  jmp     short loc_180061931
0x180061924  mov     rsi, [rbp+arg_0]
0x180061928  jmp     short loc_180061938
0x18006192a  mov     rax, [rbp+arg_0]
0x18006192e  mov     [rdi], rax
0x180061931  mov     rcx, cs:WPP_GLOBAL_Control
0x180061938  test    r14, r14
0x18006193b  jz      short loc_180061953
0x18006193d  mov     rax, [r14]
0x180061940  mov     rcx, r14
0x180061943  mov     rax, [rax+10h]
0x180061947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006194c  mov     rcx, cs:WPP_GLOBAL_Control
0x180061953  mov     rdx, [rbp+arg_18]
0x180061957  test    rdx, rdx
0x18006195a  jz      short loc_18006197A
0x18006195c  mov     rax, [rdx]
0x18006195f  mov     rcx, rdx
0x180061962  mov     rax, [rax+10h]
0x180061966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006196b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061972  mov     [rbp+arg_18], 0
0x18006197a  test    rsi, rsi
0x18006197d  jz      short loc_180061995
0x18006197f  mov     rax, [rsi]
0x180061982  mov     rcx, rsi
0x180061985  mov     rax, [rax+10h]
0x180061989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006198e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061995  cmp     rcx, r12
0x180061998  jz      short loc_1800619BA
0x18006199a  test    byte ptr [rcx+1Ch], 4
0x18006199e  jz      short loc_1800619BA
0x1800619a0  cmp     byte ptr [rcx+19h], 6
0x1800619a4  jb      short loc_1800619BA
0x1800619a6  mov     rcx, [rcx+10h]
0x1800619aa  mov     edx, 25h ; '%'
0x1800619af  mov     r9d, ebx
0x1800619b2  mov     r8, r13
0x1800619b5  call    WPP_SF_d
0x1800619ba  lea     r11, [rsp+40h+var_s0]
0x1800619bf  mov     eax, ebx
0x1800619c1  mov     rbx, [r11+38h]
0x1800619c5  mov     rsi, [r11+40h]
0x1800619c9  mov     rsp, r11
0x1800619cc  pop     r14
0x1800619ce  pop     r13
0x1800619d0  pop     r12
0x1800619d2  pop     rdi
0x1800619d3  pop     rbp
0x1800619d4  retn
```
