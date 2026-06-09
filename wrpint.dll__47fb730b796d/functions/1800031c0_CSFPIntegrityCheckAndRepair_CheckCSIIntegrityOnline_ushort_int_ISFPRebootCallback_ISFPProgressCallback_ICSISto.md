# CSFPIntegrityCheckAndRepair::CheckCSIIntegrityOnline(ushort *,int,ISFPRebootCallback *,ISFPProgressCallback *,ICSIStore2 *,IStore2 *,ICSIInventory *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x1800031c0`
- end: `0x1800036cb`
- name: `?CheckCSIIntegrityOnline@CSFPIntegrityCheckAndRepair@@EEAAJPEAGHPEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAUICSIStore2@@PEAUIStore2@@PEAUICSIInventory@@PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAK@Z`
- size: `1291`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this, unsigned __int16 *, unsigned int, struct ISFPRebootCallback *, struct ISFPProgressCallback *, struct ICSIStore2 *, struct IStore2 *, struct ICSIInventory *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800029a4`
- `0x1800031c0`
- `0x18000423c`
- `0x1800043ac`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckCSIIntegrityOnline(
        CSFPIntegrityCheckAndRepair *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ISFPRebootCallback *a4,
        struct ISFPProgressCallback *a5,
        struct ICSIStore2 *a6,
        struct IStore2 *a7,
        struct ICSIInventory *a8,
        int *a9,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a10,
        unsigned int *a11)
{
  int v11; // r14d
  int IsBootRecovery; // ebx
  struct ICSIStore2 *v14; // rsi
  __int64 v15; // rax
  int v16; // eax
  bool i; // sf
  __int64 (__fastcall *v18)(CSFPIntegrityCheckAndRepair *, unsigned __int16 *, _QWORD, struct ISFPRebootCallback *, struct ISFPProgressCallback *, struct ICSIStore2 *, struct IStore2 *, GUID *, __int64, struct ICSIRepairTransaction *, __int64 *, int, int *, int *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *); // rax
  int v19; // eax
  __int64 v20; // rcx
  struct ICSIRepairTransaction *v21; // rcx
  int v23; // [rsp+90h] [rbp-80h] BYREF
  struct IStore2 *v24; // [rsp+98h] [rbp-78h]
  struct ISFPRebootCallback *v25; // [rsp+A0h] [rbp-70h]
  int *v26; // [rsp+A8h] [rbp-68h]
  struct ICSIStore2 *v27; // [rsp+B0h] [rbp-60h]
  CSFPIntegrityCheckAndRepair *v28; // [rsp+B8h] [rbp-58h]
  unsigned __int16 *v29; // [rsp+C0h] [rbp-50h]
  __int64 v30; // [rsp+C8h] [rbp-48h] BYREF
  struct ICSIRepairTransaction *v31; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-30h] BYREF
  GUID v34; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v35; // [rsp+100h] [rbp-10h] BYREF
  __int64 v36; // [rsp+108h] [rbp-8h] BYREF
  struct IDefinitionIdentity *v37[2]; // [rsp+110h] [rbp+0h]
  int v38; // [rsp+120h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+124h] [rbp+14h] BYREF
  int v40; // [rsp+128h] [rbp+18h] BYREF
  __int64 v41; // [rsp+130h] [rbp+20h] BYREF
  __int64 v42; // [rsp+138h] [rbp+28h] BYREF
  GUID v43; // [rsp+140h] [rbp+30h] BYREF

  v11 = 0;
  v28 = this;
  v24 = a7;
  v26 = a9;
  v25 = a4;
  v29 = a2;
  v27 = a6;
  v31 = 0;
  v35 = 0;
  v33 = 0;
  v32 = 0;
  v36 = 0;
  *(_OWORD *)v37 = 0;
  v42 = 0;
  v30 = 0;
  v34 = (GUID)0LL;
  v41 = 0;
  v39 = 0;
  v23 = 0;
  v38 = 0;
  v40 = 0;
  *a11 = 1;
  IsBootRecovery = BeginRepairTransaction(a6, 4, 1, &v31, &v39);
  if ( IsBootRecovery >= 0 )
  {
    IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIInventory *, __int64, __int64 *))(*(_QWORD *)a8 + 24LL))(
                       a8,
                       4,
                       &v30);
    if ( IsBootRecovery >= 0 )
    {
      if ( a5 )
      {
        v40 = 0;
        v38 = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL))(
                   v30,
                   1,
                   &v34,
                   &v41)
             && v41 )
        {
          if ( *(_QWORD *)v34.Data4 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34.Data4 + 16LL))(*(_QWORD *)v34.Data4);
            *(_QWORD *)v34.Data4 = 0;
          }
          ++v11;
        }
        if ( v30 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v30 = 0;
        }
        IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIInventory *, __int64, __int64 *))(*(_QWORD *)a8 + 24LL))(
                           a8,
                           4,
                           &v30);
        if ( IsBootRecovery >= 0 )
        {
          (*(void (__fastcall **)(struct ISFPProgressCallback *, _QWORD))(*(_QWORD *)a5 + 24LL))(a5, 0);
          v14 = v27;
          v15 = *(_QWORD *)v27;
          v43 = GUID_NULL;
          v16 = (*(__int64 (__fastcall **)(struct ICSIStore2 *, _QWORD, GUID *, _QWORD, GUID *, __int64 *, _QWORD))(v15 + 24))(
                  v27,
                  0,
                  &v43,
                  0,
                  &GUID_b891714f_67db_4eca_8881_e5932a0f0f94,
                  &v35,
                  0);
          IsBootRecovery = 0;
          if ( v16 < 0 )
            IsBootRecovery = v16;
          for ( i = IsBootRecovery < 0; !i; i = v19 < 0 )
          {
            if ( v38
              || (IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL))(
                                     v30,
                                     1,
                                     &v34,
                                     &v41),
                  IsBootRecovery < 0) )
            {
              v20 = v30;
              if ( v30 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                v20 = 0;
                v30 = 0;
              }
              if ( a3 )
              {
                IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v31 + 48LL))(
                                   v31,
                                   0,
                                   &v33,
                                   0);
                if ( IsBootRecovery >= 0 )
                {
                  IsBootRecovery = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 24LL))(
                                     v33,
                                     0,
                                     &v32);
                  if ( IsBootRecovery >= 0 )
                  {
                    v38 = 0;
                    while ( 1 )
                    {
                      IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v32 + 24LL))(
                                         v32,
                                         1,
                                         &v36,
                                         &v42);
                      if ( IsBootRecovery < 0 )
                        break;
                      if ( v42 )
                      {
                        IsBootRecovery = ComponentIsBootRecovery(v37[0], v24, &v23);
                        if ( IsBootRecovery < 0 )
                          goto LABEL_47;
                        if ( (_DWORD)v36 )
                        {
                          ++*((_DWORD *)a10 + 1);
                          if ( v23 )
                          {
                            ++*((_DWORD *)a10 + 3);
                            --*((_DWORD *)a10 + 2);
                          }
                        }
                        if ( v37[0] )
                        {
                          (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
                          v37[0] = 0;
                        }
                      }
                      else
                      {
                        v38 = 1;
                      }
                      if ( v38 )
                      {
                        if ( v33 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                          v33 = 0;
                        }
                        if ( v32 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                          v32 = 0;
                        }
                        if ( !*(_DWORD *)a10 || (IsBootRecovery = CommitWrapper(v31, v26, v25), IsBootRecovery >= 0) )
                        {
                          v20 = v30;
                          goto LABEL_45;
                        }
                        goto LABEL_47;
                      }
                    }
                  }
                }
                break;
              }
LABEL_45:
              if ( !v31 )
                goto LABEL_51;
              (*(void (__fastcall **)(struct ICSIRepairTransaction *))(*(_QWORD *)v31 + 16LL))(v31);
              v21 = 0;
              v31 = 0;
              goto LABEL_48;
            }
            v18 = *(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, unsigned __int16 *, _QWORD, struct ISFPRebootCallback *, struct ISFPProgressCallback *, struct ICSIStore2 *, struct IStore2 *, GUID *, __int64, struct ICSIRepairTransaction *, __int64 *, int, int *, int *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *))(*(_QWORD *)v28 + 128LL);
            v39 = 1;
            v43 = v34;
            v19 = v18(v28, v29, a3, v25, a5, v14, v24, &v43, v41, v31, &v35, v11, &v40, &v38, v26, a10, &v39);
            IsBootRecovery = v19;
            if ( v39 == 2 )
              *a11 = 2;
          }
        }
      }
    }
  }
LABEL_47:
  v21 = v31;
LABEL_48:
  if ( v21 )
    (*(void (__fastcall **)(struct ICSIRepairTransaction *))(*(_QWORD *)v21 + 16LL))(v21);
  v20 = v30;
LABEL_51:
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v20 = v30;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( *(_QWORD *)v34.Data4 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34.Data4 + 16LL))(*(_QWORD *)v34.Data4);
    *(_QWORD *)v34.Data4 = 0;
  }
  if ( v37[0] )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
  return (unsigned int)IsBootRecovery;
}

```

## disassembly

```asm
0x1800031c0  push    rbp
0x1800031c2  push    rbx
0x1800031c3  push    rsi
0x1800031c4  push    rdi
0x1800031c5  push    r12
0x1800031c7  push    r13
0x1800031c9  push    r14
0x1800031cb  push    r15
0x1800031cd  lea     rbp, [rsp-58h]
0x1800031d2  sub     rsp, 168h
0x1800031d9  mov     rax, cs:__security_cookie
0x1800031e0  xor     rax, rsp
0x1800031e3  mov     [rbp+90h+var_50], rax
0x1800031e7  mov     rax, [rbp+90h+arg_28]
0x1800031ee  xor     r14d, r14d
0x1800031f1  mov     r13, [rbp+90h+arg_50]
0x1800031f8  mov     r12d, r8d
0x1800031fb  mov     rdi, [rbp+90h+arg_48]
0x180003202  xorps   xmm0, xmm0
0x180003205  mov     r15, [rbp+90h+arg_20]
0x18000320c  mov     rsi, [rbp+90h+arg_38]
0x180003213  lea     r8d, [r14+1]; int
0x180003217  mov     [rbp+90h+var_E8], rcx
0x18000321b  mov     rcx, [rbp+90h+arg_30]
0x180003222  mov     [rbp+90h+var_108], rcx
0x180003226  mov     rcx, [rbp+90h+arg_40]
0x18000322d  mov     [rbp+90h+var_F8], rcx
0x180003231  lea     rcx, [rbp+90h+var_7C]
0x180003235  mov     [rsp+1A0h+var_180], rcx; unsigned int *
0x18000323a  mov     rcx, rax; struct ICSIStore2 *
0x18000323d  mov     [rbp+90h+var_100], r9
0x180003241  lea     r9, [rbp+90h+var_D0]; struct ICSIRepairTransaction **
0x180003245  mov     [rbp+90h+var_E0], rdx
0x180003249  lea     edx, [r14+4]; unsigned int
0x18000324d  mov     [rbp+90h+var_F0], rax
0x180003251  mov     [rbp+90h+var_D0], r14
0x180003255  mov     [rbp+90h+var_A0], r14
0x180003259  mov     [rbp+90h+var_C0], r14
0x18000325d  mov     [rbp+90h+var_C8], r14
0x180003261  mov     [rbp+90h+var_98], r14
0x180003265  movdqu  xmmword ptr [rbp+90h+var_90], xmm0
0x18000326a  mov     [rbp+90h+var_68], r14
0x18000326e  mov     [rbp+90h+var_D8], r14
0x180003272  mov     qword ptr [rbp+90h+var_B0], r14
0x180003276  mov     qword ptr [rbp+90h+var_B0+8], r14
0x18000327a  mov     [rbp+90h+var_70], r14
0x18000327e  mov     [rbp+90h+var_7C], r14d
0x180003282  mov     [rbp+90h+var_110], r14d
0x180003286  mov     [rbp+90h+var_80], r14d
0x18000328a  mov     [rbp+90h+var_78], r14d
0x18000328e  mov     dword ptr [r13+0], 1
0x180003296  call    ?BeginRepairTransaction@@YAJPEAUICSIStore2@@KHPEAPEAUICSIRepairTransaction@@PEAK@Z; BeginRepairTransaction(ICSIStore2 *,ulong,int,ICSIRepairTransaction * *,ulong *)
0x18000329b  mov     ebx, eax
0x18000329d  test    eax, eax
0x18000329f  js      loc_18000360B
0x1800032a5  mov     rax, [rsi]
0x1800032a8  lea     r8, [rbp+90h+var_D8]
0x1800032ac  lea     edx, [r14+4]
0x1800032b0  mov     rcx, rsi
0x1800032b3  mov     rax, [rax+18h]
0x1800032b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bc  mov     ebx, eax
0x1800032be  test    eax, eax
0x1800032c0  js      loc_18000360B
0x1800032c6  test    r15, r15
0x1800032c9  jz      loc_18000360B
0x1800032cf  xor     ebx, ebx
0x1800032d1  mov     [rbp+90h+var_78], r14d
0x1800032d5  mov     [rbp+90h+var_80], ebx
0x1800032d8  mov     rcx, [rbp+90h+var_D8]
0x1800032dc  lea     r9, [rbp+90h+var_70]
0x1800032e0  lea     r8, [rbp+90h+var_B0]
0x1800032e4  mov     edx, 1
0x1800032e9  mov     rax, [rcx]
0x1800032ec  mov     rax, [rax+18h]
0x1800032f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f5  test    eax, eax
0x1800032f7  jnz     short loc_18000331D
0x1800032f9  cmp     [rbp+90h+var_70], rbx
0x1800032fd  jbe     short loc_18000331D
0x1800032ff  mov     rcx, qword ptr [rbp+90h+var_B0+8]
0x180003303  test    rcx, rcx
0x180003306  jz      short loc_180003318
0x180003308  mov     rax, [rcx]
0x18000330b  mov     rax, [rax+10h]
0x18000330f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003314  mov     qword ptr [rbp+90h+var_B0+8], rbx
0x180003318  inc     r14d
0x18000331b  jmp     short loc_1800032D8
0x18000331d  mov     rcx, [rbp+90h+var_D8]
0x180003321  test    rcx, rcx
0x180003324  jz      short loc_180003336
0x180003326  mov     rax, [rcx]
0x180003329  mov     rax, [rax+10h]
0x18000332d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003332  mov     [rbp+90h+var_D8], rbx
0x180003336  mov     rax, [rsi]
0x180003339  lea     r8, [rbp+90h+var_D8]
0x18000333d  mov     edx, 4
0x180003342  mov     rcx, rsi
0x180003345  mov     rax, [rax+18h]
0x180003349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334e  mov     ebx, eax
0x180003350  test    eax, eax
0x180003352  js      loc_180003608
0x180003358  mov     rax, [r15]
0x18000335b  xorps   xmm2, xmm2
0x18000335e  xor     edx, edx
0x180003360  mov     rcx, r15
0x180003363  mov     rax, [rax+18h]
0x180003367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000336c  mov     rsi, [rbp+90h+var_F0]
0x180003370  lea     rcx, [rbp+90h+var_A0]
0x180003374  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000337b  mov     [rsp+1A0h+var_170], 0
0x180003384  lea     r8, [rbp+90h+var_60]
0x180003388  mov     [rsp+1A0h+var_178], rcx
0x18000338d  xor     r9d, r9d
0x180003390  mov     rax, [rsi]
0x180003393  lea     rcx, _GUID_b891714f_67db_4eca_8881_e5932a0f0f94
0x18000339a  mov     [rsp+1A0h+var_180], rcx
0x18000339f  xor     edx, edx
0x1800033a1  mov     rcx, rsi
0x1800033a4  movdqu  [rbp+90h+var_60], xmm0
0x1800033a9  mov     rax, [rax+18h]
0x1800033ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b2  xor     ebx, ebx
0x1800033b4  test    eax, eax
0x1800033b6  cmovs   ebx, eax
0x1800033b9  test    ebx, ebx
0x1800033bb  jmp     loc_180003492
0x1800033c0  mov     rcx, [rbp+90h+var_D8]
0x1800033c4  lea     r9, [rbp+90h+var_70]
0x1800033c8  lea     r8, [rbp+90h+var_B0]
0x1800033cc  mov     edx, 1
0x1800033d1  mov     rax, [rcx]
0x1800033d4  mov     rax, [rax+18h]
0x1800033d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033dd  mov     ebx, eax
0x1800033df  test    eax, eax
0x1800033e1  js      loc_1800034A2
0x1800033e7  mov     r10, [rbp+90h+var_E8]
0x1800033eb  lea     rcx, [rbp+90h+var_7C]
0x1800033ef  movaps  xmm0, [rbp+90h+var_B0]
0x1800033f3  mov     r8d, r12d
0x1800033f6  mov     r9, [rbp+90h+var_100]
0x1800033fa  mov     rdx, [rbp+90h+var_E0]
0x1800033fe  mov     rax, [r10]
0x180003401  mov     [rsp+1A0h+var_120], rcx
0x180003409  mov     rcx, [rbp+90h+var_F8]
0x18000340d  mov     [rsp+1A0h+var_128], rdi
0x180003412  mov     rax, [rax+80h]
0x180003419  mov     [rsp+1A0h+var_130], rcx
0x18000341e  lea     rcx, [rbp+90h+var_80]
0x180003422  mov     [rsp+1A0h+var_138], rcx
0x180003427  lea     rcx, [rbp+90h+var_78]
0x18000342b  mov     [rsp+1A0h+var_140], rcx
0x180003430  lea     rcx, [rbp+90h+var_A0]
0x180003434  mov     [rsp+1A0h+var_148], r14d
0x180003439  mov     [rsp+1A0h+var_150], rcx
0x18000343e  mov     rcx, [rbp+90h+var_D0]
0x180003442  mov     [rsp+1A0h+var_158], rcx
0x180003447  mov     rcx, [rbp+90h+var_70]
0x18000344b  mov     [rsp+1A0h+var_160], rcx
0x180003450  lea     rcx, [rbp+90h+var_60]
0x180003454  mov     [rsp+1A0h+var_168], rcx
0x180003459  mov     rcx, [rbp+90h+var_108]
0x18000345d  mov     [rsp+1A0h+var_170], rcx
0x180003462  mov     rcx, r10
0x180003465  mov     [rsp+1A0h+var_178], rsi
0x18000346a  mov     [rsp+1A0h+var_180], r15
0x18000346f  mov     [rbp+90h+var_7C], 1
0x180003476  movdqa  [rbp+90h+var_60], xmm0
0x18000347b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003480  cmp     [rbp+90h+var_7C], 2
0x180003484  mov     ebx, eax
0x180003486  jnz     short loc_180003490
0x180003488  mov     dword ptr [r13+0], 2
0x180003490  test    eax, eax
0x180003492  js      loc_180003608
0x180003498  cmp     [rbp+90h+var_80], 0
0x18000349c  jz      loc_1800033C0
0x1800034a2  mov     rcx, [rbp+90h+var_D8]
0x1800034a6  xor     r14d, r14d
0x1800034a9  test    rcx, rcx
0x1800034ac  jz      short loc_1800034C1
0x1800034ae  mov     rax, [rcx]
0x1800034b1  mov     rax, [rax+10h]
0x1800034b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ba  mov     ecx, r14d
0x1800034bd  mov     [rbp+90h+var_D8], rcx
0x1800034c1  test    r12d, r12d
0x1800034c4  jz      loc_1800035E7
0x1800034ca  mov     rcx, [rbp+90h+var_D0]
0x1800034ce  lea     r8, [rbp+90h+var_C0]
0x1800034d2  xor     r9d, r9d
0x1800034d5  xor     edx, edx
0x1800034d7  mov     rax, [rcx]
0x1800034da  mov     rax, [rax+30h]
0x1800034de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e3  mov     ebx, eax
0x1800034e5  test    eax, eax
0x1800034e7  js      loc_18000360B
0x1800034ed  mov     rcx, [rbp+90h+var_C0]
0x1800034f1  lea     r8, [rbp+90h+var_C8]
0x1800034f5  xor     edx, edx
0x1800034f7  mov     rax, [rcx]
0x1800034fa  mov     rax, [rax+18h]
0x1800034fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003503  mov     ebx, eax
0x180003505  test    eax, eax
0x180003507  js      loc_18000360B
0x18000350d  mov     [rbp+90h+var_80], r14d
0x180003511  mov     esi, 1
0x180003516  mov     rcx, [rbp+90h+var_C8]
0x18000351a  lea     r9, [rbp+90h+var_68]
0x18000351e  lea     r8, [rbp+90h+var_98]
0x180003522  mov     rdx, rsi
0x180003525  mov     rax, [rcx]
0x180003528  mov     rax, [rax+18h]
0x18000352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003531  mov     ebx, eax
0x180003533  test    eax, eax
0x180003535  js      loc_18000360B
0x18000353b  cmp     [rbp+90h+var_68], r14
0x18000353f  jz      short loc_18000358C
0x180003541  mov     rdx, [rbp+90h+var_108]; struct IStore2 *
0x180003545  lea     r8, [rbp+90h+var_110]; int *
0x180003549  mov     rcx, [rbp+90h+var_90]; struct IDefinitionIdentity *
0x18000354d  call    ?ComponentIsBootRecovery@@YAJPEAUIDefinitionIdentity@@PEAUIStore2@@PEAH@Z; ComponentIsBootRecovery(IDefinitionIdentity *,IStore2 *,int *)
0x180003552  mov     ebx, eax
0x180003554  test    eax, eax
0x180003556  js      loc_18000360B
0x18000355c  cmp     dword ptr [rbp+90h+var_98], r14d
0x180003560  jz      short loc_180003571
0x180003562  add     [rdi+4], esi
0x180003565  cmp     [rbp+90h+var_110], r14d
0x180003569  jz      short loc_180003571
0x18000356b  add     [rdi+0Ch], esi
0x18000356e  dec     dword ptr [rdi+8]
0x180003571  mov     rcx, [rbp+90h+var_90]
0x180003575  test    rcx, rcx
0x180003578  jz      short loc_18000358F
0x18000357a  mov     rax, [rcx]
0x18000357d  mov     rax, [rax+10h]
0x180003581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003586  mov     [rbp+90h+var_90], r14
0x18000358a  jmp     short loc_18000358F
0x18000358c  mov     [rbp+90h+var_80], esi
0x18000358f  cmp     [rbp+90h+var_80], r14d
0x180003593  jz      short loc_180003516
0x180003595  mov     rcx, [rbp+90h+var_C0]
0x180003599  test    rcx, rcx
0x18000359c  jz      short loc_1800035AE
0x18000359e  mov     rax, [rcx]
0x1800035a1  mov     rax, [rax+10h]
0x1800035a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035aa  mov     [rbp+90h+var_C0], r14
0x1800035ae  mov     rcx, [rbp+90h+var_C8]
0x1800035b2  test    rcx, rcx
0x1800035b5  jz      short loc_1800035C7
0x1800035b7  mov     rax, [rcx]
0x1800035ba  mov     rax, [rax+10h]
0x1800035be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c3  mov     [rbp+90h+var_C8], r14
0x1800035c7  cmp     [rdi], r14d
0x1800035ca  jbe     short loc_1800035E3
0x1800035cc  mov     r8, [rbp+90h+var_100]; struct ISFPRebootCallback *
0x1800035d0  mov     rdx, [rbp+90h+var_F8]; int *
0x1800035d4  mov     rcx, [rbp+90h+var_D0]; struct ICSIRepairTransaction *
0x1800035d8  call    ?CommitWrapper@@YAJPEAUICSIRepairTransaction@@PEAHPEAUISFPRebootCallback@@@Z; CommitWrapper(ICSIRepairTransaction *,int *,ISFPRebootCallback *)
0x1800035dd  mov     ebx, eax
0x1800035df  test    eax, eax
0x1800035e1  js      short loc_18000360B
0x1800035e3  mov     rcx, [rbp+90h+var_D8]
0x1800035e7  mov     rdx, [rbp+90h+var_D0]
0x1800035eb  test    rdx, rdx
0x1800035ee  jz      short loc_180003624
0x1800035f0  mov     rax, [rdx]
0x1800035f3  mov     rcx, rdx
0x1800035f6  mov     rax, [rax+10h]
0x1800035fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ff  mov     rcx, r14
0x180003602  mov     [rbp+90h+var_D0], rcx
0x180003606  jmp     short loc_18000360F
0x180003608  xor     r14d, r14d
0x18000360b  mov     rcx, [rbp+90h+var_D0]
0x18000360f  test    rcx, rcx
0x180003612  jz      short loc_180003620
0x180003614  mov     rax, [rcx]
0x180003617  mov     rax, [rax+10h]
0x18000361b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003620  mov     rcx, [rbp+90h+var_D8]
0x180003624  mov     rdx, [rbp+90h+var_A0]
0x180003628  test    rdx, rdx
0x18000362b  jz      short loc_180003640
0x18000362d  mov     rax, [rdx]
0x180003630  mov     rcx, rdx
0x180003633  mov     rax, [rax+10h]
0x180003637  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
