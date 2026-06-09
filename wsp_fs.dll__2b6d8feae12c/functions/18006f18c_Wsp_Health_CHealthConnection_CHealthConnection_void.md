# Wsp::Health::CHealthConnection::~CHealthConnection(void)

- ea: `0x18006f18c`
- end: `0x18006f27e`
- name: `??1CHealthConnection@Health@Wsp@@UEAA@XZ`
- size: `242`
- prototype: `void __fastcall(Wsp::Health::CHealthConnection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006f530`

## callees

- `0x180002a94`
- `0x18006f05c`
- `0x18006f18c`
- `0x18006f2c4`
- `0x18006f59c`
- `0x18006f70c`
- `0x18006f738`
- `0x180070028`
- `0x180070a94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006f215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006f215`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006f230`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006f230`

## pseudocode

```c
void __fastcall Wsp::Health::CHealthConnection::~CHealthConnection(Wsp::Health::CHealthConnection *this)
{
  Wsp::Health::ResClient *v2; // rbx
  Wsp::Health::ResClient *v3; // rax
  Wsp::Health::ResClient *v4; // rax
  unsigned int v5; // edx
  struct _HHEALTH *v6; // rdx
  void *v7; // rsi
  HANDLE CurrentThread; // rax
  int v9; // r8d
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = &Wsp::Health::CHealthConnection::`vftable';
  v2 = (Wsp::Health::ResClient *)Wsp::Health::g_ptrHealthClient;
  if ( !Wsp::Health::g_ptrHealthClient )
  {
    v3 = (Wsp::Health::ResClient *)operator new(0x160u);
    v4 = (Wsp::Health::ResClient *)Wsp::Health::ResClient::ResClient(v3);
    v2 = v4;
    if ( !v4 )
      goto LABEL_10;
    if ( (int)Wsp::Health::ResClient::Initialize(v4) < 0 )
    {
      Wsp::Health::ResClient::`scalar deleting destructor'(v2, v5);
      goto LABEL_10;
    }
    Wsp::Health::g_ptrHealthClient = v2;
    if ( !v2 )
      goto LABEL_10;
  }
  v6 = (struct _HHEALTH *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    v7 = (void *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      v10[0] = &Wsp::Health::Token::`vftable';
      v10[1] = 0;
      CurrentThread = GetCurrentThread();
      Wsp::Health::Token::TryOpenThreadToken((Wsp::Health::Token *)v10, 0xCu, v9, CurrentThread);
      ImpersonateLoggedOnUser(v7);
      Wsp::Health::ResClient::CloseConnection(v2, *((struct _HHEALTH **)this + 2));
      Wsp::Health::Token::Clear((Wsp::Health::CHealthConnection *)((char *)this + 24));
      Wsp::Health::ImpersonateUser::~ImpersonateUser((Wsp::Health::ImpersonateUser *)v10);
    }
    else
    {
      Wsp::Health::ResClient::CloseConnection(v2, v6);
    }
  }
LABEL_10:
  *((_QWORD *)this + 3) = &Wsp::Health::Token::`vftable';
  Wsp::Health::Token::Clear((Wsp::Health::CHealthConnection *)((char *)this + 24));
  *(_QWORD *)this = &Wsp::Health::RefBase::`vftable';
}

```

## disassembly

```asm
0x18006f18c  push    rbx
0x18006f18e  push    rbp
0x18006f18f  push    rsi
0x18006f190  push    rdi
0x18006f191  sub     rsp, 38h
0x18006f195  lea     rax, ??_7CHealthConnection@Health@Wsp@@6B@; const Wsp::Health::CHealthConnection::`vftable'
0x18006f19c  mov     rdi, rcx
0x18006f19f  mov     [rcx], rax
0x18006f1a2  lea     rbp, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x18006f1a9  mov     rbx, cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006f1b0  test    rbx, rbx
0x18006f1b3  jnz     short loc_18006F1F5
0x18006f1b5  mov     ecx, 160h; Size
0x18006f1ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f1bf  mov     rcx, rax; this
0x18006f1c2  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x18006f1c7  mov     rbx, rax
0x18006f1ca  test    rax, rax
0x18006f1cd  jz      loc_18006F25F
0x18006f1d3  mov     rcx, rax; this
0x18006f1d6  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x18006f1db  test    eax, eax
0x18006f1dd  jns     short loc_18006F1E9
0x18006f1df  mov     rcx, rbx; this
0x18006f1e2  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x18006f1e7  jmp     short loc_18006F25F
0x18006f1e9  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006f1f0  test    rbx, rbx
0x18006f1f3  jz      short loc_18006F25F
0x18006f1f5  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x18006f1f9  test    rdx, rdx
0x18006f1fc  jz      short loc_18006F25F
0x18006f1fe  mov     rsi, [rdi+20h]
0x18006f202  test    rsi, rsi
0x18006f205  jz      short loc_18006F257
0x18006f207  mov     [rsp+58h+var_38], rbp
0x18006f20c  mov     [rsp+58h+var_30], 0
0x18006f215  call    cs:__imp_GetCurrentThread
0x18006f21b  mov     edx, 0Ch; unsigned int
0x18006f220  lea     rcx, [rsp+58h+var_38]; this
0x18006f225  mov     r9, rax; void *
0x18006f228  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x18006f22d  mov     rcx, rsi; hToken
0x18006f230  call    cs:__imp_ImpersonateLoggedOnUser
0x18006f236  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x18006f23a  mov     rcx, rbx; this
0x18006f23d  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x18006f242  lea     rcx, [rdi+18h]; this
0x18006f246  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18006f24b  lea     rcx, [rsp+58h+var_38]; this
0x18006f250  call    ??1ImpersonateUser@Health@Wsp@@QEAA@XZ; Wsp::Health::ImpersonateUser::~ImpersonateUser(void)
0x18006f255  jmp     short loc_18006F25F
0x18006f257  mov     rcx, rbx; this
0x18006f25a  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x18006f25f  lea     rcx, [rdi+18h]; this
0x18006f263  mov     [rcx], rbp
0x18006f266  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18006f26b  lea     rax, ??_7RefBase@Health@Wsp@@6B@; const Wsp::Health::RefBase::`vftable'
0x18006f272  mov     [rdi], rax
0x18006f275  add     rsp, 38h
0x18006f279  pop     rdi
0x18006f27a  pop     rsi
0x18006f27b  pop     rbp
0x18006f27c  pop     rbx
0x18006f27d  retn
```
