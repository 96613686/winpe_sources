# UbpmpStartStatePublishing

- ea: `0x180034d04`
- end: `0x180034ebb`
- name: `UbpmpStartStatePublishing`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180032bf0`

## callees

- `0x180004e10`
- `0x18000a6e0`
- `0x18000f9a0`
- `0x180019d90`
- `0x18001e9f4`
- `0x180024a80`
- `0x180034d04`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x180034e19`
- `ntdll!NtCreateWnfStateName` at `0x180034e19`
- `ntdll!RtlNtStatusToDosError` at `0x180034e25`
- `ntdll!RtlNtStatusToDosError` at `0x180034e25`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180034e71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180034e99`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180034e71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180034e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d78`

## pseudocode

```c
__int64 __fastcall UbpmpStartStatePublishing(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rsi
  ULONG LastError; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  int v10; // edx
  NTSTATUS WnfStateName; // eax

  if ( !a2 )
  {
    v4 = 0;
    LastError = 87;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 70;
LABEL_5:
      WPP_SF_Sd(
        v6[2],
        v7,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        LastError);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  v4 = UbpmAlloc(8u);
  if ( v4 )
  {
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(a1 + 208));
    if ( !UbpmUtilsIsStateNameAllocated((struct _WNF_STATE_NAME *)(a1 + 336)) )
    {
      if ( !*(_QWORD *)(a1 + 352) )
      {
        LastError = 5;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_20;
        v10 = 72;
LABEL_19:
        WPP_SF_Sd(
          v9[2],
          v10,
          (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
          LastError);
LABEL_20:
        *(_DWORD *)(a1 + 216) = 0;
        RtlReleaseSRWLockExclusive(a1 + 208);
        goto LABEL_23;
      }
      WnfStateName = NtCreateWnfStateName(v8, 3, 0, 0, 0, 4, *(_QWORD *)(a1 + 352));
      if ( WnfStateName < 0 )
      {
        LastError = RtlNtStatusToDosError(WnfStateName);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_20;
        v10 = 73;
        goto LABEL_19;
      }
      *(_DWORD *)(a1 + 344) = 0;
      UbpmTriggerConsumerPublishStateChange(a1);
    }
    LastError = 0;
    *v4 = *(_QWORD *)(a1 + 336);
    *(_DWORD *)(a1 + 216) = 0;
    RtlReleaseSRWLockExclusive(a1 + 208);
    *a2 = v4;
    v4 = 0;
    goto LABEL_23;
  }
  LastError = GetLastError();
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 71;
    goto LABEL_5;
  }
LABEL_23:
  UBPM_MIDL_user_free(v4);
  return LastError;
}

```

## disassembly

```asm
0x180034d04  push    rbx
0x180034d06  push    rbp
0x180034d07  push    rsi
0x180034d08  push    rdi
0x180034d09  push    r14
0x180034d0b  push    r15
0x180034d0d  sub     rsp, 48h
0x180034d11  mov     r14, rdx
0x180034d14  mov     rdi, rcx
0x180034d17  test    rdx, rdx
0x180034d1a  jnz     short loc_180034D66
0x180034d1c  xor     esi, esi
0x180034d1e  lea     ebx, [rdx+57h]
0x180034d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d28  lea     rax, WPP_GLOBAL_Control
0x180034d2f  cmp     rcx, rax
0x180034d32  jz      loc_180034EA4
0x180034d38  test    byte ptr [rcx+1Ch], 1
0x180034d3c  jz      loc_180034EA4
0x180034d42  lea     edx, [rsi+46h]
0x180034d45  mov     r9, [rdi+18h]
0x180034d49  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180034d50  mov     rcx, [rcx+10h]
0x180034d54  mov     dword ptr [rsp+78h+var_58], ebx
0x180034d58  mov     r9, [r9+8]
0x180034d5c  call    WPP_SF_Sd
0x180034d61  jmp     loc_180034EA4
0x180034d66  mov     ecx, 8; Size
0x180034d6b  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180034d70  mov     rsi, rax
0x180034d73  test    rax, rax
0x180034d76  jnz     short loc_180034DA6
0x180034d78  call    cs:__imp_GetLastError
0x180034d7e  mov     ebx, eax
0x180034d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d87  lea     rax, WPP_GLOBAL_Control
0x180034d8e  cmp     rcx, rax
0x180034d91  jz      loc_180034EA4
0x180034d97  test    byte ptr [rcx+1Ch], 1
0x180034d9b  jz      loc_180034EA4
0x180034da1  lea     edx, [rsi+47h]
0x180034da4  jmp     short loc_180034D45
0x180034da6  lea     rbp, [rdi+0D0h]
0x180034dad  mov     rcx, rbp; struct _UBPM_SRWLOCK *
0x180034db0  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180034db5  lea     r15, [rdi+150h]
0x180034dbc  mov     rcx, r15; struct _WNF_STATE_NAME *
0x180034dbf  call    ?UbpmUtilsIsStateNameAllocated@@YAEPEAU_WNF_STATE_NAME@@@Z; UbpmUtilsIsStateNameAllocated(_WNF_STATE_NAME *)
0x180034dc4  test    al, al
0x180034dc6  jnz     loc_180034E8B
0x180034dcc  mov     rax, [rdi+160h]
0x180034dd3  test    rax, rax
0x180034dd6  jnz     short loc_180034DF9
0x180034dd8  lea     ebx, [rax+5]
0x180034ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180034de2  lea     rax, WPP_GLOBAL_Control
0x180034de9  cmp     rcx, rax
0x180034dec  jz      short loc_180034E67
0x180034dee  test    byte ptr [rcx+1Ch], 1
0x180034df2  jz      short loc_180034E67
0x180034df4  lea     edx, [rbx+43h]
0x180034df7  jmp     short loc_180034E4B
0x180034df9  mov     [rsp+78h+var_48], rax
0x180034dfe  xor     r9d, r9d
0x180034e01  mov     [rsp+78h+var_50], 4
0x180034e09  xor     r8d, r8d
0x180034e0c  mov     [rsp+78h+var_58], 0
0x180034e15  lea     edx, [r9+3]
0x180034e19  call    cs:__imp_NtCreateWnfStateName
0x180034e1f  test    eax, eax
0x180034e21  jns     short loc_180034E79
0x180034e23  mov     ecx, eax; Status
0x180034e25  call    cs:__imp_RtlNtStatusToDosError
0x180034e2b  mov     ebx, eax
0x180034e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e34  lea     rax, WPP_GLOBAL_Control
0x180034e3b  cmp     rcx, rax
0x180034e3e  jz      short loc_180034E67
0x180034e40  test    byte ptr [rcx+1Ch], 1
0x180034e44  jz      short loc_180034E67
0x180034e46  mov     edx, 49h ; 'I'
0x180034e4b  mov     r9, [rdi+18h]
0x180034e4f  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180034e56  mov     rcx, [rcx+10h]
0x180034e5a  mov     dword ptr [rsp+78h+var_58], ebx
0x180034e5e  mov     r9, [r9+8]
0x180034e62  call    WPP_SF_Sd
0x180034e67  mov     rcx, rbp
0x180034e6a  mov     dword ptr [rbp+8], 0
0x180034e71  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180034e77  jmp     short loc_180034EA4
0x180034e79  mov     rcx, rdi
0x180034e7c  mov     dword ptr [rdi+158h], 0
0x180034e86  call    UbpmTriggerConsumerPublishStateChange
0x180034e8b  mov     rax, [r15]
0x180034e8e  xor     ebx, ebx
0x180034e90  mov     [rsi], rax
0x180034e93  mov     rcx, rbp
0x180034e96  mov     [rbp+8], ebx
0x180034e99  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180034e9f  mov     [r14], rsi
0x180034ea2  xor     esi, esi
0x180034ea4  mov     rcx, rsi
0x180034ea7  call    UBPM_MIDL_user_free
0x180034eac  mov     eax, ebx
0x180034eae  add     rsp, 48h
0x180034eb2  pop     r15
0x180034eb4  pop     r14
0x180034eb6  pop     rdi
0x180034eb7  pop     rsi
0x180034eb8  pop     rbp
0x180034eb9  pop     rbx
0x180034eba  retn
```
