# AllocateLocalSystemSid(void * *)

- ea: `0x1401051dc`
- end: `0x140105472`
- name: `?AllocateLocalSystemSid@@YAJPEAPEAX@Z`
- size: `662`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14004ac40`

## callees

- `0x140009cfc`
- `0x14000bc78`
- `0x14000c544`
- `0x14004a0d0`
- `0x14004a360`
- `0x1401051dc`
- `0x1401acde0`
- `0x140238160`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14010520d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14010520d`
- `ntoskrnl!ExAllocatePool2` at `0x140105246`
- `ntoskrnl!ExAllocatePool2` at `0x140105306`
- `ntoskrnl!ExAllocatePool2` at `0x1401053b5`
- `ntoskrnl!ExAllocatePool2` at `0x140105246`
- `ntoskrnl!ExAllocatePool2` at `0x140105306`
- `ntoskrnl!ExAllocatePool2` at `0x1401053b5`
- `ntoskrnl!RtlInitializeSid` at `0x14010528b`
- `ntoskrnl!RtlInitializeSid` at `0x14010528b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140105342`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140105342`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401052a6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1401052a6`
- `WIN32K!W32GetUserSessionState` at `0x14010521b`
- `WIN32K!W32GetUserSessionState` at `0x14010521b`

## pseudocode

```c
__int64 __fastcall AllocateLocalSystemSid(void **a1)
{
  unsigned __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  int v5; // eax
  __int64 Pool2; // rbx
  NTSTATUS v7; // edi
  char v9; // r14
  _QWORD *v10; // rax
  unsigned __int64 i; // rbp
  PVOID BackTrace[20]; // [rsp+20h] [rbp-E8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-48h] BYREF

  *a1 = 0;
  v2 = RtlLengthRequiredSid(1u);
  v4 = W32GetUserSessionState(v3) + 72016;
  v5 = *(_DWORD *)v4;
  if ( !*(_DWORD *)v4 )
  {
LABEL_2:
    Pool2 = ExAllocatePool2(257, v2, 1702064981);
    if ( Pool2 )
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 112));
    goto LABEL_4;
  }
  if ( v5 != 1 )
  {
    if ( v5 != 2 )
      return (unsigned int)-1073741801;
    if ( (*(_DWORD *)(v4 + 80) & 0x65737355) == 0x65737355 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *(unsigned int *)(v4 + 84) )
          goto LABEL_2;
        if ( *(_DWORD *)(v4 + 4 * i + 48) == 1702064981 )
          break;
      }
      if ( v2 < 0x1000 || (v9 = 0, (v2 & 0xFFF) != 0) )
      {
        v9 = 1;
        v2 += 16LL;
      }
      Pool2 = ExAllocatePool2(257, v2, 1702064981);
      if ( !Pool2 )
        return (unsigned int)-1073741801;
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 128));
      memset(BackTrace, 0, sizeof(BackTrace));
      RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
      if ( v9 && (unsigned __int64)(Pool2 & 0xFFF) + 16 < 0x1000 )
      {
        if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                v4,
                                Pool2,
                                i,
                                BackTrace) )
        {
          Pool2 += 16;
          goto LABEL_4;
        }
      }
      else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                   v4,
                                   Pool2,
                                   i,
                                   BackTrace) )
      {
        goto LABEL_5;
      }
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 136));
      _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Pool2);
      return (unsigned int)-1073741801;
    }
    goto LABEL_2;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v4,
          0x65737355u)
    || v2 + 16 < v2 )
  {
    return (unsigned int)-1073741801;
  }
  v10 = (_QWORD *)ExAllocatePool2(257, v2 + 16, 1702064981);
  Pool2 = (__int64)v10;
  if ( !v10
    || (_InterlockedIncrement64((volatile signed __int64 *)(v4 + 112)),
        *v10 = 1702064981,
        Pool2 = (__int64)(v10 + 2),
        v10 == (_QWORD *)-16LL) )
  {
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v4 + 8),
      (const void *)0x65737355);
  }
LABEL_4:
  if ( !Pool2 )
    return (unsigned int)-1073741801;
LABEL_5:
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v7 = RtlInitializeSid((PSID)Pool2, &IdentifierAuthority, 1u);
  if ( v7 < 0 )
  {
    GreDeleteFastMutex((PVOID)Pool2);
  }
  else
  {
    *RtlSubAuthoritySid((PSID)Pool2, 0) = 18;
    *a1 = (void *)Pool2;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1401051dc  push    rbx
0x1401051de  push    rbp
0x1401051df  push    rsi
0x1401051e0  push    rdi
0x1401051e1  push    r14
0x1401051e3  push    r15
0x1401051e5  sub     rsp, 0D8h
0x1401051ec  mov     rax, cs:__security_cookie
0x1401051f3  xor     rax, rsp
0x1401051f6  mov     [rsp+108h+var_40], rax
0x1401051fe  mov     r15, rcx
0x140105201  mov     qword ptr [rcx], 0
0x140105208  mov     ecx, 1; SubAuthorityCount
0x14010520d  call    cs:__imp_RtlLengthRequiredSid
0x140105214  nop     dword ptr [rax+rax+00h]
0x140105219  mov     ebx, eax
0x14010521b  call    cs:__imp_W32GetUserSessionState
0x140105222  nop     dword ptr [rax+rax+00h]
0x140105227  lea     rdi, [rax+11950h]
0x14010522e  mov     eax, [rdi]
0x140105230  test    eax, eax
0x140105232  jnz     loc_14010538C
0x140105238  mov     r8d, 65737355h
0x14010523e  mov     rdx, rbx
0x140105241  mov     ecx, 101h
0x140105246  call    cs:__imp_ExAllocatePool2
0x14010524d  nop     dword ptr [rax+rax+00h]
0x140105252  mov     rbx, rax
0x140105255  test    rax, rax
0x140105258  jz      short loc_14010525F
0x14010525a  lock inc qword ptr [rdi+70h]
0x14010525f  test    rbx, rbx
0x140105262  jz      loc_140105382
0x140105268  mov     r8b, 1; SubAuthorityCount
0x14010526b  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x140105276  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x14010527e  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x140105288  mov     rcx, rbx; Sid
0x14010528b  call    cs:__imp_RtlInitializeSid
0x140105292  nop     dword ptr [rax+rax+00h]
0x140105297  mov     edi, eax
0x140105299  mov     rcx, rbx; Buffer
0x14010529c  test    eax, eax
0x14010529e  js      loc_140105468
0x1401052a4  xor     edx, edx; SubAuthority
0x1401052a6  call    cs:__imp_RtlSubAuthoritySid
0x1401052ad  nop     dword ptr [rax+rax+00h]
0x1401052b2  mov     dword ptr [rax], 12h
0x1401052b8  mov     [r15], rbx
0x1401052bb  mov     eax, edi
0x1401052bd  mov     rcx, [rsp+108h+var_40]
0x1401052c5  xor     rcx, rsp; StackCookie
0x1401052c8  call    __security_check_cookie
0x1401052cd  add     rsp, 0D8h
0x1401052d4  pop     r15
0x1401052d6  pop     r14
0x1401052d8  pop     rdi
0x1401052d9  pop     rsi
0x1401052da  pop     rbp
0x1401052db  pop     rbx
0x1401052dc  retn
0x1401052de  cmp     rbx, 1000h
0x1401052e5  jb      loc_14010545C
0x1401052eb  xor     r14b, r14b
0x1401052ee  test    rbx, 0FFFh
0x1401052f5  jnz     loc_14010545C
0x1401052fb  mov     r8d, esi
0x1401052fe  mov     rdx, rbx
0x140105301  mov     ecx, 101h
0x140105306  call    cs:__imp_ExAllocatePool2
0x14010530d  nop     dword ptr [rax+rax+00h]
0x140105312  mov     rbx, rax
0x140105315  test    rax, rax
0x140105318  jz      short loc_140105382
0x14010531a  lock inc qword ptr [rdi+80h]
0x140105322  xor     edx, edx; Val
0x140105324  lea     rcx, [rsp+108h+BackTrace]; void *
0x140105329  mov     r8d, 0A0h; Size
0x14010532f  call    memset
0x140105334  xor     r9d, r9d; BackTraceHash
0x140105337  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x14010533c  xor     ecx, ecx; FramesToSkip
0x14010533e  lea     edx, [r9+14h]; FramesToCapture
0x140105342  call    cs:__imp_RtlCaptureStackBackTrace
0x140105349  nop     dword ptr [rax+rax+00h]
0x14010534e  test    r14b, r14b
0x140105351  jnz     loc_140105420
0x140105357  lea     r9, [rsp+108h+BackTrace]
0x14010535c  mov     r8, rbp
0x14010535f  mov     rdx, rbx
0x140105362  mov     rcx, rdi
0x140105365  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010536a  test    al, al
0x14010536c  jnz     loc_140105268
0x140105372  lock inc qword ptr [rdi+88h]
0x14010537a  mov     rcx, rbx; Buffer
0x14010537d  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x140105382  mov     edi, 0C0000017h
0x140105387  jmp     loc_1401052BB
0x14010538c  cmp     eax, 1
0x14010538f  jnz     short loc_1401053EC
0x140105391  mov     esi, 65737355h
0x140105396  mov     rcx, rdi; this
0x140105399  mov     edx, esi; unsigned int
0x14010539b  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x1401053a0  test    al, al
0x1401053a2  jz      short loc_140105382
0x1401053a4  lea     rdx, [rbx+10h]
0x1401053a8  cmp     rdx, rbx
0x1401053ab  jbe     short loc_140105382
0x1401053ad  mov     r8d, esi
0x1401053b0  mov     ecx, 101h
0x1401053b5  call    cs:__imp_ExAllocatePool2
0x1401053bc  nop     dword ptr [rax+rax+00h]
0x1401053c1  mov     rbx, rax
0x1401053c4  test    rax, rax
0x1401053c7  jz      short loc_1401053DB
0x1401053c9  lock inc qword ptr [rdi+70h]
0x1401053ce  mov     [rax], rsi
0x1401053d1  add     rbx, 10h
0x1401053d5  jnz     loc_14010525F
0x1401053db  mov     rcx, [rdi+8]; this
0x1401053df  mov     rdx, rsi; void *
0x1401053e2  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x1401053e7  jmp     loc_14010525F
0x1401053ec  cmp     eax, 2
0x1401053ef  jnz     short loc_140105382
0x1401053f1  mov     eax, [rdi+50h]
0x1401053f4  mov     esi, 65737355h
0x1401053f9  and     eax, esi
0x1401053fb  cmp     eax, esi
0x1401053fd  jz      short loc_140105407
0x1401053ff  mov     r8d, esi
0x140105402  jmp     loc_14010523E
0x140105407  mov     eax, [rdi+54h]
0x14010540a  xor     ebp, ebp
0x14010540c  cmp     rbp, rax
0x14010540f  jnb     short loc_1401053FF
0x140105411  cmp     [rdi+rbp*4+30h], esi
0x140105415  jz      loc_1401052DE
0x14010541b  inc     rbp
0x14010541e  jmp     short loc_14010540C
0x140105420  mov     rax, rbx
0x140105423  and     eax, 0FFFh
0x140105428  add     rax, 10h
0x14010542c  cmp     rax, 1000h
0x140105432  jnb     loc_140105357
0x140105438  lea     r9, [rsp+108h+BackTrace]
0x14010543d  mov     r8, rbp
0x140105440  mov     rdx, rbx
0x140105443  mov     rcx, rdi
0x140105446  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010544b  test    al, al
0x14010544d  jz      loc_140105372
0x140105453  add     rbx, 10h
0x140105457  jmp     loc_14010525F
0x14010545c  mov     r14b, 1
0x14010545f  add     rbx, 10h
0x140105463  jmp     loc_1401052FB
0x140105468  call    GreDeleteFastMutex
0x14010546d  jmp     loc_1401052BB
```
