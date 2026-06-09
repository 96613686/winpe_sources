# InitializeQec

- ea: `0x180004970`
- end: `0x180004c94`
- name: `InitializeQec`
- size: `804`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001344`
- `0x180003c6c`
- `0x180003ef8`
- `0x1800043e0`
- `0x180004970`
- `0x1800054b8`
- `0x180005658`
- `0x180005e38`
- `0x18000c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004ad5`
- `ole32!CoCreateInstance` at `0x180004ad5`
- `ole32!CoInitializeEx` at `0x180004a6d`
- `ole32!CoInitializeEx` at `0x180004a6d`
- `ADVAPI32!RegisterTraceGuidsW` at `0x1800049f9`
- `ADVAPI32!RegisterTraceGuidsW` at `0x1800049f9`

## string_xrefs

- `0x180004b11`: `CoCreateInstance for CLSID_NapEnforcementClientBinding`

## pseudocode

```c
__int64 InitializeQec()
{
  ULONG64 *v0; // rbx
  const GUID **v1; // rdi
  const GUID *v2; // r8
  int started; // eax
  int Instance; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  const wchar_t *v7; // r9
  _DWORD *v8; // rdi
  LPVOID v9; // rbx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-38h] BYREF

  qword_1800137C8 = 1;
  qword_1800137C0 = 0;
  v0 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WPPDefaultComponentGuidName;
  v1 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  do
  {
    v2 = *v1;
    TraceGuidReg.Guid = v2;
    ++v1;
    TraceGuidReg.RegHandle = 0;
    v0[4] = (ULONG64)v2;
    RegisterTraceGuidsW(WppControlCallback, v0, v2, 1u, &TraceGuidReg, 0, 0, v0 + 1);
    v0 = (ULONG64 *)*v0;
  }
  while ( v0 );
  started = StartTsgQec();
  Instance = started;
  if ( started )
  {
    if ( started > 0 )
      Instance = (unsigned __int16)started | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        (unsigned int)L"StartTsgQec",
        Instance);
    }
    if ( Instance >= 0 )
      return (unsigned int)Instance;
LABEL_38:
    if ( g_pNECCallback )
    {
      (*(void (__fastcall **)(struct CAANapEnforcementClientCallback *))(*(_QWORD *)g_pNECCallback + 16LL))(g_pNECCallback);
      g_pNECCallback = 0;
    }
    if ( g_pNECBinding )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pNECBinding + 16LL))(g_pNECBinding);
      g_pNECBinding = 0;
    }
    return (unsigned int)Instance;
  }
  Instance = CoInitializeEx(0, 0);
  if ( Instance < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v6 = 11;
    v7 = L"CoInitializeEx";
LABEL_31:
    WPP_SF_Sd(v5[2], v6, (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, (_DWORD)v7, Instance);
LABEL_37:
    StopTsgQec();
    goto LABEL_38;
  }
  Instance = CoCreateInstance(
               &CLSID_NapEnforcementClientBinding,
               0,
               3u,
               &GUID_92b93223_7487_42d9_9a91_5b8507720384,
               &g_pNECBinding);
  if ( Instance < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v6 = 12;
    v7 = L"CoCreateInstance for CLSID_NapEnforcementClientBinding";
    goto LABEL_31;
  }
  v8 = operator new(0x38u);
  if ( !v8 )
  {
    g_pNECCallback = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        L"g_pNECCallback");
    }
    Instance = -2147024882;
    goto LABEL_37;
  }
  v9 = g_pNECBinding;
  *(_QWORD *)v8 = &CAANapEnforcementClientCallback::`vftable';
  v8[8] = 0;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 5) = 0;
  *((_QWORD *)v8 + 6) = 0;
  *((_QWORD *)v8 + 5) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>>::_Buyheadnode();
  v8[2] = 1;
  *((_QWORD *)v8 + 2) = v9;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 8LL))(v9);
  if ( !v8[8] )
  {
    v8[8] = 1;
    if ( (int)PAL_System_CritSecInit(v8 + 6) < 0 )
      v8[8] = 0;
  }
  g_pNECCallback = (struct CAANapEnforcementClientCallback *)v8;
  Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _DWORD *))(*(_QWORD *)g_pNECBinding + 24LL))(
               g_pNECBinding,
               79621,
               v8);
  if ( Instance < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v6 = 14;
    v7 = L"g_pNECBinding->Initialize";
    goto LABEL_31;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004970  push    rbx
0x180004972  push    rbp
0x180004973  push    rsi
0x180004974  push    rdi
0x180004975  sub     rsp, 58h
0x180004979  xor     ebp, ebp
0x18000497b  mov     cs:qword_1800137C8, 1
0x180004986  lea     rax, WPP_ThisDir_CTLGUID_WPPDefaultComponentGuidName
0x18000498d  mov     cs:qword_1800137C0, rbp
0x180004994  lea     rbx, WPP_MAIN_CB
0x18000499b  mov     cs:WPP_MAIN_CB, rbp
0x1800049a2  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1800049a9  lea     rdi, WPP_REGISTRATION_GUIDS
0x1800049b0  mov     cs:WPP_GLOBAL_Control, rbx
0x1800049b7  mov     r8, [rdi]; ControlGuid
0x1800049ba  lea     rax, [rbx+8]
0x1800049be  mov     [rsp+78h+RegistrationHandle], rax; RegistrationHandle
0x1800049c3  lea     rcx, WppControlCallback; RequestAddress
0x1800049ca  mov     [rsp+78h+MofResourceName], rbp; MofResourceName
0x1800049cf  lea     rax, [rsp+78h+var_38]
0x1800049d4  mov     [rsp+78h+var_38.Guid], r8
0x1800049d9  lea     rdi, [rdi+8]
0x1800049dd  mov     [rsp+78h+var_38.RegHandle], rbp
0x1800049e2  mov     r9d, 1; GuidCount
0x1800049e8  mov     [rsp+78h+MofImagePath], rbp; MofImagePath
0x1800049ed  mov     rdx, rbx; RequestContext
0x1800049f0  mov     [rsp+78h+TraceGuidReg], rax; TraceGuidReg
0x1800049f5  mov     [rbx+20h], r8
0x1800049f9  call    cs:__imp_RegisterTraceGuidsW
0x1800049ff  mov     rbx, [rbx]
0x180004a02  test    rbx, rbx
0x180004a05  jnz     short loc_1800049B7
0x180004a07  call    ?StartTsgQec@@YAKXZ; StartTsgQec(void)
0x180004a0c  mov     ebx, eax
0x180004a0e  test    eax, eax
0x180004a10  jz      short loc_180004A69
0x180004a12  jle     short loc_180004A1D
0x180004a14  movzx   ebx, ax
0x180004a17  or      ebx, 80070000h
0x180004a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a24  lea     rax, WPP_GLOBAL_Control
0x180004a2b  cmp     rcx, rax
0x180004a2e  jz      short loc_180004A5C
0x180004a30  test    byte ptr [rcx+1Ch], 8
0x180004a34  jz      short loc_180004A5C
0x180004a36  cmp     byte ptr [rcx+19h], 2
0x180004a3a  jb      short loc_180004A5C
0x180004a3c  mov     rcx, [rcx+10h]
0x180004a40  lea     r9, aStarttsgqec; "StartTsgQec"
0x180004a47  mov     edx, 0Ah
0x180004a4c  mov     dword ptr [rsp+78h+TraceGuidReg], ebx
0x180004a50  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004a57  call    WPP_SF_Sd
0x180004a5c  test    ebx, ebx
0x180004a5e  js      loc_180004C4B
0x180004a64  jmp     loc_180004C89
0x180004a69  xor     edx, edx; dwCoInit
0x180004a6b  xor     ecx, ecx; pvReserved
0x180004a6d  call    cs:__imp_CoInitializeEx
0x180004a73  mov     ebx, eax
0x180004a75  test    eax, eax
0x180004a77  jns     short loc_180004AB5
0x180004a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a80  lea     rax, WPP_GLOBAL_Control
0x180004a87  cmp     rcx, rax
0x180004a8a  jz      loc_180004C46
0x180004a90  test    byte ptr [rcx+1Ch], 8
0x180004a94  jz      loc_180004C46
0x180004a9a  cmp     byte ptr [rcx+19h], 2
0x180004a9e  jb      loc_180004C46
0x180004aa4  mov     edx, 0Bh
0x180004aa9  lea     r9, aCoinitializeex; "CoInitializeEx"
0x180004ab0  jmp     loc_180004BE9
0x180004ab5  xor     edx, edx; pUnkOuter
0x180004ab7  lea     rax, ?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004abe  lea     r9, _GUID_92b93223_7487_42d9_9a91_5b8507720384; riid
0x180004ac5  mov     [rsp+78h+TraceGuidReg], rax; ppv
0x180004aca  lea     rcx, CLSID_NapEnforcementClientBinding; rclsid
0x180004ad1  lea     r8d, [rdx+3]; dwClsContext
0x180004ad5  call    cs:__imp_CoCreateInstance
0x180004adb  mov     ebx, eax
0x180004add  test    eax, eax
0x180004adf  jns     short loc_180004B1D
0x180004ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ae8  lea     rax, WPP_GLOBAL_Control
0x180004aef  cmp     rcx, rax
0x180004af2  jz      loc_180004C46
0x180004af8  test    byte ptr [rcx+1Ch], 8
0x180004afc  jz      loc_180004C46
0x180004b02  cmp     byte ptr [rcx+19h], 2
0x180004b06  jb      loc_180004C46
0x180004b0c  mov     edx, 0Ch
0x180004b11  lea     r9, aCocreateinstan; "CoCreateInstance for CLSID_NapEnforceme"...
0x180004b18  jmp     loc_180004BE9
0x180004b1d  mov     ecx, 38h ; '8'; Size
0x180004b22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b27  mov     rdi, rax
0x180004b2a  test    rax, rax
0x180004b2d  jz      loc_180004BFF
0x180004b33  mov     rbx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004b3a  lea     rax, ??_7CAANapEnforcementClientCallback@@6B@; const CAANapEnforcementClientCallback::`vftable'
0x180004b41  mov     [rdi], rax
0x180004b44  mov     [rdi+20h], ebp
0x180004b47  mov     [rdi+18h], rbp
0x180004b4b  mov     [rdi+28h], rbp
0x180004b4f  mov     [rdi+30h], rbp
0x180004b53  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>>::_Buyheadnode(void)
0x180004b58  mov     [rdi+28h], rax
0x180004b5c  mov     rcx, rbx
0x180004b5f  mov     dword ptr [rdi+8], 1
0x180004b66  mov     [rdi+10h], rbx
0x180004b6a  mov     rax, [rbx]
0x180004b6d  mov     rax, [rax+8]
0x180004b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b76  cmp     [rdi+20h], ebp
0x180004b79  jnz     short loc_180004B92
0x180004b7b  lea     rcx, [rdi+18h]
0x180004b7f  mov     dword ptr [rdi+20h], 1
0x180004b86  call    PAL_System_CritSecInit
0x180004b8b  test    eax, eax
0x180004b8d  jns     short loc_180004B92
0x180004b8f  mov     [rdi+20h], ebp
0x180004b92  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004b99  mov     r8, rdi
0x180004b9c  mov     edx, 13705h
0x180004ba1  mov     cs:?g_pNECCallback@@3PEAVCAANapEnforcementClientCallback@@EA, rdi; CAANapEnforcementClientCallback * g_pNECCallback
0x180004ba8  mov     rax, [rcx]
0x180004bab  mov     rax, [rax+18h]
0x180004baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb4  mov     ebx, eax
0x180004bb6  test    eax, eax
0x180004bb8  jns     loc_180004C89
0x180004bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bc5  lea     rax, WPP_GLOBAL_Control
0x180004bcc  cmp     rcx, rax
0x180004bcf  jz      short loc_180004C46
0x180004bd1  test    byte ptr [rcx+1Ch], 8
0x180004bd5  jz      short loc_180004C46
0x180004bd7  cmp     byte ptr [rcx+19h], 2
0x180004bdb  jb      short loc_180004C46
0x180004bdd  mov     edx, 0Eh
0x180004be2  lea     r9, aGPnecbindingIn; "g_pNECBinding->Initialize"
0x180004be9  mov     rcx, [rcx+10h]
0x180004bed  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004bf4  mov     dword ptr [rsp+78h+TraceGuidReg], ebx
0x180004bf8  call    WPP_SF_Sd
0x180004bfd  jmp     short loc_180004C46
0x180004bff  mov     cs:?g_pNECCallback@@3PEAVCAANapEnforcementClientCallback@@EA, rbp; CAANapEnforcementClientCallback * g_pNECCallback
0x180004c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c0d  lea     rax, WPP_GLOBAL_Control
0x180004c14  cmp     rcx, rax
0x180004c17  jz      short loc_180004C41
0x180004c19  test    byte ptr [rcx+1Ch], 8
0x180004c1d  jz      short loc_180004C41
0x180004c1f  cmp     byte ptr [rcx+19h], 2
0x180004c23  jb      short loc_180004C41
0x180004c25  mov     rcx, [rcx+10h]
0x180004c29  lea     r9, aGPneccallback; "g_pNECCallback"
0x180004c30  mov     edx, 0Dh
0x180004c35  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004c3c  call    WPP_SF_S
0x180004c41  mov     ebx, 8007000Eh
0x180004c46  call    ?StopTsgQec@@YAKXZ; StopTsgQec(void)
0x180004c4b  mov     rcx, cs:?g_pNECCallback@@3PEAVCAANapEnforcementClientCallback@@EA; CAANapEnforcementClientCallback * g_pNECCallback
0x180004c52  test    rcx, rcx
0x180004c55  jz      short loc_180004C6A
0x180004c57  mov     rax, [rcx]
0x180004c5a  mov     rax, [rax+10h]
0x180004c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c63  mov     cs:?g_pNECCallback@@3PEAVCAANapEnforcementClientCallback@@EA, rbp; CAANapEnforcementClientCallback * g_pNECCallback
0x180004c6a  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004c71  test    rcx, rcx
0x180004c74  jz      short loc_180004C89
0x180004c76  mov     rax, [rcx]
0x180004c79  mov     rax, [rax+10h]
0x180004c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c82  mov     cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA, rbp; INapEnforcementClientBinding * g_pNECBinding
0x180004c89  mov     eax, ebx
0x180004c8b  add     rsp, 58h
0x180004c8f  pop     rdi
0x180004c90  pop     rsi
0x180004c91  pop     rbp
0x180004c92  pop     rbx
0x180004c93  retn
```
