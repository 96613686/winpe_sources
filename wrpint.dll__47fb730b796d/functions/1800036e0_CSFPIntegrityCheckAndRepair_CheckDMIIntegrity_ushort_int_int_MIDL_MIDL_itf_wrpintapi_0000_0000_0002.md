# CSFPIntegrityCheckAndRepair::CheckDMIIntegrity(ushort *,int,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *)

- ea: `0x1800036e0`
- end: `0x1800038d5`
- name: `?CheckDMIIntegrity@CSFPIntegrityCheckAndRepair@@EEAAJPEAGHPEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, unsigned __int16 *, int, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800020d0`
- `0x1800022c4`
- `0x1800036e0`
- `0x18001b7b0`

## import_xrefs

- `setupapi!PnpEnumDrpFile` at `0x180003883`
- `setupapi!PnpEnumDrpFile` at `0x180003883`
- `setupapi!PnpIsFileContentIntact` at `0x180003724`
- `setupapi!PnpIsFileContentIntact` at `0x180003724`
- `setupapi!PnpRepairWindowsProtectedDriver` at `0x1800037c9`
- `setupapi!PnpRepairWindowsProtectedDriver` at `0x1800037c9`

## string_xrefs

- `0x180003803`: `[Pnp] Repaired file: {0}`
- `0x180003840`: `[Pnp] Failed repairing file: {0}`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckDMIIntegrity(
        CSFPIntegrityCheckAndRepair *this,
        unsigned __int16 *a2,
        int a3,
        int *a4,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a5)
{
  __int64 v7; // rdx
  int IsFileContentIntact; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  struct LogAdapter::Logger *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  int v19; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-28h] BYREF
  int v21; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v22[12]; // [rsp+48h] [rbp-18h] BYREF
  int v23; // [rsp+54h] [rbp-Ch]

  v20 = a2;
  v21 = 0;
  if ( !a2 )
  {
    *(_DWORD *)v22 = a3;
    *(_QWORD *)&v22[4] = 0;
    v23 = 0;
    v17 = PnpEnumDrpFile(v22, DrpEnumFileCallback);
    IsFileContentIntact = v17;
    if ( v17 && v17 != 259 )
    {
      if ( v17 <= 0 )
        return (unsigned int)IsFileContentIntact;
      IsFileContentIntact = (unsigned __int16)v17;
      goto LABEL_7;
    }
    *(_DWORD *)a5 += *(_DWORD *)&v22[8];
    *((_DWORD *)a5 + 1) += v23;
    if ( !*(_DWORD *)&v22[4] )
      return 0;
LABEL_25:
    *a4 = 1;
    return 0;
  }
  IsFileContentIntact = PnpIsFileContentIntact(a2, &v21);
  if ( !IsFileContentIntact )
  {
    if ( v21 )
      return 0;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<unsigned short *>(LogAdapter::g_Logger, v7, 1, "[Pnp] Corrupt file: {0}", &v20);
    }
    ++*(_DWORD *)a5;
    if ( !a3 )
      return 0;
    v11 = PnpRepairWindowsProtectedDriver(v20);
    v13 = v11;
    if ( v11 )
    {
      if ( v11 != 3010 )
        return 0;
    }
    ++*((_DWORD *)a5 + 1);
    v14 = LogAdapter::g_Logger;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<unsigned short *>(
        LogAdapter::g_Logger,
        v12,
        1,
        "[Pnp] Repaired file: {0}",
        &v20);
      v14 = LogAdapter::g_Logger;
    }
    if ( v13 != 3010 )
    {
      if ( v13 && v14 )
      {
        LogAdapter::Logger::LogNumObjects<unsigned short *>(v14, 0, 3, "[Pnp] Failed repairing file: {0}", &v20);
        v19 = v13;
        *(_QWORD *)v22 = &v19;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(v15, 3, v16, v22);
      }
      return 0;
    }
    goto LABEL_25;
  }
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<unsigned short *>(
      LogAdapter::g_Logger,
      0,
      3,
      "[Pnp] Failed verifying file: {0}",
      &v20);
    v19 = IsFileContentIntact;
    *(_QWORD *)v22 = &v19;
    LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(v9, 3, v10, v22);
  }
  if ( IsFileContentIntact > 0 )
  {
    IsFileContentIntact = (unsigned __int16)IsFileContentIntact;
LABEL_7:
    IsFileContentIntact |= 0x80070000;
  }
  return (unsigned int)IsFileContentIntact;
}

```

## disassembly

```asm
0x1800036e0  push    rbp
0x1800036e2  push    rbx
0x1800036e3  push    rsi
0x1800036e4  push    rdi
0x1800036e5  push    r14
0x1800036e7  mov     rbp, rsp
0x1800036ea  sub     rsp, 60h
0x1800036ee  mov     rax, cs:__security_cookie
0x1800036f5  xor     rax, rsp
0x1800036f8  mov     [rbp+var_8], rax
0x1800036fc  mov     rdi, [rbp+arg_20]
0x180003700  mov     r14, r9
0x180003703  mov     [rbp+var_28], rdx
0x180003707  mov     esi, r8d
0x18000370a  mov     [rbp+var_20], 0
0x180003711  mov     rax, rdx
0x180003714  test    rdx, rdx
0x180003717  jz      loc_180003866
0x18000371d  lea     rdx, [rbp+var_20]
0x180003721  mov     rcx, rax
0x180003724  call    cs:__imp_PnpIsFileContentIntact
0x18000372a  mov     ebx, eax
0x18000372c  test    eax, eax
0x18000372e  jz      short loc_180003787
0x180003730  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180003737  test    rcx, rcx
0x18000373a  jz      short loc_180003771
0x18000373c  lea     rax, [rbp+var_28]
0x180003740  mov     edi, 3
0x180003745  mov     r8d, edi
0x180003748  mov     [rsp+60h+var_40], rax
0x18000374d  lea     r9, aPnpFailedVerif; "[Pnp] Failed verifying file: {0}"
0x180003754  xor     edx, edx
0x180003756  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x18000375b  lea     rax, [rbp+var_30]
0x18000375f  mov     [rbp+var_30], ebx
0x180003762  lea     r9, [rbp+var_18]
0x180003766  mov     [rbp+var_18], rax
0x18000376a  mov     edx, edi
0x18000376c  call    ??$Log@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x180003771  test    ebx, ebx
0x180003773  jle     loc_1800038BC
0x180003779  movzx   ebx, bx
0x18000377c  or      ebx, 80070000h
0x180003782  jmp     loc_1800038BC
0x180003787  cmp     [rbp+var_20], 0
0x18000378b  jnz     loc_1800038BA
0x180003791  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180003798  test    rcx, rcx
0x18000379b  jz      short loc_1800037BB
0x18000379d  mov     r8d, 1
0x1800037a3  lea     rax, [rbp+var_28]
0x1800037a7  mov     dl, r8b
0x1800037aa  mov     [rsp+60h+var_40], rax
0x1800037af  lea     r9, aPnpCorruptFile; "[Pnp] Corrupt file: {0}"
0x1800037b6  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x1800037bb  inc     dword ptr [rdi]
0x1800037bd  test    esi, esi
0x1800037bf  jz      loc_1800038BA
0x1800037c5  mov     rcx, [rbp+var_28]
0x1800037c9  call    cs:__imp_PnpRepairWindowsProtectedDriver
0x1800037cf  mov     ebx, eax
0x1800037d1  mov     esi, 0BC2h
0x1800037d6  test    eax, eax
0x1800037d8  jz      short loc_1800037E2
0x1800037da  cmp     eax, esi
0x1800037dc  jnz     loc_1800038BA
0x1800037e2  inc     dword ptr [rdi+4]
0x1800037e5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800037ec  test    rcx, rcx
0x1800037ef  jz      short loc_180003816
0x1800037f1  mov     r8d, 1
0x1800037f7  lea     rax, [rbp+var_28]
0x1800037fb  mov     dl, r8b
0x1800037fe  mov     [rsp+60h+var_40], rax
0x180003803  lea     r9, aPnpRepairedFil; "[Pnp] Repaired file: {0}"
0x18000380a  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x18000380f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180003816  cmp     ebx, esi
0x180003818  jz      loc_1800038B3
0x18000381e  test    ebx, ebx
0x180003820  jz      loc_1800038BA
0x180003826  test    rcx, rcx
0x180003829  jz      loc_1800038BA
0x18000382f  lea     rax, [rbp+var_28]
0x180003833  mov     edi, 3
0x180003838  mov     r8d, edi
0x18000383b  mov     [rsp+60h+var_40], rax
0x180003840  lea     r9, aPnpFailedRepai; "[Pnp] Failed repairing file: {0}"
0x180003847  xor     edx, edx
0x180003849  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x18000384e  lea     rax, [rbp+var_30]
0x180003852  mov     [rbp+var_30], ebx
0x180003855  lea     r9, [rbp+var_18]
0x180003859  mov     [rbp+var_18], rax
0x18000385d  mov     edx, edi
0x18000385f  call    ??$Log@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x180003864  jmp     short loc_1800038BA
0x180003866  lea     rdx, ?DrpEnumFileCallback@@YAKPEAXPEBGK@Z; DrpEnumFileCallback(void *,ushort const *,ulong)
0x18000386d  mov     dword ptr [rbp+var_18], esi
0x180003870  lea     rcx, [rbp+var_18]
0x180003874  mov     [rbp+var_18+4], 0
0x18000387c  mov     [rbp+var_C], 0
0x180003883  call    cs:__imp_PnpEnumDrpFile
0x180003889  mov     ebx, eax
0x18000388b  test    eax, eax
0x18000388d  jz      short loc_1800038A2
0x18000388f  cmp     eax, 103h
0x180003894  jz      short loc_1800038A2
0x180003896  test    eax, eax
0x180003898  jle     short loc_1800038BC
0x18000389a  movzx   ebx, ax
0x18000389d  jmp     loc_18000377C
0x1800038a2  mov     eax, [rbp+var_10]
0x1800038a5  add     [rdi], eax
0x1800038a7  mov     eax, [rbp+var_C]
0x1800038aa  add     [rdi+4], eax
0x1800038ad  cmp     dword ptr [rbp+var_18+4], 0
0x1800038b1  jz      short loc_1800038BA
0x1800038b3  mov     dword ptr [r14], 1
0x1800038ba  xor     ebx, ebx
0x1800038bc  mov     eax, ebx
0x1800038be  mov     rcx, [rbp+var_8]
0x1800038c2  xor     rcx, rsp; StackCookie
0x1800038c5  call    __security_check_cookie
0x1800038ca  add     rsp, 60h
0x1800038ce  pop     r14
0x1800038d0  pop     rdi
0x1800038d1  pop     rsi
0x1800038d2  pop     rbx
0x1800038d3  pop     rbp
0x1800038d4  retn
```
