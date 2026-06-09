# AllocateWindowManagerSid

- ea: `0x140109660`
- end: `0x140109943`
- name: `AllocateWindowManagerSid`
- size: `739`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140041d30`
- `0x1401095f0`

## callees

- `0x1400411c0`
- `0x140041450`
- `0x14008e14c`
- `0x1400900c8`
- `0x140090964`
- `0x140109660`
- `0x1401ad340`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140109756`
- `ntoskrnl!PsGetCurrentProcess` at `0x140109756`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140109765`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140109765`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140109691`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140109691`
- `ntoskrnl!ExAllocatePool2` at `0x1401096ca`
- `ntoskrnl!ExAllocatePool2` at `0x1401097d7`
- `ntoskrnl!ExAllocatePool2` at `0x140109886`
- `ntoskrnl!ExAllocatePool2` at `0x1401096ca`
- `ntoskrnl!ExAllocatePool2` at `0x1401097d7`
- `ntoskrnl!ExAllocatePool2` at `0x140109886`
- `ntoskrnl!RtlInitializeSid` at `0x14010970f`
- `ntoskrnl!RtlInitializeSid` at `0x14010970f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140109813`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140109813`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010972a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140109744`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010977b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010972a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140109744`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14010977b`
- `WIN32K!W32GetUserSessionState` at `0x14010969f`
- `WIN32K!W32GetUserSessionState` at `0x14010969f`

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
0x140109660  push    rbx
0x140109662  push    rbp
0x140109663  push    rsi
0x140109664  push    rdi
0x140109665  push    r14
0x140109667  push    r15
0x140109669  sub     rsp, 0D8h
0x140109670  mov     rax, cs:__security_cookie
0x140109677  xor     rax, rsp
0x14010967a  mov     [rsp+108h+var_40], rax
0x140109682  mov     r15, rcx
0x140109685  mov     qword ptr [rcx], 0
0x14010968c  mov     ecx, 3; SubAuthorityCount
0x140109691  call    cs:__imp_RtlLengthRequiredSid
0x140109698  nop     dword ptr [rax+rax+00h]
0x14010969d  mov     edi, eax
0x14010969f  call    cs:__imp_W32GetUserSessionState
0x1401096a6  nop     dword ptr [rax+rax+00h]
0x1401096ab  lea     rbx, [rax+11950h]
0x1401096b2  mov     eax, [rbx]
0x1401096b4  test    eax, eax
0x1401096b6  jnz     loc_14010985D
0x1401096bc  mov     r8d, 65737355h
0x1401096c2  mov     rdx, rdi
0x1401096c5  mov     ecx, 101h
0x1401096ca  call    cs:__imp_ExAllocatePool2
0x1401096d1  nop     dword ptr [rax+rax+00h]
0x1401096d6  mov     rdi, rax
0x1401096d9  test    rax, rax
0x1401096dc  jz      short loc_1401096E3
0x1401096de  lock inc qword ptr [rbx+70h]
0x1401096e3  test    rdi, rdi
0x1401096e6  jz      loc_140109853
0x1401096ec  mov     r8b, 3; SubAuthorityCount
0x1401096ef  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x1401096fa  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x140109702  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x14010970c  mov     rcx, rdi; Sid
0x14010970f  call    cs:__imp_RtlInitializeSid
0x140109716  nop     dword ptr [rax+rax+00h]
0x14010971b  mov     esi, eax
0x14010971d  mov     rcx, rdi; Buffer
0x140109720  test    eax, eax
0x140109722  js      loc_140109939
0x140109728  xor     edx, edx; SubAuthority
0x14010972a  call    cs:__imp_RtlSubAuthoritySid
0x140109731  nop     dword ptr [rax+rax+00h]
0x140109736  mov     edx, 1; SubAuthority
0x14010973b  mov     rcx, rdi; Sid
0x14010973e  mov     dword ptr [rax], 5Ah ; 'Z'
0x140109744  call    cs:__imp_RtlSubAuthoritySid
0x14010974b  nop     dword ptr [rax+rax+00h]
0x140109750  mov     dword ptr [rax], 0
0x140109756  call    cs:__imp_PsGetCurrentProcess
0x14010975d  nop     dword ptr [rax+rax+00h]
0x140109762  mov     rcx, rax
0x140109765  call    cs:__imp_PsGetProcessSessionIdEx
0x14010976c  nop     dword ptr [rax+rax+00h]
0x140109771  mov     edx, 2; SubAuthority
0x140109776  mov     rcx, rdi; Sid
0x140109779  mov     ebx, eax
0x14010977b  call    cs:__imp_RtlSubAuthoritySid
0x140109782  nop     dword ptr [rax+rax+00h]
0x140109787  mov     [rax], ebx
0x140109789  mov     [r15], rdi
0x14010978c  mov     eax, esi
0x14010978e  mov     rcx, [rsp+108h+var_40]
0x140109796  xor     rcx, rsp; StackCookie
0x140109799  call    __security_check_cookie
0x14010979e  add     rsp, 0D8h
0x1401097a5  pop     r15
0x1401097a7  pop     r14
0x1401097a9  pop     rdi
0x1401097aa  pop     rsi
0x1401097ab  pop     rbp
0x1401097ac  pop     rbx
0x1401097ad  retn
0x1401097af  cmp     rdi, 1000h
0x1401097b6  jb      loc_14010992D
0x1401097bc  xor     r14b, r14b
0x1401097bf  test    rdi, 0FFFh
0x1401097c6  jnz     loc_14010992D
0x1401097cc  mov     r8d, esi
0x1401097cf  mov     rdx, rdi
0x1401097d2  mov     ecx, 101h
0x1401097d7  call    cs:__imp_ExAllocatePool2
0x1401097de  nop     dword ptr [rax+rax+00h]
0x1401097e3  mov     rdi, rax
0x1401097e6  test    rax, rax
0x1401097e9  jz      short loc_140109853
0x1401097eb  lock inc qword ptr [rbx+80h]
0x1401097f3  xor     edx, edx; Val
0x1401097f5  lea     rcx, [rsp+108h+BackTrace]; void *
0x1401097fa  mov     r8d, 0A0h; Size
0x140109800  call    memset
0x140109805  xor     r9d, r9d; BackTraceHash
0x140109808  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x14010980d  xor     ecx, ecx; FramesToSkip
0x14010980f  lea     edx, [r9+14h]; FramesToCapture
0x140109813  call    cs:__imp_RtlCaptureStackBackTrace
0x14010981a  nop     dword ptr [rax+rax+00h]
0x14010981f  test    r14b, r14b
0x140109822  jnz     loc_1401098F1
0x140109828  lea     r9, [rsp+108h+BackTrace]
0x14010982d  mov     r8, rbp
0x140109830  mov     rdx, rdi
0x140109833  mov     rcx, rbx
0x140109836  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010983b  test    al, al
0x14010983d  jnz     loc_1401096EC
0x140109843  lock inc qword ptr [rbx+88h]
0x14010984b  mov     rcx, rdi; Buffer
0x14010984e  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x140109853  mov     esi, 0C0000017h
0x140109858  jmp     loc_14010978C
0x14010985d  cmp     eax, 1
0x140109860  jnz     short loc_1401098BD
0x140109862  mov     esi, 65737355h
0x140109867  mov     rcx, rbx; this
0x14010986a  mov     edx, esi; unsigned int
0x14010986c  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x140109871  test    al, al
0x140109873  jz      short loc_140109853
0x140109875  lea     rdx, [rdi+10h]
0x140109879  cmp     rdx, rdi
0x14010987c  jbe     short loc_140109853
0x14010987e  mov     r8d, esi
0x140109881  mov     ecx, 101h
0x140109886  call    cs:__imp_ExAllocatePool2
0x14010988d  nop     dword ptr [rax+rax+00h]
0x140109892  mov     rdi, rax
0x140109895  test    rax, rax
0x140109898  jz      short loc_1401098AC
0x14010989a  lock inc qword ptr [rbx+70h]
0x14010989f  mov     [rax], rsi
0x1401098a2  add     rdi, 10h
0x1401098a6  jnz     loc_1401096E3
0x1401098ac  mov     rcx, [rbx+8]; this
0x1401098b0  mov     rdx, rsi; void *
0x1401098b3  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x1401098b8  jmp     loc_1401096E3
0x1401098bd  cmp     eax, 2
0x1401098c0  jnz     short loc_140109853
0x1401098c2  mov     eax, [rbx+50h]
0x1401098c5  mov     esi, 65737355h
0x1401098ca  and     eax, esi
0x1401098cc  cmp     eax, esi
0x1401098ce  jz      short loc_1401098D8
0x1401098d0  mov     r8d, esi
0x1401098d3  jmp     loc_1401096C2
0x1401098d8  mov     eax, [rbx+54h]
0x1401098db  xor     ebp, ebp
0x1401098dd  cmp     rbp, rax
0x1401098e0  jnb     short loc_1401098D0
0x1401098e2  cmp     [rbx+rbp*4+30h], esi
0x1401098e6  jz      loc_1401097AF
0x1401098ec  inc     rbp
0x1401098ef  jmp     short loc_1401098DD
0x1401098f1  mov     rax, rdi
0x1401098f4  and     eax, 0FFFh
0x1401098f9  add     rax, 10h
0x1401098fd  cmp     rax, 1000h
0x140109903  jnb     loc_140109828
0x140109909  lea     r9, [rsp+108h+BackTrace]
0x14010990e  mov     r8, rbp
0x140109911  mov     rdx, rdi
0x140109914  mov     rcx, rbx
0x140109917  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x14010991c  test    al, al
0x14010991e  jz      loc_140109843
0x140109924  add     rdi, 10h
0x140109928  jmp     loc_1401096E3
0x14010992d  mov     r14b, 1
0x140109930  add     rdi, 10h
0x140109934  jmp     loc_1401097CC
0x140109939  call    GreDeleteFastMutex
0x14010993e  jmp     loc_14010978C
```
