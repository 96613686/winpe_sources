# ?ContentChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x180010750`
- end: `0x180010b8b`
- name: `?ContentChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `1083`
- prototype: `void __fastcall(__int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004da4`
- `0x1800053b8`
- `0x1800054ec`
- `0x1800058f0`
- `0x18000635c`
- `0x1800064bc`
- `0x18000bccc`
- `0x18000c760`
- `0x18000c8f4`
- `0x180010678`
- `0x180010750`
- `0x180012214`
- `0x180012408`
- `0x180012d74`
- `0x180015164`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!rand` at `0x180010847`
- `msvcrt!rand` at `0x180010847`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800107f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800107f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800108c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800108f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010b52`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800108c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800108f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010b52`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001086b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001086b`

## pseudocode

```c
void __fastcall _ContentChange__QIFileChangeNotification__CompatibilityAdapter__UEAAXPEBG_Z(
        __int64 a1,
        unsigned __int16 *a2)
{
  HANDLE *v4; // rdi
  CompatibilityAdapter *v5; // rcx
  CJob *v6; // rbx
  int v7; // esi
  int v8; // eax
  int v9; // r13d
  int v10; // eax
  struct CJob *v11; // r8
  _QWORD *v12; // rcx
  int v13; // eax
  int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  EventManager *v16; // rcx
  unsigned int v17; // r9d
  int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  EventManager *v20; // rcx
  void *v21; // [rsp+20h] [rbp-298h]
  struct _GUID *v22; // [rsp+28h] [rbp-290h]
  const struct _GUID *v23; // [rsp+30h] [rbp-288h]
  CJob *v24; // [rsp+48h] [rbp-270h] BYREF
  int v25; // [rsp+50h] [rbp-268h]
  __int64 v26; // [rsp+58h] [rbp-260h]
  __int64 v27; // [rsp+60h] [rbp-258h]
  unsigned __int16 *v28; // [rsp+68h] [rbp-250h]
  _BYTE v29[528]; // [rsp+70h] [rbp-248h] BYREF

  v26 = a1;
  v28 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
  }
  if ( CompatibilityAdapter::GetAdapter() )
  {
    TaskLock::TaskLock((TaskLock *)v29, a2);
    v4 = (HANDLE *)(a1 + 16);
    v27 = a1 + 16;
    WaitForSingleObject(*(HANDLE *)(a1 + 16), 0xFFFFFFFF);
    v6 = 0;
    v24 = 0;
    v7 = 0;
    v8 = 0;
    v9 = 3;
    while ( 1 )
    {
      v25 = v8;
      if ( v8 >= v9 )
        break;
      v7 = CompatibilityAdapter::ActivateJob(v5, a2, &v24, 1);
      if ( v7 >= 0 )
      {
        v7 = 0;
        v6 = v24;
        goto LABEL_19;
      }
      if ( v7 == -2147024894 )
        v9 = 10;
      v10 = rand();
      Sleep(v10 % 125 + 250);
      v8 = v25 + 1;
      v6 = v24;
    }
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v7);
      }
      goto LABEL_20;
    }
LABEL_19:
    if ( !v6 )
    {
LABEL_20:
      wmi::AutoRef<CJob>::Release(&v24);
      ReleaseMutex(*v4);
      TaskLock::~TaskLock((TaskLock *)v29);
      return;
    }
    if ( (unsigned int)CJob::MatchFingerprint(v6) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
        v12 = WPP_GLOBAL_Control;
      }
      if ( (*((_DWORD *)v6 + 22) & 0x200000) == 0 )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 5u )
          WPP_SF_S(v12[2], 30, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
        v13 = CompatibilityAdapter::RegisterWithRetry(v26, 0, (__int64)v6, a2, 0, 0);
        v7 = v13;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
            (_DWORD)a2,
            v13);
        }
        if ( v7 < 0 )
          EventManager::EvtReport((EventManager *)v12, &COMPAT_TASK_UPDATE_FAILED, a2, v7, v21, v22);
      }
    }
    if ( (*((_DWORD *)v6 + 22) & 0x8000000) != 0 )
    {
      v14 = CompatibilityAdapter::StopJob((CompatibilityAdapter *)v12, a2, v11);
      v7 = v14;
      if ( v14 >= 0 )
        goto LABEL_56;
      v16 = (EventManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v14);
      }
      v17 = 3;
    }
    else
    {
      if ( (*((_DWORD *)v6 + 22) & 0x4000000) == 0 )
        goto LABEL_56;
      v18 = CompatibilityAdapter::RunJob((CompatibilityAdapter *)v12, a2, v6);
      v7 = v18;
      if ( v18 >= 0 )
        goto LABEL_56;
      v16 = (EventManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v18);
      }
      v17 = 4;
    }
    EventManager::EvtReport(v16, v15, a2, v17, v7, v22, v23);
LABEL_56:
    wmi::AutoRef<CJob>::Release(&v24);
    if ( v7 < 0 )
    {
      EventManager::EvtReport(v20, v19, a2, 0, v7, v22, v23);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (unsigned int)v7);
      }
    }
    ReleaseMutex(*v4);
    TaskLock::~TaskLock((TaskLock *)v29);
  }
}

```

## disassembly

```asm
0x180010750  mov     [rsp+arg_10], rbx
0x180010755  push    rsi
0x180010756  push    rdi
0x180010757  push    r12
0x180010759  push    r13
0x18001075b  push    r14
0x18001075d  sub     rsp, 290h
0x180010764  mov     rax, cs:__security_cookie
0x18001076b  xor     rax, rsp
0x18001076e  mov     [rsp+2B8h+var_38], rax
0x180010776  mov     r14, rdx
0x180010779  mov     rbx, rcx
0x18001077c  mov     [rsp+2B8h+var_260], rcx
0x180010781  mov     [rsp+2B8h+var_250], rdx
0x180010786  mov     [rsp+2B8h+var_278], 0
0x18001078e  lea     r12, WPP_GLOBAL_Control
0x180010795  mov     rcx, cs:WPP_GLOBAL_Control
0x18001079c  cmp     rcx, r12
0x18001079f  jz      short loc_1800107C5
0x1800107a1  test    byte ptr [rcx+1Ch], 2
0x1800107a5  jz      short loc_1800107C5
0x1800107a7  cmp     byte ptr [rcx+19h], 4
0x1800107ab  jb      short loc_1800107C5
0x1800107ad  mov     edx, 1Bh
0x1800107b2  mov     r9, r14
0x1800107b5  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800107bc  mov     rcx, [rcx+10h]
0x1800107c0  call    WPP_SF_S
0x1800107c5  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800107ca  test    rax, rax
0x1800107cd  jz      loc_180010B63
0x1800107d3  mov     rdx, r14; unsigned __int16 *
0x1800107d6  lea     rcx, [rsp+2B8h+var_248]; this
0x1800107db  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x1800107e0  nop
0x1800107e1  lea     rdi, [rbx+10h]
0x1800107e5  mov     [rsp+2B8h+var_258], rdi
0x1800107ea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800107ed  mov     rcx, [rdi]; hHandle
0x1800107f0  call    cs:__imp_WaitForSingleObject
0x1800107f6  nop
0x1800107f7  xor     ebx, ebx
0x1800107f9  mov     [rsp+2B8h+var_270], rbx
0x1800107fe  xor     esi, esi
0x180010800  xor     eax, eax
0x180010802  lea     r13d, [rbx+3]
0x180010806  mov     [rsp+2B8h+var_268], eax
0x18001080a  cmp     eax, r13d
0x18001080d  jge     short loc_18001087E
0x18001080f  mov     r9d, 1; int
0x180010815  lea     r8, [rsp+2B8h+var_270]; struct CJob **
0x18001081a  mov     rdx, r14; unsigned __int16 *
0x18001081d  call    ?ActivateJob@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateJob(ushort const *,CJob * *,int)
0x180010822  mov     esi, eax
0x180010824  test    eax, eax
0x180010826  js      short loc_180010838
0x180010828  xor     esi, esi
0x18001082a  mov     [rsp+2B8h+var_278], esi
0x18001082e  mov     rbx, [rsp+2B8h+var_270]
0x180010833  jmp     loc_1800108DF
0x180010838  mov     eax, 0Ah
0x18001083d  cmp     esi, 80070002h
0x180010843  cmovz   r13d, eax
0x180010847  call    cs:__imp_rand
0x18001084d  mov     ecx, eax
0x18001084f  mov     eax, 10624DD3h
0x180010854  imul    ecx
0x180010856  sar     edx, 3
0x180010859  mov     eax, edx
0x18001085b  shr     eax, 1Fh
0x18001085e  add     edx, eax
0x180010860  imul    eax, edx, 7Dh ; '}'
0x180010863  sub     ecx, eax
0x180010865  add     ecx, 0FAh; dwMilliseconds
0x18001086b  call    cs:__imp_Sleep
0x180010871  mov     eax, [rsp+2B8h+var_268]
0x180010875  inc     eax
0x180010877  mov     rbx, [rsp+2B8h+var_270]
0x18001087c  jmp     short loc_180010806
0x18001087e  mov     [rsp+2B8h+var_278], esi
0x180010882  test    esi, esi
0x180010884  jns     short loc_1800108DF
0x180010886  mov     rcx, cs:WPP_GLOBAL_Control
0x18001088d  cmp     rcx, r12
0x180010890  jz      short loc_1800108BB
0x180010892  test    byte ptr [rcx+1Ch], 2
0x180010896  jz      short loc_1800108BB
0x180010898  cmp     byte ptr [rcx+19h], 2
0x18001089c  jb      short loc_1800108BB
0x18001089e  mov     edx, 1Ch
0x1800108a3  mov     dword ptr [rsp+2B8h+var_298], esi
0x1800108a7  mov     r9, r14
0x1800108aa  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800108b1  mov     rcx, [rcx+10h]
0x1800108b5  call    WPP_SF_SD
0x1800108ba  nop
0x1800108bb  lea     rcx, [rsp+2B8h+var_270]
0x1800108c0  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x1800108c5  nop
0x1800108c6  mov     rcx, [rdi]; hMutex
0x1800108c9  call    cs:__imp_ReleaseMutex
0x1800108cf  nop
0x1800108d0  lea     rcx, [rsp+2B8h+var_248]; this
0x1800108d5  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800108da  jmp     loc_180010B63
0x1800108df  test    rbx, rbx
0x1800108e2  jnz     short loc_180010908
0x1800108e4  lea     rcx, [rsp+2B8h+var_270]
0x1800108e9  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x1800108ee  nop
0x1800108ef  mov     rcx, [rdi]; hMutex
0x1800108f2  call    cs:__imp_ReleaseMutex
0x1800108f8  nop
0x1800108f9  lea     rcx, [rsp+2B8h+var_248]; this
0x1800108fe  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180010903  jmp     loc_180010B63
0x180010908  mov     rcx, rbx; this
0x18001090b  call    ?MatchFingerprint@CJob@@QEAAHXZ; CJob::MatchFingerprint(void)
0x180010910  test    eax, eax
0x180010912  jnz     loc_1800109F9
0x180010918  mov     rcx, cs:WPP_GLOBAL_Control
0x18001091f  cmp     rcx, r12
0x180010922  jz      short loc_18001094D
0x180010924  test    byte ptr [rcx+1Ch], 2
0x180010928  jz      short loc_18001094D
0x18001092a  cmp     byte ptr [rcx+19h], 3
0x18001092e  jb      short loc_18001094D
0x180010930  lea     edx, [rax+1Dh]
0x180010933  mov     r9, r14
0x180010936  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001093d  mov     rcx, [rcx+10h]
0x180010941  call    WPP_SF_S
0x180010946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001094d  test    dword ptr [rbx+58h], 200000h
0x180010954  jnz     loc_180010A29
0x18001095a  cmp     rcx, r12
0x18001095d  jz      short loc_180010983
0x18001095f  test    byte ptr [rcx+1Ch], 2
0x180010963  jz      short loc_180010983
0x180010965  cmp     byte ptr [rcx+19h], 5
0x180010969  jb      short loc_180010983
0x18001096b  mov     edx, 1Eh
0x180010970  mov     r9, r14
0x180010973  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001097a  mov     rcx, [rcx+10h]
0x18001097e  call    WPP_SF_S
0x180010983  mov     [rsp+2B8h+var_290], 0; struct _GUID *
0x18001098c  mov     [rsp+2B8h+var_298], 0
0x180010995  mov     r9, r14
0x180010998  mov     r8, rbx
0x18001099b  xor     edx, edx
0x18001099d  mov     rcx, [rsp+2B8h+var_260]
0x1800109a2  call    ?RegisterWithRetry@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z; CompatibilityAdapter::RegisterWithRetry(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)
0x1800109a7  mov     esi, eax
0x1800109a9  mov     [rsp+2B8h+var_278], eax
0x1800109ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109b4  cmp     rcx, r12
0x1800109b7  jz      short loc_1800109E1
0x1800109b9  test    byte ptr [rcx+1Ch], 2
0x1800109bd  jz      short loc_1800109E1
0x1800109bf  cmp     byte ptr [rcx+19h], 4
0x1800109c3  jb      short loc_1800109E1
0x1800109c5  mov     edx, 1Fh
0x1800109ca  mov     dword ptr [rsp+2B8h+var_298], eax; void *
0x1800109ce  mov     r9, r14
0x1800109d1  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800109d8  mov     rcx, [rcx+10h]
0x1800109dc  call    WPP_SF_SD
0x1800109e1  test    esi, esi
0x1800109e3  jns     short loc_180010A29
0x1800109e5  mov     r9d, esi; unsigned int
0x1800109e8  mov     r8, r14; unsigned __int16 *
0x1800109eb  lea     rdx, COMPAT_TASK_UPDATE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800109f2  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x1800109f7  jmp     short loc_180010A29
0x1800109f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a00  cmp     rcx, r12
0x180010a03  jz      short loc_180010A29
0x180010a05  test    byte ptr [rcx+1Ch], 2
0x180010a09  jz      short loc_180010A29
0x180010a0b  cmp     byte ptr [rcx+19h], 4
0x180010a0f  jb      short loc_180010A29
0x180010a11  mov     edx, 20h ; ' '
0x180010a16  mov     r9, r14
0x180010a19  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010a20  mov     rcx, [rcx+10h]
0x180010a24  call    WPP_SF_S
0x180010a29  test    dword ptr [rbx+58h], 8000000h
0x180010a30  jz      short loc_180010A84
0x180010a32  mov     rdx, r14; unsigned __int16 *
0x180010a35  call    ?StopJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z; CompatibilityAdapter::StopJob(ushort const *,CJob *)
0x180010a3a  mov     esi, eax
0x180010a3c  mov     [rsp+2B8h+var_278], eax
0x180010a40  test    eax, eax
0x180010a42  jns     loc_180010AE9
0x180010a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a4f  cmp     rcx, r12
0x180010a52  jz      short loc_180010A7C
0x180010a54  test    byte ptr [rcx+1Ch], 2
0x180010a58  jz      short loc_180010A7C
0x180010a5a  cmp     byte ptr [rcx+19h], 2
0x180010a5e  jb      short loc_180010A7C
0x180010a60  mov     edx, 21h ; '!'
0x180010a65  mov     dword ptr [rsp+2B8h+var_298], eax
0x180010a69  mov     r9, r14
0x180010a6c  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010a73  mov     rcx, [rcx+10h]
0x180010a77  call    WPP_SF_SD
0x180010a7c  mov     r9d, 3
0x180010a82  jmp     short loc_180010ADC
0x180010a84  test    dword ptr [rbx+58h], 4000000h
0x180010a8b  jz      short loc_180010AE9
0x180010a8d  mov     r8, rbx; struct CJob *
0x180010a90  mov     rdx, r14; unsigned __int16 *
0x180010a93  call    ?RunJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z; CompatibilityAdapter::RunJob(ushort const *,CJob *)
0x180010a98  mov     esi, eax
0x180010a9a  mov     [rsp+2B8h+var_278], eax
0x180010a9e  test    eax, eax
0x180010aa0  jns     short loc_180010AE9
0x180010aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180010aa9  cmp     rcx, r12
0x180010aac  jz      short loc_180010AD6
0x180010aae  test    byte ptr [rcx+1Ch], 2
0x180010ab2  jz      short loc_180010AD6
0x180010ab4  cmp     byte ptr [rcx+19h], 2
0x180010ab8  jb      short loc_180010AD6
0x180010aba  mov     edx, 22h ; '"'
0x180010abf  mov     dword ptr [rsp+2B8h+var_298], eax
0x180010ac3  mov     r9, r14
0x180010ac6  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010acd  mov     rcx, [rcx+10h]
0x180010ad1  call    WPP_SF_SD
0x180010ad6  mov     r9d, 4; unsigned int
0x180010adc  mov     dword ptr [rsp+2B8h+var_298], esi; unsigned int
0x180010ae0  mov     r8, r14; unsigned __int16 *
0x180010ae3  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x180010ae8  nop
0x180010ae9  lea     rcx, [rsp+2B8h+var_270]
0x180010aee  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180010af3  nop
0x180010af4  jmp     short loc_180010B0B
0x180010af6  lea     r12, WPP_GLOBAL_Control
0x180010afd  mov     esi, [rsp+2B8h+var_278]
0x180010b01  mov     rdi, [rsp+2B8h+var_258]
0x180010b06  mov     r14, [rsp+2B8h+var_250]
0x180010b0b  test    esi, esi
0x180010b0d  jns     short loc_180010B4F
0x180010b0f  mov     dword ptr [rsp+2B8h+var_298], esi; unsigned int
0x180010b13  xor     r9d, r9d; unsigned int
0x180010b16  mov     r8, r14; unsigned __int16 *
0x180010b19  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x180010b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b25  cmp     rcx, r12
0x180010b28  jz      short loc_180010B4F
0x180010b2a  test    byte ptr [rcx+1Ch], 2
0x180010b2e  jz      short loc_180010B4F
0x180010b30  cmp     byte ptr [rcx+19h], 2
0x180010b34  jb      short loc_180010B4F
0x180010b36  mov     edx, 23h ; '#'
0x180010b3b  mov     r9d, esi
0x180010b3e  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180010b45  mov     rcx, [rcx+10h]
0x180010b49  call    WPP_SF_d
0x180010b4e  nop
0x180010b4f  mov     rcx, [rdi]; hMutex
0x180010b52  call    cs:__imp_ReleaseMutex
0x180010b58  nop
0x180010b59  lea     rcx, [rsp+2B8h+var_248]; this
0x180010b5e  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180010b63  mov     rcx, [rsp+2B8h+var_38]
0x180010b6b  xor     rcx, rsp; StackCookie
0x180010b6e  call    __security_check_cookie
0x180010b73  mov     rbx, [rsp+2B8h+arg_10]
0x180010b7b  add     rsp, 290h
0x180010b82  pop     r14
0x180010b84  pop     r13
0x180010b86  pop     r12
0x180010b88  pop     rdi
0x180010b89  pop     rsi
0x180010b8a  retn
```
