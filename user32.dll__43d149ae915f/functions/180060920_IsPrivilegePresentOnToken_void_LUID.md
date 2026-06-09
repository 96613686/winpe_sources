# IsPrivilegePresentOnToken(void *,_LUID)

- ea: `0x180060920`
- end: `0x1800609e6`
- name: `?IsPrivilegePresentOnToken@@YAHPEAXU_LUID@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _LUID)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006081c`

## callees

- `0x180060920`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180060953`
- `ntdll!NtQueryInformationToken` at `0x180060995`
- `ntdll!NtQueryInformationToken` at `0x180060953`
- `ntdll!NtQueryInformationToken` at `0x180060995`
- `ntdll!RtlFreeHeap` at `0x1800609d1`
- `ntdll!RtlFreeHeap` at `0x1800609d1`
- `ntdll!RtlAllocateHeap` at `0x18006096f`
- `ntdll!RtlAllocateHeap` at `0x18006096f`

## pseudocode

```c
__int64 __fastcall IsPrivilegePresentOnToken(HANDLE TokenHandle, struct _LUID a2)
{
  DWORD LowPart; // ebx
  unsigned int v3; // esi
  _DWORD *Heap; // rdi
  __int64 i; // rcx
  LONG HighPart; // [rsp+5Ch] [rbp+14h]
  SIZE_T Size; // [rsp+60h] [rbp+18h] BYREF

  HighPart = a2.HighPart;
  LODWORD(Size) = 0;
  LowPart = a2.LowPart;
  v3 = 0;
  if ( NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, (PULONG)&Size) == -1073741789 )
  {
    Heap = RtlAllocateHeap(pUserHeap, 8u, (unsigned int)Size);
    if ( Heap )
    {
      if ( NtQueryInformationToken(TokenHandle, TokenPrivileges, Heap, Size, (PULONG)&Size) >= 0 )
      {
        for ( i = 0; (unsigned int)i < *Heap; i = (unsigned int)(i + 1) )
        {
          if ( *(_QWORD *)&Heap[3 * i + 1] == __PAIR64__(HighPart, LowPart) )
          {
            v3 = 1;
            break;
          }
        }
      }
      RtlFreeHeap(pUserHeap, 0, Heap);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180060920  mov     rax, rsp
0x180060923  mov     [rax+8], rbx
0x180060927  mov     [rax+10h], rdx
0x18006092b  push    rbp
0x18006092c  push    rsi
0x18006092d  push    rdi
0x18006092e  sub     rsp, 30h
0x180060932  mov     dword ptr [rax+18h], 0
0x180060939  lea     rax, [rax+18h]
0x18006093d  mov     rbx, rdx
0x180060940  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180060945  xor     esi, esi
0x180060947  xor     r9d, r9d; TokenInformationLength
0x18006094a  xor     r8d, r8d; TokenInformation
0x18006094d  mov     rbp, rcx
0x180060950  lea     edx, [rsi+3]; TokenInformationClass
0x180060953  call    cs:__imp_NtQueryInformationToken
0x180060959  cmp     eax, 0C0000023h
0x18006095e  jnz     short loc_1800609D7
0x180060960  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180060965  lea     edx, [rsi+8]; Flags
0x180060968  mov     rcx, cs:pUserHeap; HeapHandle
0x18006096f  call    cs:__imp_RtlAllocateHeap
0x180060975  mov     rdi, rax
0x180060978  test    rax, rax
0x18006097b  jz      short loc_1800609D7
0x18006097d  mov     r9d, dword ptr [rsp+48h+Size]; TokenInformationLength
0x180060982  lea     rax, [rsp+48h+Size]
0x180060987  mov     r8, rdi; TokenInformation
0x18006098a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18006098f  lea     edx, [rsi+3]; TokenInformationClass
0x180060992  mov     rcx, rbp; TokenHandle
0x180060995  call    cs:__imp_NtQueryInformationToken
0x18006099b  test    eax, eax
0x18006099d  js      short loc_1800609C5
0x18006099f  xor     ecx, ecx
0x1800609a1  cmp     ecx, [rdi]
0x1800609a3  jnb     short loc_1800609C5
0x1800609a5  lea     rax, [rcx+rcx*2]
0x1800609a9  mov     rax, [rdi+rax*4+4]
0x1800609ae  cmp     eax, ebx
0x1800609b0  jnz     short loc_1800609BC
0x1800609b2  shr     rax, 20h
0x1800609b6  cmp     eax, [rsp+48h+arg_C]
0x1800609ba  jz      short loc_1800609C0
0x1800609bc  inc     ecx
0x1800609be  jmp     short loc_1800609A1
0x1800609c0  mov     esi, 1
0x1800609c5  mov     rcx, cs:pUserHeap; HeapHandle
0x1800609cc  mov     r8, rdi; P
0x1800609cf  xor     edx, edx; Flags
0x1800609d1  call    cs:__imp_RtlFreeHeap
0x1800609d7  mov     rbx, [rsp+48h+arg_0]
0x1800609dc  mov     eax, esi
0x1800609de  add     rsp, 30h
0x1800609e2  pop     rdi
0x1800609e3  pop     rsi
0x1800609e4  pop     rbp
0x1800609e5  retn
```
