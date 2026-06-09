# DeviceListManager::CreateDeviceInformationArray(ulong,ulong *,IWiaPropertyStorage * * *,ulong *,ulong)

- ea: `0x180007324`
- end: `0x180007871`
- name: `?CreateDeviceInformationArray@DeviceListManager@@QEAAJKPEAKPEAPEAPEAUIWiaPropertyStorage@@0K@Z`
- size: `1357`
- prototype: `__int64 __fastcall(DeviceListManager *__hidden this, unsigned int, unsigned int *, struct IWiaPropertyStorage ***, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800070fc`

## callees

- `0x180007324`
- `0x180007878`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180023f88`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180034558`
- `0x180034658`
- `0x180078010`

## string_xrefs

- `0x1800073f8`: `DeviceListManager::CreateDeviceInformationArray`
- `0x1800074d0`: `DeviceListManager::CreateDeviceInformationArray`
- `0x1800076f6`: `DeviceListManager::CreateDeviceInformationArray`
- `0x18000772f`: `DeviceListManager::CreateDeviceInformationArray`
- `0x1800077a2`: `DeviceListManager::CreateDeviceInformationArray`
- `0x1800077f1`: `DeviceListManager::CreateDeviceInformationArray`
- `0x18000766b`: `The DeviceListManager Could not create the device information storage - we are out of memory`
- `0x18000768d`: `The DeviceListManager Could not create the device information storage - we are out of memory`
- `0x1800076e8`: `The DeviceListManager was asked to create the WIA Device Information Storages, but the count parameter was NULL!`
- `0x180007713`: `The DeviceListManager was asked to create the WIA Device Information Storages, but the count parameter was NULL!`
- `0x180007721`: `The DeviceListManager was asked to create the WIA Device Information Storages, but the address of the dev. info array was NULL!`
- `0x18000774c`: `The DeviceListManager was asked to create the WIA Device Information Storages, but the address of the dev. info array was NULL!`
- `0x180007796`: `The DeviceListManager could not create the array of Device Information Storages because we are out of memory`
- `0x1800077bf`: `The DeviceListManager could not create the array of Device Information Storages because we are out of memory`
- `0x1800077e5`: `The DeviceListManager failed to copy the device list when asked to create the WIA Device Information Storages`
- `0x18000780e`: `The DeviceListManager failed to copy the device list when asked to create the WIA Device Information Storages`

## pseudocode

```c
__int64 __fastcall DeviceListManager::CreateDeviceInformationArray(
        DeviceListManager *this,
        __int64 a2,
        unsigned int *a3,
        struct IWiaPropertyStorage ***a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int *v6; // rax
  int v7; // r12d
  __int64 v8; // rbx
  struct IWiaPropertyStorage **v9; // rax
  struct IWiaPropertyStorage **v10; // r13
  _QWORD *v11; // rax
  _QWORD *v12; // r14
  signed int v13; // ebx
  __int64 v14; // r15
  _QWORD *v15; // rcx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  char *v19; // rbx
  void *v20; // rdx
  void **lpMem; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // esi
  void *v25; // rcx
  __int64 v27; // rax
  __int64 v28; // r9
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  int v44; // eax
  int v45; // ebx
  struct IWiaPropertyStorage *v46; // rcx
  char *v47; // rbx
  void *v48; // rdx
  void **v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  char *v52; // rbx
  void *v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  void **v61; // rax
  void *v62; // rdx
  __int64 v63; // rcx
  signed int v64; // [rsp+30h] [rbp-40h]
  int v65; // [rsp+34h] [rbp-3Ch]
  __int64 v66; // [rsp+38h] [rbp-38h]
  _QWORD *v67; // [rsp+40h] [rbp-30h]
  void **v68; // [rsp+48h] [rbp-28h] BYREF
  void *v69[2]; // [rsp+50h] [rbp-20h]
  int v70; // [rsp+60h] [rbp-10h]
  unsigned int *v71; // [rsp+C0h] [rbp+50h] BYREF
  struct IWiaPropertyStorage ***v72; // [rsp+C8h] [rbp+58h]

  v72 = a4;
  v71 = a3;
  v70 = 0;
  v68 = &CSimpleStack<USDWrapper *>::`vftable';
  *(_OWORD *)v69 = 0;
  if ( !a3 )
  {
    v47 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "The DeviceListManager was asked to create the WIA Device Information Storages, but the count parameter was NULL!");
    WriteDbgTraceWarningWI("DeviceListManager::CreateDeviceInformationArray", v47);
    WiaTrcLib::Free((WiaTrcLib *)v47, v48);
    v49 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "The DeviceListManager was asked to create the WIA Device Information Storages, but the count parameter was NULL!");
LABEL_44:
    WiaTrace_ProcessTrace_Ex(v51, v50, (void *)"DeviceListManager::CreateDeviceInformationArray", 2, v49);
    return (unsigned int)-2147467261;
  }
  *a3 = 0;
  if ( !a4 )
  {
    v52 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "The DeviceListManager was asked to create the WIA Device Information Storages, but the address of th"
                    "e dev. info array was NULL!");
    WriteDbgTraceWarningWI("DeviceListManager::CreateDeviceInformationArray", v52);
    WiaTrcLib::Free((WiaTrcLib *)v52, v53);
    v49 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "The DeviceListManager was asked to create the WIA Device Information Storages, but the address of t"
                     "he dev. info array was NULL!");
    goto LABEL_44;
  }
  v6 = a5;
  *a4 = 0;
  if ( v6 )
    *v6 = 0;
  if ( (int)DeviceListManager::CopyDeviceList(this, a2, &v68, a6, 1) < 0 )
  {
    v59 = (char *)WiaTrace_TraceLog("The DeviceListManager failed to copy the device list when asked to create the WIA De"
                                    "vice Information Storages");
    WriteDbgTraceErrorWI("DeviceListManager::CreateDeviceInformationArray", v59);
    WiaTrcLib::Free((WiaTrcLib *)v59, v60);
    v61 = (void **)WiaTrace_Trace(
                     "The DeviceListManager failed to copy the device list when asked to create the WIA Device Information Storages");
    WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"DeviceListManager::CreateDeviceInformationArray", 1, v61);
    v7 = v70;
    v24 = -2147418113;
  }
  else
  {
    v7 = v70;
    v65 = v70;
    if ( v70 < 1 )
    {
      v19 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "There are no devices to enumerate");
      WriteDbgTraceInfoWI("DeviceListManager::CreateDeviceInformationArray", v19);
      WiaTrcLib::Free((WiaTrcLib *)v19, v20);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(0x80000000LL, 0, "There are no devices to enumerate");
      WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"DeviceListManager::CreateDeviceInformationArray", 4, lpMem);
      v24 = 1;
    }
    else
    {
      v8 = v70;
      v9 = (struct IWiaPropertyStorage **)operator new[](saturated_mul(v70, 8u));
      v10 = v9;
      if ( v9 )
      {
        memset_0(v9, 0, 8 * v8);
        v11 = v69[1];
        v12 = v69[0];
        v13 = 0;
        v67 = v69[1];
        while ( 1 )
        {
          v64 = v13;
          if ( !v7 )
          {
            v24 = 0;
            *v71 = v13;
            *v72 = v10;
            goto LABEL_27;
          }
          if ( v12 )
          {
            v14 = v12[1];
            v15 = v12;
            v16 = 0;
            while ( v15[1] != v14 )
            {
              v16 = v15;
              v15 = (_QWORD *)*v15;
              if ( !v15 )
                goto LABEL_20;
            }
            if ( v15 == v11 )
              v11 = v16;
            v67 = v11;
            v69[1] = v11;
            if ( v15 == v12 )
            {
              v12 = (_QWORD *)*v15;
              v69[0] = *(void **)v15;
            }
            if ( v16 )
              *v16 = *v15;
            operator delete(v15, 0x10u);
            v70 = --v7;
LABEL_20:
            if ( v14 )
            {
              v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 144LL))(v14);
              v18 = a5 == 0;
              v10[v13] = (struct IWiaPropertyStorage *)v17;
              if ( !v18 )
              {
                if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) )
                {
                  v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 152LL))(v14);
                  v66 = v27;
                  if ( v27 )
                  {
                    v28 = *(_QWORD *)(v27 + 2384);
                    if ( *(_WORD *)(v27 + 42) == 1 )
                    {
                      v29 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Including %ws", v28);
                      WriteDbgTraceInfoWI("DeviceListManager::CreateDeviceInformationArray", v29);
                      WiaTrcLib::Free((WiaTrcLib *)v29, v30);
                      v31 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                                       0x80000000LL,
                                       0,
                                       "Including %ws",
                                       *(_QWORD *)(v66 + 2384));
                      WiaTrace_ProcessTrace_Ex(
                        v33,
                        v32,
                        (void *)"DeviceListManager::CreateDeviceInformationArray",
                        4,
                        v31);
                      ++*a5;
                    }
                    else
                    {
                      v34 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "Skipping %ws", v28);
                      WriteDbgTraceInfoWI("DeviceListManager::CreateDeviceInformationArray", v34);
                      WiaTrcLib::Free((WiaTrcLib *)v34, v35);
                      v36 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                                       0x80000000LL,
                                       0,
                                       "Skipping %ws",
                                       *(_QWORD *)(v66 + 2384));
                      WiaTrace_ProcessTrace_Ex(
                        v38,
                        v37,
                        (void *)"DeviceListManager::CreateDeviceInformationArray",
                        4,
                        v36);
                    }
                    v13 = v64;
                  }
                }
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
              if ( !v10[v13] )
                break;
            }
          }
          v11 = v67;
          ++v13;
        }
        v39 = (char *)WiaTrace_TraceLog("The DeviceListManager Could not create the device information storage - we are out of memory");
        WriteDbgTraceErrorWI("DeviceListManager::CreateDeviceInformationArray", v39);
        WiaTrcLib::Free((WiaTrcLib *)v39, v40);
        v41 = (void **)WiaTrace_Trace("The DeviceListManager Could not create the device information storage - we are out of memory");
        WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"DeviceListManager::CreateDeviceInformationArray", 1, v41);
        v44 = v65;
        v45 = 0;
        v24 = -2147024882;
        do
        {
          v46 = v10[v45];
          if ( v46 )
          {
            ((void (__fastcall *)(struct IWiaPropertyStorage *))v46->lpVtbl->Release)(v46);
            v44 = v65;
            v10[v45] = 0;
          }
          ++v45;
        }
        while ( v45 < v44 );
        goto LABEL_26;
      }
      v54 = (char *)WiaTrace_TraceLog("The DeviceListManager could not create the array of Device Information Storages be"
                                      "cause we are out of memory");
      WriteDbgTraceErrorWI("DeviceListManager::CreateDeviceInformationArray", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v56 = (void **)WiaTrace_Trace(
                       "The DeviceListManager could not create the array of Device Information Storages because we are out of memory");
      WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"DeviceListManager::CreateDeviceInformationArray", 1, v56);
      v24 = -2147024882;
    }
  }
  v12 = v69[0];
LABEL_26:
  if ( v7 )
  {
    do
    {
      v71 = 0;
      CSimpleStack<USDWrapper *>::Pop(&v68, &v71);
      if ( v71 )
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v71 + 16LL))(v71);
    }
    while ( v70 );
    v12 = v69[0];
  }
LABEL_27:
  while ( v12 )
  {
    v25 = v12;
    v12 = (_QWORD *)*v12;
    operator delete(v25, 0x10u);
  }
  return v24;
}

```

## disassembly

```asm
0x180007324  mov     [rsp-38h+arg_0], rbx
0x180007329  mov     [rsp-38h+arg_18], r9
0x18000732e  mov     [rsp-38h+arg_10], r8
0x180007333  push    rbp
0x180007334  push    rsi
0x180007335  push    rdi
0x180007336  push    r12
0x180007338  push    r13
0x18000733a  push    r14
0x18000733c  push    r15
0x18000733e  mov     rbp, rsp
0x180007341  sub     rsp, 70h
0x180007345  mov     rax, r8
0x180007348  mov     r15, r9
0x18000734b  xor     r9d, r9d
0x18000734e  lea     r8, ??_7?$CSimpleStack@PEAVUSDWrapper@@@@6B@; const CSimpleStack<USDWrapper *>::`vftable'
0x180007355  mov     [rbp+var_10], r9d
0x180007359  xorps   xmm0, xmm0
0x18000735c  mov     [rbp+var_28], r8
0x180007360  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180007365  test    rax, rax
0x180007368  jz      loc_1800076E3
0x18000736e  mov     [rax], r9d
0x180007371  test    r15, r15
0x180007374  jz      loc_18000771C
0x18000737a  mov     rax, [rbp+arg_20]
0x18000737e  mov     [r15], r9
0x180007381  test    rax, rax
0x180007384  jz      short loc_180007389
0x180007386  mov     [rax], r9d
0x180007389  mov     r9d, [rbp+arg_28]
0x18000738d  lea     r8, [rbp+var_28]
0x180007391  mov     edi, 1
0x180007396  mov     dword ptr [rsp+70h+lpMem], edi
0x18000739a  call    ?CopyDeviceList@DeviceListManager@@QEAAJJAEAV?$CSimpleLinkedList@PEAVUSDWrapper@@@@KH@Z; DeviceListManager::CopyDeviceList(long,CSimpleLinkedList<USDWrapper *> &,ulong,int)
0x18000739f  test    eax, eax
0x1800073a1  js      loc_1800077E5
0x1800073a7  movsxd  r12, [rbp+var_10]
0x1800073ab  mov     rax, r12
0x1800073ae  mov     [rbp+var_3C], eax
0x1800073b1  cmp     r12d, edi
0x1800073b4  jl      loc_1800074B9
0x1800073ba  mov     rbx, rax
0x1800073bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800073c4  lea     eax, [rdi+7]
0x1800073c7  mul     rbx
0x1800073ca  cmovb   rax, rcx
0x1800073ce  mov     rcx, rax; unsigned __int64
0x1800073d1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800073d6  mov     r13, rax
0x1800073d9  test    rax, rax
0x1800073dc  jz      loc_180007796
0x1800073e2  lea     r8, ds:0[rbx*8]; Size
0x1800073ea  xor     edx, edx; Val
0x1800073ec  mov     rcx, rax; void *
0x1800073ef  call    memset_0
0x1800073f4  mov     rax, [rbp+var_20+8]
0x1800073f8  lea     rsi, aDevicelistmana_5; "DeviceListManager::CreateDeviceInformat"...
0x1800073ff  mov     r14, [rbp+var_20]
0x180007403  xor     ebx, ebx
0x180007405  mov     [rbp+var_30], rax
0x180007409  mov     [rbp+var_40], ebx
0x18000740c  test    r12d, r12d
0x18000740f  jz      loc_180007557
0x180007415  test    r14, r14
0x180007418  jz      loc_1800074AE
0x18000741e  mov     r15, [r14+8]
0x180007422  mov     rcx, r14; void *
0x180007425  xor     edx, edx
0x180007427  cmp     [rcx+8], r15
0x18000742b  jnz     loc_180007777
0x180007431  cmp     rcx, rax
0x180007434  cmovz   rax, rdx
0x180007438  mov     [rbp+var_30], rax
0x18000743c  mov     [rbp+var_20+8], rax
0x180007440  cmp     rcx, r14
0x180007443  jnz     short loc_18000744C
0x180007445  mov     r14, [rcx]
0x180007448  mov     [rbp+var_20], r14
0x18000744c  test    rdx, rdx
0x18000744f  jnz     loc_18000778B
0x180007455  mov     edx, 10h; unsigned __int64
0x18000745a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000745f  sub     r12d, edi
0x180007462  mov     [rbp+var_10], r12d
0x180007466  test    r15, r15
0x180007469  jz      short loc_1800074AE
0x18000746b  mov     rax, [r15]
0x18000746e  mov     rcx, r15
0x180007471  mov     rax, [rax+90h]
0x180007478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747d  cmp     [rbp+arg_20], 0
0x180007482  movsxd  rcx, ebx
0x180007485  mov     [r13+rcx*8+0], rax
0x18000748a  jnz     loc_180007568
0x180007490  mov     rax, [r15]
0x180007493  mov     rcx, r15
0x180007496  mov     rax, [rax+10h]
0x18000749a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749f  movsxd  rax, ebx
0x1800074a2  cmp     qword ptr [r13+rax*8+0], 0
0x1800074a8  jz      loc_18000766B
0x1800074ae  mov     rax, [rbp+var_30]
0x1800074b2  add     ebx, edi
0x1800074b4  jmp     loc_180007409
0x1800074b9  mov     r14d, 80000000h
0x1800074bf  lea     r8, aThereAreNoDevi; "There are no devices to enumerate"
0x1800074c6  mov     ecx, r14d
0x1800074c9  xor     edx, edx
0x1800074cb  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800074d0  lea     rsi, aDevicelistmana_5; "DeviceListManager::CreateDeviceInformat"...
0x1800074d7  mov     rdx, rax; char *
0x1800074da  mov     rcx, rsi; char *
0x1800074dd  mov     rbx, rax
0x1800074e0  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800074e5  mov     rcx, rbx; this
0x1800074e8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800074ed  lea     r8, aThereAreNoDevi; "There are no devices to enumerate"
0x1800074f4  xor     edx, edx
0x1800074f6  mov     ecx, r14d
0x1800074f9  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800074fe  mov     r9d, 4; int
0x180007504  mov     [rsp+70h+lpMem], rax; lpMem
0x180007509  mov     r8, rsi; int
0x18000750c  call    WiaTrace_ProcessTrace_Ex
0x180007511  mov     esi, edi
0x180007513  mov     r14, [rbp+var_20]
0x180007517  test    r12d, r12d
0x18000751a  jnz     loc_180007838
0x180007520  test    r14, r14
0x180007523  jz      short loc_18000753D
0x180007525  mov     rbx, [r14]
0x180007528  mov     rcx, r14; void *
0x18000752b  mov     edx, 10h; unsigned __int64
0x180007530  mov     r14, rbx
0x180007533  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007538  test    rbx, rbx
0x18000753b  jnz     short loc_180007525
0x18000753d  mov     rbx, [rsp+70h+arg_0]
0x180007545  mov     eax, esi
0x180007547  add     rsp, 70h
0x18000754b  pop     r15
0x18000754d  pop     r14
0x18000754f  pop     r13
0x180007551  pop     r12
0x180007553  pop     rdi
0x180007554  pop     rsi
0x180007555  pop     rbp
0x180007556  retn
0x180007557  mov     rax, [rbp+arg_10]
0x18000755b  xor     esi, esi
0x18000755d  mov     [rax], ebx
0x18000755f  mov     rax, [rbp+arg_18]
0x180007563  mov     [rax], r13
0x180007566  jmp     short loc_180007520
0x180007568  mov     rax, [r15]
0x18000756b  mov     rcx, r15
0x18000756e  mov     rax, [rax+0A0h]
0x180007575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757a  test    eax, eax
0x18000757c  jz      loc_180007490
0x180007582  mov     rax, [r15]
0x180007585  mov     rcx, r15
0x180007588  mov     rax, [rax+98h]
0x18000758f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007594  mov     [rbp+var_38], rax
0x180007598  test    rax, rax
0x18000759b  jz      loc_180007490
0x1800075a1  mov     r9, [rax+950h]
0x1800075a8  xor     edx, edx
0x1800075aa  mov     ecx, 80000000h
0x1800075af  cmp     di, [rax+2Ah]
0x1800075b3  jnz     short loc_180007616
0x1800075b5  lea     r8, aIncludingWs; "Including %ws"
0x1800075bc  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800075c1  mov     rdx, rax; char *
0x1800075c4  mov     rcx, rsi; char *
0x1800075c7  mov     rbx, rax
0x1800075ca  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800075cf  mov     rcx, rbx; this
0x1800075d2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800075d7  mov     r9, [rbp+var_38]
0x1800075db  lea     r8, aIncludingWs; "Including %ws"
0x1800075e2  xor     edx, edx
0x1800075e4  mov     ecx, 80000000h
0x1800075e9  mov     r9, [r9+950h]
0x1800075f0  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800075f5  mov     r9d, 4; int
0x1800075fb  mov     [rsp+70h+lpMem], rax; lpMem
0x180007600  mov     r8, rsi; int
0x180007603  call    WiaTrace_ProcessTrace_Ex
0x180007608  mov     rax, [rbp+arg_20]
0x18000760c  add     [rax], edi
0x18000760e  mov     ebx, [rbp+var_40]
0x180007611  jmp     loc_180007490
0x180007616  lea     r8, aSkippingWs; "Skipping %ws"
0x18000761d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180007622  mov     rdx, rax; char *
0x180007625  mov     rcx, rsi; char *
0x180007628  mov     rbx, rax
0x18000762b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180007630  mov     rcx, rbx; this
0x180007633  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180007638  mov     r9, [rbp+var_38]
0x18000763c  lea     r8, aSkippingWs; "Skipping %ws"
0x180007643  xor     edx, edx
0x180007645  mov     ecx, 80000000h
0x18000764a  mov     r9, [r9+950h]
0x180007651  call    WiaTrace_TraceWithSubCompTraceLevel
0x180007656  mov     r9d, 4; int
0x18000765c  mov     [rsp+70h+lpMem], rax; lpMem
0x180007661  mov     r8, rsi; int
0x180007664  call    WiaTrace_ProcessTrace_Ex
0x180007669  jmp     short loc_18000760E
0x18000766b  lea     rcx, aTheDevicelistm_4; "The DeviceListManager Could not create "...
0x180007672  call    WiaTrace_TraceLog
0x180007677  mov     rdx, rax; char *
0x18000767a  mov     rcx, rsi; char *
0x18000767d  mov     rbx, rax
0x180007680  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180007685  mov     rcx, rbx; this
0x180007688  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000768d  lea     rcx, aTheDevicelistm_4; "The DeviceListManager Could not create "...
0x180007694  call    WiaTrace_Trace
0x180007699  mov     r9d, edi; int
0x18000769c  mov     [rsp+70h+lpMem], rax; lpMem
0x1800076a1  mov     r8, rsi; int
0x1800076a4  call    WiaTrace_ProcessTrace_Ex
0x1800076a9  mov     eax, [rbp+var_3C]
0x1800076ac  xor     ebx, ebx
0x1800076ae  mov     esi, 8007000Eh
0x1800076b3  movsxd  r15, ebx
0x1800076b6  mov     rcx, [r13+r15*8+0]
0x1800076bb  test    rcx, rcx
0x1800076be  jz      short loc_1800076D8
0x1800076c0  mov     rax, [rcx]
0x1800076c3  mov     rax, [rax+10h]
0x1800076c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076cc  mov     eax, [rbp+var_3C]
0x1800076cf  mov     qword ptr [r13+r15*8+0], 0
0x1800076d8  add     ebx, edi
0x1800076da  cmp     ebx, eax
0x1800076dc  jl      short loc_1800076B3
0x1800076de  jmp     loc_180007517
0x1800076e3  mov     edi, 1
0x1800076e8  lea     rdx, aTheDevicelistm; "The DeviceListManager was asked to crea"...
0x1800076ef  mov     ecx, edi
0x1800076f1  call    WiaTrace_TraceLogWithSubComp
0x1800076f6  lea     rsi, aDevicelistmana_5; "DeviceListManager::CreateDeviceInformat"...
0x1800076fd  mov     rdx, rax; char *
0x180007700  mov     rcx, rsi; char *
0x180007703  mov     rbx, rax
0x180007706  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000770b  mov     rcx, rbx; this
0x18000770e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180007713  lea     rdx, aTheDevicelistm; "The DeviceListManager was asked to crea"...
0x18000771a  jmp     short loc_180007753
0x18000771c  mov     edi, 1
0x180007721  lea     rdx, aTheDevicelistm_16; "The DeviceListManager was asked to crea"...
0x180007728  mov     ecx, edi
0x18000772a  call    WiaTrace_TraceLogWithSubComp
0x18000772f  lea     rsi, aDevicelistmana_5; "DeviceListManager::CreateDeviceInformat"...
0x180007736  mov     rdx, rax; char *
0x180007739  mov     rcx, rsi; char *
0x18000773c  mov     rbx, rax
0x18000773f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180007744  mov     rcx, rbx; this
0x180007747  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000774c  lea     rdx, aTheDevicelistm_16; "The DeviceListManager was asked to crea"...
0x180007753  mov     ecx, edi
0x180007755  call    WiaTrace_TraceWithSubComp
0x18000775a  mov     r9d, 2; int
0x180007760  mov     [rsp+70h+lpMem], rax; lpMem
0x180007765  mov     r8, rsi; int
0x180007768  call    WiaTrace_ProcessTrace_Ex
0x18000776d  mov     esi, 80004003h
0x180007772  jmp     loc_18000753D
0x180007777  mov     rdx, rcx
0x18000777a  mov     rcx, [rcx]
0x18000777d  test    rcx, rcx
0x180007780  jnz     loc_180007427
0x180007786  jmp     loc_180007466
0x18000778b  mov     rax, [rcx]
0x18000778e  mov     [rdx], rax
0x180007791  jmp     loc_180007455
0x180007796  lea     rcx, aTheDevicelistm_2; "The DeviceListManager could not create "...
0x18000779d  call    WiaTrace_TraceLog
0x1800077a2  lea     rsi, aDevicelistmana_5; "DeviceListManager::CreateDeviceInformat"...
0x1800077a9  mov     rdx, rax; char *
0x1800077ac  mov     rcx, rsi; char *
0x1800077af  mov     rbx, rax
0x1800077b2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800077b7  mov     rcx, rbx; this
0x1800077ba  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800077bf  lea     rcx, aTheDevicelistm_2; "The DeviceListManager could not create "...
0x1800077c6  call    WiaTrace_Trace
0x1800077cb  mov     r9d, edi; int
0x1800077ce  mov     [rsp+70h+lpMem], rax; lpMem
0x1800077d3  mov     r8, rsi; int
0x1800077d6  call    WiaTrace_ProcessTrace_Ex
  ... truncated ...
```
