# CCredentialGroup::GetKeyFilePath(ushort const * *)

- ea: `0x180072b68`
- end: `0x180072d6f`
- name: `?GetKeyFilePath@CCredentialGroup@@QEAAKPEAPEBG@Z`
- size: `519`
- prototype: `unsigned int __fastcall(CCredentialGroup *__hidden this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006f1c`
- `0x18007ce4c`

## callees

- `0x180006b54`
- `0x18003f0d0`
- `0x1800597b0`
- `0x18005a160`
- `0x18005c330`
- `0x180072ac4`
- `0x180072b68`
- `0x1800735e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072d44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072d34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180072d44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072cb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180072cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c67`
- `ntdll!RtlAcquireResourceExclusive` at `0x180072c3d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180072c3d`
- `ntdll!RtlReleaseResource` at `0x180072d26`
- `ntdll!RtlReleaseResource` at `0x180072d26`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180072c7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180072c7d`

## pseudocode

```c
__int64 __fastcall CCredentialGroup::GetKeyFilePath(void **this, unsigned __int16 **a2)
{
  struct _RTL_RESOURCE *v4; // r14
  unsigned __int16 *v5; // rdi
  unsigned __int16 **v6; // rsi
  DWORD LastError; // ebx
  SIZE_T v8; // rbx
  wchar_t *v9; // rax
  size_t *v10; // r8
  CCredentialGroup *v11; // rcx
  size_t v13; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v16[8]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v17[2]; // [rsp+50h] [rbp-B0h]
  wchar_t pszSrc[64]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 Sid[80]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(Sid, 0, 0x44u);
  v4 = (struct _RTL_RESOURCE *)(this + 14);
  wcscpy(pszSrc, L"%ALLUSERSPROFILE%\\Microsoft\\Crypto\\TlsSessionTicketKeys\\");
  v5 = 0;
  StringSid = 0;
  v15 = 0;
  *(_OWORD *)v16 = *(_OWORD *)L"\\SessionTicketKey.key";
  v17[0] = *(_OWORD *)L"TicketKey.key";
  *(_OWORD *)((char *)v17 + 12) = *(_OWORD *)L"Key.key";
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(this + 14), 1u);
  v6 = (unsigned __int16 **)(this + 120);
  if ( !this[120] )
  {
    if ( !(unsigned int)GetTokenUserSid(this[102], Sid) || !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      LastError = GetLastError();
      goto LABEL_15;
    }
    if ( (int)StringCbLengthW(StringSid, 0xFFFFFFFE, &v15) < 0 )
      goto LABEL_6;
    v8 = (unsigned int)(v15 + 156);
    v9 = (wchar_t *)LocalAlloc(0x40u, v8);
    v5 = v9;
    if ( !v9 )
    {
      LastError = 14;
      goto LABEL_15;
    }
    if ( !(v8 >> 1)
      || StringCopyWorkerW_0(v9, v8 >> 1, v10, pszSrc, v13) < 0
      || StringCbCatW(v5, v8, StringSid) < 0
      || StringCbCatW(v5, v8, v16) < 0
      || CCredentialGroup::GetFileFullPath(v11, v5, v6) < 0 )
    {
LABEL_6:
      LastError = 1359;
      goto LABEL_15;
    }
  }
  LastError = 0;
  *a2 = *v6;
LABEL_15:
  RtlReleaseResource(v4);
  if ( v5 )
    LocalFree(v5);
  if ( StringSid )
    LocalFree(StringSid);
  return LastError;
}

```

## disassembly

```asm
0x180072b68  mov     [rsp-8+arg_10], rbx
0x180072b6d  push    rbp
0x180072b6e  push    rsi
0x180072b6f  push    rdi
0x180072b70  push    r14
0x180072b72  push    r15
0x180072b74  lea     rbp, [rsp-50h]
0x180072b79  sub     rsp, 150h
0x180072b80  mov     rax, cs:__security_cookie
0x180072b87  xor     rax, rsp
0x180072b8a  mov     [rbp+70h+var_30], rax
0x180072b8e  mov     r15, rdx
0x180072b91  mov     rbx, rcx
0x180072b94  xor     edx, edx; Val
0x180072b96  lea     rcx, [rbp+70h+Sid]; void *
0x180072b9a  lea     r8d, [rdx+44h]; Size
0x180072b9e  call    memset_0
0x180072ba3  movaps  xmm0, xmmword ptr cs:aAllusersprofil; "%ALLUSERSPROFILE%\\Microsoft\\Crypto\\T"...
0x180072baa  lea     r14, [rbx+70h]
0x180072bae  movaps  xmm1, xmmword ptr cs:aAllusersprofil+10h; "SPROFILE%\\Microsoft\\Crypto\\TlsSessio"...
0x180072bb5  mov     dl, 1; Wait
0x180072bb7  movzx   eax, word ptr cs:aAllusersprofil+70h; ""
0x180072bbe  mov     rcx, r14; Resource
0x180072bc1  movaps  xmmword ptr [rsp+170h+pszSrc], xmm0
0x180072bc6  xor     edi, edi
0x180072bc8  movaps  xmm0, xmmword ptr cs:aAllusersprofil+20h; "%\\Microsoft\\Crypto\\TlsSessionTicketK"...
0x180072bcf  movaps  [rbp+70h+var_E0], xmm0
0x180072bd3  movaps  xmm0, xmmword ptr cs:aAllusersprofil+40h; "to\\TlsSessionTicketKeys\\"
0x180072bda  movaps  [rbp+70h+var_C0], xmm0
0x180072bde  movaps  xmm0, xmmword ptr cs:aAllusersprofil+60h; "ketKeys\\"
0x180072be5  movaps  [rbp+70h+var_F0], xmm1
0x180072be9  movaps  xmm1, xmmword ptr cs:aAllusersprofil+30h; "oft\\Crypto\\TlsSessionTicketKeys\\"
0x180072bf0  movaps  [rbp+70h+var_A0], xmm0
0x180072bf4  movups  xmm0, xmmword ptr cs:aSessionticketk; "\\SessionTicketKey.key"
0x180072bfb  mov     [rsp+170h+StringSid], 0
0x180072c04  movaps  [rbp+70h+var_D0], xmm1
0x180072c08  movaps  xmm1, xmmword ptr cs:aAllusersprofil+50h; "ssionTicketKeys\\"
0x180072c0f  movaps  [rbp+70h+var_B0], xmm1
0x180072c13  movups  xmm1, xmmword ptr cs:aSessionticketk+10h; "TicketKey.key"
0x180072c1a  mov     [rsp+170h+var_138], 0
0x180072c23  movups  xmmword ptr [rsp+170h+var_130], xmm0
0x180072c28  mov     [rbp+70h+var_90], ax
0x180072c2c  movups  xmm0, xmmword ptr cs:aSessionticketk+1Ch; "Key.key"
0x180072c33  movups  xmmword ptr [rsp+170h+var_120], xmm1
0x180072c38  movups  xmmword ptr [rsp+170h+var_120+0Ch], xmm0
0x180072c3d  call    cs:__imp_RtlAcquireResourceExclusive
0x180072c43  lea     rsi, [rbx+3C0h]
0x180072c4a  cmp     [rsi], rdi
0x180072c4d  jnz     loc_180072D1B
0x180072c53  mov     rcx, [rbx+330h]; void *
0x180072c5a  lea     rdx, [rbp+70h+Sid]; unsigned __int8 *
0x180072c5e  call    ?GetTokenUserSid@@YAHPEAXQEAE@Z; GetTokenUserSid(void *,uchar * const)
0x180072c63  test    eax, eax
0x180072c65  jnz     short loc_180072C74
0x180072c67  call    cs:__imp_GetLastError
0x180072c6d  mov     ebx, eax
0x180072c6f  jmp     loc_180072D23
0x180072c74  lea     rdx, [rsp+170h+StringSid]; StringSid
0x180072c79  lea     rcx, [rbp+70h+Sid]; Sid
0x180072c7d  call    cs:__imp_ConvertSidToStringSidW
0x180072c83  test    eax, eax
0x180072c85  jz      short loc_180072C67
0x180072c87  mov     rcx, [rsp+170h+StringSid]; unsigned __int16 *
0x180072c8c  lea     r8, [rsp+170h+var_138]; unsigned __int64 *
0x180072c91  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180072c96  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180072c9b  test    eax, eax
0x180072c9d  jns     short loc_180072CA6
0x180072c9f  mov     ebx, 54Fh
0x180072ca4  jmp     short loc_180072D23
0x180072ca6  mov     eax, dword ptr [rsp+170h+var_138]
0x180072caa  mov     ecx, 40h ; '@'; uFlags
0x180072caf  add     eax, 9Ch
0x180072cb4  mov     edx, eax; uBytes
0x180072cb6  mov     ebx, eax
0x180072cb8  call    cs:__imp_LocalAlloc
0x180072cbe  mov     rdi, rax
0x180072cc1  test    rax, rax
0x180072cc4  jnz     short loc_180072CCB
0x180072cc6  lea     ebx, [rax+0Eh]
0x180072cc9  jmp     short loc_180072D23
0x180072ccb  mov     rdx, rbx
0x180072cce  shr     rdx, 1; cchDest
0x180072cd1  jz      short loc_180072C9F
0x180072cd3  lea     r9, [rsp+170h+pszSrc]; pszSrc
0x180072cd8  mov     rcx, rdi; pszDest
0x180072cdb  call    StringCopyWorkerW_0
0x180072ce0  test    eax, eax
0x180072ce2  js      short loc_180072C9F
0x180072ce4  mov     r8, [rsp+170h+StringSid]; unsigned __int16 *
0x180072ce9  mov     rdx, rbx; unsigned __int64
0x180072cec  mov     rcx, rdi; unsigned __int16 *
0x180072cef  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180072cf4  test    eax, eax
0x180072cf6  js      short loc_180072C9F
0x180072cf8  lea     r8, [rsp+170h+var_130]; unsigned __int16 *
0x180072cfd  mov     rdx, rbx; unsigned __int64
0x180072d00  mov     rcx, rdi; unsigned __int16 *
0x180072d03  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180072d08  test    eax, eax
0x180072d0a  js      short loc_180072C9F
0x180072d0c  mov     r8, rsi; unsigned __int16 **
0x180072d0f  mov     rdx, rdi; unsigned __int16 *
0x180072d12  call    ?GetFileFullPath@CCredentialGroup@@AEAAJPEBGPEAPEAG@Z; CCredentialGroup::GetFileFullPath(ushort const *,ushort * *)
0x180072d17  test    eax, eax
0x180072d19  js      short loc_180072C9F
0x180072d1b  mov     rax, [rsi]
0x180072d1e  xor     ebx, ebx
0x180072d20  mov     [r15], rax
0x180072d23  mov     rcx, r14; Resource
0x180072d26  call    cs:__imp_RtlReleaseResource
0x180072d2c  test    rdi, rdi
0x180072d2f  jz      short loc_180072D3A
0x180072d31  mov     rcx, rdi; hMem
0x180072d34  call    cs:__imp_LocalFree
0x180072d3a  mov     rcx, [rsp+170h+StringSid]; hMem
0x180072d3f  test    rcx, rcx
0x180072d42  jz      short loc_180072D4A
0x180072d44  call    cs:__imp_LocalFree
0x180072d4a  mov     eax, ebx
0x180072d4c  mov     rcx, [rbp+70h+var_30]
0x180072d50  xor     rcx, rsp; StackCookie
0x180072d53  call    __security_check_cookie
0x180072d58  mov     rbx, [rsp+170h+arg_10]
0x180072d60  add     rsp, 150h
0x180072d67  pop     r15
0x180072d69  pop     r14
0x180072d6b  pop     rdi
0x180072d6c  pop     rsi
0x180072d6d  pop     rbp
0x180072d6e  retn
```
