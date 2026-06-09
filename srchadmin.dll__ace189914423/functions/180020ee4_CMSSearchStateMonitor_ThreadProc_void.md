# CMSSearchStateMonitor::_ThreadProc(void)

- ea: `0x180020ee4`
- end: `0x1800212f9`
- name: `?_ThreadProc@CMSSearchStateMonitor@@AEAAKXZ`
- size: `1045`
- prototype: `unsigned int __fastcall(CMSSearchStateMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021460`

## callees

- `0x180005cc0`
- `0x180005cf0`
- `0x1800061c0`
- `0x180010680`
- `0x18001f014`
- `0x180020430`
- `0x1800204fc`
- `0x18002055c`
- `0x1800209a0`
- `0x180020ee4`
- `0x18002c5b4`
- `0x18002c6ac`
- `0x18002c780`
- `0x18002c7bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020f46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800212a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800212a3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021052`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180021052`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800210eb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18002118b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800211be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18002123e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800210eb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18002118b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x1800211be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18002123e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSSearchStateMonitor::_ThreadProc(CMSSearchStateMonitor *this)
{
  int Error; // esi
  __int64 v3; // rdi
  HANDLE EventW; // rax
  struct IGatherManagerAdmin3 *v5; // rdx
  unsigned __int64 v6; // r14
  int v7; // eax
  int v8; // r15d
  DWORD v9; // r14d
  int v10; // esi
  __int64 v11; // rcx
  int v12; // ecx
  unsigned __int64 v13; // rsi
  _DWORD *v14; // r14
  unsigned __int64 v15; // rsi
  int started; // eax
  HANDLE v17; // rcx
  DWORD dwindex; // [rsp+30h] [rbp-D0h] BYREF
  int v20[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v21[14]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE pHandles[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  _DWORD v26[24]; // [rsp+E0h] [rbp-20h] BYREF

  Error = 0;
  *(_OWORD *)pHandles = 0;
  v23 = 0;
  v24 = 0;
  v25 = *((_QWORD *)this + 8);
  LODWORD(v3) = 0;
  do
  {
    if ( (unsigned int)v3 >= 5 )
      break;
    EventW = CreateEventW(0, 0, 0, 0);
    pHandles[(int)v3] = EventW;
    if ( !EventW )
      Error = ResultFromLastError();
    LODWORD(v3) = v3 + 1;
  }
  while ( Error >= 0 );
  v21[11] = 0;
  v21[0] = &CServiceMonitorCPL::`vftable';
  if ( Error >= 0 )
  {
    v21[12] = *((_QWORD *)&v23 + 1);
    v21[13] = v24;
    Error = CServiceMonitorBase::InitializeServiceListening((CServiceMonitorBase *)v21, L"WSearch");
  }
  `eh vector constructor iterator'(
    v26,
    0x20u,
    3u,
    (void (*)(void *))CRegMonitor::CRegMonitor,
    (void (*)(void *))CRegMonitor::~CRegMonitor);
  v6 = 0;
  if ( Error >= 0 )
  {
    while ( v6 < 3 )
    {
      *(_QWORD *)&v26[8 * v6 + 4] = pHandles[v6];
      v7 = StrDupUsingNew(
             (const unsigned __int16 *)*(&S_REGMON_SETTINGS + 2 * v6),
             (unsigned __int16 **)&v26[8 * v6 + 6]);
      ++v6;
      if ( v7 < 0 )
        goto LABEL_58;
    }
    v8 = 1;
    v9 = -1;
    v10 = 1;
    do
    {
      dwindex = 0;
      if ( !v10 || CoWaitForMultipleHandles(2u, v9, 6u, pHandles, &dwindex) == -2147417835 )
      {
        switch ( *((_DWORD *)this + 2) )
        {
          case 1:
            if ( (int)CMSSAdmin::InitGatherAdmin((CMSSearchStateMonitor *)((char *)this + 16), v5) < 0 )
            {
LABEL_55:
              v9 = 1000;
              goto LABEL_56;
            }
            *((_DWORD *)this + 2) = 2;
            goto LABEL_50;
          case 2:
            if ( (int)CMSSAdmin::InitIndexerPlugin((CMSSearchStateMonitor *)((char *)this + 16)) < 0 )
              goto LABEL_55;
            *((_DWORD *)this + 2) = 3;
            goto LABEL_50;
          case 3:
            v20[0] = 0;
            if ( (int)CMSSAdmin::GetNumberOfIndexedDocs((CMSSearchStateMonitor *)((char *)this + 16), v20) >= 0 )
            {
              v15 = 0;
              do
              {
                if ( v15 >= 3 )
                {
                  *((_DWORD *)this + 2) = 4;
                  goto LABEL_50;
                }
                started = CRegMonitor::StartSubkeyMonitoring((CRegMonitor *)&v26[8 * v15++]);
              }
              while ( started >= 0 );
              while ( v15 )
                CRegMonitor::StopSubkeyMonitoring((CRegMonitor *)(&v23 + 2 * v15++));
            }
            v9 = 3000;
            goto LABEL_56;
          case 4:
            v12 = 0;
            v13 = 0;
            while ( v13 < 3 )
            {
              v14 = &v26[8 * v13];
              if ( v26[8 * v13 + 1] )
                v12 = CRegMonitor::StartSubkeyMonitoring((CRegMonitor *)&v26[8 * v13]);
              if ( v12 >= 0 && *v14 )
              {
                PostMessageW(*((HWND *)this + 6), *((_DWORD *)&S_REGMON_SETTINGS + 4 * v13 + 2), 0, 0);
                v12 = 0;
                *v14 = 0;
                ++v13;
              }
              else
              {
                ++v13;
                if ( v12 < 0 )
                {
                  v9 = 3000;
                  v10 = 1;
                  *((_DWORD *)this + 2) = 1;
                  PostMessageW(*((HWND *)this + 6), 0x8410u, 0, 0);
                  goto LABEL_57;
                }
              }
            }
LABEL_25:
            v9 = -1;
LABEL_56:
            v10 = 1;
            break;
        }
      }
      else
      {
        v11 = dwindex;
        switch ( dwindex )
        {
          case 3u:
            if ( !*((_DWORD *)this + 2) )
            {
              *((_DWORD *)this + 2) = 1;
LABEL_50:
              PostMessageW(*((HWND *)this + 6), 0x8410u, 0, 0);
              v10 = 0;
            }
            break;
          case 4u:
            *((_DWORD *)this + 2) = 0;
            PostMessageW(*((HWND *)this + 6), 0x8410u, 0, 0);
            CMSSAdmin::UnInit((CMSSearchStateMonitor *)((char *)this + 16));
            goto LABEL_25;
          case 5u:
            if ( *((_DWORD *)this + 14) == 2 )
              v8 = 0;
            break;
          default:
            if ( dwindex < 3 )
            {
              if ( *((_DWORD *)this + 2) == 4 )
                v26[8 * dwindex] = 1;
              v9 = (((int)CRegMonitor::StartSubkeyMonitoring((CRegMonitor *)&v26[8 * v11]) >> 31) & 0xFFFFFC17) + 1000;
              goto LABEL_56;
            }
            break;
        }
      }
LABEL_57:
      ;
    }
    while ( v8 );
  }
LABEL_58:
  CServiceMonitorBase::UninitializeServiceListening((CServiceMonitorBase *)v21);
  while ( 1 )
  {
    v3 = (unsigned int)(v3 - 1);
    if ( (int)v3 <= 0 )
      break;
    v17 = pHandles[v3];
    if ( v17 )
      CloseHandle(v17);
  }
  CMSSAdmin::UnInit((CMSSearchStateMonitor *)((char *)this + 16));
  `eh vector destructor iterator'(v26, 0x20u, 3u, (void (*)(void *))CRegMonitor::~CRegMonitor);
  return 0;
}

```

## disassembly

```asm
0x180020ee4  mov     [rsp-8+arg_8], rbx
0x180020ee9  mov     [rsp-8+arg_10], rsi
0x180020eee  push    rbp
0x180020eef  push    rdi
0x180020ef0  push    r13
0x180020ef2  push    r14
0x180020ef4  push    r15
0x180020ef6  lea     rbp, [rsp-50h]
0x180020efb  sub     rsp, 150h
0x180020f02  mov     rax, cs:__security_cookie
0x180020f09  xor     rax, rsp
0x180020f0c  mov     [rbp+70h+var_30], rax
0x180020f10  mov     rbx, rcx
0x180020f13  xor     esi, esi
0x180020f15  xorps   xmm0, xmm0
0x180020f18  movdqu  xmmword ptr [rbp+70h+pHandles], xmm0
0x180020f1d  xorps   xmm1, xmm1
0x180020f20  movdqu  [rbp+70h+var_B0], xmm1
0x180020f25  mov     [rbp+70h+var_A0], rsi
0x180020f29  mov     rax, [rcx+40h]
0x180020f2d  mov     [rbp+70h+var_98], rax
0x180020f31  xor     edi, edi
0x180020f33  lea     r13d, [rsi+1]
0x180020f37  cmp     edi, 5
0x180020f3a  jnb     short loc_180020F6A
0x180020f3c  xor     r9d, r9d; lpName
0x180020f3f  xor     r8d, r8d; bInitialState
0x180020f42  xor     edx, edx; bManualReset
0x180020f44  xor     ecx, ecx; lpEventAttributes
0x180020f46  call    cs:__imp_CreateEventW
0x180020f4c  mov     rcx, rax
0x180020f4f  movsxd  rax, edi
0x180020f52  mov     [rbp+rax*8+70h+pHandles], rcx
0x180020f57  test    rcx, rcx
0x180020f5a  jnz     short loc_180020F63
0x180020f5c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180020f61  mov     esi, eax
0x180020f63  add     edi, r13d
0x180020f66  test    esi, esi
0x180020f68  jns     short loc_180020F37
0x180020f6a  mov     [rbp+70h+var_D8], 0
0x180020f72  lea     rax, ??_7CServiceMonitorCPL@@6B@; const CServiceMonitorCPL::`vftable'
0x180020f79  mov     [rsp+170h+var_130], rax
0x180020f7e  test    esi, esi
0x180020f80  js      short loc_180020FA5
0x180020f82  mov     rax, qword ptr [rbp+70h+var_B0+8]
0x180020f86  mov     [rbp+70h+var_D0], rax
0x180020f8a  mov     rax, [rbp+70h+var_A0]
0x180020f8e  mov     [rbp+70h+var_C8], rax
0x180020f92  lea     rdx, ServiceName; "WSearch"
0x180020f99  lea     rcx, [rsp+170h+var_130]; this
0x180020f9e  call    ?InitializeServiceListening@CServiceMonitorBase@@QEAAJPEBG@Z; CServiceMonitorBase::InitializeServiceListening(ushort const *)
0x180020fa3  mov     esi, eax
0x180020fa5  lea     r15, ??1CRegMonitor@@QEAA@XZ; CRegMonitor::~CRegMonitor(void)
0x180020fac  mov     [rsp+170h+lpdwindex], r15; void (*)(void *)
0x180020fb1  lea     r9, ??0CRegMonitor@@QEAA@XZ; void (*)(void *)
0x180020fb8  mov     edx, 20h ; ' '; unsigned __int64
0x180020fbd  lea     r8d, [rdx-1Dh]; unsigned __int64
0x180020fc1  lea     rcx, [rbp+70h+var_90]; void *
0x180020fc5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180020fca  nop
0x180020fcb  xor     r14d, r14d
0x180020fce  test    esi, esi
0x180020fd0  js      loc_18002128D
0x180020fd6  lea     r8, ?S_REGMON_SETTINGS@@3PAU_unnamed_type_S_REGMON_SETTINGS_@@A; _unnamed_type_S_REGMON_SETTINGS_ near * S_REGMON_SETTINGS
0x180020fdd  cmp     r14, 3
0x180020fe1  jnb     short loc_18002101D
0x180020fe3  mov     rcx, r14
0x180020fe6  shl     rcx, 5
0x180020fea  mov     rax, [rbp+r14*8+70h+pHandles]
0x180020fef  mov     [rbp+rcx+70h+var_80], rax
0x180020ff4  lea     rdx, [rbp+70h+var_78]
0x180020ff8  add     rdx, rcx; unsigned __int16 **
0x180020ffb  mov     rcx, r14
0x180020ffe  add     rcx, rcx
0x180021001  mov     rcx, [r8+rcx*8]; unsigned __int16 *
0x180021005  call    ?StrDupUsingNew@@YAJPEBGPEAPEAG@Z; StrDupUsingNew(ushort const *,ushort * *)
0x18002100a  add     r14, r13
0x18002100d  test    eax, eax
0x18002100f  lea     r8, ?S_REGMON_SETTINGS@@3PAU_unnamed_type_S_REGMON_SETTINGS_@@A; _unnamed_type_S_REGMON_SETTINGS_ near * S_REGMON_SETTINGS
0x180021016  jns     short loc_180020FDD
0x180021018  jmp     loc_18002128D
0x18002101d  mov     r15d, r13d
0x180021020  or      r14d, 0FFFFFFFFh
0x180021024  mov     esi, r13d
0x180021027  mov     [rsp+170h+dwindex], 0
0x18002102f  test    esi, esi
0x180021031  jz      loc_180021116
0x180021037  lea     rax, [rsp+170h+dwindex]
0x18002103c  mov     [rsp+170h+lpdwindex], rax; lpdwindex
0x180021041  lea     r9, [rbp+70h+pHandles]; pHandles
0x180021045  mov     r8d, 6; cHandles
0x18002104b  mov     edx, r14d; dwTimeout
0x18002104e  lea     ecx, [r8-4]; dwFlags
0x180021052  call    cs:__imp_CoWaitForMultipleHandles
0x180021058  cmp     eax, 80010115h
0x18002105d  jz      loc_180021116
0x180021063  mov     ecx, [rsp+170h+dwindex]
0x180021067  mov     eax, ecx
0x180021069  sub     eax, 3
0x18002106c  jz      loc_180021103
0x180021072  sub     eax, 1
0x180021075  jz      short loc_1800210D5
0x180021077  cmp     eax, 1
0x18002107a  jz      short loc_1800210C3
0x18002107c  cmp     ecx, 3
0x18002107f  jnb     loc_18002127D
0x180021085  cmp     dword ptr [rbx+8], 4
0x180021089  jnz     short loc_180021096
0x18002108b  mov     eax, ecx
0x18002108d  shl     rax, 5
0x180021091  mov     [rbp+rax+70h+var_90], r13d
0x180021096  mov     rax, rcx
0x180021099  shl     rax, 5
0x18002109d  lea     rcx, [rbp+70h+var_90]
0x1800210a1  add     rcx, rax; this
0x1800210a4  call    ?StartSubkeyMonitoring@CRegMonitor@@QEAAJXZ; CRegMonitor::StartSubkeyMonitoring(void)
0x1800210a9  mov     r14d, eax
0x1800210ac  sar     r14d, 1Fh
0x1800210b0  and     r14d, 0FFFFFC17h
0x1800210b7  add     r14d, 3E8h
0x1800210be  jmp     loc_18002127A
0x1800210c3  cmp     dword ptr [rbx+38h], 2
0x1800210c7  jnz     loc_18002127D
0x1800210cd  xor     r15d, r15d
0x1800210d0  jmp     loc_18002127D
0x1800210d5  mov     dword ptr [rbx+8], 0
0x1800210dc  xor     r9d, r9d; lParam
0x1800210df  xor     r8d, r8d; wParam
0x1800210e2  mov     edx, 8410h; Msg
0x1800210e7  mov     rcx, [rbx+30h]; hWnd
0x1800210eb  call    cs:__imp_PostMessageW
0x1800210f1  lea     rcx, [rbx+10h]; this
0x1800210f5  call    ?UnInit@CMSSAdmin@@QEAAXXZ; CMSSAdmin::UnInit(void)
0x1800210fa  or      r14d, 0FFFFFFFFh
0x1800210fe  jmp     loc_18002127A
0x180021103  cmp     dword ptr [rbx+8], 0
0x180021107  jnz     loc_18002127D
0x18002110d  mov     [rbx+8], r13d
0x180021111  jmp     loc_18002122F
0x180021116  mov     ecx, [rbx+8]
0x180021119  sub     ecx, 1
0x18002111c  jz      loc_18002125E
0x180021122  sub     ecx, 1
0x180021125  jz      loc_180021248
0x18002112b  sub     ecx, 1
0x18002112e  jz      loc_1800211C9
0x180021134  cmp     ecx, 1
0x180021137  jnz     loc_18002127D
0x18002113d  xor     ecx, ecx
0x18002113f  xor     esi, esi
0x180021141  cmp     rsi, 3
0x180021145  jnb     short loc_1800210FA
0x180021147  mov     rax, rsi
0x18002114a  shl     rax, 5
0x18002114e  lea     r14, [rbp+70h+var_90]
0x180021152  add     r14, rax
0x180021155  cmp     [rbp+rax+70h+var_8C], 0
0x18002115a  jz      short loc_180021166
0x18002115c  mov     rcx, r14; this
0x18002115f  call    ?StartSubkeyMonitoring@CRegMonitor@@QEAAJXZ; CRegMonitor::StartSubkeyMonitoring(void)
0x180021164  mov     ecx, eax
0x180021166  test    ecx, ecx
0x180021168  js      short loc_18002119B
0x18002116a  cmp     dword ptr [r14], 0
0x18002116e  jz      short loc_18002119B
0x180021170  mov     rdx, rsi
0x180021173  add     rdx, rdx
0x180021176  xor     r9d, r9d; lParam
0x180021179  xor     r8d, r8d; wParam
0x18002117c  lea     rax, ?S_REGMON_SETTINGS@@3PAU_unnamed_type_S_REGMON_SETTINGS_@@A; _unnamed_type_S_REGMON_SETTINGS_ near * S_REGMON_SETTINGS
0x180021183  mov     edx, [rax+rdx*8+8]; Msg
0x180021187  mov     rcx, [rbx+30h]; hWnd
0x18002118b  call    cs:__imp_PostMessageW
0x180021191  xor     ecx, ecx
0x180021193  mov     [r14], ecx
0x180021196  add     rsi, r13
0x180021199  jmp     short loc_180021141
0x18002119b  add     rsi, r13
0x18002119e  test    ecx, ecx
0x1800211a0  jns     short loc_180021141
0x1800211a2  mov     r14d, 0BB8h
0x1800211a8  mov     esi, r13d
0x1800211ab  mov     [rbx+8], r13d
0x1800211af  xor     r9d, r9d; lParam
0x1800211b2  xor     r8d, r8d; wParam
0x1800211b5  mov     edx, 8410h; Msg
0x1800211ba  mov     rcx, [rbx+30h]; hWnd
0x1800211be  call    cs:__imp_PostMessageW
0x1800211c4  jmp     loc_18002127D
0x1800211c9  mov     [rsp+170h+var_13C], 0
0x1800211d1  lea     rcx, [rbx+10h]; this
0x1800211d5  lea     rdx, [rsp+170h+var_13C]; int *
0x1800211da  call    ?GetNumberOfIndexedDocs@CMSSAdmin@@QEAAJPEAH@Z; CMSSAdmin::GetNumberOfIndexedDocs(int *)
0x1800211df  test    eax, eax
0x1800211e1  js      short loc_180021220
0x1800211e3  xor     esi, esi
0x1800211e5  cmp     rsi, 3
0x1800211e9  jnb     short loc_180021228
0x1800211eb  mov     rax, rsi
0x1800211ee  shl     rax, 5
0x1800211f2  lea     rcx, [rbp+70h+var_90]
0x1800211f6  add     rcx, rax; this
0x1800211f9  call    ?StartSubkeyMonitoring@CRegMonitor@@QEAAJXZ; CRegMonitor::StartSubkeyMonitoring(void)
0x1800211fe  add     rsi, r13
0x180021201  test    eax, eax
0x180021203  jns     short loc_1800211E5
0x180021205  jmp     short loc_18002121B
0x180021207  mov     rax, rsi
0x18002120a  shl     rax, 5
0x18002120e  lea     rcx, [rbp+rax+70h+var_B0]; this
0x180021213  call    ?StopSubkeyMonitoring@CRegMonitor@@QEAAXXZ; CRegMonitor::StopSubkeyMonitoring(void)
0x180021218  add     rsi, r13
0x18002121b  cmp     rsi, r13
0x18002121e  jnb     short loc_180021207
0x180021220  mov     r14d, 0BB8h
0x180021226  jmp     short loc_18002127A
0x180021228  mov     dword ptr [rbx+8], 4
0x18002122f  xor     r9d, r9d; lParam
0x180021232  xor     r8d, r8d; wParam
0x180021235  mov     edx, 8410h; Msg
0x18002123a  mov     rcx, [rbx+30h]; hWnd
0x18002123e  call    cs:__imp_PostMessageW
0x180021244  xor     esi, esi
0x180021246  jmp     short loc_18002127D
0x180021248  lea     rcx, [rbx+10h]; this
0x18002124c  call    ?InitIndexerPlugin@CMSSAdmin@@QEAAJXZ; CMSSAdmin::InitIndexerPlugin(void)
0x180021251  test    eax, eax
0x180021253  js      short loc_180021274
0x180021255  mov     dword ptr [rbx+8], 3
0x18002125c  jmp     short loc_18002122F
0x18002125e  lea     rcx, [rbx+10h]; this
0x180021262  call    ?InitGatherAdmin@CMSSAdmin@@QEAAJPEAUIGatherManagerAdmin3@@@Z; CMSSAdmin::InitGatherAdmin(IGatherManagerAdmin3 *)
0x180021267  test    eax, eax
0x180021269  js      short loc_180021274
0x18002126b  mov     dword ptr [rbx+8], 2
0x180021272  jmp     short loc_18002122F
0x180021274  mov     r14d, 3E8h
0x18002127a  mov     esi, r13d
0x18002127d  test    r15d, r15d
0x180021280  jnz     loc_180021027
0x180021286  lea     r15, ??1CRegMonitor@@QEAA@XZ; CRegMonitor::~CRegMonitor(void)
0x18002128d  lea     rcx, [rsp+170h+var_130]; this
0x180021292  call    ?UninitializeServiceListening@CServiceMonitorBase@@QEAAXXZ; CServiceMonitorBase::UninitializeServiceListening(void)
0x180021297  jmp     short loc_1800212A9
0x180021299  mov     rcx, [rbp+rdi*8+70h+pHandles]; hObject
0x18002129e  test    rcx, rcx
0x1800212a1  jz      short loc_1800212A9
0x1800212a3  call    cs:__imp_CloseHandle
0x1800212a9  sub     edi, r13d
0x1800212ac  test    edi, edi
0x1800212ae  jg      short loc_180021299
0x1800212b0  lea     rcx, [rbx+10h]; this
0x1800212b4  call    ?UnInit@CMSSAdmin@@QEAAXXZ; CMSSAdmin::UnInit(void)
0x1800212b9  nop
0x1800212ba  mov     r9, r15; void (*)(void *)
0x1800212bd  mov     edx, 20h ; ' '; unsigned __int64
0x1800212c2  lea     r8d, [rdx-1Dh]; unsigned __int64
0x1800212c6  lea     rcx, [rbp+70h+var_90]; void *
0x1800212ca  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800212cf  xor     eax, eax
0x1800212d1  mov     rcx, [rbp+70h+var_30]
0x1800212d5  xor     rcx, rsp; StackCookie
0x1800212d8  call    __security_check_cookie
0x1800212dd  lea     r11, [rsp+170h+var_20]
0x1800212e5  mov     rbx, [r11+38h]
0x1800212e9  mov     rsi, [r11+40h]
0x1800212ed  mov     rsp, r11
0x1800212f0  pop     r15
0x1800212f2  pop     r14
0x1800212f4  pop     r13
0x1800212f6  pop     rdi
0x1800212f7  pop     rbp
0x1800212f8  retn
```
