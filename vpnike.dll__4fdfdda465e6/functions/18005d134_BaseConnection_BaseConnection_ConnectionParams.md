# BaseConnection::BaseConnection(ConnectionParams *)

- ea: `0x18005d134`
- end: `0x18005d7eb`
- name: `??0BaseConnection@@QEAA@PEAVConnectionParams@@@Z`
- size: `1719`
- prototype: `BaseConnection *__fastcall(BaseConnection *__hidden this, struct ConnectionParams *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18000c28c`

## callees

- `0x180001f78`
- `0x180007794`
- `0x1800077bc`
- `0x18000a3a0`
- `0x18005d134`
- `0x18005d958`
- `0x18005dfcc`
- `0x180067084`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6d5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d4b6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d6cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d4b6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005d6cb`

## string_xrefs

- `0x18005d3a4`: `Configured IdleTimeOut:%u, approx. value used:%u`
- `0x18005d5bd`: `Configured IdleTimeOut:%u, approx. value used:%u`

## pseudocode

```c
BaseConnection *__fastcall BaseConnection::BaseConnection(BaseConnection *this, struct ConnectionParams *a2)
{
  PVOID *v4; // rdi
  PVOID *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  unsigned int *v9; // r14
  unsigned int *v10; // rdi
  unsigned int v11; // ecx
  int v12; // eax
  __int64 v13; // rcx
  char v14; // r10
  int v15; // edx
  __int128 v16; // xmm0
  unsigned int *v17; // rdi
  unsigned int v18; // ecx
  int v19; // eax
  __int64 v20; // rcx
  char v21; // r10
  int v22; // edx
  __int128 v23; // xmm0
  unsigned int *v24; // rsi
  DWORD LastError; // eax
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  ulong pExceptionObject; // [rsp+34h] [rbp-CCh] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+58h] [rbp-A8h]
  __int128 v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+84h] [rbp-7Ch]
  int v36; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  *(_QWORD *)this = &BaseConnection::`vftable';
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v27 = 0;
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v34 = -1;
  v35 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"BaseConnection::BaseConnection",
      &v27,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
    WPP_SF_(v4[2], 16, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      v27 = 87;
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_16;
      }
      v6 = 17;
LABEL_15:
      WPP_SF_(v5[2], v6, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
      v7 = xmmword_1800AABC0;
      if ( !(_QWORD)xmmword_1800AABC0 )
        goto LABEL_67;
      v8 = L"ERROR_INVALID_PARAMETER";
      goto LABEL_18;
    }
    *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
    *((_QWORD *)this + 3) = *((_QWORD *)a2 + 2);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 12) = 0;
    *(_OWORD *)((char *)this + 52) = 0;
    *((_DWORD *)this + 17) = 0;
    *(_OWORD *)((char *)this + 72) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
    v9 = (unsigned int *)((char *)this + 104);
    *((_DWORD *)this + 26) = 1500;
    v10 = (unsigned int *)((char *)this + 108);
    *((_DWORD *)this + 27) = 0;
    *((_QWORD *)this + 14) = a2;
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_DWORD *)this + 36) = 0;
    *((_BYTE *)this + 148) = 0;
    *((_QWORD *)this + 19) = 0;
    v11 = *((_DWORD *)a2 + 89);
    *((_DWORD *)this + 24) = v11;
    if ( v11 )
    {
      v12 = 60;
      if ( v11 >= 0x3C )
        v12 = v11;
      else
        *((_DWORD *)this + 24) = 60;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids,
          *((unsigned int *)a2 + 89),
          v12);
      }
      if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
      {
        LOWORD(v36) = 0;
        FormatRRASErrorString(
          &v36,
          L"Configured IdleTimeOut:%u, approx. value used:%u",
          *(unsigned int *)(*((_QWORD *)this + 14) + 356LL),
          *((unsigned int *)this + 24));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
          gBaseEtwContext,
          *((_QWORD *)&xmmword_1800AABC0 + 1),
          &v36);
      }
    }
    v13 = *((_QWORD *)this + 14);
    v14 = *(_BYTE *)(v13 + 4284);
    *((_BYTE *)this + 16) = v14;
    v15 = *(_DWORD *)(v13 + 4288);
    *((_DWORD *)this + 12) = v15;
    *((_DWORD *)this + 17) = *(_DWORD *)(v13 + 4292);
    v16 = *(_OWORD *)(v13 + 4296);
    *(_OWORD *)((char *)this + 52) = v16;
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)(v13 + 4312);
    *v10 = *(_DWORD *)(v13 + 4352);
    v29 = v16;
    LOBYTE(v13) = v14;
    GetInterfaceParamsFromIPAddress(v13, v15, (unsigned int)&v29, (_DWORD)this + 108, (__int64)this + 104);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids, *v10, *v9);
    }
    if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    {
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v36, L"InterfaceIndex:%u, MTU:%u", *v10, *v9);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        *((_QWORD *)&xmmword_1800AABC0 + 1),
        &v36);
    }
    InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 4, 0xFA0u);
LABEL_65:
    *((_DWORD *)this + 51) = 1;
    goto LABEL_66;
  }
  *((_QWORD *)this + 14) = a2;
  if ( !a2 )
  {
    v27 = 87;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_16;
    }
    v6 = 20;
    goto LABEL_15;
  }
  *((_QWORD *)this + 1) = *((_QWORD *)a2 + 1);
  *((_QWORD *)this + 3) = *((_QWORD *)a2 + 2);
  *((_BYTE *)this + 148) = 0;
  v17 = (unsigned int *)((char *)this + 104);
  *((_DWORD *)this + 26) = 1500;
  *((_BYTE *)this + 200) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 25) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v18 = *((_DWORD *)a2 + 89);
  *((_DWORD *)this + 24) = v18;
  if ( v18 )
  {
    v19 = 60;
    if ( v18 >= 0x3C )
      v19 = v18;
    else
      *((_DWORD *)this + 24) = 60;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids,
        *((unsigned int *)a2 + 89),
        v19);
    }
    if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    {
      LOWORD(v36) = 0;
      FormatRRASErrorString(
        &v36,
        L"Configured IdleTimeOut:%u, approx. value used:%u",
        *(unsigned int *)(*((_QWORD *)this + 14) + 356LL),
        *((unsigned int *)this + 24));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        *((_QWORD *)&xmmword_1800AABC0 + 1),
        &v36);
    }
  }
  v20 = *((_QWORD *)this + 14);
  v21 = *(_BYTE *)(v20 + 4284);
  *((_BYTE *)this + 16) = v21;
  v22 = *(_DWORD *)(v20 + 4288);
  *((_DWORD *)this + 12) = v22;
  *((_DWORD *)this + 17) = *(_DWORD *)(v20 + 4292);
  v23 = *(_OWORD *)(v20 + 4296);
  *(_OWORD *)((char *)this + 52) = v23;
  *(_OWORD *)((char *)this + 72) = *(_OWORD *)(v20 + 4312);
  v24 = (unsigned int *)((char *)this + 108);
  *((_DWORD *)this + 27) = *(_DWORD *)(v20 + 4352);
  v29 = v23;
  LOBYTE(v20) = v21;
  GetInterfaceParamsFromIPAddress(v20, v22, (unsigned int)&v29, (_DWORD)this + 108, (__int64)this + 104);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids, *v24, *v17);
  }
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v36, L"InterfaceIndex:%u, MTU:%u", *v24, *v17);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v36);
  }
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 4, 0xFA0u) )
  {
    *((_BYTE *)this + 200) = 1;
    goto LABEL_65;
  }
  LastError = GetLastError();
  v27 = LastError;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids, LastError);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800AABC0 )
  {
    LOWORD(v36) = 0;
    FormatRRASErrorString(&v36, L"InitializeCriticalSectionAndSpinCount failed = %x", v27);
    v8 = (const wchar_t *)&v36;
    v7 = xmmword_1800AABC0;
LABEL_18:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gBaseTemplateFunc)(
      gBaseEtwContext,
      v7,
      v8);
LABEL_66:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_67:
  if ( v27 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::GetImpl'::`2'::impl) )
      BaseConnection::Cleanup(this);
    pExceptionObject = v27;
    throw &pExceptionObject;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
    WPP_SF_(v5[2], 24, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return this;
}

```

## disassembly

```asm
0x18005d134  mov     [rsp-8+arg_8], rbx
0x18005d139  mov     [rsp-8+arg_10], rsi
0x18005d13e  push    rbp
0x18005d13f  push    rdi
0x18005d140  push    r13
0x18005d142  push    r14
0x18005d144  push    r15
0x18005d146  lea     rbp, [rsp-7A0h]
0x18005d14e  sub     rsp, 8A0h
0x18005d155  mov     rax, cs:__security_cookie
0x18005d15c  xor     rax, rsp
0x18005d15f  mov     [rbp+7C0h+var_30], rax
0x18005d166  mov     rsi, rdx
0x18005d169  mov     rbx, rcx
0x18005d16c  lea     rax, ??_7BaseConnection@@6B@; const BaseConnection::`vftable'
0x18005d173  mov     [rcx], rax
0x18005d176  lea     r14, WPP_GLOBAL_Control
0x18005d17d  lea     r13, WPP_123f18666a7d3e7863aedd9beb21868e_Traceguids
0x18005d184  mov     rdi, cs:WPP_GLOBAL_Control
0x18005d18b  cmp     rdi, r14
0x18005d18e  jz      short loc_18005D1AE
0x18005d190  test    byte ptr [rdi+1Ch], 4
0x18005d194  jz      short loc_18005D1AE
0x18005d196  mov     edx, 0Fh
0x18005d19b  mov     r8, r13
0x18005d19e  mov     rcx, [rdi+10h]
0x18005d1a2  call    WPP_SF_
0x18005d1a7  mov     rdi, cs:WPP_GLOBAL_Control
0x18005d1ae  xor     r15d, r15d
0x18005d1b1  mov     [rsp+8C0h+var_890], r15d
0x18005d1b6  mov     [rbp+7C0h+var_830], r15d
0x18005d1ba  xor     edx, edx; Val
0x18005d1bc  mov     r8d, 7FCh; Size
0x18005d1c2  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18005d1c6  call    memset_0
0x18005d1cb  xorps   xmm0, xmm0
0x18005d1ce  movdqu  [rsp+8C0h+var_868], xmm0
0x18005d1d4  mov     [rsp+8C0h+var_870], r15
0x18005d1d9  xorps   xmm1, xmm1
0x18005d1dc  movdqu  [rsp+8C0h+var_858], xmm1
0x18005d1e2  mov     [rsp+8C0h+var_848], r15
0x18005d1e7  mov     [rbp+7C0h+var_840], 0FFFFFFFFh
0x18005d1ee  mov     [rbp+7C0h+var_83C], r15d
0x18005d1f2  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005d1f9  jz      short loc_18005D21F
0x18005d1fb  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005d202  lea     r8, [rsp+8C0h+var_890]; unsigned int *
0x18005d207  lea     rdx, aBaseconnection_1; "BaseConnection::BaseConnection"
0x18005d20e  lea     rcx, [rsp+8C0h+var_870]; this
0x18005d213  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005d218  mov     rdi, cs:WPP_GLOBAL_Control
0x18005d21f  cmp     rdi, r14
0x18005d222  jz      short loc_18005D23B
0x18005d224  test    byte ptr [rdi+1Ch], 4
0x18005d228  jz      short loc_18005D23B
0x18005d22a  mov     edx, 10h
0x18005d22f  mov     r8, r13
0x18005d232  mov     rcx, [rdi+10h]
0x18005d236  call    WPP_SF_
0x18005d23b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::GetImpl(void)'::`2'::impl
0x18005d242  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_RemoveIPv4Settings_Crash>::__private_IsEnabled(void)
0x18005d247  test    al, al
0x18005d249  jz      loc_18005D4C8
0x18005d24f  test    rsi, rsi
0x18005d252  jnz     short loc_18005D2B9
0x18005d254  mov     [rsp+8C0h+var_890], 57h ; 'W'
0x18005d25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d263  cmp     rcx, r14
0x18005d266  jz      short loc_18005D28A
0x18005d268  test    byte ptr [rcx+1Ch], 4
0x18005d26c  jz      short loc_18005D28A
0x18005d26e  cmp     byte ptr [rcx+19h], 1
0x18005d272  jb      short loc_18005D28A
0x18005d274  lea     edx, [rsi+11h]
0x18005d277  mov     r8, r13
0x18005d27a  mov     rcx, [rcx+10h]
0x18005d27e  call    WPP_SF_
0x18005d283  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d28a  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005d291  test    rdx, rdx
0x18005d294  jz      loc_18005D75D
0x18005d29a  lea     r8, aErrorInvalidPa; "ERROR_INVALID_PARAMETER"
0x18005d2a1  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005d2a8  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2b4  jmp     loc_18005D756
0x18005d2b9  mov     rax, [rsi+8]
0x18005d2bd  mov     [rbx+8], rax
0x18005d2c1  mov     rax, [rsi+10h]
0x18005d2c5  mov     [rbx+18h], rax
0x18005d2c9  mov     [rbx+20h], r15
0x18005d2cd  mov     [rbx+28h], r15
0x18005d2d1  mov     [rbx+30h], r15d
0x18005d2d5  xorps   xmm0, xmm0
0x18005d2d8  movdqu  xmmword ptr [rbx+34h], xmm0
0x18005d2dd  mov     [rbx+44h], r15d
0x18005d2e1  movdqu  xmmword ptr [rbx+48h], xmm0
0x18005d2e6  mov     [rbx+58h], r15
0x18005d2ea  mov     [rbx+60h], r15
0x18005d2ee  lea     r14, [rbx+68h]
0x18005d2f2  mov     dword ptr [r14], 5DCh
0x18005d2f9  lea     rdi, [rbx+6Ch]
0x18005d2fd  mov     [rdi], r15d
0x18005d300  mov     [rbx+70h], rsi
0x18005d304  mov     [rbx+78h], r15
0x18005d308  mov     [rbx+80h], r15
0x18005d30f  mov     [rbx+88h], r15
0x18005d316  mov     [rbx+90h], r15d
0x18005d31d  mov     [rbx+94h], r15b
0x18005d324  mov     [rbx+98h], r15
0x18005d32b  mov     ecx, [rsi+164h]
0x18005d331  mov     [rbx+60h], ecx
0x18005d334  test    ecx, ecx
0x18005d336  jz      loc_18005D3D2
0x18005d33c  mov     eax, 3Ch ; '<'
0x18005d341  cmp     ecx, eax
0x18005d343  jnb     short loc_18005D34A
0x18005d345  mov     [rbx+60h], eax
0x18005d348  jmp     short loc_18005D34C
0x18005d34a  mov     eax, ecx
0x18005d34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d353  lea     rdx, WPP_GLOBAL_Control
0x18005d35a  cmp     rcx, rdx
0x18005d35d  jz      short loc_18005D387
0x18005d35f  test    byte ptr [rcx+1Ch], 4
0x18005d363  jz      short loc_18005D387
0x18005d365  cmp     byte ptr [rcx+19h], 3
0x18005d369  jb      short loc_18005D387
0x18005d36b  mov     edx, 12h
0x18005d370  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18005d374  mov     r9d, [rsi+164h]
0x18005d37b  mov     r8, r13
0x18005d37e  mov     rcx, [rcx+10h]
0x18005d382  call    WPP_SF_dd
0x18005d387  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005d38e  jz      short loc_18005D3D2
0x18005d390  mov     word ptr [rbp+7C0h+var_830], r15w
0x18005d395  mov     r8, [rbx+70h]
0x18005d399  mov     r9d, [rbx+60h]
0x18005d39d  mov     r8d, [r8+164h]
0x18005d3a4  lea     rdx, aConfiguredIdle; "Configured IdleTimeOut:%u, approx. valu"...
0x18005d3ab  lea     rcx, [rbp+7C0h+var_830]
0x18005d3af  call    FormatRRASErrorString
0x18005d3b4  lea     r8, [rbp+7C0h+var_830]
0x18005d3b8  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005d3bf  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005d3c6  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3d2  mov     rcx, [rbx+70h]
0x18005d3d6  mov     r10b, [rcx+10BCh]
0x18005d3dd  mov     [rbx+10h], r10b
0x18005d3e1  mov     edx, [rcx+10C0h]
0x18005d3e7  mov     [rbx+30h], edx
0x18005d3ea  mov     eax, [rcx+10C4h]
0x18005d3f0  mov     [rbx+44h], eax
0x18005d3f3  movups  xmm0, xmmword ptr [rcx+10C8h]
0x18005d3fa  movdqu  xmmword ptr [rbx+34h], xmm0
0x18005d3ff  movups  xmm1, xmmword ptr [rcx+10D8h]
0x18005d406  movdqu  xmmword ptr [rbx+48h], xmm1
0x18005d40b  mov     eax, [rcx+1100h]
0x18005d411  mov     [rdi], eax
0x18005d413  movdqu  [rsp+8C0h+var_880], xmm0
0x18005d419  mov     [rsp+8C0h+var_8A0], r14
0x18005d41e  mov     r9, rdi
0x18005d421  lea     r8, [rsp+8C0h+var_880]
0x18005d426  mov     cl, r10b
0x18005d429  call    GetInterfaceParamsFromIPAddress
0x18005d42e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d435  lea     rax, WPP_GLOBAL_Control
0x18005d43c  cmp     rcx, rax
0x18005d43f  jz      short loc_18005D468
0x18005d441  test    byte ptr [rcx+1Ch], 4
0x18005d445  jz      short loc_18005D468
0x18005d447  cmp     byte ptr [rcx+19h], 3
0x18005d44b  jb      short loc_18005D468
0x18005d44d  mov     edx, 13h
0x18005d452  mov     eax, [r14]
0x18005d455  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18005d459  mov     r9d, [rdi]
0x18005d45c  mov     r8, r13
0x18005d45f  mov     rcx, [rcx+10h]
0x18005d463  call    WPP_SF_dd
0x18005d468  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005d46f  jz      short loc_18005D4AA
0x18005d471  mov     word ptr [rbp+7C0h+var_830], r15w
0x18005d476  mov     r9d, [r14]
0x18005d479  mov     r8d, [rdi]
0x18005d47c  lea     rdx, aInterfaceindex_0; "InterfaceIndex:%u, MTU:%u"
0x18005d483  lea     rcx, [rbp+7C0h+var_830]
0x18005d487  call    FormatRRASErrorString
0x18005d48c  lea     r8, [rbp+7C0h+var_830]
0x18005d490  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005d497  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005d49e  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4aa  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x18005d4b1  mov     edx, 0FA0h; dwSpinCount
0x18005d4b6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005d4bc  lea     r14, WPP_GLOBAL_Control
0x18005d4c3  jmp     loc_18005D74C
0x18005d4c8  mov     [rbx+70h], rsi
0x18005d4cc  test    rsi, rsi
0x18005d4cf  jnz     short loc_18005D505
0x18005d4d1  mov     [rsp+8C0h+var_890], 57h ; 'W'
0x18005d4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4e0  cmp     rcx, r14
0x18005d4e3  jz      loc_18005D28A
0x18005d4e9  test    byte ptr [rcx+1Ch], 4
0x18005d4ed  jz      loc_18005D28A
0x18005d4f3  cmp     byte ptr [rcx+19h], 1
0x18005d4f7  jb      loc_18005D28A
0x18005d4fd  lea     edx, [rsi+14h]
0x18005d500  jmp     loc_18005D277
0x18005d505  mov     rax, [rsi+8]
0x18005d509  mov     [rbx+8], rax
0x18005d50d  mov     rax, [rsi+10h]
0x18005d511  mov     [rbx+18h], rax
0x18005d515  mov     [rbx+94h], r15b
0x18005d51c  lea     rdi, [rbx+68h]
0x18005d520  mov     dword ptr [rdi], 5DCh
0x18005d526  mov     [rbx+0C8h], r15b
0x18005d52d  mov     [rbx+98h], r15
0x18005d534  mov     [rbx+64h], r15d
0x18005d538  mov     [rbx+20h], r15
0x18005d53c  mov     [rbx+28h], r15
0x18005d540  mov     [rbx+78h], r15
0x18005d544  mov     [rbx+80h], r15
0x18005d54b  mov     ecx, [rsi+164h]
0x18005d551  mov     [rbx+60h], ecx
0x18005d554  test    ecx, ecx
0x18005d556  jz      loc_18005D5EB
0x18005d55c  mov     eax, 3Ch ; '<'
0x18005d561  cmp     ecx, eax
0x18005d563  jnb     short loc_18005D56A
0x18005d565  mov     [rbx+60h], eax
0x18005d568  jmp     short loc_18005D56C
0x18005d56a  mov     eax, ecx
0x18005d56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d573  cmp     rcx, r14
0x18005d576  jz      short loc_18005D5A0
0x18005d578  test    byte ptr [rcx+1Ch], 4
0x18005d57c  jz      short loc_18005D5A0
0x18005d57e  cmp     byte ptr [rcx+19h], 3
0x18005d582  jb      short loc_18005D5A0
0x18005d584  mov     edx, 15h
0x18005d589  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18005d58d  mov     r9d, [rsi+164h]
0x18005d594  mov     r8, r13
0x18005d597  mov     rcx, [rcx+10h]
0x18005d59b  call    WPP_SF_dd
0x18005d5a0  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005d5a7  jz      short loc_18005D5EB
0x18005d5a9  mov     word ptr [rbp+7C0h+var_830], r15w
0x18005d5ae  mov     r8, [rbx+70h]
0x18005d5b2  mov     r9d, [rbx+60h]
0x18005d5b6  mov     r8d, [r8+164h]
0x18005d5bd  lea     rdx, aConfiguredIdle; "Configured IdleTimeOut:%u, approx. valu"...
0x18005d5c4  lea     rcx, [rbp+7C0h+var_830]
0x18005d5c8  call    FormatRRASErrorString
0x18005d5cd  lea     r8, [rbp+7C0h+var_830]
0x18005d5d1  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x18005d5d8  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005d5df  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5eb  mov     rcx, [rbx+70h]
0x18005d5ef  mov     r10b, [rcx+10BCh]
0x18005d5f6  mov     [rbx+10h], r10b
0x18005d5fa  mov     edx, [rcx+10C0h]
0x18005d600  mov     [rbx+30h], edx
0x18005d603  mov     eax, [rcx+10C4h]
0x18005d609  mov     [rbx+44h], eax
0x18005d60c  movups  xmm0, xmmword ptr [rcx+10C8h]
0x18005d613  movdqu  xmmword ptr [rbx+34h], xmm0
0x18005d618  movups  xmm1, xmmword ptr [rcx+10D8h]
0x18005d61f  movdqu  xmmword ptr [rbx+48h], xmm1
0x18005d624  lea     rsi, [rbx+6Ch]
0x18005d628  mov     eax, [rcx+1100h]
0x18005d62e  mov     [rsi], eax
0x18005d630  movdqu  [rsp+8C0h+var_880], xmm0
0x18005d636  mov     [rsp+8C0h+var_8A0], rdi
0x18005d63b  mov     r9, rsi
0x18005d63e  lea     r8, [rsp+8C0h+var_880]
0x18005d643  mov     cl, r10b
0x18005d646  call    GetInterfaceParamsFromIPAddress
0x18005d64b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d652  cmp     rcx, r14
0x18005d655  jz      short loc_18005D67D
0x18005d657  test    byte ptr [rcx+1Ch], 4
0x18005d65b  jz      short loc_18005D67D
0x18005d65d  cmp     byte ptr [rcx+19h], 3
0x18005d661  jb      short loc_18005D67D
0x18005d663  mov     edx, 16h
0x18005d668  mov     eax, [rdi]
0x18005d66a  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18005d66e  mov     r9d, [rsi]
0x18005d671  mov     r8, r13
0x18005d674  mov     rcx, [rcx+10h]
0x18005d678  call    WPP_SF_dd
0x18005d67d  cmp     qword ptr cs:xmmword_1800AABC0+8, r15
0x18005d684  jz      short loc_18005D6BF
  ... truncated ...
```
