# _UserTestTokenForInteractive

- ea: `0x1800910b0`
- end: `0x18009116f`
- name: `_UserTestTokenForInteractive`
- size: `191`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800910b0`

## import_xrefs

- `win32u!NtUserTestForInteractiveUser` at `0x180091143`
- `win32u!NtUserTestForInteractiveUser` at `0x180091143`
- `ntdll!NtQueryInformationToken` at `0x1800910e0`
- `ntdll!NtQueryInformationToken` at `0x18009112d`
- `ntdll!NtQueryInformationToken` at `0x1800910e0`
- `ntdll!NtQueryInformationToken` at `0x18009112d`
- `ntdll!RtlFreeHeap` at `0x180091157`
- `ntdll!RtlFreeHeap` at `0x180091157`
- `ntdll!RtlAllocateHeap` at `0x1800910fe`
- `ntdll!RtlAllocateHeap` at `0x1800910fe`

## pseudocode

```c
NTSTATUS __fastcall UserTestTokenForInteractive(HANDLE TokenHandle, _QWORD *a2)
{
  NTSTATUS result; // eax
  _QWORD *Heap; // rbx
  NTSTATUS InformationToken; // edi
  SIZE_T Size; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(Size) = 0;
  result = NtQueryInformationToken(TokenHandle, TokenStatistics, 0, 0, (PULONG)&Size);
  if ( result == -1073741789 )
  {
    Heap = RtlAllocateHeap(pUserHeap, 8u, (unsigned int)Size);
    if ( Heap )
    {
      InformationToken = NtQueryInformationToken(TokenHandle, TokenStatistics, Heap, Size, (PULONG)&Size);
      if ( InformationToken >= 0 )
      {
        *a2 = Heap[1];
        InformationToken = NtUserTestForInteractiveUser();
      }
      RtlFreeHeap(pUserHeap, 0, Heap);
      return InformationToken;
    }
    else
    {
      return -1073741801;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800910b0  mov     rax, rsp
0x1800910b3  mov     [rax+8], rbx
0x1800910b7  mov     [rax+10h], rsi
0x1800910bb  push    rdi
0x1800910bc  sub     rsp, 30h
0x1800910c0  xor     r9d, r9d; TokenInformationLength
0x1800910c3  mov     dword ptr [rax+18h], 0
0x1800910ca  mov     rsi, rdx
0x1800910cd  lea     rax, [rax+18h]
0x1800910d1  xor     r8d, r8d; TokenInformation
0x1800910d4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800910d9  mov     rdi, rcx
0x1800910dc  lea     edx, [r9+0Ah]; TokenInformationClass
0x1800910e0  call    cs:__imp_NtQueryInformationToken
0x1800910e6  cmp     eax, 0C0000023h
0x1800910eb  jnz     short loc_18009115F
0x1800910ed  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x1800910f2  mov     edx, 8; Flags
0x1800910f7  mov     rcx, cs:pUserHeap; HeapHandle
0x1800910fe  call    cs:__imp_RtlAllocateHeap
0x180091104  mov     rbx, rax
0x180091107  test    rax, rax
0x18009110a  jnz     short loc_180091113
0x18009110c  mov     eax, 0C0000017h
0x180091111  jmp     short loc_18009115F
0x180091113  mov     r9d, dword ptr [rsp+38h+Size]; TokenInformationLength
0x180091118  lea     rax, [rsp+38h+Size]
0x18009111d  mov     r8, rbx; TokenInformation
0x180091120  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180091125  mov     edx, 0Ah; TokenInformationClass
0x18009112a  mov     rcx, rdi; TokenHandle
0x18009112d  call    cs:__imp_NtQueryInformationToken
0x180091133  mov     edi, eax
0x180091135  test    eax, eax
0x180091137  js      short loc_18009114B
0x180091139  lea     rcx, [rbx+8]
0x18009113d  mov     rax, [rcx]
0x180091140  mov     [rsi], rax
0x180091143  call    cs:__imp_NtUserTestForInteractiveUser
0x180091149  mov     edi, eax
0x18009114b  mov     rcx, cs:pUserHeap; HeapHandle
0x180091152  mov     r8, rbx; P
0x180091155  xor     edx, edx; Flags
0x180091157  call    cs:__imp_RtlFreeHeap
0x18009115d  mov     eax, edi
0x18009115f  mov     rbx, [rsp+38h+arg_0]
0x180091164  mov     rsi, [rsp+38h+arg_8]
0x180091169  add     rsp, 30h
0x18009116d  pop     rdi
0x18009116e  retn
```
