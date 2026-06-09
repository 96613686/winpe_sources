# UbpmpStartStatePublishing

- ea: `0x1800371e0`
- end: `0x1800373ba`
- name: `UbpmpStartStatePublishing`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180034f80`

## callees

- `0x180003790`
- `0x18000fbf0`
- `0x1800103c0`
- `0x1800150c0`
- `0x18001af64`
- `0x180026230`
- `0x1800371e0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x1800372ff`
- `ntdll!NtCreateWnfStateName` at `0x1800372ff`
- `ntdll!RtlNtStatusToDosError` at `0x180037311`
- `ntdll!RtlNtStatusToDosError` at `0x180037311`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037363`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037391`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037363`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037254`

## pseudocode

```c
__int64 __fastcall UbpmpStartStatePublishing(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  _QWORD *v6; // rsi
  ULONG LastError; // ebx
  _QWORD *v8; // rcx
  int v9; // edx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  NTSTATUS WnfStateName; // eax

  if ( !a2 )
  {
    v6 = 0;
    LastError = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 70;
LABEL_5:
      WPP_SF_Sd(
        v8[2],
        v9,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        LastError);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  v6 = UbpmAlloc(8u);
  if ( v6 )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 208));
    if ( !UbpmUtilsIsStateNameAllocated((struct _WNF_STATE_NAME *)(a1 + 336)) )
    {
      if ( !*(_QWORD *)(a1 + 352) )
      {
        LastError = 5;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_20;
        v12 = 72;
LABEL_19:
        WPP_SF_Sd(
          v11[2],
          v12,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
          LastError);
LABEL_20:
        *(_DWORD *)(a1 + 216) = 0;
        RtlReleaseSRWLockExclusive(a1 + 208);
        goto LABEL_23;
      }
      WnfStateName = NtCreateWnfStateName(v10, 3, 0, 0, 0, 4, *(_QWORD *)(a1 + 352));
      if ( WnfStateName < 0 )
      {
        LastError = RtlNtStatusToDosError(WnfStateName);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_20;
        v12 = 73;
        goto LABEL_19;
      }
      *(_DWORD *)(a1 + 344) = 0;
      UbpmTriggerConsumerPublishStateChange(a1);
    }
    LastError = 0;
    *v6 = *(_QWORD *)(a1 + 336);
    *(_DWORD *)(a1 + 216) = 0;
    RtlReleaseSRWLockExclusive(a1 + 208);
    *a2 = v6;
    v6 = 0;
    goto LABEL_23;
  }
  LastError = GetLastError();
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 71;
    goto LABEL_5;
  }
LABEL_23:
  UBPM_MIDL_user_free(v6, a2, a3, a4);
  return LastError;
}

```

## disassembly

```asm
0x1800371e0  push    rbx
0x1800371e2  push    rbp
0x1800371e3  push    rsi
0x1800371e4  push    rdi
0x1800371e5  push    r14
0x1800371e7  push    r15
0x1800371e9  sub     rsp, 48h
0x1800371ed  mov     r14, rdx
0x1800371f0  mov     rdi, rcx
0x1800371f3  test    rdx, rdx
0x1800371f6  jnz     short loc_180037242
0x1800371f8  xor     esi, esi
0x1800371fa  lea     ebx, [rdx+57h]
0x1800371fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180037204  lea     rax, WPP_GLOBAL_Control
0x18003720b  cmp     rcx, rax
0x18003720e  jz      loc_1800373A2
0x180037214  test    byte ptr [rcx+1Ch], 1
0x180037218  jz      loc_1800373A2
0x18003721e  lea     edx, [rsi+46h]
0x180037221  mov     r9, [rdi+18h]
0x180037225  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18003722c  mov     rcx, [rcx+10h]
0x180037230  mov     dword ptr [rsp+78h+var_58], ebx
0x180037234  mov     r9, [r9+8]
0x180037238  call    WPP_SF_Sd
0x18003723d  jmp     loc_1800373A2
0x180037242  mov     ecx, 8; Size
0x180037247  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18003724c  mov     rsi, rax
0x18003724f  test    rax, rax
0x180037252  jnz     short loc_180037288
0x180037254  call    cs:__imp_GetLastError
0x18003725b  nop     dword ptr [rax+rax+00h]
0x180037260  mov     ebx, eax
0x180037262  mov     rcx, cs:WPP_GLOBAL_Control
0x180037269  lea     rax, WPP_GLOBAL_Control
0x180037270  cmp     rcx, rax
0x180037273  jz      loc_1800373A2
0x180037279  test    byte ptr [rcx+1Ch], 1
0x18003727d  jz      loc_1800373A2
0x180037283  lea     edx, [rsi+47h]
0x180037286  jmp     short loc_180037221
0x180037288  lea     rbp, [rdi+0D0h]
0x18003728f  mov     rcx, rbp; struct _UBPM_SRWLOCK *
0x180037292  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180037297  lea     r15, [rdi+150h]
0x18003729e  mov     rcx, r15; struct _WNF_STATE_NAME *
0x1800372a1  call    ?UbpmUtilsIsStateNameAllocated@@YAEPEAU_WNF_STATE_NAME@@@Z; UbpmUtilsIsStateNameAllocated(_WNF_STATE_NAME *)
0x1800372a6  test    al, al
0x1800372a8  jnz     loc_180037383
0x1800372ae  mov     rax, [rdi+160h]
0x1800372b5  test    rax, rax
0x1800372b8  jnz     short loc_1800372DF
0x1800372ba  lea     ebx, [rax+5]
0x1800372bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372c4  lea     rax, WPP_GLOBAL_Control
0x1800372cb  cmp     rcx, rax
0x1800372ce  jz      loc_180037359
0x1800372d4  test    byte ptr [rcx+1Ch], 1
0x1800372d8  jz      short loc_180037359
0x1800372da  lea     edx, [rbx+43h]
0x1800372dd  jmp     short loc_18003733D
0x1800372df  mov     [rsp+78h+var_48], rax
0x1800372e4  xor     r9d, r9d
0x1800372e7  mov     [rsp+78h+var_50], 4
0x1800372ef  xor     r8d, r8d
0x1800372f2  mov     [rsp+78h+var_58], 0
0x1800372fb  lea     edx, [r9+3]
0x1800372ff  call    cs:__imp_NtCreateWnfStateName
0x180037306  nop     dword ptr [rax+rax+00h]
0x18003730b  test    eax, eax
0x18003730d  jns     short loc_180037371
0x18003730f  mov     ecx, eax; Status
0x180037311  call    cs:__imp_RtlNtStatusToDosError
0x180037318  nop     dword ptr [rax+rax+00h]
0x18003731d  mov     ebx, eax
0x18003731f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037326  lea     rax, WPP_GLOBAL_Control
0x18003732d  cmp     rcx, rax
0x180037330  jz      short loc_180037359
0x180037332  test    byte ptr [rcx+1Ch], 1
0x180037336  jz      short loc_180037359
0x180037338  mov     edx, 49h ; 'I'
0x18003733d  mov     r9, [rdi+18h]
0x180037341  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180037348  mov     rcx, [rcx+10h]
0x18003734c  mov     dword ptr [rsp+78h+var_58], ebx
0x180037350  mov     r9, [r9+8]
0x180037354  call    WPP_SF_Sd
0x180037359  mov     rcx, rbp
0x18003735c  mov     dword ptr [rbp+8], 0
0x180037363  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003736a  nop     dword ptr [rax+rax+00h]
0x18003736f  jmp     short loc_1800373A2
0x180037371  mov     rcx, rdi
0x180037374  mov     dword ptr [rdi+158h], 0
0x18003737e  call    UbpmTriggerConsumerPublishStateChange
0x180037383  mov     rax, [r15]
0x180037386  xor     ebx, ebx
0x180037388  mov     [rsi], rax
0x18003738b  mov     rcx, rbp
0x18003738e  mov     [rbp+8], ebx
0x180037391  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180037398  nop     dword ptr [rax+rax+00h]
0x18003739d  mov     [r14], rsi
0x1800373a0  xor     esi, esi
0x1800373a2  mov     rcx, rsi
0x1800373a5  call    UBPM_MIDL_user_free
0x1800373aa  mov     eax, ebx
0x1800373ac  add     rsp, 48h
0x1800373b0  pop     r15
0x1800373b2  pop     r14
0x1800373b4  pop     rdi
0x1800373b5  pop     rsi
0x1800373b6  pop     rbp
0x1800373b7  pop     rbx
0x1800373b8  retn
```
