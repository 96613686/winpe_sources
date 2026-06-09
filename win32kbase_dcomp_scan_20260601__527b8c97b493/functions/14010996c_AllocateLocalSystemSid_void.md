# AllocateLocalSystemSid(void * *)

- ea: `0x14010996c`
- end: `0x140109c02`
- name: `?AllocateLocalSystemSid@@YAJPEAPEAX@Z`
- size: `662`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140041d30`

## callees

- `0x1400411c0`
- `0x140041450`
- `0x14008e14c`
- `0x1400900c8`
- `0x140090964`
- `0x14010996c`
- `0x1401ad340`
- `0x140238b10`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14010999d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14010999d`
- `ntoskrnl!ExAllocatePool2` at `0x1401099d6`
- `ntoskrnl!ExAllocatePool2` at `0x140109a96`
- `ntoskrnl!ExAllocatePool2` at `0x140109b45`
- `ntoskrnl!ExAllocatePool2` at `0x1401099d6`
- `ntoskrnl!ExAllocatePool2` at `0x140109a96`
- `ntoskrnl!ExAllocatePool2` at `0x140109b45`
- `ntoskrnl!RtlInitializeSid` at `0x140109a1b`
- `ntoskrnl!RtlInitializeSid` at `0x140109a1b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140109ad2`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140109ad2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140109a36`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140109a36`
- `WIN32K!W32GetUserSessionState` at `0x1401099ab`
- `WIN32K!W32GetUserSessionState` at `0x1401099ab`

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
0x14010996c  push    rbx
0x14010996e  push    rbp
0x14010996f  push    rsi
0x140109970  push    rdi
0x140109971  push    r14
0x140109973  push    r15
0x140109975  sub     rsp, 0D8h
0x14010997c  mov     rax, cs:__security_cookie
0x140109983  xor     rax, rsp
0x140109986  mov     [rsp+108h+var_40], rax
0x14010998e  mov     r15, rcx
0x140109991  mov     qword ptr [rcx], 0
0x140109998  mov     ecx, 1; SubAuthorityCount
0x14010999d  call    cs:__imp_RtlLengthRequiredSid
0x1401099a4  nop     dword ptr [rax+rax+00h]
0x1401099a9  mov     ebx, eax
0x1401099ab  call    cs:__imp_W32GetUserSessionState
0x1401099b2  nop     dword ptr [rax+rax+00h]
0x1401099b7  lea     rdi, [rax+11950h]
0x1401099be  mov     eax, [rdi]
0x1401099c0  test    eax, eax
0x1401099c2  jnz     loc_140109B1C
0x1401099c8  mov     r8d, 65737355h
0x1401099ce  mov     rdx, rbx
0x1401099d1  mov     ecx, 101h
0x1401099d6  call    cs:__imp_ExAllocatePool2
0x1401099dd  nop     dword ptr [rax+rax+00h]
0x1401099e2  mov     rbx, rax
0x1401099e5  test    rax, rax
0x1401099e8  jz      short loc_1401099EF
0x1401099ea  lock inc qword ptr [rdi+70h]
0x1401099ef  test    rbx, rbx
0x1401099f2  jz      loc_140109B12
0x1401099f8  mov     r8b, 1; SubAuthorityCount
0x1401099fb  mov     dword ptr [rsp+108h+IdentifierAuthority.Value], 0
0x140109a06  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x140109a0e  mov     word ptr [rsp+108h+IdentifierAuthority.Value+4], 500h
0x140109a18  mov     rcx, rbx; Sid
0x140109a1b  call    cs:__imp_RtlInitializeSid
0x140109a22  nop     dword ptr [rax+rax+00h]
0x140109a27  mov     edi, eax
0x140109a29  mov     rcx, rbx; Buffer
0x140109a2c  test    eax, eax
0x140109a2e  js      loc_140109BF8
0x140109a34  xor     edx, edx; SubAuthority
0x140109a36  call    cs:__imp_RtlSubAuthoritySid
0x140109a3d  nop     dword ptr [rax+rax+00h]
0x140109a42  mov     dword ptr [rax], 12h
0x140109a48  mov     [r15], rbx
0x140109a4b  mov     eax, edi
0x140109a4d  mov     rcx, [rsp+108h+var_40]
0x140109a55  xor     rcx, rsp; StackCookie
0x140109a58  call    __security_check_cookie
0x140109a5d  add     rsp, 0D8h
0x140109a64  pop     r15
0x140109a66  pop     r14
0x140109a68  pop     rdi
0x140109a69  pop     rsi
0x140109a6a  pop     rbp
0x140109a6b  pop     rbx
0x140109a6c  retn
0x140109a6e  cmp     rbx, 1000h
0x140109a75  jb      loc_140109BEC
0x140109a7b  xor     r14b, r14b
0x140109a7e  test    rbx, 0FFFh
0x140109a85  jnz     loc_140109BEC
0x140109a8b  mov     r8d, esi
0x140109a8e  mov     rdx, rbx
0x140109a91  mov     ecx, 101h
0x140109a96  call    cs:__imp_ExAllocatePool2
0x140109a9d  nop     dword ptr [rax+rax+00h]
0x140109aa2  mov     rbx, rax
0x140109aa5  test    rax, rax
0x140109aa8  jz      short loc_140109B12
0x140109aaa  lock inc qword ptr [rdi+80h]
0x140109ab2  xor     edx, edx; Val
0x140109ab4  lea     rcx, [rsp+108h+BackTrace]; void *
0x140109ab9  mov     r8d, 0A0h; Size
0x140109abf  call    memset
0x140109ac4  xor     r9d, r9d; BackTraceHash
0x140109ac7  lea     r8, [rsp+108h+BackTrace]; BackTrace
0x140109acc  xor     ecx, ecx; FramesToSkip
0x140109ace  lea     edx, [r9+14h]; FramesToCapture
0x140109ad2  call    cs:__imp_RtlCaptureStackBackTrace
0x140109ad9  nop     dword ptr [rax+rax+00h]
0x140109ade  test    r14b, r14b
0x140109ae1  jnz     loc_140109BB0
0x140109ae7  lea     r9, [rsp+108h+BackTrace]
0x140109aec  mov     r8, rbp
0x140109aef  mov     rdx, rbx
0x140109af2  mov     rcx, rdi
0x140109af5  call    ??$AssociateAllocationWithBacktrace@$0A@@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x140109afa  test    al, al
0x140109afc  jnz     loc_1401099F8
0x140109b02  lock inc qword ptr [rdi+88h]
0x140109b0a  mov     rcx, rbx; Buffer
0x140109b0d  call    ??$_lambda_invoker_cdecl_@PEAX@_lambda_2af9a864ca5eb776d3057466a2e51944_@@CA?A_PPEAX@Z
0x140109b12  mov     edi, 0C0000017h
0x140109b17  jmp     loc_140109A4B
0x140109b1c  cmp     eax, 1
0x140109b1f  jnz     short loc_140109B7C
0x140109b21  mov     esi, 65737355h
0x140109b26  mov     rcx, rdi; this
0x140109b29  mov     edx, esi; unsigned int
0x140109b2b  call    ?EnsurePoolTagIncrement@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NI@Z; NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(uint)
0x140109b30  test    al, al
0x140109b32  jz      short loc_140109B12
0x140109b34  lea     rdx, [rbx+10h]
0x140109b38  cmp     rdx, rbx
0x140109b3b  jbe     short loc_140109B12
0x140109b3d  mov     r8d, esi
0x140109b40  mov     ecx, 101h
0x140109b45  call    cs:__imp_ExAllocatePool2
0x140109b4c  nop     dword ptr [rax+rax+00h]
0x140109b51  mov     rbx, rax
0x140109b54  test    rax, rax
0x140109b57  jz      short loc_140109B6B
0x140109b59  lock inc qword ptr [rdi+70h]
0x140109b5e  mov     [rax], rsi
0x140109b61  add     rbx, 10h
0x140109b65  jnz     loc_1401099EF
0x140109b6b  mov     rcx, [rdi+8]; this
0x140109b6f  mov     rdx, rsi; void *
0x140109b72  call    ?LookupInterlockedDecrement@CPointerHashTable@NSInstrumentation@@QEAA_NPEBX@Z; NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(void const *)
0x140109b77  jmp     loc_1401099EF
0x140109b7c  cmp     eax, 2
0x140109b7f  jnz     short loc_140109B12
0x140109b81  mov     eax, [rdi+50h]
0x140109b84  mov     esi, 65737355h
0x140109b89  and     eax, esi
0x140109b8b  cmp     eax, esi
0x140109b8d  jz      short loc_140109B97
0x140109b8f  mov     r8d, esi
0x140109b92  jmp     loc_1401099CE
0x140109b97  mov     eax, [rdi+54h]
0x140109b9a  xor     ebp, ebp
0x140109b9c  cmp     rbp, rax
0x140109b9f  jnb     short loc_140109B8F
0x140109ba1  cmp     [rdi+rbp*4+30h], esi
0x140109ba5  jz      loc_140109A6E
0x140109bab  inc     rbp
0x140109bae  jmp     short loc_140109B9C
0x140109bb0  mov     rax, rbx
0x140109bb3  and     eax, 0FFFh
0x140109bb8  add     rax, 10h
0x140109bbc  cmp     rax, 1000h
0x140109bc2  jnb     loc_140109AE7
0x140109bc8  lea     r9, [rsp+108h+BackTrace]
0x140109bcd  mov     r8, rbp
0x140109bd0  mov     rdx, rbx
0x140109bd3  mov     rcx, rdi
0x140109bd6  call    ??$AssociateAllocationWithBacktrace@$00@CLeakTrackingAllocator@NSInstrumentation@@AEAA_NPEAX_KPEAVCBackTrace@1@@Z; NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(void *,unsigned __int64,NSInstrumentation::CBackTrace *)
0x140109bdb  test    al, al
0x140109bdd  jz      loc_140109B02
0x140109be3  add     rbx, 10h
0x140109be7  jmp     loc_1401099EF
0x140109bec  mov     r14b, 1
0x140109bef  add     rbx, 10h
0x140109bf3  jmp     loc_140109A8B
0x140109bf8  call    GreDeleteFastMutex
0x140109bfd  jmp     loc_140109A4B
```
