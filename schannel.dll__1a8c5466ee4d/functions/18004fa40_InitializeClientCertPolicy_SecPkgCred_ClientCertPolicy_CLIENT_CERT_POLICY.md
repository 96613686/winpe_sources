# InitializeClientCertPolicy(_SecPkgCred_ClientCertPolicy *,CLIENT_CERT_POLICY *)

- ea: `0x18004fa40`
- end: `0x18004fb23`
- name: `?InitializeClientCertPolicy@@YAJPEAU_SecPkgCred_ClientCertPolicy@@PEAUCLIENT_CERT_POLICY@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct _SecPkgCred_ClientCertPolicy *, struct CLIENT_CERT_POLICY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055cc4`

## callees

- `0x18004be74`
- `0x18004fa40`
- `0x18005d4ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004faf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004faf2`
- `CRYPT32!CertOpenStore` at `0x18004faca`
- `CRYPT32!CertOpenStore` at `0x18004faca`

## pseudocode

```c
__int64 __fastcall InitializeClientCertPolicy(struct _SecPkgCred_ClientCertPolicy *a1, struct CLIENT_CERT_POLICY *a2)
{
  const unsigned __int16 *pwszSslCtlIdentifier; // rdx
  LPWSTR pwszSslCtlStoreName; // rax
  PCCTL_CONTEXT CtlInStore; // rax
  HCERTSTORE v8; // rax
  char LastError; // al

  *((_DWORD *)a2 + 4) = a1->dwCertFlags;
  *((_DWORD *)a2 + 5) = a1->dwUrlRetrievalTimeout;
  *((_DWORD *)a2 + 6) = a1->fCheckRevocationFreshnessTime;
  *((_DWORD *)a2 + 7) = a1->dwRevocationFreshnessTime;
  *(GUID *)a2 = a1->guidPolicyId;
  *((_DWORD *)a2 + 8) = a1->fOmitUsageCheck;
  *((_QWORD *)a2 + 5) = 0;
  pwszSslCtlIdentifier = a1->pwszSslCtlIdentifier;
  pwszSslCtlStoreName = a1->pwszSslCtlStoreName;
  if ( pwszSslCtlIdentifier )
  {
    if ( pwszSslCtlStoreName )
    {
      CtlInStore = FindCtlInStore(a1->pwszSslCtlStoreName, pwszSslCtlIdentifier);
      *((_QWORD *)a2 + 5) = CtlInStore;
      if ( CtlInStore )
        return 0;
    }
  }
  else
  {
    if ( !pwszSslCtlStoreName )
      return 0;
    v8 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x24000u, a1->pwszSslCtlStoreName);
    *((_QWORD *)a2 + 6) = v8;
    if ( v8 )
      return 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_373d12f1978338b61962a9e735bda8d8_Traceguids,
        a1->pwszSslCtlStoreName,
        LastError);
    }
  }
  return 2148074253LL;
}

```

## disassembly

```asm
0x18004fa40  mov     [rsp+arg_0], rbx
0x18004fa45  push    rdi
0x18004fa46  sub     rsp, 30h
0x18004fa4a  mov     eax, [rcx+14h]
0x18004fa4d  mov     rbx, rdx
0x18004fa50  mov     [rdx+10h], eax
0x18004fa53  mov     rdi, rcx
0x18004fa56  mov     eax, [rcx+18h]
0x18004fa59  mov     [rdx+14h], eax
0x18004fa5c  mov     eax, [rcx+1Ch]
0x18004fa5f  mov     [rdx+18h], eax
0x18004fa62  mov     eax, [rcx+20h]
0x18004fa65  mov     [rdx+1Ch], eax
0x18004fa68  movups  xmm0, xmmword ptr [rcx+4]
0x18004fa6c  movdqu  xmmword ptr [rdx], xmm0
0x18004fa70  mov     eax, [rcx+24h]
0x18004fa73  mov     [rdx+20h], eax
0x18004fa76  mov     qword ptr [rdx+28h], 0
0x18004fa7e  mov     rdx, [rcx+30h]; unsigned __int16 *
0x18004fa82  mov     rax, [rcx+28h]
0x18004fa86  test    rdx, rdx
0x18004fa89  jz      short loc_18004FAB2
0x18004fa8b  test    rax, rax
0x18004fa8e  jz      loc_18004FB1C
0x18004fa94  mov     rcx, rax; unsigned __int16 *
0x18004fa97  call    ?FindCtlInStore@@YAPEBU_CTL_CONTEXT@@PEBG0@Z; FindCtlInStore(ushort const *,ushort const *)
0x18004fa9c  mov     [rbx+28h], rax
0x18004faa0  test    rax, rax
0x18004faa3  jz      short loc_18004FB1C
0x18004faa5  xor     eax, eax
0x18004faa7  mov     rbx, [rsp+38h+arg_0]
0x18004faac  add     rsp, 30h
0x18004fab0  pop     rdi
0x18004fab1  retn
0x18004fab2  test    rax, rax
0x18004fab5  jz      short loc_18004FAA5
0x18004fab7  xor     edx, edx; dwEncodingType
0x18004fab9  mov     [rsp+38h+pvPara], rax; pvPara
0x18004fabe  mov     r9d, 24000h; dwFlags
0x18004fac4  xor     r8d, r8d; hCryptProv
0x18004fac7  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18004faca  call    cs:__imp_CertOpenStore
0x18004fad0  mov     [rbx+30h], rax
0x18004fad4  test    rax, rax
0x18004fad7  jnz     short loc_18004FAA5
0x18004fad9  mov     rax, cs:WPP_GLOBAL_Control
0x18004fae0  lea     rcx, WPP_GLOBAL_Control
0x18004fae7  cmp     rax, rcx
0x18004faea  jz      short loc_18004FB1C
0x18004faec  test    byte ptr [rax+1Ch], 1
0x18004faf0  jz      short loc_18004FB1C
0x18004faf2  call    cs:__imp_GetLastError
0x18004faf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004faff  lea     r8, WPP_373d12f1978338b61962a9e735bda8d8_Traceguids
0x18004fb06  mov     r9, [rdi+28h]
0x18004fb0a  mov     edx, 0Ch
0x18004fb0f  mov     dword ptr [rsp+38h+pvPara], eax
0x18004fb13  mov     rcx, [rcx+10h]
0x18004fb17  call    WPP_SF_Sd
0x18004fb1c  mov     eax, 8009030Dh
0x18004fb21  jmp     short loc_18004FAA7
```
