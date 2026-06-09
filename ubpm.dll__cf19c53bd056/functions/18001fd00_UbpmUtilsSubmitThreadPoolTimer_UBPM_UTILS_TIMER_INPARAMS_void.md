# UbpmUtilsSubmitThreadPoolTimer(_UBPM_UTILS_TIMER_INPARAMS *,void * *)

- ea: `0x18001fd00`
- end: `0x18002013c`
- name: `?UbpmUtilsSubmitThreadPoolTimer@@YAKPEAU_UBPM_UTILS_TIMER_INPARAMS@@PEAPEAX@Z`
- size: `1084`
- prototype: `unsigned int __fastcall(struct _UBPM_UTILS_TIMER_INPARAMS *, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017e88`
- `0x18001eb04`
- `0x18001fa6c`
- `0x18001fbf8`

## callees

- `0x18000f9a0`
- `0x18001fd00`
- `0x180032e38`
- `0x18003d7d2`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001fe93`
- `ntdll!RtlFreeHeap` at `0x18001fe93`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18001fdd1`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18001fdd1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ff81`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ff81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fe6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fe6b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001fdf8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001fdf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ff90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ffc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ff90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ffc1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002006d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002006d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180020028`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180020028`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolTimer(struct _UBPM_UTILS_TIMER_INPARAMS *a1, PTP_TIMER *a2)
{
  char v2; // r14
  struct _FILETIME *v5; // rax
  struct _FILETIME v6; // rax
  unsigned __int64 v7; // rdx
  _DWORD *v8; // rdi
  __int64 v9; // r15
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // r14
  void *v11; // rsi
  char v12; // r12
  PTP_TIMER ThreadpoolTimer; // r14
  char v14; // cl
  struct _FILETIME *p_SystemTimeAsFileTime; // rdx
  DWORD LastError; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD dwLowDateTime; // ecx
  FILETIME FileTime1; // [rsp+70h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+48h] BYREF
  struct _FILETIME FileTime; // [rsp+88h] [rbp+50h] BYREF

  SystemTimeAsFileTime = 0;
  v2 = 0;
  FileTime1 = 0;
  FileTime = 0;
  v5 = (struct _FILETIME *)*((_QWORD *)a1 + 7);
  if ( v5 )
  {
    v6 = *v5;
    SystemTimeAsFileTime = v6;
  }
  else
  {
    if ( *((_BYTE *)a1 + 36) )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v6 = (struct _FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 10000000 * (*((unsigned int *)a1 + 8) + 1LL));
    }
    else
    {
      v2 = 1;
      v6 = (struct _FILETIME)(-10000000LL * *((unsigned int *)a1 + 8));
    }
    SystemTimeAsFileTime = v6;
  }
  v7 = *(_QWORD *)((char *)a1 + 68);
  if ( !v7 )
    v7 = *(_QWORD *)((char *)a1 + 76) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v7 )
  {
    if ( v2 )
    {
      GetSystemTimeAsFileTime(&FileTime1);
      dwLowDateTime = FileTime1.dwLowDateTime + 10000000 * *((_DWORD *)a1 + 8);
      *(_QWORD *)&FileTime1 += 10000000LL * *((unsigned int *)a1 + 8);
      v6 = FileTime1;
    }
    else
    {
      FileTime1 = v6;
      dwLowDateTime = v6.dwLowDateTime;
    }
    FileTime1 = (FILETIME)((dwLowDateTime | *(_QWORD *)&v6 & 0xFFFFFFFF00000000uLL) - 10000000);
    if ( SystemTimeToFileTime((const SYSTEMTIME *)((char *)a1 + 68), &FileTime) )
    {
      if ( CompareFileTime(&FileTime1, &FileTime) <= 0 )
        goto LABEL_8;
      LastError = 4320;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v19 = 24;
    }
    else
    {
      LastError = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v19 = 23;
    }
LABEL_36:
    WPP_SF_d(v18[2], v19, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
    return LastError;
  }
LABEL_8:
  v8 = UbpmAlloc((unsigned int)*((unsigned __int16 *)a1 + 12) + 48);
  if ( !v8 )
  {
    LastError = GetLastError();
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v19 = 25;
    goto LABEL_36;
  }
  v9 = *((_QWORD *)a1 + 6);
  if ( v9 )
  {
    v11 = (void *)*((_QWORD *)a1 + 11);
    v12 = 0;
    v10 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)a1 + 6);
    if ( !v11 )
      goto LABEL_14;
  }
  else
  {
    v10 = &g_CallbackEnv;
    v11 = &g_TpSubmitLock;
  }
  if ( !(unsigned __int8)RtlTryAcquireSRWLockShared(v11) )
  {
    LastError = 1235;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1235);
    goto LABEL_25;
  }
  if ( !v9 && !g_pThreadpool )
  {
    LastError = 1115;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1115);
LABEL_39:
    RtlReleaseSRWLockShared(v11);
    goto LABEL_24;
  }
  v12 = 1;
LABEL_14:
  ThreadpoolTimer = CreateThreadpoolTimer(UbpmUtilsTimerCallback, v8, v10);
  if ( ThreadpoolTimer )
  {
    v14 = *((_BYTE *)v8 + 24);
    *v8 = 1886667349;
    *((_QWORD *)v8 + 1) = *((_QWORD *)a1 + 1);
    *((_QWORD *)v8 + 2) = *(_QWORD *)a1;
    *((_BYTE *)v8 + 24) ^= (*((_BYTE *)a1 + 28) ^ v14) & 1;
    if ( *((_WORD *)a1 + 12) )
    {
      *((_QWORD *)v8 + 4) = v8 + 12;
      memcpy_0(v8 + 12, *((const void **)a1 + 2), *((unsigned __int16 *)a1 + 12));
    }
    if ( a2 )
    {
      if ( (*((_BYTE *)a1 + 96) & 1) != 0 )
      {
        *a2 = ThreadpoolTimer;
      }
      else
      {
        *a2 = (PTP_TIMER)v8;
        *((_BYTE *)v8 + 24) |= 2u;
        *((_QWORD *)v8 + 5) = ThreadpoolTimer;
      }
    }
    p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
    v8 = 0;
    if ( *((_DWORD *)a1 + 16) )
      p_SystemTimeAsFileTime = 0;
    SetThreadpoolTimer(ThreadpoolTimer, p_SystemTimeAsFileTime, *((_DWORD *)a1 + 10), 0);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
  }
  if ( v12 )
    goto LABEL_39;
LABEL_24:
  if ( v8 )
LABEL_25:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return LastError;
}

```

## disassembly

```asm
0x18001fd00  push    rbp
0x18001fd02  push    rbx
0x18001fd03  push    rsi
0x18001fd04  push    rdi
0x18001fd05  push    r13
0x18001fd07  push    r14
0x18001fd09  mov     rbp, rsp
0x18001fd0c  sub     rsp, 38h
0x18001fd10  xor     eax, eax
0x18001fd12  movaps  [rsp+38h+var_18], xmm6
0x18001fd17  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001fd1b  xor     r14b, r14b
0x18001fd1e  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18001fd22  mov     r13, rdx
0x18001fd25  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18001fd29  mov     rbx, rcx
0x18001fd2c  mov     rax, [rcx+38h]
0x18001fd30  xorps   xmm6, xmm6
0x18001fd33  test    rax, rax
0x18001fd36  jnz     loc_18001FEEA
0x18001fd3c  cmp     [rcx+24h], r14b
0x18001fd40  jnz     loc_18001FF8C
0x18001fd46  mov     eax, [rcx+20h]
0x18001fd49  mov     r14b, 1
0x18001fd4c  imul    rax, 0FFFFFFFFFF676980h
0x18001fd53  mov     rcx, rax
0x18001fd56  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x18001fd59  shr     rcx, 20h
0x18001fd5d  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18001fd60  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001fd64  mov     rdx, [rbx+44h]
0x18001fd68  movq    rcx, xmm6
0x18001fd6d  sub     rdx, rcx
0x18001fd70  jnz     short loc_18001FD83
0x18001fd72  mov     rdx, [rbx+4Ch]
0x18001fd76  psrldq  xmm6, 8
0x18001fd7b  movq    rcx, xmm6
0x18001fd80  sub     rdx, rcx
0x18001fd83  movaps  xmm6, [rsp+38h+var_18]
0x18001fd88  test    rdx, rdx
0x18001fd8b  jnz     loc_18001FFB8
0x18001fd91  movzx   ecx, word ptr [rbx+18h]
0x18001fd95  add     ecx, 30h ; '0'; Size
0x18001fd98  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001fd9d  mov     rdi, rax
0x18001fda0  test    rax, rax
0x18001fda3  jz      loc_18001FF0E
0x18001fda9  mov     [rsp+38h+arg_8], r12
0x18001fdae  mov     [rsp+38h+var_8], r15
0x18001fdb3  mov     r15, [rbx+30h]
0x18001fdb7  test    r15, r15
0x18001fdba  jnz     loc_18001FEF6
0x18001fdc0  lea     r14, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv
0x18001fdc7  lea     rsi, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x18001fdce  mov     rcx, rsi
0x18001fdd1  call    cs:__imp_RtlTryAcquireSRWLockShared
0x18001fdd7  test    al, al
0x18001fdd9  jz      loc_18001FEB2
0x18001fddf  test    r15, r15
0x18001fde2  jz      loc_18001FF54
0x18001fde8  mov     r12b, 1
0x18001fdeb  mov     r8, r14; pcbe
0x18001fdee  lea     rcx, ?UbpmUtilsTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001fdf5  mov     rdx, rdi; pv
0x18001fdf8  call    cs:__imp_CreateThreadpoolTimer
0x18001fdfe  mov     r14, rax
0x18001fe01  test    rax, rax
0x18001fe04  jz      loc_1800200D2
0x18001fe0a  movzx   ecx, byte ptr [rdi+18h]
0x18001fe0e  mov     dword ptr [rdi], 70744255h
0x18001fe14  mov     rax, [rbx+8]
0x18001fe18  mov     [rdi+8], rax
0x18001fe1c  mov     rax, [rbx]
0x18001fe1f  mov     [rdi+10h], rax
0x18001fe23  xor     cl, [rbx+1Ch]
0x18001fe26  and     cl, 1
0x18001fe29  xor     [rdi+18h], cl
0x18001fe2c  cmp     word ptr [rbx+18h], 0
0x18001fe31  ja      loc_180020118
0x18001fe37  test    r13, r13
0x18001fe3a  jz      short loc_18001FE52
0x18001fe3c  test    byte ptr [rbx+60h], 1
0x18001fe40  jnz     loc_180020133
0x18001fe46  mov     [r13+0], rdi
0x18001fe4a  or      byte ptr [rdi+18h], 2
0x18001fe4e  mov     [rdi+28h], r14
0x18001fe52  mov     r8d, [rbx+28h]; msPeriod
0x18001fe56  lea     rdx, [rbp+SystemTimeAsFileTime]
0x18001fe5a  xor     eax, eax
0x18001fe5c  xor     edi, edi
0x18001fe5e  cmp     [rbx+40h], eax
0x18001fe61  mov     rcx, r14; pti
0x18001fe64  cmovnz  rdx, rax; pftDueTime
0x18001fe68  xor     r9d, r9d; msWindowLength
0x18001fe6b  call    cs:__imp_SetThreadpoolTimer
0x18001fe71  xor     ebx, ebx
0x18001fe73  test    r12b, r12b
0x18001fe76  jnz     loc_18001FF7E
0x18001fe7c  test    rdi, rdi
0x18001fe7f  jz      short loc_18001FE99
0x18001fe81  mov     rcx, gs:60h
0x18001fe8a  mov     r8, rdi; P
0x18001fe8d  xor     edx, edx; Flags
0x18001fe8f  mov     rcx, [rcx+30h]; HeapHandle
0x18001fe93  call    cs:__imp_RtlFreeHeap
0x18001fe99  mov     r12, [rsp+38h+arg_8]
0x18001fe9e  mov     r15, [rsp+38h+var_8]
0x18001fea3  mov     eax, ebx
0x18001fea5  add     rsp, 38h
0x18001fea9  pop     r14
0x18001feab  pop     r13
0x18001fead  pop     rdi
0x18001feae  pop     rsi
0x18001feaf  pop     rbx
0x18001feb0  pop     rbp
0x18001feb1  retn
0x18001feb2  mov     ebx, 4D3h
0x18001feb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001febe  lea     rax, WPP_GLOBAL_Control
0x18001fec5  cmp     rcx, rax
0x18001fec8  jz      short loc_18001FE81
0x18001feca  test    byte ptr [rcx+1Ch], 1
0x18001fece  jz      short loc_18001FE81
0x18001fed0  mov     rcx, [rcx+10h]
0x18001fed4  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001fedb  mov     edx, 1Ah
0x18001fee0  mov     r9d, ebx
0x18001fee3  call    WPP_SF_d
0x18001fee8  jmp     short loc_18001FE81
0x18001feea  mov     rax, [rax]
0x18001feed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001fef1  jmp     loc_18001FD64
0x18001fef6  mov     rsi, [rbx+58h]
0x18001fefa  xor     r12b, r12b
0x18001fefd  mov     r14, r15
0x18001ff00  test    rsi, rsi
0x18001ff03  jnz     loc_18001FDCE
0x18001ff09  jmp     loc_18001FDEB
0x18001ff0e  call    cs:__imp_GetLastError
0x18001ff14  mov     ebx, eax
0x18001ff16  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff1d  lea     rax, WPP_GLOBAL_Control
0x18001ff24  cmp     rcx, rax
0x18001ff27  jz      loc_18001FEA3
0x18001ff2d  test    byte ptr [rcx+1Ch], 1
0x18001ff31  jz      loc_18001FEA3
0x18001ff37  mov     edx, 19h
0x18001ff3c  mov     rcx, [rcx+10h]
0x18001ff40  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001ff47  mov     r9d, ebx
0x18001ff4a  call    WPP_SF_d
0x18001ff4f  jmp     loc_18001FEA3
0x18001ff54  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x18001ff5c  jnz     loc_18001FDE8
0x18001ff62  mov     ebx, 45Bh
0x18001ff67  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff6e  lea     rax, WPP_GLOBAL_Control
0x18001ff75  cmp     rcx, rax
0x18001ff78  jnz     loc_1800200AB
0x18001ff7e  mov     rcx, rsi
0x18001ff81  call    cs:__imp_RtlReleaseSRWLockShared
0x18001ff87  jmp     loc_18001FE7C
0x18001ff8c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ff90  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ff96  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ff99  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18001ff9c  shl     rcx, 20h
0x18001ffa0  or      rcx, rax
0x18001ffa3  mov     eax, [rbx+20h]
0x18001ffa6  inc     rax
0x18001ffa9  imul    rax, 989680h
0x18001ffb0  add     rax, rcx
0x18001ffb3  jmp     loc_18001FD53
0x18001ffb8  test    r14b, r14b
0x18001ffbb  jz      short loc_18001FFF4
0x18001ffbd  lea     rcx, [rbp+FileTime1]; lpSystemTimeAsFileTime
0x18001ffc1  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ffc7  mov     eax, [rbp+FileTime1.dwLowDateTime]
0x18001ffca  mov     edx, [rbp+FileTime1.dwHighDateTime]
0x18001ffcd  shl     rdx, 20h
0x18001ffd1  or      rdx, rax
0x18001ffd4  mov     eax, [rbx+20h]
0x18001ffd7  imul    rcx, rax, 989680h
0x18001ffde  add     rcx, rdx
0x18001ffe1  mov     rax, rcx
0x18001ffe4  mov     [rbp+FileTime1.dwLowDateTime], ecx
0x18001ffe7  shr     rax, 20h
0x18001ffeb  mov     [rbp+FileTime1.dwHighDateTime], eax
0x18001ffee  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18001fff2  jmp     short loc_18001FFFB
0x18001fff4  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18001fff8  mov     ecx, [rbp+FileTime1.dwLowDateTime]
0x18001fffb  mov     rdx, 0FFFFFFFF00000000h
0x180020005  and     rax, rdx
0x180020008  mov     edx, ecx
0x18002000a  or      rax, rdx
0x18002000d  lea     rcx, [rbx+44h]; lpSystemTime
0x180020011  add     rax, 0FFFFFFFFFF676980h
0x180020017  mov     rdx, rax
0x18002001a  mov     [rbp+FileTime1.dwLowDateTime], eax
0x18002001d  shr     rdx, 20h
0x180020021  mov     [rbp+FileTime1.dwHighDateTime], edx
0x180020024  lea     rdx, [rbp+FileTime]; lpFileTime
0x180020028  call    cs:__imp_SystemTimeToFileTime
0x18002002e  test    eax, eax
0x180020030  jnz     short loc_180020065
0x180020032  call    cs:__imp_GetLastError
0x180020038  mov     ebx, eax
0x18002003a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020041  lea     rax, WPP_GLOBAL_Control
0x180020048  cmp     rcx, rax
0x18002004b  jz      loc_18001FEA3
0x180020051  test    byte ptr [rcx+1Ch], 1
0x180020055  jz      loc_18001FEA3
0x18002005b  mov     edx, 17h
0x180020060  jmp     loc_18001FF3C
0x180020065  lea     rdx, [rbp+FileTime]; lpFileTime2
0x180020069  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002006d  call    cs:__imp_CompareFileTime
0x180020073  test    eax, eax
0x180020075  jle     loc_18001FD91
0x18002007b  mov     ebx, 10E0h
0x180020080  mov     rcx, cs:WPP_GLOBAL_Control
0x180020087  lea     rax, WPP_GLOBAL_Control
0x18002008e  cmp     rcx, rax
0x180020091  jz      loc_18001FEA3
0x180020097  test    byte ptr [rcx+1Ch], 1
0x18002009b  jz      loc_18001FEA3
0x1800200a1  mov     edx, 18h
0x1800200a6  jmp     loc_18001FF3C
0x1800200ab  test    byte ptr [rcx+1Ch], 1
0x1800200af  jz      loc_18001FF7E
0x1800200b5  mov     rcx, [rcx+10h]
0x1800200b9  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x1800200c0  mov     edx, 1Bh
0x1800200c5  mov     r9d, ebx
0x1800200c8  call    WPP_SF_d
0x1800200cd  jmp     loc_18001FF7E
0x1800200d2  call    cs:__imp_GetLastError
0x1800200d8  mov     ebx, eax
0x1800200da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200e1  lea     rax, WPP_GLOBAL_Control
0x1800200e8  cmp     rcx, rax
0x1800200eb  jz      loc_18001FE73
0x1800200f1  test    byte ptr [rcx+1Ch], 1
0x1800200f5  jz      loc_18001FE73
0x1800200fb  mov     rcx, [rcx+10h]
0x1800200ff  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180020106  mov     edx, 1Ch
0x18002010b  mov     r9d, ebx
0x18002010e  call    WPP_SF_d
0x180020113  jmp     loc_18001FE73
0x180020118  lea     rcx, [rdi+30h]; void *
0x18002011c  mov     [rdi+20h], rcx
0x180020120  movzx   r8d, word ptr [rbx+18h]; Size
0x180020125  mov     rdx, [rbx+10h]; Src
0x180020129  call    memcpy_0
0x18002012e  jmp     loc_18001FE37
0x180020133  mov     [r13+0], r14
0x180020137  jmp     loc_18001FE52
```
