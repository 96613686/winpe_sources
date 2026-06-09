# CreateChainEngine(CCredentialGroup *)

- ea: `0x180084a50`
- end: `0x180084b12`
- name: `?CreateChainEngine@@YAPEAXPEAVCCredentialGroup@@@Z`
- size: `194`
- prototype: `void *__fastcall(struct CCredentialGroup *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180084b18`

## callees

- `0x180021da8`
- `0x18005a160`
- `0x180084a50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ac3`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180084ab9`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180084ab9`

## pseudocode

```c
__int64 __fastcall CreateChainEngine(struct CCredentialGroup *a1)
{
  DWORD LastError; // eax
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+20h] [rbp-68h] BYREF
  int v5; // [rsp+70h] [rbp-18h]
  HCERTCHAINENGINE phChainEngine; // [rsp+98h] [rbp+10h] BYREF

  memset_0(&pConfig, 0, 0x58u);
  phChainEngine = 0;
  pConfig.cbSize = 88;
  pConfig.dwFlags = 56;
  if ( !g_eClientAuthMode )
    return 1;
  if ( g_eClientAuthMode != 1 )
  {
    if ( g_eClientAuthMode != 2 )
      goto LABEL_6;
    v5 = 1;
  }
  pConfig.hExclusiveRoot = (HCERTSTORE)*((_QWORD *)a1 + 110);
LABEL_6:
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee3ada077a243a8835f858b78da5bb63_Traceguids, LastError);
    return 1;
  }
  return (__int64)phChainEngine;
}

```

## disassembly

```asm
0x180084a50  push    rbx
0x180084a52  sub     rsp, 80h
0x180084a59  xor     edx, edx; Val
0x180084a5b  mov     rbx, rcx
0x180084a5e  lea     rcx, [rsp+88h+pConfig]; void *
0x180084a63  lea     r8d, [rdx+58h]; Size
0x180084a67  call    memset_0
0x180084a6c  mov     edx, cs:?g_eClientAuthMode@@3W4eClientAuthTrustMode@@A; eClientAuthTrustMode g_eClientAuthMode
0x180084a72  mov     [rsp+88h+phChainEngine], 0
0x180084a7e  mov     [rsp+88h+pConfig.cbSize], 58h ; 'X'
0x180084a86  mov     [rsp+88h+pConfig.dwFlags], 38h ; '8'
0x180084a8e  test    edx, edx
0x180084a90  jz      short loc_180084AFA
0x180084a92  sub     edx, 1
0x180084a95  jz      short loc_180084AA0
0x180084a97  cmp     edx, 1
0x180084a9a  jnz     short loc_180084AAC
0x180084a9c  mov     [rsp+88h+var_18], edx
0x180084aa0  mov     rax, [rbx+370h]
0x180084aa7  mov     [rsp+88h+pConfig.hExclusiveRoot], rax
0x180084aac  lea     rdx, [rsp+88h+phChainEngine]; phChainEngine
0x180084ab4  lea     rcx, [rsp+88h+pConfig]; pConfig
0x180084ab9  call    cs:__imp_CertCreateCertificateChainEngine
0x180084abf  test    eax, eax
0x180084ac1  jnz     short loc_180084B08
0x180084ac3  call    cs:__imp_GetLastError
0x180084ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180084ad0  lea     rdx, WPP_GLOBAL_Control
0x180084ad7  cmp     rcx, rdx
0x180084ada  jz      short loc_180084AFA
0x180084adc  test    byte ptr [rcx+1Ch], 1
0x180084ae0  jz      short loc_180084AFA
0x180084ae2  mov     rcx, [rcx+10h]
0x180084ae6  lea     r8, WPP_ee3ada077a243a8835f858b78da5bb63_Traceguids
0x180084aed  mov     edx, 0Ah
0x180084af2  mov     r9d, eax
0x180084af5  call    WPP_SF_d
0x180084afa  mov     eax, 1
0x180084aff  add     rsp, 80h
0x180084b06  pop     rbx
0x180084b07  retn
0x180084b08  mov     rax, [rsp+88h+phChainEngine]
0x180084b10  jmp     short loc_180084AFF
```
