# SkeBugCheckEx

- ea: `0x1400119c4`
- end: `0x140011d45`
- name: `SkeBugCheckEx`
- size: `897`
- prototype: `void __stdcall __noreturn(ULONG BugCheckCode, ULONG_PTR BugCheckParameter1, ULONG_PTR BugCheckParameter2, ULONG_PTR BugCheckParameter3, ULONG_PTR BugCheckParameter4)`
- caller_count: `110`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008ec4`
- `0x1400091e0`
- `0x140009940`
- `0x140009a90`
- `0x14000b2c0`
- `0x14000b980`
- `0x14000bab0`
- `0x14000e4b0`
- `0x140011f1c`
- `0x140014dd0`
- `0x14001b0c0`
- `0x140024724`
- `0x14002aeac`
- `0x140033544`
- `0x1400346b0`
- `0x140036860`
- `0x14003793c`
- `0x14003b9dc`
- `0x140040c94`
- `0x140041954`
- `0x1400435d4`
- `0x1400443e4`
- `0x1400450a4`
- `0x140048448`
- `0x14004e52c`
- `0x14004e670`
- `0x14004ea5c`
- `0x140050ba4`
- `0x1400518a4`
- `0x140051998`
- `0x140052318`
- `0x140053104`
- `0x140053250`
- `0x140053348`
- `0x14005443c`
- `0x140055000`
- `0x140055a0c`
- `0x1400576d8`
- `0x1400578dc`
- `0x140057dac`
- `0x140058538`
- `0x14005982c`
- `0x14005f8b8`
- `0x14006004c`
- `0x140063ca8`
- `0x140071224`
- `0x140078a40`
- `0x14007e4d8`
- `0x140082760`
- `0x140084c54`

## callees

- `0x1400119c4`
- `0x14002944c`
- `0x14002955c`
- `0x140029a9c`
- `0x14002a0b0`
- `0x14002a8f8`
- `0x14002c310`
- `0x14002c4f8`
- `0x14003f2d0`
- `0x1400716d0`
- `0x140088ef4`
- `0x14009e598`
- `0x14009efb8`
- `0x1400aa380`
- `0x1400ef310`
- `0x1400f06e0`
- `0x1400f2f80`
- `0x1400f2fc0`
- `0x1400f9780`
- `0x1400f9a80`

## pseudocode

```c
void __stdcall __noreturn SkeBugCheckEx(
        ULONG BugCheckCode,
        ULONG_PTR BugCheckParameter1,
        ULONG_PTR BugCheckParameter2,
        ULONG_PTR BugCheckParameter3,
        ULONG_PTR BugCheckParameter4)
{
  __int64 v6; // rbx
  ULONG_PTR v7; // rdi
  ULONG_PTR v8; // rsi
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r14
  ULONG_PTR v10; // r12
  __int64 v11; // r15
  struct _EXCEPTION_REGISTRATION_RECORD *v12; // rcx
  PEXCEPTION_ROUTINE Handler; // rax
  __int64 *v14; // rbp
  char *v15; // rdi
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rsi
  size_t v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rbx
  unsigned __int64 ReferenceTime; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *v27; // rdi
  unsigned int v29; // esi
  unsigned __int8 CurrentIrql; // bp
  _DWORD *v31; // rbx
  __int64 PhysicalAddress; // rax
  __int64 v33; // rcx

  v6 = BugCheckCode;
  v7 = BugCheckParameter2;
  v8 = BugCheckParameter1;
  SkeDisableInterrupts();
  KeGetCurrentIrql();
  __writecr8(0xFu);
  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  if ( _InterlockedCompareExchange64(&SkiBugCheckOwner, (signed __int64)ExceptionList, 0) )
  {
    while ( 1 )
      _mm_pause();
  }
  v10 = BugCheckParameter4;
  v11 = (unsigned int)v6;
  qword_14014EFE0 = BugCheckParameter4;
  SkiBugCheckData = v6;
  qword_14014EFC8 = v8;
  qword_14014EFD0 = v7;
  qword_14014EFD8 = BugCheckParameter3;
  if ( !_InterlockedCompareExchange(&SkiPreBugCheckStackSaved, 1, 0) )
  {
    v12 = KeGetPcr()->NtTib.ExceptionList;
    Handler = v12->Handler;
    if ( !Handler )
      Handler = v12[2].Handler;
    v14 = SkiPreBugCheckStackSaveArea;
    v15 = (char *)(*((_QWORD *)Handler + 15) & 0xFFFFFFFFFFFFF000uLL);
    v16 = *((_QWORD *)Handler + 14) - (_QWORD)v15;
    v17 = 24576;
    if ( v16 > 0x6000 || (v17 = v16) != 0 )
    {
      do
      {
        if ( !(unsigned __int8)SkmmDbgIsAddressValid(v15) )
          break;
        v18 = v17;
        if ( v17 > 0x1000 )
          v18 = 4096;
        memmove(v14, v15, v18);
        v15 += v18;
        v14 = (__int64 *)((char *)v14 + v18);
        v17 -= v18;
      }
      while ( v17 );
      v10 = BugCheckParameter4;
    }
    v8 = BugCheckParameter1;
    v7 = BugCheckParameter2;
  }
  SkiHibernateAborted = 1;
  _InterlockedExchange64(&SkiBarrierWait, 0);
  _InterlockedExchange64(&SkiMirrorOwner, 0);
  ShvlNotifyRootCrashdump(0);
  RtlCaptureContext((PCONTEXT)ExceptionList[62].Handler);
  SkiSaveProcessorControlState(&ExceptionList[63]);
  SkeFreezeExecution();
  v20 = 500 * (qword_14014EC10 / 0xF4240uLL);
  if ( SkeTscInfo == 2 )
  {
    v21 = ((__int64 (*)(void))ShvlGetReferenceTime)();
  }
  else
  {
    v21 = __rdtsc();
    v22 = (unsigned __int64)HIDWORD(v21) << 32;
  }
  v23 = v21 + v20;
  while ( 1 )
  {
    if ( SkeTscInfo == 2 )
    {
      ReferenceTime = ShvlGetReferenceTime(v19, v22);
    }
    else
    {
      ReferenceTime = __rdtsc();
      v22 = (unsigned __int64)HIDWORD(ReferenceTime) << 32;
    }
    if ( ReferenceTime >= v23 )
      break;
    _mm_pause();
  }
  if ( (SkhalpEfiFlags & 1) != 0 )
  {
    SkhalpReportBugCheckProgress((unsigned int)L"BugCheckCode", (unsigned int)BUGCHECK_EFI_GUID, 395, 4, 1);
    SkhalpReportBugCheckProgress((unsigned int)L"BugCheckParameter1", (unsigned int)BUGCHECK_EFI_GUID, v11, 8, 1);
  }
  SkhalSaveBugCheckProgress(160);
  LOBYTE(v25) = 1;
  SkSwitchToCrashdumpMode(v25);
  v26 = qword_14016B5E0;
  if ( qword_14016B5E0 )
  {
    *(_DWORD *)(qword_14016B5E0 + 4) |= 1u;
    *(_DWORD *)(v26 + 8) = 395;
    *(_QWORD *)(v26 + 16) = v11;
    *(_QWORD *)(v26 + 24) = v8;
    *(_QWORD *)(v26 + 32) = v7;
    *(_QWORD *)(v26 + 40) = BugCheckParameter3;
    *(_QWORD *)(v26 + 48) = v10;
    RtlCaptureContext(&IumCrashCpuContext);
  }
  ShvlNotifyRootCrashdump(1);
  SkhalSaveBugCheckProgress(161);
  if ( SkpgInitialized )
  {
    if ( SkpgContext )
    {
      _InterlockedExchange(&SkpgBugCheckActive, 1);
      if ( !_interlockedbittestandset((volatile signed __int32 *)&KeGetPcr()->NtTib.ExceptionList[12].Handler + 1, 0) )
      {
        SkpgxDefeatureProcessorForBugCheck();
        ShvlRestrictUserMode();
      }
    }
  }
  v27 = KeGetPcr()->NtTib.ExceptionList;
  while ( _BitScanForward(&v29, HIDWORD(v27[8].Next)) )
  {
    if ( _interlockedbittestandreset((volatile signed __int32 *)&v27[8].Next + 1, v29) )
    {
      CurrentIrql = 0;
      goto LABEL_35;
    }
  }
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(0xFu);
  v27 = KeGetPcr()->NtTib.ExceptionList;
  v29 = 4;
LABEL_35:
  v31 = (_DWORD *)((char *)v27[8].Handler + 4096 * v29);
  memset_0(v31 + 2, 0, 0xFF8u);
  *v31 = 2;
  v31[1] = 2;
  PhysicalAddress = SkmmGetPhysicalAddress(v31);
  HvcallCodeVa(135, PhysicalAddress, 0);
  if ( v29 >= 4 )
  {
    LOBYTE(v33) = CurrentIrql;
    SkeLowerIrql(v33);
  }
  else
  {
    _interlockedbittestandset((volatile signed __int32 *)&v27[8].Next + 1, v29);
  }
  SkhalSaveBugCheckProgress(162);
  SkiSaveCrashMinidump();
  if ( (ShvlpFlags & 1) == 0 )
    ShvlInjectVtl0Nmi();
  SkSwitchToLimitedDispatchLoop((unsigned int)SkeBugCheckStatus);
}

```

## disassembly

```asm
0x1400119c4  mov     [rsp+arg_18], rbx
0x1400119c9  mov     [rsp+arg_10], r8
0x1400119ce  mov     [rsp+arg_8], rdx
0x1400119d3  push    rbp
0x1400119d4  push    rsi
0x1400119d5  push    rdi
0x1400119d6  push    r12
0x1400119d8  push    r13
0x1400119da  push    r14
0x1400119dc  push    r15
0x1400119de  sub     rsp, 40h
0x1400119e2  mov     r13, r9
0x1400119e5  mov     ebx, ecx
0x1400119e7  mov     rdi, r8
0x1400119ea  mov     rsi, rdx
0x1400119ed  call    SkeDisableInterrupts
0x1400119f2  mov     rax, cr8
0x1400119f6  mov     eax, 0Fh
0x1400119fb  mov     cr8, rax
0x1400119ff  mov     r14, gs:0
0x140011a08  xor     eax, eax
0x140011a0a  lock cmpxchg cs:SkiBugCheckOwner, r14
0x140011a13  jnz     loc_140011D41
0x140011a19  mov     r12, [rsp+78h+BugCheckParameter4]
0x140011a21  mov     r15d, ebx
0x140011a24  mov     cs:qword_14014EFE0, r12
0x140011a2b  mov     ebp, 1
0x140011a30  mov     cs:SkiBugCheckData, rbx
0x140011a37  xor     eax, eax
0x140011a39  mov     cs:qword_14014EFC8, rsi
0x140011a40  mov     cs:qword_14014EFD0, rdi
0x140011a47  mov     cs:qword_14014EFD8, r13
0x140011a4e  lock cmpxchg cs:SkiPreBugCheckStackSaved, ebp
0x140011a56  jnz     loc_140011AEF
0x140011a5c  mov     rcx, gs:0
0x140011a65  mov     rax, [rcx+8]
0x140011a69  test    rax, rax
0x140011a6c  jnz     short loc_140011A72
0x140011a6e  mov     rax, [rcx+28h]
0x140011a72  mov     rdi, [rax+78h]
0x140011a76  lea     rbp, SkiPreBugCheckStackSaveArea
0x140011a7d  mov     rax, [rax+70h]
0x140011a81  and     rdi, 0FFFFFFFFFFFFF000h
0x140011a88  sub     rax, rdi
0x140011a8b  mov     esi, 6000h
0x140011a90  cmp     rax, rsi
0x140011a93  ja      short loc_140011A9D
0x140011a95  mov     rsi, rax
0x140011a98  test    rax, rax
0x140011a9b  jz      short loc_140011ADA
0x140011a9d  mov     r12d, 1000h
0x140011aa3  mov     rcx, rdi
0x140011aa6  call    SkmmDbgIsAddressValid
0x140011aab  test    al, al
0x140011aad  jz      short loc_140011AD2
0x140011aaf  cmp     rsi, r12
0x140011ab2  mov     rbx, rsi
0x140011ab5  mov     rdx, rdi; Src
0x140011ab8  mov     rcx, rbp; void *
0x140011abb  cmova   rbx, r12
0x140011abf  mov     r8, rbx; Size
0x140011ac2  call    memmove
0x140011ac7  add     rdi, rbx
0x140011aca  add     rbp, rbx
0x140011acd  sub     rsi, rbx
0x140011ad0  jnz     short loc_140011AA3
0x140011ad2  mov     r12, [rsp+78h+BugCheckParameter4]
0x140011ada  mov     rsi, [rsp+78h+arg_8]
0x140011ae2  mov     ebp, 1
0x140011ae7  mov     rdi, [rsp+78h+arg_10]
0x140011aef  mov     cs:SkiHibernateAborted, ebp
0x140011af5  xor     ecx, ecx
0x140011af7  xor     eax, eax
0x140011af9  xchg    rax, cs:SkiBarrierWait
0x140011b00  xchg    rcx, cs:SkiMirrorOwner
0x140011b07  xor     ecx, ecx
0x140011b09  call    ShvlNotifyRootCrashdump
0x140011b0e  mov     rcx, [r14+3E8h]; ContextRecord
0x140011b15  call    RtlCaptureContext
0x140011b1a  lea     rcx, [r14+3F0h]
0x140011b21  call    SkiSaveProcessorControlState
0x140011b26  call    SkeFreezeExecution
0x140011b2b  mov     rax, 431BDE82D7B634DBh
0x140011b35  mul     cs:qword_14014EC10
0x140011b3c  shr     rdx, 12h
0x140011b40  imul    rbx, rdx, 1F4h
0x140011b47  cmp     cs:SkeTscInfo, 2
0x140011b4e  jnz     short loc_140011B57
0x140011b50  call    ShvlGetReferenceTime
0x140011b55  jmp     short loc_140011B60
0x140011b57  rdtsc
0x140011b59  shl     rdx, 20h
0x140011b5d  or      rax, rdx
0x140011b60  add     rbx, rax
0x140011b63  cmp     cs:SkeTscInfo, 2
0x140011b6a  jnz     short loc_140011B73
0x140011b6c  call    ShvlGetReferenceTime
0x140011b71  jmp     short loc_140011B7C
0x140011b73  rdtsc
0x140011b75  shl     rdx, 20h
0x140011b79  or      rax, rdx
0x140011b7c  cmp     rax, rbx
0x140011b7f  jnb     short loc_140011B85
0x140011b81  pause
0x140011b83  jmp     short loc_140011B63
0x140011b85  mov     eax, cs:SkhalpEfiFlags
0x140011b8b  mov     ebx, 18Bh
0x140011b90  test    bpl, al
0x140011b93  jz      short loc_140011BD5
0x140011b95  mov     r9d, 4
0x140011b9b  mov     [rsp+78h+var_58], ebp
0x140011b9f  mov     r8d, ebx
0x140011ba2  lea     rdx, BUGCHECK_EFI_GUID
0x140011ba9  lea     rcx, aBugcheckcode; "BugCheckCode"
0x140011bb0  call    SkhalpReportBugCheckProgress
0x140011bb5  mov     r9d, 8
0x140011bbb  mov     [rsp+78h+var_58], ebp
0x140011bbf  mov     r8, r15
0x140011bc2  lea     rdx, BUGCHECK_EFI_GUID
0x140011bc9  lea     rcx, aBugcheckparame; "BugCheckParameter1"
0x140011bd0  call    SkhalpReportBugCheckProgress
0x140011bd5  mov     ecx, 0A0h
0x140011bda  call    SkhalSaveBugCheckProgress
0x140011bdf  mov     cl, bpl
0x140011be2  call    SkSwitchToCrashdumpMode
0x140011be7  mov     rax, cs:qword_14016B5E0
0x140011bee  xor     r14d, r14d
0x140011bf1  test    rax, rax
0x140011bf4  jz      short loc_140011C1C
0x140011bf6  or      [rax+4], ebp
0x140011bf9  lea     rcx, IumCrashCpuContext; ContextRecord
0x140011c00  mov     [rax+8], ebx
0x140011c03  mov     [rax+10h], r15
0x140011c07  mov     [rax+18h], rsi
0x140011c0b  mov     [rax+20h], rdi
0x140011c0f  mov     [rax+28h], r13
0x140011c13  mov     [rax+30h], r12
0x140011c17  call    RtlCaptureContext
0x140011c1c  mov     ecx, ebp
0x140011c1e  call    ShvlNotifyRootCrashdump
0x140011c23  mov     ecx, 0A1h
0x140011c28  call    SkhalSaveBugCheckProgress
0x140011c2d  mov     eax, cs:SkpgInitialized
0x140011c33  test    eax, eax
0x140011c35  jz      short loc_140011C66
0x140011c37  cmp     cs:SkpgContext, r14
0x140011c3e  jz      short loc_140011C66
0x140011c40  mov     eax, ebp
0x140011c42  xchg    eax, cs:SkpgBugCheckActive
0x140011c48  mov     rcx, gs:0
0x140011c51  lock bts dword ptr [rcx+0CCh], 0
0x140011c5a  jb      short loc_140011C66
0x140011c5c  call    SkpgxDefeatureProcessorForBugCheck
0x140011c61  call    ShvlRestrictUserMode
0x140011c66  mov     rdi, gs:0
0x140011c6f  xorps   xmm0, xmm0
0x140011c72  movups  [rsp+78h+var_48], xmm0
0x140011c77  mov     eax, [rdi+84h]
0x140011c7d  bsf     esi, eax
0x140011c80  jz      short loc_140011C93
0x140011c82  lock btr [rdi+84h], esi
0x140011c8a  jnb     short loc_140011C77
0x140011c8c  mov     bpl, byte ptr [rsp+78h+var_48+4]
0x140011c91  jmp     short loc_140011CAC
0x140011c93  mov     rbp, cr8
0x140011c97  mov     eax, 0Fh
0x140011c9c  mov     cr8, rax
0x140011ca0  mov     rdi, gs:0
0x140011ca9  lea     esi, [rax-0Bh]
0x140011cac  mov     ebx, esi
0x140011cae  xor     edx, edx; Val
0x140011cb0  shl     ebx, 0Ch
0x140011cb3  mov     r8d, 0FF8h; Size
0x140011cb9  add     rbx, [rdi+88h]
0x140011cc0  lea     rcx, [rbx+8]; void *
0x140011cc4  call    memset_0
0x140011cc9  mov     eax, 2
0x140011cce  mov     rcx, rbx
0x140011cd1  mov     [rbx], eax
0x140011cd3  mov     [rbx+4], eax
0x140011cd6  call    SkmmGetPhysicalAddress
0x140011cdb  mov     rdx, rax
0x140011cde  mov     [rsp+78h+arg_10], 87h
0x140011cea  mov     rax, cs:HvcallCodeVa
0x140011cf1  xor     r8d, r8d
0x140011cf4  mov     rcx, [rsp+78h+arg_10]
0x140011cfc  call    rax ; HvcallCodeVa
0x140011cfe  nop     dword ptr [rax]
0x140011d01  cmp     esi, 4
0x140011d04  jnb     short loc_140011D10
0x140011d06  lock bts [rdi+84h], esi
0x140011d0e  jmp     short loc_140011D18
0x140011d10  mov     cl, bpl
0x140011d13  call    SkeLowerIrql
0x140011d18  mov     ecx, 0A2h
0x140011d1d  call    SkhalSaveBugCheckProgress
0x140011d22  call    SkiSaveCrashMinidump
0x140011d27  test    byte ptr cs:ShvlpFlags, 1
0x140011d2e  jnz     short loc_140011D35
0x140011d30  call    ShvlInjectVtl0Nmi
0x140011d35  mov     ecx, cs:SkeBugCheckStatus
0x140011d3b  call    SkSwitchToLimitedDispatchLoop
0x140011d41  pause
0x140011d43  jmp     short loc_140011D41
```
