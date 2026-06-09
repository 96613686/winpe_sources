# DrpEnumFileCallback(void *,ushort const *,ulong)

- ea: `0x180004680`
- end: `0x1800047df`
- name: `?DrpEnumFileCallback@@YAKPEAXPEBGK@Z`
- size: `351`
- prototype: `__int64 __fastcall(_DWORD *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800020d0`
- `0x1800022c4`
- `0x180004680`
- `0x18001b7b0`

## import_xrefs

- `setupapi!PnpIsFileContentIntact` at `0x1800046c2`
- `setupapi!PnpIsFileContentIntact` at `0x1800046c2`
- `setupapi!PnpRepairWindowsProtectedDriver` at `0x180004758`
- `setupapi!PnpRepairWindowsProtectedDriver` at `0x180004758`

## string_xrefs

- `0x1800047a4`: `[Pnp] Repaired file: {0}`
- `0x180004777`: `[Pnp] Failed repairing file: {0}`

## pseudocode

```c
__int64 __fastcall DrpEnumFileCallback(_DWORD *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v4; // rdx
  int IsFileContentIntact; // edi
  struct LogAdapter::Logger *v6; // rcx
  const char *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+30h] [rbp-30h] BYREF
  int *v14; // [rsp+38h] [rbp-28h] BYREF
  const unsigned __int16 *v15; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+48h] [rbp-18h] BYREF

  v15 = a2;
  if ( a3 == 1 )
  {
    v16 = 0;
    IsFileContentIntact = PnpIsFileContentIntact(a2, &v16);
    if ( IsFileContentIntact )
    {
      v6 = LogAdapter::g_Logger;
      if ( LogAdapter::g_Logger )
      {
        v7 = "[Pnp] Failed verifying file: {0}";
LABEL_5:
        LogAdapter::Logger::LogNumObjects<unsigned short *>(v6, 0, 3, v7, &v15);
        v13 = IsFileContentIntact;
        v14 = &v13;
        LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(v8, 3, v9, &v14);
      }
    }
    else if ( !v16 )
    {
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v4) = 1;
        LogAdapter::Logger::LogNumObjects<unsigned short *>(
          LogAdapter::g_Logger,
          v4,
          1,
          "[Pnp] Corrupt file: {0}",
          &v15);
      }
      ++a1[2];
      if ( *a1 )
      {
        v10 = PnpRepairWindowsProtectedDriver(v15);
        IsFileContentIntact = v10;
        if ( v10 && v10 != 3010 )
        {
          v6 = LogAdapter::g_Logger;
          if ( !LogAdapter::g_Logger )
            return 0;
          v7 = "[Pnp] Failed repairing file: {0}";
          goto LABEL_5;
        }
        ++a1[3];
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v11) = 1;
          LogAdapter::Logger::LogNumObjects<unsigned short *>(
            LogAdapter::g_Logger,
            v11,
            1,
            "[Pnp] Repaired file: {0}",
            &v15);
        }
        if ( IsFileContentIntact == 3010 )
          a1[1] = 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004680  mov     [rsp-8+arg_10], rbx
0x180004685  mov     [rsp-8+arg_18], rdi
0x18000468a  push    rbp
0x18000468b  mov     rbp, rsp
0x18000468e  sub     rsp, 60h
0x180004692  mov     rax, cs:__security_cookie
0x180004699  xor     rax, rsp
0x18000469c  mov     [rbp+var_10], rax
0x1800046a0  mov     [rbp+var_20], rdx
0x1800046a4  mov     rax, rdx
0x1800046a7  mov     rbx, rcx
0x1800046aa  cmp     r8d, 1
0x1800046ae  jnz     loc_1800047BF
0x1800046b4  lea     rdx, [rbp+var_18]
0x1800046b8  mov     [rbp+var_18], 0
0x1800046bf  mov     rcx, rax
0x1800046c2  call    cs:__imp_PnpIsFileContentIntact
0x1800046c8  mov     edi, eax
0x1800046ca  test    eax, eax
0x1800046cc  jz      short loc_180004718
0x1800046ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800046d5  test    rcx, rcx
0x1800046d8  jz      loc_1800047BF
0x1800046de  lea     r9, aPnpFailedVerif; "[Pnp] Failed verifying file: {0}"
0x1800046e5  lea     rax, [rbp+var_20]
0x1800046e9  mov     ebx, 3
0x1800046ee  mov     r8d, ebx
0x1800046f1  mov     [rsp+60h+var_40], rax
0x1800046f6  xor     edx, edx
0x1800046f8  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x1800046fd  lea     rax, [rbp+var_30]
0x180004701  mov     [rbp+var_30], edi
0x180004704  lea     r9, [rbp+var_28]
0x180004708  mov     [rbp+var_28], rax
0x18000470c  mov     edx, ebx
0x18000470e  call    ??$Log@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::Log<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x180004713  jmp     loc_1800047BF
0x180004718  cmp     [rbp+var_18], 0
0x18000471c  jnz     loc_1800047BF
0x180004722  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180004729  test    rcx, rcx
0x18000472c  jz      short loc_18000474C
0x18000472e  mov     r8d, 1
0x180004734  lea     rax, [rbp+var_20]
0x180004738  mov     dl, r8b
0x18000473b  mov     [rsp+60h+var_40], rax
0x180004740  lea     r9, aPnpCorruptFile; "[Pnp] Corrupt file: {0}"
0x180004747  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x18000474c  inc     dword ptr [rbx+8]
0x18000474f  cmp     dword ptr [rbx], 0
0x180004752  jz      short loc_1800047BF
0x180004754  mov     rcx, [rbp+var_20]
0x180004758  call    cs:__imp_PnpRepairWindowsProtectedDriver
0x18000475e  mov     edi, eax
0x180004760  test    eax, eax
0x180004762  jz      short loc_180004783
0x180004764  cmp     eax, 0BC2h
0x180004769  jz      short loc_180004783
0x18000476b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180004772  test    rcx, rcx
0x180004775  jz      short loc_1800047BF
0x180004777  lea     r9, aPnpFailedRepai; "[Pnp] Failed repairing file: {0}"
0x18000477e  jmp     loc_1800046E5
0x180004783  inc     dword ptr [rbx+0Ch]
0x180004786  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18000478d  test    rcx, rcx
0x180004790  jz      short loc_1800047B0
0x180004792  mov     r8d, 1
0x180004798  lea     rax, [rbp+var_20]
0x18000479c  mov     dl, r8b
0x18000479f  mov     [rsp+60h+var_40], rax
0x1800047a4  lea     r9, aPnpRepairedFil; "[Pnp] Repaired file: {0}"
0x1800047ab  call    ??$LogNumObjects@PEAG@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEAG@Z; LogAdapter::Logger::LogNumObjects<ushort *>(bool,LogAdapter::LogLevel,char const * const,ushort * const &)
0x1800047b0  cmp     edi, 0BC2h
0x1800047b6  jnz     short loc_1800047BF
0x1800047b8  mov     dword ptr [rbx+4], 1
0x1800047bf  xor     eax, eax
0x1800047c1  mov     rcx, [rbp+var_10]
0x1800047c5  xor     rcx, rsp; StackCookie
0x1800047c8  call    __security_check_cookie
0x1800047cd  lea     r11, [rsp+60h+var_s0]
0x1800047d2  mov     rbx, [r11+20h]
0x1800047d6  mov     rdi, [r11+28h]
0x1800047da  mov     rsp, r11
0x1800047dd  pop     rbp
0x1800047de  retn
```
