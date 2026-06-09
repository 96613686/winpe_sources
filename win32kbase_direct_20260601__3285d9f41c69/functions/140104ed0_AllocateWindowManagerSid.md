# AllocateWindowManagerSid

- ea: `0x140104ed0`
- end: `0x1401051b3`
- name: `AllocateWindowManagerSid`
- size: `739`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14004ac40`
- `0x140104e60`

## callees

- `0x140009cfc`
- `0x14000bc78`
- `0x14000c544`
- `0x14004a0d0`
- `0x14004a360`
- `0x140104ed0`
- `0x1401acde0`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140104fc6`
- `ntoskrnl!PsGetCurrentProcess` at `0x140104fc6`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140104fd5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140104fd5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140104f01`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140104f01`
- `ntoskrnl!ExAllocatePool2` at `0x140104f3a`
- `ntoskrnl!ExAllocatePool2` at `0x140105047`
- `ntoskrnl!ExAllocatePool2` at `0x1401050f6`
- `ntoskrnl!ExAllocatePool2` at `0x140104f3a`
- `ntoskrnl!ExAllocatePool2` at `0x140105047`
- `ntoskrnl!ExAllocatePool2` at `0x1401050f6`
- `ntoskrnl!RtlInitializeSid` at `0x140104f7f`
- `ntoskrnl!RtlInitializeSid` at `0x140104f7f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140105083`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140105083`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104f9a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104fb4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104feb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104f9a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104fb4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140104feb`
- `WIN32K!W32GetUserSessionState` at `0x140104f0f`
- `WIN32K!W32GetUserSessionState` at `0x140104f0f`

## pseudocode

```c
__int64 __fastcall AllocateWindowManagerSid(__int64 *a1)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rbx
  int v7; // eax
  __int64 Pool2; // rdi
  NTSTATUS v9; // esi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 CurrentProcess; // rax
  ULONG ProcessSessionId; // ebx
  char v16; // r14
  _QWORD *v17; // rax
  unsigned __int64 i; // rbp
  PVOID BackTrace[20]; // [rsp+20h] [rbp-E8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-48h] BYREF

  *a1 = 0;
  v2 = RtlLengthRequiredSid(3u);
  v6 = W32GetUserSessionState(v4, v3, v5) + 72016;
  v7 = *(_DWORD *)v6;
  if ( !*(_DWORD *)v6 )
  {
LABEL_2:
    Pool2 = ExAllocatePool2(257, v2, 1702064981);
    if ( Pool2 )
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 112));
    goto LABEL_4;
  }
  if ( v7 != 1 )
  {
    if ( v7 != 2 )
      return (unsigned int)-1073741801;
    if ( (*(_DWORD *)(v6 + 80) & 0x65737355) == 0x65737355 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *(unsigned int *)(v6 + 84) )
          goto LABEL_2;
        if ( *(_DWORD *)(v6 + 4 * i + 48) == 1702064981 )
          break;
      }
      if ( v2 < 0x1000 || (v16 = 0, (v2 & 0xFFF) != 0) )
      {
        v16 = 1;
        v2 += 16LL;
      }
      Pool2 = ExAllocatePool2(257, v2, 1702064981);
      if ( !Pool2 )
        return (unsigned int)-1073741801;
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 128));
      memset(BackTrace, 0, sizeof(BackTrace));
      RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
      if ( v16 && (unsigned __int64)(Pool2 & 0xFFF) + 16 < 0x1000 )
      {
        if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                v6,
                                Pool2,
                                i,
                                BackTrace) )
        {
          Pool2 += 16;
          goto LABEL_4;
        }
      }
      else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                   v6,
                                   Pool2,
                                   i,
                                   BackTrace) )
      {
        goto LABEL_5;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 136));
      _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Pool2);
      return (unsigned int)-1073741801;
    }
    goto LABEL_2;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v6,
          0x65737355u)
    || v2 + 16 < v2 )
  {
    return (unsigned int)-1073741801;
  }
  v17 = (_QWORD *)ExAllocatePool2(257, v2 + 16, 1702064981);
  Pool2 = (__int64)v17;
  if ( !v17
    || (_InterlockedIncrement64((volatile signed __int64 *)(v6 + 112)),
        *v17 = 1702064981,
        Pool2 = (__int64)(v17 + 2),
        v17 == (_QWORD *)-16LL) )
  {
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v6 + 8),
      (const void *)0x65737355);
  }
LABEL_4:
  if ( !Pool2 )
    return (unsigned int)-1073741801;
LABEL_5:
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v9 = RtlInitializeSid((PSID)Pool2, &IdentifierAuthority, 3u);
  if ( v9 < 0 )
  {
    GreDeleteFastMutex((PVOID)Pool2);
  }
  else
  {
    *RtlSubAuthoritySid((PSID)Pool2, 0) = 90;
    *RtlSubAuthoritySid((PSID)Pool2, 1u) = 0;
    CurrentProcess = PsGetCurrentProcess(v11, v10, v12);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    *RtlSubAuthoritySid((PSID)Pool2, 2u) = ProcessSessionId;
    *a1 = Pool2;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140104ed0  push    rbx
0x140104ed2  push    rbp
0x140104ed3  push    rsi
0x140104ed4  push    rdi
0x140104ed5  push    r14
0x140104ed7  push    r15
0x140104ed9  sub     rsp, 0D8h
0x140104ee0  mov     rax, cs:__security_cookie
0x140104ee7  xor     rax, rsp
0x140104eea  mov     [rsp+108h+var_40], rax
0x140104ef2  mov     r15, rcx
0x140104ef5  mov     qword ptr [rcx], 0
0x140104efc  mov     ecx, 3; SubAuthorityCount
0x140104f01  call    cs:__imp_RtlLengthRequiredSid
0x140104f08  nop     dword ptr [rax+rax+00h]
0x140104f0d  mov     edi, eax
0x140104f0f  call    cs:__imp_W32GetUserSessionState
0x140104f16  nop     dword ptr [rax+rax+00h]
0x140104f1b  lea     rbx, [rax+11950h]
0x140104f22  mov     eax, [rbx]
0x140104f24  test    eax, eax
0x140104f26  jnz     loc_1401050CD
0x140104f2c  mov     r8d, 65737355h
0x140104f32  mov     rdx, rdi
0x140104f35  mov     ecx, 101h
0x140104f3a  call    cs:__imp_ExAllocatePool2
0x140104f41  nop     dword ptr [rax+rax+00h]
0x140104f46  mov     rdi, rax
0x140104f49  test    rax, rax
0x140104f4c  jz      short loc_140104F53
0x140104f4e  lock inc qword ptr [rbx+70h]
0x140104f53  test    rdi, rdi
0x140104f56  jz      loc_1401050C3
0x140104f5c  mov     r8b, 3; SubAuthorityCount
0x140104f5f  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x140104f6a  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x140104f72  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x140104f7c  mov     rcx, rdi; Sid
0x140104f7f  call    cs:__imp_RtlInitializeSid
0x140104f86  nop     dword ptr [rax+rax+00h]
0x140104f8b  mov     esi, eax
0x140104f8d  mov     rcx, rdi; Buffer
0x140104f90  test    eax, eax
0x140104f92  js      loc_1401051A9
0x140104f98  xor     edx, edx; SubAuthority
0x140104f9a  call    cs:__imp_RtlSubAuthoritySid
0x140104fa1  nop     dword ptr [rax+rax+00h]
0x140104fa6  mov     edx, 1; SubAuthority
0x140104fab  mov     rcx, rdi; Sid
0x140104fae  mov     dword ptr [rax], 5Ah ; 'Z'
0x140104fb4  call    cs:__imp_RtlSubAuthoritySid
0x140104fbb  nop     dword ptr [rax+rax+00h]
0x140104fc0  mov     dword ptr [rax], 0
0x140104fc6  call    cs:__imp_PsGetCurrentProcess
0x140104fcd  nop     dword ptr [rax+rax+00h]
0x140104fd2  mov     rcx, rax
0x140104fd5  call    cs:__imp_PsGetProcessSessionIdEx
0x140104fdc  nop     dword ptr [rax+rax+00h]
0x140104fe1  mov     edx, 2; SubAuthority
0x140104fe6  mov     rcx, rdi; Sid
0x140104fe9  mov     ebx, eax
0x140104feb  call    cs:__imp_RtlSubAuthoritySid
0x140104ff2  nop     dword ptr [rax+rax+00h]
0x140104ff7  mov     [rax], ebx
0x140104ff9  mov     [r15], rdi
0x140104ffc  mov     eax, esi
0x140104ffe  mov     rcx, [rsp+108h+var_40]
0x140105006  xor     rcx, rsp; StackCookie
0x140105009  call    __security_check_cookie
0x14010500e  add     rsp, 0D8h
0x140105015  pop     r15
0x140105017  pop     r14
0x140105019  pop     rdi
0x14010501a  pop     rsi
0x14010501b  pop     rbp
0x14010501c  pop     rbx
0x14010501d  retn
0x14010501f  cmp     rdi, 1000h
0x140105026  jb      loc_14010519D
0x14010502c  xor     r14b, r14b
0x14010502f  test    rdi, 0FFFh
0x140105036  jnz     loc_14010519D
0x14010503c  mov     r8d, esi
0x14010503f  mov     rdx, rdi
0x140105042  mov     ecx, 101h
0x140105047  call    cs:__imp_ExAllocatePool2
0x14010504e  nop     dword ptr [rax+rax+00h]
0x140105053  mov     rdi, rax
0x140105056  test    rax, rax
0x140105059  jz      short loc_1401050C3
0x14010505b  lock inc qword ptr [rbx+80h]
0x140105063  xor     edx, edx; Val
0x140105065  lea     rcx, [rsp+108h+BackTrace]; void *
0x14010506a  mov     r8d, 0A0h; Size
0x140105070  call    memset
0x140105075  xor     r9d, r9d; BackTraceHash
0x140105078  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x14010507d  xor     ecx, ecx; FramesToSkip
0x14010507f  lea     edx, [r9+14h]; FramesToCapture
0x140105083  call    cs:__imp_RtlCaptureStackBackTrace
0x14010508a  nop     dword ptr [rax+rax+00h]
0x14010508f  test    r14b, r14b
0x140105092  jnz     loc_140105161
0x140105098  lea     r9, [rsp+108h+BackTrace]
0x14010509d  mov     r8, rbp
0x1401050a0  mov     rdx, rdi
0x1401050a3  mov     rcx, rbx
0x1401050a6  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x1401050ab  test    al, al
0x1401050ad  jnz     loc_140104F5C
0x1401050b3  lock inc qword ptr [rbx+88h]
0x1401050bb  mov     rcx, rdi; Buffer
0x1401050be  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x1401050c3  mov     esi, 0C0000017h
0x1401050c8  jmp     loc_140104FFC
0x1401050cd  cmp     eax, 1
0x1401050d0  jnz     short loc_14010512D
0x1401050d2  mov     esi, 65737355h
0x1401050d7  mov     rcx, rbx; this
0x1401050da  mov     edx, esi; unsigned int
0x1401050dc  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x1401050e1  test    al, al
0x1401050e3  jz      short loc_1401050C3
0x1401050e5  lea     rdx, [rdi+10h]
0x1401050e9  cmp     rdx, rdi
0x1401050ec  jbe     short loc_1401050C3
0x1401050ee  mov     r8d, esi
0x1401050f1  mov     ecx, 101h
0x1401050f6  call    cs:__imp_ExAllocatePool2
0x1401050fd  nop     dword ptr [rax+rax+00h]
0x140105102  mov     rdi, rax
0x140105105  test    rax, rax
0x140105108  jz      short loc_14010511C
0x14010510a  lock inc qword ptr [rbx+70h]
0x14010510f  mov     [rax], rsi
0x140105112  add     rdi, 10h
0x140105116  jnz     loc_140104F53
0x14010511c  mov     rcx, [rbx+8]; this
0x140105120  mov     rdx, rsi; void *
0x140105123  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x140105128  jmp     loc_140104F53
0x14010512d  cmp     eax, 2
0x140105130  jnz     short loc_1401050C3
0x140105132  mov     eax, [rbx+50h]
0x140105135  mov     esi, 65737355h
0x14010513a  and     eax, esi
0x14010513c  cmp     eax, esi
0x14010513e  jz      short loc_140105148
0x140105140  mov     r8d, esi
0x140105143  jmp     loc_140104F32
0x140105148  mov     eax, [rbx+54h]
0x14010514b  xor     ebp, ebp
0x14010514d  cmp     rbp, rax
0x140105150  jnb     short loc_140105140
0x140105152  cmp     [rbx+rbp*4+30h], esi
0x140105156  jz      loc_14010501F
0x14010515c  inc     rbp
0x14010515f  jmp     short loc_14010514D
0x140105161  mov     rax, rdi
0x140105164  and     eax, 0FFFh
0x140105169  add     rax, 10h
0x14010516d  cmp     rax, 1000h
0x140105173  jnb     loc_140105098
0x140105179  lea     r9, [rsp+108h+BackTrace]
0x14010517e  mov     r8, rbp
0x140105181  mov     rdx, rdi
0x140105184  mov     rcx, rbx
0x140105187  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010518c  test    al, al
0x14010518e  jz      loc_1401050B3
0x140105194  add     rdi, 10h
0x140105198  jmp     loc_140104F53
0x14010519d  mov     r14b, 1
0x1401051a0  add     rdi, 10h
0x1401051a4  jmp     loc_14010503C
0x1401051a9  call    GreDeleteFastMutex
0x1401051ae  jmp     loc_140104FFC
```
