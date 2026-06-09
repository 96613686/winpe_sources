# CMRSWLock::Initialize(ulong)

- ea: `0x1800248d4`
- end: `0x18002498b`
- name: `?Initialize@CMRSWLock@@QEAAKK@Z`
- size: `183`
- prototype: `unsigned int __fastcall(CMRSWLock *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180005098`
- `0x1800053a0`
- `0x18000ce38`
- `0x18000e340`

## callees

- `0x1800248d4`
- `0x180026694`
- `0x180026d46`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024935`
- `KERNEL32!GetLastError` at `0x180024935`
- `KERNEL32!CreateSemaphoreW` at `0x180024926`
- `KERNEL32!CreateSemaphoreW` at `0x18002494c`
- `KERNEL32!CreateSemaphoreW` at `0x180024968`
- `KERNEL32!CreateSemaphoreW` at `0x180024926`
- `KERNEL32!CreateSemaphoreW` at `0x18002494c`
- `KERNEL32!CreateSemaphoreW` at `0x180024968`

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
0x1800248d4  mov     [rsp+arg_0], rbx
0x1800248d9  push    rdi
0x1800248da  sub     rsp, 20h
0x1800248de  mov     rdi, rcx
0x1800248e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800248e8  mov     ecx, 1000h; unsigned __int64
0x1800248ed  xor     ebx, ebx
0x1800248ef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800248f4  mov     [rdi+60h], rax
0x1800248f8  test    rax, rax
0x1800248fb  jnz     short loc_180024902
0x1800248fd  lea     ebx, [rax+8]
0x180024900  jmp     short loc_18002497E
0x180024902  xor     edx, edx; Val
0x180024904  mov     r8d, 1000h; Size
0x18002490a  mov     rcx, rax; void *
0x18002490d  call    memset_0
0x180024912  xor     r9d, r9d; lpName
0x180024915  mov     dword ptr [rdi+54h], 200h
0x18002491c  xor     edx, edx; lInitialCount
0x18002491e  xor     ecx, ecx; lpSemaphoreAttributes
0x180024920  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180024926  call    cs:__imp_CreateSemaphoreW
0x18002492c  mov     [rdi+38h], rax
0x180024930  test    rax, rax
0x180024933  jnz     short loc_18002493F
0x180024935  call    cs:__imp_GetLastError
0x18002493b  mov     ebx, eax
0x18002493d  jmp     short loc_18002497E
0x18002493f  xor     r9d, r9d; lpName
0x180024942  xor     edx, edx; lInitialCount
0x180024944  xor     ecx, ecx; lpSemaphoreAttributes
0x180024946  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18002494c  call    cs:__imp_CreateSemaphoreW
0x180024952  mov     [rdi+30h], rax
0x180024956  test    rax, rax
0x180024959  jz      short loc_180024935
0x18002495b  mov     edx, 200h; lInitialCount
0x180024960  xor     r9d, r9d; lpName
0x180024963  mov     r8d, edx; lMaximumCount
0x180024966  xor     ecx, ecx; lpSemaphoreAttributes
0x180024968  call    cs:__imp_CreateSemaphoreW
0x18002496e  mov     [rdi+40h], rax
0x180024972  test    rax, rax
0x180024975  jz      short loc_180024935
0x180024977  mov     dword ptr [rdi+28h], 1
0x18002497e  mov     eax, ebx
0x180024980  mov     rbx, [rsp+28h+arg_0]
0x180024985  add     rsp, 20h
0x180024989  pop     rdi
0x18002498a  retn
```
