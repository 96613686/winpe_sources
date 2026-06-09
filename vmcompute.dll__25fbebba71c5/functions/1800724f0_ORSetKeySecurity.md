# ORSetKeySecurity

- ea: `0x1800724f0`
- end: `0x180072690`
- name: `ORSetKeySecurity`
- size: `416`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006994c`
- `0x1800699f4`
- `0x18006b024`

## callees

- `0x180004829`
- `0x180004a60`
- `0x1800724f0`
- `0x180072698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072669`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072669`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007254a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007254a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072604`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800725f4`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1800725f4`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18007256a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18007256a`
- `ntdll!RtlAllocateHeap` at `0x1800725a2`
- `ntdll!RtlAllocateHeap` at `0x1800725a2`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap; // rax
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+80h] [rbp+8h] BYREF

  ObjectsSecurityDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 && (v6 = *(_QWORD *)(a1 + 16), *(_DWORD *)v6 == -1092567328) )
  {
    if ( a3 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
      if ( *(_WORD *)(a1 + 30) )
      {
        LastError = 1018;
      }
      else if ( IsValidSecurityDescriptor(a3) )
      {
        LastError = 0;
        v8 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL);
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap;
        if ( Heap )
        {
          memcpy_0(Heap, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
          if ( SetPrivateObjectSecurityEx(a2, a3, &ObjectsSecurityDescriptor, 8u, &CmKeyMapping, 0)
            || (LastError = GetLastError()) == 0 )
          {
            LastError = OrpAssignKeySecurityToTreeNode(a1, ObjectsSecurityDescriptor);
            if ( !LastError )
            {
              ++*(_QWORD *)(a1 + 168);
              LastError = 0;
              *(_DWORD *)(v6 + 180) = 1;
            }
          }
        }
      }
      else
      {
        LastError = 1338;
      }
      if ( ObjectsSecurityDescriptor )
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, ObjectsSecurityDescriptor);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 6;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800724f0  mov     rax, rsp
0x1800724f3  push    rbx
0x1800724f4  push    rbp
0x1800724f5  push    rsi
0x1800724f6  push    rdi
0x1800724f7  push    r12
0x1800724f9  push    r13
0x1800724fb  push    r14
0x1800724fd  push    r15
0x1800724ff  sub     rsp, 38h
0x180072503  xor     r13d, r13d
0x180072506  mov     rbp, r8
0x180072509  mov     [rax+8], r13
0x18007250d  mov     r12d, edx
0x180072510  mov     eax, 746Eh
0x180072515  mov     rdi, rcx
0x180072518  cmp     [rcx+1Ch], ax
0x18007251c  jnz     loc_180072677
0x180072522  mov     rsi, [rcx+10h]
0x180072526  cmp     dword ptr [rsi], 0BEE0BEE0h
0x18007252c  jnz     loc_180072677
0x180072532  test    r8, r8
0x180072535  jnz     short loc_180072540
0x180072537  lea     ebx, [r8+57h]
0x18007253b  jmp     loc_18007267C
0x180072540  lea     r14, [rsi+88h]
0x180072547  mov     rcx, r14; lpCriticalSection
0x18007254a  call    cs:__imp_EnterCriticalSection
0x180072551  nop     dword ptr [rax+rax+00h]
0x180072556  cmp     [rdi+1Eh], r13w
0x18007255b  jz      short loc_180072567
0x18007255d  mov     ebx, 3FAh
0x180072562  jmp     loc_180072640
0x180072567  mov     rcx, rbp; pSecurityDescriptor
0x18007256a  call    cs:__imp_IsValidSecurityDescriptor
0x180072571  nop     dword ptr [rax+rax+00h]
0x180072576  test    eax, eax
0x180072578  jnz     short loc_180072584
0x18007257a  mov     ebx, 53Ah
0x18007257f  jmp     loc_180072640
0x180072584  mov     rax, [rdi+60h]
0x180072588  xor     edx, edx; Flags
0x18007258a  mov     rcx, gs:60h
0x180072593  mov     ebx, r13d
0x180072596  mov     r15, [rax+10h]
0x18007259a  mov     rcx, [rcx+30h]; HeapHandle
0x18007259e  mov     r8d, [r15+10h]; Size
0x1800725a2  call    cs:__imp_RtlAllocateHeap
0x1800725a9  nop     dword ptr [rax+rax+00h]
0x1800725ae  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x1800725b6  test    rax, rax
0x1800725b9  jz      loc_180072640
0x1800725bf  mov     r8d, [r15+10h]; Size
0x1800725c3  lea     rdx, [r15+14h]; Src
0x1800725c7  mov     rcx, rax; void *
0x1800725ca  call    memcpy_0
0x1800725cf  lea     rax, CmKeyMapping
0x1800725d6  mov     [rsp+78h+Token], r13; Token
0x1800725db  mov     r9d, 8; AutoInheritFlags
0x1800725e1  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1800725e6  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1800725ee  mov     rdx, rbp; ModificationDescriptor
0x1800725f1  mov     ecx, r12d; SecurityInformation
0x1800725f4  call    cs:__imp_SetPrivateObjectSecurityEx
0x1800725fb  nop     dword ptr [rax+rax+00h]
0x180072600  test    eax, eax
0x180072602  jnz     short loc_180072616
0x180072604  call    cs:__imp_GetLastError
0x18007260b  nop     dword ptr [rax+rax+00h]
0x180072610  mov     ebx, eax
0x180072612  test    eax, eax
0x180072614  jnz     short loc_180072640
0x180072616  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x18007261e  mov     rcx, rdi
0x180072621  call    OrpAssignKeySecurityToTreeNode
0x180072626  mov     ebx, eax
0x180072628  test    eax, eax
0x18007262a  jnz     short loc_180072640
0x18007262c  inc     qword ptr [rdi+0A8h]
0x180072633  mov     ebx, r13d
0x180072636  mov     dword ptr [rsi+0B4h], 1
0x180072640  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x180072648  jz      short loc_180072666
0x18007264a  mov     rcx, gs:60h
0x180072653  xor     edx, edx; Flags
0x180072655  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x18007265d  mov     rcx, [rcx+30h]; HeapHandle
0x180072661  call    RtlFreeHeap_0
0x180072666  mov     rcx, r14; lpCriticalSection
0x180072669  call    cs:__imp_LeaveCriticalSection
0x180072670  nop     dword ptr [rax+rax+00h]
0x180072675  jmp     short loc_18007267C
0x180072677  mov     ebx, 6
0x18007267c  mov     eax, ebx
0x18007267e  add     rsp, 38h
0x180072682  pop     r15
0x180072684  pop     r14
0x180072686  pop     r13
0x180072688  pop     r12
0x18007268a  pop     rdi
0x18007268b  pop     rsi
0x18007268c  pop     rbp
0x18007268d  pop     rbx
0x18007268e  retn
```
