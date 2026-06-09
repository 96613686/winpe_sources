# ?ContentChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x1800111e0`
- end: `0x1800115c8`
- name: `?ContentChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `1000`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180005010`
- `0x180005650`
- `0x1800057a0`
- `0x180005c10`
- `0x180006764`
- `0x1800068e4`
- `0x18000c4c8`
- `0x18000cf80`
- `0x18000d128`
- `0x18001114c`
- `0x1800111e0`
- `0x180012d48`
- `0x180012f5c`
- `0x18001394c`
- `0x180015f30`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011280`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011280`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800112f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011324`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011588`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800112f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011324`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011588`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall _ContentChange__QIFileChangeNotification__CompatibilityAdapter__UEAAXPEBG_Z(__int64 a1, CJob *a2)
{
  HANDLE *v4; // rbx
  CompatibilityAdapter *v5; // rcx
  int v6; // r9d
  int v7; // eax
  int v8; // esi
  CJob *v9; // rdi
  struct CJob *v10; // r8
  _QWORD *v11; // rcx
  int v12; // eax
  int v13; // eax
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  EventManager *v15; // rcx
  int v16; // r9d
  int v17; // eax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  EventManager *v19; // rcx
  CJob *v20[5]; // [rsp+48h] [rbp-270h] BYREF
  _BYTE v21[528]; // [rsp+70h] [rbp-248h] BYREF

  v20[1] = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
  }
  if ( CompatibilityAdapter::GetAdapter() )
  {
    TaskLock::TaskLock((TaskLock *)v21, (const unsigned __int16 *)a2);
    v4 = (HANDLE *)(a1 + 16);
    v20[2] = (CJob *)(a1 + 16);
    v20[3] = (CJob *)(a1 + 16);
    WaitForSingleObject(*(HANDLE *)(a1 + 16), 0xFFFFFFFF);
    v20[0] = 0;
    v7 = CompatibilityAdapter::ActivateWithRetry(v5, (const unsigned __int16 *)a2, v20, v6);
    v8 = v7;
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
      goto LABEL_13;
    }
    v9 = v20[0];
    if ( !v20[0] )
    {
LABEL_13:
      wmi::AutoRef<CJob>::Release(v20);
      ReleaseMutex(*v4);
      TaskLock::~TaskLock((TaskLock *)v21);
      return;
    }
    if ( (unsigned int)CJob::MatchFingerprint(v20[0]) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (*((_DWORD *)v9 + 22) & 0x200000) == 0 )
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 && *((_BYTE *)v11 + 25) >= 5u )
          WPP_SF_S(v11[2], 30, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a2);
        v12 = CompatibilityAdapter::RegisterWithRetry(a1, 0, v9, a2, 0, 0);
        v8 = v12;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
            (_DWORD)a2,
            v12);
        }
        if ( v8 < 0 )
          EventManager::EvtReport((EventManager *)v11, &COMPAT_TASK_UPDATE_FAILED, (const unsigned __int16 *)a2, v8);
      }
    }
    if ( (*((_DWORD *)v9 + 22) & 0x8000000) != 0 )
    {
      v13 = CompatibilityAdapter::StopJob((CompatibilityAdapter *)v11, (const unsigned __int16 *)a2, v10);
      v8 = v13;
      if ( v13 >= 0 )
        goto LABEL_49;
      v15 = (EventManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v13);
      }
      v16 = 3;
    }
    else
    {
      if ( (*((_DWORD *)v9 + 22) & 0x4000000) == 0 )
        goto LABEL_49;
      v17 = CompatibilityAdapter::RunJob((CompatibilityAdapter *)v11, (const unsigned __int16 *)a2, v9);
      v8 = v17;
      if ( v17 >= 0 )
        goto LABEL_49;
      v15 = (EventManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (_DWORD)a2,
          v17);
      }
      v16 = 4;
    }
    EventManager::EvtReport(v15, v14, (const unsigned __int16 *)a2, v16, v8);
LABEL_49:
    wmi::AutoRef<CJob>::Release(v20);
    if ( v8 < 0 )
    {
      EventManager::EvtReport(v19, v18, (const unsigned __int16 *)a2, 0, v8);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
          (unsigned int)v8);
      }
    }
    ReleaseMutex(*v4);
    TaskLock::~TaskLock((TaskLock *)v21);
  }
}

```

## disassembly

```asm
0x1800111e0  mov     [rsp+arg_10], rbx
0x1800111e5  push    rsi
0x1800111e6  push    rdi
0x1800111e7  push    r12
0x1800111e9  push    r13
0x1800111eb  push    r15
0x1800111ed  sub     rsp, 290h
0x1800111f4  mov     rax, cs:__security_cookie
0x1800111fb  xor     rax, rsp
0x1800111fe  mov     [rsp+2B8h+var_38], rax
0x180011206  mov     r15, rdx
0x180011209  mov     r13, rcx
0x18001120c  mov     [rsp+2B8h+var_268], rdx
0x180011211  mov     [rsp+2B8h+var_278], 0
0x180011219  lea     r12, WPP_GLOBAL_Control
0x180011220  mov     rcx, cs:WPP_GLOBAL_Control
0x180011227  cmp     rcx, r12
0x18001122a  jz      short loc_180011250
0x18001122c  test    byte ptr [rcx+1Ch], 2
0x180011230  jz      short loc_180011250
0x180011232  cmp     byte ptr [rcx+19h], 4
0x180011236  jb      short loc_180011250
0x180011238  mov     edx, 1Bh
0x18001123d  mov     r9, r15
0x180011240  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011247  mov     rcx, [rcx+10h]
0x18001124b  call    WPP_SF_S
0x180011250  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180011255  test    rax, rax
0x180011258  jz      loc_18001159F
0x18001125e  mov     rdx, r15; unsigned __int16 *
0x180011261  lea     rcx, [rsp+2B8h+var_248]; this
0x180011266  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x18001126b  nop
0x18001126c  lea     rbx, [r13+10h]
0x180011270  mov     [rsp+2B8h+var_260], rbx
0x180011275  mov     [rsp+2B8h+var_258], rbx
0x18001127a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001127d  mov     rcx, [rbx]; hHandle
0x180011280  call    cs:__imp_WaitForSingleObject
0x180011287  nop     dword ptr [rax+rax+00h]
0x18001128c  nop
0x18001128d  mov     [rsp+2B8h+var_270], 0
0x180011296  lea     r8, [rsp+2B8h+var_270]; struct CJob **
0x18001129b  mov     rdx, r15; unsigned __int16 *
0x18001129e  call    ?ActivateWithRetry@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateWithRetry(ushort const *,CJob * *,int)
0x1800112a3  mov     esi, eax
0x1800112a5  mov     [rsp+2B8h+var_278], eax
0x1800112a9  test    eax, eax
0x1800112ab  jns     short loc_18001130C
0x1800112ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112b4  cmp     rcx, r12
0x1800112b7  jz      short loc_1800112E2
0x1800112b9  test    byte ptr [rcx+1Ch], 2
0x1800112bd  jz      short loc_1800112E2
0x1800112bf  cmp     byte ptr [rcx+19h], 2
0x1800112c3  jb      short loc_1800112E2
0x1800112c5  mov     edx, 1Ch
0x1800112ca  mov     dword ptr [rsp+2B8h+var_298], eax
0x1800112ce  mov     r9, r15
0x1800112d1  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800112d8  mov     rcx, [rcx+10h]
0x1800112dc  call    WPP_SF_SD
0x1800112e1  nop
0x1800112e2  lea     rcx, [rsp+2B8h+var_270]
0x1800112e7  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x1800112ec  nop
0x1800112ed  mov     rcx, [rbx]; hMutex
0x1800112f0  call    cs:__imp_ReleaseMutex
0x1800112f7  nop     dword ptr [rax+rax+00h]
0x1800112fc  nop
0x1800112fd  lea     rcx, [rsp+2B8h+var_248]; this
0x180011302  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180011307  jmp     loc_18001159F
0x18001130c  mov     rdi, [rsp+2B8h+var_270]
0x180011311  test    rdi, rdi
0x180011314  jnz     short loc_180011340
0x180011316  lea     rcx, [rsp+2B8h+var_270]
0x18001131b  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180011320  nop
0x180011321  mov     rcx, [rbx]; hMutex
0x180011324  call    cs:__imp_ReleaseMutex
0x18001132b  nop     dword ptr [rax+rax+00h]
0x180011330  nop
0x180011331  lea     rcx, [rsp+2B8h+var_248]; this
0x180011336  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001133b  jmp     loc_18001159F
0x180011340  mov     rcx, rdi; this
0x180011343  call    ?MatchFingerprint@CJob@@QEAAHXZ; CJob::MatchFingerprint(void)
0x180011348  test    eax, eax
0x18001134a  jnz     loc_18001142F
0x180011350  mov     rcx, cs:WPP_GLOBAL_Control
0x180011357  cmp     rcx, r12
0x18001135a  jz      short loc_180011385
0x18001135c  test    byte ptr [rcx+1Ch], 2
0x180011360  jz      short loc_180011385
0x180011362  cmp     byte ptr [rcx+19h], 3
0x180011366  jb      short loc_180011385
0x180011368  lea     edx, [rax+1Dh]
0x18001136b  mov     r9, r15
0x18001136e  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011375  mov     rcx, [rcx+10h]
0x180011379  call    WPP_SF_S
0x18001137e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011385  test    dword ptr [rdi+58h], 200000h
0x18001138c  jnz     loc_18001145F
0x180011392  cmp     rcx, r12
0x180011395  jz      short loc_1800113BB
0x180011397  test    byte ptr [rcx+1Ch], 2
0x18001139b  jz      short loc_1800113BB
0x18001139d  cmp     byte ptr [rcx+19h], 5
0x1800113a1  jb      short loc_1800113BB
0x1800113a3  mov     edx, 1Eh
0x1800113a8  mov     r9, r15
0x1800113ab  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800113b2  mov     rcx, [rcx+10h]
0x1800113b6  call    WPP_SF_S
0x1800113bb  mov     [rsp+2B8h+var_290], 0; struct _GUID *
0x1800113c4  mov     [rsp+2B8h+var_298], 0
0x1800113cd  mov     r9, r15
0x1800113d0  mov     r8, rdi
0x1800113d3  xor     edx, edx
0x1800113d5  mov     rcx, r13
0x1800113d8  call    ?RegisterWithRetry@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z; CompatibilityAdapter::RegisterWithRetry(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)
0x1800113dd  mov     esi, eax
0x1800113df  mov     [rsp+2B8h+var_278], eax
0x1800113e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113ea  cmp     rcx, r12
0x1800113ed  jz      short loc_180011417
0x1800113ef  test    byte ptr [rcx+1Ch], 2
0x1800113f3  jz      short loc_180011417
0x1800113f5  cmp     byte ptr [rcx+19h], 4
0x1800113f9  jb      short loc_180011417
0x1800113fb  mov     edx, 1Fh
0x180011400  mov     dword ptr [rsp+2B8h+var_298], eax; void *
0x180011404  mov     r9, r15
0x180011407  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001140e  mov     rcx, [rcx+10h]
0x180011412  call    WPP_SF_SD
0x180011417  test    esi, esi
0x180011419  jns     short loc_18001145F
0x18001141b  mov     r9d, esi; unsigned int
0x18001141e  mov     r8, r15; unsigned __int16 *
0x180011421  lea     rdx, COMPAT_TASK_UPDATE_FAILED; struct _EVENT_DESCRIPTOR *
0x180011428  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18001142d  jmp     short loc_18001145F
0x18001142f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011436  cmp     rcx, r12
0x180011439  jz      short loc_18001145F
0x18001143b  test    byte ptr [rcx+1Ch], 2
0x18001143f  jz      short loc_18001145F
0x180011441  cmp     byte ptr [rcx+19h], 4
0x180011445  jb      short loc_18001145F
0x180011447  mov     edx, 20h ; ' '
0x18001144c  mov     r9, r15
0x18001144f  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011456  mov     rcx, [rcx+10h]
0x18001145a  call    WPP_SF_S
0x18001145f  test    dword ptr [rdi+58h], 8000000h
0x180011466  jz      short loc_1800114BA
0x180011468  mov     rdx, r15; unsigned __int16 *
0x18001146b  call    ?StopJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z; CompatibilityAdapter::StopJob(ushort const *,CJob *)
0x180011470  mov     esi, eax
0x180011472  mov     [rsp+2B8h+var_278], eax
0x180011476  test    eax, eax
0x180011478  jns     loc_18001151F
0x18001147e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011485  cmp     rcx, r12
0x180011488  jz      short loc_1800114B2
0x18001148a  test    byte ptr [rcx+1Ch], 2
0x18001148e  jz      short loc_1800114B2
0x180011490  cmp     byte ptr [rcx+19h], 2
0x180011494  jb      short loc_1800114B2
0x180011496  mov     edx, 21h ; '!'
0x18001149b  mov     dword ptr [rsp+2B8h+var_298], eax
0x18001149f  mov     r9, r15
0x1800114a2  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800114a9  mov     rcx, [rcx+10h]
0x1800114ad  call    WPP_SF_SD
0x1800114b2  mov     r9d, 3
0x1800114b8  jmp     short loc_180011512
0x1800114ba  test    dword ptr [rdi+58h], 4000000h
0x1800114c1  jz      short loc_18001151F
0x1800114c3  mov     r8, rdi; struct CJob *
0x1800114c6  mov     rdx, r15; unsigned __int16 *
0x1800114c9  call    ?RunJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z; CompatibilityAdapter::RunJob(ushort const *,CJob *)
0x1800114ce  mov     esi, eax
0x1800114d0  mov     [rsp+2B8h+var_278], eax
0x1800114d4  test    eax, eax
0x1800114d6  jns     short loc_18001151F
0x1800114d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114df  cmp     rcx, r12
0x1800114e2  jz      short loc_18001150C
0x1800114e4  test    byte ptr [rcx+1Ch], 2
0x1800114e8  jz      short loc_18001150C
0x1800114ea  cmp     byte ptr [rcx+19h], 2
0x1800114ee  jb      short loc_18001150C
0x1800114f0  mov     edx, 22h ; '"'
0x1800114f5  mov     dword ptr [rsp+2B8h+var_298], eax
0x1800114f9  mov     r9, r15
0x1800114fc  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011503  mov     rcx, [rcx+10h]
0x180011507  call    WPP_SF_SD
0x18001150c  mov     r9d, 4; unsigned int
0x180011512  mov     dword ptr [rsp+2B8h+var_298], esi; unsigned int
0x180011516  mov     r8, r15; unsigned __int16 *
0x180011519  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x18001151e  nop
0x18001151f  lea     rcx, [rsp+2B8h+var_270]
0x180011524  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180011529  nop
0x18001152a  jmp     short loc_180011541
0x18001152c  lea     r12, WPP_GLOBAL_Control
0x180011533  mov     esi, [rsp+2B8h+var_278]
0x180011537  mov     r15, [rsp+2B8h+var_268]
0x18001153c  mov     rbx, [rsp+2B8h+var_260]
0x180011541  test    esi, esi
0x180011543  jns     short loc_180011585
0x180011545  mov     dword ptr [rsp+2B8h+var_298], esi; unsigned int
0x180011549  xor     r9d, r9d; unsigned int
0x18001154c  mov     r8, r15; unsigned __int16 *
0x18001154f  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x180011554  mov     rcx, cs:WPP_GLOBAL_Control
0x18001155b  cmp     rcx, r12
0x18001155e  jz      short loc_180011585
0x180011560  test    byte ptr [rcx+1Ch], 2
0x180011564  jz      short loc_180011585
0x180011566  cmp     byte ptr [rcx+19h], 2
0x18001156a  jb      short loc_180011585
0x18001156c  mov     edx, 23h ; '#'
0x180011571  mov     r9d, esi
0x180011574  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001157b  mov     rcx, [rcx+10h]
0x18001157f  call    WPP_SF_d
0x180011584  nop
0x180011585  mov     rcx, [rbx]; hMutex
0x180011588  call    cs:__imp_ReleaseMutex
0x18001158f  nop     dword ptr [rax+rax+00h]
0x180011594  nop
0x180011595  lea     rcx, [rsp+2B8h+var_248]; this
0x18001159a  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001159f  mov     rcx, [rsp+2B8h+var_38]
0x1800115a7  xor     rcx, rsp; StackCookie
0x1800115aa  call    __security_check_cookie
0x1800115af  mov     rbx, [rsp+2B8h+arg_10]
0x1800115b7  add     rsp, 290h
0x1800115be  pop     r15
0x1800115c0  pop     r13
0x1800115c2  pop     r12
0x1800115c4  pop     rdi
0x1800115c5  pop     rsi
0x1800115c6  retn
```
