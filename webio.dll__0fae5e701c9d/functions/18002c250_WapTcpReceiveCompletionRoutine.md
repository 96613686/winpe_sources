# WapTcpReceiveCompletionRoutine

- ea: `0x18002c250`
- end: `0x18002c944`
- name: `WapTcpReceiveCompletionRoutine`
- size: `1780`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180013284`
- `0x180014f30`
- `0x1800151d0`
- `0x1800153e0`
- `0x1800154c0`
- `0x1800180e0`
- `0x18002c250`
- `0x18002c94c`
- `0x1800464f4`
- `0x1800722f0`
- `0x180092564`
- `0x1800958c0`
- `0x18009592c`
- `0x1800959c8`
- `0x180096350`
- `0x1800971ec`
- `0x180097374`
- `0x180097810`
- `0x180097864`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002c5da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002c5da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c29a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c72f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c29a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c72f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c31c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c805`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c31c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c805`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c648`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c648`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c6e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c6e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c933`

## pseudocode

```c
void __fastcall WapTcpReceiveCompletionRoutine(char *lpMem, unsigned int a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v5; // r14
  unsigned int v6; // r15d
  unsigned int *v7; // rsi
  int v8; // r8d
  RTL_SRWLOCK *v9; // r12
  volatile signed __int32 *v10; // rcx
  char v11; // al
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rcx
  bool v15; // zf
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, _QWORD, __int64); // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // r14
  ULONGLONG TickCount64; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  ULONGLONG v25; // rsi
  char v26; // cl
  unsigned __int64 v27; // rsi
  RTL_SRWLOCK *v28; // rsi
  __int64 v29; // r8
  int v30; // ecx
  int v31; // eax
  RTL_SRWLOCK **Ptr; // rdx
  struct _RTL_CRITICAL_SECTION *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // [rsp+20h] [rbp-178h]
  BOOL v36; // [rsp+28h] [rbp-170h]
  int v37; // [rsp+30h] [rbp-168h]
  __int64 v38; // [rsp+40h] [rbp-158h] BYREF
  __int64 v39; // [rsp+48h] [rbp-150h] BYREF
  __int64 v40; // [rsp+50h] [rbp-148h] BYREF
  char *v41; // [rsp+58h] [rbp-140h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-138h] BYREF
  unsigned __int64 v43; // [rsp+68h] [rbp-130h] BYREF
  unsigned int v44; // [rsp+70h] [rbp-128h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-120h] BYREF
  __int64 v46; // [rsp+88h] [rbp-110h] BYREF
  __int64 v47; // [rsp+90h] [rbp-108h] BYREF
  __int64 v48; // [rsp+98h] [rbp-100h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+A0h] [rbp-F8h] BYREF
  __int64 *v50; // [rsp+B0h] [rbp-E8h]
  __int64 v51; // [rsp+B8h] [rbp-E0h]
  __int64 *v52; // [rsp+C0h] [rbp-D8h]
  __int64 v53; // [rsp+C8h] [rbp-D0h]
  __int64 *v54; // [rsp+D0h] [rbp-C8h]
  __int64 v55; // [rsp+D8h] [rbp-C0h]
  __int64 *v56; // [rsp+E0h] [rbp-B8h]
  __int64 v57; // [rsp+E8h] [rbp-B0h]
  char **v58; // [rsp+F0h] [rbp-A8h]
  __int64 v59; // [rsp+F8h] [rbp-A0h]
  unsigned int *v60; // [rsp+100h] [rbp-98h]
  __int64 v61; // [rsp+108h] [rbp-90h]
  __int64 *v62; // [rsp+110h] [rbp-88h]
  __int64 v63; // [rsp+118h] [rbp-80h]
  __int64 *v64; // [rsp+120h] [rbp-78h]
  __int64 v65; // [rsp+128h] [rbp-70h]
  GUID *p_ActivityId; // [rsp+130h] [rbp-68h]
  __int64 v67; // [rsp+138h] [rbp-60h]
  unsigned int *v68; // [rsp+140h] [rbp-58h]
  __int64 v69; // [rsp+148h] [rbp-50h]
  unsigned __int64 *v70; // [rsp+150h] [rbp-48h]
  __int64 v71; // [rsp+158h] [rbp-40h]

  v3 = *((_QWORD *)lpMem + 1);
  v5 = a3;
  v39 = a3;
  v6 = a2;
  v44 = a2;
  v7 = (unsigned int *)(v3 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  --*(_DWORD *)(v3 + 140);
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    v37 = *(_DWORD *)(v3 + 140);
    v36 = v7 == (unsigned int *)(v3 + 144);
    WPP_SF_qqlD(v37, 73, v8, v3, v3 + 64);
    if ( (xmmword_1800AD720 & 8) != 0 )
    {
      v36 = v7 == (unsigned int *)(v3 + 144);
      WPP_SF_qqD(1027, 74, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3, v3 + 64);
    }
  }
  v9 = (RTL_SRWLOCK *)(v3 + 72);
  if ( (unsigned __int8)WaCancelTwTimer(v3 + 72) )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 75, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3 + 64);
    *(_BYTE *)(v3 + 136) = 0;
    v10 = *(volatile signed __int32 **)(v3 + 8);
    if ( _InterlockedExchangeAdd(v10 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v10);
  }
  v11 = xmmword_1800AD720;
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    v36 = v7 == (unsigned int *)(v3 + 144);
    WPP_SF_qqD(1027, 76, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3, v3 + 64);
    v11 = xmmword_1800AD720;
  }
  v12 = *(unsigned int *)(v3 + 140);
  if ( (_DWORD)v12 )
  {
    if ( !*(_BYTE *)(v3 + 136) )
    {
      v18 = *(unsigned __int8 *)(v3 + 68);
      if ( (_BYTE)v18 )
      {
        v19 = *v7;
        if ( (_DWORD)v19 )
        {
          if ( (v11 & 8) != 0 )
            WPP_SF_qdlld(v12, v18, v19, v3 + 64, v12, 0, v18, *v7);
          *(_BYTE *)(v3 + 136) = 1;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v3 + 8) + 4LL));
          v20 = *v7;
          ActivityId = 0;
          v42 = v20;
          v38 = -1;
          if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
            WPP_SF_qdqq(
              (unsigned int)WapTcpIoTimeoutRoutine,
              v18,
              v19,
              v3 + 72,
              v20,
              (__int64)WapTcpIoTimeoutRoutine,
              v3);
          WaGetCurrentThreadToken(&v38);
          WaEtwControlActivityId(&ActivityId);
          v21 = v42;
          while ( 1 )
          {
            if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
              WPP_SF_d(1038, 10, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, (unsigned int)v21);
            TickCount64 = GetTickCount64();
            if ( (_DWORD)v21 )
              v25 = TickCount64 + v21 + 999;
            else
              v25 = TickCount64;
            v26 = BYTE1(xmmword_1800AD720);
            if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
            {
              WPP_SF_II(BYTE1(xmmword_1800AD720), v23, v24, TickCount64, v25, v36, v37);
              v26 = BYTE1(xmmword_1800AD720);
            }
            v27 = v25 / 0x3E8;
            v43 = v27;
            if ( (v26 & 0x40) != 0 )
              WPP_SF_d(1038, 12, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, (unsigned int)v27);
            v28 = (RTL_SRWLOCK *)((char *)WaTimerWheel + 24 * (v27 & 0x3FF) + 8);
            AcquireSRWLockExclusive(v28);
            v29 = *((unsigned int *)WaTimerWheel + 1);
            v30 = v43;
            if ( WaKirUcsanFixes25Q3 )
            {
              v31 = v43 - v29;
              v42 = v43 - v29;
              if ( (BYTE1(xmmword_1800AD720) & 0x40) == 0 )
                goto LABEL_37;
              v34 = 18;
            }
            else
            {
              v31 = v43 - v29;
              v42 = v43 - v29;
              if ( (BYTE1(xmmword_1800AD720) & 0x40) == 0 )
                goto LABEL_37;
              v34 = 19;
            }
            LODWORD(v35) = v21;
            WPP_SF_qdddd(v43, v34, v29, v9, v35, v31, v29, v43);
            v30 = v43;
            v31 = v42;
LABEL_37:
            if ( v31 > 0 )
            {
              WapUpdateTimerObjectOnInsert(
                (_DWORD)v9,
                v30,
                (unsigned int)WapTcpIoTimeoutRoutine,
                v3,
                (__int64)&v38,
                (__int64)&ActivityId);
              Ptr = (RTL_SRWLOCK **)v28[2].Ptr;
              v5 = v39;
              v6 = v44;
              if ( *Ptr != &v28[1] )
                __fastfail(3u);
              v9->Ptr = &v28[1];
              *(_QWORD *)(v3 + 80) = Ptr;
              *Ptr = v9;
              v28[2].Ptr = v9;
              ReleaseSRWLockExclusive(v28);
              if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
                WPP_SF_(1038, 20, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids);
              break;
            }
            ReleaseSRWLockExclusive(v28);
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
  {
    v14 = *((_QWORD *)lpMem + 1);
    v41 = lpMem + 16;
    v40 = *((_QWORD *)lpMem + 16);
    v42 = 0;
    *(_QWORD *)&ActivityId.Data1 = 0;
    v48 = 0;
    LODWORD(v43) = 1;
    v47 = v5;
    v44 = v6;
    v46 = *(_QWORD *)(v14 + 704);
    v38 = 0;
    v39 = *(_QWORD *)(v14 + 8);
    v50 = &v39;
    v52 = &v38;
    v54 = &v46;
    v56 = &v40;
    v58 = &v41;
    v60 = &v44;
    v62 = &v47;
    v64 = &v48;
    p_ActivityId = &ActivityId;
    v68 = &v42;
    v70 = &v43;
    v51 = 8;
    v53 = 8;
    v55 = 8;
    v57 = 8;
    v59 = 8;
    v61 = 4;
    v63 = 8;
    v65 = 8;
    v67 = 8;
    v69 = 4;
    v71 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)NetSocketRecvEntityComplete,
      v13,
      0xCu,
      &v49);
  }
  if ( !v6 && !v5 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
    *(_DWORD *)(v3 + 228) |= 4u;
    v33 = (struct _RTL_CRITICAL_SECTION *)(v3 + 24);
    if ( *(_DWORD *)(v3 + 224) == 5 )
    {
      *(_DWORD *)(v3 + 224) = 6;
      LeaveCriticalSection(v33);
      WapTcpIndicateCleanupEvent(v3);
    }
    else
    {
      LeaveCriticalSection(v33);
    }
  }
  v15 = lpMem[124] == 0;
  *((_DWORD *)lpMem + 26) = v6;
  *((_QWORD *)lpMem + 14) = v5;
  if ( v15 )
  {
    v16 = *((_QWORD *)lpMem + 12);
    v17 = (void (__fastcall *)(__int64, _QWORD, __int64))*((_QWORD *)lpMem + 11);
    lpMem[124] = 1;
    v17(v16, v6, v5);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 1, 0xFFFFFFFF) == 1 )
    WapTcpFreeIoContext(lpMem);
}

```

## disassembly

```asm
0x18002c250  mov     [rsp+arg_8], rbx
0x18002c255  mov     [rsp+arg_10], rsi
0x18002c25a  push    rdi
0x18002c25b  push    r12
0x18002c25d  push    r13
0x18002c25f  push    r14
0x18002c261  push    r15
0x18002c263  sub     rsp, 170h
0x18002c26a  mov     rax, cs:__security_cookie
0x18002c271  xor     rax, rsp
0x18002c274  mov     [rsp+198h+var_38], rax
0x18002c27c  mov     r13, [rcx+8]
0x18002c280  mov     rbx, rcx
0x18002c283  mov     r14, r8
0x18002c286  mov     [rsp+198h+var_150], r8
0x18002c28b  mov     r15d, edx
0x18002c28e  mov     [rsp+198h+var_128], edx
0x18002c292  lea     rcx, [r13+18h]; lpCriticalSection
0x18002c296  lea     rsi, [r13+40h]
0x18002c29a  call    cs:__imp_EnterCriticalSection
0x18002c2a1  nop     dword ptr [rax+rax+00h]
0x18002c2a6  dec     dword ptr [rsi+4Ch]
0x18002c2a9  mov     ecx, [rsi+4Ch]
0x18002c2ac  movzx   eax, byte ptr cs:xmmword_1800AD720
0x18002c2b3  lea     rdx, [r13+90h]
0x18002c2ba  test    al, 8
0x18002c2bc  jnz     loc_18002C79E
0x18002c2c2  lea     r12, [rsi+8]
0x18002c2c6  mov     rcx, r12
0x18002c2c9  call    WaCancelTwTimer
0x18002c2ce  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18002c2d5  test    al, al
0x18002c2d7  jz      short loc_18002C2FE
0x18002c2d9  test    byte ptr cs:xmmword_1800AD720, 8
0x18002c2e0  jnz     loc_18002C816
0x18002c2e6  mov     byte ptr [rsi+48h], 0
0x18002c2ea  mov     eax, edi
0x18002c2ec  mov     rcx, [r13+8]; lpMem
0x18002c2f0  lock xadd [rcx+4], eax
0x18002c2f5  cmp     eax, 1
0x18002c2f8  jz      loc_18002C721
0x18002c2fe  movzx   eax, byte ptr cs:xmmword_1800AD720
0x18002c305  test    al, 8
0x18002c307  jnz     loc_18002C834
0x18002c30d  mov     ecx, [rsi+4Ch]
0x18002c310  test    ecx, ecx
0x18002c312  jnz     loc_18002C548
0x18002c318  lea     rcx, [r13+18h]; lpCriticalSection
0x18002c31c  call    cs:__imp_LeaveCriticalSection
0x18002c323  nop     dword ptr [rax+rax+00h]
0x18002c328  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18002c32f  jz      loc_18002C4D5
0x18002c335  mov     rcx, [rbx+8]
0x18002c339  lea     rax, [rbx+10h]
0x18002c33d  mov     [rsp+198h+var_140], rax
0x18002c342  xor     edx, edx
0x18002c344  mov     rax, [rbx+80h]
0x18002c34b  mov     r9d, 0Ch
0x18002c351  mov     [rsp+198h+var_148], rax
0x18002c356  mov     [rsp+198h+var_138], edx
0x18002c35a  mov     qword ptr [rsp+198h+ActivityId.Data1], rdx
0x18002c35f  mov     [rsp+198h+var_100], rdx
0x18002c367  mov     dword ptr [rsp+198h+var_130], 1
0x18002c36f  mov     [rsp+198h+var_108], r14
0x18002c377  mov     [rsp+198h+var_128], r15d
0x18002c37c  mov     rax, [rcx+2C0h]
0x18002c383  mov     [rsp+198h+var_110], rax
0x18002c38b  mov     [rsp+198h+var_158], rdx
0x18002c390  lea     rdx, NetSocketRecvEntityComplete
0x18002c397  mov     rax, [rcx+8]
0x18002c39b  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18002c3a2  mov     [rsp+198h+var_150], rax
0x18002c3a7  lea     rax, [rsp+198h+var_150]
0x18002c3ac  mov     [rsp+198h+var_E8], rax
0x18002c3b4  lea     rax, [rsp+198h+var_158]
0x18002c3b9  mov     [rsp+198h+var_D8], rax
0x18002c3c1  lea     rax, [rsp+198h+var_110]
0x18002c3c9  mov     [rsp+198h+var_C8], rax
0x18002c3d1  lea     rax, [rsp+198h+var_148]
0x18002c3d6  mov     [rsp+198h+var_B8], rax
0x18002c3de  lea     rax, [rsp+198h+var_140]
0x18002c3e3  mov     [rsp+198h+var_A8], rax
0x18002c3eb  lea     rax, [rsp+198h+var_128]
0x18002c3f0  mov     [rsp+198h+var_98], rax
0x18002c3f8  lea     rax, [rsp+198h+var_108]
0x18002c400  mov     [rsp+198h+var_88], rax
0x18002c408  lea     rax, [rsp+198h+var_100]
0x18002c410  mov     [rsp+198h+var_78], rax
0x18002c418  lea     rax, [rsp+198h+ActivityId]
0x18002c41d  mov     [rsp+198h+var_68], rax
0x18002c425  lea     rax, [rsp+198h+var_138]
0x18002c42a  mov     [rsp+198h+var_58], rax
0x18002c432  lea     rax, [rsp+198h+var_130]
0x18002c437  mov     [rsp+198h+var_48], rax
0x18002c43f  lea     rax, [rsp+198h+var_F8]
0x18002c447  mov     [rsp+198h+var_178], rax
0x18002c44c  mov     [rsp+198h+var_E0], 8
0x18002c458  mov     [rsp+198h+var_D0], 8
0x18002c464  mov     [rsp+198h+var_C0], 8
0x18002c470  mov     [rsp+198h+var_B0], 8
0x18002c47c  mov     [rsp+198h+var_A0], 8
0x18002c488  mov     [rsp+198h+var_90], 4
0x18002c494  mov     [rsp+198h+var_80], 8
0x18002c4a0  mov     [rsp+198h+var_70], 8
0x18002c4ac  mov     [rsp+198h+var_60], 8
0x18002c4b8  mov     [rsp+198h+var_50], 4
0x18002c4c4  mov     [rsp+198h+var_40], 4
0x18002c4d0  call    McGenEventWrite_EventWriteTransfer
0x18002c4d5  test    r15d, r15d
0x18002c4d8  jnz     short loc_18002C4E3
0x18002c4da  test    r14, r14
0x18002c4dd  jz      loc_18002C72B
0x18002c4e3  cmp     byte ptr [rbx+7Ch], 0
0x18002c4e7  mov     [rbx+68h], r15d
0x18002c4eb  mov     [rbx+70h], r14
0x18002c4ef  jnz     short loc_18002C508
0x18002c4f1  mov     rcx, [rbx+60h]
0x18002c4f5  mov     r8, r14
0x18002c4f8  mov     rax, [rbx+58h]
0x18002c4fc  mov     edx, r15d
0x18002c4ff  mov     byte ptr [rbx+7Ch], 1
0x18002c503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c508  lock xadd [rbx+4], edi
0x18002c50d  cmp     edi, 1
0x18002c510  jnz     short loc_18002C51A
0x18002c512  mov     rcx, rbx; lpMem
0x18002c515  call    WapTcpFreeIoContext
0x18002c51a  mov     rcx, [rsp+198h+var_38]
0x18002c522  xor     rcx, rsp; StackCookie
0x18002c525  call    __security_check_cookie
0x18002c52a  lea     r11, [rsp+198h+var_28]
0x18002c532  mov     rbx, [r11+38h]
0x18002c536  mov     rsi, [r11+40h]
0x18002c53a  mov     rsp, r11
0x18002c53d  pop     r15
0x18002c53f  pop     r14
0x18002c541  pop     r13
0x18002c543  pop     r12
0x18002c545  pop     rdi
0x18002c546  retn
0x18002c548  cmp     byte ptr [rsi+48h], 0
0x18002c54c  jnz     loc_18002C318
0x18002c552  movzx   edx, byte ptr [rsi+4]
0x18002c556  test    dl, dl
0x18002c558  jz      loc_18002C318
0x18002c55e  mov     r8d, [rsi]
0x18002c561  test    r8d, r8d
0x18002c564  jz      loc_18002C318
0x18002c56a  test    al, 8
0x18002c56c  jnz     loc_18002C871
0x18002c572  mov     byte ptr [rsi+48h], 1
0x18002c576  mov     rax, [r13+8]
0x18002c57a  lock inc dword ptr [rax+4]
0x18002c57e  mov     eax, [rsi]
0x18002c580  xorps   xmm0, xmm0
0x18002c583  movups  xmmword ptr [rsp+198h+ActivityId.Data1], xmm0
0x18002c588  mov     [rsp+198h+var_138], eax
0x18002c58c  mov     [rsp+198h+var_158], rdi
0x18002c591  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18002c598  lea     rcx, WapTcpIoTimeoutRoutine
0x18002c59f  jnz     loc_18002C893
0x18002c5a5  lea     rcx, [rsp+198h+var_158]
0x18002c5aa  call    WaGetCurrentThreadToken
0x18002c5af  mov     edx, 2
0x18002c5b4  lea     rcx, [rsp+198h+ActivityId]; ActivityId
0x18002c5b9  call    WaEtwControlActivityId
0x18002c5be  mov     r14d, [rsp+198h+var_138]
0x18002c5c3  mov     r15, 624DD2F1A9FBE77h
0x18002c5cd  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18002c5d4  jnz     loc_18002C8AE
0x18002c5da  call    cs:__imp_GetTickCount64
0x18002c5e1  nop     dword ptr [rax+rax+00h]
0x18002c5e6  test    r14d, r14d
0x18002c5e9  jz      loc_18002C719
0x18002c5ef  lea     rsi, [r14+3E7h]
0x18002c5f6  add     rsi, rax
0x18002c5f9  movzx   ecx, byte ptr cs:xmmword_1800AD720+1
0x18002c600  test    cl, 40h
0x18002c603  jnz     loc_18002C8CC
0x18002c609  mov     rax, r15
0x18002c60c  mul     rsi
0x18002c60f  sub     rsi, rdx
0x18002c612  shr     rsi, 1
0x18002c615  add     rsi, rdx
0x18002c618  shr     rsi, 9
0x18002c61c  mov     [rsp+198h+var_130], rsi
0x18002c621  test    cl, 40h
0x18002c624  jnz     loc_18002C8E5
0x18002c62a  mov     rax, rsi
0x18002c62d  and     eax, 3FFh
0x18002c632  lea     rcx, [rax+rax*2]
0x18002c636  mov     rax, cs:WaTimerWheel
0x18002c63d  lea     rcx, [rcx+1]
0x18002c641  lea     rsi, [rax+rcx*8]
0x18002c645  mov     rcx, rsi; SRWLock
0x18002c648  call    cs:__imp_AcquireSRWLockExclusive
0x18002c64f  nop     dword ptr [rax+rax+00h]
0x18002c654  cmp     cs:WaKirUcsanFixes25Q3, 0
0x18002c65b  mov     rax, cs:WaTimerWheel
0x18002c662  mov     r8d, [rax+4]
0x18002c666  mov     rcx, [rsp+198h+var_130]
0x18002c66b  mov     eax, ecx
0x18002c66d  jnz     loc_18002C780
0x18002c673  sub     eax, r8d
0x18002c676  mov     [rsp+198h+var_138], eax
0x18002c67a  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18002c681  jnz     loc_18002C903
0x18002c687  test    eax, eax
0x18002c689  jle     loc_18002C930
0x18002c68f  lea     rax, [rsp+198h+ActivityId]
0x18002c694  mov     edx, ecx
0x18002c696  mov     [rsp+198h+var_170], rax
0x18002c69b  lea     r8, WapTcpIoTimeoutRoutine
0x18002c6a2  lea     rax, [rsp+198h+var_158]
0x18002c6a7  mov     r9, r13
0x18002c6aa  mov     rcx, r12
0x18002c6ad  mov     [rsp+198h+var_178], rax
0x18002c6b2  call    WapUpdateTimerObjectOnInsert
0x18002c6b7  mov     rdx, [rsi+10h]
0x18002c6bb  lea     rax, [rsi+8]
0x18002c6bf  mov     r14, [rsp+198h+var_150]
0x18002c6c4  mov     r15d, [rsp+198h+var_128]
0x18002c6c9  cmp     [rdx], rax
0x18002c6cc  jnz     loc_18002C779
0x18002c6d2  mov     [r12], rax
0x18002c6d6  mov     rcx, rsi; SRWLock
0x18002c6d9  mov     [r12+8], rdx
0x18002c6de  mov     [rdx], r12
0x18002c6e1  mov     [rax+8], r12
0x18002c6e5  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c6ec  nop     dword ptr [rax+rax+00h]
0x18002c6f1  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18002c6f8  jz      loc_18002C318
0x18002c6fe  mov     edx, 14h
0x18002c703  lea     r8, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids
0x18002c70a  mov     ecx, 40Eh
0x18002c70f  call    WPP_SF_
0x18002c714  jmp     loc_18002C318
0x18002c719  mov     rsi, rax
0x18002c71c  jmp     loc_18002C5F9
0x18002c721  call    WaDestroyConnection
0x18002c726  jmp     loc_18002C2FE
0x18002c72b  lea     rcx, [r13+18h]; lpCriticalSection
0x18002c72f  call    cs:__imp_EnterCriticalSection
0x18002c736  nop     dword ptr [rax+rax+00h]
0x18002c73b  or      dword ptr [r13+0E4h], 4
0x18002c743  lea     rcx, [r13+18h]; lpCriticalSection
0x18002c747  cmp     dword ptr [r13+0E0h], 5
0x18002c74f  jnz     loc_18002C805
0x18002c755  mov     dword ptr [r13+0E0h], 6
0x18002c760  call    cs:__imp_LeaveCriticalSection
0x18002c767  nop     dword ptr [rax+rax+00h]
0x18002c76c  mov     rcx, r13
0x18002c76f  call    WapTcpIndicateCleanupEvent
0x18002c774  jmp     loc_18002C4E3
0x18002c779  mov     ecx, 3
0x18002c77e  int     29h; Win8: RtlFailFast(ecx)
0x18002c780  sub     eax, r8d
0x18002c783  mov     [rsp+198h+var_138], eax
0x18002c787  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18002c78e  jz      loc_18002C687
0x18002c794  mov     edx, 12h
0x18002c799  jmp     loc_18002C908
0x18002c79e  xor     eax, eax
0x18002c7a0  mov     dword ptr [rsp+198h+var_168], ecx
0x18002c7a4  cmp     rsi, rdx
0x18002c7a7  mov     r9, r13
0x18002c7aa  mov     edx, 49h ; 'I'
0x18002c7af  setz    al
0x18002c7b2  mov     dword ptr [rsp+198h+var_170], eax
0x18002c7b6  mov     [rsp+198h+var_178], rsi
0x18002c7bb  call    WPP_SF_qqlD
0x18002c7c0  movzx   eax, byte ptr cs:xmmword_1800AD720
0x18002c7c7  lea     rdx, [r13+90h]
0x18002c7ce  test    al, 8
0x18002c7d0  jz      loc_18002C2C2
0x18002c7d6  xor     eax, eax
0x18002c7d8  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18002c7df  cmp     rsi, rdx
0x18002c7e2  mov     ecx, 403h
0x18002c7e7  mov     edx, 4Ah ; 'J'
0x18002c7ec  mov     r9, r13
0x18002c7ef  setz    al
0x18002c7f2  mov     dword ptr [rsp+198h+var_170], eax
0x18002c7f6  mov     [rsp+198h+var_178], rsi
0x18002c7fb  call    WPP_SF_qqD
0x18002c800  jmp     loc_18002C2C2
0x18002c805  call    cs:__imp_LeaveCriticalSection
0x18002c80c  nop     dword ptr [rax+rax+00h]
0x18002c811  jmp     loc_18002C4E3
0x18002c816  mov     edx, 4Bh ; 'K'
0x18002c81b  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x18002c822  mov     ecx, 403h
0x18002c827  mov     r9, rsi
0x18002c82a  call    WPP_SF_q
0x18002c82f  jmp     loc_18002C2E6
0x18002c834  xor     eax, eax
0x18002c836  lea     rdx, [r13+90h]
0x18002c83d  cmp     rsi, rdx
0x18002c840  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
  ... truncated ...
```
