# VhdmpiUpdateDynamicGlobalPolicy

- ea: `0x1400d132c`
- end: `0x1400d162c`
- name: `VhdmpiUpdateDynamicGlobalPolicy`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b36d0`
- `0x1400c0740`
- `0x1400ee9dc`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x1400d111c`
- `0x1400d116c`
- `0x1400d1228`
- `0x1400d132c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400d15f1`
- `ntoskrnl!ZwClose` at `0x1400d1606`
- `ntoskrnl!ZwClose` at `0x1400d15f1`
- `ntoskrnl!ZwClose` at `0x1400d1606`

## string_xrefs

- `0x1400d13fa`: `InternalConcurrentMirrorMaxReaders`
- `0x1400d1454`: `InternalConcurrentMirrorMaxWriters`
- `0x1400d1493`: `EnableSMBCompression`
- `0x1400d13b3`: `InternalConcurrentMirrorThreadCount`
- `0x1400d15cb`: `DisableMountOnCSV`
- `0x1400d1591`: `CacheNodeQuota`

## pseudocode

```c
__int64 __fastcall VhdmpiUpdateDynamicGlobalPolicy(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // ebx
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  HANDLE v8; // rcx
  char v10; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v11[3]; // [rsp+21h] [rbp-2Fh] BYREF
  int v12; // [rsp+24h] [rbp-2Ch]
  int v13; // [rsp+28h] [rbp-28h]
  int v14; // [rsp+2Ch] [rbp-24h]
  int v15; // [rsp+30h] [rbp-20h]
  HANDLE Handle; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v17; // [rsp+40h] [rbp-10h] BYREF
  char v18; // [rsp+90h] [rbp+40h] BYREF
  char v19; // [rsp+98h] [rbp+48h] BYREF
  char v20; // [rsp+A0h] [rbp+50h] BYREF
  char v21; // [rsp+A8h] [rbp+58h] BYREF

  v18 = 0;
  v20 = 1;
  v21 = 1;
  v10 = 1;
  v19 = 0;
  v11[0] = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  Handle = 0;
  v17 = 0;
  VhdmpiAcquirePassiveLock(a1, a2, a3);
  v4 = VhdmpiOpenGlobalPolicyKey(&v17, &Handle);
  if ( v4 >= 0 )
  {
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableSMBCompression", 0, &v18);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableLiveMigrationIrpTagging", 0, &v19);
    LOBYTE(v5) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableRefsSparseMigration", v5, &v20);
    LOBYTE(v6) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"PreserveAbcSparseMigration", v6, &v21);
    LOBYTE(v7) = 1;
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableFileSystemAttributeOverrides", v7, &v10);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableExpansionNotification", 0, v11);
    v8 = Handle;
    *(_BYTE *)(a1 + 132) = v18;
    *(_BYTE *)(a1 + 133) = v19;
    *(_BYTE *)(a1 + 134) = v20;
    *(_BYTE *)(a1 + 135) = v21;
    *(_BYTE *)(a1 + 136) = v10;
    *(_BYTE *)(a1 + 137) = v11[0];
    *(_DWORD *)(a1 + 128) = 0x10000;
    *(_DWORD *)(a1 + 116) = 1;
    *(_DWORD *)(a1 + 120) = 1;
    *(_DWORD *)(a1 + 124) = 1;
    VhdmpiGetPolicyBOOLEAN(v8, L"AlwaysAllowSparseFiles", 0, a1 + 138);
    VhdmpiGetPolicyDWORD(Handle);
    VhdmpiGetPolicyBOOLEAN(Handle, L"EnableLiveDumpOnSurfaceCancel", 0, &byte_14008E3B4);
    VhdmpiGetPolicyBOOLEAN(Handle, L"DisableMountOnCSV", 0, a1 + 165);
    if ( *(_DWORD *)(a1 + 140) <= 0x100u || ((*(_DWORD *)(a1 + 140) - 1) & *(_DWORD *)(a1 + 140)) != 0 )
      *(_DWORD *)(a1 + 140) = 256;
    v4 = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v17 )
    ZwClose(v17);
  VhdmpiReleasePassiveLock(a1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400d132c  push    rbp
0x1400d132e  push    rbx
0x1400d132f  push    rsi
0x1400d1330  push    rdi
0x1400d1331  push    r13
0x1400d1333  push    r14
0x1400d1335  push    r15
0x1400d1337  mov     rbp, rsp
0x1400d133a  sub     rsp, 50h
0x1400d133e  mov     r13d, 1
0x1400d1344  mov     [rbp+arg_0], 0
0x1400d1348  mov     [rbp+arg_10], r13b
0x1400d134c  mov     r15, rcx
0x1400d134f  mov     [rbp+arg_18], r13b
0x1400d1353  mov     [rbp+var_30], r13b
0x1400d1357  mov     [rbp+arg_8], 0
0x1400d135b  mov     [rbp+var_2F], 0
0x1400d135f  mov     [rbp+var_28], 0
0x1400d1366  mov     [rbp+var_2C], 0
0x1400d136d  mov     [rbp+var_24], 0
0x1400d1374  mov     [rbp+var_20], 0
0x1400d137b  mov     [rbp+Handle], 0
0x1400d1383  mov     [rbp+var_10], 0
0x1400d138b  call    VhdmpiAcquirePassiveLock
0x1400d1390  lea     rdx, [rbp+Handle]
0x1400d1394  lea     rcx, [rbp+var_10]
0x1400d1398  call    VhdmpiOpenGlobalPolicyKey
0x1400d139d  mov     ebx, eax
0x1400d139f  test    eax, eax
0x1400d13a1  js      loc_1400D15E8
0x1400d13a7  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d13ab  lea     r9, [rbp+var_2C]
0x1400d13af  lea     r8d, [r13+1]
0x1400d13b3  lea     rdx, aInternalconcur_0; "InternalConcurrentMirrorThreadCount"
0x1400d13ba  call    VhdmpiGetPolicyDWORD
0x1400d13bf  mov     ebx, [rbp+var_2C]
0x1400d13c2  lea     eax, [r13+3Fh]
0x1400d13c6  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d13ca  lea     r9, [rbp+var_28]
0x1400d13ce  cmp     ebx, r13d
0x1400d13d1  lea     rdx, aMirrorblocksiz; "MirrorBlockSize"
0x1400d13d8  mov     edi, 800000h
0x1400d13dd  cmovb   ebx, r13d
0x1400d13e1  mov     r8d, edi
0x1400d13e4  cmp     ebx, eax
0x1400d13e6  cmova   ebx, eax
0x1400d13e9  call    VhdmpiGetPolicyDWORD
0x1400d13ee  mov     r14d, [rbp+var_28]
0x1400d13f2  lea     r9, [rbp+var_24]
0x1400d13f6  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d13fa  lea     rdx, aInternalconcur; "InternalConcurrentMirrorMaxReaders"
0x1400d1401  mov     eax, 10000h
0x1400d1406  cmp     r14d, eax
0x1400d1409  cmovb   r14d, eax
0x1400d140d  cmp     r14d, edi
0x1400d1410  cmova   r14d, edi
0x1400d1414  lea     eax, [r14-1]
0x1400d1418  test    r14d, eax
0x1400d141b  cmovnz  r14d, edi
0x1400d141f  xor     r8d, r8d
0x1400d1422  call    VhdmpiGetPolicyDWORD
0x1400d1427  mov     edi, [rbp+var_24]
0x1400d142a  test    edi, edi
0x1400d142c  jnz     short loc_1400D144A
0x1400d142e  cmp     ebx, 2
0x1400d1431  jbe     short loc_1400D1447
0x1400d1433  lea     ecx, ds:2[rbx*2]
0x1400d143a  mov     eax, 0AAAAAAABh
0x1400d143f  mul     ecx
0x1400d1441  mov     edi, edx
0x1400d1443  shr     edi, 1
0x1400d1445  jmp     short loc_1400D144A
0x1400d1447  mov     edi, r13d
0x1400d144a  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d144e  lea     r9, [rbp+var_20]
0x1400d1452  cmp     edi, ebx
0x1400d1454  lea     rdx, aInternalconcur_2; "InternalConcurrentMirrorMaxWriters"
0x1400d145b  cmova   edi, ebx
0x1400d145e  xor     r8d, r8d
0x1400d1461  call    VhdmpiGetPolicyDWORD
0x1400d1466  mov     esi, [rbp+var_20]
0x1400d1469  test    esi, esi
0x1400d146b  jnz     short loc_1400D1489
0x1400d146d  cmp     ebx, 2
0x1400d1470  jbe     short loc_1400D1486
0x1400d1472  lea     ecx, ds:2[rbx*2]
0x1400d1479  mov     eax, 0AAAAAAABh
0x1400d147e  mul     ecx
0x1400d1480  mov     esi, edx
0x1400d1482  shr     esi, 1
0x1400d1484  jmp     short loc_1400D1489
0x1400d1486  mov     esi, r13d
0x1400d1489  mov     rcx, [rbp+Handle]
0x1400d148d  lea     r9, [rbp+arg_0]
0x1400d1491  cmp     esi, ebx
0x1400d1493  lea     rdx, aEnablesmbcompr; "EnableSMBCompression"
0x1400d149a  cmova   esi, ebx
0x1400d149d  xor     r8d, r8d
0x1400d14a0  call    VhdmpiGetPolicyBOOLEAN
0x1400d14a5  mov     rcx, [rbp+Handle]
0x1400d14a9  lea     r9, [rbp+arg_8]
0x1400d14ad  xor     r8d, r8d
0x1400d14b0  lea     rdx, aEnablelivemigr; "EnableLiveMigrationIrpTagging"
0x1400d14b7  call    VhdmpiGetPolicyBOOLEAN
0x1400d14bc  mov     rcx, [rbp+Handle]
0x1400d14c0  lea     r9, [rbp+arg_10]
0x1400d14c4  mov     r8b, r13b
0x1400d14c7  lea     rdx, aEnablerefsspar; "EnableRefsSparseMigration"
0x1400d14ce  call    VhdmpiGetPolicyBOOLEAN
0x1400d14d3  mov     rcx, [rbp+Handle]
0x1400d14d7  lea     r9, [rbp+arg_18]
0x1400d14db  mov     r8b, r13b
0x1400d14de  lea     rdx, aPreserveabcspa; "PreserveAbcSparseMigration"
0x1400d14e5  call    VhdmpiGetPolicyBOOLEAN
0x1400d14ea  mov     rcx, [rbp+Handle]
0x1400d14ee  lea     r9, [rbp+var_30]
0x1400d14f2  mov     r8b, r13b
0x1400d14f5  lea     rdx, aEnablefilesyst; "EnableFileSystemAttributeOverrides"
0x1400d14fc  call    VhdmpiGetPolicyBOOLEAN
0x1400d1501  mov     rcx, [rbp+Handle]
0x1400d1505  lea     r9, [rbp+var_2F]
0x1400d1509  xor     r8d, r8d
0x1400d150c  lea     rdx, aEnableexpansio; "EnableExpansionNotification"
0x1400d1513  call    VhdmpiGetPolicyBOOLEAN
0x1400d1518  mov     al, [rbp+arg_0]
0x1400d151b  lea     r9, [r15+8Ah]
0x1400d1522  mov     rcx, [rbp+Handle]
0x1400d1526  lea     rdx, aAlwaysallowspa; "AlwaysAllowSparseFiles"
0x1400d152d  mov     [r15+84h], al
0x1400d1534  xor     r8d, r8d
0x1400d1537  mov     al, [rbp+arg_8]
0x1400d153a  mov     [r15+85h], al
0x1400d1541  mov     al, [rbp+arg_10]
0x1400d1544  mov     [r15+86h], al
0x1400d154b  mov     al, [rbp+arg_18]
0x1400d154e  mov     [r15+87h], al
0x1400d1555  mov     al, [rbp+var_30]
0x1400d1558  mov     [r15+88h], al
0x1400d155f  mov     al, [rbp+var_2F]
0x1400d1562  mov     [r15+89h], al
0x1400d1569  mov     [r15+80h], r14d
0x1400d1570  mov     [r15+74h], ebx
0x1400d1574  mov     [r15+78h], edi
0x1400d1578  mov     [r15+7Ch], esi
0x1400d157c  call    VhdmpiGetPolicyBOOLEAN
0x1400d1581  mov     rcx, [rbp+Handle]; KeyHandle
0x1400d1585  lea     rbx, [r15+8Ch]
0x1400d158c  mov     edi, 100h
0x1400d1591  lea     rdx, aCachenodequota; "CacheNodeQuota"
0x1400d1598  mov     r9, rbx
0x1400d159b  mov     r8d, edi
0x1400d159e  call    VhdmpiGetPolicyDWORD
0x1400d15a3  mov     rcx, [rbp+Handle]
0x1400d15a7  lea     r9, byte_14008E3B4
0x1400d15ae  xor     r8d, r8d
0x1400d15b1  lea     rdx, aEnablelivedump; "EnableLiveDumpOnSurfaceCancel"
0x1400d15b8  call    VhdmpiGetPolicyBOOLEAN
0x1400d15bd  mov     rcx, [rbp+Handle]
0x1400d15c1  lea     r9, [r15+0A5h]
0x1400d15c8  xor     r8d, r8d
0x1400d15cb  lea     rdx, aDisablemounton; "DisableMountOnCSV"
0x1400d15d2  call    VhdmpiGetPolicyBOOLEAN
0x1400d15d7  mov     ecx, [rbx]
0x1400d15d9  cmp     ecx, edi
0x1400d15db  jbe     short loc_1400D15E4
0x1400d15dd  lea     eax, [rcx-1]
0x1400d15e0  test    ecx, eax
0x1400d15e2  jz      short loc_1400D15E6
0x1400d15e4  mov     [rbx], edi
0x1400d15e6  xor     ebx, ebx
0x1400d15e8  mov     rcx, [rbp+Handle]; Handle
0x1400d15ec  test    rcx, rcx
0x1400d15ef  jz      short loc_1400D15FD
0x1400d15f1  call    cs:__imp_ZwClose
0x1400d15f8  nop     dword ptr [rax+rax+00h]
0x1400d15fd  mov     rcx, [rbp+var_10]; Handle
0x1400d1601  test    rcx, rcx
0x1400d1604  jz      short loc_1400D1612
0x1400d1606  call    cs:__imp_ZwClose
0x1400d160d  nop     dword ptr [rax+rax+00h]
0x1400d1612  mov     rcx, r15
0x1400d1615  call    VhdmpiReleasePassiveLock
0x1400d161a  mov     eax, ebx
0x1400d161c  add     rsp, 50h
0x1400d1620  pop     r15
0x1400d1622  pop     r14
0x1400d1624  pop     r13
0x1400d1626  pop     rdi
0x1400d1627  pop     rsi
0x1400d1628  pop     rbx
0x1400d1629  pop     rbp
0x1400d162a  retn
```
