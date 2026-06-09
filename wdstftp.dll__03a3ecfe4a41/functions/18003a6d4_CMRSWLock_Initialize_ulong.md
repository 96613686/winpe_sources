# CMRSWLock::Initialize(ulong)

- ea: `0x18003a6d4`
- end: `0x18003a7a6`
- name: `?Initialize@CMRSWLock@@QEAAKK@Z`
- size: `210`
- prototype: `unsigned int __fastcall(CMRSWLock *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010a4`
- `0x18000bfcc`
- `0x18000c09c`

## callees

- `0x18003a6d4`
- `0x180060808`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x18003a729`
- `KERNEL32!CreateSemaphoreW` at `0x18003a75b`
- `KERNEL32!CreateSemaphoreW` at `0x18003a77d`
- `KERNEL32!CreateSemaphoreW` at `0x18003a729`
- `KERNEL32!CreateSemaphoreW` at `0x18003a75b`
- `KERNEL32!CreateSemaphoreW` at `0x18003a77d`
- `KERNEL32!GetLastError` at `0x18003a73e`
- `KERNEL32!GetLastError` at `0x18003a73e`

## pseudocode

```c
__int64 __fastcall CMRSWLock::Initialize(CMRSWLock *this)
{
  unsigned int v2; // ebx
  void *v3; // rax
  HANDLE SemaphoreW; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax

  v2 = 0;
  v3 = operator new[](0x1000u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 12) = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x1000u);
    *((_DWORD *)this + 21) = 512;
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    *((_QWORD *)this + 7) = SemaphoreW;
    if ( SemaphoreW
      && (v5 = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0), (*((_QWORD *)this + 6) = v5) != 0)
      && (v6 = CreateSemaphoreW(0, 512, 512, 0), (*((_QWORD *)this + 8) = v6) != 0) )
    {
      *((_DWORD *)this + 10) = 1;
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    return 8;
  }
  return v2;
}

```

## disassembly

```asm
0x18003a6d4  mov     [rsp+arg_0], rbx
0x18003a6d9  push    rdi
0x18003a6da  sub     rsp, 20h
0x18003a6de  mov     rdi, rcx
0x18003a6e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a6e8  mov     ecx, 1000h; unsigned __int64
0x18003a6ed  xor     ebx, ebx
0x18003a6ef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003a6f4  mov     [rdi+60h], rax
0x18003a6f8  test    rax, rax
0x18003a6fb  jnz     short loc_18003A705
0x18003a6fd  lea     ebx, [rax+8]
0x18003a700  jmp     loc_18003A799
0x18003a705  xor     edx, edx; Val
0x18003a707  mov     r8d, 1000h; Size
0x18003a70d  mov     rcx, rax; void *
0x18003a710  call    memset_0
0x18003a715  xor     r9d, r9d; lpName
0x18003a718  mov     dword ptr [rdi+54h], 200h
0x18003a71f  xor     edx, edx; lInitialCount
0x18003a721  xor     ecx, ecx; lpSemaphoreAttributes
0x18003a723  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18003a729  call    cs:__imp_CreateSemaphoreW
0x18003a730  nop     dword ptr [rax+rax+00h]
0x18003a735  mov     [rdi+38h], rax
0x18003a739  test    rax, rax
0x18003a73c  jnz     short loc_18003A74E
0x18003a73e  call    cs:__imp_GetLastError
0x18003a745  nop     dword ptr [rax+rax+00h]
0x18003a74a  mov     ebx, eax
0x18003a74c  jmp     short loc_18003A799
0x18003a74e  xor     r9d, r9d; lpName
0x18003a751  xor     edx, edx; lInitialCount
0x18003a753  xor     ecx, ecx; lpSemaphoreAttributes
0x18003a755  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18003a75b  call    cs:__imp_CreateSemaphoreW
0x18003a762  nop     dword ptr [rax+rax+00h]
0x18003a767  mov     [rdi+30h], rax
0x18003a76b  test    rax, rax
0x18003a76e  jz      short loc_18003A73E
0x18003a770  mov     edx, 200h; lInitialCount
0x18003a775  xor     r9d, r9d; lpName
0x18003a778  mov     r8d, edx; lMaximumCount
0x18003a77b  xor     ecx, ecx; lpSemaphoreAttributes
0x18003a77d  call    cs:__imp_CreateSemaphoreW
0x18003a784  nop     dword ptr [rax+rax+00h]
0x18003a789  mov     [rdi+40h], rax
0x18003a78d  test    rax, rax
0x18003a790  jz      short loc_18003A73E
0x18003a792  mov     dword ptr [rdi+28h], 1
0x18003a799  mov     eax, ebx
0x18003a79b  mov     rbx, [rsp+28h+arg_0]
0x18003a7a0  add     rsp, 20h
0x18003a7a4  pop     rdi
0x18003a7a5  retn
```
