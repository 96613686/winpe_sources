# WapTcpSendCompletionRoutine

- ea: `0x1800442f0`
- end: `0x1800449e9`
- name: `WapTcpSendCompletionRoutine`
- size: `1785`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180012700`
- `0x180013284`
- `0x180014f30`
- `0x1800151d0`
- `0x1800153e0`
- `0x1800154c0`
- `0x1800180e0`
- `0x1800442f0`
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

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180044634`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180044634`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004433f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004433f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800443f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004469d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800447fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004469d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800447fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004472e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044843`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044862`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800449bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004472e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044843`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180044862`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800449bd`

## pseudocode

```c
__int64 __fastcall WapTcpSendCompletionRoutine(char *lpMem, unsigned int a2, __int64 a3)
{
  __int64 v3; // r13
  char *v4; // rbx
  __int64 v5; // r12
  unsigned int *v6; // rdi
  int v7; // ecx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rsi
  unsigned __int8 v10; // r15
  volatile signed __int32 *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  bool v15; // zf
  __int64 result; // rax
  __int64 v17; // rcx
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64); // rax
  int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // eax
  ULONGLONG TickCount64; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  ULONGLONG v25; // rdi
  char v26; // cl
  unsigned __int64 v27; // r12
  RTL_SRWLOCK *v28; // rdi
  __int64 v29; // r8
  __int64 v30; // rcx
  int v31; // r15d
  RTL_SRWLOCK **v32; // rcx
  __int64 v33; // rdx
  RTL_SRWLOCK *v34; // r14
  _QWORD *Ptr; // rax
  void **v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+30h] [rbp-D0h]
  char *v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  char *v44; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+B0h] [rbp-50h] BYREF
  char **v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 *v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int64 *v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  char **v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  unsigned int *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  __int64 *v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  __int64 *v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  GUID *p_ActivityId; // [rsp+140h] [rbp+40h]
  __int64 v70; // [rsp+148h] [rbp+48h]
  __int64 *v71; // [rsp+150h] [rbp+50h]
  __int64 v72; // [rsp+158h] [rbp+58h]
  __int64 *v73; // [rsp+160h] [rbp+60h]
  __int64 v74; // [rsp+168h] [rbp+68h]

  v3 = *((_QWORD *)lpMem + 1);
  v4 = lpMem;
  v41 = lpMem;
  v5 = a3;
  v47 = a3;
  v6 = (unsigned int *)(v3 + 144);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  --*(_DWORD *)(v3 + 220);
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    v39 = *(_DWORD *)(v3 + 220);
    v38 = 1;
    WPP_SF_qqlD(v7, 73, v8, v3, v3 + 144);
    if ( (xmmword_1800AD720 & 8) != 0 )
    {
      v38 = 1;
      WPP_SF_qqD(1027, 74, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3, v3 + 144);
    }
  }
  v9 = (RTL_SRWLOCK *)(v3 + 152);
  v10 = 0;
  if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
    WPP_SF_q(1038, 21, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, v3 + 152);
  if ( WaKirUcsanFixes25Q3 )
  {
    if ( !*(_BYTE *)(v3 + 168) )
      goto LABEL_6;
  }
  else if ( !*(_BYTE *)(v3 + 168) )
  {
    goto LABEL_6;
  }
  v34 = (RTL_SRWLOCK *)((char *)WaTimerWheel + 24 * (*(_DWORD *)(v3 + 172) & 0x3FF) + 8);
  AcquireSRWLockExclusive(v34);
  if ( *(_BYTE *)(v3 + 168) )
  {
    Ptr = v9->Ptr;
    if ( *((RTL_SRWLOCK **)v9->Ptr + 1) != v9 )
      goto LABEL_47;
    v36 = *(void ***)(v3 + 160);
    if ( *v36 != v9 )
      goto LABEL_47;
    *v36 = Ptr;
    Ptr[1] = v36;
    *(_QWORD *)(v3 + 160) = v3 + 152;
    v9->Ptr = v9;
    *(_BYTE *)(v3 + 168) = 0;
    ReleaseSRWLockExclusive(v34);
    WapUpdateTimerObjectOnCancel(v3 + 152);
    v10 = 1;
  }
  else
  {
    ReleaseSRWLockExclusive(v34);
  }
LABEL_6:
  if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
    WPP_SF_d(1038, 22, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, v10);
  if ( v10 )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_q(1027, 75, WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3 + 144);
    *(_BYTE *)(v3 + 216) = 0;
    v11 = *(volatile signed __int32 **)(v3 + 8);
    if ( _InterlockedExchangeAdd(v11 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v11);
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
  {
    v38 = 1;
    WPP_SF_qqD(1027, 76, (unsigned int)WPP_14086b36644f38024399eb8d606249d9_Traceguids, v3, v3 + 144);
  }
  v12 = *(unsigned int *)(v3 + 220);
  if ( (_DWORD)v12 )
  {
    if ( !*(_BYTE *)(v3 + 216) )
    {
      v19 = *(unsigned __int8 *)(v3 + 148);
      if ( (_BYTE)v19 )
      {
        v20 = *v6;
        if ( (_DWORD)v20 )
        {
          if ( (xmmword_1800AD720 & 8) != 0 )
            WPP_SF_qdlld(v20, v12, v8, v3 + 144, v12, 0, v19, *v6);
          *(_BYTE *)(v3 + 216) = 1;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v3 + 8) + 4LL));
          v21 = *v6;
          ActivityId = 0;
          v45 = v21;
          v46 = -1;
          if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
            WPP_SF_qdqq(
              (unsigned int)WapTcpIoTimeoutRoutine,
              v12,
              v8,
              v3 + 152,
              v21,
              (__int64)WapTcpIoTimeoutRoutine,
              v3);
          WaGetCurrentThreadToken(&v46);
          WaEtwControlActivityId(&ActivityId);
          while ( 1 )
          {
            if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
              WPP_SF_d(1038, 10, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, v45);
            TickCount64 = GetTickCount64();
            if ( v45 )
              v25 = TickCount64 + v45 + 999LL;
            else
              v25 = TickCount64;
            v26 = BYTE1(xmmword_1800AD720);
            if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
            {
              WPP_SF_II(BYTE1(xmmword_1800AD720), v23, v24, TickCount64, v25, v38, v39);
              v26 = BYTE1(xmmword_1800AD720);
            }
            v27 = v25 / 0x3E8;
            if ( (v26 & 0x40) != 0 )
              WPP_SF_d(1038, 12, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids, (unsigned int)v27);
            v28 = (RTL_SRWLOCK *)((char *)WaTimerWheel + 24 * ((v25 / 0x3E8) & 0x3FF) + 8);
            AcquireSRWLockExclusive(v28);
            v30 = *((unsigned int *)WaTimerWheel + 1);
            if ( WaKirUcsanFixes25Q3 )
            {
              v31 = v27 - v30;
              if ( (BYTE1(xmmword_1800AD720) & 0x40) == 0 )
                goto LABEL_41;
              v33 = 18;
            }
            else
            {
              v31 = v27 - v30;
              if ( (BYTE1(xmmword_1800AD720) & 0x40) == 0 )
                goto LABEL_41;
              v33 = 19;
            }
            LODWORD(v37) = v45;
            WPP_SF_qdddd(v30, v33, v29, v9, v37, v31, v30, v27);
LABEL_41:
            if ( v31 > 0 )
            {
              WapUpdateTimerObjectOnInsert(
                (_DWORD)v9,
                v27,
                (unsigned int)WapTcpIoTimeoutRoutine,
                v3,
                (__int64)&v46,
                (__int64)&ActivityId);
              v32 = (RTL_SRWLOCK **)v28[2].Ptr;
              v4 = v41;
              if ( *v32 == &v28[1] )
              {
                *(_QWORD *)(v3 + 160) = v32;
                v9->Ptr = &v28[1];
                *v32 = v9;
                v28[2].Ptr = v9;
                ReleaseSRWLockExclusive(v28);
                if ( (BYTE1(xmmword_1800AD720) & 0x40) != 0 )
                  WPP_SF_(1038, 20, WPP_b0c89987f54c3619f65b793441fe93b4_Traceguids);
                v5 = v47;
                break;
              }
LABEL_47:
              __fastfail(3u);
            }
            ReleaseSRWLockExclusive(v28);
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  if ( (Microsoft_Windows_WebIOEnableBits & 0x100) != 0 )
  {
    v14 = *((_QWORD *)v4 + 1);
    v45 = a2;
    v44 = v4 + 16;
    v43 = *((_QWORD *)v4 + 16);
    LODWORD(v46) = 1;
    LODWORD(v47) = 0;
    *(_QWORD *)&ActivityId.Data1 = 0;
    v51 = 0;
    v50 = v5;
    v49 = *(_QWORD *)(v14 + 704);
    v42 = 0;
    v41 = *(char **)(v14 + 8);
    v53 = &v41;
    v55 = &v42;
    v57 = &v49;
    v59 = &v43;
    v61 = &v44;
    v63 = &v45;
    v65 = &v50;
    v67 = &v51;
    p_ActivityId = &ActivityId;
    v71 = &v47;
    v73 = &v46;
    v54 = 8;
    v56 = 8;
    v58 = 8;
    v60 = 8;
    v62 = 8;
    v64 = 4;
    v66 = 8;
    v68 = 8;
    v70 = 8;
    v72 = 4;
    v74 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)NetSocketSendEntityComplete,
      v13,
      0xCu,
      &v52);
  }
  v15 = v4[124] == 0;
  result = a2;
  *((_DWORD *)v4 + 26) = a2;
  *((_QWORD *)v4 + 14) = v5;
  if ( v15 )
  {
    v17 = *((_QWORD *)v4 + 12);
    v18 = (__int64 (__fastcall *)(__int64, _QWORD, __int64))*((_QWORD *)v4 + 11);
    v4[124] = 1;
    result = v18(v17, a2, v5);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 1, 0xFFFFFFFF) == 1 )
    return WapTcpFreeIoContext(v4);
  return result;
}

```

## disassembly

```asm
0x1800442f0  mov     [rsp-8+arg_10], rbx
0x1800442f5  mov     [rsp-8+arg_18], rsi
0x1800442fa  push    rbp
0x1800442fb  push    rdi
0x1800442fc  push    r12
0x1800442fe  push    r13
0x180044300  push    r15
0x180044302  lea     rbp, [rsp-80h]
0x180044307  sub     rsp, 180h
0x18004430e  mov     rax, cs:__security_cookie
0x180044315  xor     rax, rsp
0x180044318  mov     [rbp+0A0h+var_30], rax
0x18004431c  mov     r13, [rcx+8]
0x180044320  mov     rbx, rcx
0x180044323  mov     [rsp+1A0h+var_158], rcx
0x180044328  mov     r12, r8
0x18004432b  mov     [rsp+1A0h+var_128], r8
0x180044330  mov     [rsp+1A0h+var_160], edx
0x180044334  lea     rcx, [r13+18h]; lpCriticalSection
0x180044338  lea     rdi, [r13+90h]
0x18004433f  call    cs:__imp_EnterCriticalSection
0x180044346  nop     dword ptr [rax+rax+00h]
0x18004434b  dec     dword ptr [rdi+4Ch]
0x18004434e  mov     eax, [rdi+4Ch]
0x180044351  test    byte ptr cs:xmmword_1800AD720, 8
0x180044358  jnz     loc_180044787
0x18004435e  lea     rsi, [rdi+8]
0x180044362  xor     r15b, r15b
0x180044365  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18004436c  jnz     loc_180044873
0x180044372  cmp     cs:WaKirUcsanFixes25Q3, r15b
0x180044379  mov     [rsp+1A0h+arg_8], r14
0x180044381  jz      loc_180044891
0x180044387  movzx   eax, byte ptr [rsi+10h]
0x18004438b  test    al, al
0x18004438d  jnz     loc_1800447DD
0x180044393  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18004439a  jnz     loc_1800448A0
0x1800443a0  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800443a7  test    r15b, r15b
0x1800443aa  jz      short loc_1800443D2
0x1800443ac  test    byte ptr cs:xmmword_1800AD720, 8
0x1800443b3  jnz     loc_1800448BF
0x1800443b9  mov     byte ptr [rdi+48h], 0
0x1800443bd  mov     eax, r14d
0x1800443c0  mov     rcx, [r13+8]; lpMem
0x1800443c4  lock xadd [rcx+4], eax
0x1800443c9  cmp     eax, 1
0x1800443cc  jz      loc_18004475C
0x1800443d2  test    byte ptr cs:xmmword_1800AD720, 8
0x1800443d9  jnz     loc_1800448DD
0x1800443df  mov     edx, [rdi+4Ch]
0x1800443e2  xor     r15d, r15d
0x1800443e5  test    edx, edx
0x1800443e7  jnz     loc_1800445A2
0x1800443ed  lea     rcx, [r13+18h]; lpCriticalSection
0x1800443f1  call    cs:__imp_LeaveCriticalSection
0x1800443f8  nop     dword ptr [rax+rax+00h]
0x1800443fd  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 1
0x180044404  jz      loc_180044536
0x18004440a  mov     rcx, [rbx+8]
0x18004440e  lea     rdx, NetSocketSendEntityComplete
0x180044415  mov     eax, [rsp+1A0h+var_160]
0x180044419  mov     r9d, 0Ch
0x18004441f  mov     [rsp+1A0h+var_138], eax
0x180044423  lea     rax, [rbx+10h]
0x180044427  mov     [rsp+1A0h+var_140], rax
0x18004442c  mov     rax, [rbx+80h]
0x180044433  mov     [rsp+1A0h+var_148], rax
0x180044438  mov     dword ptr [rsp+1A0h+var_130], 1
0x180044440  mov     dword ptr [rsp+1A0h+var_128], r15d
0x180044445  mov     qword ptr [rbp+0A0h+ActivityId.Data1], r15
0x180044449  mov     [rbp+0A0h+var_100], r15
0x18004444d  mov     [rbp+0A0h+var_108], r12
0x180044451  mov     rax, [rcx+2C0h]
0x180044458  mov     [rbp+0A0h+var_110], rax
0x18004445c  mov     [rsp+1A0h+var_150], r15
0x180044461  mov     rax, [rcx+8]
0x180044465  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18004446c  mov     [rsp+1A0h+var_158], rax
0x180044471  lea     rax, [rsp+1A0h+var_158]
0x180044476  mov     [rbp+0A0h+var_E0], rax
0x18004447a  lea     rax, [rsp+1A0h+var_150]
0x18004447f  mov     [rbp+0A0h+var_D0], rax
0x180044483  lea     rax, [rbp+0A0h+var_110]
0x180044487  mov     [rbp+0A0h+var_C0], rax
0x18004448b  lea     rax, [rsp+1A0h+var_148]
0x180044490  mov     [rbp+0A0h+var_B0], rax
0x180044494  lea     rax, [rsp+1A0h+var_140]
0x180044499  mov     [rbp+0A0h+var_A0], rax
0x18004449d  lea     rax, [rsp+1A0h+var_138]
0x1800444a2  mov     [rbp+0A0h+var_90], rax
0x1800444a6  lea     rax, [rbp+0A0h+var_108]
0x1800444aa  mov     [rbp+0A0h+var_80], rax
0x1800444ae  lea     rax, [rbp+0A0h+var_100]
0x1800444b2  mov     [rbp+0A0h+var_70], rax
0x1800444b6  lea     rax, [rbp+0A0h+ActivityId]
0x1800444ba  mov     [rbp+0A0h+var_60], rax
0x1800444be  lea     rax, [rsp+1A0h+var_128]
0x1800444c3  mov     [rbp+0A0h+var_50], rax
0x1800444c7  lea     rax, [rsp+1A0h+var_130]
0x1800444cc  mov     [rbp+0A0h+var_40], rax
0x1800444d0  lea     rax, [rbp+0A0h+var_F0]
0x1800444d4  mov     [rsp+1A0h+var_180], rax
0x1800444d9  mov     [rbp+0A0h+var_D8], 8
0x1800444e1  mov     [rbp+0A0h+var_C8], 8
0x1800444e9  mov     [rbp+0A0h+var_B8], 8
0x1800444f1  mov     [rbp+0A0h+var_A8], 8
0x1800444f9  mov     [rbp+0A0h+var_98], 8
0x180044501  mov     [rbp+0A0h+var_88], 4
0x180044509  mov     [rbp+0A0h+var_78], 8
0x180044511  mov     [rbp+0A0h+var_68], 8
0x180044519  mov     [rbp+0A0h+var_58], 8
0x180044521  mov     [rbp+0A0h+var_48], 4
0x180044529  mov     [rbp+0A0h+var_38], 4
0x180044531  call    McGenEventWrite_EventWriteTransfer
0x180044536  cmp     byte ptr [rbx+7Ch], 0
0x18004453a  mov     eax, [rsp+1A0h+var_160]
0x18004453e  mov     [rbx+68h], eax
0x180044541  mov     [rbx+70h], r12
0x180044545  jnz     short loc_18004455D
0x180044547  mov     rcx, [rbx+60h]
0x18004454b  mov     edx, eax
0x18004454d  mov     rax, [rbx+58h]
0x180044551  mov     r8, r12
0x180044554  mov     byte ptr [rbx+7Ch], 1
0x180044558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004455d  lock xadd [rbx+4], r14d
0x180044563  cmp     r14d, 1
0x180044567  jnz     short loc_180044571
0x180044569  mov     rcx, rbx; lpMem
0x18004456c  call    WapTcpFreeIoContext
0x180044571  mov     r14, [rsp+1A0h+arg_8]
0x180044579  mov     rcx, [rbp+0A0h+var_30]
0x18004457d  xor     rcx, rsp; StackCookie
0x180044580  call    __security_check_cookie
0x180044585  lea     r11, [rsp+1A0h+var_20]
0x18004458d  mov     rbx, [r11+40h]
0x180044591  mov     rsi, [r11+48h]
0x180044595  mov     rsp, r11
0x180044598  pop     r15
0x18004459a  pop     r13
0x18004459c  pop     r12
0x18004459e  pop     rdi
0x18004459f  pop     rbp
0x1800445a0  retn
0x1800445a2  cmp     [rdi+48h], r15b
0x1800445a6  jnz     loc_1800443ED
0x1800445ac  movzx   eax, byte ptr [rdi+4]
0x1800445b0  test    al, al
0x1800445b2  jz      loc_1800443ED
0x1800445b8  mov     ecx, [rdi]
0x1800445ba  test    ecx, ecx
0x1800445bc  jz      loc_1800443ED
0x1800445c2  test    byte ptr cs:xmmword_1800AD720, 8
0x1800445c9  jnz     loc_180044908
0x1800445cf  mov     byte ptr [rdi+48h], 1
0x1800445d3  mov     rax, [r13+8]
0x1800445d7  lock inc dword ptr [rax+4]
0x1800445db  mov     eax, [rdi]
0x1800445dd  xorps   xmm0, xmm0
0x1800445e0  movups  xmmword ptr [rbp+0A0h+ActivityId.Data1], xmm0
0x1800445e4  mov     [rsp+1A0h+var_138], eax
0x1800445e8  mov     [rsp+1A0h+var_130], r14
0x1800445ed  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x1800445f4  lea     rcx, WapTcpIoTimeoutRoutine
0x1800445fb  jnz     loc_180044926
0x180044601  lea     rcx, [rsp+1A0h+var_130]
0x180044606  call    WaGetCurrentThreadToken
0x18004460b  mov     edx, 2
0x180044610  lea     rcx, [rbp+0A0h+ActivityId]; ActivityId
0x180044614  call    WaEtwControlActivityId
0x180044619  mov     ebx, [rsp+1A0h+var_138]
0x18004461d  mov     r14, 624DD2F1A9FBE77h
0x180044627  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x18004462e  jnz     loc_180044941
0x180044634  call    cs:__imp_GetTickCount64
0x18004463b  nop     dword ptr [rax+rax+00h]
0x180044640  test    ebx, ebx
0x180044642  jz      loc_180044754
0x180044648  lea     rdi, [rbx+3E7h]
0x18004464f  add     rdi, rax
0x180044652  movzx   ecx, byte ptr cs:xmmword_1800AD720+1
0x180044659  test    cl, 40h
0x18004465c  jnz     loc_18004495F
0x180044662  mov     rax, r14
0x180044665  mul     rdi
0x180044668  sub     rdi, rdx
0x18004466b  shr     rdi, 1
0x18004466e  lea     r12, [rdx+rdi]
0x180044672  shr     r12, 9
0x180044676  test    cl, 40h
0x180044679  jnz     loc_180044978
0x18004467f  mov     rax, r12
0x180044682  and     eax, 3FFh
0x180044687  lea     rcx, [rax+rax*2]
0x18004468b  mov     rax, cs:WaTimerWheel
0x180044692  lea     rcx, [rcx+1]
0x180044696  lea     rdi, [rax+rcx*8]
0x18004469a  mov     rcx, rdi; SRWLock
0x18004469d  call    cs:__imp_AcquireSRWLockExclusive
0x1800446a4  nop     dword ptr [rax+rax+00h]
0x1800446a9  cmp     cs:WaKirUcsanFixes25Q3, 0
0x1800446b0  mov     r15d, r12d
0x1800446b3  mov     rax, cs:WaTimerWheel
0x1800446ba  mov     ecx, [rax+4]
0x1800446bd  jnz     loc_18004476D
0x1800446c3  sub     r15d, ecx
0x1800446c6  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x1800446cd  jnz     loc_180044996
0x1800446d3  test    r15d, r15d
0x1800446d6  jle     loc_1800449BA
0x1800446dc  lea     rax, [rbp+0A0h+ActivityId]
0x1800446e0  mov     r9, r13
0x1800446e3  mov     [rsp+1A0h+var_178], rax
0x1800446e8  lea     r8, WapTcpIoTimeoutRoutine
0x1800446ef  lea     rax, [rsp+1A0h+var_130]
0x1800446f4  mov     edx, r12d
0x1800446f7  mov     rcx, rsi
0x1800446fa  mov     [rsp+1A0h+var_180], rax
0x1800446ff  call    WapUpdateTimerObjectOnInsert
0x180044704  mov     rcx, [rdi+10h]
0x180044708  lea     rax, [rdi+8]
0x18004470c  mov     rbx, [rsp+1A0h+var_158]
0x180044711  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180044718  cmp     [rcx], rax
0x18004471b  jnz     short loc_180044766
0x18004471d  mov     [rsi+8], rcx
0x180044721  mov     [rsi], rax
0x180044724  mov     [rcx], rsi
0x180044727  mov     rcx, rdi; SRWLock
0x18004472a  mov     [rax+8], rsi
0x18004472e  call    cs:__imp_ReleaseSRWLockExclusive
0x180044735  nop     dword ptr [rax+rax+00h]
0x18004473a  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x180044741  jnz     loc_1800449CE
0x180044747  mov     r12, [rsp+1A0h+var_128]
0x18004474c  xor     r15d, r15d
0x18004474f  jmp     loc_1800443ED
0x180044754  mov     rdi, rax
0x180044757  jmp     loc_180044652
0x18004475c  call    WaDestroyConnection
0x180044761  jmp     loc_1800443D2
0x180044766  mov     ecx, 3
0x18004476b  int     29h; Win8: RtlFailFast(ecx)
0x18004476d  sub     r15d, ecx
0x180044770  test    byte ptr cs:xmmword_1800AD720+1, 40h
0x180044777  jz      loc_1800446D3
0x18004477d  mov     edx, 12h
0x180044782  jmp     loc_18004499B
0x180044787  mov     dword ptr [rsp+1A0h+var_170], eax
0x18004478b  mov     edx, 49h ; 'I'
0x180044790  mov     dword ptr [rsp+1A0h+var_178], 1
0x180044798  mov     r9, r13
0x18004479b  mov     [rsp+1A0h+var_180], rdi
0x1800447a0  call    WPP_SF_qqlD
0x1800447a5  test    byte ptr cs:xmmword_1800AD720, 8
0x1800447ac  jz      loc_18004435E
0x1800447b2  mov     edx, 4Ah ; 'J'
0x1800447b7  mov     dword ptr [rsp+1A0h+var_178], 1
0x1800447bf  mov     ecx, 403h
0x1800447c4  mov     [rsp+1A0h+var_180], rdi
0x1800447c9  mov     r9, r13
0x1800447cc  lea     r8, WPP_14086b36644f38024399eb8d606249d9_Traceguids
0x1800447d3  call    WPP_SF_qqD
0x1800447d8  jmp     loc_18004435E
0x1800447dd  mov     eax, [rsi+14h]
0x1800447e0  and     eax, 3FFh
0x1800447e5  lea     rcx, [rax+rax*2]
0x1800447e9  mov     rax, cs:WaTimerWheel
0x1800447f0  lea     rcx, [rcx+1]
0x1800447f4  lea     r14, [rax+rcx*8]
0x1800447f8  mov     rcx, r14; SRWLock
0x1800447fb  call    cs:__imp_AcquireSRWLockExclusive
0x180044802  nop     dword ptr [rax+rax+00h]
0x180044807  cmp     [rsi+10h], r15b
0x18004480b  jz      short loc_18004485F
0x18004480d  mov     rax, [rsi]
0x180044810  cmp     [rax+8], rsi
0x180044814  jnz     loc_180044766
0x18004481a  mov     rcx, [rsi+8]
0x18004481e  cmp     [rcx], rsi
0x180044821  jnz     loc_180044766
0x180044827  cmp     cs:WaKirUcsanFixes25Q3, r15b
0x18004482e  mov     [rcx], rax
0x180044831  mov     [rax+8], rcx
0x180044835  mov     rcx, r14; SRWLock
0x180044838  mov     [rsi+8], rsi
0x18004483c  mov     [rsi], rsi
0x18004483f  mov     [rsi+10h], r15b
0x180044843  call    cs:__imp_ReleaseSRWLockExclusive
0x18004484a  nop     dword ptr [rax+rax+00h]
0x18004484f  mov     rcx, rsi
0x180044852  call    WapUpdateTimerObjectOnCancel
0x180044857  mov     r15b, 1
0x18004485a  jmp     loc_180044393
0x18004485f  mov     rcx, r14; SRWLock
0x180044862  call    cs:__imp_ReleaseSRWLockExclusive
0x180044869  nop     dword ptr [rax+rax+00h]
0x18004486e  jmp     loc_180044393
  ... truncated ...
```
