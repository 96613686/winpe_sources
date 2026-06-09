# CWamAdmin::Serialize(ulong,uchar *,ulong *)

- ea: `0x180003d80`
- end: `0x1800041cb`
- name: `?Serialize@CWamAdmin@@UEAAJKPEAEPEAK@Z`
- size: `1099`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x180003cdc`
- `0x180003d80`
- `0x180004864`
- `0x180005a50`
- `0x180005b90`
- `0x180005cfc`
- `0x180005f74`
- `0x180006816`
- `0x180006850`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003e81`
- `msvcrt!_wcsnicmp` at `0x180003e81`
- `iisutil!PuDbgPrint` at `0x180004048`
- `iisutil!PuDbgPrint` at `0x180004095`
- `iisutil!PuDbgPrint` at `0x1800040d8`
- `iisutil!PuDbgPrint` at `0x18000411e`
- `iisutil!PuDbgPrint` at `0x180004188`
- `iisutil!PuDbgPrint` at `0x180004048`
- `iisutil!PuDbgPrint` at `0x180004095`
- `iisutil!PuDbgPrint` at `0x1800040d8`
- `iisutil!PuDbgPrint` at `0x18000411e`
- `iisutil!PuDbgPrint` at `0x180004188`

## string_xrefs

- `0x180004107`: `ConstructFullPath failed for base (%S) partial (%S) hr=%08x\n`
- `0x180004176`: `Serialize: GetPropPaths failed hr = %08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::Serialize(CWamAdmin *this, unsigned int a2, unsigned __int8 *a3, unsigned int *a4)
{
  unsigned int v5; // edi
  WamRegMetabaseConfig *v6; // rcx
  int v7; // eax
  WamRegGlobal *v8; // rcx
  int v9; // esi
  unsigned int v10; // r12d
  wchar_t *v11; // r14
  void *v12; // r15
  const unsigned __int16 *v13; // r13
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  unsigned __int8 *v23; // rdi
  __int64 v24; // rbx
  unsigned __int8 *v25; // rdi
  size_t v26; // rbx
  __int64 v27; // rax
  unsigned int v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v35; // [rsp+68h] [rbp-98h]
  unsigned __int16 v36[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+90h] [rbp-70h]
  _OWORD v39[2]; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v40[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v41; // [rsp+D0h] [rbp-30h]
  __int128 v42; // [rsp+E0h] [rbp-20h]
  _OWORD v43[2]; // [rsp+F0h] [rbp-10h]

  v35 = a4;
  Block = 0;
  v5 = a2;
  v33 = a2;
  WamRegGlobal::AcquireAdmWriteLock(this);
  v7 = WamRegMetabaseConfig::MDGetPropPaths(v6, L"/LM/W3SVC", 0x839u, (unsigned __int16 **)&Block, &v30);
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        1218,
        "CWamAdmin::Serialize",
        "Serialize: GetPropPaths failed hr = %08x\n",
        v7);
  }
  else
  {
    v29 = 0;
    v10 = 4;
    v11 = 0;
    String1 = 0;
    v12 = 0;
    Src = 0;
    v13 = (const unsigned __int16 *)Block;
    if ( *(_WORD *)Block )
    {
      do
      {
        if ( v11 )
        {
          operator delete(v11);
          String1 = 0;
        }
        if ( v12 )
        {
          operator delete(v12);
          v12 = 0;
          Src = 0;
        }
        v14 = WamRegGlobal::ConstructFullPath(v8, L"/LM/W3SVC", 9u, v13, &String1);
        v9 = v14;
        if ( v14 < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
              1096,
              "CWamAdmin::Serialize",
              "ConstructFullPath failed for base (%S) partial (%S) hr=%08x\n",
              L"/LM/W3SVC",
              v13,
              v14);
          v11 = String1;
          goto LABEL_37;
        }
        v11 = String1;
        if ( _wcsnicmp(String1, L"/LM/W3SVC", 0xAu) )
        {
          v16 = WamRegMetabaseConfig::MDGetDWORD(v8, v11, v15, &v29);
          v9 = v16;
          if ( v16 < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                1115,
                "CWamAdmin::Serialize",
                "Failed to get MD_APP_ISOLATED, hr=%08x\n",
                v16);
            goto LABEL_37;
          }
          if ( v29 == 1 )
          {
            v17 = WamRegMetabaseConfig::MDGetIDs(v8, v11, v36, v40, 1u);
            v9 = v17;
            if ( v17 < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                  1136,
                  "CWamAdmin::Serialize",
                  "Failed to get IDs for %S, hr = %08x\n",
                  v11,
                  v17);
              goto LABEL_37;
            }
            v18 = WamRegMetabaseConfig::MDGetStringAttribute(v8, v11, 0x83Bu, (unsigned __int16 **)&Src);
            v9 = v18;
            if ( v18 < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                  1149,
                  "CWamAdmin::Serialize",
                  "Failed to get AppName for %S, hr = %08x\n",
                  v11,
                  v18);
              v12 = Src;
              goto LABEL_37;
            }
            v19 = -1;
            do
              ++v19;
            while ( v11[v19] );
            v12 = Src;
            v8 = (WamRegGlobal *)(unsigned int)(v19 + 1);
            v20 = -1;
            do
              ++v20;
            while ( *((_WORD *)Src + v20) );
            v30 = v20 + 1;
            v21 = (_DWORD)v8 + v20 + 1;
            v10 += 2 * v21 + 160;
            v22 = 2 * v21 + 160;
            if ( v10 <= v5 )
            {
              *(_DWORD *)a3 = v22;
              v23 = a3 + 160;
              *(_OWORD *)(a3 + 4) = *(_OWORD *)v36;
              *(_OWORD *)(a3 + 20) = v37;
              *(_OWORD *)(a3 + 36) = v38;
              *(_OWORD *)(a3 + 52) = v39[0];
              *(_OWORD *)(a3 + 66) = *(_OWORD *)((char *)v39 + 14);
              *(_OWORD *)(a3 + 82) = *(_OWORD *)v40;
              *(_OWORD *)(a3 + 98) = v41;
              *(_OWORD *)(a3 + 114) = v42;
              *(_OWORD *)(a3 + 130) = v43[0];
              *((_OWORD *)a3 + 9) = *(_OWORD *)((char *)v43 + 14);
              v24 = 2LL * (_QWORD)v8;
              memcpy_0(v23, v11, 2LL * (_QWORD)v8);
              v25 = &v23[v24];
              v26 = 2LL * v30;
              memcpy_0(v25, v12, v26);
              a3 = &v25[v26];
              v5 = v33;
            }
          }
        }
        v27 = -1;
        do
          ++v27;
        while ( v13[v27] );
        v13 += v27 + 1;
      }
      while ( *v13 );
      if ( v9 < 0 )
        goto LABEL_37;
    }
    if ( v10 > v5 )
      v9 = -2147024774;
    else
      *(_DWORD *)a3 = 0;
    *v35 = v10;
LABEL_37:
    if ( v11 )
      operator delete(v11);
    if ( v12 )
      operator delete(v12);
  }
  WamRegGlobal::ReleaseAdmWriteLock(v8);
  if ( Block )
    operator delete(Block);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003d80  mov     [rsp-8+arg_0], rbx
0x180003d85  push    rbp
0x180003d86  push    rsi
0x180003d87  push    rdi
0x180003d88  push    r12
0x180003d8a  push    r13
0x180003d8c  push    r14
0x180003d8e  push    r15
0x180003d90  lea     rbp, [rsp-20h]
0x180003d95  sub     rsp, 120h
0x180003d9c  mov     rax, cs:__security_cookie
0x180003da3  xor     rax, rsp
0x180003da6  mov     [rbp+50h+var_40], rax
0x180003daa  xor     r13d, r13d
0x180003dad  mov     [rsp+150h+var_E8], r9
0x180003db2  mov     [rsp+150h+Block], r13
0x180003db7  mov     rbx, r8
0x180003dba  mov     edi, edx
0x180003dbc  mov     [rsp+150h+var_F8], edx
0x180003dc0  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x180003dc5  lea     rax, [rsp+150h+var_10C]
0x180003dca  mov     r8d, 839h; unsigned int
0x180003dd0  lea     r9, [rsp+150h+Block]; unsigned __int16 **
0x180003dd5  mov     [rsp+150h+var_130], rax; unsigned int *
0x180003dda  lea     rdx, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x180003de1  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x180003de6  mov     esi, eax
0x180003de8  test    eax, eax
0x180003dea  js      loc_180004154
0x180003df0  mov     [rsp+150h+var_110], r13d
0x180003df5  lea     r12d, [r13+4]
0x180003df9  mov     r14d, r13d
0x180003dfc  mov     [rsp+150h+String1], r13
0x180003e01  mov     r15d, r13d
0x180003e04  mov     [rsp+150h+Src], r13
0x180003e09  mov     r13, [rsp+150h+Block]
0x180003e0e  xor     edx, edx
0x180003e10  cmp     [r13+0], dx
0x180003e15  jz      loc_180003FFF
0x180003e1b  test    r14, r14
0x180003e1e  jz      short loc_180003E2F
0x180003e20  mov     rcx, r14; Block
0x180003e23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003e28  xor     edx, edx
0x180003e2a  mov     [rsp+150h+String1], rdx
0x180003e2f  test    r15, r15
0x180003e32  jz      short loc_180003E44
0x180003e34  mov     rcx, r15; Block
0x180003e37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003e3c  xor     r15d, r15d
0x180003e3f  mov     [rsp+150h+Src], r15
0x180003e44  lea     rax, [rsp+150h+String1]
0x180003e49  mov     r9, r13; unsigned __int16 *
0x180003e4c  lea     r14, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x180003e53  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x180003e58  mov     rdx, r14; unsigned __int16 *
0x180003e5b  mov     r8d, 9; unsigned int
0x180003e61  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x180003e66  mov     esi, eax
0x180003e68  test    eax, eax
0x180003e6a  js      loc_1800040E0
0x180003e70  mov     rdx, r14; String2
0x180003e73  mov     r8d, 0Ah; MaxCount
0x180003e79  mov     r14, [rsp+150h+String1]
0x180003e7e  mov     rcx, r14; String1
0x180003e81  call    cs:__imp__wcsnicmp
0x180003e87  xor     edx, edx
0x180003e89  test    eax, eax
0x180003e8b  jz      loc_180003FD4
0x180003e91  lea     r9, [rsp+150h+var_110]; unsigned int *
0x180003e96  mov     rdx, r14; unsigned __int16 *
0x180003e99  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180003e9e  xor     edx, edx
0x180003ea0  mov     esi, eax
0x180003ea2  test    eax, eax
0x180003ea4  js      loc_1800040A0
0x180003eaa  cmp     [rsp+150h+var_110], 1
0x180003eaf  jnz     loc_180003FD4
0x180003eb5  lea     r9, [rbp+50h+var_90]; unsigned __int16 *
0x180003eb9  mov     dword ptr [rsp+150h+var_130], 1; unsigned int
0x180003ec1  lea     r8, [rsp+150h+var_E0]; unsigned __int16 *
0x180003ec6  mov     rdx, r14; unsigned __int16 *
0x180003ec9  call    ?MDGetIDs@WamRegMetabaseConfig@@QEAAJPEBGPEAG1K@Z; WamRegMetabaseConfig::MDGetIDs(ushort const *,ushort *,ushort *,ulong)
0x180003ece  mov     esi, eax
0x180003ed0  test    eax, eax
0x180003ed2  js      loc_180004058
0x180003ed8  lea     r9, [rsp+150h+Src]; unsigned __int16 **
0x180003edd  mov     r8d, 83Bh; unsigned int
0x180003ee3  mov     rdx, r14; unsigned __int16 *
0x180003ee6  call    ?MDGetStringAttribute@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAG@Z; WamRegMetabaseConfig::MDGetStringAttribute(ushort const *,ulong,ushort * *)
0x180003eeb  xor     edx, edx
0x180003eed  mov     esi, eax
0x180003eef  test    eax, eax
0x180003ef1  js      loc_18000400F
0x180003ef7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003efb  mov     rax, r8
0x180003efe  inc     rax
0x180003f01  cmp     [r14+rax*2], dx
0x180003f06  jnz     short loc_180003EFE
0x180003f08  mov     r15, [rsp+150h+Src]
0x180003f0d  lea     ecx, [rax+1]
0x180003f10  mov     rax, r8
0x180003f13  inc     rax
0x180003f16  cmp     [r15+rax*2], dx
0x180003f1b  jnz     short loc_180003F13
0x180003f1d  inc     eax
0x180003f1f  mov     [rsp+150h+var_10C], eax
0x180003f23  add     eax, ecx
0x180003f25  lea     r12d, [r12+rax*2]
0x180003f29  add     r12d, 0A0h
0x180003f30  lea     eax, ds:0A0h[rax*2]
0x180003f37  cmp     r12d, edi
0x180003f3a  ja      loc_180003FD4
0x180003f40  mov     [rbx], eax
0x180003f42  lea     rdi, [rbx+0A0h]
0x180003f49  movaps  xmm0, xmmword ptr [rsp+150h+var_E0]
0x180003f4e  mov     rdx, r14; Src
0x180003f51  movups  xmmword ptr [rbx+4], xmm0
0x180003f55  movaps  xmm1, [rbp+50h+var_D0]
0x180003f59  movups  xmmword ptr [rbx+14h], xmm1
0x180003f5d  movaps  xmm0, [rbp+50h+var_C0]
0x180003f61  movups  xmmword ptr [rbx+24h], xmm0
0x180003f65  movaps  xmm1, xmmword ptr [rbp+50h+var_B0]
0x180003f69  movups  xmmword ptr [rbx+34h], xmm1
0x180003f6d  movups  xmm0, xmmword ptr [rbp+50h+var_B0+0Eh]
0x180003f71  movups  xmmword ptr [rbx+42h], xmm0
0x180003f75  movaps  xmm0, xmmword ptr [rbp+50h+var_90]
0x180003f79  movups  xmmword ptr [rbx+52h], xmm0
0x180003f7d  movaps  xmm1, [rbp+50h+var_80]
0x180003f81  movups  xmmword ptr [rbx+62h], xmm1
0x180003f85  movaps  xmm0, [rbp+50h+var_70]
0x180003f89  movups  xmmword ptr [rbx+72h], xmm0
0x180003f8d  movaps  xmm1, xmmword ptr [rbp+50h+var_60]
0x180003f91  movups  xmmword ptr [rbx+82h], xmm1
0x180003f98  movups  xmm0, xmmword ptr [rbp+50h+var_60+0Eh]
0x180003f9c  movups  xmmword ptr [rbx+90h], xmm0
0x180003fa3  lea     rbx, [rcx+rcx]
0x180003fa7  mov     rcx, rdi; void *
0x180003faa  mov     r8, rbx; Size
0x180003fad  call    memcpy_0
0x180003fb2  mov     eax, [rsp+150h+var_10C]
0x180003fb6  add     rdi, rbx
0x180003fb9  mov     rdx, r15; Src
0x180003fbc  mov     rcx, rdi; void *
0x180003fbf  lea     rbx, [rax+rax]
0x180003fc3  mov     r8, rbx; Size
0x180003fc6  call    memcpy_0
0x180003fcb  add     rbx, rdi
0x180003fce  mov     edi, [rsp+150h+var_F8]
0x180003fd2  xor     edx, edx
0x180003fd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003fd8  inc     rax
0x180003fdb  cmp     [r13+rax*2+0], dx
0x180003fe1  jnz     short loc_180003FD8
0x180003fe3  lea     r13, [r13+rax*2+0]
0x180003fe8  add     r13, 2
0x180003fec  cmp     [r13+0], dx
0x180003ff1  jnz     loc_180003E1B
0x180003ff7  test    esi, esi
0x180003ff9  js      loc_180004138
0x180003fff  cmp     r12d, edi
0x180004002  ja      loc_18000412B
0x180004008  mov     [rbx], edx
0x18000400a  jmp     loc_180004130
0x18000400f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004016  jz      short loc_18000404E
0x180004018  mov     rcx, cs:g_pDebug
0x18000401f  lea     r9, aCwamadminSeria; "CWamAdmin::Serialize"
0x180004026  mov     dword ptr [rsp+150h+var_120], eax
0x18000402a  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180004031  lea     rax, aFailedToGetApp; "Failed to get AppName for %S, hr = %08x"...
0x180004038  mov     [rsp+150h+var_128], r14
0x18000403d  mov     r8d, 47Dh
0x180004043  mov     [rsp+150h+var_130], rax
0x180004048  call    cs:__imp_PuDbgPrint
0x18000404e  mov     r15, [rsp+150h+Src]
0x180004053  jmp     loc_180004138
0x180004058  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000405f  jz      loc_180004138
0x180004065  mov     rcx, cs:g_pDebug
0x18000406c  lea     r9, aCwamadminSeria; "CWamAdmin::Serialize"
0x180004073  mov     dword ptr [rsp+150h+var_120], eax
0x180004077  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x18000407e  lea     rax, aFailedToGetIds; "Failed to get IDs for %S, hr = %08x\n"
0x180004085  mov     [rsp+150h+var_128], r14
0x18000408a  mov     r8d, 470h
0x180004090  mov     [rsp+150h+var_130], rax
0x180004095  call    cs:__imp_PuDbgPrint
0x18000409b  jmp     loc_180004138
0x1800040a0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800040a7  jz      loc_180004138
0x1800040ad  mov     rcx, cs:g_pDebug
0x1800040b4  lea     r9, aCwamadminSeria; "CWamAdmin::Serialize"
0x1800040bb  mov     dword ptr [rsp+150h+var_128], eax
0x1800040bf  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800040c6  lea     rax, aFailedToGetMdA; "Failed to get MD_APP_ISOLATED, hr=%08x"...
0x1800040cd  mov     r8d, 45Bh
0x1800040d3  mov     [rsp+150h+var_130], rax
0x1800040d8  call    cs:__imp_PuDbgPrint
0x1800040de  jmp     short loc_180004138
0x1800040e0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800040e7  jz      short loc_180004124
0x1800040e9  mov     rcx, cs:g_pDebug
0x1800040f0  lea     r9, aCwamadminSeria; "CWamAdmin::Serialize"
0x1800040f7  mov     [rsp+150h+var_118], eax
0x1800040fb  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180004102  mov     [rsp+150h+var_120], r13
0x180004107  lea     rax, aConstructfullp; "ConstructFullPath failed for base (%S) "...
0x18000410e  mov     [rsp+150h+var_128], r14
0x180004113  mov     r8d, 448h
0x180004119  mov     [rsp+150h+var_130], rax
0x18000411e  call    cs:__imp_PuDbgPrint
0x180004124  mov     r14, [rsp+150h+String1]
0x180004129  jmp     short loc_180004138
0x18000412b  mov     esi, 8007007Ah
0x180004130  mov     rax, [rsp+150h+var_E8]
0x180004135  mov     [rax], r12d
0x180004138  test    r14, r14
0x18000413b  jz      short loc_180004145
0x18000413d  mov     rcx, r14; Block
0x180004140  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004145  test    r15, r15
0x180004148  jz      short loc_18000418E
0x18000414a  mov     rcx, r15; Block
0x18000414d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004152  jmp     short loc_18000418E
0x180004154  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000415b  jz      short loc_18000418E
0x18000415d  mov     rcx, cs:g_pDebug
0x180004164  lea     r9, aCwamadminSeria; "CWamAdmin::Serialize"
0x18000416b  mov     dword ptr [rsp+150h+var_128], eax
0x18000416f  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180004176  lea     rax, aSerializeGetpr; "Serialize: GetPropPaths failed hr = %08"...
0x18000417d  mov     r8d, 4C2h
0x180004183  mov     [rsp+150h+var_130], rax
0x180004188  call    cs:__imp_PuDbgPrint
0x18000418e  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x180004193  mov     rcx, [rsp+150h+Block]; Block
0x180004198  test    rcx, rcx
0x18000419b  jz      short loc_1800041A2
0x18000419d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800041a2  mov     eax, esi
0x1800041a4  mov     rcx, [rbp+50h+var_40]
0x1800041a8  xor     rcx, rsp; StackCookie
0x1800041ab  call    __security_check_cookie
0x1800041b0  mov     rbx, [rsp+150h+arg_0]
0x1800041b8  add     rsp, 120h
0x1800041bf  pop     r15
0x1800041c1  pop     r14
0x1800041c3  pop     r13
0x1800041c5  pop     r12
0x1800041c7  pop     rdi
0x1800041c8  pop     rsi
0x1800041c9  pop     rbp
0x1800041ca  retn
```
