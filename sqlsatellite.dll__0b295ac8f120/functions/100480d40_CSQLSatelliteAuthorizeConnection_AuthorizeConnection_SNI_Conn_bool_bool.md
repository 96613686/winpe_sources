# CSQLSatelliteAuthorizeConnection::AuthorizeConnection(SNI_Conn *,bool,bool *)

- ea: `0x100480d40`
- end: `0x100480eac`
- name: `?AuthorizeConnection@CSQLSatelliteAuthorizeConnection@@YAKPEAVSNI_Conn@@_NPEA_N@Z`
- size: `364`
- prototype: `unsigned int __fastcall(CSQLSatelliteAuthorizeConnection *__hidden this, struct SNI_Conn *, bool, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100473a60`

## callees

- `0x1004269b0`
- `0x1004781c0`
- `0x100478670`
- `0x100480a90`
- `0x100480d40`

## import_xrefs

- `KERNEL32!LocalFree` at `0x100480dee`
- `KERNEL32!LocalFree` at `0x100480dee`
- `Secur32!QueryContextAttributesW` at `0x100480e43`
- `Secur32!QueryContextAttributesW` at `0x100480e43`
- `ADVAPI32!EqualSid` at `0x100480daf`
- `ADVAPI32!EqualSid` at `0x100480dc3`
- `ADVAPI32!EqualSid` at `0x100480daf`
- `ADVAPI32!EqualSid` at `0x100480dc3`

## string_xrefs

- `0x100480e66`: `AuthorizeSecurityContextForAppContainer Failed. \n`
- `0x100480d7e`: `SNIGetInfo() failed while retrieving named pipe owner sid for SNI connection 0x%p.\n`

## pseudocode

```c
void __fastcall CSQLSatelliteAuthorizeConnection::AuthorizeConnection(
        CSQLSatelliteAuthorizeConnection *this,
        struct SNI_Conn *a2,
        bool *a3,
        const wchar_t *a4)
{
  PSID v6; // rbp
  PSID v7; // r14
  int v8; // eax
  PSID pSid2[5]; // [rsp+20h] [rbp-28h] BYREF
  PCtxtHandle phContext; // [rsp+60h] [rbp+18h] BYREF
  void *pBuffer; // [rsp+68h] [rbp+20h] BYREF

  if ( (_BYTE)a2 )
  {
    if ( CSQLSatelliteConnection::sm_expectedNamedPipeOwner )
    {
      *a3 = 0;
      if ( (unsigned int)SNIGetInfo((__int64)this, 43, (__int64)pSid2, a4) )
      {
        TracePrintSatellite(
          L"SNIGetInfo() failed while retrieving named pipe owner sid for SNI connection 0x%p.\n",
          this);
      }
      else
      {
        v6 = pSid2[1];
        v7 = pSid2[0];
        if ( EqualSid(CSQLSatelliteConnection::sm_expectedNamedPipeOwner, pSid2[0])
          || EqualSid(CSQLSatelliteConnection::sm_adminGroupSid, v7) )
        {
          *a3 = 1;
        }
        else
        {
          TracePrintSatellite(L"Authorization Failed for connection 0x%p.\n", this);
        }
        if ( v6 )
          LocalFree(v6);
      }
      return;
    }
LABEL_19:
    *a3 = 1;
    return;
  }
  if ( !this || !CSQLSatelliteConnection::sm_expectedNamedPipeOwner )
    goto LABEL_19;
  *a3 = 0;
  phContext = 0;
  if ( !(unsigned int)SNIGetInfo((__int64)this, 35, (__int64)&phContext, a4)
    && !QueryContextAttributesW(phContext, 0x12u, &pBuffer) )
  {
    v8 = AuthorizeSecurityContextForAppContainer(pBuffer, a3);
    if ( v8 < 0 )
    {
      _mm_lfence();
      FireTraceEvent(1, (unsigned int)v8, 0, L"AuthorizeSecurityContextForAppContainer Failed. \n");
    }
  }
}

```

## disassembly

```asm
0x100480d40  push    rbx
0x100480d42  push    rsi
0x100480d43  push    rdi
0x100480d44  sub     rsp, 30h
0x100480d48  mov     rdi, r8
0x100480d4b  mov     rsi, rcx
0x100480d4e  test    dl, dl
0x100480d50  jz      loc_100480E03
0x100480d56  xor     ebx, ebx
0x100480d58  cmp     cs:?sm_expectedNamedPipeOwner@CSQLSatelliteConnection@@2PEAXEA, rbx; void * CSQLSatelliteConnection::sm_expectedNamedPipeOwner
0x100480d5f  jz      loc_100480E9E
0x100480d65  mov     [r8], bl
0x100480d68  lea     edx, [rbx+2Bh]
0x100480d6b  lea     r8, [rsp+48h+pSid2]
0x100480d70  call    SNIGetInfo
0x100480d75  mov     ebx, eax
0x100480d77  test    eax, eax
0x100480d79  jz      short loc_100480D91
0x100480d7b  mov     rdx, rsi
0x100480d7e  lea     rcx, aSnigetinfoFail; "SNIGetInfo() failed while retrieving na"...
0x100480d85  add     rsp, 30h
0x100480d89  pop     rdi
0x100480d8a  pop     rsi
0x100480d8b  pop     rbx
0x100480d8c  jmp     ?TracePrintSatellite@@YAXPEB_WZZ; TracePrintSatellite(wchar_t const *,...)
0x100480d91  mov     rcx, cs:?sm_expectedNamedPipeOwner@CSQLSatelliteConnection@@2PEAXEA; pSid1
0x100480d98  mov     [rsp+48h+arg_0], rbp
0x100480d9d  mov     rbp, [rsp+48h+hMem]
0x100480da2  mov     [rsp+48h+arg_8], r14
0x100480da7  mov     r14, [rsp+48h+pSid2]
0x100480dac  mov     rdx, r14; pSid2
0x100480daf  call    cs:__imp_EqualSid
0x100480db5  test    eax, eax
0x100480db7  jnz     short loc_100480DDE
0x100480db9  mov     rcx, cs:?sm_adminGroupSid@CSQLSatelliteConnection@@2PEAXEA; pSid1
0x100480dc0  mov     rdx, r14; pSid2
0x100480dc3  call    cs:__imp_EqualSid
0x100480dc9  test    eax, eax
0x100480dcb  jnz     short loc_100480DDE
0x100480dcd  mov     rdx, rsi
0x100480dd0  lea     rcx, aAuthorizationF; "Authorization Failed for connection 0x%"...
0x100480dd7  call    ?TracePrintSatellite@@YAXPEB_WZZ; TracePrintSatellite(wchar_t const *,...)
0x100480ddc  jmp     short loc_100480DE1
0x100480dde  mov     byte ptr [rdi], 1
0x100480de1  mov     r14, [rsp+48h+arg_8]
0x100480de6  test    rbp, rbp
0x100480de9  jz      short loc_100480DF4
0x100480deb  mov     rcx, rbp; hMem
0x100480dee  call    cs:__imp_LocalFree
0x100480df4  mov     rbp, [rsp+48h+arg_0]
0x100480df9  mov     eax, ebx
0x100480dfb  add     rsp, 30h
0x100480dff  pop     rdi
0x100480e00  pop     rsi
0x100480e01  pop     rbx
0x100480e02  retn
0x100480e03  test    rsi, rsi
0x100480e06  jz      loc_100480E9C
0x100480e0c  cmp     cs:?sm_expectedNamedPipeOwner@CSQLSatelliteConnection@@2PEAXEA, 0; void * CSQLSatelliteConnection::sm_expectedNamedPipeOwner
0x100480e14  jz      loc_100480E9C
0x100480e1a  xor     ebx, ebx
0x100480e1c  mov     byte ptr [r8], 0
0x100480e20  lea     r8, [rsp+48h+phContext]
0x100480e25  mov     [rsp+48h+phContext], rbx
0x100480e2a  lea     edx, [rbx+23h]
0x100480e2d  call    SNIGetInfo
0x100480e32  test    eax, eax
0x100480e34  jnz     short loc_100480EA4
0x100480e36  mov     rcx, [rsp+48h+phContext]; phContext
0x100480e3b  lea     r8, [rsp+48h+pBuffer]; pBuffer
0x100480e40  lea     edx, [rbx+12h]; ulAttribute
0x100480e43  call    cs:__imp_QueryContextAttributesW
0x100480e49  test    eax, eax
0x100480e4b  jnz     short loc_100480EA4
0x100480e4d  mov     rcx, [rsp+48h+pBuffer]
0x100480e52  mov     rdx, rdi
0x100480e55  call    AuthorizeSecurityContextForAppContainer
0x100480e5a  mov     ebx, eax
0x100480e5c  test    eax, eax
0x100480e5e  jns     short loc_100480E78
0x100480e60  lfence
0x100480e63  xor     r8d, r8d
0x100480e66  lea     r9, aAuthorizesecur_0; "AuthorizeSecurityContextForAppContainer"...
0x100480e6d  mov     edx, eax
0x100480e6f  lea     ecx, [r8+1]
0x100480e73  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x100480e78  mov     ecx, ebx
0x100480e7a  and     ecx, 0FFFF0000h
0x100480e80  cmp     ecx, 80070000h
0x100480e86  jz      short loc_100480E91
0x100480e88  mov     eax, 0FFFFFFFFh
0x100480e8d  test    ebx, ebx
0x100480e8f  jnz     short loc_100480EA4
0x100480e91  movzx   eax, bx
0x100480e94  add     rsp, 30h
0x100480e98  pop     rdi
0x100480e99  pop     rsi
0x100480e9a  pop     rbx
0x100480e9b  retn
0x100480e9c  xor     ebx, ebx
0x100480e9e  mov     byte ptr [r8], 1
0x100480ea2  mov     eax, ebx
0x100480ea4  add     rsp, 30h
0x100480ea8  pop     rdi
0x100480ea9  pop     rsi
0x100480eaa  pop     rbx
0x100480eab  retn
```
