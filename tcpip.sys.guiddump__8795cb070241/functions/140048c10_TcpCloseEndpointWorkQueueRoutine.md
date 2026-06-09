# TcpCloseEndpointWorkQueueRoutine

- ea: `0x140048c10`
- end: `0x140048f1f`
- name: `TcpCloseEndpointWorkQueueRoutine`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400479a0`
- `0x140048a40`

## callees

- `0x140048c10`
- `0x1400491f0`
- `0x140095d30`
- `0x140096000`
- `0x1400b6760`
- `0x1400b6880`
- `0x1400b6bc4`
- `0x1400ed04c`
- `0x14016896c`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x140048eb4`
- `ntoskrnl!KeBugCheck` at `0x140048eb4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x140048ccf`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x140048ccf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140048cde`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140048cde`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140048cfe`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140048cfe`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048dba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048dba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048df2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048df2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048de6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048de6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048da9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048da9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048d13`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048d13`
- `NETIO!NetioInsertWorkQueue` at `0x140048ecb`
- `NETIO!NetioInsertWorkQueue` at `0x140048ecb`

## pseudocode

```c
void __fastcall TcpCloseEndpointWorkQueueRoutine(_QWORD *a1)
{
  _QWORD *v2; // r14
  _QWORD *v3; // rbp
  __int64 v4; // rbx
  volatile signed __int32 *v5; // r8
  _QWORD *v6; // r15
  _QWORD *v7; // r12
  signed __int32 v8; // r9d
  volatile unsigned __int32 v9; // r10d
  unsigned __int32 v10; // r9d
  volatile unsigned __int32 v11; // r11d
  volatile signed __int32 *v12; // rdi
  unsigned int *v13; // rax
  PKSPIN_LOCK v14; // rbx
  unsigned int v15; // edi
  __int64 CompartmentUnderLock; // r15
  __int64 *v17; // rax
  __int64 v18; // rbx
  unsigned __int16 v19; // r12
  __int64 v20; // r15
  signed __int32 v21; // r9d
  char v22; // [rsp+20h] [rbp-68h]
  char v23[4]; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-44h]
  __int128 v25; // [rsp+48h] [rbp-40h] BYREF

  do
  {
    v2 = (_QWORD *)*a1;
    v3 = a1 - 18;
    if ( (*(_DWORD *)(a1 - 16) & 3) == 1 )
    {
      v13 = (unsigned int *)v3[11];
      v14 = TcpCompartmentSet;
      v23[0] = 0;
      v24 = 0;
      v15 = *v13;
      if ( *v13 == 1 )
      {
        CompartmentUnderLock = TcpCompartmentSet[41];
      }
      else
      {
        RtlAcquireScalableReadLock(TcpCompartmentSet);
        CompartmentUnderLock = InetGetCompartmentUnderLock(v14, v15, 0);
        RtlReleaseScalableReadLock(v14, v24, (unsigned __int8)v23[0]);
      }
      v17 = *(__int64 **)(CompartmentUnderLock + 32);
      v18 = v3[12];
      v19 = *((_WORD *)v3 + 57);
      v23[0] = 0;
      v20 = *v17;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite((PERESOURCE)v20, 1u);
      InetReleasePortUnderLock(v20, v19, (_DWORD)v3 + 120, v18, (__int64)v23);
      ExReleaseResourceLite((PERESOURCE)v20);
      KeLeaveCriticalRegion();
      if ( v23[0] )
        PtClientReleasePortRange(v3[16]);
      v3[16] = 0;
      if ( *(_DWORD *)(v20 + 104) == 17 && v19 == 0x9411 )
        UdpOffloadEnableUroForIpsec();
      if ( dword_1402241D4 )
      {
        v25 = 0;
        if ( (BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
        {
          v22 = __ROR2__(*((_WORD *)v3 + 57), 8);
          *(_QWORD *)&v25 = a1 - 18;
          McTemplateK0phqp_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_RELEASE_PORT,
            (unsigned int)&v25,
            (_DWORD)a1 - 144,
            v22,
            0,
            0);
        }
      }
    }
    v4 = _InterlockedDecrement64(v3 + 1);
    if ( v4 < 0 )
      KeBugCheck(0x1Cu);
    v5 = (volatile signed __int32 *)EndpointReferenceHistory;
    v6 = a1;
    v7 = a1;
    a1 = v2;
    if ( EndpointReferenceHistory )
    {
      v8 = _InterlockedExchangeAdd((volatile signed __int32 *)EndpointReferenceHistory + 1, 1u);
      v9 = *v5;
      v10 = v8 + 1;
      if ( *v5 )
      {
        v11 = 0;
        while ( v5[18 * (v10 % v9) + 3] )
        {
          v21 = _InterlockedExchangeAdd(v5 + 1, 1u);
          v9 = *v5;
          v10 = v21 + 1;
          if ( ++v11 >= *v5 )
            goto LABEL_9;
        }
        if ( v11 < v9 )
        {
          v12 = &v5[18 * (v10 % v9)];
          *((_DWORD *)v12 + 2) = v4;
          *((_DWORD *)v12 + 4) = PsGetCurrentThreadProcessId();
          *((_DWORD *)v12 + 5) = (unsigned int)PsGetCurrentThreadId();
          RtlCaptureStackBackTrace(1u, 6u, (PVOID *)v12 + 3, 0);
          *((_QWORD *)v12 + 9) = v3;
        }
      }
    }
LABEL_9:
    if ( !v4 )
    {
      if ( KeGetCurrentIrql() )
      {
        NetioInsertWorkQueue(TcpCleanupEndpointWorkQueue, v6);
      }
      else
      {
        *v6 = 0;
        TcpCleanupEndpointWorkQueueRoutine(v7);
      }
    }
  }
  while ( v2 );
}

```

## disassembly

```asm
0x140048c10  mov     r11, rsp
0x140048c13  push    rbx
0x140048c14  push    rbp
0x140048c15  push    rsi
0x140048c16  push    r13
0x140048c18  push    r14
0x140048c1a  sub     rsp, 60h
0x140048c1e  mov     rax, cs:__security_cookie
0x140048c25  xor     rax, rsp
0x140048c28  mov     [rsp+88h+var_30], rax
0x140048c2d  mov     [r11+10h], rdi
0x140048c31  mov     rsi, rcx
0x140048c34  mov     [r11+18h], r12
0x140048c38  xor     r13d, r13d
0x140048c3b  mov     [r11+20h], r15
0x140048c3f  mov     r14, [rsi]
0x140048c42  lea     rbp, [rsi-90h]
0x140048c49  mov     eax, [rbp+10h]
0x140048c4c  and     al, 3
0x140048c4e  cmp     al, 1
0x140048c50  jz      loc_140048D6D
0x140048c56  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140048c5d  lock xadd [rbp+8], rbx
0x140048c63  sub     rbx, 1
0x140048c67  js      loc_140048EAF
0x140048c6d  mov     r8, cs:EndpointReferenceHistory
0x140048c74  mov     r15, rsi
0x140048c77  mov     r12, rsi
0x140048c7a  mov     rsi, r14
0x140048c7d  test    r8, r8
0x140048c80  jz      loc_140048D0E
0x140048c86  mov     r9d, 1
0x140048c8c  lock xadd [r8+4], r9d
0x140048c92  mov     r10d, [r8]
0x140048c95  inc     r9d
0x140048c98  test    r10d, r10d
0x140048c9b  jz      short loc_140048D0E
0x140048c9d  mov     r11d, r13d
0x140048ca0  xor     edx, edx
0x140048ca2  mov     eax, r9d
0x140048ca5  div     r10d
0x140048ca8  lea     rax, [rdx+rdx*8]
0x140048cac  cmp     [r8+rax*8+0Ch], r13d
0x140048cb1  jnz     loc_140048E8C
0x140048cb7  cmp     r11d, r10d
0x140048cba  jnb     short loc_140048D0E
0x140048cbc  xor     edx, edx
0x140048cbe  mov     eax, r9d
0x140048cc1  div     r10d
0x140048cc4  lea     rax, [rdx+rdx*8]
0x140048cc8  lea     rdi, [r8+rax*8]
0x140048ccc  mov     [rdi+8], ebx
0x140048ccf  call    cs:__imp_PsGetCurrentThreadProcessId
0x140048cd6  nop     dword ptr [rax+rax+00h]
0x140048cdb  mov     [rdi+10h], eax
0x140048cde  call    cs:__imp_PsGetCurrentThreadId
0x140048ce5  nop     dword ptr [rax+rax+00h]
0x140048cea  lea     r8, [rdi+18h]; BackTrace
0x140048cee  xor     r9d, r9d; BackTraceHash
0x140048cf1  mov     edx, 6; FramesToCapture
0x140048cf6  mov     [rdi+14h], eax
0x140048cf9  mov     ecx, 1; FramesToSkip
0x140048cfe  call    cs:__imp_RtlCaptureStackBackTrace
0x140048d05  nop     dword ptr [rax+rax+00h]
0x140048d0a  mov     [rdi+48h], rbp
0x140048d0e  test    rbx, rbx
0x140048d11  jnz     short loc_140048D32
0x140048d13  call    cs:__imp_KeGetCurrentIrql
0x140048d1a  nop     dword ptr [rax+rax+00h]
0x140048d1f  test    al, al
0x140048d21  jnz     loc_140048EC1
0x140048d27  mov     rcx, r12
0x140048d2a  mov     [r15], r13
0x140048d2d  call    TcpCleanupEndpointWorkQueueRoutine
0x140048d32  test    r14, r14
0x140048d35  jnz     loc_140048C3F
0x140048d3b  mov     r15, [rsp+88h+arg_18]
0x140048d43  mov     r12, [rsp+88h+arg_10]
0x140048d4b  mov     rdi, [rsp+88h+arg_8]
0x140048d53  mov     rcx, [rsp+88h+var_30]
0x140048d58  xor     rcx, rsp; StackCookie
0x140048d5b  call    __security_check_cookie
0x140048d60  add     rsp, 60h
0x140048d64  pop     r14
0x140048d66  pop     r13
0x140048d68  pop     rsi
0x140048d69  pop     rbp
0x140048d6a  pop     rbx
0x140048d6b  retn
0x140048d6d  mov     rax, [rbp+58h]
0x140048d71  mov     rbx, cs:TcpCompartmentSet
0x140048d78  mov     [rsp+88h+var_48], r13b
0x140048d7d  mov     [rsp+88h+var_44], r13d
0x140048d82  mov     edi, [rax]
0x140048d84  cmp     edi, 1
0x140048d87  jnz     loc_140048EDC
0x140048d8d  mov     r15, [rbx+148h]
0x140048d94  mov     rax, [r15+20h]
0x140048d98  mov     rbx, [rbp+60h]
0x140048d9c  movzx   r12d, word ptr [rbp+72h]
0x140048da1  mov     [rsp+88h+var_48], r13b
0x140048da6  mov     r15, [rax]
0x140048da9  call    cs:__imp_KeEnterCriticalRegion
0x140048db0  nop     dword ptr [rax+rax+00h]
0x140048db5  mov     dl, 1; Wait
0x140048db7  mov     rcx, r15; Resource
0x140048dba  call    cs:__imp_ExAcquireResourceSharedLite
0x140048dc1  nop     dword ptr [rax+rax+00h]
0x140048dc6  lea     rax, [rsp+88h+var_48]
0x140048dcb  mov     r9, rbx
0x140048dce  lea     r8, [rbp+78h]
0x140048dd2  mov     [rsp+88h+var_68], rax
0x140048dd7  movzx   edx, r12w
0x140048ddb  mov     rcx, r15
0x140048dde  call    InetReleasePortUnderLock
0x140048de3  mov     rcx, r15; Resource
0x140048de6  call    cs:__imp_ExReleaseResourceLite
0x140048ded  nop     dword ptr [rax+rax+00h]
0x140048df2  call    cs:__imp_KeLeaveCriticalRegion
0x140048df9  nop     dword ptr [rax+rax+00h]
0x140048dfe  cmp     [rsp+88h+var_48], r13b
0x140048e03  jz      short loc_140048E11
0x140048e05  mov     rcx, [rbp+80h]
0x140048e0c  call    PtClientReleasePortRange
0x140048e11  mov     [rbp+80h], r13
0x140048e18  cmp     dword ptr [r15+68h], 11h
0x140048e1d  jnz     short loc_140048E2E
0x140048e1f  mov     eax, 9411h
0x140048e24  cmp     r12w, ax
0x140048e28  jz      loc_140048F15
0x140048e2e  cmp     cs:dword_1402241D4, r13d
0x140048e35  jz      loc_140048C56
0x140048e3b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 10h
0x140048e42  xorps   xmm0, xmm0
0x140048e45  movups  [rsp+88h+var_40], xmm0
0x140048e4a  jz      loc_140048C56
0x140048e50  movzx   eax, word ptr [rbp+72h]
0x140048e54  lea     r8, [rsp+88h+var_40]
0x140048e59  ror     ax, 8
0x140048e5d  lea     rdx, TCP_RELEASE_PORT
0x140048e64  mov     [rsp+88h+var_58], r13
0x140048e69  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140048e70  mov     [rsp+88h+var_60], r13d
0x140048e75  mov     r9, rbp
0x140048e78  mov     word ptr [rsp+88h+var_68], ax
0x140048e7d  mov     qword ptr [rsp+88h+var_40], rbp
0x140048e82  call    McTemplateK0phqp_EtwWriteTransfer
0x140048e87  jmp     loc_140048C56
0x140048e8c  mov     r9d, 1
0x140048e92  lock xadd [r8+4], r9d
0x140048e98  mov     r10d, [r8]
0x140048e9b  inc     r9d
0x140048e9e  inc     r11d
0x140048ea1  cmp     r11d, r10d
0x140048ea4  jb      loc_140048CA0
0x140048eaa  jmp     loc_140048D0E
0x140048eaf  mov     ecx, 1Ch; BugCheckCode
0x140048eb4  call    cs:__imp_KeBugCheck
0x140048ec1  mov     rdx, r15
0x140048ec4  lea     rcx, TcpCleanupEndpointWorkQueue
0x140048ecb  call    cs:__imp_NetioInsertWorkQueue
0x140048ed2  nop     dword ptr [rax+rax+00h]
0x140048ed7  jmp     loc_140048D32
0x140048edc  lea     r8, [rsp+88h+var_48]
0x140048ee1  mov     rcx, rbx; SpinLock
0x140048ee4  lea     rdx, [rsp+88h+var_44]
0x140048ee9  call    RtlAcquireScalableReadLock
0x140048eee  xor     r8d, r8d
0x140048ef1  mov     edx, edi
0x140048ef3  mov     rcx, rbx
0x140048ef6  call    InetGetCompartmentUnderLock
0x140048efb  movzx   r8d, [rsp+88h+var_48]
0x140048f01  mov     rcx, rbx
0x140048f04  mov     edx, [rsp+88h+var_44]
0x140048f08  mov     r15, rax
0x140048f0b  call    RtlReleaseScalableReadLock
0x140048f10  jmp     loc_140048D94
0x140048f15  call    UdpOffloadEnableUroForIpsec
0x140048f1a  jmp     loc_140048E2E
```
