# MpAsyncpWorkerThread

- ea: `0x140059670`
- end: `0x140059ea7`
- name: `MpAsyncpWorkerThread`
- size: `2103`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140003d20`
- `0x1400051bc`
- `0x1400059dc`
- `0x140011890`
- `0x1400118d0`
- `0x140059670`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14005975d`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005975d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400599a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400599a5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400597a3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400597a3`
- `ntoskrnl!ExQueryDepthSList` at `0x140059894`
- `ntoskrnl!ExQueryDepthSList` at `0x140059894`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400598b2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400598b2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400596dd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005973b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400596dd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14005973b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005985a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059b41`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005985a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059b41`
- `FLTMGR!FltSendMessage` at `0x140059917`
- `FLTMGR!FltSendMessage` at `0x1400599fb`
- `FLTMGR!FltSendMessage` at `0x140059917`
- `FLTMGR!FltSendMessage` at `0x1400599fb`

## pseudocode

```c
void __fastcall MpAsyncpWorkerThread(PVOID StartContext)
{
  int v1; // r14d
  NTSTATUS v2; // eax
  bool v3; // sf
  int v4; // ebp
  _QWORD *v5; // rdi
  char *v6; // rcx
  _QWORD *v7; // r8
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  _QWORD *v12; // rsi
  char *v13; // rbp
  USHORT v14; // bx
  ULONG v15; // r9d
  NTSTATUS v16; // ecx
  unsigned int v17; // eax
  ULONG v18; // r9d
  NTSTATUS v19; // ecx
  int v20; // ecx
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  union _LARGE_INTEGER Timeout; // [rsp+48h] [rbp-50h] BYREF
  union _LARGE_INTEGER v25; // [rsp+50h] [rbp-48h] BYREF
  PVOID Object[2]; // [rsp+58h] [rbp-40h] BYREF

  LOBYTE(v1) = -1;
  Object[0] = (char *)MpAsync + 48;
  Object[1] = (char *)MpAsync + 72;
  v2 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
  v3 = v2 < 0;
  if ( v2 )
  {
    v4 = 262153;
    while ( v3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
          KeGetCurrentThread(),
          v2);
LABEL_5:
      v2 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
      v3 = v2 < 0;
      if ( !v2 )
        goto LABEL_6;
    }
    v5 = 0;
    ExAcquireFastMutex((PFAST_MUTEX)((char *)MpAsync + 104));
    if ( dword_1400269E0 == _InterlockedCompareExchange(&dword_140026858, 0, dword_1400269E0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
          KeGetCurrentThread(),
          dword_1400269E0);
      v6 = (char *)MpAsync;
      v7 = (_QWORD *)*((_QWORD *)MpAsync + 3);
      v21 = (char *)MpAsync + 24;
      if ( v7 != (_QWORD *)((char *)MpAsync + 24) )
      {
        if ( (_QWORD *)v7[1] != v21 || (v22 = *v7, *(_QWORD **)(*v7 + 8LL) != v7) )
LABEL_51:
          __fastfail(3u);
        *v21 = v22;
        *(_QWORD *)(v22 + 8) = v21;
        goto LABEL_14;
      }
      v7 = (_QWORD *)*((_QWORD *)MpAsync + 1);
      v8 = (char *)MpAsync + 8;
      if ( v7 == (_QWORD *)((char *)MpAsync + 8) )
      {
LABEL_55:
        ExReleaseFastMutex((PFAST_MUTEX)(v6 + 104));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
            KeGetCurrentThread(),
            -1073741275);
        }
        goto LABEL_5;
      }
    }
    else
    {
      v6 = (char *)MpAsync;
      v7 = (_QWORD *)*((_QWORD *)MpAsync + 1);
      v8 = (char *)MpAsync + 8;
      if ( v7 == (_QWORD *)((char *)MpAsync + 8) )
      {
        v7 = (_QWORD *)*((_QWORD *)MpAsync + 3);
        v9 = (char *)MpAsync + 24;
        if ( v7 == (_QWORD *)((char *)MpAsync + 24) )
          goto LABEL_55;
        if ( (_QWORD *)v7[1] != v9 )
          goto LABEL_51;
        v10 = *v7;
        if ( *(_QWORD **)(*v7 + 8LL) != v7 )
          goto LABEL_51;
        *v9 = v10;
        *(_QWORD *)(v10 + 8) = v9;
        _InterlockedCompareExchange(&dword_140026858, 0, dword_140026858);
LABEL_14:
        if ( v7 )
        {
          v5 = v7 - 1;
          v11 = MpAsync;
          --*((_DWORD *)MpAsync + 40);
          v11[41] -= *((unsigned int *)v7 + 8);
        }
        ExReleaseFastMutex((PFAST_MUTEX)((char *)MpAsync + 104));
        v12 = 0;
        if ( v5 )
        {
          v12 = (_QWORD *)v5[4];
          v13 = (char *)MpAsync + 192;
          v1 = *((_DWORD *)v5 + 6);
          *(_DWORD *)v5 = -1162151174;
          ++*((_DWORD *)v13 + 7);
          v14 = *((_WORD *)v13 + 8);
          if ( ExQueryDepthSList((PSLIST_HEADER)v13) >= v14 )
          {
            ++*((_DWORD *)v13 + 8);
            (*((void (__fastcall **)(_QWORD *))v13 + 7))(v5);
          }
          else
          {
            _mm_lfence();
            ExpInterlockedPushEntrySList((PSLIST_HEADER)v13, (PSLIST_ENTRY)v5);
          }
          v4 = 262153;
        }
        if ( (v1 & 1) != 0 )
        {
          v15 = *((_DWORD *)v12 - 5);
          Timeout.QuadPart = 0;
          if ( v15 )
          {
            Timeout.QuadPart = -10000LL * (unsigned int)dword_1400269E4;
            v16 = FltSendMessage(
                    *(PFLT_FILTER *)(MpData + 16),
                    (PFLT_PORT *)(MpData + 416),
                    v12 - 3,
                    v15,
                    0,
                    0,
                    &Timeout);
            if ( v16 >= 0 )
              goto LABEL_23;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                18,
                WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
                KeGetCurrentThread());
            }
            v16 = -1073741811;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread(),
              v16);
          }
          _InterlockedIncrement((volatile signed __int32 *)MpAsync + 84);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            _mm_lfence();
            WPP_SF_qidd(
              WPP_GLOBAL_Control->AttachedDevice,
              22,
              *((unsigned int *)MpAsync + 84),
              KeGetCurrentThread(),
              *v12,
              *((_DWORD *)v12 + 4),
              *((_DWORD *)MpAsync + 84));
          }
        }
LABEL_23:
        if ( !v12 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread());
          }
          *((_QWORD *)MpAsync + 40) += MEMORY[0xFFFFFFFFFFFFFFEC];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread());
          }
          goto LABEL_5;
        }
        v17 = *((_DWORD *)v12 + 4);
        if ( v17 == 19
          || v17 <= 0x12 && _bittest(&v4, v17)
          || v17 == 2
          && *((_DWORD *)v12 + 6) == 2
          && MpDlpData
          && *((_BYTE *)MpDlpData + 32)
          && ((v20 = *((_DWORD *)MpDlpData + 68), (v20 & 1) != 0) || (v20 & 2) != 0 && (v12[19] & 0x810) != 0) )
        {
          if ( !*(_QWORD *)(MpData + 432) || (v1 & 2) == 0 )
            goto LABEL_27;
          v18 = *((_DWORD *)v12 - 5);
          v25.QuadPart = 0;
          if ( v18 )
          {
            v25.QuadPart = -10000LL * (unsigned int)dword_1400269E4;
            v19 = FltSendMessage(*(PFLT_FILTER *)(MpData + 16), (PFLT_PORT *)(MpData + 432), v12 - 3, v18, 0, 0, &v25);
            if ( v19 >= 0 )
            {
LABEL_27:
              *((_QWORD *)MpAsync + 40) += *((unsigned int *)v12 - 5);
              goto LABEL_31;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                18,
                WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
                KeGetCurrentThread());
            }
            v19 = -1073741811;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              23,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread(),
              v19);
          }
          _InterlockedIncrement((volatile signed __int32 *)MpAsync + 84);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 )
          {
            goto LABEL_27;
          }
          _mm_lfence();
          WPP_SF_qidd(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            *((unsigned int *)MpAsync + 84),
            KeGetCurrentThread(),
            *v12,
            *((_DWORD *)v12 + 4),
            *((_DWORD *)MpAsync + 84));
        }
        *((_QWORD *)MpAsync + 40) += *((unsigned int *)v12 - 5);
LABEL_31:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 3, 0xFFFFFFFF) == 1 )
          ExFreePoolWithTag(v12 - 3, 0x6D61504Du);
        goto LABEL_5;
      }
    }
    if ( (_QWORD *)v7[1] != v8 )
      goto LABEL_51;
    v23 = *v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_51;
    *v8 = v23;
    *(_QWORD *)(v23 + 8) = v8;
    _InterlockedIncrement(&dword_140026858);
    goto LABEL_14;
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
      KeGetCurrentThread());
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140059670  mov     r11, rsp
0x140059673  mov     [r11+8], rbx
0x140059677  mov     [r11+10h], rbp
0x14005967b  mov     [r11+18h], rsi
0x14005967f  push    rdi
0x140059680  push    r12
0x140059682  push    r13
0x140059684  push    r14
0x140059686  push    r15
0x140059688  sub     rsp, 70h
0x14005968c  mov     rax, cs:__security_cookie
0x140059693  xor     rax, rsp
0x140059696  mov     [rsp+98h+var_30], rax
0x14005969b  mov     rcx, cs:MpAsync
0x1400596a2  lea     rdx, [r11-40h]; Object
0x1400596a6  xor     r15d, r15d
0x1400596a9  xor     r9d, r9d; WaitReason
0x1400596ac  mov     [r11-60h], r15
0x1400596b0  mov     r8d, 1; WaitType
0x1400596b6  mov     [r11-68h], r15
0x1400596ba  mov     r14d, 0FFFFFFFFh
0x1400596c0  lea     rax, [rcx+30h]
0x1400596c4  mov     [r11-70h], r15b
0x1400596c8  mov     [r11-40h], rax
0x1400596cc  lea     rax, [rcx+48h]
0x1400596d0  mov     ecx, 2; Count
0x1400596d5  mov     [r11-38h], rax
0x1400596d9  mov     [r11-78h], r15b
0x1400596dd  call    cs:__imp_KeWaitForMultipleObjects
0x1400596e4  nop     dword ptr [rax+rax+00h]
0x1400596e9  lea     r12, WPP_GLOBAL_Control
0x1400596f0  test    eax, eax
0x1400596f2  jz      short loc_14005974B
0x1400596f4  mov     ebx, 0FFFFBABAh
0x1400596f9  mov     ebp, 40009h
0x1400596fe  jns     loc_140059795
0x140059704  mov     rcx, cs:WPP_GLOBAL_Control
0x14005970b  cmp     rcx, r12
0x14005970e  jnz     loc_140059B99
0x140059714  mov     [rsp+98h+WaitBlockArray], r15; WaitBlockArray
0x140059719  lea     rdx, [rsp+98h+Object]; Object
0x14005971e  mov     [rsp+98h+Timeout], r15; Timeout
0x140059723  xor     r9d, r9d; WaitReason
0x140059726  mov     [rsp+98h+Alertable], r15b; Alertable
0x14005972b  mov     r8d, 1; WaitType
0x140059731  mov     ecx, 2; Count
0x140059736  mov     [rsp+98h+WaitMode], r15b; WaitMode
0x14005973b  call    cs:__imp_KeWaitForMultipleObjects
0x140059742  nop     dword ptr [rax+rax+00h]
0x140059747  test    eax, eax
0x140059749  jnz     short loc_1400596FE
0x14005974b  mov     rax, cs:WPP_GLOBAL_Control
0x140059752  cmp     rax, r12
0x140059755  jnz     loc_140059E72
0x14005975b  xor     ecx, ecx; ExitStatus
0x14005975d  call    cs:__imp_PsTerminateSystemThread
0x140059764  nop     dword ptr [rax+rax+00h]
0x140059769  mov     rcx, [rsp+98h+var_30]
0x14005976e  xor     rcx, rsp; StackCookie
0x140059771  call    __security_check_cookie
0x140059776  lea     r11, [rsp+98h+var_28]
0x14005977b  mov     rbx, [r11+30h]
0x14005977f  mov     rbp, [r11+38h]
0x140059783  mov     rsi, [r11+40h]
0x140059787  mov     rsp, r11
0x14005978a  pop     r15
0x14005978c  pop     r14
0x14005978e  pop     r13
0x140059790  pop     r12
0x140059792  pop     rdi
0x140059793  retn
0x140059795  mov     rcx, cs:MpAsync
0x14005979c  mov     rdi, r15
0x14005979f  add     rcx, 68h ; 'h'; FastMutex
0x1400597a3  call    cs:__imp_ExAcquireFastMutex
0x1400597aa  nop     dword ptr [rax+rax+00h]
0x1400597af  mov     eax, cs:dword_1400269E0
0x1400597b5  lock cmpxchg cs:dword_140026858, r15d
0x1400597be  cmp     cs:dword_1400269E0, eax
0x1400597c4  jz      loc_140059AFF
0x1400597ca  mov     rcx, cs:MpAsync
0x1400597d1  mov     r8, [rcx+8]
0x1400597d5  lea     rax, [rcx+8]
0x1400597d9  cmp     r8, rax
0x1400597dc  jnz     loc_140059C35
0x1400597e2  mov     r8, [rcx+18h]
0x1400597e6  lea     rax, [rcx+18h]
0x1400597ea  cmp     r8, rax
0x1400597ed  jz      loc_140059B38
0x1400597f3  cmp     [r8+8], rax
0x1400597f7  jnz     loc_140059AF8
0x1400597fd  mov     rcx, [r8]
0x140059800  cmp     [rcx+8], r8
0x140059804  jnz     loc_140059AF8
0x14005980a  mov     [rax], rcx
0x14005980d  mov     [rcx+8], rax
0x140059811  mov     eax, cs:dword_140026858
0x140059817  lock cmpxchg cs:dword_140026858, r15d
0x140059820  test    r8, r8
0x140059823  jz      short loc_14005984F
0x140059825  mov     rax, cs:MpAsync
0x14005982c  lea     rdi, [r8-8]
0x140059830  mov     ecx, [rax+0A0h]
0x140059836  mov     rdx, cs:MpAsync
0x14005983d  dec     ecx
0x14005983f  mov     [rdx+0A0h], ecx
0x140059845  mov     eax, [rdi+28h]
0x140059848  sub     [rdx+148h], rax
0x14005984f  mov     rcx, cs:MpAsync
0x140059856  add     rcx, 68h ; 'h'; FastMutex
0x14005985a  call    cs:__imp_ExReleaseFastMutex
0x140059861  nop     dword ptr [rax+rax+00h]
0x140059866  mov     rsi, r15
0x140059869  test    rdi, rdi
0x14005986c  jz      short loc_1400598C3
0x14005986e  mov     rbp, cs:MpAsync
0x140059875  mov     rsi, [rdi+20h]
0x140059879  add     rbp, 0C0h
0x140059880  mov     r14d, [rdi+18h]
0x140059884  mov     rcx, rbp; SListHead
0x140059887  mov     dword ptr [rdi], 0BABAFAFAh
0x14005988d  inc     dword ptr [rbp+1Ch]
0x140059890  movzx   ebx, word ptr [rbp+10h]
0x140059894  call    cs:__imp_ExQueryDepthSList
0x14005989b  nop     dword ptr [rax+rax+00h]
0x1400598a0  cmp     ax, bx
0x1400598a3  jnb     loc_140059A93
0x1400598a9  lfence
0x1400598ac  mov     rdx, rdi; ListEntry
0x1400598af  mov     rcx, rbp; ListHead
0x1400598b2  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400598b9  nop     dword ptr [rax+rax+00h]
0x1400598be  mov     ebp, 40009h
0x1400598c3  test    r14b, 1
0x1400598c7  jz      short loc_14005992D
0x1400598c9  mov     rcx, cs:MpData
0x1400598d0  mov     r9d, [rsi-14h]; SenderBufferLength
0x1400598d4  mov     qword ptr [rsp+98h+var_50], r15
0x1400598d9  lea     rdx, [rcx+1A0h]; ClientPort
0x1400598e0  test    r9d, r9d
0x1400598e3  jz      loc_140059C5F
0x1400598e9  mov     eax, cs:dword_1400269E4
0x1400598ef  imul    r8, rax, 0FFFFFFFFFFFFD8F0h
0x1400598f6  lea     rax, [rsp+98h+var_50]
0x1400598fb  mov     qword ptr [rsp+98h+var_50], r8
0x140059900  lea     r8, [rsi-18h]; SenderBuffer
0x140059904  mov     rcx, [rcx+10h]; Filter
0x140059908  mov     [rsp+98h+Timeout], rax; Timeout
0x14005990d  mov     qword ptr [rsp+98h+Alertable], r15; ReplyLength
0x140059912  mov     qword ptr [rsp+98h+WaitMode], r15; ReplyBuffer
0x140059917  call    cs:__imp_FltSendMessage
0x14005991e  nop     dword ptr [rax+rax+00h]
0x140059923  mov     ecx, eax
0x140059925  test    eax, eax
0x140059927  js      loc_140059C9C
0x14005992d  test    rsi, rsi
0x140059930  jz      loc_140059A2D
0x140059936  mov     eax, [rsi+10h]
0x140059939  cmp     eax, 13h
0x14005993c  jnz     loc_140059A16
0x140059942  mov     rcx, cs:MpData
0x140059949  lea     rdx, [rcx+1B0h]; ClientPort
0x140059950  cmp     [rdx], r15
0x140059953  jz      short loc_14005995B
0x140059955  test    r14b, 2
0x140059959  jnz     short loc_1400599BB
0x14005995b  mov     rdx, cs:MpAsync
0x140059962  mov     eax, [rsi-14h]
0x140059965  add     [rdx+140h], rax
0x14005996c  jmp     short loc_14005998D
0x14005996e  cmp     eax, 2
0x140059971  jnz     short loc_14005997C
0x140059973  cmp     [rsi+18h], eax
0x140059976  jz      loc_140059AA8
0x14005997c  mov     rcx, cs:MpAsync
0x140059983  mov     eax, [rsi-14h]
0x140059986  add     [rcx+140h], rax
0x14005998d  mov     eax, 0FFFFFFFFh
0x140059992  lock xadd [rsi+0Ch], eax
0x140059997  cmp     eax, 1
0x14005999a  jnz     short loc_1400599B1
0x14005999c  mov     edx, 6D61504Dh; Tag
0x1400599a1  lea     rcx, [rsi-18h]; P
0x1400599a5  call    cs:__imp_ExFreePoolWithTag
0x1400599ac  nop     dword ptr [rax+rax+00h]
0x1400599b1  mov     ebx, 0FFFFBABAh
0x1400599b6  jmp     loc_140059714
0x1400599bb  mov     r9d, [rsi-14h]; SenderBufferLength
0x1400599bf  mov     qword ptr [rsp+98h+var_48], r15
0x1400599c4  test    r9d, r9d
0x1400599c7  jz      loc_140059D83
0x1400599cd  mov     eax, cs:dword_1400269E4
0x1400599d3  imul    r8, rax, 0FFFFFFFFFFFFD8F0h
0x1400599da  lea     rax, [rsp+98h+var_48]
0x1400599df  mov     qword ptr [rsp+98h+var_48], r8
0x1400599e4  lea     r8, [rsi-18h]; SenderBuffer
0x1400599e8  mov     rcx, [rcx+10h]; Filter
0x1400599ec  mov     [rsp+98h+Timeout], rax; Timeout
0x1400599f1  mov     qword ptr [rsp+98h+Alertable], r15; ReplyLength
0x1400599f6  mov     qword ptr [rsp+98h+WaitMode], r15; ReplyBuffer
0x1400599fb  call    cs:__imp_FltSendMessage
0x140059a02  nop     dword ptr [rax+rax+00h]
0x140059a07  mov     ecx, eax
0x140059a09  test    eax, eax
0x140059a0b  jns     loc_14005995B
0x140059a11  jmp     loc_140059DC0
0x140059a16  cmp     eax, 12h
0x140059a19  ja      loc_14005996E
0x140059a1f  bt      ebp, eax
0x140059a22  jb      loc_140059942
0x140059a28  jmp     loc_14005996E
0x140059a2d  mov     rax, cs:WPP_GLOBAL_Control
0x140059a34  cmp     rax, r12
0x140059a37  jnz     loc_140059D4E
0x140059a3d  mov     rcx, cs:MpAsync
0x140059a44  mov     eax, [rsi-14h]
0x140059a47  add     [rcx+140h], rax
0x140059a4e  mov     rax, cs:WPP_GLOBAL_Control
0x140059a55  cmp     rax, r12
0x140059a58  jz      loc_1400599B1
0x140059a5e  mov     eax, [rax+2Ch]
0x140059a61  test    al, 2
0x140059a63  jz      loc_1400599B1
0x140059a69  mov     r9, gs:188h
0x140059a72  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140059a79  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a80  mov     edx, 1Ch
0x140059a85  mov     rcx, [rcx+18h]
0x140059a89  call    WPP_SF_q
0x140059a8e  jmp     loc_1400599B1
0x140059a93  inc     dword ptr [rbp+20h]
0x140059a96  mov     rcx, rdi
0x140059a99  mov     rax, [rbp+38h]
0x140059a9d  call    cs:__guard_dispatch_icall_fptr
0x140059aa3  jmp     loc_1400598BE
0x140059aa8  mov     rax, cs:MpDlpData
0x140059aaf  test    rax, rax
0x140059ab2  jz      loc_14005997C
0x140059ab8  movzx   eax, byte ptr [rax+20h]
0x140059abc  test    al, al
0x140059abe  jz      loc_14005997C
0x140059ac4  mov     rax, cs:MpDlpData
0x140059acb  mov     ecx, [rax+110h]
0x140059ad1  test    cl, 1
0x140059ad4  jnz     loc_140059942
0x140059ada  test    cl, 2
0x140059add  jz      loc_14005997C
0x140059ae3  test    dword ptr [rsi+98h], 810h
0x140059aed  jz      loc_14005997C
0x140059af3  jmp     loc_140059942
0x140059af8  mov     ecx, 3
0x140059afd  int     29h; Win8: RtlFailFast(ecx)
0x140059aff  mov     rax, cs:WPP_GLOBAL_Control
0x140059b06  cmp     rax, r12
0x140059b09  jnz     loc_140059BD3
0x140059b0f  mov     rcx, cs:MpAsync
0x140059b16  mov     r8, [rcx+18h]
0x140059b1a  lea     rax, [rcx+18h]
0x140059b1e  cmp     r8, rax
0x140059b21  jnz     loc_140059C12
0x140059b27  mov     r8, [rcx+8]
0x140059b2b  lea     rax, [rcx+8]
0x140059b2f  cmp     r8, rax
0x140059b32  jnz     loc_140059C35
0x140059b38  add     rcx, 68h ; 'h'; FastMutex
0x140059b3c  mov     ebx, 0C0000225h
0x140059b41  call    cs:__imp_ExReleaseFastMutex
0x140059b48  nop     dword ptr [rax+rax+00h]
0x140059b4d  mov     rax, cs:WPP_GLOBAL_Control
0x140059b54  cmp     rax, r12
0x140059b57  jz      loc_1400599B1
0x140059b5d  mov     eax, [rax+2Ch]
0x140059b60  test    al, 1
0x140059b62  jz      loc_1400599B1
0x140059b68  lfence
0x140059b6b  mov     r9, gs:188h
0x140059b74  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140059b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b82  mov     edx, 19h
0x140059b87  mov     dword ptr [rsp+98h+WaitMode], ebx
0x140059b8b  mov     rcx, [rcx+18h]
0x140059b8f  call    WPP_SF_qD
0x140059b94  jmp     loc_1400599B1
0x140059b99  mov     ecx, [rcx+2Ch]
0x140059b9c  test    cl, 1
0x140059b9f  jz      loc_140059714
0x140059ba5  mov     r9, gs:188h
0x140059bae  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140059bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140059bbc  mov     edx, 14h
0x140059bc1  mov     dword ptr [rsp+98h+WaitMode], eax
0x140059bc5  mov     rcx, [rcx+18h]
0x140059bc9  call    WPP_SF_qD
0x140059bce  jmp     loc_140059714
0x140059bd3  mov     eax, [rax+2Ch]
0x140059bd6  test    al, 2
0x140059bd8  jz      loc_140059B0F
0x140059bde  mov     r9, gs:188h
0x140059be7  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140059bee  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
