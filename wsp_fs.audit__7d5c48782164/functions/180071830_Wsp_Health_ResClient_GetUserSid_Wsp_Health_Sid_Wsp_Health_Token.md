# Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)

- ea: `0x180071830`
- end: `0x180071920`
- name: `?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z`
- size: `240`
- prototype: `bool(Wsp::Health::ResClient *__hidden this, struct Wsp::Health::Sid *, struct Wsp::Health::Token *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800721dc`

## callees

- `0x180070ff8`
- `0x18007105c`
- `0x180071150`
- `0x18007178c`
- `0x180071830`
- `0x180072590`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800718a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007186d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007186d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071890`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180071890`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007184a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007184a`

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
0x180071830  mov     [rsp+arg_8], rbx
0x180071835  mov     [rsp+arg_10], rsi
0x18007183a  mov     [rsp+arg_0], rcx
0x18007183f  push    rdi
0x180071840  sub     rsp, 20h
0x180071844  mov     rsi, r8
0x180071847  mov     rdi, rdx
0x18007184a  call    cs:__imp_GetCurrentThread
0x180071851  nop     dword ptr [rax+rax+00h]
0x180071856  mov     edx, 2000Eh; unsigned int
0x18007185b  mov     rcx, rsi; this
0x18007185e  mov     r9, rax; void *
0x180071861  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x180071866  cmp     eax, 3F0h
0x18007186b  jnz     short loc_1800718AE
0x18007186d  call    cs:__imp_GetCurrentProcess
0x180071874  nop     dword ptr [rax+rax+00h]
0x180071879  mov     rcx, rsi; this
0x18007187c  mov     rbx, rax
0x18007187f  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180071884  lea     r8, [rsi+8]; TokenHandle
0x180071888  mov     edx, 2000Eh; DesiredAccess
0x18007188d  mov     rcx, rbx; ProcessHandle
0x180071890  call    cs:__imp_OpenProcessToken
0x180071897  nop     dword ptr [rax+rax+00h]
0x18007189c  test    eax, eax
0x18007189e  jnz     short loc_1800718B2
0x1800718a0  call    cs:__imp_GetLastError
0x1800718a7  nop     dword ptr [rax+rax+00h]
0x1800718ac  jmp     short loc_1800718B2
0x1800718ae  test    eax, eax
0x1800718b0  jnz     short loc_18007190D
0x1800718b2  mov     rax, [rdi]
0x1800718b5  mov     rcx, rdi
0x1800718b8  xor     bl, bl
0x1800718ba  mov     rax, [rax+8]
0x1800718be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718c3  lea     r8, [rsp+28h+arg_0]
0x1800718c8  mov     [rsp+28h+arg_0], 0
0x1800718d1  mov     rcx, rsi; this
0x1800718d4  call    ?GetInformationData@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAV?$LocalHeapPtr@X@23@@Z; Wsp::Health::Token::GetInformationData(_TOKEN_INFORMATION_CLASS,Wsp::Health::LocalHeapPtr<void> *)
0x1800718d9  cmp     eax, 10h
0x1800718dc  jb      short loc_1800718F5
0x1800718de  mov     rax, [rsp+28h+arg_0]
0x1800718e3  mov     rdx, [rax]; struct _SID *
0x1800718e6  test    rdx, rdx
0x1800718e9  jz      short loc_1800718F5
0x1800718eb  mov     rcx, rdi; this
0x1800718ee  call    ?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z; Wsp::Health::Sid::Duplicate(_SID const *)
0x1800718f3  mov     bl, al
0x1800718f5  lea     rcx, [rsp+28h+arg_0]
0x1800718fa  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x1800718ff  test    bl, bl
0x180071901  jz      short loc_18007190D
0x180071903  cmp     qword ptr [rdi+8], 0
0x180071908  setnz   al
0x18007190b  jmp     short loc_18007190F
0x18007190d  xor     al, al
0x18007190f  mov     rbx, [rsp+28h+arg_8]
0x180071914  mov     rsi, [rsp+28h+arg_10]
0x180071919  add     rsp, 20h
0x18007191d  pop     rdi
0x18007191e  retn
```
