# CWdsService::ReadServerDuid(void)

- ea: `0x18000b1ec`
- end: `0x18000b4db`
- name: `?ReadServerDuid@CWdsService@@AEAAKXZ`
- size: `751`
- prototype: `unsigned int __fastcall(CWdsService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009da4`

## callees

- `0x180001984`
- `0x18000b1ec`
- `0x18000f0dc`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000b4bd`
- `KERNEL32!LeaveCriticalSection` at `0x18000b4bd`
- `KERNEL32!EnterCriticalSection` at `0x18000b20b`
- `KERNEL32!EnterCriticalSection` at `0x18000b20b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b251`
- `ADVAPI32!RegOpenKeyExW` at `0x18000b251`
- `ADVAPI32!RegCloseKey` at `0x18000b4a9`
- `ADVAPI32!RegCloseKey` at `0x18000b4a9`
- `ADVAPI32!RegQueryValueExW` at `0x18000b295`
- `ADVAPI32!RegQueryValueExW` at `0x18000b326`
- `ADVAPI32!RegQueryValueExW` at `0x18000b295`
- `ADVAPI32!RegQueryValueExW` at `0x18000b326`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000b473`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000b494`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000b473`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18000b494`
- `WdsServerCommonLib!?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z` at `0x18000b405`
- `WdsServerCommonLib!?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z` at `0x18000b405`
- `WdsServerCommonLib!?ParseDuid@@YAKPEBE_KPEAUtagDHCPV6_DUID@@@Z` at `0x18000b42e`
- `WdsServerCommonLib!?ParseDuid@@YAKPEBE_KPEAUtagDHCPV6_DUID@@@Z` at `0x18000b42e`

## string_xrefs

- `0x18000b21c`: `System\CurrentControlSet\Services\WDSServer\Parameters`
- `0x18000b2e3`: `Reading registry value %s: expected type REG_BINARY, got %u`
- `0x18000b35f`: `Registry value %s is empty`

## pseudocode

```c
__int64 __fastcall CWdsService::ReadServerDuid(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r14
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  DWORD v15; // eax
  void *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  void *v23; // rcx
  __int128 v25; // [rsp+30h] [rbp-20h] BYREF
  __int64 v26; // [rsp+40h] [rbp-10h]
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD Type; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF

  v1 = this + 1683;
  EnterCriticalSection(this + 1683);
  hKey = 0;
  Type = 0;
  cbData = 0;
  v26 = 0;
  v25 = 0;
  LODWORD(v3) = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Services\\WDSServer\\Parameters",
                  0,
                  0x20119u,
                  &hKey);
  if ( !(unsigned int)ElValidateWin32_0((unsigned int)v3, v4, v5, 1333) )
  {
    v6 = RegQueryValueExW(hKey, L"ServerDuid", 0, &Type, 0, 0);
    LODWORD(v3) = v6;
    if ( v6 != 2 && !(unsigned int)ElValidateWin32_0(v6, v7, v8, 1341) )
    {
      if ( Type == 3 )
        goto LABEL_8;
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x80000u, L"Reading registry value %s: expected type REG_BINARY, got %u", L"ServerDuid");
      LODWORD(v3) = 13;
      if ( !(unsigned int)ElValidateWin32_0(13, v9, v10, 1350) )
      {
LABEL_8:
        v3 = (unsigned int)RegQueryValueExW(hKey, L"ServerDuid", 0, 0, 0, &cbData);
        if ( !(unsigned int)ElValidateWin32_0(v3, v11, v12, 1355) )
        {
          v15 = cbData;
          if ( !cbData )
          {
            if ( g_ErrLibTraceFunctionEx )
              g_ErrLibTraceFunctionEx(0x80000u, L"Registry value %s is empty", L"ServerDuid");
            LODWORD(v3) = 13;
            if ( (unsigned int)ElValidateWin32_0(13, v13, v14, 1363) )
              goto LABEL_29;
            v15 = cbData;
          }
          if ( v15 <= 0x80 )
            goto LABEL_19;
          if ( g_ErrLibTraceFunctionEx )
            g_ErrLibTraceFunctionEx(
              0x80000u,
              L"Specified DHCPv6 server DUID is too long at %u bytes, %u max per RFC 3315",
              v15);
          LODWORD(v3) = 13;
          if ( !(unsigned int)ElValidateWin32_0(13, v13, v14, 1373) )
          {
            v15 = cbData;
LABEL_19:
            v16 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
            if ( v16 )
            {
              LODWORD(v3) = CRegKey::GetValue((CRegKey *)&hKey, L"ServerDuid", 3u, v16, cbData);
              if ( (unsigned int)ElValidateWin32_0((unsigned int)v3, v17, v18, 1383)
                || (LODWORD(v3) = ParseDuid((const unsigned __int8 *)v16, cbData, (struct tagDHCPV6_DUID *)&v25),
                    (unsigned int)ElValidateWin32_0((unsigned int)v3, v19, v20, 1386))
                || !DWORD1(v25) && (LODWORD(v3) = 13, (unsigned int)ElValidateWin32_0(13, v21, v22, 1391)) )
              {
                WdsPrivateHpFree(v16);
              }
              else
              {
                v23 = *(void **)&this[1684].LockCount;
                if ( v23 )
                  WdsPrivateHpFree(v23);
                LODWORD(this[1684].DebugInfo) = cbData;
                *(_QWORD *)&this[1684].LockCount = v16;
              }
            }
            else
            {
              LODWORD(v3) = 8;
            }
          }
        }
      }
    }
  }
LABEL_29:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b1ec  push    rbp
0x18000b1ee  push    rbx
0x18000b1ef  push    rsi
0x18000b1f0  push    rdi
0x18000b1f1  push    r12
0x18000b1f3  push    r13
0x18000b1f5  push    r14
0x18000b1f7  mov     rbp, rsp
0x18000b1fa  sub     rsp, 50h
0x18000b1fe  lea     r14, [rcx+106F8h]
0x18000b205  mov     rsi, rcx
0x18000b208  mov     rcx, r14; lpCriticalSection
0x18000b20b  call    cs:__imp_EnterCriticalSection
0x18000b212  nop     dword ptr [rax+rax+00h]
0x18000b217  and     [rbp+hKey], 0
0x18000b21c  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x18000b223  and     [rbp+Type], 0
0x18000b227  xor     eax, eax
0x18000b229  and     [rbp+cbData], 0
0x18000b22d  xorps   xmm0, xmm0
0x18000b230  mov     [rbp+var_10], rax
0x18000b234  mov     r9d, 20119h; samDesired
0x18000b23a  lea     rax, [rbp+hKey]
0x18000b23e  xor     r8d, r8d; ulOptions
0x18000b241  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b248  mov     [rsp+50h+phkResult], rax; lpData
0x18000b24d  movups  [rbp+var_20], xmm0
0x18000b251  call    cs:__imp_RegOpenKeyExW
0x18000b258  nop     dword ptr [rax+rax+00h]
0x18000b25d  mov     ecx, eax
0x18000b25f  mov     r9d, 535h
0x18000b265  mov     ebx, eax
0x18000b267  call    ElValidateWin32_0
0x18000b26c  test    eax, eax
0x18000b26e  jnz     loc_18000B4A0
0x18000b274  and     [rsp+50h+lpcbData], 0
0x18000b27a  lea     r13, ValueName; "ServerDuid"
0x18000b281  mov     rcx, [rbp+hKey]; hKey
0x18000b285  lea     r9, [rbp+Type]; lpType
0x18000b289  and     [rsp+50h+phkResult], 0
0x18000b28f  mov     rdx, r13; lpValueName
0x18000b292  xor     r8d, r8d; lpReserved
0x18000b295  call    cs:__imp_RegQueryValueExW
0x18000b29c  nop     dword ptr [rax+rax+00h]
0x18000b2a1  mov     ebx, eax
0x18000b2a3  cmp     eax, 2
0x18000b2a6  jz      loc_18000B4A0
0x18000b2ac  mov     r9d, 53Dh
0x18000b2b2  mov     ecx, eax
0x18000b2b4  call    ElValidateWin32_0
0x18000b2b9  test    eax, eax
0x18000b2bb  jnz     loc_18000B4A0
0x18000b2c1  mov     r9d, [rbp+Type]
0x18000b2c5  lea     r12d, [rax+0Dh]
0x18000b2c9  mov     edi, 80000h
0x18000b2ce  cmp     r9d, 3
0x18000b2d2  jz      short loc_18000B30A
0x18000b2d4  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000b2db  test    rax, rax
0x18000b2de  jz      short loc_18000B2F1
0x18000b2e0  mov     r8, r13
0x18000b2e3  lea     rdx, aReadingRegistr; "Reading registry value %s: expected typ"...
0x18000b2ea  mov     ecx, edi
0x18000b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2f1  mov     r9d, 546h
0x18000b2f7  mov     ecx, r12d
0x18000b2fa  mov     ebx, r12d
0x18000b2fd  call    ElValidateWin32_0
0x18000b302  test    eax, eax
0x18000b304  jnz     loc_18000B4A0
0x18000b30a  mov     rcx, [rbp+hKey]; hKey
0x18000b30e  lea     rax, [rbp+cbData]
0x18000b312  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000b317  xor     r9d, r9d; lpType
0x18000b31a  and     [rsp+50h+phkResult], 0
0x18000b320  xor     r8d, r8d; lpReserved
0x18000b323  mov     rdx, r13; lpValueName
0x18000b326  call    cs:__imp_RegQueryValueExW
0x18000b32d  nop     dword ptr [rax+rax+00h]
0x18000b332  mov     ecx, eax
0x18000b334  mov     r9d, 54Bh
0x18000b33a  mov     ebx, eax
0x18000b33c  call    ElValidateWin32_0
0x18000b341  test    eax, eax
0x18000b343  jnz     loc_18000B4A0
0x18000b349  mov     eax, [rbp+cbData]
0x18000b34c  test    eax, eax
0x18000b34e  jnz     short loc_18000B389
0x18000b350  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000b357  test    rax, rax
0x18000b35a  jz      short loc_18000B36D
0x18000b35c  mov     r8, r13
0x18000b35f  lea     rdx, aRegistryValueS; "Registry value %s is empty"
0x18000b366  mov     ecx, edi
0x18000b368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b36d  mov     r9d, 553h
0x18000b373  mov     ecx, r12d
0x18000b376  mov     ebx, r12d
0x18000b379  call    ElValidateWin32_0
0x18000b37e  test    eax, eax
0x18000b380  jnz     loc_18000B4A0
0x18000b386  mov     eax, [rbp+cbData]
0x18000b389  mov     r9d, 80h
0x18000b38f  cmp     eax, r9d
0x18000b392  jbe     short loc_18000B3D0
0x18000b394  mov     r10, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000b39b  test    r10, r10
0x18000b39e  jz      short loc_18000B3B4
0x18000b3a0  mov     r8d, eax
0x18000b3a3  lea     rdx, aSpecifiedDhcpv; "Specified DHCPv6 server DUID is too lon"...
0x18000b3aa  mov     rax, r10
0x18000b3ad  mov     ecx, edi
0x18000b3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3b4  mov     r9d, 55Dh
0x18000b3ba  mov     ecx, r12d
0x18000b3bd  mov     ebx, r12d
0x18000b3c0  call    ElValidateWin32_0
0x18000b3c5  test    eax, eax
0x18000b3c7  jnz     loc_18000B4A0
0x18000b3cd  mov     eax, [rbp+cbData]
0x18000b3d0  mov     ecx, eax; unsigned __int64
0x18000b3d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b3d9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000b3de  mov     rdi, rax
0x18000b3e1  test    rax, rax
0x18000b3e4  jnz     short loc_18000B3EE
0x18000b3e6  lea     ebx, [rax+8]
0x18000b3e9  jmp     loc_18000B4A0
0x18000b3ee  mov     eax, [rbp+cbData]
0x18000b3f1  lea     rcx, [rbp+hKey]
0x18000b3f5  mov     r9, rdi
0x18000b3f8  mov     dword ptr [rsp+50h+phkResult], eax
0x18000b3fc  mov     r8d, 3
0x18000b402  mov     rdx, r13
0x18000b405  call    cs:__imp_?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18000b40c  nop     dword ptr [rax+rax+00h]
0x18000b411  mov     ecx, eax
0x18000b413  mov     r9d, 567h
0x18000b419  mov     ebx, eax
0x18000b41b  call    ElValidateWin32_0
0x18000b420  test    eax, eax
0x18000b422  jnz     short loc_18000B491
0x18000b424  mov     edx, [rbp+cbData]
0x18000b427  lea     r8, [rbp+var_20]
0x18000b42b  mov     rcx, rdi
0x18000b42e  call    cs:__imp_?ParseDuid@@YAKPEBE_KPEAUtagDHCPV6_DUID@@@Z; ParseDuid(uchar const *,unsigned __int64,tagDHCPV6_DUID *)
0x18000b435  nop     dword ptr [rax+rax+00h]
0x18000b43a  mov     ecx, eax
0x18000b43c  mov     r9d, 56Ah
0x18000b442  mov     ebx, eax
0x18000b444  call    ElValidateWin32_0
0x18000b449  test    eax, eax
0x18000b44b  jnz     short loc_18000B491
0x18000b44d  cmp     dword ptr [rbp+var_20+4], eax
0x18000b450  jnz     short loc_18000B467
0x18000b452  mov     r9d, 56Fh
0x18000b458  mov     ecx, r12d
0x18000b45b  mov     ebx, r12d
0x18000b45e  call    ElValidateWin32_0
0x18000b463  test    eax, eax
0x18000b465  jnz     short loc_18000B491
0x18000b467  mov     rcx, [rsi+10728h]
0x18000b46e  test    rcx, rcx
0x18000b471  jz      short loc_18000B47F
0x18000b473  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000b47a  nop     dword ptr [rax+rax+00h]
0x18000b47f  mov     eax, [rbp+cbData]
0x18000b482  mov     [rsi+10720h], eax
0x18000b488  mov     [rsi+10728h], rdi
0x18000b48f  jmp     short loc_18000B4A0
0x18000b491  mov     rcx, rdi
0x18000b494  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18000b49b  nop     dword ptr [rax+rax+00h]
0x18000b4a0  mov     rcx, [rbp+hKey]; hKey
0x18000b4a4  test    rcx, rcx
0x18000b4a7  jz      short loc_18000B4BA
0x18000b4a9  call    cs:__imp_RegCloseKey
0x18000b4b0  nop     dword ptr [rax+rax+00h]
0x18000b4b5  and     [rbp+hKey], 0
0x18000b4ba  mov     rcx, r14; lpCriticalSection
0x18000b4bd  call    cs:__imp_LeaveCriticalSection
0x18000b4c4  nop     dword ptr [rax+rax+00h]
0x18000b4c9  mov     eax, ebx
0x18000b4cb  add     rsp, 50h
0x18000b4cf  pop     r14
0x18000b4d1  pop     r13
0x18000b4d3  pop     r12
0x18000b4d5  pop     rdi
0x18000b4d6  pop     rsi
0x18000b4d7  pop     rbx
0x18000b4d8  pop     rbp
0x18000b4d9  retn
```
