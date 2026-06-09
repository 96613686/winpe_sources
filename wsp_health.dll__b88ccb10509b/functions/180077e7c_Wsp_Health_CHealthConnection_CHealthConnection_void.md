# Wsp::Health::CHealthConnection::~CHealthConnection(void)

- ea: `0x180077e7c`
- end: `0x180077f6e`
- name: `??1CHealthConnection@Health@Wsp@@UEAA@XZ`
- size: `242`
- prototype: `void __fastcall(Wsp::Health::CHealthConnection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800781f0`

## callees

- `0x180002f00`
- `0x180077d68`
- `0x180077e7c`
- `0x180077f90`
- `0x18007825c`
- `0x18007872c`
- `0x180078758`
- `0x180079368`
- `0x180079e54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180077f05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180077f05`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180077f20`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180077f20`

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
0x180077e7c  push    rbx
0x180077e7e  push    rbp
0x180077e7f  push    rsi
0x180077e80  push    rdi
0x180077e81  sub     rsp, 38h
0x180077e85  lea     rax, ??_7CHealthConnection@Health@Wsp@@6B@; const Wsp::Health::CHealthConnection::`vftable'
0x180077e8c  mov     rdi, rcx
0x180077e8f  mov     [rcx], rax
0x180077e92  lea     rbp, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180077e99  mov     rbx, cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180077ea0  test    rbx, rbx
0x180077ea3  jnz     short loc_180077EE5
0x180077ea5  mov     ecx, 160h; Size
0x180077eaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077eaf  mov     rcx, rax; this
0x180077eb2  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180077eb7  mov     rbx, rax
0x180077eba  test    rax, rax
0x180077ebd  jz      loc_180077F4F
0x180077ec3  mov     rcx, rax; this
0x180077ec6  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180077ecb  test    eax, eax
0x180077ecd  jns     short loc_180077ED9
0x180077ecf  mov     rcx, rbx; this
0x180077ed2  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x180077ed7  jmp     short loc_180077F4F
0x180077ed9  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180077ee0  test    rbx, rbx
0x180077ee3  jz      short loc_180077F4F
0x180077ee5  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180077ee9  test    rdx, rdx
0x180077eec  jz      short loc_180077F4F
0x180077eee  mov     rsi, [rdi+20h]
0x180077ef2  test    rsi, rsi
0x180077ef5  jz      short loc_180077F47
0x180077ef7  mov     [rsp+58h+var_38], rbp
0x180077efc  mov     [rsp+58h+var_30], 0
0x180077f05  call    cs:__imp_GetCurrentThread
0x180077f0b  mov     edx, 0Ch; unsigned int
0x180077f10  lea     rcx, [rsp+58h+var_38]; this
0x180077f15  mov     r9, rax; void *
0x180077f18  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x180077f1d  mov     rcx, rsi; hToken
0x180077f20  call    cs:__imp_ImpersonateLoggedOnUser
0x180077f26  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180077f2a  mov     rcx, rbx; this
0x180077f2d  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180077f32  lea     rcx, [rdi+18h]; this
0x180077f36  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180077f3b  lea     rcx, [rsp+58h+var_38]; this
0x180077f40  call    ??1ImpersonateUser@Health@Wsp@@QEAA@XZ; Wsp::Health::ImpersonateUser::~ImpersonateUser(void)
0x180077f45  jmp     short loc_180077F4F
0x180077f47  mov     rcx, rbx; this
0x180077f4a  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180077f4f  lea     rcx, [rdi+18h]; this
0x180077f53  mov     [rcx], rbp
0x180077f56  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180077f5b  lea     rax, ??_7RefBase@Health@Wsp@@6B@; const Wsp::Health::RefBase::`vftable'
0x180077f62  mov     [rdi], rax
0x180077f65  add     rsp, 38h
0x180077f69  pop     rdi
0x180077f6a  pop     rsi
0x180077f6b  pop     rbp
0x180077f6c  pop     rbx
0x180077f6d  retn
```
