# WnpKaDetectorImpl::SetupNetworkMonitor(void)

- ea: `0x18008f108`
- end: `0x18008f496`
- name: `?SetupNetworkMonitor@WnpKaDetectorImpl@@AEAAJXZ`
- size: `910`
- prototype: `__int64 __fastcall(WnpKaDetectorImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008f8d0`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18008f108`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008f1b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008f1b4`

## pseudocode

```c
__int64 __fastcall WnpKaDetectorImpl::SetupNetworkMonitor(WnpKaDetectorImpl *this)
{
  PVOID v2; // rcx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  int v12; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF
  __int64 v14; // [rsp+80h] [rbp+50h] BYREF
  __int64 v15; // [rsp+88h] [rbp+58h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids);
  }
  if ( *((_QWORD *)this + 19) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  if ( *((_DWORD *)this + 40) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  ppv = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  v3 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
           ppv,
           &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
           &v14);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v14 + 32LL))(
             v14,
             &GUID_dcb00007_570f_4a9b_8d69_199fdba5723b,
             &v15);
      v4 = v8;
      if ( v8 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, int *))(*(_QWORD *)v15 + 40LL))(
               v15,
               ((unsigned __int64)this + 24) & -(__int64)(this != 0),
               &v12);
        v4 = v9;
        if ( v9 >= 0 )
        {
          *((_DWORD *)this + 40) = v12;
          *((_QWORD *)this + 19) = ppv;
          ppv = 0;
          goto LABEL_43;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            289,
            &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
            (unsigned int)v9);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBDF,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
          (const char *)v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v6 = 290;
          goto LABEL_17;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            287,
            &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
            (unsigned int)v8);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBDB,
          (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
          (const char *)v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v6 = 288;
          goto LABEL_17;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          285,
          &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
          (unsigned int)v7);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBD7,
        (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
        (const char *)v4);
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v6 = 286;
        goto LABEL_17;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        283,
        &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids,
        (unsigned int)v3);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBD2,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\kadetector\\wnpkadetectorimpl.cpp",
      (const char *)v4);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 284;
LABEL_17:
      WPP_SF_d(v5[2], v6, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v4);
LABEL_43:
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    ppv = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v14 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v15 = 0;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 291, &WPP_9a262fb51b93373699b13bc917fc3706_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18008f108  push    rbp
0x18008f10a  push    rbx
0x18008f10b  push    rsi
0x18008f10c  push    rdi
0x18008f10d  push    r12
0x18008f10f  push    r13
0x18008f111  push    r14
0x18008f113  mov     rbp, rsp
0x18008f116  sub     rsp, 30h
0x18008f11a  mov     rdi, rcx
0x18008f11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f124  lea     r12, WPP_GLOBAL_Control
0x18008f12b  lea     r13, WPP_9a262fb51b93373699b13bc917fc3706_Traceguids
0x18008f132  cmp     rcx, r12
0x18008f135  jz      short loc_18008F154
0x18008f137  test    byte ptr [rcx+1Ch], 8
0x18008f13b  jz      short loc_18008F154
0x18008f13d  cmp     byte ptr [rcx+19h], 6
0x18008f141  jb      short loc_18008F154
0x18008f143  mov     rcx, [rcx+10h]
0x18008f147  mov     edx, 11Ah
0x18008f14c  mov     r8, r13
0x18008f14f  call    WPP_SF_
0x18008f154  lea     rsi, [rdi+98h]
0x18008f15b  cmp     qword ptr [rsi], 0
0x18008f15f  jz      short loc_18008F166
0x18008f161  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008f166  lea     r14, [rdi+0A0h]
0x18008f16d  cmp     dword ptr [r14], 0
0x18008f171  jz      short loc_18008F178
0x18008f173  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008f178  xor     edx, edx; pUnkOuter
0x18008f17a  mov     [rbp+arg_8], 0
0x18008f182  lea     rax, [rbp+arg_8]
0x18008f186  mov     [rbp+arg_10], 0
0x18008f18e  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18008f195  mov     [rbp+arg_18], 0
0x18008f19d  lea     rcx, CLSID_NetworkListManager; rclsid
0x18008f1a4  mov     [rbp+arg_0], 0
0x18008f1ab  lea     r8d, [rdx+1]; dwClsContext
0x18008f1af  mov     [rsp+30h+ppv], rax; int
0x18008f1b4  call    cs:__imp_CoCreateInstance
0x18008f1ba  mov     ebx, eax
0x18008f1bc  test    eax, eax
0x18008f1be  jns     short loc_18008F237
0x18008f1c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f1c7  cmp     rcx, r12
0x18008f1ca  jz      short loc_18008F1EC
0x18008f1cc  test    byte ptr [rcx+1Ch], 8
0x18008f1d0  jz      short loc_18008F1EC
0x18008f1d2  cmp     byte ptr [rcx+19h], 2
0x18008f1d6  jb      short loc_18008F1EC
0x18008f1d8  mov     rcx, [rcx+10h]
0x18008f1dc  mov     edx, 11Bh
0x18008f1e1  mov     r9d, eax
0x18008f1e4  mov     r8, r13
0x18008f1e7  call    WPP_SF_d
0x18008f1ec  mov     rcx, [rbp+38h]; this
0x18008f1f0  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008f1f7  mov     r9d, ebx; char *
0x18008f1fa  mov     edx, 0BD2h; void *
0x18008f1ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008f204  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f20b  cmp     rcx, r12
0x18008f20e  jz      loc_18008F3EB
0x18008f214  test    byte ptr [rcx+1Ch], 80h
0x18008f218  jz      loc_18008F3EB
0x18008f21e  mov     edx, 11Ch
0x18008f223  mov     rcx, [rcx+10h]
0x18008f227  mov     r9d, ebx
0x18008f22a  mov     r8, r13
0x18008f22d  call    WPP_SF_d
0x18008f232  jmp     loc_18008F3E4
0x18008f237  mov     rcx, [rbp+arg_8]
0x18008f23b  lea     r8, [rbp+arg_10]
0x18008f23f  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18008f246  mov     rax, [rcx]
0x18008f249  mov     rax, [rax]
0x18008f24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f251  mov     ebx, eax
0x18008f253  test    eax, eax
0x18008f255  jns     short loc_18008F2BF
0x18008f257  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f25e  cmp     rcx, r12
0x18008f261  jz      short loc_18008F283
0x18008f263  test    byte ptr [rcx+1Ch], 8
0x18008f267  jz      short loc_18008F283
0x18008f269  cmp     byte ptr [rcx+19h], 2
0x18008f26d  jb      short loc_18008F283
0x18008f26f  mov     rcx, [rcx+10h]
0x18008f273  mov     edx, 11Dh
0x18008f278  mov     r9d, eax
0x18008f27b  mov     r8, r13
0x18008f27e  call    WPP_SF_d
0x18008f283  mov     rcx, [rbp+38h]; this
0x18008f287  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008f28e  mov     r9d, ebx; char *
0x18008f291  mov     edx, 0BD7h; void *
0x18008f296  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008f29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f2a2  cmp     rcx, r12
0x18008f2a5  jz      loc_18008F3EB
0x18008f2ab  test    byte ptr [rcx+1Ch], 80h
0x18008f2af  jz      loc_18008F3EB
0x18008f2b5  mov     edx, 11Eh
0x18008f2ba  jmp     loc_18008F223
0x18008f2bf  mov     rcx, [rbp+arg_10]
0x18008f2c3  lea     r8, [rbp+arg_18]
0x18008f2c7  lea     rdx, _GUID_dcb00007_570f_4a9b_8d69_199fdba5723b
0x18008f2ce  mov     rax, [rcx]
0x18008f2d1  mov     rax, [rax+20h]
0x18008f2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f2da  mov     ebx, eax
0x18008f2dc  test    eax, eax
0x18008f2de  jns     short loc_18008F348
0x18008f2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f2e7  cmp     rcx, r12
0x18008f2ea  jz      short loc_18008F30C
0x18008f2ec  test    byte ptr [rcx+1Ch], 8
0x18008f2f0  jz      short loc_18008F30C
0x18008f2f2  cmp     byte ptr [rcx+19h], 2
0x18008f2f6  jb      short loc_18008F30C
0x18008f2f8  mov     rcx, [rcx+10h]
0x18008f2fc  mov     edx, 11Fh
0x18008f301  mov     r9d, eax
0x18008f304  mov     r8, r13
0x18008f307  call    WPP_SF_d
0x18008f30c  mov     rcx, [rbp+38h]; this
0x18008f310  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008f317  mov     r9d, ebx; char *
0x18008f31a  mov     edx, 0BDBh; void *
0x18008f31f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008f324  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f32b  cmp     rcx, r12
0x18008f32e  jz      loc_18008F3EB
0x18008f334  test    byte ptr [rcx+1Ch], 80h
0x18008f338  jz      loc_18008F3EB
0x18008f33e  mov     edx, 120h
0x18008f343  jmp     loc_18008F223
0x18008f348  mov     rcx, [rbp+arg_18]
0x18008f34c  lea     rax, [rdi+18h]
0x18008f350  neg     rdi
0x18008f353  lea     r8, [rbp+arg_0]
0x18008f357  sbb     rdx, rdx
0x18008f35a  mov     r9, [rcx]
0x18008f35d  and     rdx, rax
0x18008f360  mov     rax, [r9+28h]
0x18008f364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f369  mov     ebx, eax
0x18008f36b  test    eax, eax
0x18008f36d  jns     short loc_18008F3CF
0x18008f36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f376  cmp     rcx, r12
0x18008f379  jz      short loc_18008F39B
0x18008f37b  test    byte ptr [rcx+1Ch], 8
0x18008f37f  jz      short loc_18008F39B
0x18008f381  cmp     byte ptr [rcx+19h], 2
0x18008f385  jb      short loc_18008F39B
0x18008f387  mov     rcx, [rcx+10h]
0x18008f38b  mov     edx, 121h
0x18008f390  mov     r9d, eax
0x18008f393  mov     r8, r13
0x18008f396  call    WPP_SF_d
0x18008f39b  mov     rcx, [rbp+38h]; this
0x18008f39f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008f3a6  mov     r9d, ebx; char *
0x18008f3a9  mov     edx, 0BDFh; void *
0x18008f3ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008f3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f3ba  cmp     rcx, r12
0x18008f3bd  jz      short loc_18008F3EB
0x18008f3bf  test    byte ptr [rcx+1Ch], 80h
0x18008f3c3  jz      short loc_18008F3EB
0x18008f3c5  mov     edx, 122h
0x18008f3ca  jmp     loc_18008F223
0x18008f3cf  mov     eax, [rbp+arg_0]
0x18008f3d2  mov     [r14], eax
0x18008f3d5  mov     rax, [rbp+arg_8]
0x18008f3d9  mov     [rsi], rax
0x18008f3dc  mov     [rbp+arg_8], 0
0x18008f3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f3eb  mov     rdx, [rbp+arg_8]
0x18008f3ef  test    rdx, rdx
0x18008f3f2  jz      short loc_18008F412
0x18008f3f4  mov     rax, [rdx]
0x18008f3f7  mov     rcx, rdx
0x18008f3fa  mov     rax, [rax+10h]
0x18008f3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f403  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f40a  mov     [rbp+arg_8], 0
0x18008f412  mov     rdx, [rbp+arg_10]
0x18008f416  test    rdx, rdx
0x18008f419  jz      short loc_18008F439
0x18008f41b  mov     rax, [rdx]
0x18008f41e  mov     rcx, rdx
0x18008f421  mov     rax, [rax+10h]
0x18008f425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f42a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f431  mov     [rbp+arg_10], 0
0x18008f439  mov     rdx, [rbp+arg_18]
0x18008f43d  test    rdx, rdx
0x18008f440  jz      short loc_18008F460
0x18008f442  mov     rax, [rdx]
0x18008f445  mov     rcx, rdx
0x18008f448  mov     rax, [rax+10h]
0x18008f44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f451  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f458  mov     [rbp+arg_18], 0
0x18008f460  cmp     rcx, r12
0x18008f463  jz      short loc_18008F485
0x18008f465  test    byte ptr [rcx+1Ch], 8
0x18008f469  jz      short loc_18008F485
0x18008f46b  cmp     byte ptr [rcx+19h], 6
0x18008f46f  jb      short loc_18008F485
0x18008f471  mov     rcx, [rcx+10h]
0x18008f475  mov     edx, 123h
0x18008f47a  mov     r9d, ebx
0x18008f47d  mov     r8, r13
0x18008f480  call    WPP_SF_d
0x18008f485  mov     eax, ebx
0x18008f487  add     rsp, 30h
0x18008f48b  pop     r14
0x18008f48d  pop     r13
0x18008f48f  pop     r12
0x18008f491  pop     rdi
0x18008f492  pop     rsi
0x18008f493  pop     rbx
0x18008f494  pop     rbp
0x18008f495  retn
```
