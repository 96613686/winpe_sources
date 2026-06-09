# CMRSWLock::Initialize(ulong)

- ea: `0x18001fb00`
- end: `0x18001fbee`
- name: `?Initialize@CMRSWLock@@QEAAKK@Z`
- size: `238`
- prototype: `unsigned int(CMRSWLock *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000179c`
- `0x18001fb00`
- `0x18002f3ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001fb83`
- `KERNEL32!GetLastError` at `0x18001fb83`
- `KERNEL32!CreateSemaphoreW` at `0x18001fb6e`
- `KERNEL32!CreateSemaphoreW` at `0x18001fba0`
- `KERNEL32!CreateSemaphoreW` at `0x18001fbbf`
- `KERNEL32!CreateSemaphoreW` at `0x18001fb6e`
- `KERNEL32!CreateSemaphoreW` at `0x18001fba0`
- `KERNEL32!CreateSemaphoreW` at `0x18001fbbf`

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
0x18001fb00  mov     [rsp+arg_0], rbx
0x18001fb05  mov     [rsp+arg_8], rsi
0x18001fb0a  push    rdi
0x18001fb0b  sub     rsp, 20h
0x18001fb0f  xor     ebx, ebx
0x18001fb11  mov     rdi, rcx
0x18001fb14  test    edx, edx
0x18001fb16  mov     esi, 200h
0x18001fb1b  cmovnz  esi, edx
0x18001fb1e  lea     rcx, [rbx-1]
0x18001fb22  lea     eax, [rbx+8]
0x18001fb25  mul     rsi
0x18001fb28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fb2f  cmovo   rax, rcx
0x18001fb33  mov     rcx, rax; unsigned __int64
0x18001fb36  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001fb3b  mov     [rdi+60h], rax
0x18001fb3f  test    rax, rax
0x18001fb42  jnz     short loc_18001FB4C
0x18001fb44  lea     ebx, [rax+8]
0x18001fb47  jmp     loc_18001FBDB
0x18001fb4c  lea     r8, ds:0[rsi*8]; Size
0x18001fb54  xor     edx, edx; Val
0x18001fb56  mov     rcx, rax; void *
0x18001fb59  call    memset_0
0x18001fb5e  xor     r9d, r9d; lpName
0x18001fb61  mov     [rdi+54h], esi
0x18001fb64  xor     edx, edx; lInitialCount
0x18001fb66  xor     ecx, ecx; lpSemaphoreAttributes
0x18001fb68  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001fb6e  call    cs:__imp_CreateSemaphoreW
0x18001fb75  nop     dword ptr [rax+rax+00h]
0x18001fb7a  mov     [rdi+38h], rax
0x18001fb7e  test    rax, rax
0x18001fb81  jnz     short loc_18001FB93
0x18001fb83  call    cs:__imp_GetLastError
0x18001fb8a  nop     dword ptr [rax+rax+00h]
0x18001fb8f  mov     ebx, eax
0x18001fb91  jmp     short loc_18001FBDB
0x18001fb93  xor     r9d, r9d; lpName
0x18001fb96  xor     edx, edx; lInitialCount
0x18001fb98  xor     ecx, ecx; lpSemaphoreAttributes
0x18001fb9a  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001fba0  call    cs:__imp_CreateSemaphoreW
0x18001fba7  nop     dword ptr [rax+rax+00h]
0x18001fbac  mov     [rdi+30h], rax
0x18001fbb0  test    rax, rax
0x18001fbb3  jz      short loc_18001FB83
0x18001fbb5  xor     r9d, r9d; lpName
0x18001fbb8  mov     r8d, esi; lMaximumCount
0x18001fbbb  mov     edx, esi; lInitialCount
0x18001fbbd  xor     ecx, ecx; lpSemaphoreAttributes
0x18001fbbf  call    cs:__imp_CreateSemaphoreW
0x18001fbc6  nop     dword ptr [rax+rax+00h]
0x18001fbcb  mov     [rdi+40h], rax
0x18001fbcf  test    rax, rax
0x18001fbd2  jz      short loc_18001FB83
0x18001fbd4  mov     dword ptr [rdi+28h], 1
0x18001fbdb  mov     rsi, [rsp+28h+arg_8]
0x18001fbe0  mov     eax, ebx
0x18001fbe2  mov     rbx, [rsp+28h+arg_0]
0x18001fbe7  add     rsp, 20h
0x18001fbeb  pop     rdi
0x18001fbec  retn
```
