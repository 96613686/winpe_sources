# WinBioCredMgrSrvGetCredentialState

- ea: `0x1800bc1d0`
- end: `0x1800bc498`
- name: `WinBioCredMgrSrvGetCredentialState`
- size: `712`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004808`
- `0x1800048c8`
- `0x180011d24`
- `0x180025d94`
- `0x1800275b4`
- `0x18003ecc8`
- `0x180040600`
- `0x180068f60`
- `0x180069cc8`
- `0x18006fde0`
- `0x1800bbb84`
- `0x1800bc1d0`
- `0x1800bd7d8`
- `0x1800bdc64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc455`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bc252`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800bc252`
- `RPCRT4!RpcRevertToSelf` at `0x1800bc449`
- `RPCRT4!RpcRevertToSelf` at `0x1800bc449`
- `RPCRT4!RpcImpersonateClient` at `0x1800bc2ee`
- `RPCRT4!RpcImpersonateClient` at `0x1800bc2ee`

## pseudocode

```c
__int64 __fastcall WinBioCredMgrSrvGetCredentialState(void *a1, _DWORD *a2, int a3, _DWORD *a4)
{
  CUserContext *v8; // rcx
  unsigned int Credential; // eax
  RPC_STATUS v10; // edi
  unsigned int v11; // r8d
  __int64 v12; // rcx
  unsigned int v13; // ebx
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v16[2]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v17; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v22[128]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v23[256]; // [rsp+190h] [rbp+90h] BYREF

  v15 = -2147467259;
  v20 = 0;
  v19 = 0;
  CCredProvVault::CCredProvVault((CCredProvVault *)v21);
  CActivityMonitor::NotifyClientArrival(0xC0FFFFFF);
  if ( a3 == 1 && a4 && *a2 == 3 && IsValidSid(a2 + 2) )
  {
    if ( CUserContext::OpenContext((CUserContext *)&v19, a1) < 0 )
    {
      v15 = -2146861053;
      goto LABEL_17;
    }
    if ( !CUserContext::IsCredProvEnabled(v8, a2 + 2) )
    {
      v15 = -2146861008;
      goto LABEL_17;
    }
    v16[0] = 0;
    Credential = CCredProvVault::GetCredential((CCredProvVault *)v21, a2 + 2, 0, v16);
    if ( !Credential || Credential == 122 )
    {
      *a4 = 2;
    }
    else
    {
      if ( Credential != 1168 )
      {
        v15 = -2146861007;
        goto LABEL_17;
      }
      *a4 = 1;
    }
    v15 = 0;
  }
  else
  {
    v15 = -2147024809;
  }
LABEL_17:
  v10 = RpcImpersonateClient(0);
  if ( v15 < 0 )
  {
    if ( v15 == -2146861008 )
    {
      v12 = 1510;
      memset(v18, 0, sizeof(v18));
    }
    else
    {
      *(_QWORD *)&v18[0] = &v15;
      v12 = 1511;
      memset((char *)v18 + 8, 0, 24);
    }
  }
  else
  {
    memset_0(v22, 0, sizeof(v22));
    *(_QWORD *)v16 = v22;
    memset_0(v23, 0, sizeof(v23));
    v17 = v23;
    GetTextSid(a2 + 2, v22);
    GetSIDUserName(a2 + 2, v23, v11);
    *(_QWORD *)&v18[0] = v16;
    v12 = 1508;
    *((_QWORD *)&v18[0] + 1) = &v17;
    v18[1] = 0;
  }
  _LogEvent(v12, v18);
  if ( !v10 )
    RpcRevertToSelf();
  v13 = v15;
  LocalFree(0);
  CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
  CBioKeyVault::~CBioKeyVault((CBioKeyVault *)v21);
  CUserContext::~CUserContext((CUserContext *)&v19);
  return v13;
}

```

## disassembly

```asm
0x1800bc1d0  push    rbp
0x1800bc1d2  push    rbx
0x1800bc1d3  push    rsi
0x1800bc1d4  push    rdi
0x1800bc1d5  push    r14
0x1800bc1d7  lea     rbp, [rsp-2A0h]
0x1800bc1df  sub     rsp, 3A0h
0x1800bc1e6  mov     rax, cs:__security_cookie
0x1800bc1ed  xor     rax, rsp
0x1800bc1f0  mov     [rbp+2C0h+var_30], rax
0x1800bc1f7  mov     r14, rcx
0x1800bc1fa  mov     [rsp+3C0h+var_3A0], 80004005h
0x1800bc202  xorps   xmm0, xmm0
0x1800bc205  mov     [rsp+3C0h+var_358], 0
0x1800bc20d  lea     rcx, [rsp+3C0h+var_350]; this
0x1800bc212  mov     rdi, r9
0x1800bc215  movdqu  [rsp+3C0h+var_368], xmm0
0x1800bc21b  mov     ebx, r8d
0x1800bc21e  mov     rsi, rdx
0x1800bc221  call    ??0CCredProvVault@@QEAA@XZ; CCredProvVault::CCredProvVault(void)
0x1800bc226  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800bc22b  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x1800bc230  cmp     ebx, 1
0x1800bc233  jnz     loc_1800BC2E4
0x1800bc239  test    rdi, rdi
0x1800bc23c  jz      loc_1800BC2E4
0x1800bc242  cmp     dword ptr [rsi], 3
0x1800bc245  jnz     loc_1800BC2E4
0x1800bc24b  lea     rbx, [rsi+8]
0x1800bc24f  mov     rcx, rbx; pSid
0x1800bc252  call    cs:__imp_IsValidSid
0x1800bc258  test    eax, eax
0x1800bc25a  jz      loc_1800BC2E4
0x1800bc260  mov     rdx, r14; void *
0x1800bc263  lea     rcx, [rsp+3C0h+var_368]; this
0x1800bc268  call    ?OpenContext@CUserContext@@QEAAJPEAX@Z; CUserContext::OpenContext(void *)
0x1800bc26d  mov     [rsp+3C0h+var_3A0], eax
0x1800bc271  test    eax, eax
0x1800bc273  jns     short loc_1800BC27F
0x1800bc275  mov     [rsp+3C0h+var_3A0], 80098003h
0x1800bc27d  jmp     short loc_1800BC2EC
0x1800bc27f  mov     rdx, rbx; void *
0x1800bc282  call    ?IsCredProvEnabled@CUserContext@@QEBAHPEAX@Z; CUserContext::IsCredProvEnabled(void *)
0x1800bc287  test    eax, eax
0x1800bc289  jnz     short loc_1800BC295
0x1800bc28b  mov     [rsp+3C0h+var_3A0], 80098030h
0x1800bc293  jmp     short loc_1800BC2EC
0x1800bc295  lea     r9, [rsp+3C0h+var_398]; unsigned int *
0x1800bc29a  mov     [rsp+3C0h+var_398], 0
0x1800bc2a2  xor     r8d, r8d; unsigned __int8 *
0x1800bc2a5  lea     rcx, [rsp+3C0h+var_350]; this
0x1800bc2aa  mov     rdx, rbx; void *
0x1800bc2ad  call    ?GetCredential@CCredProvVault@@QEAAKPEAXPEAEPEAK@Z; CCredProvVault::GetCredential(void *,uchar *,ulong *)
0x1800bc2b2  test    eax, eax
0x1800bc2b4  jz      short loc_1800BC2D4
0x1800bc2b6  cmp     eax, 7Ah ; 'z'
0x1800bc2b9  jz      short loc_1800BC2D4
0x1800bc2bb  cmp     eax, 490h
0x1800bc2c0  jz      short loc_1800BC2CC
0x1800bc2c2  mov     [rsp+3C0h+var_3A0], 80098031h
0x1800bc2ca  jmp     short loc_1800BC2EC
0x1800bc2cc  mov     dword ptr [rdi], 1
0x1800bc2d2  jmp     short loc_1800BC2DA
0x1800bc2d4  mov     dword ptr [rdi], 2
0x1800bc2da  mov     [rsp+3C0h+var_3A0], 0
0x1800bc2e2  jmp     short loc_1800BC2EC
0x1800bc2e4  mov     [rsp+3C0h+var_3A0], 80070057h
0x1800bc2ec  xor     ecx, ecx; BindingHandle
0x1800bc2ee  call    cs:__imp_RpcImpersonateClient
0x1800bc2f4  mov     ecx, [rsp+3C0h+var_3A0]
0x1800bc2f8  mov     edi, eax
0x1800bc2fa  test    ecx, ecx
0x1800bc2fc  js      short loc_1800BC37C
0x1800bc2fe  xor     edx, edx; Val
0x1800bc300  lea     rcx, [rbp+2C0h+var_330]; void *
0x1800bc304  mov     r8d, 100h; Size
0x1800bc30a  call    memset_0
0x1800bc30f  lea     rax, [rbp+2C0h+var_330]
0x1800bc313  xor     edx, edx; Val
0x1800bc315  mov     r8d, 200h; Size
0x1800bc31b  mov     qword ptr [rsp+3C0h+var_398], rax
0x1800bc320  lea     rcx, [rbp+2C0h+var_230]; void *
0x1800bc327  call    memset_0
0x1800bc32c  lea     rax, [rbp+2C0h+var_230]
0x1800bc333  lea     rdx, [rbp+2C0h+var_330]; unsigned __int16 *
0x1800bc337  mov     [rsp+3C0h+var_390], rax
0x1800bc33c  lea     rcx, [rsi+8]; pSid
0x1800bc340  call    ?GetTextSid@@YAJPEAXPEAGK@Z; GetTextSid(void *,ushort *,ulong)
0x1800bc345  lea     rdx, [rbp+2C0h+var_230]; unsigned __int16 *
0x1800bc34c  lea     rcx, [rsi+8]; void *
0x1800bc350  call    ?GetSIDUserName@@YAJPEAXPEAGK@Z; GetSIDUserName(void *,ushort *,ulong)
0x1800bc355  lea     rax, [rsp+3C0h+var_398]
0x1800bc35a  xorps   xmm0, xmm0
0x1800bc35d  mov     qword ptr [rsp+3C0h+var_388], rax
0x1800bc362  mov     ecx, 5E4h
0x1800bc367  lea     rax, [rsp+3C0h+var_390]
0x1800bc36c  mov     qword ptr [rsp+3C0h+var_388+8], rax
0x1800bc371  movdqu  [rsp+3C0h+var_378], xmm0
0x1800bc377  jmp     loc_1800BC43B
0x1800bc37c  cmp     ecx, 80070005h
0x1800bc382  jz      short loc_1800BC3D5
0x1800bc384  cmp     ecx, 8009030Ch
0x1800bc38a  jz      short loc_1800BC3D5
0x1800bc38c  lea     rdx, [rsp+3C0h+var_388]
0x1800bc391  xorps   xmm0, xmm0
0x1800bc394  cmp     ecx, 80098030h
0x1800bc39a  jnz     short loc_1800BC3B5
0x1800bc39c  xorps   xmm1, xmm1
0x1800bc39f  mov     ecx, 5E6h
0x1800bc3a4  movdqu  [rsp+3C0h+var_378], xmm1
0x1800bc3aa  movdqu  [rsp+3C0h+var_388], xmm0
0x1800bc3b0  jmp     loc_1800BC440
0x1800bc3b5  lea     rax, [rsp+3C0h+var_3A0]
0x1800bc3ba  mov     qword ptr [rsp+3C0h+var_378+8], 0
0x1800bc3c3  mov     qword ptr [rsp+3C0h+var_388], rax
0x1800bc3c8  mov     ecx, 5E7h
0x1800bc3cd  movdqu  [rsp+3C0h+var_388+8], xmm0
0x1800bc3d3  jmp     short loc_1800BC440
0x1800bc3d5  xor     edx, edx; Val
0x1800bc3d7  lea     rcx, [rbp+2C0h+var_330]; void *
0x1800bc3db  mov     r8d, 100h; Size
0x1800bc3e1  call    memset_0
0x1800bc3e6  lea     rax, [rbp+2C0h+var_330]
0x1800bc3ea  xor     edx, edx; Val
0x1800bc3ec  mov     r8d, 200h; Size
0x1800bc3f2  mov     [rsp+3C0h+var_390], rax
0x1800bc3f7  lea     rcx, [rbp+2C0h+var_230]; void *
0x1800bc3fe  call    memset_0
0x1800bc403  lea     rax, [rbp+2C0h+var_230]
0x1800bc40a  mov     qword ptr [rsp+3C0h+var_378+8], 0
0x1800bc413  mov     qword ptr [rsp+3C0h+var_398], rax
0x1800bc418  mov     ecx, 5E5h
0x1800bc41d  lea     rax, [rsp+3C0h+var_390]
0x1800bc422  mov     qword ptr [rsp+3C0h+var_388], rax
0x1800bc427  lea     rax, [rsp+3C0h+var_398]
0x1800bc42c  mov     qword ptr [rsp+3C0h+var_388+8], rax
0x1800bc431  lea     rax, [rsp+3C0h+var_3A0]
0x1800bc436  mov     qword ptr [rsp+3C0h+var_378], rax
0x1800bc43b  lea     rdx, [rsp+3C0h+var_388]
0x1800bc440  call    ?_LogEvent@@YAJKPEAPEAXKW4WBioEventLevel@@@Z; _LogEvent(ulong,void * *,ulong,WBioEventLevel)
0x1800bc445  test    edi, edi
0x1800bc447  jnz     short loc_1800BC44F
0x1800bc449  call    cs:__imp_RpcRevertToSelf
0x1800bc44f  mov     ebx, [rsp+3C0h+var_3A0]
0x1800bc453  xor     ecx, ecx; hMem
0x1800bc455  call    cs:__imp_LocalFree
0x1800bc45b  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800bc460  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x1800bc465  lea     rcx, [rsp+3C0h+var_350]; this
0x1800bc46a  call    ??1CBioKeyVault@@QEAA@XZ; CBioKeyVault::~CBioKeyVault(void)
0x1800bc46f  lea     rcx, [rsp+3C0h+var_368]; this
0x1800bc474  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x1800bc479  mov     eax, ebx
0x1800bc47b  mov     rcx, [rbp+2C0h+var_30]
0x1800bc482  xor     rcx, rsp; StackCookie
0x1800bc485  call    __security_check_cookie
0x1800bc48a  add     rsp, 3A0h
0x1800bc491  pop     r14
0x1800bc493  pop     rdi
0x1800bc494  pop     rsi
0x1800bc495  pop     rbx
0x1800bc496  pop     rbp
0x1800bc497  retn
```
