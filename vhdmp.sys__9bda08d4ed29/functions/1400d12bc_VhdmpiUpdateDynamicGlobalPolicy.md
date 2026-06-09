# VhdmpiUpdateDynamicGlobalPolicy

- ea: `0x1400d12bc`
- end: `0x1400d15bc`
- name: `VhdmpiUpdateDynamicGlobalPolicy`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b36d0`
- `0x1400c0730`
- `0x1400ee9dc`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x1400d10ac`
- `0x1400d10fc`
- `0x1400d11b8`
- `0x1400d12bc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400d1581`
- `ntoskrnl!ZwClose` at `0x1400d1596`
- `ntoskrnl!ZwClose` at `0x1400d1581`
- `ntoskrnl!ZwClose` at `0x1400d1596`

## string_xrefs

- `0x1400d1343`: `InternalConcurrentMirrorThreadCount`
- `0x1400d138a`: `InternalConcurrentMirrorMaxReaders`
- `0x1400d13e4`: `InternalConcurrentMirrorMaxWriters`
- `0x1400d155b`: `DisableMountOnCSV`
- `0x1400d1521`: `CacheNodeQuota`
- `0x1400d1423`: `EnableSMBCompression`

## pseudocode

```c
__int64 __fastcall VhdmpiUpdateDynamicGlobalPolicy(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  HANDLE v6; // rcx
  char v8; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v9[3]; // [rsp+21h] [rbp-2Fh] BYREF
  int v10; // [rsp+24h] [rbp-2Ch]
  int v11; // [rsp+28h] [rbp-28h]
  int v12; // [rsp+2Ch] [rbp-24h]
  int v13; // [rsp+30h] [rbp-20h]
  HANDLE Handle; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v15; // [rsp+40h] [rbp-10h] BYREF
  char v16; // [rsp+90h] [rbp+40h] BYREF
  char v17; // [rsp+98h] [rbp+48h] BYREF
  char v18; // [rsp+A0h] [rbp+50h] BYREF
  char v19; // [rsp+A8h] [rbp+58h] BYREF

  v16 = 0;
  v18 = 1;
  v19 = 1;
  v8 = 1;
  v17 = 0;
  v9[0] = 0;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  Handle = 0;
  v15 = 0;
  VhdmpiAcquirePassiveLock(a1);
  v2 = VhdmpiOpenGlobalPolicyKey(&v15, &Handle);
  if ( v2 >= 0 )
  {
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableSMBCompression", 0, &v16);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableLiveMigrationIrpTagging", 0, &v17);
    LOBYTE(v3) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableRefsSparseMigration", v3, &v18);
    LOBYTE(v4) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"PreserveAbcSparseMigration", v4, &v19);
    LOBYTE(v5) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableFileSystemAttributeOverrides", v5, &v8);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableExpansionNotification", 0, v9);
    v6 = Handle;
    *(_BYTE *)(a1 + 132) = v16;
    *(_BYTE *)(a1 + 133) = v17;
    *(_BYTE *)(a1 + 134) = v18;
    *(_BYTE *)(a1 + 135) = v19;
    *(_BYTE *)(a1 + 136) = v8;
    *(_BYTE *)(a1 + 137) = v9[0];
    *(_DWORD *)(a1 + 128) = 0x10000;
    *(_DWORD *)(a1 + 116) = 1;
    *(_DWORD *)(a1 + 120) = 1;
    *(_DWORD *)(a1 + 124) = 1;
    VhdmpiGetPolicyBOOLEAN(v6, L"AlwaysAllowSparseFiles", 0, a1 + 138);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableLiveDumpOnSurfaceCancel", 0, &byte_14008E3B4);
    VhdmpiGetPolicyBOOLEAN(Handle, L"DisableMountOnCSV", 0, a1 + 165);
    if ( *(_DWORD *)(a1 + 140) <= 0x100u || ((*(_DWORD *)(a1 + 140) - 1) & *(_DWORD *)(a1 + 140)) != 0 )
      *(_DWORD *)(a1 + 140) = 256;
    v2 = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v15 )
    ZwClose(v15);
  VhdmpiReleasePassiveLock(a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400d12bc  push    rbp
0x1400d12be  push    rbx
0x1400d12bf  push    rsi
0x1400d12c0  push    rdi
0x1400d12c1  push    r13
0x1400d12c3  push    r14
0x1400d12c5  push    r15
0x1400d12c7  mov     rbp, rsp
0x1400d12ca  sub     rsp, 50h
0x1400d12ce  mov     r13d, 1
0x1400d12d4  mov     [rbp+arg_0], 0
0x1400d12d8  mov     [rbp+arg_10], r13b
0x1400d12dc  mov     r15, rcx
0x1400d12df  mov     [rbp+arg_18], r13b
0x1400d12e3  mov     [rbp+var_30], r13b
0x1400d12e7  mov     [rbp+arg_8], 0
0x1400d12eb  mov     [rbp+var_2F], 0
0x1400d12ef  mov     [rbp+var_28], 0
0x1400d12f6  mov     [rbp+var_2C], 0
0x1400d12fd  mov     [rbp+var_24], 0
0x1400d1304  mov     [rbp+var_20], 0
0x1400d130b  mov     [rbp+Handle], 0
0x1400d1313  mov     [rbp+var_10], 0
0x1400d131b  call    VhdmpiAcquirePassiveLock
0x1400d1320  lea     rdx, [rbp+Handle]
0x1400d1324  lea     rcx, [rbp+var_10]
0x1400d1328  call    VhdmpiOpenGlobalPolicyKey
0x1400d132d  mov     ebx, eax
0x1400d132f  test    eax, eax
0x1400d1331  js      loc_1400D1578
0x1400d1337  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d133b  lea     r9, [rbp+var_2C]
0x1400d133f  lea     r8d, [r13+1]
0x1400d1343  lea     rdx, aInternalconcur_0; "InternalConcurrentMirrorThreadCount"
0x1400d134a  call    VhdmpiGetPolicyDWORD
0x1400d134f  mov     ebx, [rbp+var_2C]
0x1400d1352  lea     eax, [r13+3Fh]
0x1400d1356  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d135a  lea     r9, [rbp+var_28]
0x1400d135e  cmp     ebx, r13d
0x1400d1361  lea     rdx, aMirrorblocksiz; "MirrorBlockSize"
0x1400d1368  mov     edi, 800000h
0x1400d136d  cmovb   ebx, r13d
0x1400d1371  mov     r8d, edi
0x1400d1374  cmp     ebx, eax
0x1400d1376  cmova   ebx, eax
0x1400d1379  call    VhdmpiGetPolicyDWORD
0x1400d137e  mov     r14d, [rbp+var_28]
0x1400d1382  lea     r9, [rbp+var_24]
0x1400d1386  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d138a  lea     rdx, aInternalconcur; "InternalConcurrentMirrorMaxReaders"
0x1400d1391  mov     eax, 10000h
0x1400d1396  cmp     r14d, eax
0x1400d1399  cmovb   r14d, eax
0x1400d139d  cmp     r14d, edi
0x1400d13a0  cmova   r14d, edi
0x1400d13a4  lea     eax, [r14-1]
0x1400d13a8  test    r14d, eax
0x1400d13ab  cmovnz  r14d, edi
0x1400d13af  xor     r8d, r8d
0x1400d13b2  call    VhdmpiGetPolicyDWORD
0x1400d13b7  mov     edi, [rbp+var_24]
0x1400d13ba  test    edi, edi
0x1400d13bc  jnz     short loc_1400D13DA
0x1400d13be  cmp     ebx, 2
0x1400d13c1  jbe     short loc_1400D13D7
0x1400d13c3  lea     ecx, ds:2[rbx*2]
0x1400d13ca  mov     eax, 0AAAAAAABh
0x1400d13cf  mul     ecx
0x1400d13d1  mov     edi, edx
0x1400d13d3  shr     edi, 1
0x1400d13d5  jmp     short loc_1400D13DA
0x1400d13d7  mov     edi, r13d
0x1400d13da  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d13de  lea     r9, [rbp+var_20]
0x1400d13e2  cmp     edi, ebx
0x1400d13e4  lea     rdx, aInternalconcur_2; "InternalConcurrentMirrorMaxWriters"
0x1400d13eb  cmova   edi, ebx
0x1400d13ee  xor     r8d, r8d
0x1400d13f1  call    VhdmpiGetPolicyDWORD
0x1400d13f6  mov     esi, [rbp+var_20]
0x1400d13f9  test    esi, esi
0x1400d13fb  jnz     short loc_1400D1419
0x1400d13fd  cmp     ebx, 2
0x1400d1400  jbe     short loc_1400D1416
0x1400d1402  lea     ecx, ds:2[rbx*2]
0x1400d1409  mov     eax, 0AAAAAAABh
0x1400d140e  mul     ecx
0x1400d1410  mov     esi, edx
0x1400d1412  shr     esi, 1
0x1400d1414  jmp     short loc_1400D1419
0x1400d1416  mov     esi, r13d
0x1400d1419  mov     rcx, [rbp+Handle]
0x1400d141d  lea     r9, [rbp+arg_0]
0x1400d1421  cmp     esi, ebx
0x1400d1423  lea     rdx, aEnablesmbcompr; "EnableSMBCompression"
0x1400d142a  cmova   esi, ebx
0x1400d142d  xor     r8d, r8d
0x1400d1430  call    VhdmpiGetPolicyBOOLEAN
0x1400d1435  mov     rcx, [rbp+Handle]
0x1400d1439  lea     r9, [rbp+arg_8]
0x1400d143d  xor     r8d, r8d
0x1400d1440  lea     rdx, aEnablelivemigr; "EnableLiveMigrationIrpTagging"
0x1400d1447  call    VhdmpiGetPolicyBOOLEAN
0x1400d144c  mov     rcx, [rbp+Handle]
0x1400d1450  lea     r9, [rbp+arg_10]
0x1400d1454  mov     r8b, r13b
0x1400d1457  lea     rdx, aEnablerefsspar; "EnableRefsSparseMigration"
0x1400d145e  call    VhdmpiGetPolicyBOOLEAN
0x1400d1463  mov     rcx, [rbp+Handle]
0x1400d1467  lea     r9, [rbp+arg_18]
0x1400d146b  mov     r8b, r13b
0x1400d146e  lea     rdx, aPreserveabcspa; "PreserveAbcSparseMigration"
0x1400d1475  call    VhdmpiGetPolicyBOOLEAN
0x1400d147a  mov     rcx, [rbp+Handle]
0x1400d147e  lea     r9, [rbp+var_30]
0x1400d1482  mov     r8b, r13b
0x1400d1485  lea     rdx, aEnablefilesyst; "EnableFileSystemAttributeOverrides"
0x1400d148c  call    VhdmpiGetPolicyBOOLEAN
0x1400d1491  mov     rcx, [rbp+Handle]
0x1400d1495  lea     r9, [rbp+var_2F]
0x1400d1499  xor     r8d, r8d
0x1400d149c  lea     rdx, aEnableexpansio; "EnableExpansionNotification"
0x1400d14a3  call    VhdmpiGetPolicyBOOLEAN
0x1400d14a8  mov     al, [rbp+arg_0]
0x1400d14ab  lea     r9, [r15+8Ah]
0x1400d14b2  mov     rcx, [rbp+Handle]
0x1400d14b6  lea     rdx, aAlwaysallowspa; "AlwaysAllowSparseFiles"
0x1400d14bd  mov     [r15+84h], al
0x1400d14c4  xor     r8d, r8d
0x1400d14c7  mov     al, [rbp+arg_8]
0x1400d14ca  mov     [r15+85h], al
0x1400d14d1  mov     al, [rbp+arg_10]
0x1400d14d4  mov     [r15+86h], al
0x1400d14db  mov     al, [rbp+arg_18]
0x1400d14de  mov     [r15+87h], al
0x1400d14e5  mov     al, [rbp+var_30]
0x1400d14e8  mov     [r15+88h], al
0x1400d14ef  mov     al, [rbp+var_2F]
0x1400d14f2  mov     [r15+89h], al
0x1400d14f9  mov     [r15+80h], r14d
0x1400d1500  mov     [r15+74h], ebx
0x1400d1504  mov     [r15+78h], edi
0x1400d1508  mov     [r15+7Ch], esi
0x1400d150c  call    VhdmpiGetPolicyBOOLEAN
0x1400d1511  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d1515  lea     rbx, [r15+8Ch]
0x1400d151c  mov     edi, 100h
0x1400d1521  lea     rdx, aCachenodequota; "CacheNodeQuota"
0x1400d1528  mov     r9, rbx
0x1400d152b  mov     r8d, edi
0x1400d152e  call    VhdmpiGetPolicyDWORD
0x1400d1533  mov     rcx, [rbp+Handle]
0x1400d1537  lea     r9, byte_14008E3B4
0x1400d153e  xor     r8d, r8d
0x1400d1541  lea     rdx, aEnablelivedump; "EnableLiveDumpOnSurfaceCancel"
0x1400d1548  call    VhdmpiGetPolicyBOOLEAN
0x1400d154d  mov     rcx, [rbp+Handle]
0x1400d1551  lea     r9, [r15+0A5h]
0x1400d1558  xor     r8d, r8d
0x1400d155b  lea     rdx, aDisablemounton; "DisableMountOnCSV"
0x1400d1562  call    VhdmpiGetPolicyBOOLEAN
0x1400d1567  mov     ecx, [rbx]
0x1400d1569  cmp     ecx, edi
0x1400d156b  jbe     short loc_1400D1574
0x1400d156d  lea     eax, [rcx-1]
0x1400d1570  test    ecx, eax
0x1400d1572  jz      short loc_1400D1576
0x1400d1574  mov     [rbx], edi
0x1400d1576  xor     ebx, ebx
0x1400d1578  mov     rcx, [rbp+Handle]; Handle
0x1400d157c  test    rcx, rcx
0x1400d157f  jz      short loc_1400D158D
0x1400d1581  call    cs:__imp_ZwClose
0x1400d1588  nop     dword ptr [rax+rax+00h]
0x1400d158d  mov     rcx, [rbp+var_10]; Handle
0x1400d1591  test    rcx, rcx
0x1400d1594  jz      short loc_1400D15A2
0x1400d1596  call    cs:__imp_ZwClose
0x1400d159d  nop     dword ptr [rax+rax+00h]
0x1400d15a2  mov     rcx, r15
0x1400d15a5  call    VhdmpiReleasePassiveLock
0x1400d15aa  mov     eax, ebx
0x1400d15ac  add     rsp, 50h
0x1400d15b0  pop     r15
0x1400d15b2  pop     r14
0x1400d15b4  pop     r13
0x1400d15b6  pop     rdi
0x1400d15b7  pop     rsi
0x1400d15b8  pop     rbx
0x1400d15b9  pop     rbp
0x1400d15ba  retn
```
