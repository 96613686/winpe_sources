# WinBioCredMgrSrvRemoveCredential

- ea: `0x1800bca60`
- end: `0x1800bcd79`
- name: `WinBioCredMgrSrvRemoveCredential`
- size: `793`
- prototype: `__int64 __fastcall(void *, _DWORD *, int)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004808`
- `0x1800048c8`
- `0x180011d24`
- `0x180025d94`
- `0x1800275b4`
- `0x18003ecc8`
- `0x180040600`
- `0x180059038`
- `0x180068f60`
- `0x180069cc8`
- `0x18006fde0`
- `0x1800bb8fc`
- `0x1800bbb1c`
- `0x1800bbcec`
- `0x1800bbe9c`
- `0x1800bca60`
- `0x1800bd7d8`
- `0x1800bdfa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcd36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcd36`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bcae5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bcae5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bcb60`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bcb60`
- `RPCRT4!RpcRevertToSelf` at `0x1800bcd1f`
- `RPCRT4!RpcRevertToSelf` at `0x1800bcd1f`
- `RPCRT4!RpcImpersonateClient` at `0x1800bcba3`
- `RPCRT4!RpcImpersonateClient` at `0x1800bcba3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinBioCredMgrSrvRemoveCredential(void *a1, _DWORD *a2, int a3)
{
  PSID v4; // rdi
  CUserContext *v7; // rcx
  int IsLowIntegrity; // eax
  RPC_STATUS v9; // ebx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  __int64 v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int UserSid; // [rsp+20h] [rbp-E0h] BYREF
  PSID pSid1; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v19; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[128]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[256]; // [rsp+190h] [rbp+90h] BYREF

  UserSid = -2147467259;
  v4 = 0;
  pSid1 = 0;
  CCredProvVault::CCredProvVault((CCredProvVault *)v23);
  v22 = 0;
  v21 = 0;
  CActivityMonitor::NotifyClientArrival(0xC0FFFFFF);
  if ( ((a3 + 1) & 0xFFFFFFFD) == 0 && *a2 == 3 && IsValidSid(a2 + 2) )
  {
    if ( (int)CUserContext::OpenContext((CUserContext *)&v21, a1) < 0 || CUserContext::IsProhibitedAccount(v7, a2 + 2) )
    {
      UserSid = -2146861053;
    }
    else
    {
      UserSid = CUserContext::GetUserSid((CUserContext *)&v21, &pSid1);
      IsLowIntegrity = CUserContext::IsLowIntegrity((CUserContext *)&v21);
      v4 = pSid1;
      if ( IsLowIntegrity
        || (unsigned int)CUserContext::IsAppContainer((CUserContext *)&v21)
        || !(unsigned int)CUserContext::IsAdmin((CUserContext *)&v21) && !EqualSid(v4, a2 + 2) )
      {
        UserSid = -2147024891;
      }
      else if ( CCredProvVault::RemoveCredential((CCredProvVault *)v23, a2 + 2) )
      {
        UserSid = -2146861007;
      }
    }
  }
  else
  {
    UserSid = -2147024809;
  }
  v9 = RpcImpersonateClient(0);
  if ( UserSid < 0 )
  {
    if ( UserSid == -2147024891 || UserSid == -2146893044 )
    {
      memset_0(v24, 0, sizeof(v24));
      v19 = v24;
      memset_0(v25, 0, sizeof(v25));
      pSid1 = v25;
      if ( v4 )
      {
        GetTextSid(v4, v24, v13);
        GetSIDUserName(v4, v25, v14);
      }
      *(_QWORD *)&v20[0] = &v19;
      v12 = 1505;
      *((_QWORD *)&v20[0] + 1) = &pSid1;
      v20[1] = (unsigned __int64)&UserSid;
    }
    else if ( UserSid == -2146861008 )
    {
      v12 = 1506;
      memset(v20, 0, sizeof(v20));
    }
    else
    {
      *(_QWORD *)&v20[0] = &UserSid;
      v12 = 1507;
      memset((char *)v20 + 8, 0, 24);
    }
  }
  else
  {
    memset_0(v24, 0, sizeof(v24));
    pSid1 = v24;
    memset_0(v25, 0, sizeof(v25));
    v19 = v25;
    GetTextSid(v4, v24, v10);
    GetSIDUserName(v4, v25, v11);
    *(_QWORD *)&v20[0] = &pSid1;
    v12 = 1504;
    *((_QWORD *)&v20[0] + 1) = &v19;
    v20[1] = 0;
  }
  _LogEvent(v12, v20);
  if ( !v9 )
    RpcRevertToSelf();
  v15 = UserSid;
  CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
  LocalFree(v4);
  CUserContext::~CUserContext((CUserContext *)&v21);
  CBioKeyVault::~CBioKeyVault((CBioKeyVault *)v23);
  return v15;
}

```

## disassembly

```asm
0x1800bca60  mov     [rsp-8+arg_10], rbx
0x1800bca65  mov     [rsp-8+arg_18], rsi
0x1800bca6a  push    rbp
0x1800bca6b  push    rdi
0x1800bca6c  push    r14
0x1800bca6e  lea     rbp, [rsp-2A0h]
0x1800bca76  sub     rsp, 3A0h
0x1800bca7d  mov     rax, cs:__security_cookie
0x1800bca84  xor     rax, rsp
0x1800bca87  mov     [rbp+2B0h+var_20], rax
0x1800bca8e  mov     r14, rcx
0x1800bca91  mov     [rsp+3B0h+var_390], 80004005h
0x1800bca99  xor     edi, edi
0x1800bca9b  lea     rcx, [rsp+3B0h+var_340]; this
0x1800bcaa0  mov     [rsp+3B0h+pSid1], rdi
0x1800bcaa5  mov     ebx, r8d
0x1800bcaa8  mov     rsi, rdx
0x1800bcaab  call    ??0CCredProvVault@@QEAA@XZ; CCredProvVault::CCredProvVault(void)
0x1800bcab0  xorps   xmm0, xmm0
0x1800bcab3  mov     [rsp+3B0h+var_348], edi
0x1800bcab7  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800bcabc  movdqu  [rsp+3B0h+var_358], xmm0
0x1800bcac2  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x1800bcac7  lea     eax, [rbx+1]
0x1800bcaca  test    eax, 0FFFFFFFDh
0x1800bcacf  jnz     loc_1800BCB99
0x1800bcad5  cmp     dword ptr [rsi], 3
0x1800bcad8  jnz     loc_1800BCB99
0x1800bcade  lea     rbx, [rsi+8]
0x1800bcae2  mov     rcx, rbx; pSid
0x1800bcae5  call    cs:__imp_IsValidSid
0x1800bcaeb  test    eax, eax
0x1800bcaed  jz      loc_1800BCB99
0x1800bcaf3  mov     rdx, r14; void *
0x1800bcaf6  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcafb  call    ?OpenContext@CUserContext@@QEAAJPEAX@Z; CUserContext::OpenContext(void *)
0x1800bcb00  mov     [rsp+3B0h+var_390], eax
0x1800bcb04  test    eax, eax
0x1800bcb06  js      loc_1800BCB8F
0x1800bcb0c  mov     rdx, rbx; void *
0x1800bcb0f  call    ?IsProhibitedAccount@CUserContext@@QEBAHPEAX@Z; CUserContext::IsProhibitedAccount(void *)
0x1800bcb14  test    eax, eax
0x1800bcb16  jnz     short loc_1800BCB8F
0x1800bcb18  lea     rdx, [rsp+3B0h+pSid1]; void **
0x1800bcb1d  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcb22  call    ?GetUserSid@CUserContext@@QEBAJPEAPEAX@Z; CUserContext::GetUserSid(void * *)
0x1800bcb27  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcb2c  mov     [rsp+3B0h+var_390], eax
0x1800bcb30  call    ?IsLowIntegrity@CUserContext@@QEBAHXZ; CUserContext::IsLowIntegrity(void)
0x1800bcb35  mov     rdi, [rsp+3B0h+pSid1]
0x1800bcb3a  test    eax, eax
0x1800bcb3c  jnz     short loc_1800BCB85
0x1800bcb3e  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcb43  call    ?IsAppContainer@CUserContext@@QEBAHXZ; CUserContext::IsAppContainer(void)
0x1800bcb48  test    eax, eax
0x1800bcb4a  jnz     short loc_1800BCB85
0x1800bcb4c  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcb51  call    ?IsAdmin@CUserContext@@QEBAHXZ; CUserContext::IsAdmin(void)
0x1800bcb56  test    eax, eax
0x1800bcb58  jnz     short loc_1800BCB6A
0x1800bcb5a  mov     rdx, rbx; pSid2
0x1800bcb5d  mov     rcx, rdi; pSid1
0x1800bcb60  call    cs:__imp_EqualSid
0x1800bcb66  test    eax, eax
0x1800bcb68  jz      short loc_1800BCB85
0x1800bcb6a  mov     rdx, rbx; void *
0x1800bcb6d  lea     rcx, [rsp+3B0h+var_340]; this
0x1800bcb72  call    ?RemoveCredential@CCredProvVault@@QEAAKPEAX@Z; CCredProvVault::RemoveCredential(void *)
0x1800bcb77  test    eax, eax
0x1800bcb79  jz      short loc_1800BCBA1
0x1800bcb7b  mov     [rsp+3B0h+var_390], 80098031h
0x1800bcb83  jmp     short loc_1800BCBA1
0x1800bcb85  mov     [rsp+3B0h+var_390], 80070005h
0x1800bcb8d  jmp     short loc_1800BCBA1
0x1800bcb8f  mov     [rsp+3B0h+var_390], 80098003h
0x1800bcb97  jmp     short loc_1800BCBA1
0x1800bcb99  mov     [rsp+3B0h+var_390], 80070057h
0x1800bcba1  xor     ecx, ecx; BindingHandle
0x1800bcba3  call    cs:__imp_RpcImpersonateClient
0x1800bcba9  mov     ecx, [rsp+3B0h+var_390]
0x1800bcbad  mov     ebx, eax
0x1800bcbaf  test    ecx, ecx
0x1800bcbb1  js      short loc_1800BCC2F
0x1800bcbb3  xor     edx, edx; Val
0x1800bcbb5  lea     rcx, [rbp+2B0h+var_320]; void *
0x1800bcbb9  mov     r8d, 100h; Size
0x1800bcbbf  call    memset_0
0x1800bcbc4  lea     rax, [rbp+2B0h+var_320]
0x1800bcbc8  xor     edx, edx; Val
0x1800bcbca  mov     r8d, 200h; Size
0x1800bcbd0  mov     [rsp+3B0h+pSid1], rax
0x1800bcbd5  lea     rcx, [rbp+2B0h+var_220]; void *
0x1800bcbdc  call    memset_0
0x1800bcbe1  lea     rax, [rbp+2B0h+var_220]
0x1800bcbe8  mov     rcx, rdi; pSid
0x1800bcbeb  lea     rdx, [rbp+2B0h+var_320]; unsigned __int16 *
0x1800bcbef  mov     [rsp+3B0h+var_380], rax
0x1800bcbf4  call    ?GetTextSid@@YAJPEAXPEAGK@Z; GetTextSid(void *,ushort *,ulong)
0x1800bcbf9  lea     rdx, [rbp+2B0h+var_220]; unsigned __int16 *
0x1800bcc00  mov     rcx, rdi; void *
0x1800bcc03  call    ?GetSIDUserName@@YAJPEAXPEAGK@Z; GetSIDUserName(void *,ushort *,ulong)
0x1800bcc08  lea     rax, [rsp+3B0h+pSid1]
0x1800bcc0d  xorps   xmm0, xmm0
0x1800bcc10  mov     qword ptr [rsp+3B0h+var_378], rax
0x1800bcc15  mov     ecx, 5E0h
0x1800bcc1a  lea     rax, [rsp+3B0h+var_380]
0x1800bcc1f  mov     qword ptr [rsp+3B0h+var_378+8], rax
0x1800bcc24  movdqu  [rsp+3B0h+var_368], xmm0
0x1800bcc2a  jmp     loc_1800BCD11
0x1800bcc2f  cmp     ecx, 80070005h
0x1800bcc35  jz      short loc_1800BCC8B
0x1800bcc37  cmp     ecx, 8009030Ch
0x1800bcc3d  jz      short loc_1800BCC8B
0x1800bcc3f  lea     rdx, [rsp+3B0h+var_378]
0x1800bcc44  xorps   xmm0, xmm0
0x1800bcc47  cmp     ecx, 80098030h
0x1800bcc4d  jnz     short loc_1800BCC68
0x1800bcc4f  xorps   xmm1, xmm1
0x1800bcc52  mov     ecx, 5E2h
0x1800bcc57  movdqu  [rsp+3B0h+var_368], xmm1
0x1800bcc5d  movdqu  [rsp+3B0h+var_378], xmm0
0x1800bcc63  jmp     loc_1800BCD16
0x1800bcc68  lea     rax, [rsp+3B0h+var_390]
0x1800bcc6d  mov     qword ptr [rsp+3B0h+var_368+8], 0
0x1800bcc76  mov     qword ptr [rsp+3B0h+var_378], rax
0x1800bcc7b  mov     ecx, 5E3h
0x1800bcc80  movdqu  [rsp+3B0h+var_378+8], xmm0
0x1800bcc86  jmp     loc_1800BCD16
0x1800bcc8b  xor     edx, edx; Val
0x1800bcc8d  lea     rcx, [rbp+2B0h+var_320]; void *
0x1800bcc91  mov     r8d, 100h; Size
0x1800bcc97  call    memset_0
0x1800bcc9c  lea     rax, [rbp+2B0h+var_320]
0x1800bcca0  xor     edx, edx; Val
0x1800bcca2  mov     r8d, 200h; Size
0x1800bcca8  mov     [rsp+3B0h+var_380], rax
0x1800bccad  lea     rcx, [rbp+2B0h+var_220]; void *
0x1800bccb4  call    memset_0
0x1800bccb9  lea     rax, [rbp+2B0h+var_220]
0x1800bccc0  mov     [rsp+3B0h+pSid1], rax
0x1800bccc5  test    rdi, rdi
0x1800bccc8  jz      short loc_1800BCCE5
0x1800bccca  lea     rdx, [rbp+2B0h+var_320]; unsigned __int16 *
0x1800bccce  mov     rcx, rdi; pSid
0x1800bccd1  call    ?GetTextSid@@YAJPEAXPEAGK@Z; GetTextSid(void *,ushort *,ulong)
0x1800bccd6  lea     rdx, [rbp+2B0h+var_220]; unsigned __int16 *
0x1800bccdd  mov     rcx, rdi; void *
0x1800bcce0  call    ?GetSIDUserName@@YAJPEAXPEAGK@Z; GetSIDUserName(void *,ushort *,ulong)
0x1800bcce5  lea     rax, [rsp+3B0h+var_380]
0x1800bccea  mov     qword ptr [rsp+3B0h+var_368+8], 0
0x1800bccf3  mov     qword ptr [rsp+3B0h+var_378], rax
0x1800bccf8  mov     ecx, 5E1h
0x1800bccfd  lea     rax, [rsp+3B0h+pSid1]
0x1800bcd02  mov     qword ptr [rsp+3B0h+var_378+8], rax
0x1800bcd07  lea     rax, [rsp+3B0h+var_390]
0x1800bcd0c  mov     qword ptr [rsp+3B0h+var_368], rax
0x1800bcd11  lea     rdx, [rsp+3B0h+var_378]
0x1800bcd16  call    ?_LogEvent@@YAJKPEAPEAXKW4WBioEventLevel@@@Z; _LogEvent(ulong,void * *,ulong,WBioEventLevel)
0x1800bcd1b  test    ebx, ebx
0x1800bcd1d  jnz     short loc_1800BCD25
0x1800bcd1f  call    cs:__imp_RpcRevertToSelf
0x1800bcd25  mov     ebx, [rsp+3B0h+var_390]
0x1800bcd29  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800bcd2e  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x1800bcd33  mov     rcx, rdi; hMem
0x1800bcd36  call    cs:__imp_LocalFree
0x1800bcd3c  lea     rcx, [rsp+3B0h+var_358]; this
0x1800bcd41  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x1800bcd46  lea     rcx, [rsp+3B0h+var_340]; this
0x1800bcd4b  call    ??1CBioKeyVault@@QEAA@XZ; CBioKeyVault::~CBioKeyVault(void)
0x1800bcd50  mov     eax, ebx
0x1800bcd52  mov     rcx, [rbp+2B0h+var_20]
0x1800bcd59  xor     rcx, rsp; StackCookie
0x1800bcd5c  call    __security_check_cookie
0x1800bcd61  lea     r11, [rsp+3B0h+var_10]
0x1800bcd69  mov     rbx, [r11+30h]
0x1800bcd6d  mov     rsi, [r11+38h]
0x1800bcd71  mov     rsp, r11
0x1800bcd74  pop     r14
0x1800bcd76  pop     rdi
0x1800bcd77  pop     rbp
0x1800bcd78  retn
```
