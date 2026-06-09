# CWamAdmin::AppRecover(ushort const *,int)

- ea: `0x1800021d0`
- end: `0x18000245a`
- name: `?AppRecover@CWamAdmin@@UEAAJPEBGH@Z`
- size: `650`
- prototype: `__int64 __fastcall(CWamAdmin *this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x1800021d0`
- `0x180003cdc`
- `0x180004864`
- `0x180004fd4`
- `0x180005cfc`
- `0x180007010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800022b4`
- `msvcrt!_wcsnicmp` at `0x1800022b4`
- `iisutil!PuDbgPrint` at `0x180002313`
- `iisutil!PuDbgPrint` at `0x180002374`
- `iisutil!PuDbgPrint` at `0x1800023b0`
- `iisutil!PuDbgPrint` at `0x180002452`
- `iisutil!PuDbgPrint` at `0x180002313`
- `iisutil!PuDbgPrint` at `0x180002374`
- `iisutil!PuDbgPrint` at `0x1800023b0`
- `iisutil!PuDbgPrint` at `0x180002452`

## string_xrefs

- `0x18000235d`: `Failed to Recover on path %S, hr = %08x\n`
- `0x18000243b`: `Failed to Recover on path %S, hr = %08x\n`
- `0x18000239e`: `Recover: GetPropPaths failed hr = %08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AppRecover(CWamAdmin *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  WamRegGlobal *v6; // rcx
  WamRegMetabaseConfig *v7; // rcx
  int v8; // r8d
  __int64 v9; // r15
  int v10; // eax
  WamRegGlobal *v11; // rcx
  int v12; // ebx
  const unsigned __int16 *v13; // rdi
  wchar_t *v14; // r14
  WamRegGlobal *v15; // rcx
  int v16; // r8d
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  unsigned __int16 *v20; // [rsp+40h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+38h] BYREF
  void *Block; // [rsp+98h] [rbp+48h] BYREF

  v20 = 0;
  if ( !a2 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(CWamAdmin *, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
             this,
             a2,
             &v20);
  if ( (int)result >= 0 )
  {
    WamRegGlobal::AcquireAdmWriteLock(v6);
    if ( a3 )
    {
      Block = 0;
      v9 = -1;
      do
        ++v9;
      while ( v20[v9] );
      v10 = WamRegMetabaseConfig::MDGetPropPaths(v7, v20, 0x838u, (unsigned __int16 **)&Block, (unsigned int *)&String1);
      v12 = v10;
      if ( v10 >= 0 && Block )
      {
        v13 = (const unsigned __int16 *)Block;
        String1 = 0;
        while ( *v13 && v12 >= 0 )
        {
          v12 = WamRegGlobal::ConstructFullPath(v11, v20, v9, v13, &String1);
          if ( v12 < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                644,
                "CWamAdmin::AppRecover",
                "Failed to Recover, hr = %08x\n",
                (_DWORD)v13);
          }
          else
          {
            v14 = String1;
            if ( _wcsnicmp(String1, L"/LM/W3SVC", 0xAu) )
            {
              v17 = WamRegGlobal::RecoverApp(v15, v14, v16);
              v12 = v17;
              if ( v17 < 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                    632,
                    "CWamAdmin::AppRecover",
                    "Failed to Recover on path %S, hr = %08x\n",
                    v14,
                    v17);
                break;
              }
            }
            operator delete(v14);
            String1 = 0;
          }
          v18 = -1;
          do
            ++v18;
          while ( v13[v18] );
          v13 += v18 + 1;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
          650,
          "CWamAdmin::AppRecover",
          "Recover: GetPropPaths failed hr = %08x\n",
          v10);
      }
      if ( Block )
        operator delete(Block);
      if ( v12 < 0 )
        goto LABEL_30;
    }
    else
    {
      v19 = WamRegGlobal::RecoverApp(v7, v20, v8);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
            667,
            "CWamAdmin::AppRecover",
            "Failed to Recover on path %S, hr = %08x\n",
            a2,
            v19);
        goto LABEL_30;
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 160LL))(WamRegMetabaseConfig::m_pMetabase);
LABEL_30:
    WamRegGlobal::ReleaseAdmWriteLock(v11);
    if ( v20 != a2 )
      operator delete(v20);
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x1800021d0  mov     [rsp-28h+arg_0], rbx
0x1800021d5  mov     [rsp-28h+arg_10], rdi
0x1800021da  push    rbp
0x1800021db  push    r12
0x1800021dd  push    r13
0x1800021df  push    r14
0x1800021e1  push    r15
0x1800021e3  mov     rbp, rsp
0x1800021e6  sub     rsp, 50h
0x1800021ea  xor     r13d, r13d
0x1800021ed  mov     ebx, r8d
0x1800021f0  mov     [rbp+var_10], r13
0x1800021f4  mov     r12, rdx
0x1800021f7  test    rdx, rdx
0x1800021fa  jnz     short loc_180002206
0x1800021fc  mov     eax, 80070057h
0x180002201  jmp     loc_1800023F4
0x180002206  mov     rax, [rcx]
0x180002209  lea     r8, [rbp+var_10]
0x18000220d  mov     rax, [rax+58h]
0x180002211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002216  test    eax, eax
0x180002218  js      loc_1800023F4
0x18000221e  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x180002223  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180002227  test    ebx, ebx
0x180002229  jz      loc_18000240E
0x18000222f  mov     [rbp+Block], r13
0x180002233  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002237  inc     r15
0x18000223a  cmp     [rdx+r15*2], r13w
0x18000223f  jnz     short loc_180002237
0x180002241  lea     rax, [rbp+String1]
0x180002245  mov     r8d, 838h; unsigned int
0x18000224b  lea     r9, [rbp+Block]; unsigned __int16 **
0x18000224f  mov     [rsp+50h+var_30], rax; unsigned int *
0x180002254  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x180002259  mov     ebx, eax
0x18000225b  test    eax, eax
0x18000225d  js      loc_18000237C
0x180002263  cmp     [rbp+Block], r13
0x180002267  jz      loc_18000237C
0x18000226d  mov     rdi, [rbp+Block]
0x180002271  mov     [rbp+String1], r13
0x180002275  jmp     loc_18000232F
0x18000227a  test    ebx, ebx
0x18000227c  js      loc_1800023B6
0x180002282  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180002286  lea     rax, [rbp+String1]
0x18000228a  mov     r9, rdi; unsigned __int16 *
0x18000228d  mov     [rsp+50h+var_30], rax; unsigned __int16 **
0x180002292  mov     r8d, r15d; unsigned int
0x180002295  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x18000229a  mov     ebx, eax
0x18000229c  test    eax, eax
0x18000229e  js      short loc_1800022DA
0x1800022a0  mov     r14, [rbp+String1]
0x1800022a4  lea     rdx, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x1800022ab  mov     rcx, r14; String1
0x1800022ae  mov     r8d, 0Ah; MaxCount
0x1800022b4  call    cs:__imp__wcsnicmp
0x1800022ba  test    eax, eax
0x1800022bc  jz      short loc_1800022CC
0x1800022be  mov     rdx, r14; unsigned __int16 *
0x1800022c1  call    ?RecoverApp@WamRegGlobal@@QEAAJPEBGH@Z; WamRegGlobal::RecoverApp(ushort const *,int)
0x1800022c6  mov     ebx, eax
0x1800022c8  test    eax, eax
0x1800022ca  js      short loc_18000233B
0x1800022cc  mov     rcx, r14; Block
0x1800022cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800022d4  mov     [rbp+String1], r13
0x1800022d8  jmp     short loc_180002319
0x1800022da  test    byte ptr cs:g_dwDebugFlags, 3
0x1800022e1  jz      short loc_180002319
0x1800022e3  mov     rcx, cs:g_pDebug
0x1800022ea  lea     r9, aCwamadminAppre; "CWamAdmin::AppRecover"
0x1800022f1  mov     [rsp+50h+var_20], eax
0x1800022f5  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800022fc  lea     rax, aFailedToRecove_0; "Failed to Recover, hr = %08x\n"
0x180002303  mov     [rsp+50h+var_28], rdi
0x180002308  mov     r8d, 284h
0x18000230e  mov     [rsp+50h+var_30], rax
0x180002313  call    cs:__imp_PuDbgPrint
0x180002319  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000231d  inc     rax
0x180002320  cmp     [rdi+rax*2], r13w
0x180002325  jnz     short loc_18000231D
0x180002327  lea     rdi, [rdi+rax*2]
0x18000232b  add     rdi, 2
0x18000232f  cmp     [rdi], r13w
0x180002333  jnz     loc_18000227A
0x180002339  jmp     short loc_1800023B6
0x18000233b  test    byte ptr cs:g_dwDebugFlags, 3
0x180002342  jz      short loc_1800023B6
0x180002344  mov     rcx, cs:g_pDebug
0x18000234b  lea     r9, aCwamadminAppre; "CWamAdmin::AppRecover"
0x180002352  mov     [rsp+50h+var_20], eax
0x180002356  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x18000235d  lea     rax, aFailedToRecove; "Failed to Recover on path %S, hr = %08x"...
0x180002364  mov     [rsp+50h+var_28], r14
0x180002369  mov     r8d, 278h
0x18000236f  mov     [rsp+50h+var_30], rax
0x180002374  call    cs:__imp_PuDbgPrint
0x18000237a  jmp     short loc_1800023B6
0x18000237c  test    byte ptr cs:g_dwDebugFlags, 3
0x180002383  jz      short loc_1800023B6
0x180002385  mov     rcx, cs:g_pDebug
0x18000238c  lea     r9, aCwamadminAppre; "CWamAdmin::AppRecover"
0x180002393  mov     dword ptr [rsp+50h+var_28], eax
0x180002397  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x18000239e  lea     rax, aRecoverGetprop; "Recover: GetPropPaths failed hr = %08x"...
0x1800023a5  mov     r8d, 28Ah
0x1800023ab  mov     [rsp+50h+var_30], rax
0x1800023b0  call    cs:__imp_PuDbgPrint
0x1800023b6  cmp     [rbp+Block], r13
0x1800023ba  jz      short loc_1800023C5
0x1800023bc  mov     rcx, [rbp+Block]; Block
0x1800023c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800023c5  test    ebx, ebx
0x1800023c7  js      short loc_1800023DF
0x1800023c9  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800023d0  mov     rax, [rcx]
0x1800023d3  mov     rax, [rax+0A0h]
0x1800023da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023df  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x1800023e4  mov     rcx, [rbp+var_10]; Block
0x1800023e8  cmp     rcx, r12
0x1800023eb  jz      short loc_1800023F2
0x1800023ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800023f2  mov     eax, ebx
0x1800023f4  lea     r11, [rsp+50h+var_s0]
0x1800023f9  mov     rbx, [r11+30h]
0x1800023fd  mov     rdi, [r11+40h]
0x180002401  mov     rsp, r11
0x180002404  pop     r15
0x180002406  pop     r14
0x180002408  pop     r13
0x18000240a  pop     r12
0x18000240c  pop     rbp
0x18000240d  retn
0x18000240e  call    ?RecoverApp@WamRegGlobal@@QEAAJPEBGH@Z; WamRegGlobal::RecoverApp(ushort const *,int)
0x180002413  mov     ebx, eax
0x180002415  test    eax, eax
0x180002417  jns     short loc_1800023C9
0x180002419  test    byte ptr cs:g_dwDebugFlags, 3
0x180002420  jz      short loc_1800023DF
0x180002422  mov     rcx, cs:g_pDebug
0x180002429  lea     r9, aCwamadminAppre; "CWamAdmin::AppRecover"
0x180002430  mov     [rsp+50h+var_20], eax
0x180002434  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x18000243b  lea     rax, aFailedToRecove; "Failed to Recover on path %S, hr = %08x"...
0x180002442  mov     [rsp+50h+var_28], r12
0x180002447  mov     r8d, 29Bh
0x18000244d  mov     [rsp+50h+var_30], rax
0x180002452  call    cs:__imp_PuDbgPrint
0x180002458  jmp     short loc_1800023DF
```
