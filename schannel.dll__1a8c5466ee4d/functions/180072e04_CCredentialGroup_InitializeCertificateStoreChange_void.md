# CCredentialGroup::InitializeCertificateStoreChange(void)

- ea: `0x180072e04`
- end: `0x180073053`
- name: `?InitializeCertificateStoreChange@CCredentialGroup@@AEAAXXZ`
- size: `591`
- prototype: `void __fastcall(CCredentialGroup *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007223c`

## callees

- `0x180021da8`
- `0x18003f740`
- `0x180072e04`
- `0x180073658`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072fd7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007303c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18007303c`
- `CRYPT32!CertOpenStore` at `0x180072ee5`
- `CRYPT32!CertOpenStore` at `0x180072fc5`
- `CRYPT32!CertOpenStore` at `0x180072ee5`
- `CRYPT32!CertOpenStore` at `0x180072fc5`

## pseudocode

```c
void __fastcall CCredentialGroup::InitializeCertificateStoreChange(CCredentialGroup *this)
{
  void *v1; // rdx
  CCredentialGroup *v2; // rbx
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // eax
  HCERTSTORE v6; // rax
  CCredentialGroup *v7; // rcx
  DWORD LastError; // eax
  CCipherMill *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  HCERTSTORE v12; // rax
  CCredentialGroup *v13; // rcx
  DWORD v14; // eax
  CCipherMill *v15; // rcx
  __int64 v16; // rdx
  int v17; // [rsp+40h] [rbp+8h] BYREF

  v1 = (void *)*((_QWORD *)this + 104);
  v17 = 0;
  v2 = this;
  if ( v1 )
  {
    if ( !*((_QWORD *)this + 105) )
    {
      v3 = CCredentialGroup::SubscribeCertStoreChangeNotification(this, v1, (void **)this + 105);
      if ( v3 )
      {
        this = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, v3);
      }
    }
  }
  v4 = (void *)*((_QWORD *)v2 + 110);
  if ( v4 )
  {
    if ( !*((_QWORD *)v2 + 111) )
    {
      v5 = CCredentialGroup::SubscribeCertStoreChangeNotification(this, v4, (void **)v2 + 111);
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, v5);
      }
    }
  }
  if ( !*((_QWORD *)v2 + 112) )
  {
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"ClientAuthIssuer");
    *((_QWORD *)v2 + 112) = v6;
    if ( v6 )
    {
      if ( !*((_QWORD *)v2 + 113) )
      {
        LastError = CCredentialGroup::SubscribeCertStoreChangeNotification(v7, v6, (void **)v2 + 113);
        if ( LastError )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 17;
            goto LABEL_23;
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 16;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, LastError);
      }
    }
  }
  if ( *((_QWORD *)v2 + 106) )
    return;
  v11 = SslImpersonateClient(*((void **)v2 + 102), &v17);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, v11);
    return;
  }
  v12 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x18001u, L"ROOT");
  *((_QWORD *)v2 + 106) = v12;
  if ( v12 )
  {
    if ( !*((_QWORD *)v2 + 107) )
    {
      v14 = CCredentialGroup::SubscribeCertStoreChangeNotification(v13, v12, (void **)v2 + 107);
      if ( v14 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 20;
          goto LABEL_38;
        }
      }
    }
  }
  else
  {
    v14 = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 19;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, v14);
    }
  }
  if ( v17 )
    RevertToSelf();
}

```

## disassembly

```asm
0x180072e04  mov     [rsp+arg_8], rbx
0x180072e09  mov     [rsp+arg_10], rbp
0x180072e0e  push    r14
0x180072e10  sub     rsp, 30h
0x180072e14  mov     rdx, [rcx+340h]; void *
0x180072e1b  lea     r14, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x180072e22  mov     [rsp+38h+arg_0], 0
0x180072e2a  mov     rbx, rcx
0x180072e2d  lea     rbp, WPP_GLOBAL_Control
0x180072e34  test    rdx, rdx
0x180072e37  jz      short loc_180072E75
0x180072e39  lea     r8, [rcx+348h]; void **
0x180072e40  cmp     qword ptr [r8], 0
0x180072e44  jnz     short loc_180072E75
0x180072e46  call    ?SubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAKPEAXPEAPEAX@Z; CCredentialGroup::SubscribeCertStoreChangeNotification(void *,void * *)
0x180072e4b  test    eax, eax
0x180072e4d  jz      short loc_180072E75
0x180072e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e56  cmp     rcx, rbp
0x180072e59  jz      short loc_180072E75
0x180072e5b  test    byte ptr [rcx+1Ch], 1
0x180072e5f  jz      short loc_180072E75
0x180072e61  mov     rcx, [rcx+10h]
0x180072e65  mov     edx, 0Eh
0x180072e6a  mov     r9d, eax
0x180072e6d  mov     r8, r14
0x180072e70  call    WPP_SF_d
0x180072e75  mov     rdx, [rbx+370h]; void *
0x180072e7c  test    rdx, rdx
0x180072e7f  jz      short loc_180072EBD
0x180072e81  lea     r8, [rbx+378h]; void **
0x180072e88  cmp     qword ptr [r8], 0
0x180072e8c  jnz     short loc_180072EBD
0x180072e8e  call    ?SubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAKPEAXPEAPEAX@Z; CCredentialGroup::SubscribeCertStoreChangeNotification(void *,void * *)
0x180072e93  test    eax, eax
0x180072e95  jz      short loc_180072EBD
0x180072e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e9e  cmp     rcx, rbp
0x180072ea1  jz      short loc_180072EBD
0x180072ea3  test    byte ptr [rcx+1Ch], 1
0x180072ea7  jz      short loc_180072EBD
0x180072ea9  mov     rcx, [rcx+10h]
0x180072ead  mov     edx, 0Fh
0x180072eb2  mov     r9d, eax
0x180072eb5  mov     r8, r14
0x180072eb8  call    WPP_SF_d
0x180072ebd  cmp     qword ptr [rbx+380h], 0
0x180072ec5  jnz     loc_180072F55
0x180072ecb  xor     edx, edx; dwEncodingType
0x180072ecd  lea     rax, aClientauthissu; "ClientAuthIssuer"
0x180072ed4  mov     r9d, 20000h; dwFlags
0x180072eda  mov     [rsp+38h+pvPara], rax; pvPara
0x180072edf  xor     r8d, r8d; hCryptProv
0x180072ee2  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180072ee5  call    cs:__imp_CertOpenStore
0x180072eeb  mov     [rbx+380h], rax
0x180072ef2  test    rax, rax
0x180072ef5  jnz     short loc_180072F16
0x180072ef7  call    cs:__imp_GetLastError
0x180072efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f04  cmp     rcx, rbp
0x180072f07  jz      short loc_180072F55
0x180072f09  test    byte ptr [rcx+1Ch], 1
0x180072f0d  jz      short loc_180072F55
0x180072f0f  mov     edx, 10h
0x180072f14  jmp     short loc_180072F46
0x180072f16  lea     r8, [rbx+388h]; void **
0x180072f1d  cmp     qword ptr [r8], 0
0x180072f21  jnz     short loc_180072F55
0x180072f23  mov     rdx, rax; void *
0x180072f26  call    ?SubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAKPEAXPEAPEAX@Z; CCredentialGroup::SubscribeCertStoreChangeNotification(void *,void * *)
0x180072f2b  test    eax, eax
0x180072f2d  jz      short loc_180072F55
0x180072f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f36  cmp     rcx, rbp
0x180072f39  jz      short loc_180072F55
0x180072f3b  test    byte ptr [rcx+1Ch], 1
0x180072f3f  jz      short loc_180072F55
0x180072f41  mov     edx, 11h
0x180072f46  mov     rcx, [rcx+10h]
0x180072f4a  mov     r9d, eax
0x180072f4d  mov     r8, r14
0x180072f50  call    WPP_SF_d
0x180072f55  cmp     qword ptr [rbx+350h], 0
0x180072f5d  jnz     loc_180073042
0x180072f63  mov     rcx, [rbx+330h]; void *
0x180072f6a  lea     rdx, [rsp+38h+arg_0]; int *
0x180072f6f  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x180072f74  test    eax, eax
0x180072f76  jz      short loc_180072FAB
0x180072f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f7f  cmp     rcx, rbp
0x180072f82  jz      loc_180073042
0x180072f88  test    byte ptr [rcx+1Ch], 1
0x180072f8c  jz      loc_180073042
0x180072f92  mov     rcx, [rcx+10h]
0x180072f96  mov     edx, 12h
0x180072f9b  mov     r9d, eax
0x180072f9e  mov     r8, r14
0x180072fa1  call    WPP_SF_d
0x180072fa6  jmp     loc_180073042
0x180072fab  xor     edx, edx; dwEncodingType
0x180072fad  lea     rax, aRoot; "ROOT"
0x180072fb4  mov     r9d, 18001h; dwFlags
0x180072fba  mov     [rsp+38h+pvPara], rax; pvPara
0x180072fbf  xor     r8d, r8d; hCryptProv
0x180072fc2  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180072fc5  call    cs:__imp_CertOpenStore
0x180072fcb  mov     [rbx+350h], rax
0x180072fd2  test    rax, rax
0x180072fd5  jnz     short loc_180072FF6
0x180072fd7  call    cs:__imp_GetLastError
0x180072fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fe4  cmp     rcx, rbp
0x180072fe7  jz      short loc_180073035
0x180072fe9  test    byte ptr [rcx+1Ch], 1
0x180072fed  jz      short loc_180073035
0x180072fef  mov     edx, 13h
0x180072ff4  jmp     short loc_180073026
0x180072ff6  lea     r8, [rbx+358h]; void **
0x180072ffd  cmp     qword ptr [r8], 0
0x180073001  jnz     short loc_180073035
0x180073003  mov     rdx, rax; void *
0x180073006  call    ?SubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAKPEAXPEAPEAX@Z; CCredentialGroup::SubscribeCertStoreChangeNotification(void *,void * *)
0x18007300b  test    eax, eax
0x18007300d  jz      short loc_180073035
0x18007300f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073016  cmp     rcx, rbp
0x180073019  jz      short loc_180073035
0x18007301b  test    byte ptr [rcx+1Ch], 1
0x18007301f  jz      short loc_180073035
0x180073021  mov     edx, 14h
0x180073026  mov     rcx, [rcx+10h]
0x18007302a  mov     r9d, eax
0x18007302d  mov     r8, r14
0x180073030  call    WPP_SF_d
0x180073035  cmp     [rsp+38h+arg_0], 0
0x18007303a  jz      short loc_180073042
0x18007303c  call    cs:__imp_RevertToSelf
0x180073042  mov     rbx, [rsp+38h+arg_8]
0x180073047  mov     rbp, [rsp+38h+arg_10]
0x18007304c  add     rsp, 30h
0x180073050  pop     r14
0x180073052  retn
```
