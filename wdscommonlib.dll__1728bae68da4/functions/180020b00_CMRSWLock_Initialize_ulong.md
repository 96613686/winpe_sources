# CMRSWLock::Initialize(ulong)

- ea: `0x180020b00`
- end: `0x180020bee`
- name: `?Initialize@CMRSWLock@@QEAAKK@Z`
- size: `238`
- prototype: `unsigned int(CMRSWLock *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000214c`
- `0x180020b00`
- `0x180030362`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020b83`
- `KERNEL32!GetLastError` at `0x180020b83`
- `KERNEL32!CreateSemaphoreW` at `0x180020b6e`
- `KERNEL32!CreateSemaphoreW` at `0x180020ba0`
- `KERNEL32!CreateSemaphoreW` at `0x180020bbf`
- `KERNEL32!CreateSemaphoreW` at `0x180020b6e`
- `KERNEL32!CreateSemaphoreW` at `0x180020ba0`
- `KERNEL32!CreateSemaphoreW` at `0x180020bbf`

## pseudocode

```c
__int64 __fastcall CMRSWLock::Initialize(CMRSWLock *this, unsigned int a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rsi
  unsigned __int64 v5; // rax
  void *v6; // rax
  HANDLE SemaphoreW; // rax
  HANDLE v8; // rax
  HANDLE v9; // rax

  v2 = 0;
  v4 = 512;
  if ( a2 )
    v4 = a2;
  v5 = 8 * v4;
  if ( !is_mul_ok(v4, 8u) )
    v5 = -1;
  v6 = operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 12) = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 8 * v4);
    *((_DWORD *)this + 21) = v4;
    SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
    *((_QWORD *)this + 7) = SemaphoreW;
    if ( SemaphoreW
      && (v8 = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0), (*((_QWORD *)this + 6) = v8) != 0)
      && (v9 = CreateSemaphoreW(0, v4, v4, 0), (*((_QWORD *)this + 8) = v9) != 0) )
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
0x180020b00  mov     [rsp+arg_0], rbx
0x180020b05  mov     [rsp+arg_8], rsi
0x180020b0a  push    rdi
0x180020b0b  sub     rsp, 20h
0x180020b0f  xor     ebx, ebx
0x180020b11  mov     rdi, rcx
0x180020b14  test    edx, edx
0x180020b16  mov     esi, 200h
0x180020b1b  cmovnz  esi, edx
0x180020b1e  lea     rcx, [rbx-1]
0x180020b22  lea     eax, [rbx+8]
0x180020b25  mul     rsi
0x180020b28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020b2f  cmovo   rax, rcx
0x180020b33  mov     rcx, rax; unsigned __int64
0x180020b36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020b3b  mov     [rdi+60h], rax
0x180020b3f  test    rax, rax
0x180020b42  jnz     short loc_180020B4C
0x180020b44  lea     ebx, [rax+8]
0x180020b47  jmp     loc_180020BDB
0x180020b4c  lea     r8, ds:0[rsi*8]; Size
0x180020b54  xor     edx, edx; Val
0x180020b56  mov     rcx, rax; void *
0x180020b59  call    memset_0
0x180020b5e  xor     r9d, r9d; lpName
0x180020b61  mov     [rdi+54h], esi
0x180020b64  xor     edx, edx; lInitialCount
0x180020b66  xor     ecx, ecx; lpSemaphoreAttributes
0x180020b68  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180020b6e  call    cs:__imp_CreateSemaphoreW
0x180020b75  nop     dword ptr [rax+rax+00h]
0x180020b7a  mov     [rdi+38h], rax
0x180020b7e  test    rax, rax
0x180020b81  jnz     short loc_180020B93
0x180020b83  call    cs:__imp_GetLastError
0x180020b8a  nop     dword ptr [rax+rax+00h]
0x180020b8f  mov     ebx, eax
0x180020b91  jmp     short loc_180020BDB
0x180020b93  xor     r9d, r9d; lpName
0x180020b96  xor     edx, edx; lInitialCount
0x180020b98  xor     ecx, ecx; lpSemaphoreAttributes
0x180020b9a  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180020ba0  call    cs:__imp_CreateSemaphoreW
0x180020ba7  nop     dword ptr [rax+rax+00h]
0x180020bac  mov     [rdi+30h], rax
0x180020bb0  test    rax, rax
0x180020bb3  jz      short loc_180020B83
0x180020bb5  xor     r9d, r9d; lpName
0x180020bb8  mov     r8d, esi; lMaximumCount
0x180020bbb  mov     edx, esi; lInitialCount
0x180020bbd  xor     ecx, ecx; lpSemaphoreAttributes
0x180020bbf  call    cs:__imp_CreateSemaphoreW
0x180020bc6  nop     dword ptr [rax+rax+00h]
0x180020bcb  mov     [rdi+40h], rax
0x180020bcf  test    rax, rax
0x180020bd2  jz      short loc_180020B83
0x180020bd4  mov     dword ptr [rdi+28h], 1
0x180020bdb  mov     rsi, [rsp+28h+arg_8]
0x180020be0  mov     eax, ebx
0x180020be2  mov     rbx, [rsp+28h+arg_0]
0x180020be7  add     rsp, 20h
0x180020beb  pop     rdi
0x180020bec  retn
```
