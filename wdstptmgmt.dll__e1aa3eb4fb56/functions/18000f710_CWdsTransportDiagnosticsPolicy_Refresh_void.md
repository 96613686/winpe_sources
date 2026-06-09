# CWdsTransportDiagnosticsPolicy::Refresh(void)

- ea: `0x18000f710`
- end: `0x18000fa38`
- name: `?Refresh@CWdsTransportDiagnosticsPolicy@@UEAAJXZ`
- size: `808`
- prototype: `__int64 __fastcall(CWdsTransportDiagnosticsPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009e20`
- `0x18000f710`
- `0x18000fdcc`

## import_xrefs

- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f7fa`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f864`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f8d0`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f93f`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f9ae`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f7fa`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f864`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f8d0`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f93f`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000f9ae`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f7b1`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f834`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f8ae`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f91a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f989`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f7b1`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f834`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f8ae`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f91a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f989`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f758`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f9fe`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f758`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f9fe`

## string_xrefs

- `0x18000f81d`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Diagnostics`
- `0x18000f897`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP\Diagnostics`
- `0x18000f903`: `System\CurrentControlSet\Services\WDSServer\Providers\WdsImgSrv\Diagnostics`
- `0x18000f972`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Diagnostics`

## pseudocode

```c
__int64 __fastcall CWdsTransportDiagnosticsPolicy::Refresh(CWdsTransportDiagnosticsPolicy *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 ValueBool; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v20; // [rsp+20h] [rbp-20h]
  _BYTE v21[16]; // [rsp+30h] [rbp-10h] BYREF
  int v22; // [rsp+70h] [rbp+30h] BYREF
  __int64 v23; // [rsp+78h] [rbp+38h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v21, (char *)this + 80);
  v23 = 0;
  v22 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportDiagnosticsPolicy::Refresh(0x%p)", this);
  if ( !*((_DWORD *)this + 32) )
  {
    v3 = *((_QWORD *)this + 8);
    *((_DWORD *)this + 31) = 0;
    *((_DWORD *)this + 33) = 0;
    *((_DWORD *)this + 34) = 0;
    ValueBool = CRegKey::RemoteOpen(
                  (CRegKey *)&v23,
                  *(const unsigned __int16 **)(v3 + 112),
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\WDS\\Diagnostics",
                  0x20019u);
    if ( (unsigned int)ElValidateWin32_5(ValueBool, v5, v6, 631) )
      goto LABEL_4;
    ValueBool = CRegKey::GetValueBool((CRegKey *)&v23, L"DiagnosticsEnabled", (int *)this + 33);
    if ( (unsigned int)ElValidateWin32_5(ValueBool, v8, v9, 635) )
      goto LABEL_4;
    v10 = CRegKey::RemoteOpen(
            (CRegKey *)&v23,
            *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Diagnostics",
            0x20019u);
    if ( v10 )
    {
      if ( v10 != 2 )
      {
LABEL_11:
        if ( v10 <= 0 )
        {
          v2 = v10;
          goto LABEL_36;
        }
        v7 = (unsigned __int16)v10;
        goto LABEL_7;
      }
    }
    else
    {
      ValueBool = CRegKey::GetValueBool((CRegKey *)&v23, L"DiagnosticsEnabled", &v22);
      if ( (unsigned int)ElValidateWin32_5(ValueBool, v11, v12, 658) )
        goto LABEL_4;
      if ( v22 )
        *((_DWORD *)this + 34) |= 1u;
    }
    v10 = CRegKey::RemoteOpen(
            (CRegKey *)&v23,
            *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP\\Diagnostics",
            0x20019u);
    if ( v10 )
    {
      if ( v10 != 2 )
        goto LABEL_11;
    }
    else
    {
      ValueBool = CRegKey::GetValueBool((CRegKey *)&v23, L"DiagnosticsEnabled", &v22);
      if ( (unsigned int)ElValidateWin32_5(ValueBool, v13, v14, 687) )
        goto LABEL_4;
      if ( v22 )
        *((_DWORD *)this + 34) |= 2u;
    }
    v10 = CRegKey::RemoteOpen(
            (CRegKey *)&v23,
            *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WdsImgSrv\\Diagnostics",
            0x20019u);
    if ( v10 )
    {
      if ( v10 != 2 )
        goto LABEL_11;
    }
    else
    {
      ValueBool = CRegKey::GetValueBool((CRegKey *)&v23, L"DiagnosticsEnabled", &v22);
      if ( (unsigned int)ElValidateWin32_5(ValueBool, v15, v16, 716) )
        goto LABEL_4;
      if ( v22 )
        *((_DWORD *)this + 34) |= 4u;
    }
    v10 = CRegKey::RemoteOpen(
            (CRegKey *)&v23,
            *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Diagnostics",
            0x20019u);
    if ( v10 )
    {
      if ( v10 != 2 )
        goto LABEL_11;
LABEL_35:
      *((_DWORD *)this + 31) = 1;
      goto LABEL_36;
    }
    ValueBool = CRegKey::GetValueBool((CRegKey *)&v23, L"DiagnosticsEnabled", &v22);
    if ( !(unsigned int)ElValidateWin32_5(ValueBool, v17, v18, 745) )
    {
      if ( v22 )
        *((_DWORD *)this + 34) |= 8u;
      goto LABEL_35;
    }
LABEL_4:
    if ( (int)ValueBool <= 0 )
    {
      v2 = ValueBool;
      goto LABEL_36;
    }
    v7 = (unsigned __int16)ValueBool;
LABEL_7:
    v2 = v7 | 0x80070000;
    goto LABEL_36;
  }
  v2 = -1055915761;
LABEL_36:
  LODWORD(v20) = v2;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportDiagnosticsPolicy::Refresh(0x%p) =%x", this, v20);
  CRegKey::Close((CRegKey *)&v23);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v21);
  return v2;
}

```

## disassembly

```asm
0x18000f710  mov     [rsp-28h+arg_10], rbx
0x18000f715  mov     [rsp-28h+arg_18], rsi
0x18000f71a  push    rbp
0x18000f71b  push    rdi
0x18000f71c  push    r12
0x18000f71e  push    r14
0x18000f720  push    r15
0x18000f722  mov     rbp, rsp
0x18000f725  sub     rsp, 40h
0x18000f729  mov     rdi, rcx
0x18000f72c  lea     rdx, [rcx+50h]
0x18000f730  lea     rcx, [rbp+var_10]
0x18000f734  xor     ebx, ebx
0x18000f736  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000f73b  mov     r9, rdi
0x18000f73e  mov     [rbp+arg_8], rbx
0x18000f742  lea     r8, aCwdstransportd_1; "-> CWdsTransportDiagnosticsPolicy::Refr"...
0x18000f749  mov     [rbp+arg_0], ebx
0x18000f74c  mov     edx, 10000h
0x18000f751  lea     rcx, qword_18003B770
0x18000f758  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000f75f  nop     dword ptr [rax+rax+00h]
0x18000f764  cmp     [rdi+80h], ebx
0x18000f76a  jz      short loc_18000F776
0x18000f76c  mov     ebx, 0C110010Fh
0x18000f771  jmp     loc_18000F9E4
0x18000f776  mov     rdx, [rdi+40h]
0x18000f77a  lea     r14, [rdi+84h]
0x18000f781  mov     [rdi+7Ch], ebx
0x18000f784  lea     r9, aSoftwareMicros; "Software\\Microsoft\\WDS\\Diagnostics"
0x18000f78b  mov     [r14], ebx
0x18000f78e  lea     rcx, [rbp+arg_8]
0x18000f792  mov     [rdi+88h], ebx
0x18000f798  mov     r12, 0FFFFFFFF80000002h
0x18000f79f  mov     rdx, [rdx+70h]
0x18000f7a3  mov     r15d, 20019h
0x18000f7a9  mov     r8, r12
0x18000f7ac  mov     [rsp+40h+var_20], r15d
0x18000f7b1  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f7b8  nop     dword ptr [rax+rax+00h]
0x18000f7bd  mov     ecx, eax
0x18000f7bf  mov     r9d, 277h
0x18000f7c5  mov     esi, eax
0x18000f7c7  call    ElValidateWin32_5
0x18000f7cc  test    eax, eax
0x18000f7ce  jz      short loc_18000F7E9
0x18000f7d0  test    esi, esi
0x18000f7d2  jg      short loc_18000F7DB
0x18000f7d4  mov     ebx, esi
0x18000f7d6  jmp     loc_18000F9E4
0x18000f7db  movzx   ebx, si
0x18000f7de  or      ebx, 80070000h
0x18000f7e4  jmp     loc_18000F9E4
0x18000f7e9  mov     r8, r14
0x18000f7ec  lea     rcx, [rbp+arg_8]
0x18000f7f0  lea     r14, aDiagnosticsena; "DiagnosticsEnabled"
0x18000f7f7  mov     rdx, r14
0x18000f7fa  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000f801  nop     dword ptr [rax+rax+00h]
0x18000f806  mov     ecx, eax
0x18000f808  mov     r9d, 27Bh
0x18000f80e  mov     esi, eax
0x18000f810  call    ElValidateWin32_5
0x18000f815  test    eax, eax
0x18000f817  jnz     short loc_18000F7D0
0x18000f819  mov     rdx, [rdi+40h]
0x18000f81d  lea     r9, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\WD"...
0x18000f824  mov     r8, r12
0x18000f827  mov     [rsp+40h+var_20], r15d
0x18000f82c  lea     rcx, [rbp+arg_8]
0x18000f830  mov     rdx, [rdx+70h]
0x18000f834  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f83b  nop     dword ptr [rax+rax+00h]
0x18000f840  test    eax, eax
0x18000f842  jz      short loc_18000F859
0x18000f844  cmp     eax, 2
0x18000f847  jz      short loc_18000F893
0x18000f849  test    eax, eax
0x18000f84b  jg      short loc_18000F854
0x18000f84d  mov     ebx, eax
0x18000f84f  jmp     loc_18000F9E4
0x18000f854  movzx   ebx, ax
0x18000f857  jmp     short loc_18000F7DE
0x18000f859  lea     r8, [rbp+arg_0]
0x18000f85d  mov     rdx, r14
0x18000f860  lea     rcx, [rbp+arg_8]
0x18000f864  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000f86b  nop     dword ptr [rax+rax+00h]
0x18000f870  mov     ecx, eax
0x18000f872  mov     r9d, 292h
0x18000f878  mov     esi, eax
0x18000f87a  call    ElValidateWin32_5
0x18000f87f  test    eax, eax
0x18000f881  jnz     loc_18000F7D0
0x18000f887  cmp     [rbp+arg_0], ebx
0x18000f88a  jz      short loc_18000F893
0x18000f88c  or      dword ptr [rdi+88h], 1
0x18000f893  mov     rdx, [rdi+40h]
0x18000f897  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000f89e  mov     r8, r12
0x18000f8a1  mov     [rsp+40h+var_20], r15d
0x18000f8a6  lea     rcx, [rbp+arg_8]
0x18000f8aa  mov     rdx, [rdx+70h]
0x18000f8ae  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f8b5  nop     dword ptr [rax+rax+00h]
0x18000f8ba  test    eax, eax
0x18000f8bc  jz      short loc_18000F8C5
0x18000f8be  cmp     eax, 2
0x18000f8c1  jz      short loc_18000F8FF
0x18000f8c3  jmp     short loc_18000F849
0x18000f8c5  lea     r8, [rbp+arg_0]
0x18000f8c9  mov     rdx, r14
0x18000f8cc  lea     rcx, [rbp+arg_8]
0x18000f8d0  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000f8d7  nop     dword ptr [rax+rax+00h]
0x18000f8dc  mov     ecx, eax
0x18000f8de  mov     r9d, 2AFh
0x18000f8e4  mov     esi, eax
0x18000f8e6  call    ElValidateWin32_5
0x18000f8eb  test    eax, eax
0x18000f8ed  jnz     loc_18000F7D0
0x18000f8f3  cmp     [rbp+arg_0], ebx
0x18000f8f6  jz      short loc_18000F8FF
0x18000f8f8  or      dword ptr [rdi+88h], 2
0x18000f8ff  mov     rdx, [rdi+40h]
0x18000f903  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x18000f90a  mov     r8, r12
0x18000f90d  mov     [rsp+40h+var_20], r15d
0x18000f912  lea     rcx, [rbp+arg_8]
0x18000f916  mov     rdx, [rdx+70h]
0x18000f91a  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f921  nop     dword ptr [rax+rax+00h]
0x18000f926  test    eax, eax
0x18000f928  jz      short loc_18000F934
0x18000f92a  cmp     eax, 2
0x18000f92d  jz      short loc_18000F96E
0x18000f92f  jmp     loc_18000F849
0x18000f934  lea     r8, [rbp+arg_0]
0x18000f938  mov     rdx, r14
0x18000f93b  lea     rcx, [rbp+arg_8]
0x18000f93f  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000f946  nop     dword ptr [rax+rax+00h]
0x18000f94b  mov     ecx, eax
0x18000f94d  mov     r9d, 2CCh
0x18000f953  mov     esi, eax
0x18000f955  call    ElValidateWin32_5
0x18000f95a  test    eax, eax
0x18000f95c  jnz     loc_18000F7D0
0x18000f962  cmp     [rbp+arg_0], ebx
0x18000f965  jz      short loc_18000F96E
0x18000f967  or      dword ptr [rdi+88h], 4
0x18000f96e  mov     rdx, [rdi+40h]
0x18000f972  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WD"...
0x18000f979  mov     r8, r12
0x18000f97c  mov     [rsp+40h+var_20], r15d
0x18000f981  lea     rcx, [rbp+arg_8]
0x18000f985  mov     rdx, [rdx+70h]
0x18000f989  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f990  nop     dword ptr [rax+rax+00h]
0x18000f995  test    eax, eax
0x18000f997  jz      short loc_18000F9A3
0x18000f999  cmp     eax, 2
0x18000f99c  jz      short loc_18000F9DD
0x18000f99e  jmp     loc_18000F849
0x18000f9a3  lea     r8, [rbp+arg_0]
0x18000f9a7  mov     rdx, r14
0x18000f9aa  lea     rcx, [rbp+arg_8]
0x18000f9ae  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000f9b5  nop     dword ptr [rax+rax+00h]
0x18000f9ba  mov     ecx, eax
0x18000f9bc  mov     r9d, 2E9h
0x18000f9c2  mov     esi, eax
0x18000f9c4  call    ElValidateWin32_5
0x18000f9c9  test    eax, eax
0x18000f9cb  jnz     loc_18000F7D0
0x18000f9d1  cmp     [rbp+arg_0], ebx
0x18000f9d4  jz      short loc_18000F9DD
0x18000f9d6  or      dword ptr [rdi+88h], 8
0x18000f9dd  mov     dword ptr [rdi+7Ch], 1
0x18000f9e4  mov     r9, rdi
0x18000f9e7  mov     [rsp+40h+var_20], ebx
0x18000f9eb  lea     r8, aCwdstransportd_7; "<- CWdsTransportDiagnosticsPolicy::Refr"...
0x18000f9f2  mov     edx, 10000h
0x18000f9f7  lea     rcx, qword_18003B770
0x18000f9fe  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000fa05  nop     dword ptr [rax+rax+00h]
0x18000fa0a  lea     rcx, [rbp+arg_8]; this
0x18000fa0e  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000fa13  lea     rcx, [rbp+var_10]
0x18000fa17  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000fa1c  lea     r11, [rsp+40h+var_s0]
0x18000fa21  mov     eax, ebx
0x18000fa23  mov     rbx, [r11+40h]
0x18000fa27  mov     rsi, [r11+48h]
0x18000fa2b  mov     rsp, r11
0x18000fa2e  pop     r15
0x18000fa30  pop     r14
0x18000fa32  pop     r12
0x18000fa34  pop     rdi
0x18000fa35  pop     rbp
0x18000fa36  retn
```
