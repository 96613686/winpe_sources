# CWamAdmin::AppUnLoad(ushort const *,int)

- ea: `0x180002460`
- end: `0x180002720`
- name: `?AppUnLoad@CWamAdmin@@UEAAJPEBGH@Z`
- size: `704`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x180002460`
- `0x180003b30`
- `0x180003cdc`
- `0x180004864`
- `0x180005654`
- `0x180005a50`
- `0x180005cfc`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800025b7`
- `iisutil!PuDbgPrint` at `0x1800026b2`
- `iisutil!PuDbgPrint` at `0x1800025b7`
- `iisutil!PuDbgPrint` at `0x1800026b2`

## string_xrefs

- `0x1800025a0`: `Insufficient Access to unload Application %S, hr = %08x\n`
- `0x180002689`: `Insufficient Access to unload Application %S, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AppUnLoad(CWamAdmin *this, const unsigned __int16 *a2, int a3)
{
  int HasAdminAccess; // r15d
  __int64 result; // rax
  WamRegGlobal *v8; // rcx
  int v9; // ebx
  WamRegMetabaseConfig *v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // r15
  int v13; // eax
  unsigned __int16 *v14; // r12
  unsigned __int16 *v15; // r14
  int v16; // r13d
  int v17; // eax
  unsigned int v18; // r8d
  wchar_t *v19; // rsi
  int v20; // eax
  __int64 v21; // rax
  int v22; // [rsp+40h] [rbp-20h] BYREF
  int v23; // [rsp+44h] [rbp-1Ch]
  void *Block; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v25; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+58h] BYREF

  v28 = 0;
  v27 = 0;
  if ( !a2 || !*a2 )
    return 2147942487LL;
  HasAdminAccess = WamRegMetabaseConfig::HasAdminAccess(this);
  v23 = HasAdminAccess;
  v22 = 0;
  result = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 2) + 72LL))((char *)this + 16, &v22);
  v9 = result;
  if ( (int)result >= 0 )
  {
    WamRegGlobal::AcquireAdmWriteLock(v8);
    if ( a3 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v25 = 0;
      v13 = WamRegMetabaseConfig::MDGetPropPaths(v10, a2, 0x838u, &v25, (unsigned int *)&Block);
      v14 = v25;
      v9 = v13;
      if ( v13 >= 0 )
      {
        v15 = v25;
        Block = 0;
        if ( *v25 )
        {
          do
          {
            if ( v9 < 0 )
              break;
            v16 = 1;
            v17 = WamRegGlobal::ConstructFullPath(v10, a2, v12, v15, (unsigned __int16 **)&Block);
            v19 = (wchar_t *)Block;
            v9 = v17;
            if ( v17 >= 0 && !v23 )
            {
              v20 = WamRegMetabaseConfig::MDGetDWORD(v10, (const unsigned __int16 *)Block, v18, &v27);
              v9 = v20;
              if ( v20 >= 0 && v27 == 2 )
              {
                v16 = 0;
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
                    410,
                    "CWamAdmin::AppUnLoad",
                    "Insufficient Access to unload Application %S, hr = %08x\n",
                    v19,
                    v20);
              }
            }
            if ( v22 == 1 )
            {
              CWamAdmin::RecycleAppPoolContainingApp(this, v19);
            }
            else if ( v9 >= 0 && v16 )
            {
              if ( g_pfnW3ServiceSink )
              {
                v9 = g_pfnW3ServiceSink((const char *)v19, 9u, &v28);
              }
              else
              {
                v28 = 5;
                v9 = 0;
              }
            }
            if ( v19 )
            {
              operator delete(v19);
              Block = 0;
            }
            v21 = -1;
            do
              ++v21;
            while ( v15[v21] );
            v15 += v21 + 1;
          }
          while ( *v15 );
          v14 = v25;
        }
      }
      if ( v14 )
        operator delete(v14);
    }
    else
    {
      if ( !HasAdminAccess )
      {
        v9 = WamRegMetabaseConfig::MDGetDWORD(v10, a2, v11, &v27);
        if ( v9 >= 0 && v27 == 2 )
        {
          v9 = -2147024891;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
              455,
              "CWamAdmin::AppUnLoad",
              "Insufficient Access to unload Application %S, hr = %08x\n",
              a2,
              -2147024891);
        }
      }
      if ( v22 == 1 )
      {
        CWamAdmin::RecycleAppPoolContainingApp(this, a2);
      }
      else if ( v9 >= 0 )
      {
        if ( g_pfnW3ServiceSink )
        {
          v9 = g_pfnW3ServiceSink((const char *)a2, 9u, &v28);
        }
        else
        {
          v28 = 5;
          v9 = 0;
        }
      }
    }
    WamRegGlobal::ReleaseAdmWriteLock(v10);
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180002460  mov     [rsp-38h+arg_10], rbx
0x180002465  mov     [rsp-38h+arg_0], rcx
0x18000246a  push    rbp
0x18000246b  push    rsi
0x18000246c  push    rdi
0x18000246d  push    r12
0x18000246f  push    r13
0x180002471  push    r14
0x180002473  push    r15
0x180002475  mov     rbp, rsp
0x180002478  sub     rsp, 60h
0x18000247c  xor     r13d, r13d
0x18000247f  mov     esi, r8d
0x180002482  mov     [rbp+arg_18], r13d
0x180002486  mov     rdi, rdx
0x180002489  mov     [rbp+arg_8], r13d
0x18000248d  mov     r14, rcx
0x180002490  test    rdx, rdx
0x180002493  jz      loc_180002703
0x180002499  cmp     [rdx], r13w
0x18000249d  jz      loc_180002703
0x1800024a3  call    ?HasAdminAccess@WamRegMetabaseConfig@@QEAAHXZ; WamRegMetabaseConfig::HasAdminAccess(void)
0x1800024a8  mov     r15d, eax
0x1800024ab  mov     [rbp+var_1C], eax
0x1800024ae  lea     rcx, [r14+10h]
0x1800024b2  mov     [rbp+var_20], r13d
0x1800024b6  mov     rax, [rcx]
0x1800024b9  lea     rdx, [rbp+var_20]
0x1800024bd  mov     rax, [rax+48h]
0x1800024c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024c6  mov     ebx, eax
0x1800024c8  test    eax, eax
0x1800024ca  js      loc_180002708
0x1800024d0  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x1800024d5  test    esi, esi
0x1800024d7  jz      loc_180002657
0x1800024dd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800024e1  inc     r15
0x1800024e4  cmp     [rdi+r15*2], r13w
0x1800024e9  jnz     short loc_1800024E1
0x1800024eb  lea     rax, [rbp+Block]
0x1800024ef  mov     [rbp+var_10], r13
0x1800024f3  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800024f7  mov     [rsp+60h+var_40], rax; unsigned int *
0x1800024fc  mov     r8d, 838h; unsigned int
0x180002502  mov     rdx, rdi; unsigned __int16 *
0x180002505  call    ?MDGetPropPaths@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAGPEAK@Z; WamRegMetabaseConfig::MDGetPropPaths(ushort const *,ulong,ushort * *,ulong *)
0x18000250a  mov     r12, [rbp+var_10]
0x18000250e  mov     ebx, eax
0x180002510  test    eax, eax
0x180002512  js      loc_180002606
0x180002518  mov     r14, r12
0x18000251b  mov     [rbp+Block], r13
0x18000251f  cmp     [r12], r13w
0x180002524  jz      loc_180002606
0x18000252a  mov     r12, [rbp+arg_0]
0x18000252e  test    ebx, ebx
0x180002530  js      loc_180002602
0x180002536  lea     rax, [rbp+Block]
0x18000253a  mov     r9, r14; unsigned __int16 *
0x18000253d  mov     r8d, r15d; unsigned int
0x180002540  mov     [rsp+60h+var_40], rax; unsigned __int16 **
0x180002545  mov     rdx, rdi; unsigned __int16 *
0x180002548  mov     r13d, 1
0x18000254e  call    ?ConstructFullPath@WamRegGlobal@@QEAAJPEBGK0PEAPEAG@Z; WamRegGlobal::ConstructFullPath(ushort const *,ulong,ushort const *,ushort * *)
0x180002553  mov     rsi, [rbp+Block]
0x180002557  mov     ebx, eax
0x180002559  test    eax, eax
0x18000255b  js      short loc_1800025BD
0x18000255d  cmp     [rbp+var_1C], 0
0x180002561  jnz     short loc_1800025BD
0x180002563  lea     r9, [rbp+arg_8]; unsigned int *
0x180002567  mov     rdx, rsi; unsigned __int16 *
0x18000256a  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x18000256f  mov     ebx, eax
0x180002571  test    eax, eax
0x180002573  js      short loc_1800025BD
0x180002575  cmp     [rbp+arg_8], 2
0x180002579  jnz     short loc_1800025BD
0x18000257b  xor     r13d, r13d
0x18000257e  test    byte ptr cs:g_dwDebugFlags, 3
0x180002585  jz      short loc_1800025BD
0x180002587  mov     rcx, cs:g_pDebug
0x18000258e  lea     r9, aCwamadminAppun; "CWamAdmin::AppUnLoad"
0x180002595  mov     [rsp+60h+var_30], eax
0x180002599  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800025a0  lea     rax, aInsufficientAc; "Insufficient Access to unload Applicati"...
0x1800025a7  mov     [rsp+60h+var_38], rsi
0x1800025ac  mov     r8d, 19Ah
0x1800025b2  mov     [rsp+60h+var_40], rax
0x1800025b7  call    cs:__imp_PuDbgPrint
0x1800025bd  cmp     [rbp+var_20], 1
0x1800025c1  jnz     short loc_18000261C
0x1800025c3  mov     rdx, rsi; unsigned __int16 *
0x1800025c6  mov     rcx, r12; this
0x1800025c9  call    ?RecycleAppPoolContainingApp@CWamAdmin@@AEAAJPEBG@Z; CWamAdmin::RecycleAppPoolContainingApp(ushort const *)
0x1800025ce  xor     r13d, r13d
0x1800025d1  test    rsi, rsi
0x1800025d4  jz      short loc_1800025E2
0x1800025d6  mov     rcx, rsi; Block
0x1800025d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025de  mov     [rbp+Block], r13
0x1800025e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800025e6  inc     rax
0x1800025e9  cmp     [r14+rax*2], r13w
0x1800025ee  jnz     short loc_1800025E6
0x1800025f0  lea     r14, [r14+rax*2]
0x1800025f4  add     r14, 2
0x1800025f8  cmp     [r14], r13w
0x1800025fc  jnz     loc_18000252E
0x180002602  mov     r12, [rbp+var_10]
0x180002606  test    r12, r12
0x180002609  jz      loc_1800026FA
0x18000260f  mov     rcx, r12; Block
0x180002612  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002617  jmp     loc_1800026FA
0x18000261c  test    ebx, ebx
0x18000261e  js      short loc_1800025CE
0x180002620  test    r13d, r13d
0x180002623  jz      short loc_1800025CE
0x180002625  mov     rax, cs:?g_pfnW3ServiceSink@@3P6AJPEBDKPEAK@ZEA; long (*g_pfnW3ServiceSink)(char const *,ulong,ulong *)
0x18000262c  xor     r13d, r13d
0x18000262f  test    rax, rax
0x180002632  jz      short loc_180002648
0x180002634  lea     r8, [rbp+arg_18]
0x180002638  mov     rcx, rsi
0x18000263b  lea     edx, [r13+9]
0x18000263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002644  mov     ebx, eax
0x180002646  jmp     short loc_1800025D1
0x180002648  mov     [rbp+arg_18], 5
0x18000264f  mov     ebx, r13d
0x180002652  jmp     loc_1800025D1
0x180002657  test    r15d, r15d
0x18000265a  jnz     short loc_1800026B8
0x18000265c  lea     r9, [rbp+arg_8]; unsigned int *
0x180002660  mov     rdx, rdi; unsigned __int16 *
0x180002663  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180002668  mov     ebx, eax
0x18000266a  test    eax, eax
0x18000266c  js      short loc_1800026B8
0x18000266e  cmp     [rbp+arg_8], 2
0x180002672  jnz     short loc_1800026B8
0x180002674  test    byte ptr cs:g_dwDebugFlags, 3
0x18000267b  mov     ebx, 80070005h
0x180002680  jz      short loc_1800026B8
0x180002682  mov     rcx, cs:g_pDebug
0x180002689  lea     rax, aInsufficientAc; "Insufficient Access to unload Applicati"...
0x180002690  mov     [rsp+60h+var_30], ebx
0x180002694  lea     r9, aCwamadminAppun; "CWamAdmin::AppUnLoad"
0x18000269b  mov     [rsp+60h+var_38], rdi
0x1800026a0  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x1800026a7  mov     r8d, 1C7h
0x1800026ad  mov     [rsp+60h+var_40], rax
0x1800026b2  call    cs:__imp_PuDbgPrint
0x1800026b8  cmp     [rbp+var_20], 1
0x1800026bc  jnz     short loc_1800026CB
0x1800026be  mov     rdx, rdi; unsigned __int16 *
0x1800026c1  mov     rcx, r14; this
0x1800026c4  call    ?RecycleAppPoolContainingApp@CWamAdmin@@AEAAJPEBG@Z; CWamAdmin::RecycleAppPoolContainingApp(ushort const *)
0x1800026c9  jmp     short loc_1800026FA
0x1800026cb  test    ebx, ebx
0x1800026cd  js      short loc_1800026FA
0x1800026cf  mov     rax, cs:?g_pfnW3ServiceSink@@3P6AJPEBDKPEAK@ZEA; long (*g_pfnW3ServiceSink)(char const *,ulong,ulong *)
0x1800026d6  test    rax, rax
0x1800026d9  jz      short loc_1800026F0
0x1800026db  lea     r8, [rbp+arg_18]
0x1800026df  mov     edx, 9
0x1800026e4  mov     rcx, rdi
0x1800026e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ec  mov     ebx, eax
0x1800026ee  jmp     short loc_1800026FA
0x1800026f0  mov     [rbp+arg_18], 5
0x1800026f7  mov     ebx, r13d
0x1800026fa  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x1800026ff  mov     eax, ebx
0x180002701  jmp     short loc_180002708
0x180002703  mov     eax, 80070057h
0x180002708  mov     rbx, [rsp+60h+arg_10]
0x180002710  add     rsp, 60h
0x180002714  pop     r15
0x180002716  pop     r14
0x180002718  pop     r13
0x18000271a  pop     r12
0x18000271c  pop     rdi
0x18000271d  pop     rsi
0x18000271e  pop     rbp
0x18000271f  retn
```
