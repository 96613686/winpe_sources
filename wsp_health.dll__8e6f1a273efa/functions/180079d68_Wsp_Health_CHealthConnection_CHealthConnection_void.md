# Wsp::Health::CHealthConnection::~CHealthConnection(void)

- ea: `0x180079d68`
- end: `0x180079e6a`
- name: `??1CHealthConnection@Health@Wsp@@UEAA@XZ`
- size: `258`
- prototype: `void __fastcall(Wsp::Health::CHealthConnection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007a130`

## callees

- `0x180002f70`
- `0x180079c48`
- `0x180079d68`
- `0x180079e90`
- `0x18007a1a0`
- `0x18007a67c`
- `0x18007a6b0`
- `0x18007b370`
- `0x18007bf80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079df4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180079df4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180079e15`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180079e15`

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
0x180079d68  push    rbx
0x180079d6a  push    rbp
0x180079d6b  push    rsi
0x180079d6c  push    rdi
0x180079d6d  sub     rsp, 38h
0x180079d71  lea     rax, ??_7CHealthConnection@Health@Wsp@@6B@; const Wsp::Health::CHealthConnection::`vftable'
0x180079d78  mov     rdi, rcx
0x180079d7b  mov     [rcx], rax
0x180079d7e  lea     rbp, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180079d85  mov     rbx, cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180079d8c  test    rbx, rbx
0x180079d8f  jnz     short loc_180079DD4
0x180079d91  mov     ecx, 160h; Size
0x180079d96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079d9b  mov     rcx, rax; this
0x180079d9e  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180079da3  mov     rbx, rax
0x180079da6  test    rax, rax
0x180079da9  jz      loc_180079E4A
0x180079daf  mov     rcx, rax; this
0x180079db2  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180079db7  test    eax, eax
0x180079db9  jns     short loc_180079DC8
0x180079dbb  mov     rcx, rbx; this
0x180079dbe  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x180079dc3  jmp     loc_180079E4A
0x180079dc8  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180079dcf  test    rbx, rbx
0x180079dd2  jz      short loc_180079E4A
0x180079dd4  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180079dd8  test    rdx, rdx
0x180079ddb  jz      short loc_180079E4A
0x180079ddd  mov     rsi, [rdi+20h]
0x180079de1  test    rsi, rsi
0x180079de4  jz      short loc_180079E42
0x180079de6  mov     [rsp+58h+var_38], rbp
0x180079deb  mov     [rsp+58h+var_30], 0
0x180079df4  call    cs:__imp_GetCurrentThread
0x180079dfb  nop     dword ptr [rax+rax+00h]
0x180079e00  mov     edx, 0Ch; unsigned int
0x180079e05  lea     rcx, [rsp+58h+var_38]; this
0x180079e0a  mov     r9, rax; void *
0x180079e0d  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x180079e12  mov     rcx, rsi; hToken
0x180079e15  call    cs:__imp_ImpersonateLoggedOnUser
0x180079e1c  nop     dword ptr [rax+rax+00h]
0x180079e21  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180079e25  mov     rcx, rbx; this
0x180079e28  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180079e2d  lea     rcx, [rdi+18h]; this
0x180079e31  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079e36  lea     rcx, [rsp+58h+var_38]; this
0x180079e3b  call    ??1ImpersonateUser@Health@Wsp@@QEAA@XZ; Wsp::Health::ImpersonateUser::~ImpersonateUser(void)
0x180079e40  jmp     short loc_180079E4A
0x180079e42  mov     rcx, rbx; this
0x180079e45  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180079e4a  lea     rcx, [rdi+18h]; this
0x180079e4e  mov     [rcx], rbp
0x180079e51  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079e56  lea     rax, ??_7RefBase@Health@Wsp@@6B@; const Wsp::Health::RefBase::`vftable'
0x180079e5d  mov     [rdi], rax
0x180079e60  add     rsp, 38h
0x180079e64  pop     rdi
0x180079e65  pop     rsi
0x180079e66  pop     rbp
0x180079e67  pop     rbx
0x180079e68  retn
```
