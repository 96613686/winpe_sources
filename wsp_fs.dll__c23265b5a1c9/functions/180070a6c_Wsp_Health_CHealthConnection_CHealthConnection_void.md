# Wsp::Health::CHealthConnection::~CHealthConnection(void)

- ea: `0x180070a6c`
- end: `0x180070b6e`
- name: `??1CHealthConnection@Health@Wsp@@UEAA@XZ`
- size: `258`
- prototype: `void __fastcall(Wsp::Health::CHealthConnection *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070e60`

## callees

- `0x180002af4`
- `0x18007092c`
- `0x180070a6c`
- `0x180070bc0`
- `0x180070ed0`
- `0x18007105c`
- `0x180071090`
- `0x180071a00`
- `0x180072590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180070af8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180070af8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180070b19`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180070b19`

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
0x180070a6c  push    rbx
0x180070a6e  push    rbp
0x180070a6f  push    rsi
0x180070a70  push    rdi
0x180070a71  sub     rsp, 38h
0x180070a75  lea     rax, ??_7CHealthConnection@Health@Wsp@@6B@; const Wsp::Health::CHealthConnection::`vftable'
0x180070a7c  mov     rdi, rcx
0x180070a7f  mov     [rcx], rax
0x180070a82  lea     rbp, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180070a89  mov     rbx, cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180070a90  test    rbx, rbx
0x180070a93  jnz     short loc_180070AD8
0x180070a95  mov     ecx, 160h; Size
0x180070a9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070a9f  mov     rcx, rax; this
0x180070aa2  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180070aa7  mov     rbx, rax
0x180070aaa  test    rax, rax
0x180070aad  jz      loc_180070B4E
0x180070ab3  mov     rcx, rax; this
0x180070ab6  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180070abb  test    eax, eax
0x180070abd  jns     short loc_180070ACC
0x180070abf  mov     rcx, rbx; this
0x180070ac2  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x180070ac7  jmp     loc_180070B4E
0x180070acc  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180070ad3  test    rbx, rbx
0x180070ad6  jz      short loc_180070B4E
0x180070ad8  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180070adc  test    rdx, rdx
0x180070adf  jz      short loc_180070B4E
0x180070ae1  mov     rsi, [rdi+20h]
0x180070ae5  test    rsi, rsi
0x180070ae8  jz      short loc_180070B46
0x180070aea  mov     [rsp+58h+var_38], rbp
0x180070aef  mov     [rsp+58h+var_30], 0
0x180070af8  call    cs:__imp_GetCurrentThread
0x180070aff  nop     dword ptr [rax+rax+00h]
0x180070b04  mov     edx, 0Ch; unsigned int
0x180070b09  lea     rcx, [rsp+58h+var_38]; this
0x180070b0e  mov     r9, rax; void *
0x180070b11  call    ?TryOpenThreadToken@Token@Health@Wsp@@QEAAKKHPEAX@Z; Wsp::Health::Token::TryOpenThreadToken(ulong,int,void *)
0x180070b16  mov     rcx, rsi; hToken
0x180070b19  call    cs:__imp_ImpersonateLoggedOnUser
0x180070b20  nop     dword ptr [rax+rax+00h]
0x180070b25  mov     rdx, [rdi+10h]; struct _HHEALTH *
0x180070b29  mov     rcx, rbx; this
0x180070b2c  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180070b31  lea     rcx, [rdi+18h]; this
0x180070b35  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180070b3a  lea     rcx, [rsp+58h+var_38]; this
0x180070b3f  call    ??1ImpersonateUser@Health@Wsp@@QEAA@XZ; Wsp::Health::ImpersonateUser::~ImpersonateUser(void)
0x180070b44  jmp     short loc_180070B4E
0x180070b46  mov     rcx, rbx; this
0x180070b49  call    ?CloseConnection@ResClient@Health@Wsp@@QEBAJPEAU_HHEALTH@@@Z; Wsp::Health::ResClient::CloseConnection(_HHEALTH *)
0x180070b4e  lea     rcx, [rdi+18h]; this
0x180070b52  mov     [rcx], rbp
0x180070b55  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180070b5a  lea     rax, ??_7RefBase@Health@Wsp@@6B@; const Wsp::Health::RefBase::`vftable'
0x180070b61  mov     [rdi], rax
0x180070b64  add     rsp, 38h
0x180070b68  pop     rdi
0x180070b69  pop     rsi
0x180070b6a  pop     rbp
0x180070b6b  pop     rbx
0x180070b6c  retn
```
