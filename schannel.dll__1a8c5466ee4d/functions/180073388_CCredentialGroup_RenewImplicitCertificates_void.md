# CCredentialGroup::RenewImplicitCertificates(void)

- ea: `0x180073388`
- end: `0x180073551`
- name: `?RenewImplicitCertificates@CCredentialGroup@@AEAAKXZ`
- size: `457`
- prototype: `unsigned int __fastcall(CCredentialGroup *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180058bbc`

## callees

- `0x180011054`
- `0x180012d10`
- `0x180021da8`
- `0x1800597b0`
- `0x18005a160`
- `0x180070e5c`
- `0x1800728fc`
- `0x180073388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007342d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007342d`
- `CRYPT32!CryptObjectLocatorGetUpdated` at `0x1800733fd`
- `CRYPT32!CryptObjectLocatorGetUpdated` at `0x1800733fd`
- `CRYPT32!CertCloseStore` at `0x180073518`
- `CRYPT32!CertCloseStore` at `0x180073518`
- `CRYPT32!CryptObjectLocatorIsChanged` at `0x1800733c6`
- `CRYPT32!CryptObjectLocatorIsChanged` at `0x1800733c6`
- `CRYPT32!CryptObjectLocatorFree` at `0x180073474`
- `CRYPT32!CryptObjectLocatorFree` at `0x180073474`

## pseudocode

```c
__int64 __fastcall CCredentialGroup::RenewImplicitCertificates(void **this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  void *Updated; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int LastError; // edi
  CCipherMill *v10; // rcx
  __int64 v11; // rdx
  int v13; // r8d
  int v14; // r9d
  unsigned int i; // edi
  unsigned int RenewedCredential; // eax
  _BYTE v17[4]; // [rsp+30h] [rbp-98h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-94h]
  __int64 v19; // [rsp+38h] [rbp-90h]
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+A0h] [rbp-28h] BYREF

  memset_0(v17, 0, 0x70u);
  if ( CryptObjectLocatorIsChanged(this[108]) )
  {
    if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v2, (const EVENT_DESCRIPTOR *)&LocatorGetUpdatedStart, v3, v4, &v21);
    Updated = CryptObjectLocatorGetUpdated(this[108]);
    if ( (Microsoft_Windows_Schannel_EventsEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v5, (const EVENT_DESCRIPTOR *)&LocatorGetUpdatedStop, v7, v8, &v21);
    if ( !Updated )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v11 = 25;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids, LastError);
      return LastError;
    }
    CryptObjectLocatorFree(this[108]);
    this[108] = Updated;
    LastError = LoadCertificatesFromLocator(Updated, (struct LSA_SCHANNEL_CRED *)v17, v13, v14);
    if ( LastError )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v11 = 26;
      goto LABEL_10;
    }
    for ( i = 0; i < v18; ++i )
    {
      RenewedCredential = CCredentialGroup::CreateRenewedCredential(
                            (CCredentialGroup *)this,
                            (struct LSA_SCHANNEL_SUB_CRED *)(v19 + 56LL * i));
      if ( RenewedCredential
        && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids,
          RenewedCredential);
      }
    }
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
    FreeSchannelCred((struct LSA_SCHANNEL_CRED *)v17, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180073388  mov     [rsp+arg_8], rbx
0x18007338d  mov     [rsp+arg_10], rsi
0x180073392  push    rdi
0x180073393  sub     rsp, 0C0h
0x18007339a  mov     rax, cs:__security_cookie
0x1800733a1  xor     rax, rsp
0x1800733a4  mov     [rsp+0C8h+var_18], rax
0x1800733ac  xor     edx, edx; Val
0x1800733ae  mov     rsi, rcx
0x1800733b1  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800733b6  lea     r8d, [rdx+70h]; Size
0x1800733ba  call    memset_0
0x1800733bf  mov     rcx, [rsi+360h]
0x1800733c6  call    cs:__imp_?CryptObjectLocatorIsChanged@@YAHPEAX@Z; CryptObjectLocatorIsChanged(void *)
0x1800733cc  test    eax, eax
0x1800733ce  jz      loc_18007352A
0x1800733d4  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x1800733db  jz      short loc_1800733F6
0x1800733dd  lea     rax, [rsp+0C8h+var_28]
0x1800733e5  lea     rdx, LocatorGetUpdatedStart; int
0x1800733ec  mov     [rsp+0C8h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x1800733f1  call    McGenEventWrite_EventWriteTransfer
0x1800733f6  mov     rcx, [rsi+360h]
0x1800733fd  call    cs:__imp_?CryptObjectLocatorGetUpdated@@YAPEAXPEAX@Z; CryptObjectLocatorGetUpdated(void *)
0x180073403  test    byte ptr cs:Microsoft_Windows_Schannel_EventsEnableBits, 1
0x18007340a  mov     rbx, rax
0x18007340d  jz      short loc_180073428
0x18007340f  lea     rax, [rsp+0C8h+var_28]
0x180073417  lea     rdx, LocatorGetUpdatedStop; int
0x18007341e  mov     [rsp+0C8h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x180073423  call    McGenEventWrite_EventWriteTransfer
0x180073428  test    rbx, rbx
0x18007342b  jnz     short loc_18007346D
0x18007342d  call    cs:__imp_GetLastError
0x180073433  mov     edi, eax
0x180073435  mov     rcx, cs:WPP_GLOBAL_Control
0x18007343c  lea     rbx, WPP_GLOBAL_Control
0x180073443  cmp     rcx, rbx
0x180073446  jz      short loc_180073466
0x180073448  test    byte ptr [rcx+1Ch], 1
0x18007344c  jz      short loc_180073466
0x18007344e  mov     edx, 19h
0x180073453  mov     rcx, [rcx+10h]
0x180073457  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x18007345e  mov     r9d, edi
0x180073461  call    WPP_SF_d
0x180073466  mov     eax, edi
0x180073468  jmp     loc_18007352C
0x18007346d  mov     rcx, [rsi+360h]
0x180073474  call    cs:__imp_?CryptObjectLocatorFree@@YAXPEAX@Z; CryptObjectLocatorFree(void *)
0x18007347a  lea     rdx, [rsp+0C8h+var_98]; struct LSA_SCHANNEL_CRED *
0x18007347f  mov     [rsi+360h], rbx
0x180073486  mov     rcx, rbx; void *
0x180073489  call    ?LoadCertificatesFromLocator@@YAKPEAXPEAULSA_SCHANNEL_CRED@@@Z; LoadCertificatesFromLocator(void *,LSA_SCHANNEL_CRED *)
0x18007348e  mov     edi, eax
0x180073490  test    eax, eax
0x180073492  jz      short loc_1800734B4
0x180073494  mov     rcx, cs:WPP_GLOBAL_Control
0x18007349b  lea     rbx, WPP_GLOBAL_Control
0x1800734a2  cmp     rcx, rbx
0x1800734a5  jz      short loc_180073466
0x1800734a7  test    byte ptr [rcx+1Ch], 1
0x1800734ab  jz      short loc_180073466
0x1800734ad  mov     edx, 1Ah
0x1800734b2  jmp     short loc_180073453
0x1800734b4  xor     edi, edi
0x1800734b6  cmp     [rsp+0C8h+var_94], edi
0x1800734ba  jbe     short loc_18007350C
0x1800734bc  lea     rbx, WPP_GLOBAL_Control
0x1800734c3  mov     eax, edi
0x1800734c5  mov     rcx, rsi; this
0x1800734c8  imul    rdx, rax, 38h ; '8'
0x1800734cc  add     rdx, [rsp+0C8h+var_90]; struct LSA_SCHANNEL_SUB_CRED *
0x1800734d1  call    ?CreateRenewedCredential@CCredentialGroup@@AEAAKPEAULSA_SCHANNEL_SUB_CRED@@@Z; CCredentialGroup::CreateRenewedCredential(LSA_SCHANNEL_SUB_CRED *)
0x1800734d6  test    eax, eax
0x1800734d8  jz      short loc_180073504
0x1800734da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800734e1  cmp     rcx, rbx
0x1800734e4  jz      short loc_180073504
0x1800734e6  test    byte ptr [rcx+1Ch], 1
0x1800734ea  jz      short loc_180073504
0x1800734ec  mov     rcx, [rcx+10h]
0x1800734f0  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x1800734f7  mov     edx, 1Bh
0x1800734fc  mov     r9d, eax
0x1800734ff  call    WPP_SF_d
0x180073504  inc     edi
0x180073506  cmp     edi, [rsp+0C8h+var_94]
0x18007350a  jb      short loc_1800734C3
0x18007350c  mov     rcx, [rsp+0C8h+hCertStore]; hCertStore
0x180073511  test    rcx, rcx
0x180073514  jz      short loc_18007351E
0x180073516  xor     edx, edx; dwFlags
0x180073518  call    cs:__imp_CertCloseStore
0x18007351e  xor     edx, edx; unsigned __int8
0x180073520  lea     rcx, [rsp+0C8h+var_98]; struct LSA_SCHANNEL_CRED *
0x180073525  call    ?FreeSchannelCred@@YAXPEAULSA_SCHANNEL_CRED@@E@Z; FreeSchannelCred(LSA_SCHANNEL_CRED *,uchar)
0x18007352a  xor     eax, eax
0x18007352c  mov     rcx, [rsp+0C8h+var_18]
0x180073534  xor     rcx, rsp; StackCookie
0x180073537  call    __security_check_cookie
0x18007353c  lea     r11, [rsp+0C8h+var_8]
0x180073544  mov     rbx, [r11+18h]
0x180073548  mov     rsi, [r11+20h]
0x18007354c  mov     rsp, r11
0x18007354f  pop     rdi
0x180073550  retn
```
