# CWdsTransportSetupManager::DelayInitialize(void)

- ea: `0x18000a0dc`
- end: `0x18000a4a0`
- name: `?DelayInitialize@CWdsTransportSetupManager@@QEAAJXZ`
- size: `964`
- prototype: `__int64 __fastcall(CWdsTransportSetupManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180009940`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180009e20`
- `0x18000a0dc`
- `0x18000b16c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a425`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a425`
- `NETAPI32!NetWkstaGetInfo` at `0x18000a19d`
- `NETAPI32!NetWkstaGetInfo` at `0x18000a19d`
- `NETAPI32!NetApiBufferFree` at `0x18000a43e`
- `NETAPI32!NetApiBufferFree` at `0x18000a43e`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000a39f`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000a3f2`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000a39f`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x18000a3f2`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a2dc`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a31b`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a35a`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a2dc`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a31b`
- `WdsCommonLib!?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z` at `0x18000a35a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a21a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a280`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a21a`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000a280`
- `WdsCommonLib!?AppendStrings@@YAKPEAPEAGKZZ` at `0x18000a158`
- `WdsCommonLib!?AppendStrings@@YAKPEAPEAGKZZ` at `0x18000a158`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a12b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a1d3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a2bc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a468`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a12b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a1d3`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a2bc`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000a468`

## string_xrefs

- `0x18000a26a`: `Software\Microsoft\WDS\InstalledFeatures`
- `0x18000a2a9`: `Error 0x%lx: Could not open WDS features key.\n`
- `0x18000a3e7`: `TransportProtocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWdsTransportSetupManager::DelayInitialize(CWdsTransportSetupManager *this)
{
  unsigned int v2; // ebx
  __int64 appended; // rsi
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  signed int Info; // eax
  LPBYTE v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v22; // [rsp+20h] [rbp-30h]
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v24[24]; // [rsp+38h] [rbp-18h] BYREF
  int v25; // [rsp+80h] [rbp+30h] BYREF
  __int64 v26; // [rsp+88h] [rbp+38h] BYREF
  LPWSTR servername; // [rsp+90h] [rbp+40h] BYREF
  LPBYTE bufptr; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v24, (char *)this + 80);
  servername = 0;
  bufptr = 0;
  v23 = 0;
  v26 = 0;
  v25 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportSetupManager::DelayInitialize(0x%p)", this);
  if ( *((_DWORD *)this + 30) )
    goto LABEL_40;
  appended = AppendStrings(&servername, 2u, L"\\\\", *(_QWORD *)(*((_QWORD *)this + 8) + 112LL));
  if ( (unsigned int)ElValidateWin32_2(appended, v4, v5, 248) )
  {
LABEL_3:
    if ( (int)appended <= 0 )
    {
      v2 = appended;
      goto LABEL_40;
    }
    v6 = (unsigned __int16)appended;
    goto LABEL_6;
  }
  Info = NetWkstaGetInfo(servername, 0x64u, &bufptr);
  if ( Info )
  {
    if ( Info > 0 )
      v2 = (unsigned __int16)Info | 0x80070000;
    else
      v2 = Info;
    CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Could not get OS version of server %s.\n", servername);
    goto LABEL_40;
  }
  v8 = bufptr;
  *((_DWORD *)this + 31) = *((_DWORD *)bufptr + 6);
  *((_DWORD *)this + 32) = *((_DWORD *)v8 + 7);
  v9 = CRegKey::RemoteOpen(
         (CRegKey *)&v23,
         *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\WDS",
         0x20019u);
  if ( !v9 )
  {
    if ( *((_DWORD *)this + 31) < 6u )
    {
      *((_DWORD *)this + 33) = 4;
      *((_DWORD *)this + 35) = 0;
    }
    else
    {
      v10 = CRegKey::RemoteOpen(
              (CRegKey *)&v26,
              *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\WDS\\InstalledFeatures",
              0x20019u);
      if ( v10 )
      {
        if ( v10 == 2 )
          goto LABEL_14;
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        else
          v2 = v10;
        CTrace::Trace((CTrace *)qword_18003B770, 0x80000u, L"Error 0x%lx: Could not open WDS features key.\n", v2);
        goto LABEL_40;
      }
      appended = CRegKey::GetValueBool((CRegKey *)&v26, L"WdsAdminPack", &v25);
      if ( (unsigned int)ElValidateWin32_2(appended, v11, v12, 369) )
        goto LABEL_3;
      if ( v25 )
        *((_DWORD *)this + 33) |= 1u;
      appended = CRegKey::GetValueBool((CRegKey *)&v26, L"WdsTransportServer", &v25);
      if ( (unsigned int)ElValidateWin32_2(appended, v13, v14, 381) )
        goto LABEL_3;
      if ( v25 )
        *((_DWORD *)this + 33) |= 2u;
      appended = CRegKey::GetValueBool((CRegKey *)&v26, L"WdsDeploymentServer", &v25);
      if ( (unsigned int)ElValidateWin32_2(appended, v15, v16, 393) )
        goto LABEL_3;
      if ( v25 )
        *((_DWORD *)this + 33) |= 4u;
      appended = CRegKey::GetValueDwordWithDefault(
                   (CRegKey *)&v26,
                   L"WdsTftpCapabilities",
                   0,
                   (unsigned int *)this + 35);
      if ( (unsigned int)ElValidateWin32_2(appended, v17, v18, 406) )
        goto LABEL_3;
    }
    if ( (*((_BYTE *)this + 132) & 2) != 0 )
    {
      appended = CRegKey::GetValueDwordWithDefault((CRegKey *)&v23, L"TransportProtocols", 0, (unsigned int *)this + 34);
      if ( (unsigned int)ElValidateWin32_2(appended, v19, v20, 442) )
        goto LABEL_3;
    }
    *((_DWORD *)this + 30) = 1;
    goto LABEL_40;
  }
  if ( v9 == 2 )
  {
LABEL_14:
    *((_DWORD *)this + 33) = 0;
    *((_DWORD *)this + 35) = 0;
    v2 = 0;
    goto LABEL_40;
  }
  if ( v9 > 0 )
  {
    v6 = (unsigned __int16)v9;
LABEL_6:
    v2 = v6 | 0x80070000;
    goto LABEL_40;
  }
  v2 = v9;
LABEL_40:
  if ( servername )
  {
    operator delete[](servername);
    servername = 0;
  }
  if ( bufptr )
  {
    NetApiBufferFree(bufptr);
    bufptr = 0;
  }
  LODWORD(v22) = v2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportSetupManager::DelayInitialize(0x%p) =%x",
    this,
    v22);
  CRegKey::Close((CRegKey *)&v26);
  CRegKey::Close((CRegKey *)&v23);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v24);
  return v2;
}

```

## disassembly

```asm
0x18000a0dc  push    rbp
0x18000a0de  push    rbx
0x18000a0df  push    rsi
0x18000a0e0  push    rdi
0x18000a0e1  push    r14
0x18000a0e3  mov     rbp, rsp
0x18000a0e6  sub     rsp, 50h
0x18000a0ea  mov     rdi, rcx
0x18000a0ed  xor     r14d, r14d
0x18000a0f0  mov     ebx, r14d
0x18000a0f3  lea     rdx, [rcx+50h]
0x18000a0f7  lea     rcx, [rbp+var_18]
0x18000a0fb  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000a100  nop
0x18000a101  mov     [rbp+servername], r14
0x18000a105  mov     [rbp+bufptr], r14
0x18000a109  mov     [rbp+var_20], r14
0x18000a10d  mov     [rbp+arg_8], r14
0x18000a111  mov     [rbp+arg_0], r14d
0x18000a115  mov     r9, rdi
0x18000a118  lea     r8, aCwdstransports_4; "-> CWdsTransportSetupManager::DelayInit"...
0x18000a11f  mov     edx, 10000h
0x18000a124  lea     rcx, qword_18003B770
0x18000a12b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a132  nop     dword ptr [rax+rax+00h]
0x18000a137  cmp     [rdi+78h], r14d
0x18000a13b  jnz     loc_18000A41C
0x18000a141  mov     r9, [rdi+40h]
0x18000a145  mov     r9, [r9+70h]
0x18000a149  lea     r8, asc_180026D68; "\\\\"
0x18000a150  lea     edx, [r14+2]
0x18000a154  lea     rcx, [rbp+servername]
0x18000a158  call    cs:__imp_?AppendStrings@@YAKPEAPEAGKZZ; AppendStrings(ushort * *,ulong,...)
0x18000a15f  nop     dword ptr [rax+rax+00h]
0x18000a164  mov     esi, eax
0x18000a166  mov     r9d, 0F8h
0x18000a16c  mov     ecx, eax
0x18000a16e  call    ElValidateWin32_2
0x18000a173  test    eax, eax
0x18000a175  jz      short loc_18000A190
0x18000a177  test    esi, esi
0x18000a179  jg      short loc_18000A182
0x18000a17b  mov     ebx, esi
0x18000a17d  jmp     loc_18000A41C
0x18000a182  movzx   ebx, si
0x18000a185  or      ebx, 80070000h
0x18000a18b  jmp     loc_18000A41C
0x18000a190  lea     r8, [rbp+bufptr]; bufptr
0x18000a194  mov     edx, 64h ; 'd'; level
0x18000a199  mov     rcx, [rbp+servername]; servername
0x18000a19d  call    cs:__imp_NetWkstaGetInfo
0x18000a1a4  nop     dword ptr [rax+rax+00h]
0x18000a1a9  test    eax, eax
0x18000a1ab  jz      short loc_18000A1E4
0x18000a1ad  jg      short loc_18000A1B3
0x18000a1af  mov     ebx, eax
0x18000a1b1  jmp     short loc_18000A1BC
0x18000a1b3  movzx   ebx, ax
0x18000a1b6  or      ebx, 80070000h
0x18000a1bc  mov     r9, [rbp+servername]
0x18000a1c0  lea     r8, aCouldNotGetOsV; "Could not get OS version of server %s."...
0x18000a1c7  mov     edx, 80000h
0x18000a1cc  lea     rcx, qword_18003B770
0x18000a1d3  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a1da  nop     dword ptr [rax+rax+00h]
0x18000a1df  jmp     loc_18000A41C
0x18000a1e4  mov     rcx, [rbp+bufptr]
0x18000a1e8  mov     eax, [rcx+18h]
0x18000a1eb  mov     [rdi+7Ch], eax
0x18000a1ee  mov     eax, [rcx+1Ch]
0x18000a1f1  mov     [rdi+80h], eax
0x18000a1f7  mov     rdx, [rdi+40h]
0x18000a1fb  mov     esi, 20019h
0x18000a200  mov     [rsp+50h+var_30], esi
0x18000a204  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\WDS"
0x18000a20b  mov     r8, 0FFFFFFFF80000002h
0x18000a212  mov     rdx, [rdx+70h]
0x18000a216  lea     rcx, [rbp+var_20]
0x18000a21a  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000a221  nop     dword ptr [rax+rax+00h]
0x18000a226  test    eax, eax
0x18000a228  jz      short loc_18000A258
0x18000a22a  cmp     eax, 2
0x18000a22d  jnz     short loc_18000A245
0x18000a22f  mov     [rdi+84h], r14d
0x18000a236  mov     [rdi+8Ch], r14d
0x18000a23d  mov     ebx, r14d
0x18000a240  jmp     loc_18000A41C
0x18000a245  test    eax, eax
0x18000a247  jg      short loc_18000A250
0x18000a249  mov     ebx, eax
0x18000a24b  jmp     loc_18000A41C
0x18000a250  movzx   ebx, ax
0x18000a253  jmp     loc_18000A185
0x18000a258  cmp     dword ptr [rdi+7Ch], 6
0x18000a25c  jb      loc_18000A3C3
0x18000a262  mov     rdx, [rdi+40h]
0x18000a266  mov     [rsp+50h+var_30], esi
0x18000a26a  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\WDS\\InstalledFeat"...
0x18000a271  mov     r8, 0FFFFFFFF80000002h
0x18000a278  mov     rdx, [rdx+70h]
0x18000a27c  lea     rcx, [rbp+arg_8]
0x18000a280  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000a287  nop     dword ptr [rax+rax+00h]
0x18000a28c  test    eax, eax
0x18000a28e  jz      short loc_18000A2CD
0x18000a290  cmp     eax, 2
0x18000a293  jz      short loc_18000A22F
0x18000a295  test    eax, eax
0x18000a297  jg      short loc_18000A29D
0x18000a299  mov     ebx, eax
0x18000a29b  jmp     short loc_18000A2A6
0x18000a29d  movzx   ebx, ax
0x18000a2a0  or      ebx, 80070000h
0x18000a2a6  mov     r9d, ebx
0x18000a2a9  lea     r8, aError0xLxCould; "Error 0x%lx: Could not open WDS feature"...
0x18000a2b0  mov     edx, 80000h
0x18000a2b5  lea     rcx, qword_18003B770
0x18000a2bc  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a2c3  nop     dword ptr [rax+rax+00h]
0x18000a2c8  jmp     loc_18000A41C
0x18000a2cd  lea     r8, [rbp+arg_0]
0x18000a2d1  lea     rdx, aWdsadminpack; "WdsAdminPack"
0x18000a2d8  lea     rcx, [rbp+arg_8]
0x18000a2dc  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000a2e3  nop     dword ptr [rax+rax+00h]
0x18000a2e8  mov     esi, eax
0x18000a2ea  mov     r9d, 171h
0x18000a2f0  mov     ecx, eax
0x18000a2f2  call    ElValidateWin32_2
0x18000a2f7  test    eax, eax
0x18000a2f9  jnz     loc_18000A177
0x18000a2ff  cmp     [rbp+arg_0], r14d
0x18000a303  jz      short loc_18000A30C
0x18000a305  or      dword ptr [rdi+84h], 1
0x18000a30c  lea     r8, [rbp+arg_0]
0x18000a310  lea     rdx, aWdstransportse; "WdsTransportServer"
0x18000a317  lea     rcx, [rbp+arg_8]
0x18000a31b  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000a322  nop     dword ptr [rax+rax+00h]
0x18000a327  mov     esi, eax
0x18000a329  mov     r9d, 17Dh
0x18000a32f  mov     ecx, eax
0x18000a331  call    ElValidateWin32_2
0x18000a336  test    eax, eax
0x18000a338  jnz     loc_18000A177
0x18000a33e  cmp     [rbp+arg_0], r14d
0x18000a342  jz      short loc_18000A34B
0x18000a344  or      dword ptr [rdi+84h], 2
0x18000a34b  lea     r8, [rbp+arg_0]
0x18000a34f  lea     rdx, aWdsdeployments; "WdsDeploymentServer"
0x18000a356  lea     rcx, [rbp+arg_8]
0x18000a35a  call    cs:__imp_?GetValueBool@CRegKey@@QEAAKPEBGPEAH@Z; CRegKey::GetValueBool(ushort const *,int *)
0x18000a361  nop     dword ptr [rax+rax+00h]
0x18000a366  mov     esi, eax
0x18000a368  mov     r9d, 189h
0x18000a36e  mov     ecx, eax
0x18000a370  call    ElValidateWin32_2
0x18000a375  test    eax, eax
0x18000a377  jnz     loc_18000A177
0x18000a37d  cmp     [rbp+arg_0], r14d
0x18000a381  jz      short loc_18000A38A
0x18000a383  or      dword ptr [rdi+84h], 4
0x18000a38a  lea     r9, [rdi+8Ch]
0x18000a391  xor     r8d, r8d
0x18000a394  lea     rdx, aWdstftpcapabil; "WdsTftpCapabilities"
0x18000a39b  lea     rcx, [rbp+arg_8]
0x18000a39f  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000a3a6  nop     dword ptr [rax+rax+00h]
0x18000a3ab  mov     esi, eax
0x18000a3ad  mov     r9d, 196h
0x18000a3b3  mov     ecx, eax
0x18000a3b5  call    ElValidateWin32_2
0x18000a3ba  test    eax, eax
0x18000a3bc  jz      short loc_18000A3D4
0x18000a3be  jmp     loc_18000A177
0x18000a3c3  mov     dword ptr [rdi+84h], 4
0x18000a3cd  mov     [rdi+8Ch], r14d
0x18000a3d4  test    byte ptr [rdi+84h], 2
0x18000a3db  jz      short loc_18000A415
0x18000a3dd  lea     r9, [rdi+88h]
0x18000a3e4  xor     r8d, r8d
0x18000a3e7  lea     rdx, aTransportproto; "TransportProtocols"
0x18000a3ee  lea     rcx, [rbp+var_20]
0x18000a3f2  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x18000a3f9  nop     dword ptr [rax+rax+00h]
0x18000a3fe  mov     esi, eax
0x18000a400  mov     r9d, 1BAh
0x18000a406  mov     ecx, eax
0x18000a408  call    ElValidateWin32_2
0x18000a40d  test    eax, eax
0x18000a40f  jnz     loc_18000A177
0x18000a415  mov     dword ptr [rdi+78h], 1
0x18000a41c  mov     rcx, [rbp+servername]
0x18000a420  test    rcx, rcx
0x18000a423  jz      short loc_18000A435
0x18000a425  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a42c  nop     dword ptr [rax+rax+00h]
0x18000a431  mov     [rbp+servername], r14
0x18000a435  mov     rcx, [rbp+bufptr]; Buffer
0x18000a439  test    rcx, rcx
0x18000a43c  jz      short loc_18000A44E
0x18000a43e  call    cs:__imp_NetApiBufferFree
0x18000a445  nop     dword ptr [rax+rax+00h]
0x18000a44a  mov     [rbp+bufptr], r14
0x18000a44e  mov     [rsp+50h+var_30], ebx
0x18000a452  mov     r9, rdi
0x18000a455  lea     r8, aCwdstransports_28; "<- CWdsTransportSetupManager::DelayInit"...
0x18000a45c  mov     edx, 10000h
0x18000a461  lea     rcx, qword_18003B770
0x18000a468  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000a46f  nop     dword ptr [rax+rax+00h]
0x18000a474  nop
0x18000a475  lea     rcx, [rbp+arg_8]; this
0x18000a479  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a47e  nop
0x18000a47f  lea     rcx, [rbp+var_20]; this
0x18000a483  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000a488  nop
0x18000a489  lea     rcx, [rbp+var_18]
0x18000a48d  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000a492  mov     eax, ebx
0x18000a494  add     rsp, 50h
0x18000a498  pop     r14
0x18000a49a  pop     rdi
0x18000a49b  pop     rsi
0x18000a49c  pop     rbx
0x18000a49d  pop     rbp
0x18000a49e  retn
```
