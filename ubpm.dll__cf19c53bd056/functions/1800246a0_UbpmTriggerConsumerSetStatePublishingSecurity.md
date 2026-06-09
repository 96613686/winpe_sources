# UbpmTriggerConsumerSetStatePublishingSecurity

- ea: `0x1800246a0`
- end: `0x180024a7a`
- name: `UbpmTriggerConsumerSetStatePublishingSecurity`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x18001e9f4`
- `0x1800246a0`
- `0x180024a80`
- `0x180032dd8`
- `0x18003d7d2`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800248c4`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800248c4`
- `ntdll!RtlFreeHeap` at `0x180024a00`
- `ntdll!RtlFreeHeap` at `0x180024a00`
- `ntdll!RtlNtStatusToDosError` at `0x180024a30`
- `ntdll!RtlNtStatusToDosError` at `0x180024a30`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024753`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180024753`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800247ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002485b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024907`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800249e8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800247ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002485b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180024907`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800249e8`
- `ntdll!NtDeleteWnfStateName` at `0x180024a12`
- `ntdll!NtDeleteWnfStateName` at `0x180024a12`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800246ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800247e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800246ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800247e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024759`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180024700`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800247fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180024700`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800247fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024835`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002477b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002477b`

## pseudocode

```c
__int64 __fastcall UbpmTriggerConsumerSetStatePublishingSecurity(struct _WNF_STATE_NAME *a1, const void **a2)
{
  DWORD v4; // ebx
  unsigned int v5; // ebp
  const void *v6; // rcx
  SIZE_T v7; // rbx
  DWORD v8; // ebx
  void *v10; // rax
  void *v11; // r15
  DWORD LastError; // eax
  NTSTATUS v13; // eax
  char v14; // al
  _BYTE TlsValue[144]; // [rsp+30h] [rbp-C8h] BYREF

  memset_0(TlsValue, 0, 0x88u);
  v4 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v4, TlsValue);
  }
  if ( a2 && a2[1] && *(_DWORD *)a2 )
  {
    v5 = 0;
    RtlAcquireSRWLockExclusive(&a1[26]);
    a1[27].Data[0] = GetCurrentThreadId();
    v6 = (const void *)a1[44];
    if ( v6 )
    {
      v7 = *(unsigned int *)a2;
      if ( RtlCompareMemory(v6, a2[1], v7) == v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
            *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL));
LABEL_13:
        a1[27].Data[0] = 0;
        RtlReleaseSRWLockExclusive(&a1[26]);
        goto LABEL_14;
      }
    }
    v10 = UbpmAlloc(*(unsigned int *)a2);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
          LastError);
      goto LABEL_13;
    }
    memcpy_0(v10, a2[1], *(unsigned int *)a2);
    if ( IsValidSecurityDescriptor(v11) )
    {
      if ( UbpmUtilsIsStateNameAllocated(a1 + 42) )
      {
        v13 = NtDeleteWnfStateName(&a1[42]);
        if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = RtlNtStatusToDosError(v13);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
            *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
            v14);
        }
        a1[42] = 0;
        a1[43].Data[0] = 0;
      }
      UBPM_MIDL_user_free(*(_QWORD *)&a1[44]);
      a1[44] = (struct _WNF_STATE_NAME)v11;
      a1[27].Data[0] = 0;
      RtlReleaseSRWLockExclusive(&a1[26]);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL));
    }
    else
    {
      v5 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
          *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
          87);
      a1[27].Data[0] = 0;
      RtlReleaseSRWLockExclusive(&a1[26]);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    }
  }
  else
  {
    v5 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
        *(_QWORD *)(*(_QWORD *)&a1[3] + 8LL),
        87);
  }
LABEL_14:
  v8 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v8, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x1800246a0  mov     r11, rsp
0x1800246a3  push    rbx
0x1800246a4  sub     rsp, 0F0h
0x1800246ab  mov     rax, cs:__security_cookie
0x1800246b2  xor     rax, rsp
0x1800246b5  mov     [rsp+0F8h+var_38], rax
0x1800246bd  mov     [r11+20h], rsi
0x1800246c1  mov     r8d, 88h; Size
0x1800246c7  mov     [r11-20h], r14
0x1800246cb  mov     rsi, rdx
0x1800246ce  mov     r14, rcx
0x1800246d1  xor     edx, edx; Val
0x1800246d3  lea     rcx, [rsp+0F8h+TlsValue]; void *
0x1800246d8  call    memset_0
0x1800246dd  mov     ebx, cs:UbpmpLockTrackerId
0x1800246e3  cmp     ebx, 0FFFFFFFFh
0x1800246e6  jz      short loc_180024706
0x1800246e8  mov     ecx, ebx; dwTlsIndex
0x1800246ea  call    cs:__imp_TlsGetValue
0x1800246f0  test    rax, rax
0x1800246f3  jnz     loc_180024979
0x1800246f9  lea     rdx, [rsp+0F8h+TlsValue]; lpTlsValue
0x1800246fe  mov     ecx, ebx; dwTlsIndex
0x180024700  call    cs:__imp_TlsSetValue
0x180024706  mov     [rsp+0F8h+arg_10], rbp
0x18002470e  mov     [rsp+0F8h+var_10], rdi
0x180024716  mov     [rsp+0F8h+var_18], r12
0x18002471e  mov     [rsp+0F8h+var_28], r15
0x180024726  test    rsi, rsi
0x180024729  jz      loc_180024866
0x18002472f  cmp     qword ptr [rsi+8], 0
0x180024734  jz      loc_180024866
0x18002473a  cmp     dword ptr [rsi], 0
0x18002473d  jz      loc_180024866
0x180024743  lea     rdi, [r14+0D0h]
0x18002474a  xor     r12d, r12d
0x18002474d  mov     rcx, rdi
0x180024750  mov     ebp, r12d
0x180024753  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180024759  call    cs:__imp_GetCurrentThreadId
0x18002475f  mov     [rdi+8], eax
0x180024762  mov     rcx, [r14+160h]; Source1
0x180024769  test    rcx, rcx
0x18002476c  jz      loc_180024826
0x180024772  mov     ebx, [rsi]
0x180024774  mov     rdx, [rsi+8]; Source2
0x180024778  mov     r8d, ebx; Length
0x18002477b  call    cs:__imp_RtlCompareMemory
0x180024781  cmp     rax, rbx
0x180024784  jnz     loc_180024826
0x18002478a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024791  lea     rbx, WPP_GLOBAL_Control
0x180024798  cmp     rcx, rbx
0x18002479b  jz      short loc_1800247A7
0x18002479d  test    byte ptr [rcx+1Ch], 4
0x1800247a1  jnz     loc_180024980
0x1800247a7  mov     rcx, rdi
0x1800247aa  mov     [rdi+8], r12d
0x1800247ae  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800247b4  mov     ebx, cs:UbpmpLockTrackerId
0x1800247ba  mov     r15, [rsp+0F8h+var_28]
0x1800247c2  mov     r14, [rsp+0F8h+var_20]
0x1800247ca  mov     r12, [rsp+0F8h+var_18]
0x1800247d2  mov     rdi, [rsp+0F8h+var_10]
0x1800247da  mov     rsi, [rsp+0F8h+arg_18]
0x1800247e2  cmp     ebx, 0FFFFFFFFh
0x1800247e5  jz      short loc_180024803
0x1800247e7  mov     ecx, ebx; dwTlsIndex
0x1800247e9  call    cs:__imp_TlsGetValue
0x1800247ef  cmp     qword ptr [rax], 0
0x1800247f3  jnz     loc_180024A73
0x1800247f9  xor     edx, edx; lpTlsValue
0x1800247fb  mov     ecx, ebx; dwTlsIndex
0x1800247fd  call    cs:__imp_TlsSetValue
0x180024803  mov     eax, ebp
0x180024805  mov     rbp, [rsp+0F8h+arg_10]
0x18002480d  mov     rcx, [rsp+0F8h+var_38]
0x180024815  xor     rcx, rsp; StackCookie
0x180024818  call    __security_check_cookie
0x18002481d  add     rsp, 0F0h
0x180024824  pop     rbx
0x180024825  retn
0x180024826  mov     ecx, [rsi]; Size
0x180024828  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002482d  mov     r15, rax
0x180024830  test    rax, rax
0x180024833  jnz     short loc_1800248B2
0x180024835  call    cs:__imp_GetLastError
0x18002483b  mov     ebp, eax
0x18002483d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024844  lea     rbx, WPP_GLOBAL_Control
0x18002484b  cmp     rcx, rbx
0x18002484e  jnz     loc_180024949
0x180024854  mov     rcx, rdi
0x180024857  mov     [rdi+8], r12d
0x18002485b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180024861  jmp     loc_1800247B4
0x180024866  mov     ebp, 57h ; 'W'
0x18002486b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024872  lea     rbx, WPP_GLOBAL_Control
0x180024879  cmp     rcx, rbx
0x18002487c  jz      loc_1800247B4
0x180024882  test    byte ptr [rcx+1Ch], 1
0x180024886  jz      loc_1800247B4
0x18002488c  mov     r9, [r14+18h]
0x180024890  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180024897  mov     rcx, [rcx+10h]
0x18002489b  mov     edx, 13h
0x1800248a0  mov     [rsp+0F8h+var_D8], ebp
0x1800248a4  mov     r9, [r9+8]
0x1800248a8  call    WPP_SF_Sd
0x1800248ad  jmp     loc_1800247B4
0x1800248b2  mov     r8d, [rsi]; Size
0x1800248b5  mov     rcx, r15; void *
0x1800248b8  mov     rdx, [rsi+8]; Src
0x1800248bc  call    memcpy_0
0x1800248c1  mov     rcx, r15; pSecurityDescriptor
0x1800248c4  call    cs:__imp_IsValidSecurityDescriptor
0x1800248ca  test    eax, eax
0x1800248cc  jz      loc_1800249A2
0x1800248d2  lea     rcx, [r14+150h]; struct _WNF_STATE_NAME *
0x1800248d9  call    ?UbpmUtilsIsStateNameAllocated@@YAEPEAU_WNF_STATE_NAME@@@Z; UbpmUtilsIsStateNameAllocated(_WNF_STATE_NAME *)
0x1800248de  lea     rbx, WPP_GLOBAL_Control
0x1800248e5  test    al, al
0x1800248e7  jnz     loc_180024A0B
0x1800248ed  mov     rcx, [r14+160h]
0x1800248f4  call    UBPM_MIDL_user_free
0x1800248f9  mov     [r14+160h], r15
0x180024900  mov     rcx, rdi
0x180024903  mov     [rdi+8], r12d
0x180024907  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002490d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024914  cmp     rcx, rbx
0x180024917  jz      loc_1800247B4
0x18002491d  test    byte ptr [rcx+1Ch], 4
0x180024921  jz      loc_1800247B4
0x180024927  mov     r9, [r14+18h]
0x18002492b  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180024932  mov     rcx, [rcx+10h]
0x180024936  mov     edx, 18h
0x18002493b  mov     r9, [r9+8]
0x18002493f  call    WPP_SF_S
0x180024944  jmp     loc_1800247B4
0x180024949  test    byte ptr [rcx+1Ch], 1
0x18002494d  jz      loc_180024854
0x180024953  mov     r9, [r14+18h]
0x180024957  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002495e  mov     rcx, [rcx+10h]
0x180024962  mov     edx, 15h
0x180024967  mov     [rsp+0F8h+var_D8], eax
0x18002496b  mov     r9, [r9+8]
0x18002496f  call    WPP_SF_Sd
0x180024974  jmp     loc_180024854
0x180024979  int     2Ch; Windows NT - assertion failure
0x18002497b  jmp     loc_1800246F9
0x180024980  mov     r9, [r14+18h]
0x180024984  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x18002498b  mov     rcx, [rcx+10h]
0x18002498f  mov     edx, 14h
0x180024994  mov     r9, [r9+8]
0x180024998  call    WPP_SF_S
0x18002499d  jmp     loc_1800247A7
0x1800249a2  mov     ebp, 57h ; 'W'
0x1800249a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ae  lea     rbx, WPP_GLOBAL_Control
0x1800249b5  cmp     rcx, rbx
0x1800249b8  jz      short loc_1800249E1
0x1800249ba  test    byte ptr [rcx+1Ch], 1
0x1800249be  jz      short loc_1800249E1
0x1800249c0  mov     r9, [r14+18h]
0x1800249c4  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x1800249cb  mov     rcx, [rcx+10h]
0x1800249cf  mov     edx, 16h
0x1800249d4  mov     [rsp+0F8h+var_D8], ebp
0x1800249d8  mov     r9, [r9+8]
0x1800249dc  call    WPP_SF_Sd
0x1800249e1  mov     rcx, rdi
0x1800249e4  mov     [rdi+8], r12d
0x1800249e8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800249ee  mov     rcx, gs:60h
0x1800249f7  mov     r8, r15; P
0x1800249fa  xor     edx, edx; Flags
0x1800249fc  mov     rcx, [rcx+30h]; HeapHandle
0x180024a00  call    cs:__imp_RtlFreeHeap
0x180024a06  jmp     loc_1800247B4
0x180024a0b  lea     rcx, [r14+150h]
0x180024a12  call    cs:__imp_NtDeleteWnfStateName
0x180024a18  test    eax, eax
0x180024a1a  jns     short loc_180024A5E
0x180024a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a23  cmp     rcx, rbx
0x180024a26  jz      short loc_180024A5E
0x180024a28  test    byte ptr [rcx+1Ch], 1
0x180024a2c  jz      short loc_180024A5E
0x180024a2e  mov     ecx, eax; Status
0x180024a30  call    cs:__imp_RtlNtStatusToDosError
0x180024a36  mov     r9, [r14+18h]
0x180024a3a  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180024a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a48  mov     edx, 17h
0x180024a4d  mov     [rsp+0F8h+var_D8], eax
0x180024a51  mov     r9, [r9+8]
0x180024a55  mov     rcx, [rcx+10h]
0x180024a59  call    WPP_SF_Sd
0x180024a5e  xor     eax, eax
0x180024a60  mov     [r14+150h], rax
0x180024a67  mov     [r14+158h], r12d
0x180024a6e  jmp     loc_1800248ED
0x180024a73  int     2Ch; Windows NT - assertion failure
0x180024a75  jmp     loc_1800247F9
```
