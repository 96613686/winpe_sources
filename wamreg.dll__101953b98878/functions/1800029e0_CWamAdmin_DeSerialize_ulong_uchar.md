# CWamAdmin::DeSerialize(ulong,uchar *)

- ea: `0x1800029e0`
- end: `0x180002cee`
- name: `?DeSerialize@CWamAdmin@@UEAAJKPEAE@Z`
- size: `782`
- prototype: `__int64 __fastcall(CWamAdmin *this, int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x1800029e0`
- `0x180003cdc`
- `0x180004864`
- `0x180004acc`
- `0x180005a50`
- `0x180005cfc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180002b24`
- `iisutil!PuDbgPrint` at `0x180002b8d`
- `iisutil!PuDbgPrint` at `0x180002bd9`
- `iisutil!PuDbgPrint` at `0x180002c57`
- `iisutil!PuDbgPrint` at `0x180002ca4`
- `iisutil!PuDbgPrint` at `0x180002b24`
- `iisutil!PuDbgPrint` at `0x180002b8d`
- `iisutil!PuDbgPrint` at `0x180002bd9`
- `iisutil!PuDbgPrint` at `0x180002c57`
- `iisutil!PuDbgPrint` at `0x180002ca4`

## string_xrefs

- `0x180002b76`: `ConstructFullPath failed for base (%S) partial (%S) hr=%08x\n`
- `0x180002b0c`: `CWamAdmin::DeSerialize`
- `0x180002b5f`: `CWamAdmin::DeSerialize`
- `0x180002bc0`: `CWamAdmin::DeSerialize`
- `0x180002c39`: `CWamAdmin::DeSerialize`
- `0x180002c7c`: `CWamAdmin::DeSerialize`
- `0x180002afe`: `Unable to delete app at %S, hr = %08x\n`
- `0x180002bb4`: `DeSerialize: buffer size %d, \n`
- `0x180002c2d`: `Deserialize path = %S, WAMCLSID = %S.\n`
- `0x180002c6d`: `Failed to create COM application. Path(%S) Clsid(%S) AppId(%S). hr=%08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::DeSerialize(CWamAdmin *this, int a2, unsigned __int8 *a3)
{
  WamRegMetabaseConfig *v5; // rcx
  WamRegGlobal *v6; // rcx
  int v7; // ebx
  unsigned __int16 *v8; // rsi
  void *v9; // rdi
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  const wchar_t *v15; // rdi
  const wchar_t *v16; // rsi
  __int64 v17; // rax
  const wchar_t *v18; // rbx
  __int64 v19; // rax
  __int64 v21; // [rsp+30h] [rbp-58h]
  void *Block; // [rsp+50h] [rbp-38h] BYREF
  unsigned int v23; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int16 *v24; // [rsp+A8h] [rbp+20h] BYREF

  v24 = 0;
  WamRegGlobal::AcquireAdmWriteLock(this);
  v7 = WamRegMetabaseConfig::MDGetPropPaths(v5, L"/LM/W3SVC", 0x839u, &v24, &v23);
  if ( v7 < 0 )
    goto LABEL_22;
  v8 = v24;
  v9 = 0;
  v23 = 0;
  Block = 0;
  if ( !*v24 )
    goto LABEL_22;
  while ( 1 )
  {
    if ( v9 )
    {
      operator delete(v9);
      Block = 0;
    }
    v10 = WamRegGlobal::ConstructFullPath(v6, L"/LM/W3SVC", 9u, v8, (unsigned __int16 **)&Block);
    v9 = Block;
    v7 = v10;
    if ( v10 < 0 )
      break;
    v12 = WamRegMetabaseConfig::MDGetDWORD(v6, (const unsigned __int16 *)Block, v11, &v23);
    v7 = v12;
    if ( v12 >= 0 )
    {
      if ( v23 != 1 )
        goto LABEL_14;
      v13 = WamRegGlobal::DeleteApp(v6, (const unsigned __int16 *)v9, 0, 0);
      v7 = v13;
      if ( v13 >= 0 )
        goto LABEL_14;
      if ( (g_dwDebugFlags & 7) != 0 )
      {
        LODWORD(v21) = v13;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
          1333,
          "CWamAdmin::DeSerialize",
          "Unable to delete app at %S, hr = %08x\n",
          v9,
          v21);
      }
    }
    else if ( (g_dwDebugFlags & 7) != 0 )
    {
      LODWORD(v21) = v12;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        1318,
        "CWamAdmin::DeSerialize",
        "Failed to get MD_APP_ISOLATED at (%S) hr=%08x\n",
        v9,
        v21);
    }
    v7 = 0;
LABEL_14:
    v14 = -1;
    do
      ++v14;
    while ( v8[v14] );
    v8 += v14 + 1;
    if ( !*v8 )
      goto LABEL_20;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
      1304,
      "CWamAdmin::DeSerialize",
      "ConstructFullPath failed for base (%S) partial (%S) hr=%08x\n",
      L"/LM/W3SVC",
      v8,
      v10);
LABEL_20:
  if ( v9 )
    operator delete(v9);
LABEL_22:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
      1362,
      "CWamAdmin::DeSerialize",
      "DeSerialize: buffer size %d, \n",
      a2);
  while ( *(_DWORD *)a3 )
  {
    v15 = (const wchar_t *)(a3 + 4);
    v16 = (const wchar_t *)(a3 + 82);
    v17 = -1;
    v18 = (const wchar_t *)(a3 + 160);
    do
      ++v17;
    while ( v18[v17] );
    v6 = (WamRegGlobal *)&v18[v17 + 1];
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v6 + v19) );
    a3 = (unsigned __int8 *)v6 + 2 * v19 + 2;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        1391,
        "CWamAdmin::DeSerialize",
        "Deserialize path = %S, WAMCLSID = %S.\n",
        v18,
        v15);
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        1412,
        "CWamAdmin::DeSerialize",
        "Failed to create COM application. Path(%S) Clsid(%S) AppId(%S). hr=%08x\n",
        v18,
        v15,
        v16,
        -2147467263);
    v7 = 0;
  }
  if ( v24 )
    operator delete(v24);
  WamRegGlobal::ReleaseAdmWriteLock(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800029e0  mov     rax, rsp
0x1800029e3  mov     [rax+8], rbx
0x1800029e7  mov     [rax+10h], rbp
0x1800029eb  push    rsi
0x1800029ec  push    rdi
0x1800029ed  push    r12
0x1800029ef  push    r13
0x1800029f1  push    r15
0x1800029f3  sub     rsp, 60h
0x1800029f7  xor     r12d, r12d
0x1800029fa  mov     rbp, r8
0x1800029fd  mov     [rax+20h], r12
0x180002a01  mov     r15d, edx
0x180002a04  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x180002a09  lea     rax, [rsp+88h+arg_10]
0x180002a11  mov     r8d, 839h; unsigned int
0x180002a17  lea     r13, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x180002a1e  mov     [rsp+88h+var_68], rax; unsigned int *
0x180002a23  mov     rdx, r13; unsigned __int16 *
0x180002a26  lea     r9, [rsp+88h+arg_18]; unsigned __int16 **
0x180002a2e  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x180002a33  mov     ebx, eax
0x180002a35  test    eax, eax
0x180002a37  js      loc_180002BA0
0x180002a3d  mov     rsi, [rsp+88h+arg_18]
0x180002a45  mov     edi, r12d
0x180002a48  mov     [rsp+88h+arg_10], r12d
0x180002a50  mov     [rsp+88h+Block], r12
0x180002a55  cmp     [rsi], r12w
0x180002a59  jz      loc_180002BA0
0x180002a5f  test    rdi, rdi
0x180002a62  jz      short loc_180002A71
0x180002a64  mov     rcx, rdi; Block
0x180002a67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a6c  mov     [rsp+88h+Block], r12
0x180002a71  lea     rax, [rsp+88h+Block]
0x180002a76  mov     r9, rsi; unsigned __int16 *
0x180002a79  mov     r8d, 9; unsigned int
0x180002a7f  mov     [rsp+88h+var_68], rax; unsigned __int16 **
0x180002a84  mov     rdx, r13; unsigned __int16 *
0x180002a87  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x180002a8c  mov     rdi, [rsp+88h+Block]
0x180002a91  mov     ebx, eax
0x180002a93  test    eax, eax
0x180002a95  js      loc_180002B4F
0x180002a9b  lea     r9, [rsp+88h+arg_10]; unsigned int *
0x180002aa3  mov     rdx, rdi; unsigned __int16 *
0x180002aa6  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180002aab  mov     ebx, eax
0x180002aad  test    eax, eax
0x180002aaf  jns     short loc_180002ACD
0x180002ab1  test    byte ptr cs:g_dwDebugFlags, 7
0x180002ab8  jz      short loc_180002B2A
0x180002aba  mov     dword ptr [rsp+88h+var_58], eax
0x180002abe  mov     r8d, 526h
0x180002ac4  lea     rax, aFailedToGetMdA_0; "Failed to get MD_APP_ISOLATED at (%S) h"...
0x180002acb  jmp     short loc_180002B05
0x180002acd  cmp     [rsp+88h+arg_10], 1
0x180002ad5  jnz     short loc_180002B2D
0x180002ad7  xor     r9d, r9d; int
0x180002ada  xor     r8d, r8d; int
0x180002add  mov     rdx, rdi; unsigned __int16 *
0x180002ae0  call    ?DeleteApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::DeleteApp(ushort const *,int,int)
0x180002ae5  mov     ebx, eax
0x180002ae7  test    eax, eax
0x180002ae9  jns     short loc_180002B2D
0x180002aeb  test    byte ptr cs:g_dwDebugFlags, 7
0x180002af2  jz      short loc_180002B2A
0x180002af4  mov     dword ptr [rsp+88h+var_58], eax
0x180002af8  mov     r8d, 535h
0x180002afe  lea     rax, aUnableToDelete; "Unable to delete app at %S, hr = %08x\n"
0x180002b05  mov     rcx, cs:g_pDebug
0x180002b0c  lea     r9, aCwamadminDeser; "CWamAdmin::DeSerialize"
0x180002b13  mov     [rsp+88h+var_60], rdi
0x180002b18  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002b1f  mov     [rsp+88h+var_68], rax
0x180002b24  call    cs:__imp_PuDbgPrint
0x180002b2a  mov     ebx, r12d
0x180002b2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002b31  inc     rax
0x180002b34  cmp     [rsi+rax*2], r12w
0x180002b39  jnz     short loc_180002B31
0x180002b3b  lea     rsi, [rsi+rax*2]
0x180002b3f  add     rsi, 2
0x180002b43  cmp     [rsi], r12w
0x180002b47  jnz     loc_180002A5F
0x180002b4d  jmp     short loc_180002B93
0x180002b4f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002b56  jz      short loc_180002B93
0x180002b58  mov     rcx, cs:g_pDebug
0x180002b5f  lea     r9, aCwamadminDeser; "CWamAdmin::DeSerialize"
0x180002b66  mov     dword ptr [rsp+88h+var_50], eax
0x180002b6a  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002b71  mov     [rsp+88h+var_58], rsi
0x180002b76  lea     rax, aConstructfullp; "ConstructFullPath failed for base (%S) "...
0x180002b7d  mov     [rsp+88h+var_60], r13
0x180002b82  mov     r8d, 518h
0x180002b88  mov     [rsp+88h+var_68], rax
0x180002b8d  call    cs:__imp_PuDbgPrint
0x180002b93  test    rdi, rdi
0x180002b96  jz      short loc_180002BA0
0x180002b98  mov     rcx, rdi; Block
0x180002b9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ba0  test    byte ptr cs:g_dwDebugFlags, 3
0x180002ba7  jz      loc_180002CAD
0x180002bad  mov     rcx, cs:g_pDebug
0x180002bb4  lea     rax, aDeserializeBuf; "DeSerialize: buffer size %d, \n"
0x180002bbb  mov     dword ptr [rsp+88h+var_60], r15d
0x180002bc0  lea     r9, aCwamadminDeser; "CWamAdmin::DeSerialize"
0x180002bc7  mov     r8d, 552h
0x180002bcd  mov     [rsp+88h+var_68], rax
0x180002bd2  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002bd9  call    cs:__imp_PuDbgPrint
0x180002bdf  jmp     loc_180002CAD
0x180002be4  lea     rdi, [rbp+4]
0x180002be8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002bec  lea     rsi, [rdi+4Eh]
0x180002bf0  mov     rax, rdx
0x180002bf3  lea     rbx, [rsi+4Eh]
0x180002bf7  inc     rax
0x180002bfa  cmp     [rbx+rax*2], r12w
0x180002bff  jnz     short loc_180002BF7
0x180002c01  inc     rax
0x180002c04  lea     rcx, [rbx+rax*2]
0x180002c08  mov     rax, rdx
0x180002c0b  inc     rax
0x180002c0e  cmp     [rcx+rax*2], r12w
0x180002c13  jnz     short loc_180002C0B
0x180002c15  test    byte ptr cs:g_dwDebugFlags, 3
0x180002c1c  lea     rbp, [rax+1]
0x180002c20  lea     rbp, [rcx+rbp*2]
0x180002c24  jz      short loc_180002C5D
0x180002c26  mov     rcx, cs:g_pDebug
0x180002c2d  lea     rax, aDeserializePat; "Deserialize path = %S, WAMCLSID = %S.\n"
0x180002c34  mov     [rsp+88h+var_58], rdi
0x180002c39  lea     r9, aCwamadminDeser; "CWamAdmin::DeSerialize"
0x180002c40  mov     [rsp+88h+var_60], rbx
0x180002c45  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002c4c  mov     r8d, 56Fh
0x180002c52  mov     [rsp+88h+var_68], rax
0x180002c57  call    cs:__imp_PuDbgPrint
0x180002c5d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002c64  jz      short loc_180002CAA
0x180002c66  mov     rcx, cs:g_pDebug
0x180002c6d  lea     rax, aFailedToCreate_3; "Failed to create COM application. Path("...
0x180002c74  mov     [rsp+88h+var_48], 80004001h
0x180002c7c  lea     r9, aCwamadminDeser; "CWamAdmin::DeSerialize"
0x180002c83  mov     [rsp+88h+var_50], rsi
0x180002c88  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002c8f  mov     [rsp+88h+var_58], rdi
0x180002c94  mov     r8d, 584h
0x180002c9a  mov     [rsp+88h+var_60], rbx
0x180002c9f  mov     [rsp+88h+var_68], rax
0x180002ca4  call    cs:__imp_PuDbgPrint
0x180002caa  mov     ebx, r12d
0x180002cad  cmp     [rbp+0], r12d
0x180002cb1  jnz     loc_180002BE4
0x180002cb7  cmp     [rsp+88h+arg_18], r12
0x180002cbf  jz      short loc_180002CCE
0x180002cc1  mov     rcx, [rsp+88h+arg_18]; Block
0x180002cc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002cce  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x180002cd3  lea     r11, [rsp+88h+var_28]
0x180002cd8  mov     eax, ebx
0x180002cda  mov     rbx, [r11+30h]
0x180002cde  mov     rbp, [r11+38h]
0x180002ce2  mov     rsp, r11
0x180002ce5  pop     r15
0x180002ce7  pop     r13
0x180002ce9  pop     r12
0x180002ceb  pop     rdi
0x180002cec  pop     rsi
0x180002ced  retn
```
