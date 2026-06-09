# ORSetKeySecurity

- ea: `0x1402930b0`
- end: `0x140293249`
- name: `ORSetKeySecurity`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140124038`
- `0x140134831`
- `0x14013483d`
- `0x1401365b9`
- `0x1402930b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1402931ad`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1402931ad`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x14029312a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x14029312a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140293222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140293222`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14029310a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14029310a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402931bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402931bd`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap_0; // rax
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
        Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap_0;
        if ( Heap_0 )
        {
          memcpy_0(Heap_0, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
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
0x1402930b0  mov     rax, rsp
0x1402930b3  push    rbx
0x1402930b4  push    rbp
0x1402930b5  push    rsi
0x1402930b6  push    rdi
0x1402930b7  push    r12
0x1402930b9  push    r13
0x1402930bb  push    r14
0x1402930bd  push    r15
0x1402930bf  sub     rsp, 38h
0x1402930c3  xor     r13d, r13d
0x1402930c6  mov     rbp, r8
0x1402930c9  mov     [rax+8], r13
0x1402930cd  mov     r12d, edx
0x1402930d0  mov     eax, 746Eh
0x1402930d5  mov     rdi, rcx
0x1402930d8  cmp     [rcx+1Ch], ax
0x1402930dc  jnz     loc_140293230
0x1402930e2  mov     rsi, [rcx+10h]
0x1402930e6  cmp     dword ptr [rsi], 0BEE0BEE0h
0x1402930ec  jnz     loc_140293230
0x1402930f2  test    r8, r8
0x1402930f5  jnz     short loc_140293100
0x1402930f7  lea     ebx, [r8+57h]
0x1402930fb  jmp     loc_140293235
0x140293100  lea     r14, [rsi+88h]
0x140293107  mov     rcx, r14; lpCriticalSection
0x14029310a  call    cs:__imp_EnterCriticalSection
0x140293111  nop     dword ptr [rax+rax+00h]
0x140293116  cmp     [rdi+1Eh], r13w
0x14029311b  jz      short loc_140293127
0x14029311d  mov     ebx, 3FAh
0x140293122  jmp     loc_1402931F9
0x140293127  mov     rcx, rbp; pSecurityDescriptor
0x14029312a  call    cs:__imp_IsValidSecurityDescriptor
0x140293131  nop     dword ptr [rax+rax+00h]
0x140293136  test    eax, eax
0x140293138  jnz     short loc_140293144
0x14029313a  mov     ebx, 53Ah
0x14029313f  jmp     loc_1402931F9
0x140293144  mov     rax, [rdi+60h]
0x140293148  xor     edx, edx; Flags
0x14029314a  mov     rcx, gs:60h
0x140293153  mov     ebx, r13d
0x140293156  mov     r15, [rax+10h]
0x14029315a  mov     rcx, [rcx+30h]; HeapHandle
0x14029315e  mov     r8d, [r15+10h]; Size
0x140293162  call    RtlAllocateHeap_0
0x140293167  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x14029316f  test    rax, rax
0x140293172  jz      loc_1402931F9
0x140293178  mov     r8d, [r15+10h]; Size
0x14029317c  lea     rdx, [r15+14h]; Src
0x140293180  mov     rcx, rax; void *
0x140293183  call    memcpy_0
0x140293188  lea     rax, CmKeyMapping
0x14029318f  mov     [rsp+78h+Token], r13; Token
0x140293194  mov     r9d, 8; AutoInheritFlags
0x14029319a  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x14029319f  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1402931a7  mov     rdx, rbp; ModificationDescriptor
0x1402931aa  mov     ecx, r12d; SecurityInformation
0x1402931ad  call    cs:__imp_SetPrivateObjectSecurityEx
0x1402931b4  nop     dword ptr [rax+rax+00h]
0x1402931b9  test    eax, eax
0x1402931bb  jnz     short loc_1402931CF
0x1402931bd  call    cs:__imp_GetLastError
0x1402931c4  nop     dword ptr [rax+rax+00h]
0x1402931c9  mov     ebx, eax
0x1402931cb  test    eax, eax
0x1402931cd  jnz     short loc_1402931F9
0x1402931cf  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x1402931d7  mov     rcx, rdi
0x1402931da  call    OrpAssignKeySecurityToTreeNode
0x1402931df  mov     ebx, eax
0x1402931e1  test    eax, eax
0x1402931e3  jnz     short loc_1402931F9
0x1402931e5  inc     qword ptr [rdi+0A8h]
0x1402931ec  mov     ebx, r13d
0x1402931ef  mov     dword ptr [rsi+0B4h], 1
0x1402931f9  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x140293201  jz      short loc_14029321F
0x140293203  mov     rcx, gs:60h
0x14029320c  xor     edx, edx; Flags
0x14029320e  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x140293216  mov     rcx, [rcx+30h]; HeapHandle
0x14029321a  call    RtlFreeHeap_0
0x14029321f  mov     rcx, r14; lpCriticalSection
0x140293222  call    cs:__imp_LeaveCriticalSection
0x140293229  nop     dword ptr [rax+rax+00h]
0x14029322e  jmp     short loc_140293235
0x140293230  mov     ebx, 6
0x140293235  mov     eax, ebx
0x140293237  add     rsp, 38h
0x14029323b  pop     r15
0x14029323d  pop     r14
0x14029323f  pop     r13
0x140293241  pop     r12
0x140293243  pop     rdi
0x140293244  pop     rsi
0x140293245  pop     rbp
0x140293246  pop     rbx
0x140293247  retn
```
