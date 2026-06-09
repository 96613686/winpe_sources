# Private::WorkItemBase::QueueTimerCallback(stdext::shared_ref<Private::WorkItemBase>,TimeSpan const *,TimeSpan const *,ComApartments::ComApartment)

- ea: `0x1400666c0`
- end: `0x14006698d`
- name: `?QueueTimerCallback@WorkItemBase@Private@@SA?AV?$shared_ptr@UITimerCallback@@@std@@V?$shared_ref@VWorkItemBase@Private@@@stdext@@PEBVTimeSpan@@1W4ComApartment@ComApartments@@@Z`
- size: `717`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002794c`
- `0x14002b8dc`
- `0x14003d77c`
- `0x14003d918`
- `0x14003ebe0`
- `0x140085c50`
- `0x140085da8`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x1400666c0`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400667af`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400667af`
- `KERNEL32!SetThreadpoolTimer` at `0x14006680b`
- `KERNEL32!SetThreadpoolTimer` at `0x14006680b`
- `KERNEL32!GetLastError` at `0x14006690b`
- `KERNEL32!GetLastError` at `0x14006690b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Private::WorkItemBase::QueueTimerCallback(_QWORD *a1, __int64 *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  volatile signed __int32 *v12; // rbx
  struct _TP_CALLBACK_ENVIRON_V3 *v13; // rdi
  __int64 v14; // r14
  _QWORD *v15; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  unsigned __int64 v17; // rdx
  char *v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rax
  PVOID v21; // rax
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rbx
  signed int LastError; // eax
  unsigned int v26; // ebx
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v28; // [rsp+40h] [rbp-30h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a3 && !a4 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *(_DWORD *)(*a2 + 28) = 0;
  v7 = a4;
  if ( a3 )
    v7 = a3;
  pftDueTime = (struct _FILETIME)-*v7;
  v8 = *a2;
  v9 = *(_QWORD *)(*a2 + 40);
  if ( v9 )
  {
    v10 = *(_DWORD *)(v9 + 8);
    while ( v10 )
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v10 + 1, v10);
      if ( v11 == v10 )
      {
        v13 = *(struct _TP_CALLBACK_ENVIRON_V3 **)(v8 + 32);
        v12 = *(volatile signed __int32 **)(v8 + 40);
        goto LABEL_10;
      }
    }
  }
  v12 = 0;
  v13 = 0;
LABEL_10:
  if ( v13 )
  {
    v14 = *a2;
    (*((void (__fastcall **)(PTP_CLEANUP_GROUP *, __int64 *))v13[1].CleanupGroup + 6))(&v13[1].CleanupGroup, &v27);
    v15 = v28;
    if ( *v28 )
    {
      *(_QWORD *)(*v28 + 80LL) = v14;
      v15 = v28;
    }
    *(_QWORD *)(v14 + 80) = 0;
    *(_QWORD *)(v14 + 88) = *v15;
    *v15 = v14;
    v13 = (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)v13 + 8);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  }
  ThreadpoolTimer = CreateThreadpoolTimer(Private::WorkItemBase::WaitCallback, (PVOID)*a2, v13);
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    v26 = LastError;
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v26);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v26);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( !a4 )
  {
    LODWORD(v17) = 0;
    goto LABEL_22;
  }
  if ( *a4 < TimeSpan::Zero || *a4 > TimeSpan::Zero )
  {
    v17 = *a4 / 0x2710uLL;
LABEL_22:
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, v17, 0);
  }
  v18 = (char *)operator new(0x30u);
  *(_OWORD *)v18 = 0;
  *((_DWORD *)v18 + 2) = 1;
  *((_DWORD *)v18 + 3) = 1;
  *(_QWORD *)v18 = &std::_Ref_count_obj2<Private::TimerCallback>::`vftable';
  v19 = v18 + 16;
  v20 = a2[1];
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  v21 = (PVOID)*a2;
  v22 = a2[1];
  *v19 = &Private::TimerCallback::`vftable';
  *((_QWORD *)v18 + 3) = v21;
  *((_QWORD *)v18 + 4) = v22;
  *((_QWORD *)v18 + 5) = ThreadpoolTimer;
  *a1 = v19;
  a1[1] = v18;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v23 = (volatile signed __int32 *)a2[1];
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400666c0  mov     [rsp-28h+arg_0], rbx
0x1400666c5  mov     [rsp-28h+arg_18], rsi
0x1400666ca  mov     [rsp-28h+arg_8], rdx
0x1400666cf  push    rbp
0x1400666d0  push    rdi
0x1400666d1  push    r12
0x1400666d3  push    r14
0x1400666d5  push    r15
0x1400666d7  mov     rbp, rsp
0x1400666da  sub     rsp, 70h
0x1400666de  mov     r15, r9
0x1400666e1  mov     rsi, rdx
0x1400666e4  mov     r12, rcx
0x1400666e7  test    r8, r8
0x1400666ea  jnz     short loc_1400666F5
0x1400666ec  test    r9, r9
0x1400666ef  jz      loc_14006696E
0x1400666f5  mov     rax, [rdx]
0x1400666f8  mov     dword ptr [rax+1Ch], 0
0x1400666ff  mov     rax, r15
0x140066702  test    r8, r8
0x140066705  cmovnz  rax, r8
0x140066709  mov     rax, [rax]
0x14006670c  neg     rax
0x14006670f  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x140066713  mov     rbx, [rdx]
0x140066716  xorps   xmm0, xmm0
0x140066719  movdqu  xmmword ptr [rbp+pcbe], xmm0
0x14006671e  mov     rdx, [rbx+28h]
0x140066722  test    rdx, rdx
0x140066725  jz      short loc_14006673E
0x140066727  mov     eax, [rdx+8]
0x14006672a  jmp     short loc_14006673A
0x14006672c  lea     ecx, [rax+1]
0x14006672f  lock cmpxchg [rdx+8], ecx
0x140066734  jz      loc_1400667E7
0x14006673a  test    eax, eax
0x14006673c  jnz     short loc_14006672C
0x14006673e  mov     rdi, [rbp+pcbe]
0x140066742  mov     rbx, [rbp+pcbe+8]
0x140066746  test    rdi, rdi
0x140066749  jz      short loc_1400667A2
0x14006674b  mov     r14, [rsi]
0x14006674e  lea     rcx, [rdi+58h]
0x140066752  mov     rax, [rcx]
0x140066755  lea     rdx, [rbp+var_38]
0x140066759  mov     rax, [rax+30h]
0x14006675d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066762  mov     rcx, [rbp+var_30]
0x140066766  mov     rax, [rcx]
0x140066769  test    rax, rax
0x14006676c  jz      short loc_140066776
0x14006676e  mov     [rax+50h], r14
0x140066772  mov     rcx, [rbp+var_30]
0x140066776  mov     qword ptr [r14+50h], 0
0x14006677e  mov     rax, [rcx]
0x140066781  mov     [r14+58h], rax
0x140066785  mov     [rcx], r14
0x140066788  add     rdi, 8
0x14006678c  mov     rcx, [rbp+var_38]
0x140066790  test    rcx, rcx
0x140066793  jz      short loc_1400667A2
0x140066795  mov     rax, [rcx]
0x140066798  mov     rax, [rax+18h]
0x14006679c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400667a1  nop
0x1400667a2  mov     r8, rdi; pcbe
0x1400667a5  mov     rdx, [rsi]; pv
0x1400667a8  lea     rcx, ?WaitCallback@WorkItemBase@Private@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnti
0x1400667af  call    cs:__imp_CreateThreadpoolTimer
0x1400667b5  mov     rdi, rax
0x1400667b8  test    rax, rax
0x1400667bb  jz      loc_14006690B
0x1400667c1  test    r15, r15
0x1400667c4  jz      short loc_1400667FC
0x1400667c6  mov     rax, cs:?Zero@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Zero
0x1400667cd  cmp     [r15], rax
0x1400667d0  jb      short loc_1400667D4
0x1400667d2  jbe     short loc_140066811
0x1400667d4  mov     rax, 346DC5D63886594Bh
0x1400667de  mul     qword ptr [r15]
0x1400667e1  shr     rdx, 0Bh
0x1400667e5  jmp     short loc_1400667FE
0x1400667e7  mov     rdi, [rbx+20h]
0x1400667eb  mov     [rbp+pcbe], rdi
0x1400667ef  mov     rbx, [rbx+28h]
0x1400667f3  mov     [rbp+pcbe+8], rbx
0x1400667f7  jmp     loc_140066746
0x1400667fc  xor     edx, edx
0x1400667fe  xor     r9d, r9d; msWindowLength
0x140066801  mov     r8d, edx; msPeriod
0x140066804  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x140066808  mov     rcx, rdi; pti
0x14006680b  call    cs:__imp_SetThreadpoolTimer
0x140066811  mov     ecx, 30h ; '0'; Size
0x140066816  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006681b  mov     rdx, rax
0x14006681e  mov     [rbp+pcbe], rax
0x140066822  xorps   xmm0, xmm0
0x140066825  movups  xmmword ptr [rax], xmm0
0x140066828  mov     dword ptr [rax+8], 1
0x14006682f  mov     dword ptr [rax+0Ch], 1
0x140066836  lea     rax, ??_7?$_Ref_count_obj2@VTimerCallback@Private@@@std@@6B@; const std::_Ref_count_obj2<Private::TimerCallback>::`vftable'
0x14006683d  mov     [rdx], rax
0x140066840  lea     r8, [rdx+10h]
0x140066844  mov     rax, [rsi+8]
0x140066848  test    rax, rax
0x14006684b  jz      short loc_140066851
0x14006684d  lock inc dword ptr [rax+8]
0x140066851  mov     rax, [rsi]
0x140066854  mov     rcx, [rsi+8]
0x140066858  lea     r9, ??_7TimerCallback@Private@@6B@; const Private::TimerCallback::`vftable'
0x14006685f  mov     [r8], r9
0x140066862  mov     [r8+8], rax
0x140066866  mov     [r8+10h], rcx
0x14006686a  mov     [r8+18h], rdi
0x14006686e  mov     [r12], r8
0x140066872  mov     [r12+8], rdx
0x140066877  or      edi, 0FFFFFFFFh
0x14006687a  test    rbx, rbx
0x14006687d  jz      short loc_1400668B3
0x14006687f  mov     eax, edi
0x140066881  lock xadd [rbx+8], eax
0x140066886  add     eax, edi
0x140066888  jnz     short loc_1400668B3
0x14006688a  mov     rax, [rbx]
0x14006688d  mov     rcx, rbx
0x140066890  mov     rax, [rax]
0x140066893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066898  mov     eax, edi
0x14006689a  lock xadd [rbx+0Ch], eax
0x14006689f  add     eax, edi
0x1400668a1  jnz     short loc_1400668B3
0x1400668a3  mov     rax, [rbx]
0x1400668a6  mov     rcx, rbx
0x1400668a9  mov     rax, [rax+8]
0x1400668ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400668b2  nop
0x1400668b3  mov     rbx, [rsi+8]
0x1400668b7  test    rbx, rbx
0x1400668ba  jz      short loc_1400668EF
0x1400668bc  mov     eax, edi
0x1400668be  lock xadd [rbx+8], eax
0x1400668c3  add     eax, edi
0x1400668c5  jnz     short loc_1400668EF
0x1400668c7  mov     rax, [rbx]
0x1400668ca  mov     rcx, rbx
0x1400668cd  mov     rax, [rax]
0x1400668d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400668d5  mov     eax, edi
0x1400668d7  lock xadd [rbx+0Ch], eax
0x1400668dc  add     eax, edi
0x1400668de  jnz     short loc_1400668EF
0x1400668e0  mov     rax, [rbx]
0x1400668e3  mov     rcx, rbx
0x1400668e6  mov     rax, [rax+8]
0x1400668ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400668ef  mov     rax, r12
0x1400668f2  lea     r11, [rsp+70h+var_s0]
0x1400668f7  mov     rbx, [r11+30h]
0x1400668fb  mov     rsi, [r11+48h]
0x1400668ff  mov     rsp, r11
0x140066902  pop     r15
0x140066904  pop     r14
0x140066906  pop     r12
0x140066908  pop     rdi
0x140066909  pop     rbp
0x14006690a  retn
0x14006690b  call    cs:__imp_GetLastError
0x140066911  nop
0x140066912  mov     ebx, eax
0x140066914  test    eax, eax
0x140066916  jle     short loc_140066921
0x140066918  movzx   ebx, ax
0x14006691b  or      ebx, 80070000h
0x140066921  lea     rax, WPP_GLOBAL_Control
0x140066928  mov     rcx, cs:WPP_GLOBAL_Control
0x14006692f  cmp     rcx, rax
0x140066932  jz      short loc_140066952
0x140066934  test    byte ptr [rcx+1Ch], 1
0x140066938  jz      short loc_140066952
0x14006693a  mov     edx, 0Dh
0x14006693f  mov     r9d, ebx
0x140066942  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x140066949  mov     rcx, [rcx+10h]
0x14006694d  call    WPP_SF_d
0x140066952  mov     edx, ebx; int
0x140066954  lea     rcx, [rbp+pExceptionObject]; this
0x140066958  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14006695d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140066964  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140066968  call    _CxxThrowException_0
0x14006696e  mov     edx, 8000FFFFh; int
0x140066973  lea     rcx, [rbp+pExceptionObject]; this
0x140066977  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14006697c  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140066983  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140066987  call    _CxxThrowException_0
```
