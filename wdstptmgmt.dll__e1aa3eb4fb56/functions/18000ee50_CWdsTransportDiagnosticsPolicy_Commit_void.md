# CWdsTransportDiagnosticsPolicy::Commit(void)

- ea: `0x18000ee50`
- end: `0x18000f1fc`
- name: `?Commit@CWdsTransportDiagnosticsPolicy@@UEAAJXZ`
- size: `940`
- prototype: `__int64 __fastcall(CWdsTransportDiagnosticsPolicy *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009254`
- `0x180009e20`
- `0x18000ee50`
- `0x18000fdcc`

## import_xrefs

- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000eee5`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000ef86`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f017`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f09a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f11b`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000eee5`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000ef86`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f017`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f09a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000f11b`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ef33`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000efd2`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f04f`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f0d0`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f14c`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000ef33`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000efd2`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f04f`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f0d0`
- `WdsCommonLib!?SetValueDword@CRegKey@@QEAAKPEBGK@Z` at `0x18000f14c`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ee9b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f18d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f1bd`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ee9b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f18d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000f1bd`

## string_xrefs

- `0x18000f17a`: `Will notify WDS Transport services of the settings modification.\n`
- `0x18000ef6b`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Diagnostics`
- `0x18000effc`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSTFTP\Diagnostics`
- `0x18000f07c`: `System\CurrentControlSet\Services\WDSServer\Providers\WdsImgSrv\Diagnostics`
- `0x18000f0fd`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Diagnostics`
- `0x18000ee88`: `-> CWdsTransportDiagnosticsPolicy::Commit(0x%p)`
- `0x18000f1aa`: `<- CWdsTransportDiagnosticsPolicy::Commit(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportDiagnosticsPolicy::Commit(CWdsTransportDiagnosticsPolicy *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  CWdsTransportServer **v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  _DWORD *v12; // r12
  CWdsTransportServer **v13; // r15
  __int64 v14; // rdx
  __int64 v15; // r8
  _DWORD *v16; // r13
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v24; // [rsp+20h] [rbp-20h]
  _BYTE v25[16]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+70h] [rbp+30h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v25, (char *)this + 80);
  v26 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportDiagnosticsPolicy::Commit(0x%p)", this);
  v3 = *((_DWORD *)this + 32);
  if ( !v3 )
    goto LABEL_32;
  v4 = (CWdsTransportServer **)((char *)this + 64);
  if ( (v3 & 1) != 0 )
  {
    v5 = CRegKey::RemoteOpen(
           (CRegKey *)&v26,
           *((const unsigned __int16 **)*v4 + 14),
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\WDS\\Diagnostics",
           0x20006u);
    if ( (unsigned int)ElValidateWin32_5(v5, v6, v7, 833) )
      goto LABEL_4;
    v5 = CRegKey::SetValueDword((CRegKey *)&v26, L"DiagnosticsEnabled", *((_DWORD *)this + 33));
    if ( (unsigned int)ElValidateWin32_5(v5, v9, v10, 837) )
      goto LABEL_4;
    *((_DWORD *)this + 32) &= ~1u;
    v3 = *((_DWORD *)this + 32);
  }
  if ( (v3 & 2) == 0 )
  {
LABEL_30:
    CTrace::Trace(
      (CTrace *)qword_18003B770,
      0x10000u,
      L"Will notify WDS Transport services of the settings modification.\n");
    v11 = CWdsTransportServer::SignalSettingsChange(*v4);
    goto LABEL_31;
  }
  v11 = CRegKey::RemoteOpen(
          (CRegKey *)&v26,
          *((const unsigned __int16 **)*v4 + 14),
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Diagnostics",
          0x20006u);
  if ( v11 )
  {
    if ( v11 != 2 )
      goto LABEL_13;
    v12 = (_DWORD *)((char *)this + 136);
    v13 = (CWdsTransportServer **)((char *)this + 64);
  }
  else
  {
    v12 = (_DWORD *)((char *)this + 136);
    v13 = (CWdsTransportServer **)((char *)this + 64);
    v5 = CRegKey::SetValueDword((CRegKey *)&v26, L"DiagnosticsEnabled", *((_DWORD *)this + 34) & 1);
    if ( (unsigned int)ElValidateWin32_5(v5, v14, v15, 870) )
      goto LABEL_4;
  }
  v11 = CRegKey::RemoteOpen(
          (CRegKey *)&v26,
          *((const unsigned __int16 **)*v4 + 14),
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSTFTP\\Diagnostics",
          0x20006u);
  if ( v11 )
  {
    if ( v11 != 2 )
      goto LABEL_13;
    v16 = (_DWORD *)((char *)this + 136);
  }
  else
  {
    v13 = (CWdsTransportServer **)((char *)this + 64);
    v5 = CRegKey::SetValueDword((CRegKey *)&v26, L"DiagnosticsEnabled", (*v12 >> 1) & 1);
    v16 = v12;
    if ( (unsigned int)ElValidateWin32_5(v5, v17, v18, 893) )
      goto LABEL_4;
  }
  v11 = CRegKey::RemoteOpen(
          (CRegKey *)&v26,
          *((const unsigned __int16 **)*v13 + 14),
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WdsImgSrv\\Diagnostics",
          0x20006u);
  if ( v11 )
  {
    if ( v11 != 2 )
      goto LABEL_13;
    v4 = (CWdsTransportServer **)((char *)this + 64);
    goto LABEL_25;
  }
  v16 = v12;
  v5 = CRegKey::SetValueDword((CRegKey *)&v26, L"DiagnosticsEnabled", (*v12 >> 2) & 1);
  v4 = v13;
  if ( !(unsigned int)ElValidateWin32_5(v5, v19, v20, 916) )
  {
LABEL_25:
    v11 = CRegKey::RemoteOpen(
            (CRegKey *)&v26,
            *((const unsigned __int16 **)*v13 + 14),
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Diagnostics",
            0x20006u);
    if ( v11 )
    {
      if ( v11 != 2 )
      {
LABEL_13:
        if ( v11 > 0 )
        {
          v8 = (unsigned __int16)v11;
          goto LABEL_7;
        }
LABEL_31:
        v2 = v11;
        goto LABEL_32;
      }
      goto LABEL_29;
    }
    v4 = v13;
    v5 = CRegKey::SetValueDword((CRegKey *)&v26, L"DiagnosticsEnabled", (*v16 >> 3) & 1);
    if ( !(unsigned int)ElValidateWin32_5(v5, v21, v22, 939) )
    {
LABEL_29:
      *((_DWORD *)this + 32) &= ~2u;
      goto LABEL_30;
    }
  }
LABEL_4:
  if ( (int)v5 > 0 )
  {
    v8 = (unsigned __int16)v5;
LABEL_7:
    v2 = v8 | 0x80070000;
    goto LABEL_32;
  }
  v2 = v5;
LABEL_32:
  LODWORD(v24) = v2;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"<- CWdsTransportDiagnosticsPolicy::Commit(0x%p) =%x", this, v24);
  CRegKey::Close((CRegKey *)&v26);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v25);
  return v2;
}

```

## disassembly

```asm
0x18000ee50  mov     [rsp-28h+arg_8], rbx
0x18000ee55  mov     [rsp-28h+arg_10], rsi
0x18000ee5a  mov     [rsp-28h+arg_18], rdi
0x18000ee5f  push    rbp
0x18000ee60  push    r12
0x18000ee62  push    r13
0x18000ee64  push    r14
0x18000ee66  push    r15
0x18000ee68  mov     rbp, rsp
0x18000ee6b  sub     rsp, 40h
0x18000ee6f  mov     rdi, rcx
0x18000ee72  lea     rdx, [rcx+50h]
0x18000ee76  lea     rcx, [rbp+var_10]
0x18000ee7a  xor     ebx, ebx
0x18000ee7c  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000ee81  mov     r9, rdi
0x18000ee84  mov     [rbp+arg_0], rbx
0x18000ee88  lea     r8, aCwdstransportd_0; "-> CWdsTransportDiagnosticsPolicy::Comm"...
0x18000ee8f  mov     edx, 10000h
0x18000ee94  lea     rcx, qword_18003B770
0x18000ee9b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000eea2  nop     dword ptr [rax+rax+00h]
0x18000eea7  mov     eax, [rdi+80h]
0x18000eead  test    eax, eax
0x18000eeaf  jz      loc_18000F1A3
0x18000eeb5  lea     rsi, [rdi+40h]
0x18000eeb9  mov     r13d, 20006h
0x18000eebf  test    al, 1
0x18000eec1  jz      loc_18000EF60
0x18000eec7  mov     rdx, [rsi]
0x18000eeca  lea     r9, aSoftwareMicros; "Software\\Microsoft\\WDS\\Diagnostics"
0x18000eed1  mov     r8, 0FFFFFFFF80000002h
0x18000eed8  mov     [rsp+40h+var_20], r13d
0x18000eedd  lea     rcx, [rbp+arg_0]
0x18000eee1  mov     rdx, [rdx+70h]
0x18000eee5  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000eeec  nop     dword ptr [rax+rax+00h]
0x18000eef1  mov     ecx, eax
0x18000eef3  mov     r9d, 341h
0x18000eef9  mov     r14d, eax
0x18000eefc  call    ElValidateWin32_5
0x18000ef01  test    eax, eax
0x18000ef03  jz      short loc_18000EF21
0x18000ef05  test    r14d, r14d
0x18000ef08  jg      short loc_18000EF12
0x18000ef0a  mov     ebx, r14d
0x18000ef0d  jmp     loc_18000F1A3
0x18000ef12  movzx   ebx, r14w
0x18000ef16  or      ebx, 80070000h
0x18000ef1c  jmp     loc_18000F1A3
0x18000ef21  mov     r8d, [rdi+84h]
0x18000ef28  lea     rdx, aDiagnosticsena; "DiagnosticsEnabled"
0x18000ef2f  lea     rcx, [rbp+arg_0]
0x18000ef33  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000ef3a  nop     dword ptr [rax+rax+00h]
0x18000ef3f  mov     ecx, eax
0x18000ef41  mov     r9d, 345h
0x18000ef47  mov     r14d, eax
0x18000ef4a  call    ElValidateWin32_5
0x18000ef4f  test    eax, eax
0x18000ef51  jnz     short loc_18000EF05
0x18000ef53  and     dword ptr [rdi+80h], 0FFFFFFFEh
0x18000ef5a  mov     eax, [rdi+80h]
0x18000ef60  test    al, 2
0x18000ef62  jz      loc_18000F17A
0x18000ef68  mov     rdx, [rsi]
0x18000ef6b  lea     r9, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\WD"...
0x18000ef72  mov     r8, 0FFFFFFFF80000002h
0x18000ef79  mov     [rsp+40h+var_20], r13d
0x18000ef7e  lea     rcx, [rbp+arg_0]
0x18000ef82  mov     rdx, [rdx+70h]
0x18000ef86  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000ef8d  nop     dword ptr [rax+rax+00h]
0x18000ef92  test    eax, eax
0x18000ef94  jz      short loc_18000EFB8
0x18000ef96  cmp     eax, 2
0x18000ef99  jz      short loc_18000EFAB
0x18000ef9b  test    eax, eax
0x18000ef9d  jle     loc_18000F1A1
0x18000efa3  movzx   ebx, ax
0x18000efa6  jmp     loc_18000EF16
0x18000efab  lea     r12, [rdi+88h]
0x18000efb2  lea     r15, [rdi+40h]
0x18000efb6  jmp     short loc_18000EFF9
0x18000efb8  lea     r12, [rdi+88h]
0x18000efbf  mov     r8d, [r12]
0x18000efc3  lea     rdx, aDiagnosticsena; "DiagnosticsEnabled"
0x18000efca  and     r8d, 1
0x18000efce  lea     rcx, [rbp+arg_0]
0x18000efd2  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000efd9  nop     dword ptr [rax+rax+00h]
0x18000efde  mov     r9d, 366h
0x18000efe4  mov     r15, rsi
0x18000efe7  mov     ecx, eax
0x18000efe9  mov     r14d, eax
0x18000efec  call    ElValidateWin32_5
0x18000eff1  test    eax, eax
0x18000eff3  jnz     loc_18000EF05
0x18000eff9  mov     rdx, [rsi]
0x18000effc  lea     r9, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WD"...
0x18000f003  mov     r8, 0FFFFFFFF80000002h
0x18000f00a  mov     [rsp+40h+var_20], r13d
0x18000f00f  lea     rcx, [rbp+arg_0]
0x18000f013  mov     rdx, [rdx+70h]
0x18000f017  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f01e  nop     dword ptr [rax+rax+00h]
0x18000f023  test    eax, eax
0x18000f025  jz      short loc_18000F039
0x18000f027  cmp     eax, 2
0x18000f02a  jnz     loc_18000EF9B
0x18000f030  lea     r13, [rdi+88h]
0x18000f037  jmp     short loc_18000F079
0x18000f039  mov     r8d, [r12]
0x18000f03d  lea     rdx, aDiagnosticsena; "DiagnosticsEnabled"
0x18000f044  shr     r8d, 1
0x18000f047  lea     rcx, [rbp+arg_0]
0x18000f04b  and     r8d, 1
0x18000f04f  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000f056  nop     dword ptr [rax+rax+00h]
0x18000f05b  mov     r9d, 37Dh
0x18000f061  mov     r15, rsi
0x18000f064  mov     ecx, eax
0x18000f066  mov     r14d, eax
0x18000f069  mov     r13, r12
0x18000f06c  call    ElValidateWin32_5
0x18000f071  test    eax, eax
0x18000f073  jnz     loc_18000EF05
0x18000f079  mov     rdx, [r15]
0x18000f07c  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x18000f083  mov     r8, 0FFFFFFFF80000002h
0x18000f08a  mov     [rsp+40h+var_20], 20006h
0x18000f092  lea     rcx, [rbp+arg_0]
0x18000f096  mov     rdx, [rdx+70h]
0x18000f09a  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f0a1  nop     dword ptr [rax+rax+00h]
0x18000f0a6  test    eax, eax
0x18000f0a8  jz      short loc_18000F0B9
0x18000f0aa  cmp     eax, 2
0x18000f0ad  jnz     loc_18000EF9B
0x18000f0b3  lea     rsi, [rdi+40h]
0x18000f0b7  jmp     short loc_18000F0FA
0x18000f0b9  mov     r8d, [r12]
0x18000f0bd  lea     rdx, aDiagnosticsena; "DiagnosticsEnabled"
0x18000f0c4  shr     r8d, 2
0x18000f0c8  lea     rcx, [rbp+arg_0]
0x18000f0cc  and     r8d, 1
0x18000f0d0  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000f0d7  nop     dword ptr [rax+rax+00h]
0x18000f0dc  mov     r9d, 394h
0x18000f0e2  mov     r13, r12
0x18000f0e5  mov     ecx, eax
0x18000f0e7  mov     r14d, eax
0x18000f0ea  mov     rsi, r15
0x18000f0ed  call    ElValidateWin32_5
0x18000f0f2  test    eax, eax
0x18000f0f4  jnz     loc_18000EF05
0x18000f0fa  mov     rdx, [r15]
0x18000f0fd  lea     r9, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WD"...
0x18000f104  mov     r8, 0FFFFFFFF80000002h
0x18000f10b  mov     [rsp+40h+var_20], 20006h
0x18000f113  lea     rcx, [rbp+arg_0]
0x18000f117  mov     rdx, [rdx+70h]
0x18000f11b  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000f122  nop     dword ptr [rax+rax+00h]
0x18000f127  test    eax, eax
0x18000f129  jz      short loc_18000F135
0x18000f12b  cmp     eax, 2
0x18000f12e  jz      short loc_18000F173
0x18000f130  jmp     loc_18000EF9B
0x18000f135  mov     r8d, [r13+0]
0x18000f139  lea     rdx, aDiagnosticsena; "DiagnosticsEnabled"
0x18000f140  shr     r8d, 3
0x18000f144  lea     rcx, [rbp+arg_0]
0x18000f148  and     r8d, 1
0x18000f14c  call    cs:__imp_?SetValueDword@CRegKey@@QEAAKPEBGK@Z; CRegKey::SetValueDword(ushort const *,ulong)
0x18000f153  nop     dword ptr [rax+rax+00h]
0x18000f158  mov     r9d, 3ABh
0x18000f15e  mov     rsi, r15
0x18000f161  mov     ecx, eax
0x18000f163  mov     r14d, eax
0x18000f166  call    ElValidateWin32_5
0x18000f16b  test    eax, eax
0x18000f16d  jnz     loc_18000EF05
0x18000f173  and     dword ptr [rdi+80h], 0FFFFFFFDh
0x18000f17a  lea     r8, aWillNotifyWdsT; "Will notify WDS Transport services of t"...
0x18000f181  mov     edx, 10000h
0x18000f186  lea     rcx, qword_18003B770
0x18000f18d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000f194  nop     dword ptr [rax+rax+00h]
0x18000f199  mov     rcx, [rsi]; this
0x18000f19c  call    ?SignalSettingsChange@CWdsTransportServer@@QEAAJXZ; CWdsTransportServer::SignalSettingsChange(void)
0x18000f1a1  mov     ebx, eax
0x18000f1a3  mov     r9, rdi
0x18000f1a6  mov     [rsp+40h+var_20], ebx
0x18000f1aa  lea     r8, aCwdstransportd_12; "<- CWdsTransportDiagnosticsPolicy::Comm"...
0x18000f1b1  mov     edx, 10000h
0x18000f1b6  lea     rcx, qword_18003B770
0x18000f1bd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000f1c4  nop     dword ptr [rax+rax+00h]
0x18000f1c9  lea     rcx, [rbp+arg_0]; this
0x18000f1cd  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000f1d2  lea     rcx, [rbp+var_10]
0x18000f1d6  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000f1db  lea     r11, [rsp+40h+var_s0]
0x18000f1e0  mov     eax, ebx
0x18000f1e2  mov     rbx, [r11+38h]
0x18000f1e6  mov     rsi, [r11+40h]
0x18000f1ea  mov     rdi, [r11+48h]
0x18000f1ee  mov     rsp, r11
0x18000f1f1  pop     r15
0x18000f1f3  pop     r14
0x18000f1f5  pop     r13
0x18000f1f7  pop     r12
0x18000f1f9  pop     rbp
0x18000f1fa  retn
```
