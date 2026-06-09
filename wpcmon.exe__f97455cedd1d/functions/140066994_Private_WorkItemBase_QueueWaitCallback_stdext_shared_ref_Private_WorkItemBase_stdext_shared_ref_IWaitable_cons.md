# Private::WorkItemBase::QueueWaitCallback(stdext::shared_ref<Private::WorkItemBase>,stdext::shared_ref<IWaitable const> const &,Optional<TimeSpan> const &,ComApartments::ComApartment)

- ea: `0x140066994`
- end: `0x140066c3c`
- name: `?QueueWaitCallback@WorkItemBase@Private@@SA?AV?$shared_ptr@VWaitCallback@Private@@@std@@V?$shared_ref@VWorkItemBase@Private@@@stdext@@AEBV?$shared_ref@$$CBUIWaitable@@@6@AEBV?$Optional@VTimeSpan@@@@W4ComApartment@ComApartments@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020f3c`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14001f6b4`
- `0x140060f58`
- `0x140066994`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x140066ab4`
- `KERNEL32!SetThreadpoolWait` at `0x140066ab4`
- `KERNEL32!CreateThreadpoolWait` at `0x140066a89`
- `KERNEL32!CreateThreadpoolWait` at `0x140066a89`
- `KERNEL32!GetLastError` at `0x140066bda`
- `KERNEL32!GetLastError` at `0x140066bda`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *Private::WorkItemBase::QueueWaitCallback(_QWORD *a1, __int64 *a2, _QWORD *a3, ...)
{
  struct _FILETIME *v6; // r13
  __int64 v7; // rbx
  __int64 v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  volatile signed __int32 *v11; // rbx
  struct _TP_CALLBACK_ENVIRON_V3 *v12; // rsi
  __int64 v13; // r14
  _QWORD *v14; // rcx
  struct _TP_WAIT *ThreadpoolWait; // rsi
  void *v16; // rax
  char *v17; // r8
  _QWORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // r10
  __int64 v22; // rax
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rbx
  signed int LastError; // eax
  unsigned int v27; // ebx
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v29; // [rsp+40h] [rbp-30h]
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+58h] BYREF
  va_list va; // [rsp+C8h] [rbp+58h]
  va_list va1; // [rsp+D0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v31 = va_arg(va1, _QWORD);
  *(_DWORD *)(*a2 + 28) = 0;
  v31 = 0;
  v6 = 0;
  if ( qword_140110030 )
  {
    v31 = -*(_QWORD *)qword_140110030;
    va_copy((va_list)v6, va);
  }
  v7 = *a2;
  v8 = *(_QWORD *)(*a2 + 40);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 8);
    while ( v9 )
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
      if ( v10 == v9 )
      {
        v12 = *(struct _TP_CALLBACK_ENVIRON_V3 **)(v7 + 32);
        v11 = *(volatile signed __int32 **)(v7 + 40);
        goto LABEL_8;
      }
    }
  }
  v11 = 0;
  v12 = 0;
LABEL_8:
  if ( v12 )
  {
    v13 = *a2;
    (*((void (__fastcall **)(PTP_CLEANUP_GROUP *, __int64 *))v12[1].CleanupGroup + 6))(&v12[1].CleanupGroup, &v28);
    v14 = v29;
    if ( *v29 )
    {
      *(_QWORD *)(*v29 + 80LL) = v13;
      v14 = v29;
    }
    *(_QWORD *)(v13 + 80) = 0;
    *(_QWORD *)(v13 + 88) = *v14;
    *v14 = v13;
    v12 = (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)v12 + 8);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
  }
  ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)Private::WorkItemBase::WaitCallback, (PVOID)*a2, v12);
  if ( !ThreadpoolWait )
  {
    LastError = GetLastError();
    v27 = LastError;
    if ( LastError > 0 )
      v27 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids, v27);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v27);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v16 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  SetThreadpoolWait(ThreadpoolWait, v16, v6);
  v17 = (char *)operator new(0x38u);
  *(_OWORD *)v17 = 0;
  *((_DWORD *)v17 + 2) = 1;
  *((_DWORD *)v17 + 3) = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<Private::WaitCallback>::`vftable';
  v18 = v17 + 16;
  v19 = a3[1];
  if ( v19 )
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
  v20 = *a3;
  v21 = a3[1];
  v22 = a2[1];
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
  v23 = a2[1];
  *v18 = *a2;
  *((_QWORD *)v17 + 3) = v23;
  *((_QWORD *)v17 + 4) = v20;
  *((_QWORD *)v17 + 5) = v21;
  *((_QWORD *)v17 + 6) = ThreadpoolWait;
  *a1 = v18;
  a1[1] = v17;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v24 = (volatile signed __int32 *)a2[1];
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140066994  mov     [rsp-38h+arg_0], rbx
0x140066999  mov     [rsp-38h+arg_18], r9
0x14006699e  mov     [rsp-38h+arg_8], rdx
0x1400669a3  push    rbp
0x1400669a4  push    rsi
0x1400669a5  push    rdi
0x1400669a6  push    r12
0x1400669a8  push    r13
0x1400669aa  push    r14
0x1400669ac  push    r15
0x1400669ae  mov     rbp, rsp
0x1400669b1  sub     rsp, 70h
0x1400669b5  mov     r12, r8
0x1400669b8  mov     rdi, rdx
0x1400669bb  mov     r15, rcx
0x1400669be  mov     rax, [rdx]
0x1400669c1  mov     dword ptr [rax+1Ch], 0
0x1400669c8  mov     [rbp+arg_18], 0
0x1400669d0  xor     r13d, r13d
0x1400669d3  mov     rax, cs:qword_140110030
0x1400669da  test    rax, rax
0x1400669dd  jz      short loc_1400669ED
0x1400669df  mov     rax, [rax]
0x1400669e2  neg     rax
0x1400669e5  mov     [rbp+arg_18], rax
0x1400669e9  lea     r13, [rbp+arg_18]
0x1400669ed  mov     rbx, [rdx]
0x1400669f0  xorps   xmm0, xmm0
0x1400669f3  movdqu  xmmword ptr [rbp+pcbe], xmm0
0x1400669f8  mov     rdx, [rbx+28h]
0x1400669fc  test    rdx, rdx
0x1400669ff  jz      short loc_140066A18
0x140066a01  mov     eax, [rdx+8]
0x140066a04  jmp     short loc_140066A14
0x140066a06  lea     ecx, [rax+1]
0x140066a09  lock cmpxchg [rdx+8], ecx
0x140066a0e  jz      loc_140066BC5
0x140066a14  test    eax, eax
0x140066a16  jnz     short loc_140066A06
0x140066a18  mov     rsi, [rbp+pcbe]
0x140066a1c  mov     rbx, [rbp+pcbe+8]
0x140066a20  test    rsi, rsi
0x140066a23  jz      short loc_140066A7C
0x140066a25  mov     r14, [rdi]
0x140066a28  lea     rcx, [rsi+58h]
0x140066a2c  mov     rax, [rcx]
0x140066a2f  lea     rdx, [rbp+var_38]
0x140066a33  mov     rax, [rax+30h]
0x140066a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066a3c  mov     rcx, [rbp+var_30]
0x140066a40  mov     rax, [rcx]
0x140066a43  test    rax, rax
0x140066a46  jz      short loc_140066A50
0x140066a48  mov     [rax+50h], r14
0x140066a4c  mov     rcx, [rbp+var_30]
0x140066a50  mov     qword ptr [r14+50h], 0
0x140066a58  mov     rax, [rcx]
0x140066a5b  mov     [r14+58h], rax
0x140066a5f  mov     [rcx], r14
0x140066a62  add     rsi, 8
0x140066a66  mov     rcx, [rbp+var_38]
0x140066a6a  test    rcx, rcx
0x140066a6d  jz      short loc_140066A7C
0x140066a6f  mov     rax, [rcx]
0x140066a72  mov     rax, [rax+18h]
0x140066a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066a7b  nop
0x140066a7c  mov     r8, rsi; pcbe
0x140066a7f  mov     rdx, [rdi]; pv
0x140066a82  lea     rcx, ?WaitCallback@WorkItemBase@Private@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140066a89  call    cs:__imp_CreateThreadpoolWait
0x140066a8f  mov     rsi, rax
0x140066a92  test    rax, rax
0x140066a95  jz      loc_140066BDA
0x140066a9b  mov     rcx, [r12]
0x140066a9f  mov     rax, [rcx]
0x140066aa2  mov     rax, [rax+8]
0x140066aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066aab  mov     r8, r13; pftTimeout
0x140066aae  mov     rdx, rax; h
0x140066ab1  mov     rcx, rsi; pwa
0x140066ab4  call    cs:__imp_SetThreadpoolWait
0x140066aba  mov     ecx, 38h ; '8'; Size
0x140066abf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140066ac4  mov     r8, rax
0x140066ac7  mov     [rbp+arg_8], rax
0x140066acb  xorps   xmm0, xmm0
0x140066ace  movups  xmmword ptr [rax], xmm0
0x140066ad1  mov     dword ptr [rax+8], 1
0x140066ad8  mov     dword ptr [rax+0Ch], 1
0x140066adf  lea     rax, ??_7?$_Ref_count_obj2@VWaitCallback@Private@@@std@@6B@; const std::_Ref_count_obj2<Private::WaitCallback>::`vftable'
0x140066ae6  mov     [r8], rax
0x140066ae9  lea     rdx, [r8+10h]
0x140066aed  mov     rcx, [r12+8]
0x140066af2  test    rcx, rcx
0x140066af5  jz      short loc_140066AFB
0x140066af7  lock inc dword ptr [rcx+8]
0x140066afb  mov     r9, [r12]
0x140066aff  mov     r10, [r12+8]
0x140066b04  mov     rax, [rdi+8]
0x140066b08  test    rax, rax
0x140066b0b  jz      short loc_140066B11
0x140066b0d  lock inc dword ptr [rax+8]
0x140066b11  mov     rcx, [rdi+8]
0x140066b15  mov     rax, [rdi]
0x140066b18  mov     [rdx], rax
0x140066b1b  mov     [rdx+8], rcx
0x140066b1f  mov     [rdx+10h], r9
0x140066b23  mov     [rdx+18h], r10
0x140066b27  mov     [rdx+20h], rsi
0x140066b2b  mov     [r15], rdx
0x140066b2e  mov     [r15+8], r8
0x140066b32  or      esi, 0FFFFFFFFh
0x140066b35  test    rbx, rbx
0x140066b38  jz      short loc_140066B6E
0x140066b3a  mov     eax, esi
0x140066b3c  lock xadd [rbx+8], eax
0x140066b41  add     eax, esi
0x140066b43  jnz     short loc_140066B6E
0x140066b45  mov     rax, [rbx]
0x140066b48  mov     rcx, rbx
0x140066b4b  mov     rax, [rax]
0x140066b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066b53  mov     eax, esi
0x140066b55  lock xadd [rbx+0Ch], eax
0x140066b5a  add     eax, esi
0x140066b5c  jnz     short loc_140066B6E
0x140066b5e  mov     rax, [rbx]
0x140066b61  mov     rcx, rbx
0x140066b64  mov     rax, [rax+8]
0x140066b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066b6d  nop
0x140066b6e  mov     rbx, [rdi+8]
0x140066b72  test    rbx, rbx
0x140066b75  jz      short loc_140066BAA
0x140066b77  mov     eax, esi
0x140066b79  lock xadd [rbx+8], eax
0x140066b7e  add     eax, esi
0x140066b80  jnz     short loc_140066BAA
0x140066b82  mov     rax, [rbx]
0x140066b85  mov     rcx, rbx
0x140066b88  mov     rax, [rax]
0x140066b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066b90  mov     eax, esi
0x140066b92  lock xadd [rbx+0Ch], eax
0x140066b97  add     eax, esi
0x140066b99  jnz     short loc_140066BAA
0x140066b9b  mov     rax, [rbx]
0x140066b9e  mov     rcx, rbx
0x140066ba1  mov     rax, [rax+8]
0x140066ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066baa  mov     rax, r15
0x140066bad  mov     rbx, [rsp+70h+arg_0]
0x140066bb5  add     rsp, 70h
0x140066bb9  pop     r15
0x140066bbb  pop     r14
0x140066bbd  pop     r13
0x140066bbf  pop     r12
0x140066bc1  pop     rdi
0x140066bc2  pop     rsi
0x140066bc3  pop     rbp
0x140066bc4  retn
0x140066bc5  mov     rsi, [rbx+20h]
0x140066bc9  mov     [rbp+pcbe], rsi
0x140066bcd  mov     rbx, [rbx+28h]
0x140066bd1  mov     [rbp+pcbe+8], rbx
0x140066bd5  jmp     loc_140066A20
0x140066bda  call    cs:__imp_GetLastError
0x140066be0  mov     ebx, eax
0x140066be2  test    eax, eax
0x140066be4  jle     short loc_140066BEF
0x140066be6  movzx   ebx, ax
0x140066be9  or      ebx, 80070000h
0x140066bef  lea     rax, WPP_GLOBAL_Control
0x140066bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140066bfd  cmp     rcx, rax
0x140066c00  jz      short loc_140066C20
0x140066c02  test    byte ptr [rcx+1Ch], 1
0x140066c06  jz      short loc_140066C20
0x140066c08  mov     edx, 0Ch
0x140066c0d  mov     r9d, ebx
0x140066c10  lea     r8, WPP_a6e5c4a2fee73d0f0f64a9c4f51812c4_Traceguids
0x140066c17  mov     rcx, [rcx+10h]
0x140066c1b  call    WPP_SF_d
0x140066c20  mov     edx, ebx; int
0x140066c22  lea     rcx, [rbp+pExceptionObject]; this
0x140066c26  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140066c2b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140066c32  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140066c36  call    _CxxThrowException_0
```
