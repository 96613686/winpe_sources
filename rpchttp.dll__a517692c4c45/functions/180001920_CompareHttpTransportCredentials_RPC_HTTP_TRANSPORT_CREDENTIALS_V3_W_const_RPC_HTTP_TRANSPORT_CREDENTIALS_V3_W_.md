# CompareHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *,_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *)

- ea: `0x180001920`
- end: `0x180001a36`
- name: `?CompareHttpTransportCredentials@@YAHPEBU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@0@Z`
- size: `278`
- prototype: `_BOOL8 __fastcall(const struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *, const struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001920`
- `0x180001fb0`
- `0x180024611`
- `0x180025010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800019af`
- `ntdll!_wcsicmp` at `0x1800019af`

## pseudocode

```c
_BOOL8 __fastcall CompareHttpTransportCredentials(
        const struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *a1,
        const struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *a2)
{
  unsigned int NumberOfAuthnSchemes; // r9d
  unsigned int *AuthnSchemes; // r10
  __int64 i; // r8
  unsigned int v7; // ecx
  unsigned int v8; // r11d
  unsigned __int16 *ServerCertificateSubject; // rcx
  unsigned __int16 *v10; // rax
  bool v11; // zf
  unsigned int NumberOfProxyAuthnSchemes; // eax
  unsigned int *ProxyAuthnSchemes; // rcx

  if ( a1->Flags != a2->Flags )
    return 1;
  if ( a1->AuthenticationTarget != a2->AuthenticationTarget )
    return 1;
  NumberOfAuthnSchemes = a1->NumberOfAuthnSchemes;
  if ( NumberOfAuthnSchemes != a2->NumberOfAuthnSchemes )
    return 1;
  AuthnSchemes = a1->AuthnSchemes;
  if ( AuthnSchemes )
  {
    for ( i = 0; (unsigned int)i < NumberOfAuthnSchemes; i = (unsigned int)(i + 1) )
    {
      v7 = AuthnSchemes[i];
      if ( v7 != a2->AuthnSchemes[i] && (!(unsigned int)IsCertAuthScheme(v7) || !(unsigned int)IsCertAuthScheme(v8)) )
        return 1;
    }
  }
  ServerCertificateSubject = a1->ServerCertificateSubject;
  v10 = a2->ServerCertificateSubject;
  if ( ServerCertificateSubject )
  {
    if ( !v10 )
      return 1;
    v11 = _wcsicmp(ServerCertificateSubject, a2->ServerCertificateSubject) == 0;
  }
  else
  {
    v11 = v10 == 0;
  }
  if ( v11 )
  {
    NumberOfProxyAuthnSchemes = a1->NumberOfProxyAuthnSchemes;
    if ( NumberOfProxyAuthnSchemes == a2->NumberOfProxyAuthnSchemes )
    {
      ProxyAuthnSchemes = a1->ProxyAuthnSchemes;
      if ( !ProxyAuthnSchemes || !memcmp_0(ProxyAuthnSchemes, a2->ProxyAuthnSchemes, 4LL * NumberOfProxyAuthnSchemes) )
      {
        if ( (*((unsigned int (__fastcall **)(RPC_AUTH_IDENTITY_HANDLE, RPC_AUTH_IDENTITY_HANDLE))pRuntimeImportTable
              + 44))(
               a1->TransportCredentials,
               a2->TransportCredentials) )
        {
          return (*((unsigned int (__fastcall **)(RPC_AUTH_IDENTITY_HANDLE, RPC_AUTH_IDENTITY_HANDLE))pRuntimeImportTable
                  + 44))(
                   a1->ProxyCredentials,
                   a2->ProxyCredentials) == 0;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_0], rbx
0x180001925  push    rdi
0x180001926  sub     rsp, 20h
0x18000192a  mov     eax, [rdx+8]
0x18000192d  mov     rdi, rdx
0x180001930  mov     rbx, rcx
0x180001933  cmp     [rcx+8], eax
0x180001936  jnz     loc_180001A26
0x18000193c  mov     eax, [rdx+0Ch]
0x18000193f  cmp     [rcx+0Ch], eax
0x180001942  jnz     loc_180001A26
0x180001948  mov     r9d, [rcx+10h]
0x18000194c  cmp     r9d, [rdx+10h]
0x180001950  jnz     loc_180001A26
0x180001956  mov     r10, [rcx+18h]
0x18000195a  test    r10, r10
0x18000195d  jz      short loc_18000199A
0x18000195f  xor     r8d, r8d
0x180001962  cmp     r8d, r9d
0x180001965  jnb     short loc_18000199A
0x180001967  mov     rax, [rdx+18h]
0x18000196b  mov     ecx, [r10+r8*4]; unsigned int
0x18000196f  mov     r11d, [rax+r8*4]
0x180001973  cmp     ecx, r11d
0x180001976  jz      short loc_180001995
0x180001978  call    ?IsCertAuthScheme@@YAHK@Z; IsCertAuthScheme(ulong)
0x18000197d  test    eax, eax
0x18000197f  jz      loc_180001A26
0x180001985  mov     ecx, r11d; unsigned int
0x180001988  call    ?IsCertAuthScheme@@YAHK@Z; IsCertAuthScheme(ulong)
0x18000198d  test    eax, eax
0x18000198f  jz      loc_180001A26
0x180001995  inc     r8d
0x180001998  jmp     short loc_180001962
0x18000199a  mov     rcx, [rbx+20h]; String1
0x18000199e  mov     rax, [rdx+20h]
0x1800019a2  test    rcx, rcx
0x1800019a5  jz      short loc_1800019B9
0x1800019a7  test    rax, rax
0x1800019aa  jz      short loc_180001A26
0x1800019ac  mov     rdx, rax; String2
0x1800019af  call    cs:__imp__wcsicmp
0x1800019b5  test    eax, eax
0x1800019b7  jmp     short loc_1800019BC
0x1800019b9  test    rax, rax
0x1800019bc  jnz     short loc_180001A26
0x1800019be  mov     eax, [rbx+30h]
0x1800019c1  cmp     eax, [rdi+30h]
0x1800019c4  jnz     short loc_180001A26
0x1800019c6  mov     rcx, [rbx+38h]; Buf1
0x1800019ca  test    rcx, rcx
0x1800019cd  jz      short loc_1800019E3
0x1800019cf  mov     rdx, [rdi+38h]; Buf2
0x1800019d3  mov     r8d, eax
0x1800019d6  shl     r8, 2; Size
0x1800019da  call    memcmp_0
0x1800019df  test    eax, eax
0x1800019e1  jnz     short loc_180001A26
0x1800019e3  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800019ea  mov     rdx, [rdi]
0x1800019ed  mov     rcx, [rbx]
0x1800019f0  mov     rax, [rax+160h]
0x1800019f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019fc  test    eax, eax
0x1800019fe  jz      short loc_180001A26
0x180001a00  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180001a07  mov     rdx, [rdi+28h]
0x180001a0b  mov     rcx, [rbx+28h]
0x180001a0f  mov     rax, [rax+160h]
0x180001a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1b  xor     ecx, ecx
0x180001a1d  test    eax, eax
0x180001a1f  setz    cl
0x180001a22  mov     eax, ecx
0x180001a24  jmp     short loc_180001A2B
0x180001a26  mov     eax, 1
0x180001a2b  mov     rbx, [rsp+28h+arg_0]
0x180001a30  add     rsp, 20h
0x180001a34  pop     rdi
0x180001a35  retn
```
