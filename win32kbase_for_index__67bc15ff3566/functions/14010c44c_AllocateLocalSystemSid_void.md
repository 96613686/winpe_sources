# AllocateLocalSystemSid(void * *)

- ea: `0x14010c44c`
- end: `0x14010c6e2`
- name: `?AllocateLocalSystemSid@@YAJPEAPEAX@Z`
- size: `662`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14007c4a0`

## callees

- `0x14000988c`
- `0x14000b798`
- `0x14000c064`
- `0x14007b930`
- `0x14007bbc0`
- `0x14010c44c`
- `0x1401ade20`
- `0x1402388e0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14010c47d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14010c47d`
- `ntoskrnl!ExAllocatePool2` at `0x14010c4b6`
- `ntoskrnl!ExAllocatePool2` at `0x14010c576`
- `ntoskrnl!ExAllocatePool2` at `0x14010c625`
- `ntoskrnl!ExAllocatePool2` at `0x14010c4b6`
- `ntoskrnl!ExAllocatePool2` at `0x14010c576`
- `ntoskrnl!ExAllocatePool2` at `0x14010c625`
- `ntoskrnl!RtlInitializeSid` at `0x14010c4fb`
- `ntoskrnl!RtlInitializeSid` at `0x14010c4fb`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14010c5b2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14010c5b2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c516`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010c516`
- `WIN32K!W32GetUserSessionState` at `0x14010c48b`
- `WIN32K!W32GetUserSessionState` at `0x14010c48b`

## pseudocode

```c
__int64 __fastcall AllocateLocalSystemSid(void **a1)
{
  unsigned __int64 v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdi
  int v7; // eax
  __int64 Pool2; // rbx
  NTSTATUS v9; // edi
  char v11; // r14
  _QWORD *v12; // rax
  unsigned __int64 i; // rbp
  PVOID BackTrace[20]; // [rsp+20h] [rbp-E8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-48h] BYREF

  *a1 = 0;
  v2 = RtlLengthRequiredSid(1u);
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
      if ( v2 < 0x1000 || (v11 = 0, (v2 & 0xFFF) != 0) )
      {
        v11 = 1;
        v2 += 16LL;
      }
      Pool2 = ExAllocatePool2(257, v2, 1702064981);
      if ( !Pool2 )
        return (unsigned int)-1073741801;
      _InterlockedIncrement64((volatile signed __int64 *)(v6 + 128));
      memset(BackTrace, 0, sizeof(BackTrace));
      RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
      if ( v11 && (unsigned __int64)(Pool2 & 0xFFF) + 16 < 0x1000 )
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
  v12 = (_QWORD *)ExAllocatePool2(257, v2 + 16, 1702064981);
  Pool2 = (__int64)v12;
  if ( !v12
    || (_InterlockedIncrement64((volatile signed __int64 *)(v6 + 112)),
        *v12 = 1702064981,
        Pool2 = (__int64)(v12 + 2),
        v12 == (_QWORD *)-16LL) )
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
  v9 = RtlInitializeSid((PSID)Pool2, &IdentifierAuthority, 1u);
  if ( v9 < 0 )
  {
    GreDeleteFastMutex((PVOID)Pool2);
  }
  else
  {
    *RtlSubAuthoritySid((PSID)Pool2, 0) = 18;
    *a1 = (void *)Pool2;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14010c44c  push    rbx
0x14010c44e  push    rbp
0x14010c44f  push    rsi
0x14010c450  push    rdi
0x14010c451  push    r14
0x14010c453  push    r15
0x14010c455  sub     rsp, 0D8h
0x14010c45c  mov     rax, cs:__security_cookie
0x14010c463  xor     rax, rsp
0x14010c466  mov     [rsp+108h+var_40], rax
0x14010c46e  mov     r15, rcx
0x14010c471  mov     qword ptr [rcx], 0
0x14010c478  mov     ecx, 1; SubAuthorityCount
0x14010c47d  call    cs:__imp_RtlLengthRequiredSid
0x14010c484  nop     dword ptr [rax+rax+00h]
0x14010c489  mov     ebx, eax
0x14010c48b  call    cs:__imp_W32GetUserSessionState
0x14010c492  nop     dword ptr [rax+rax+00h]
0x14010c497  lea     rdi, [rax+11950h]
0x14010c49e  mov     eax, [rdi]
0x14010c4a0  test    eax, eax
0x14010c4a2  jnz     loc_14010C5FC
0x14010c4a8  mov     r8d, 65737355h
0x14010c4ae  mov     rdx, rbx
0x14010c4b1  mov     ecx, 101h
0x14010c4b6  call    cs:__imp_ExAllocatePool2
0x14010c4bd  nop     dword ptr [rax+rax+00h]
0x14010c4c2  mov     rbx, rax
0x14010c4c5  test    rax, rax
0x14010c4c8  jz      short loc_14010C4CF
0x14010c4ca  lock inc qword ptr [rdi+70h]
0x14010c4cf  test    rbx, rbx
0x14010c4d2  jz      loc_14010C5F2
0x14010c4d8  mov     r8b, 1; SubAuthorityCount
0x14010c4db  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x14010c4e6  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x14010c4ee  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x14010c4f8  mov     rcx, rbx; Sid
0x14010c4fb  call    cs:__imp_RtlInitializeSid
0x14010c502  nop     dword ptr [rax+rax+00h]
0x14010c507  mov     edi, eax
0x14010c509  mov     rcx, rbx; Buffer
0x14010c50c  test    eax, eax
0x14010c50e  js      loc_14010C6D8
0x14010c514  xor     edx, edx; SubAuthority
0x14010c516  call    cs:__imp_RtlSubAuthoritySid
0x14010c51d  nop     dword ptr [rax+rax+00h]
0x14010c522  mov     dword ptr [rax], 12h
0x14010c528  mov     [r15], rbx
0x14010c52b  mov     eax, edi
0x14010c52d  mov     rcx, [rsp+108h+var_40]
0x14010c535  xor     rcx, rsp; StackCookie
0x14010c538  call    __security_check_cookie
0x14010c53d  add     rsp, 0D8h
0x14010c544  pop     r15
0x14010c546  pop     r14
0x14010c548  pop     rdi
0x14010c549  pop     rsi
0x14010c54a  pop     rbp
0x14010c54b  pop     rbx
0x14010c54c  retn
0x14010c54e  cmp     rbx, 1000h
0x14010c555  jb      loc_14010C6CC
0x14010c55b  xor     r14b, r14b
0x14010c55e  test    rbx, 0FFFh
0x14010c565  jnz     loc_14010C6CC
0x14010c56b  mov     r8d, esi
0x14010c56e  mov     rdx, rbx
0x14010c571  mov     ecx, 101h
0x14010c576  call    cs:__imp_ExAllocatePool2
0x14010c57d  nop     dword ptr [rax+rax+00h]
0x14010c582  mov     rbx, rax
0x14010c585  test    rax, rax
0x14010c588  jz      short loc_14010C5F2
0x14010c58a  lock inc qword ptr [rdi+80h]
0x14010c592  xor     edx, edx; Val
0x14010c594  lea     rcx, [rsp+108h+BackTrace]; void *
0x14010c599  mov     r8d, 0A0h; Size
0x14010c59f  call    memset
0x14010c5a4  xor     r9d, r9d; BackTraceHash
0x14010c5a7  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x14010c5ac  xor     ecx, ecx; FramesToSkip
0x14010c5ae  lea     edx, [r9+14h]; FramesToCapture
0x14010c5b2  call    cs:__imp_RtlCaptureStackBackTrace
0x14010c5b9  nop     dword ptr [rax+rax+00h]
0x14010c5be  test    r14b, r14b
0x14010c5c1  jnz     loc_14010C690
0x14010c5c7  lea     r9, [rsp+108h+BackTrace]
0x14010c5cc  mov     r8, rbp
0x14010c5cf  mov     rdx, rbx
0x14010c5d2  mov     rcx, rdi
0x14010c5d5  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010c5da  test    al, al
0x14010c5dc  jnz     loc_14010C4D8
0x14010c5e2  lock inc qword ptr [rdi+88h]
0x14010c5ea  mov     rcx, rbx; Buffer
0x14010c5ed  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x14010c5f2  mov     edi, 0C0000017h
0x14010c5f7  jmp     loc_14010C52B
0x14010c5fc  cmp     eax, 1
0x14010c5ff  jnz     short loc_14010C65C
0x14010c601  mov     esi, 65737355h
0x14010c606  mov     rcx, rdi; this
0x14010c609  mov     edx, esi; unsigned int
0x14010c60b  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x14010c610  test    al, al
0x14010c612  jz      short loc_14010C5F2
0x14010c614  lea     rdx, [rbx+10h]
0x14010c618  cmp     rdx, rbx
0x14010c61b  jbe     short loc_14010C5F2
0x14010c61d  mov     r8d, esi
0x14010c620  mov     ecx, 101h
0x14010c625  call    cs:__imp_ExAllocatePool2
0x14010c62c  nop     dword ptr [rax+rax+00h]
0x14010c631  mov     rbx, rax
0x14010c634  test    rax, rax
0x14010c637  jz      short loc_14010C64B
0x14010c639  lock inc qword ptr [rdi+70h]
0x14010c63e  mov     [rax], rsi
0x14010c641  add     rbx, 10h
0x14010c645  jnz     loc_14010C4CF
0x14010c64b  mov     rcx, [rdi+8]; this
0x14010c64f  mov     rdx, rsi; void *
0x14010c652  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x14010c657  jmp     loc_14010C4CF
0x14010c65c  cmp     eax, 2
0x14010c65f  jnz     short loc_14010C5F2
0x14010c661  mov     eax, [rdi+50h]
0x14010c664  mov     esi, 65737355h
0x14010c669  and     eax, esi
0x14010c66b  cmp     eax, esi
0x14010c66d  jz      short loc_14010C677
0x14010c66f  mov     r8d, esi
0x14010c672  jmp     loc_14010C4AE
0x14010c677  mov     eax, [rdi+54h]
0x14010c67a  xor     ebp, ebp
0x14010c67c  cmp     rbp, rax
0x14010c67f  jnb     short loc_14010C66F
0x14010c681  cmp     [rdi+rbp*4+30h], esi
0x14010c685  jz      loc_14010C54E
0x14010c68b  inc     rbp
0x14010c68e  jmp     short loc_14010C67C
0x14010c690  mov     rax, rbx
0x14010c693  and     eax, 0FFFh
0x14010c698  add     rax, 10h
0x14010c69c  cmp     rax, 1000h
0x14010c6a2  jnb     loc_14010C5C7
0x14010c6a8  lea     r9, [rsp+108h+BackTrace]
0x14010c6ad  mov     r8, rbp
0x14010c6b0  mov     rdx, rbx
0x14010c6b3  mov     rcx, rdi
0x14010c6b6  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010c6bb  test    al, al
0x14010c6bd  jz      loc_14010C5E2
0x14010c6c3  add     rbx, 10h
0x14010c6c7  jmp     loc_14010C4CF
0x14010c6cc  mov     r14b, 1
0x14010c6cf  add     rbx, 10h
0x14010c6d3  jmp     loc_14010C56B
0x14010c6d8  call    GreDeleteFastMutex
0x14010c6dd  jmp     loc_14010C52B
```
