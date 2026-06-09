# CCompPort::Initialize(void *,ulong)

- ea: `0x1800124b0`
- end: `0x1800125e0`
- name: `?Initialize@CCompPort@@QEAAKPEAXK@Z`
- size: `304`
- prototype: `unsigned int __fastcall(CCompPort *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000214c`
- `0x1800124b0`
- `0x180030362`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800125b4`
- `KERNEL32!GetLastError` at `0x1800125b4`
- `KERNEL32!GetSystemInfo` at `0x1800124ec`
- `KERNEL32!GetSystemInfo` at `0x1800124ec`
- `KERNEL32!CreateIoCompletionPort` at `0x180012512`
- `KERNEL32!CreateIoCompletionPort` at `0x180012512`
- `KERNEL32!CreateThread` at `0x180012587`
- `KERNEL32!CreateThread` at `0x180012587`

## pseudocode

```c
__int64 __fastcall CCompPort::Initialize(CCompPort *this, void *a2, DWORD a3)
{
  unsigned int v3; // ebx
  DWORD v4; // edi
  HANDLE IoCompletionPort; // rax
  unsigned __int64 v8; // rax
  void *v9; // rax
  int v10; // ebp
  __int64 i; // r14
  struct _SYSTEM_INFO v13; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  v4 = a3;
  if ( !a3 )
  {
    memset(&v13, 0, sizeof(v13));
    GetSystemInfo(&v13);
    v4 = 2 * v13.dwNumberOfProcessors;
  }
  *((_QWORD *)this + 8) = a2;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, v4);
  *((_QWORD *)this + 5) = IoCompletionPort;
  if ( !IoCompletionPort )
    return GetLastError();
  v8 = 8LL * v4;
  if ( !is_mul_ok(v4, 8u) )
    v8 = -1;
  v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 6) = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 8LL * v4);
    v10 = 0;
    if ( !v4 )
      return v3;
    for ( i = 0; ; i += 8 )
    {
      *(_QWORD *)(i + *((_QWORD *)this + 6)) = CreateThread(0, 0, CCompPort::_Worker, this, 0, 0);
      if ( !*(_QWORD *)(i + *((_QWORD *)this + 6)) )
        break;
      ++*((_DWORD *)this + 14);
      if ( ++v10 >= v4 )
        return v3;
    }
    return GetLastError();
  }
  return 8;
}

```

## disassembly

```asm
0x1800124b0  mov     rax, rsp
0x1800124b3  mov     [rax+8], rbx
0x1800124b7  mov     [rax+10h], rbp
0x1800124bb  mov     [rax+18h], rsi
0x1800124bf  mov     [rax+20h], rdi
0x1800124c3  push    r14
0x1800124c5  sub     rsp, 60h
0x1800124c9  xor     ebx, ebx
0x1800124cb  mov     edi, r8d
0x1800124ce  mov     rbp, rdx
0x1800124d1  mov     rsi, rcx
0x1800124d4  test    r8d, r8d
0x1800124d7  jnz     short loc_1800124FF
0x1800124d9  xorps   xmm0, xmm0
0x1800124dc  lea     rcx, [rax-38h]; lpSystemInfo
0x1800124e0  movups  xmmword ptr [rax-38h], xmm0
0x1800124e4  movups  xmmword ptr [rax-28h], xmm0
0x1800124e8  movups  xmmword ptr [rax-18h], xmm0
0x1800124ec  call    cs:__imp_GetSystemInfo
0x1800124f3  nop     dword ptr [rax+rax+00h]
0x1800124f8  mov     eax, [rsp+68h+var_18]
0x1800124fc  lea     edi, [rax+rax]
0x1800124ff  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012503  mov     [rsi+40h], rbp
0x180012507  mov     rcx, r14; FileHandle
0x18001250a  mov     r9d, edi; NumberOfConcurrentThreads
0x18001250d  xor     r8d, r8d; CompletionKey
0x180012510  xor     edx, edx; ExistingCompletionPort
0x180012512  call    cs:__imp_CreateIoCompletionPort
0x180012519  nop     dword ptr [rax+rax+00h]
0x18001251e  mov     [rsi+28h], rax
0x180012522  test    rax, rax
0x180012525  jz      loc_1800125B4
0x18001252b  mov     ebp, edi
0x18001252d  lea     eax, [r14+9]
0x180012531  mul     rbp
0x180012534  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001253b  cmovo   rax, r14
0x18001253f  mov     rcx, rax; unsigned __int64
0x180012542  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012547  mov     [rsi+30h], rax
0x18001254b  test    rax, rax
0x18001254e  jnz     short loc_180012555
0x180012550  lea     ebx, [rax+8]
0x180012553  jmp     short loc_1800125C2
0x180012555  lea     r8, ds:0[rbp*8]; Size
0x18001255d  xor     edx, edx; Val
0x18001255f  mov     rcx, rax; void *
0x180012562  call    memset_0
0x180012567  mov     ebp, ebx
0x180012569  test    edi, edi
0x18001256b  jz      short loc_1800125C2
0x18001256d  mov     r14, rbx
0x180012570  mov     [rsp+68h+lpThreadId], rbx; lpThreadId
0x180012575  lea     r8, ?_Worker@CCompPort@@CAKPEAX@Z; lpStartAddress
0x18001257c  mov     r9, rsi; lpParameter
0x18001257f  mov     [rsp+68h+dwCreationFlags], ebx; dwCreationFlags
0x180012583  xor     edx, edx; dwStackSize
0x180012585  xor     ecx, ecx; lpThreadAttributes
0x180012587  call    cs:__imp_CreateThread
0x18001258e  nop     dword ptr [rax+rax+00h]
0x180012593  mov     rcx, [rsi+30h]
0x180012597  mov     [r14+rcx], rax
0x18001259b  mov     rax, [rsi+30h]
0x18001259f  cmp     [r14+rax], rbx
0x1800125a3  jz      short loc_1800125B4
0x1800125a5  inc     dword ptr [rsi+38h]
0x1800125a8  inc     ebp
0x1800125aa  add     r14, 8
0x1800125ae  cmp     ebp, edi
0x1800125b0  jb      short loc_180012570
0x1800125b2  jmp     short loc_1800125C2
0x1800125b4  call    cs:__imp_GetLastError
0x1800125bb  nop     dword ptr [rax+rax+00h]
0x1800125c0  mov     ebx, eax
0x1800125c2  lea     r11, [rsp+68h+var_8]
0x1800125c7  mov     eax, ebx
0x1800125c9  mov     rbx, [r11+10h]
0x1800125cd  mov     rbp, [r11+18h]
0x1800125d1  mov     rsi, [r11+20h]
0x1800125d5  mov     rdi, [r11+28h]
0x1800125d9  mov     rsp, r11
0x1800125dc  pop     r14
0x1800125de  retn
```
