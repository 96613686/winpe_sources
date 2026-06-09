# Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)

- ea: `0x18007b1a8`
- end: `0x18007b298`
- name: `?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z`
- size: `240`
- prototype: `bool(Wsp::Health::ResClient *__hidden this, struct Wsp::Health::Sid *, struct Wsp::Health::Token *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18007ae8c`
- `0x18007bba4`

## callees

- `0x18007a620`
- `0x18007a67c`
- `0x18007a770`
- `0x18007acc8`
- `0x18007b1a8`
- `0x18007bf80`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b1e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b208`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b1c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007b1c2`

## pseudocode

```c
bool __fastcall Wsp::Health::ResClient::GetUserSid(const struct _SID **this, struct Wsp::Health::Sid *a2, void **a3)
{
  HANDLE CurrentThread; // rax
  int v6; // r8d
  unsigned int v7; // eax
  HANDLE CurrentProcess; // rbx
  bool v9; // bl
  const struct _SID **v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = this;
  CurrentThread = GetCurrentThread();
  v7 = Wsp::Health::Token::TryOpenThreadToken((Wsp::Health::Token *)a3, 0x2000Eu, v6, CurrentThread);
  if ( v7 == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    Wsp::Health::Token::Clear((Wsp::Health::Token *)a3);
    if ( !OpenProcessToken(CurrentProcess, 0x2000Eu, a3 + 1) )
      GetLastError();
  }
  else if ( v7 )
  {
    return 0;
  }
  v9 = 0;
  (*(void (__fastcall **)(struct Wsp::Health::Sid *))(*(_QWORD *)a2 + 8LL))(a2);
  v11 = 0;
  if ( (unsigned int)Wsp::Health::Token::GetInformationData((Wsp::Health::Token *)a3) >= 0x10 )
  {
    if ( *v11 )
      v9 = Wsp::Health::Sid::Duplicate(a2, *v11);
  }
  Wsp::Health::LocalHeapPtr<void>::Clear(&v11);
  if ( v9 )
    return *((_QWORD *)a2 + 1) != 0;
  return 0;
}

```

## disassembly

```asm
0x18007b1a8  mov     [rsp+arg_8], rbx
0x18007b1ad  mov     [rsp+arg_10], rsi
0x18007b1b2  mov     [rsp+arg_0], rcx
0x18007b1b7  push    rdi
0x18007b1b8  sub     rsp, 20h
0x18007b1bc  mov     rsi, r8
0x18007b1bf  mov     rdi, rdx
0x18007b1c2  call    cs:__imp_GetCurrentThread
0x18007b1c9  nop     dword ptr [rax+rax+00h]
0x18007b1ce  mov     edx, 2000Eh; unsigned int
0x18007b1d3  mov     rcx, rsi; this
0x18007b1d6  mov     r9, rax; void *
0x18007b1d9  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x18007b1de  cmp     eax, 3F0h
0x18007b1e3  jnz     short loc_18007B226
0x18007b1e5  call    cs:__imp_GetCurrentProcess
0x18007b1ec  nop     dword ptr [rax+rax+00h]
0x18007b1f1  mov     rcx, rsi; this
0x18007b1f4  mov     rbx, rax
0x18007b1f7  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007b1fc  lea     r8, [rsi+8]; TokenHandle
0x18007b200  mov     edx, 2000Eh; DesiredAccess
0x18007b205  mov     rcx, rbx; ProcessHandle
0x18007b208  call    cs:__imp_OpenProcessToken
0x18007b20f  nop     dword ptr [rax+rax+00h]
0x18007b214  test    eax, eax
0x18007b216  jnz     short loc_18007B22A
0x18007b218  call    cs:__imp_GetLastError
0x18007b21f  nop     dword ptr [rax+rax+00h]
0x18007b224  jmp     short loc_18007B22A
0x18007b226  test    eax, eax
0x18007b228  jnz     short loc_18007B285
0x18007b22a  mov     rax, [rdi]
0x18007b22d  mov     rcx, rdi
0x18007b230  xor     bl, bl
0x18007b232  mov     rax, [rax+8]
0x18007b236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b23b  lea     r8, [rsp+28h+arg_0]
0x18007b240  mov     [rsp+28h+arg_0], 0
0x18007b249  mov     rcx, rsi; this
0x18007b24c  call    ?GetInformationData@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAV?$LocalHeapPtr@X@23@@Z; Wsp::Health::Token::GetInformationData(_TOKEN_INFORMATION_CLASS,Wsp::Health::LocalHeapPtr<void> *)
0x18007b251  cmp     eax, 10h
0x18007b254  jb      short loc_18007B26D
0x18007b256  mov     rax, [rsp+28h+arg_0]
0x18007b25b  mov     rdx, [rax]; struct _SID *
0x18007b25e  test    rdx, rdx
0x18007b261  jz      short loc_18007B26D
0x18007b263  mov     rcx, rdi; this
0x18007b266  call    ?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z; Wsp::Health::Sid::Duplicate(_SID const *)
0x18007b26b  mov     bl, al
0x18007b26d  lea     rcx, [rsp+28h+arg_0]
0x18007b272  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18007b277  test    bl, bl
0x18007b279  jz      short loc_18007B285
0x18007b27b  cmp     qword ptr [rdi+8], 0
0x18007b280  setnz   al
0x18007b283  jmp     short loc_18007B287
0x18007b285  xor     al, al
0x18007b287  mov     rbx, [rsp+28h+arg_8]
0x18007b28c  mov     rsi, [rsp+28h+arg_10]
0x18007b291  add     rsp, 20h
0x18007b295  pop     rdi
0x18007b296  retn
```
