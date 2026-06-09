# CWamAdmin::PrivateDeleteApplication(ushort const *,int,int,int)

- ea: `0x180003720`
- end: `0x1800039cc`
- name: `?PrivateDeleteApplication@CWamAdmin@@AEAAJPEBGHHH@Z`
- size: `684`
- prototype: `__int64 __fastcall(CWamAdmin *this, WamRegGlobal *, int, unsigned int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800020c0`
- `0x1800020e0`
- `0x180002d00`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x180003720`
- `0x180003cdc`
- `0x180004864`
- `0x180004acc`
- `0x180005cfc`
- `0x180007010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003881`
- `msvcrt!_wcsnicmp` at `0x180003881`
- `iisutil!PuDbgPrint` at `0x1800037f2`
- `iisutil!PuDbgPrint` at `0x1800038ea`
- `iisutil!PuDbgPrint` at `0x18000394b`
- `iisutil!PuDbgPrint` at `0x180003990`
- `iisutil!PuDbgPrint` at `0x1800037f2`
- `iisutil!PuDbgPrint` at `0x1800038ea`
- `iisutil!PuDbgPrint` at `0x18000394b`
- `iisutil!PuDbgPrint` at `0x180003990`

## string_xrefs

- `0x1800037c9`: `Failed to Delete on path %S, hr = %08x\n`
- `0x180003934`: `Failed to Delete on path %S, hr = %08x\n`
- `0x1800037d4`: `CWamAdmin::PrivateDeleteApplication`
- `0x1800038c1`: `CWamAdmin::PrivateDeleteApplication`
- `0x180003922`: `CWamAdmin::PrivateDeleteApplication`
- `0x18000396c`: `CWamAdmin::PrivateDeleteApplication`
- `0x1800038d3`: `Failed to DeleteRecoverable, hr = %08x\n`
- `0x18000397e`: `Delete: GetPropPaths failed hr = %08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::PrivateDeleteApplication(
        CWamAdmin *this,
        WamRegGlobal *a2,
        int a3,
        unsigned int a4,
        int a5)
{
  __int64 result; // rax
  __int64 v9; // rax
  WamRegMetabaseConfig *v10; // rcx
  int v11; // eax
  WamRegGlobal *v12; // rcx
  int v13; // ebx
  __int64 v14; // r14
  int v15; // eax
  const unsigned __int16 *v16; // rdi
  wchar_t *v17; // r15
  WamRegGlobal *v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  WamRegGlobal *v21; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+48h] [rbp-8h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+38h] BYREF

  v21 = 0;
  if ( !a2 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(CWamAdmin *, WamRegGlobal *, WamRegGlobal **))(*(_QWORD *)this + 88LL))(
             this,
             a2,
             &v21);
  if ( (int)result < 0 )
    return result;
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)v21 + v9) );
  if ( (unsigned int)v9 <= 0xA )
    return 2147942487LL;
  WamRegGlobal::AcquireAdmWriteLock(v21);
  if ( a3 )
  {
    Block = 0;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v21 + v14) );
    v15 = WamRegMetabaseConfig::MDGetPropPaths(
            v10,
            (const unsigned __int16 *)v21,
            0x838u,
            (unsigned __int16 **)&Block,
            (unsigned int *)&String1);
    v13 = v15;
    if ( v15 >= 0 && Block )
    {
      v16 = (const unsigned __int16 *)Block;
      String1 = 0;
      while ( *v16 && v13 >= 0 )
      {
        v13 = WamRegGlobal::ConstructFullPath(v12, (const unsigned __int16 *)v21, v14, v16, &String1);
        if ( v13 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
              299,
              "CWamAdmin::PrivateDeleteApplication",
              "Failed to DeleteRecoverable, hr = %08x\n",
              (_DWORD)v16);
        }
        else
        {
          v17 = String1;
          if ( _wcsnicmp(String1, L"/LM/W3SVC", 0xAu) )
          {
            v19 = WamRegGlobal::DeleteApp(v18, v17, a4, a5);
            v13 = v19;
            if ( v19 < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                  287,
                  "CWamAdmin::PrivateDeleteApplication",
                  "Failed to Delete on path %S, hr = %08x\n",
                  v16,
                  v19);
              break;
            }
          }
          operator delete(v17);
          String1 = 0;
        }
        v20 = -1;
        do
          ++v20;
        while ( v16[v20] );
        v16 += v20 + 1;
      }
      operator delete(Block);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        308,
        "CWamAdmin::PrivateDeleteApplication",
        "Delete: GetPropPaths failed hr = %08x\n",
        v15);
    }
  }
  else
  {
    v11 = WamRegGlobal::DeleteApp(v10, (const unsigned __int16 *)v21, a4, a5);
    v13 = 0;
    if ( v11 != -2146646015 )
      v13 = v11;
    if ( v13 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        249,
        "CWamAdmin::PrivateDeleteApplication",
        "Failed to Delete on path %S, hr = %08x\n",
        (const wchar_t *)a2,
        v13);
  }
  WamRegGlobal::ReleaseAdmWriteLock(v12);
  if ( v21 != a2 )
    operator delete(v21);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180003720  mov     [rsp-28h+arg_0], rbx
0x180003725  mov     [rsp-28h+arg_10], rdi
0x18000372a  push    rbp
0x18000372b  push    r12
0x18000372d  push    r13
0x18000372f  push    r14
0x180003731  push    r15
0x180003733  mov     rbp, rsp
0x180003736  sub     rsp, 50h
0x18000373a  xor     r15d, r15d
0x18000373d  mov     r13d, r9d
0x180003740  mov     [rbp+var_10], r15
0x180003744  mov     ebx, r8d
0x180003747  mov     r12, rdx
0x18000374a  test    rdx, rdx
0x18000374d  jz      loc_1800039AD
0x180003753  mov     rax, [rcx]
0x180003756  lea     r8, [rbp+var_10]
0x18000375a  mov     rax, [rax+58h]
0x18000375e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003763  test    eax, eax
0x180003765  js      loc_1800039B2
0x18000376b  mov     rcx, [rbp+var_10]; this
0x18000376f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003773  mov     rax, rdi
0x180003776  inc     rax
0x180003779  cmp     [rcx+rax*2], r15w
0x18000377e  jnz     short loc_180003776
0x180003780  cmp     eax, 0Ah
0x180003783  jbe     loc_1800039AD
0x180003789  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x18000378e  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180003792  test    ebx, ebx
0x180003794  jnz     short loc_1800037FD
0x180003796  mov     r9d, [rbp+arg_20]; int
0x18000379a  mov     r8d, r13d; int
0x18000379d  call    ?DeleteApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::DeleteApp(ushort const *,int,int)
0x1800037a2  cmp     eax, 800CC801h
0x1800037a7  mov     ebx, r15d
0x1800037aa  cmovnz  ebx, eax
0x1800037ad  test    ebx, ebx
0x1800037af  jns     loc_180003996
0x1800037b5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800037bc  jz      loc_180003996
0x1800037c2  mov     rcx, cs:g_pDebug
0x1800037c9  lea     rax, aFailedToDelete_1; "Failed to Delete on path %S, hr = %08x"...
0x1800037d0  mov     [rsp+50h+var_20], ebx
0x1800037d4  lea     r9, aCwamadminPriva; "CWamAdmin::PrivateDeleteApplication"
0x1800037db  mov     [rsp+50h+var_28], r12
0x1800037e0  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800037e7  mov     r8d, 0F9h
0x1800037ed  mov     [rsp+50h+var_30], rax
0x1800037f2  call    cs:__imp_PuDbgPrint
0x1800037f8  jmp     loc_180003996
0x1800037fd  mov     [rbp+Block], r15
0x180003801  mov     r14, rdi
0x180003804  inc     r14
0x180003807  cmp     [rdx+r14*2], r15w
0x18000380c  jnz     short loc_180003804
0x18000380e  lea     rax, [rbp+String1]
0x180003812  mov     r8d, 838h; unsigned int
0x180003818  lea     r9, [rbp+Block]; unsigned __int16 **
0x18000381c  mov     [rsp+50h+var_30], rax; unsigned int *
0x180003821  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x180003826  mov     ebx, eax
0x180003828  test    eax, eax
0x18000382a  js      loc_18000395C
0x180003830  cmp     [rbp+Block], r15
0x180003834  jz      loc_18000395C
0x18000383a  mov     rdi, [rbp+Block]
0x18000383e  mov     [rbp+String1], r15
0x180003842  jmp     loc_180003906
0x180003847  test    ebx, ebx
0x180003849  js      loc_180003951
0x18000384f  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180003853  lea     rax, [rbp+String1]
0x180003857  mov     r9, rdi; unsigned __int16 *
0x18000385a  mov     [rsp+50h+var_30], rax; unsigned __int16 **
0x18000385f  mov     r8d, r14d; unsigned int
0x180003862  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x180003867  mov     ebx, eax
0x180003869  test    eax, eax
0x18000386b  js      short loc_1800038B1
0x18000386d  mov     r15, [rbp+String1]
0x180003871  lea     rdx, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x180003878  mov     rcx, r15; String1
0x18000387b  mov     r8d, 0Ah; MaxCount
0x180003881  call    cs:__imp__wcsnicmp
0x180003887  test    eax, eax
0x180003889  jz      short loc_1800038A0
0x18000388b  mov     r9d, [rbp+arg_20]; int
0x18000388f  mov     r8d, r13d; int
0x180003892  mov     rdx, r15; unsigned __int16 *
0x180003895  call    ?DeleteApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::DeleteApp(ushort const *,int,int)
0x18000389a  mov     ebx, eax
0x18000389c  test    eax, eax
0x18000389e  js      short loc_180003912
0x1800038a0  mov     rcx, r15; Block
0x1800038a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038a8  xor     r15d, r15d
0x1800038ab  mov     [rbp+String1], r15
0x1800038af  jmp     short loc_1800038F0
0x1800038b1  test    byte ptr cs:g_dwDebugFlags, 3
0x1800038b8  jz      short loc_1800038F0
0x1800038ba  mov     rcx, cs:g_pDebug
0x1800038c1  lea     r9, aCwamadminPriva; "CWamAdmin::PrivateDeleteApplication"
0x1800038c8  mov     [rsp+50h+var_20], eax
0x1800038cc  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800038d3  lea     rax, aFailedToDelete; "Failed to DeleteRecoverable, hr = %08x"...
0x1800038da  mov     [rsp+50h+var_28], rdi
0x1800038df  mov     r8d, 12Bh
0x1800038e5  mov     [rsp+50h+var_30], rax
0x1800038ea  call    cs:__imp_PuDbgPrint
0x1800038f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800038f4  inc     rax
0x1800038f7  cmp     [rdi+rax*2], r15w
0x1800038fc  jnz     short loc_1800038F4
0x1800038fe  lea     rdi, [rdi+rax*2]
0x180003902  add     rdi, 2
0x180003906  cmp     [rdi], r15w
0x18000390a  jnz     loc_180003847
0x180003910  jmp     short loc_180003951
0x180003912  test    byte ptr cs:g_dwDebugFlags, 3
0x180003919  jz      short loc_180003951
0x18000391b  mov     rcx, cs:g_pDebug
0x180003922  lea     r9, aCwamadminPriva; "CWamAdmin::PrivateDeleteApplication"
0x180003929  mov     [rsp+50h+var_20], eax
0x18000392d  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180003934  lea     rax, aFailedToDelete_1; "Failed to Delete on path %S, hr = %08x"...
0x18000393b  mov     [rsp+50h+var_28], rdi
0x180003940  mov     r8d, 11Fh
0x180003946  mov     [rsp+50h+var_30], rax
0x18000394b  call    cs:__imp_PuDbgPrint
0x180003951  mov     rcx, [rbp+Block]; Block
0x180003955  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000395a  jmp     short loc_180003996
0x18000395c  test    byte ptr cs:g_dwDebugFlags, 3
0x180003963  jz      short loc_180003996
0x180003965  mov     rcx, cs:g_pDebug
0x18000396c  lea     r9, aCwamadminPriva; "CWamAdmin::PrivateDeleteApplication"
0x180003973  mov     dword ptr [rsp+50h+var_28], eax
0x180003977  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x18000397e  lea     rax, aDeleteGetpropp; "Delete: GetPropPaths failed hr = %08x\n"
0x180003985  mov     r8d, 134h
0x18000398b  mov     [rsp+50h+var_30], rax
0x180003990  call    cs:__imp_PuDbgPrint
0x180003996  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x18000399b  mov     rcx, [rbp+var_10]; Block
0x18000399f  cmp     rcx, r12
0x1800039a2  jz      short loc_1800039A9
0x1800039a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800039a9  mov     eax, ebx
0x1800039ab  jmp     short loc_1800039B2
0x1800039ad  mov     eax, 80070057h
0x1800039b2  lea     r11, [rsp+50h+var_s0]
0x1800039b7  mov     rbx, [r11+30h]
0x1800039bb  mov     rdi, [r11+40h]
0x1800039bf  mov     rsp, r11
0x1800039c2  pop     r15
0x1800039c4  pop     r14
0x1800039c6  pop     r13
0x1800039c8  pop     r12
0x1800039ca  pop     rbp
0x1800039cb  retn
```
