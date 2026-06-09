# CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)

- ea: `0x180039bf8`
- end: `0x180039cb7`
- name: `?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `191`
- prototype: `int(CTokenActivation *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180039398`
- `0x18003a474`
- `0x18003a800`

## callees

- `0x180003520`
- `0x180004288`
- `0x180039bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c69`
- `CRYPT32!CertFreeCertificateContext` at `0x180039c1b`
- `CRYPT32!CertFreeCertificateContext` at `0x180039c51`
- `CRYPT32!CertFreeCertificateContext` at `0x180039c1b`
- `CRYPT32!CertFreeCertificateContext` at `0x180039c51`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180039c36`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180039c36`

## pseudocode

```c
__int64 __fastcall CTokenActivation::SetSelectedCert(CTokenActivation *this, const struct _CERT_CONTEXT *a2)
{
  unsigned int v3; // ebx
  const CERT_CONTEXT *v4; // rcx
  PCCERT_CONTEXT v6; // rax
  const CERT_CONTEXT *v7; // rcx
  PCCERT_CONTEXT v8; // rsi
  signed int LastError; // eax

  v3 = 0;
  v4 = (const CERT_CONTEXT *)*((_QWORD *)this + 30);
  if ( v4 )
  {
    CertFreeCertificateContext(v4);
    *((_QWORD *)this + 30) = 0;
  }
  if ( a2 )
  {
    v6 = CertDuplicateCertificateContext(a2);
    v7 = (const CERT_CONTEXT *)*((_QWORD *)this + 30);
    v8 = v6;
    if ( v7 )
      CertFreeCertificateContext(v7);
    if ( v8 )
    {
      *((_QWORD *)this + 30) = v8;
    }
    else
    {
      *((_QWORD *)this + 30) = 0;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x180039bf8  mov     [rsp+arg_0], rbx
0x180039bfd  mov     [rsp+arg_8], rsi
0x180039c02  push    rdi
0x180039c03  sub     rsp, 20h
0x180039c07  mov     rdi, rcx
0x180039c0a  xor     ebx, ebx
0x180039c0c  mov     rcx, [rcx+0F0h]; pCertContext
0x180039c13  mov     rsi, rdx
0x180039c16  test    rcx, rcx
0x180039c19  jz      short loc_180039C2E
0x180039c1b  call    cs:__imp_CertFreeCertificateContext
0x180039c22  nop     dword ptr [rax+rax+00h]
0x180039c27  mov     [rdi+0F0h], rbx
0x180039c2e  test    rsi, rsi
0x180039c31  jz      short loc_180039C9D
0x180039c33  mov     rcx, rsi; pCertContext
0x180039c36  call    cs:__imp_CertDuplicateCertificateContext
0x180039c3d  nop     dword ptr [rax+rax+00h]
0x180039c42  mov     rcx, [rdi+0F0h]; pCertContext
0x180039c49  mov     rsi, rax
0x180039c4c  test    rcx, rcx
0x180039c4f  jz      short loc_180039C5D
0x180039c51  call    cs:__imp_CertFreeCertificateContext
0x180039c58  nop     dword ptr [rax+rax+00h]
0x180039c5d  test    rsi, rsi
0x180039c60  jnz     short loc_180039C96
0x180039c62  mov     [rdi+0F0h], rbx
0x180039c69  call    cs:__imp_GetLastError
0x180039c70  nop     dword ptr [rax+rax+00h]
0x180039c75  mov     ebx, eax
0x180039c77  test    eax, eax
0x180039c79  jnz     short loc_180039C82
0x180039c7b  mov     ebx, 80004005h
0x180039c80  jmp     short loc_180039C8D
0x180039c82  jle     short loc_180039C8D
0x180039c84  movzx   ebx, ax
0x180039c87  or      ebx, 80070000h
0x180039c8d  mov     ecx, ebx
0x180039c8f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039c94  jmp     short loc_180039C9D
0x180039c96  mov     [rdi+0F0h], rsi
0x180039c9d  mov     ecx, ebx
0x180039c9f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039ca4  mov     rsi, [rsp+28h+arg_8]
0x180039ca9  mov     eax, ebx
0x180039cab  mov     rbx, [rsp+28h+arg_0]
0x180039cb0  add     rsp, 20h
0x180039cb4  pop     rdi
0x180039cb5  retn
```
