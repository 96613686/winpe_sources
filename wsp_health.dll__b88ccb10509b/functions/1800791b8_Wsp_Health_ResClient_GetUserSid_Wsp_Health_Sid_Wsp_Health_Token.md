# Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)

- ea: `0x1800791b8`
- end: `0x18007928f`
- name: `?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z`
- size: `215`
- prototype: `bool(Wsp::Health::ResClient *__hidden this, struct Wsp::Health::Sid *, struct Wsp::Health::Token *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180078ec8`
- `0x180079abc`

## callees

- `0x1800786c8`
- `0x18007872c`
- `0x18007881c`
- `0x180078d08`
- `0x1800791b8`
- `0x180079e54`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800791ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800791ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007920c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007920c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800791d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800791d2`

## pseudocode

```c
bool __fastcall Wsp::Health::ResClient::GetUserSid(struct _SID **this, struct Wsp::Health::Sid *a2, void **a3)
{
  HANDLE CurrentThread; // rax
  int v6; // r8d
  unsigned int v7; // eax
  HANDLE CurrentProcess; // rbx
  char v9; // bl
  struct _SID **v11; // [rsp+30h] [rbp+8h] BYREF

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
0x1800791b8  mov     [rsp+arg_8], rbx
0x1800791bd  mov     [rsp+arg_10], rsi
0x1800791c2  mov     [rsp+arg_0], rcx
0x1800791c7  push    rdi
0x1800791c8  sub     rsp, 20h
0x1800791cc  mov     rsi, r8
0x1800791cf  mov     rdi, rdx
0x1800791d2  call    cs:__imp_GetCurrentThread
0x1800791d8  mov     edx, 2000Eh; unsigned int
0x1800791dd  mov     rcx, rsi; this
0x1800791e0  mov     r9, rax; void *
0x1800791e3  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x1800791e8  cmp     eax, 3F0h
0x1800791ed  jnz     short loc_18007921E
0x1800791ef  call    cs:__imp_GetCurrentProcess
0x1800791f5  mov     rcx, rsi; this
0x1800791f8  mov     rbx, rax
0x1800791fb  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079200  lea     r8, [rsi+8]; TokenHandle
0x180079204  mov     edx, 2000Eh; DesiredAccess
0x180079209  mov     rcx, rbx; ProcessHandle
0x18007920c  call    cs:__imp_OpenProcessToken
0x180079212  test    eax, eax
0x180079214  jnz     short loc_180079222
0x180079216  call    cs:__imp_GetLastError
0x18007921c  jmp     short loc_180079222
0x18007921e  test    eax, eax
0x180079220  jnz     short loc_18007927D
0x180079222  mov     rax, [rdi]
0x180079225  mov     rcx, rdi
0x180079228  xor     bl, bl
0x18007922a  mov     rax, [rax+8]
0x18007922e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079233  lea     r8, [rsp+28h+arg_0]
0x180079238  mov     [rsp+28h+arg_0], 0
0x180079241  mov     rcx, rsi; this
0x180079244  call    ?GetInformationData@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAV?$LocalHeapPtr@X@23@@Z; Wsp::Health::Token::GetInformationData(_TOKEN_INFORMATION_CLASS,Wsp::Health::LocalHeapPtr<void> *)
0x180079249  cmp     eax, 10h
0x18007924c  jb      short loc_180079265
0x18007924e  mov     rax, [rsp+28h+arg_0]
0x180079253  mov     rdx, [rax]; struct _SID *
0x180079256  test    rdx, rdx
0x180079259  jz      short loc_180079265
0x18007925b  mov     rcx, rdi; this
0x18007925e  call    ?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z; Wsp::Health::Sid::Duplicate(_SID const *)
0x180079263  mov     bl, al
0x180079265  lea     rcx, [rsp+28h+arg_0]
0x18007926a  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18007926f  test    bl, bl
0x180079271  jz      short loc_18007927D
0x180079273  cmp     qword ptr [rdi+8], 0
0x180079278  setnz   al
0x18007927b  jmp     short loc_18007927F
0x18007927d  xor     al, al
0x18007927f  mov     rbx, [rsp+28h+arg_8]
0x180079284  mov     rsi, [rsp+28h+arg_10]
0x180079289  add     rsp, 20h
0x18007928d  pop     rdi
0x18007928e  retn
```
