# CCompPort::Initialize(void *,ulong)

- ea: `0x1800118b0`
- end: `0x1800119e0`
- name: `?Initialize@CCompPort@@QEAAKPEAXK@Z`
- size: `304`
- prototype: `unsigned int __fastcall(CCompPort *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000179c`
- `0x1800118b0`
- `0x18002f3ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800119b4`
- `KERNEL32!GetLastError` at `0x1800119b4`
- `KERNEL32!GetSystemInfo` at `0x1800118ec`
- `KERNEL32!GetSystemInfo` at `0x1800118ec`
- `KERNEL32!CreateIoCompletionPort` at `0x180011912`
- `KERNEL32!CreateIoCompletionPort` at `0x180011912`
- `KERNEL32!CreateThread` at `0x180011987`
- `KERNEL32!CreateThread` at `0x180011987`

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
0x1800118b0  mov     rax, rsp
0x1800118b3  mov     [rax+8], rbx
0x1800118b7  mov     [rax+10h], rbp
0x1800118bb  mov     [rax+18h], rsi
0x1800118bf  mov     [rax+20h], rdi
0x1800118c3  push    r14
0x1800118c5  sub     rsp, 60h
0x1800118c9  xor     ebx, ebx
0x1800118cb  mov     edi, r8d
0x1800118ce  mov     rbp, rdx
0x1800118d1  mov     rsi, rcx
0x1800118d4  test    r8d, r8d
0x1800118d7  jnz     short loc_1800118FF
0x1800118d9  xorps   xmm0, xmm0
0x1800118dc  lea     rcx, [rax-38h]; lpSystemInfo
0x1800118e0  movups  xmmword ptr [rax-38h], xmm0
0x1800118e4  movups  xmmword ptr [rax-28h], xmm0
0x1800118e8  movups  xmmword ptr [rax-18h], xmm0
0x1800118ec  call    cs:__imp_GetSystemInfo
0x1800118f3  nop     dword ptr [rax+rax+00h]
0x1800118f8  mov     eax, [rsp+68h+var_18]
0x1800118fc  lea     edi, [rax+rax]
0x1800118ff  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011903  mov     [rsi+40h], rbp
0x180011907  mov     rcx, r14; FileHandle
0x18001190a  mov     r9d, edi; NumberOfConcurrentThreads
0x18001190d  xor     r8d, r8d; CompletionKey
0x180011910  xor     edx, edx; ExistingCompletionPort
0x180011912  call    cs:__imp_CreateIoCompletionPort
0x180011919  nop     dword ptr [rax+rax+00h]
0x18001191e  mov     [rsi+28h], rax
0x180011922  test    rax, rax
0x180011925  jz      loc_1800119B4
0x18001192b  mov     ebp, edi
0x18001192d  lea     eax, [r14+9]
0x180011931  mul     rbp
0x180011934  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001193b  cmovo   rax, r14
0x18001193f  mov     rcx, rax; unsigned __int64
0x180011942  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180011947  mov     [rsi+30h], rax
0x18001194b  test    rax, rax
0x18001194e  jnz     short loc_180011955
0x180011950  lea     ebx, [rax+8]
0x180011953  jmp     short loc_1800119C2
0x180011955  lea     r8, ds:0[rbp*8]; Size
0x18001195d  xor     edx, edx; Val
0x18001195f  mov     rcx, rax; void *
0x180011962  call    memset_0
0x180011967  mov     ebp, ebx
0x180011969  test    edi, edi
0x18001196b  jz      short loc_1800119C2
0x18001196d  mov     r14, rbx
0x180011970  mov     [rsp+68h+lpThreadId], rbx; lpThreadId
0x180011975  lea     r8, ?_Worker@CCompPort@@CAKPEAX@Z; lpStartAddress
0x18001197c  mov     r9, rsi; lpParameter
0x18001197f  mov     [rsp+68h+dwCreationFlags], ebx; dwCreationFlags
0x180011983  xor     edx, edx; dwStackSize
0x180011985  xor     ecx, ecx; lpThreadAttributes
0x180011987  call    cs:__imp_CreateThread
0x18001198e  nop     dword ptr [rax+rax+00h]
0x180011993  mov     rcx, [rsi+30h]
0x180011997  mov     [r14+rcx], rax
0x18001199b  mov     rax, [rsi+30h]
0x18001199f  cmp     [r14+rax], rbx
0x1800119a3  jz      short loc_1800119B4
0x1800119a5  inc     dword ptr [rsi+38h]
0x1800119a8  inc     ebp
0x1800119aa  add     r14, 8
0x1800119ae  cmp     ebp, edi
0x1800119b0  jb      short loc_180011970
0x1800119b2  jmp     short loc_1800119C2
0x1800119b4  call    cs:__imp_GetLastError
0x1800119bb  nop     dword ptr [rax+rax+00h]
0x1800119c0  mov     ebx, eax
0x1800119c2  lea     r11, [rsp+68h+var_8]
0x1800119c7  mov     eax, ebx
0x1800119c9  mov     rbx, [r11+10h]
0x1800119cd  mov     rbp, [r11+18h]
0x1800119d1  mov     rsi, [r11+20h]
0x1800119d5  mov     rdi, [r11+28h]
0x1800119d9  mov     rsp, r11
0x1800119dc  pop     r14
0x1800119de  retn
```
