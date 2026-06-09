# CWnpConnManager::Init(bool,CNetLayerEventSink *,LogCommandManager *)

- ea: `0x1800651b0`
- end: `0x180065463`
- name: `?Init@CWnpConnManager@@QEAAJ_NPEAVCNetLayerEventSink@@PEAVLogCommandManager@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(CWnpConnManager *this, char, struct CNetLayerEventSink *, struct LogCommandManager *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180060b10`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x180021524`
- `0x180039c24`
- `0x1800643d4`
- `0x1800651b0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065405`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065405`

## pseudocode

```c
__int64 __fastcall CWnpConnManager::Init(
        CWnpConnManager *this,
        char a2,
        struct CNetLayerEventSink *a3,
        struct LogCommandManager *a4)
{
  PVOID v8; // rcx
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  int NetworkLayers; // eax
  HRESULT Guid; // eax
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
  }
  if ( !a3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
    v9 = -2147418113;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          2147549183LL);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      {
        v11 = 16;
LABEL_47:
        WPP_SF_d(v10[2], v11, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v9);
        return v9;
      }
    }
    return v9;
  }
  *((_BYTE *)this + 212) = a2;
  *((_QWORD *)this + 29) = a3;
  Microsoft::WRL::ComPtr<LogCommandManager>::operator=((char *)this + 296, a4);
  if ( CMsgrWndBase::IsMsgrWindow((CWnpConnManager *)((char *)this + 16)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
    }
    v12 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, __int64))(*((_QWORD *)this + 2) + 8LL))(
            (char *)this + 16,
            L"WnpConnManager",
            -3);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          (unsigned int)v12);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)v9,
        v17);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_43;
      v13 = 19;
      goto LABEL_27;
    }
  }
  NetworkLayers = CWnpConnManager::CreateNetworkLayers(this);
  v9 = NetworkLayers;
  if ( NetworkLayers >= 0 )
  {
    Guid = CoCreateGuid((GUID *)((char *)this + 276));
    if ( Guid < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)(unsigned int)Guid,
        v17);
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
      (unsigned int)NetworkLayers);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x68,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
    (const char *)v9,
    v17);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    goto LABEL_43;
  v13 = 22;
LABEL_27:
  WPP_SF_d(v10[2], v13, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v9);
LABEL_42:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 6u )
  {
    v11 = 23;
    goto LABEL_47;
  }
  return v9;
}

```

## disassembly

```asm
0x1800651b0  push    rbx
0x1800651b2  push    rbp
0x1800651b3  push    rsi
0x1800651b4  push    rdi
0x1800651b5  push    r14
0x1800651b7  push    r15
0x1800651b9  sub     rsp, 28h
0x1800651bd  mov     rsi, r9
0x1800651c0  mov     rbx, r8
0x1800651c3  mov     bpl, dl
0x1800651c6  mov     rdi, rcx
0x1800651c9  lea     r14, WPP_GLOBAL_Control
0x1800651d0  lea     r15, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800651d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800651de  cmp     rcx, r14
0x1800651e1  jz      short loc_180065200
0x1800651e3  test    byte ptr [rcx+1Ch], 4
0x1800651e7  jz      short loc_180065200
0x1800651e9  cmp     byte ptr [rcx+19h], 6
0x1800651ed  jb      short loc_180065200
0x1800651ef  mov     edx, 0Eh
0x1800651f4  mov     r8, r15
0x1800651f7  mov     rcx, [rcx+10h]
0x1800651fb  call    WPP_SF_
0x180065200  test    rbx, rbx
0x180065203  jnz     short loc_18006526D
0x180065205  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006520a  mov     ebx, 8000FFFFh
0x18006520f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065216  cmp     rcx, r14
0x180065219  jz      loc_180065454
0x18006521f  test    byte ptr [rcx+1Ch], 4
0x180065223  jz      short loc_180065246
0x180065225  cmp     byte ptr [rcx+19h], 2
0x180065229  jb      short loc_180065246
0x18006522b  mov     edx, 0Fh
0x180065230  mov     r9d, ebx
0x180065233  mov     r8, r15
0x180065236  mov     rcx, [rcx+10h]
0x18006523a  call    WPP_SF_d
0x18006523f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065246  cmp     rcx, r14
0x180065249  jz      loc_180065454
0x18006524f  test    byte ptr [rcx+1Ch], 4
0x180065253  jz      loc_180065454
0x180065259  cmp     byte ptr [rcx+19h], 6
0x18006525d  jb      loc_180065454
0x180065263  mov     edx, 10h
0x180065268  jmp     loc_180065445
0x18006526d  mov     [rdi+0D4h], bpl
0x180065274  mov     [rdi+0E8h], rbx
0x18006527b  lea     rcx, [rdi+128h]
0x180065282  mov     rdx, rsi
0x180065285  call    ??4?$ComPtr@VLogCommandManager@@@WRL@Microsoft@@QEAAAEAV012@PEAVLogCommandManager@@@Z; Microsoft::WRL::ComPtr<LogCommandManager>::operator=(LogCommandManager *)
0x18006528a  lea     rbx, [rdi+10h]
0x18006528e  mov     rcx, rbx; this
0x180065291  call    ?IsMsgrWindow@CMsgrWndBase@@IEAA_NXZ; CMsgrWndBase::IsMsgrWindow(void)
0x180065296  test    al, al
0x180065298  jnz     loc_180065366
0x18006529e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652a5  cmp     rcx, r14
0x1800652a8  jz      short loc_1800652C7
0x1800652aa  test    byte ptr [rcx+1Ch], 4
0x1800652ae  jz      short loc_1800652C7
0x1800652b0  cmp     byte ptr [rcx+19h], 5
0x1800652b4  jb      short loc_1800652C7
0x1800652b6  mov     edx, 11h
0x1800652bb  mov     r8, r15
0x1800652be  mov     rcx, [rcx+10h]
0x1800652c2  call    WPP_SF_
0x1800652c7  mov     rax, [rbx]
0x1800652ca  mov     r8, 0FFFFFFFFFFFFFFFDh
0x1800652d1  lea     rdx, ?g_ConnManagerWindowName@@3QBGB; "WnpConnManager"
0x1800652d8  mov     rcx, rbx
0x1800652db  mov     rax, [rax+8]
0x1800652df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652e4  mov     ebx, eax
0x1800652e6  test    eax, eax
0x1800652e8  jns     loc_18006538F
0x1800652ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652f5  cmp     rcx, r14
0x1800652f8  jz      short loc_18006531A
0x1800652fa  test    byte ptr [rcx+1Ch], 4
0x1800652fe  jz      short loc_18006531A
0x180065300  cmp     byte ptr [rcx+19h], 2
0x180065304  jb      short loc_18006531A
0x180065306  mov     edx, 12h
0x18006530b  mov     r9d, eax
0x18006530e  mov     r8, r15
0x180065311  mov     rcx, [rcx+10h]
0x180065315  call    WPP_SF_d
0x18006531a  mov     rcx, [rsp+58h]; this
0x18006531f  mov     r9d, ebx; char *
0x180065322  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180065329  mov     edx, 5Fh ; '_'; void *
0x18006532e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065333  mov     rcx, cs:WPP_GLOBAL_Control
0x18006533a  cmp     rcx, r14
0x18006533d  jz      loc_180065454
0x180065343  test    byte ptr [rcx+1Ch], 80h
0x180065347  jz      loc_18006542F
0x18006534d  mov     edx, 13h
0x180065352  mov     r9d, ebx
0x180065355  mov     r8, r15
0x180065358  mov     rcx, [rcx+10h]
0x18006535c  call    WPP_SF_d
0x180065361  jmp     loc_180065428
0x180065366  mov     rcx, cs:WPP_GLOBAL_Control
0x18006536d  cmp     rcx, r14
0x180065370  jz      short loc_18006538F
0x180065372  test    byte ptr [rcx+1Ch], 4
0x180065376  jz      short loc_18006538F
0x180065378  cmp     byte ptr [rcx+19h], 5
0x18006537c  jb      short loc_18006538F
0x18006537e  mov     edx, 14h
0x180065383  mov     r8, r15
0x180065386  mov     rcx, [rcx+10h]
0x18006538a  call    WPP_SF_
0x18006538f  mov     rcx, rdi; this
0x180065392  call    ?CreateNetworkLayers@CWnpConnManager@@AEAAJXZ; CWnpConnManager::CreateNetworkLayers(void)
0x180065397  mov     ebx, eax
0x180065399  test    eax, eax
0x18006539b  jns     short loc_1800653FE
0x18006539d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800653a4  cmp     rcx, r14
0x1800653a7  jz      short loc_1800653C9
0x1800653a9  test    byte ptr [rcx+1Ch], 4
0x1800653ad  jz      short loc_1800653C9
0x1800653af  cmp     byte ptr [rcx+19h], 2
0x1800653b3  jb      short loc_1800653C9
0x1800653b5  mov     edx, 15h
0x1800653ba  mov     r9d, eax
0x1800653bd  mov     r8, r15
0x1800653c0  mov     rcx, [rcx+10h]
0x1800653c4  call    WPP_SF_d
0x1800653c9  mov     rcx, [rsp+58h]; this
0x1800653ce  mov     r9d, ebx; char *
0x1800653d1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800653d8  mov     edx, 68h ; 'h'; void *
0x1800653dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800653e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800653e9  cmp     rcx, r14
0x1800653ec  jz      short loc_180065454
0x1800653ee  test    byte ptr [rcx+1Ch], 80h
0x1800653f2  jz      short loc_18006542F
0x1800653f4  mov     edx, 16h
0x1800653f9  jmp     loc_180065352
0x1800653fe  lea     rcx, [rdi+114h]; pguid
0x180065405  call    cs:__imp_CoCreateGuid
0x18006540b  test    eax, eax
0x18006540d  jns     short loc_180065428
0x18006540f  mov     rcx, [rsp+58h]; this
0x180065414  mov     r9d, eax; char *
0x180065417  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006541e  mov     edx, 6Ah ; 'j'; void *
0x180065423  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065428  mov     rcx, cs:WPP_GLOBAL_Control
0x18006542f  cmp     rcx, r14
0x180065432  jz      short loc_180065454
0x180065434  test    byte ptr [rcx+1Ch], 4
0x180065438  jz      short loc_180065454
0x18006543a  cmp     byte ptr [rcx+19h], 6
0x18006543e  jb      short loc_180065454
0x180065440  mov     edx, 17h
0x180065445  mov     r9d, ebx
0x180065448  mov     r8, r15
0x18006544b  mov     rcx, [rcx+10h]
0x18006544f  call    WPP_SF_d
0x180065454  mov     eax, ebx
0x180065456  add     rsp, 28h
0x18006545a  pop     r15
0x18006545c  pop     r14
0x18006545e  pop     rdi
0x18006545f  pop     rsi
0x180065460  pop     rbp
0x180065461  pop     rbx
0x180065462  retn
```
