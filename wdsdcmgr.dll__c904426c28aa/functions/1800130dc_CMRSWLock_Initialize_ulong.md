# CMRSWLock::Initialize(ulong)

- ea: `0x1800130dc`
- end: `0x180013193`
- name: `?Initialize@CMRSWLock@@QEAAKK@Z`
- size: `183`
- prototype: `unsigned int __fastcall(CMRSWLock *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e14`
- `0x180003acc`

## callees

- `0x1800130dc`
- `0x1800157a4`
- `0x180015c9d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001313d`
- `KERNEL32!GetLastError` at `0x18001313d`
- `KERNEL32!CreateSemaphoreW` at `0x18001312e`
- `KERNEL32!CreateSemaphoreW` at `0x180013154`
- `KERNEL32!CreateSemaphoreW` at `0x180013170`
- `KERNEL32!CreateSemaphoreW` at `0x18001312e`
- `KERNEL32!CreateSemaphoreW` at `0x180013154`
- `KERNEL32!CreateSemaphoreW` at `0x180013170`

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
0x1800130dc  mov     [rsp+arg_0], rbx
0x1800130e1  push    rdi
0x1800130e2  sub     rsp, 20h
0x1800130e6  mov     rdi, rcx
0x1800130e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800130f0  mov     ecx, 1000h; unsigned __int64
0x1800130f5  xor     ebx, ebx
0x1800130f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800130fc  mov     [rdi+60h], rax
0x180013100  test    rax, rax
0x180013103  jnz     short loc_18001310A
0x180013105  lea     ebx, [rax+8]
0x180013108  jmp     short loc_180013186
0x18001310a  xor     edx, edx; Val
0x18001310c  mov     r8d, 1000h; Size
0x180013112  mov     rcx, rax; void *
0x180013115  call    memset_0
0x18001311a  xor     r9d, r9d; lpName
0x18001311d  mov     dword ptr [rdi+54h], 200h
0x180013124  xor     edx, edx; lInitialCount
0x180013126  xor     ecx, ecx; lpSemaphoreAttributes
0x180013128  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001312e  call    cs:__imp_CreateSemaphoreW
0x180013134  mov     [rdi+38h], rax
0x180013138  test    rax, rax
0x18001313b  jnz     short loc_180013147
0x18001313d  call    cs:__imp_GetLastError
0x180013143  mov     ebx, eax
0x180013145  jmp     short loc_180013186
0x180013147  xor     r9d, r9d; lpName
0x18001314a  xor     edx, edx; lInitialCount
0x18001314c  xor     ecx, ecx; lpSemaphoreAttributes
0x18001314e  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180013154  call    cs:__imp_CreateSemaphoreW
0x18001315a  mov     [rdi+30h], rax
0x18001315e  test    rax, rax
0x180013161  jz      short loc_18001313D
0x180013163  mov     edx, 200h; lInitialCount
0x180013168  xor     r9d, r9d; lpName
0x18001316b  mov     r8d, edx; lMaximumCount
0x18001316e  xor     ecx, ecx; lpSemaphoreAttributes
0x180013170  call    cs:__imp_CreateSemaphoreW
0x180013176  mov     [rdi+40h], rax
0x18001317a  test    rax, rax
0x18001317d  jz      short loc_18001313D
0x18001317f  mov     dword ptr [rdi+28h], 1
0x180013186  mov     eax, ebx
0x180013188  mov     rbx, [rsp+28h+arg_0]
0x18001318d  add     rsp, 20h
0x180013191  pop     rdi
0x180013192  retn
```
