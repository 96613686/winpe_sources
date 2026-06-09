# Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)

- ea: `0x18006fe74`
- end: `0x18006ff4b`
- name: `?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z`
- size: `215`
- prototype: `bool(Wsp::Health::ResClient *__hidden this, struct Wsp::Health::Sid *, struct Wsp::Health::Token *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180070724`

## callees

- `0x18006f6b4`
- `0x18006f70c`
- `0x18006f7fc`
- `0x18006fdd4`
- `0x18006fe74`
- `0x180070a94`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fed2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006feab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006feab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006fec8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006fec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006fe8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006fe8e`

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
0x18006fe74  mov     [rsp+arg_8], rbx
0x18006fe79  mov     [rsp+arg_10], rsi
0x18006fe7e  mov     [rsp+arg_0], rcx
0x18006fe83  push    rdi
0x18006fe84  sub     rsp, 20h
0x18006fe88  mov     rsi, r8
0x18006fe8b  mov     rdi, rdx
0x18006fe8e  call    cs:__imp_GetCurrentThread
0x18006fe94  mov     edx, 2000Eh; unsigned int
0x18006fe99  mov     rcx, rsi; this
0x18006fe9c  mov     r9, rax; void *
0x18006fe9f  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x18006fea4  cmp     eax, 3F0h
0x18006fea9  jnz     short loc_18006FEDA
0x18006feab  call    cs:__imp_GetCurrentProcess
0x18006feb1  mov     rcx, rsi; this
0x18006feb4  mov     rbx, rax
0x18006feb7  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18006febc  lea     r8, [rsi+8]; TokenHandle
0x18006fec0  mov     edx, 2000Eh; DesiredAccess
0x18006fec5  mov     rcx, rbx; ProcessHandle
0x18006fec8  call    cs:__imp_OpenProcessToken
0x18006fece  test    eax, eax
0x18006fed0  jnz     short loc_18006FEDE
0x18006fed2  call    cs:__imp_GetLastError
0x18006fed8  jmp     short loc_18006FEDE
0x18006feda  test    eax, eax
0x18006fedc  jnz     short loc_18006FF39
0x18006fede  mov     rax, [rdi]
0x18006fee1  mov     rcx, rdi
0x18006fee4  xor     bl, bl
0x18006fee6  mov     rax, [rax+8]
0x18006feea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006feef  lea     r8, [rsp+28h+arg_0]
0x18006fef4  mov     [rsp+28h+arg_0], 0
0x18006fefd  mov     rcx, rsi; this
0x18006ff00  call    ?GetInformationData@Token@Health@Wsp@@QEAAKW4_TOKEN_INFORMATION_CLASS@@PEAV?$LocalHeapPtr@X@23@@Z; Wsp::Health::Token::GetInformationData(_TOKEN_INFORMATION_CLASS,Wsp::Health::LocalHeapPtr<void> *)
0x18006ff05  cmp     eax, 10h
0x18006ff08  jb      short loc_18006FF21
0x18006ff0a  mov     rax, [rsp+28h+arg_0]
0x18006ff0f  mov     rdx, [rax]; struct _SID *
0x18006ff12  test    rdx, rdx
0x18006ff15  jz      short loc_18006FF21
0x18006ff17  mov     rcx, rdi; this
0x18006ff1a  call    ?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z; Wsp::Health::Sid::Duplicate(_SID const *)
0x18006ff1f  mov     bl, al
0x18006ff21  lea     rcx, [rsp+28h+arg_0]
0x18006ff26  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18006ff2b  test    bl, bl
0x18006ff2d  jz      short loc_18006FF39
0x18006ff2f  cmp     qword ptr [rdi+8], 0
0x18006ff34  setnz   al
0x18006ff37  jmp     short loc_18006FF3B
0x18006ff39  xor     al, al
0x18006ff3b  mov     rbx, [rsp+28h+arg_8]
0x18006ff40  mov     rsi, [rsp+28h+arg_10]
0x18006ff45  add     rsp, 20h
0x18006ff49  pop     rdi
0x18006ff4a  retn
```
