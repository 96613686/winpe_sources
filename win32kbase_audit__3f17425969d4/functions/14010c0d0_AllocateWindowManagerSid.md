# AllocateWindowManagerSid

- ea: `0x14010c0d0`
- end: `0x14010c3b3`
- name: `AllocateWindowManagerSid`
- size: `739`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x14007c4a0`
- `0x14010c060`

## callees

- `0x14000988c`
- `0x14000b798`
- `0x14000c064`
- `0x14007b930`
- `0x14007bbc0`
- `0x14010c0d0`
- `0x1401ade20`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14010c1c6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010c1c6`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010c1d5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14010c1d5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14010c101`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14010c101`
- `ntoskrnl!ExAllocatePool2` at `0x14010c13a`
- `ntoskrnl!ExAllocatePool2` at `0x14010c247`
- `ntoskrnl!ExAllocatePool2` at `0x14010c2f6`
- `ntoskrnl!ExAllocatePool2` at `0x14010c13a`
- `ntoskrnl!ExAllocatePool2` at `0x14010c247`
- `ntoskrnl!ExAllocatePool2` at `0x14010c2f6`
- `ntoskrnl!RtlInitializeSid` at `0x14010c17f`
- `ntoskrnl!RtlInitializeSid` at `0x14010c17f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14010c283`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14010c283`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c19a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c1b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c1eb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c19a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c1b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c1eb`
- `WIN32K!W32GetUserSessionState` at `0x14010c10f`
- `WIN32K!W32GetUserSessionState` at `0x14010c10f`

## pseudocode

```c
__int64 __fastcall AllocateWindowManagerSid(__int64 *a1)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rbx
  int v6; // eax
  __int64 Pool2; // rdi
  __int64 v8; // rdx
  NTSTATUS v9; // esi
  __int64 v10; // rcx
  __int64 CurrentProcess; // rax
  ULONG ProcessSessionId; // ebx
  char v14; // r14
  _QWORD *v15; // rax
  unsigned __int64 i; // rbp
  PVOID BackTrace[20]; // [rsp+20h] [rbp-E8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-48h] BYREF

  *a1 = 0;
  v2 = RtlLengthRequiredSid(3u);
  v5 = W32GetUserSessionState(v4, v3) + 72016;
  v6 = *(_DWORD *)v5;
  if ( !*(_DWORD *)v5 )
  {
LABEL_2:
    Pool2 = ExAllocatePool2(257, v2, 1702064981);
    if ( Pool2 )
      _InterlockedIncrement64((volatile signed __int64 *)(v5 + 112));
    goto LABEL_4;
  }
  if ( v6 != 1 )
  {
    if ( v6 != 2 )
      return (unsigned int)-1073741801;
    if ( (*(_DWORD *)(v5 + 80) & 0x65737355) == 0x65737355 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *(unsigned int *)(v5 + 84) )
          goto LABEL_2;
        if ( *(_DWORD *)(v5 + 4 * i + 48) == 1702064981 )
          break;
      }
      if ( v2 < 0x1000 || (v14 = 0, (v2 & 0xFFF) != 0) )
      {
        v14 = 1;
        v2 += 16LL;
      }
      Pool2 = ExAllocatePool2(257, v2, 1702064981);
      if ( !Pool2 )
        return (unsigned int)-1073741801;
      _InterlockedIncrement64((volatile signed __int64 *)(v5 + 128));
      memset(BackTrace, 0, sizeof(BackTrace));
      RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
      if ( v14 && (unsigned __int64)(Pool2 & 0xFFF) + 16 < 0x1000 )
      {
        if ( NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
               v5,
               (const void *)Pool2,
               i,
               (NSInstrumentation::CBackTrace *)BackTrace) )
        {
          Pool2 += 16;
          goto LABEL_4;
        }
      }
      else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                   v5,
                                   Pool2,
                                   i,
                                   BackTrace) )
      {
        goto LABEL_5;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v5 + 136));
      _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Pool2);
      return (unsigned int)-1073741801;
    }
    goto LABEL_2;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v5,
          0x65737355u)
    || v2 + 16 < v2 )
  {
    return (unsigned int)-1073741801;
  }
  v15 = (_QWORD *)ExAllocatePool2(257, v2 + 16, 1702064981);
  Pool2 = (__int64)v15;
  if ( !v15
    || (_InterlockedIncrement64((volatile signed __int64 *)(v5 + 112)),
        *v15 = 1702064981,
        Pool2 = (__int64)(v15 + 2),
        v15 == (_QWORD *)-16LL) )
  {
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v5 + 8),
      0x65737355u);
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
    GreDeleteFastMutex((_DWORD *)Pool2, v8);
  }
  else
  {
    *RtlSubAuthoritySid((PSID)Pool2, 0) = 90;
    *RtlSubAuthoritySid((PSID)Pool2, 1u) = 0;
    CurrentProcess = PsGetCurrentProcess(v10);
    ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess);
    *RtlSubAuthoritySid((PSID)Pool2, 2u) = ProcessSessionId;
    *a1 = Pool2;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14010c0d0  push    rbx
0x14010c0d2  push    rbp
0x14010c0d3  push    rsi
0x14010c0d4  push    rdi
0x14010c0d5  push    r14
0x14010c0d7  push    r15
0x14010c0d9  sub     rsp, 0D8h
0x14010c0e0  mov     rax, cs:__security_cookie
0x14010c0e7  xor     rax, rsp
0x14010c0ea  mov     [rsp+108h+var_40], rax
0x14010c0f2  mov     r15, rcx
0x14010c0f5  mov     qword ptr [rcx], 0
0x14010c0fc  mov     ecx, 3; SubAuthorityCount
0x14010c101  call    cs:__imp_RtlLengthRequiredSid
0x14010c108  nop     dword ptr [rax+rax+00h]
0x14010c10d  mov     edi, eax
0x14010c10f  call    cs:__imp_W32GetUserSessionState
0x14010c116  nop     dword ptr [rax+rax+00h]
0x14010c11b  lea     rbx, [rax+11950h]
0x14010c122  mov     eax, [rbx]
0x14010c124  test    eax, eax
0x14010c126  jnz     loc_14010C2CD
0x14010c12c  mov     r8d, 65737355h
0x14010c132  mov     rdx, rdi
0x14010c135  mov     ecx, 101h
0x14010c13a  call    cs:__imp_ExAllocatePool2
0x14010c141  nop     dword ptr [rax+rax+00h]
0x14010c146  mov     rdi, rax
0x14010c149  test    rax, rax
0x14010c14c  jz      short loc_14010C153
0x14010c14e  lock inc qword ptr [rbx+70h]
0x14010c153  test    rdi, rdi
0x14010c156  jz      loc_14010C2C3
0x14010c15c  mov     r8b, 3; SubAuthorityCount
0x14010c15f  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x14010c16a  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x14010c172  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x14010c17c  mov     rcx, rdi; Sid
0x14010c17f  call    cs:__imp_RtlInitializeSid
0x14010c186  nop     dword ptr [rax+rax+00h]
0x14010c18b  mov     esi, eax
0x14010c18d  mov     rcx, rdi; Buffer
0x14010c190  test    eax, eax
0x14010c192  js      loc_14010C3A9
0x14010c198  xor     edx, edx; SubAuthority
0x14010c19a  call    cs:__imp_RtlSubAuthoritySid
0x14010c1a1  nop     dword ptr [rax+rax+00h]
0x14010c1a6  mov     edx, 1; SubAuthority
0x14010c1ab  mov     rcx, rdi; Sid
0x14010c1ae  mov     dword ptr [rax], 5Ah ; 'Z'
0x14010c1b4  call    cs:__imp_RtlSubAuthoritySid
0x14010c1bb  nop     dword ptr [rax+rax+00h]
0x14010c1c0  mov     dword ptr [rax], 0
0x14010c1c6  call    cs:__imp_PsGetCurrentProcess
0x14010c1cd  nop     dword ptr [rax+rax+00h]
0x14010c1d2  mov     rcx, rax
0x14010c1d5  call    cs:__imp_PsGetProcessSessionIdEx
0x14010c1dc  nop     dword ptr [rax+rax+00h]
0x14010c1e1  mov     edx, 2; SubAuthority
0x14010c1e6  mov     rcx, rdi; Sid
0x14010c1e9  mov     ebx, eax
0x14010c1eb  call    cs:__imp_RtlSubAuthoritySid
0x14010c1f2  nop     dword ptr [rax+rax+00h]
0x14010c1f7  mov     [rax], ebx
0x14010c1f9  mov     [r15], rdi
0x14010c1fc  mov     eax, esi
0x14010c1fe  mov     rcx, [rsp+108h+var_40]
0x14010c206  xor     rcx, rsp; StackCookie
0x14010c209  call    __security_check_cookie
0x14010c20e  add     rsp, 0D8h
0x14010c215  pop     r15
0x14010c217  pop     r14
0x14010c219  pop     rdi
0x14010c21a  pop     rsi
0x14010c21b  pop     rbp
0x14010c21c  pop     rbx
0x14010c21d  retn
0x14010c21f  cmp     rdi, 1000h
0x14010c226  jb      loc_14010C39D
0x14010c22c  xor     r14b, r14b
0x14010c22f  test    rdi, 0FFFh
0x14010c236  jnz     loc_14010C39D
0x14010c23c  mov     r8d, esi
0x14010c23f  mov     rdx, rdi
0x14010c242  mov     ecx, 101h
0x14010c247  call    cs:__imp_ExAllocatePool2
0x14010c24e  nop     dword ptr [rax+rax+00h]
0x14010c253  mov     rdi, rax
0x14010c256  test    rax, rax
0x14010c259  jz      short loc_14010C2C3
0x14010c25b  lock inc qword ptr [rbx+80h]
0x14010c263  xor     edx, edx; Val
0x14010c265  lea     rcx, [rsp+108h+BackTrace]; void *
0x14010c26a  mov     r8d, 0A0h; Size
0x14010c270  call    memset
0x14010c275  xor     r9d, r9d; BackTraceHash
0x14010c278  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x14010c27d  xor     ecx, ecx; FramesToSkip
0x14010c27f  lea     edx, [r9+14h]; FramesToCapture
0x14010c283  call    cs:__imp_RtlCaptureStackBackTrace
0x14010c28a  nop     dword ptr [rax+rax+00h]
0x14010c28f  test    r14b, r14b
0x14010c292  jnz     loc_14010C361
0x14010c298  lea     r9, [rsp+108h+BackTrace]
0x14010c29d  mov     r8, rbp
0x14010c2a0  mov     rdx, rdi
0x14010c2a3  mov     rcx, rbx
0x14010c2a6  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010c2ab  test    al, al
0x14010c2ad  jnz     loc_14010C15C
0x14010c2b3  lock inc qword ptr [rbx+88h]
0x14010c2bb  mov     rcx, rdi; Buffer
0x14010c2be  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x14010c2c3  mov     esi, 0C0000017h
0x14010c2c8  jmp     loc_14010C1FC
0x14010c2cd  cmp     eax, 1
0x14010c2d0  jnz     short loc_14010C32D
0x14010c2d2  mov     esi, 65737355h
0x14010c2d7  mov     rcx, rbx; this
0x14010c2da  mov     edx, esi; unsigned int
0x14010c2dc  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x14010c2e1  test    al, al
0x14010c2e3  jz      short loc_14010C2C3
0x14010c2e5  lea     rdx, [rdi+10h]
0x14010c2e9  cmp     rdx, rdi
0x14010c2ec  jbe     short loc_14010C2C3
0x14010c2ee  mov     r8d, esi
0x14010c2f1  mov     ecx, 101h
0x14010c2f6  call    cs:__imp_ExAllocatePool2
0x14010c2fd  nop     dword ptr [rax+rax+00h]
0x14010c302  mov     rdi, rax
0x14010c305  test    rax, rax
0x14010c308  jz      short loc_14010C31C
0x14010c30a  lock inc qword ptr [rbx+70h]
0x14010c30f  mov     [rax], rsi
0x14010c312  add     rdi, 10h
0x14010c316  jnz     loc_14010C153
0x14010c31c  mov     rcx, [rbx+8]; this
0x14010c320  mov     rdx, rsi; void *
0x14010c323  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x14010c328  jmp     loc_14010C153
0x14010c32d  cmp     eax, 2
0x14010c330  jnz     short loc_14010C2C3
0x14010c332  mov     eax, [rbx+50h]
0x14010c335  mov     esi, 65737355h
0x14010c33a  and     eax, esi
0x14010c33c  cmp     eax, esi
0x14010c33e  jz      short loc_14010C348
0x14010c340  mov     r8d, esi
0x14010c343  jmp     loc_14010C132
0x14010c348  mov     eax, [rbx+54h]
0x14010c34b  xor     ebp, ebp
0x14010c34d  cmp     rbp, rax
0x14010c350  jnb     short loc_14010C340
0x14010c352  cmp     [rbx+rbp*4+30h], esi
0x14010c356  jz      loc_14010C21F
0x14010c35c  inc     rbp
0x14010c35f  jmp     short loc_14010C34D
0x14010c361  mov     rax, rdi
0x14010c364  and     eax, 0FFFh
0x14010c369  add     rax, 10h
0x14010c36d  cmp     rax, 1000h
0x14010c373  jnb     loc_14010C298
0x14010c379  lea     r9, [rsp+108h+BackTrace]
0x14010c37e  mov     r8, rbp
0x14010c381  mov     rdx, rdi
0x14010c384  mov     rcx, rbx
0x14010c387  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010c38c  test    al, al
0x14010c38e  jz      loc_14010C2B3
0x14010c394  add     rdi, 10h
0x14010c398  jmp     loc_14010C153
0x14010c39d  mov     r14b, 1
0x14010c3a0  add     rdi, 10h
0x14010c3a4  jmp     loc_14010C23C
0x14010c3a9  call    GreDeleteFastMutex
0x14010c3ae  jmp     loc_14010C1FC
```
