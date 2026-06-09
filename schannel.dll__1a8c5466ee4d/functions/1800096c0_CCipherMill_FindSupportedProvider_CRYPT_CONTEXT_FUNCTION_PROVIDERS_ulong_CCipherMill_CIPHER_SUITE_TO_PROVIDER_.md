# CCipherMill::FindSupportedProvider(_CRYPT_CONTEXT_FUNCTION_PROVIDERS *,ulong,CCipherMill::CIPHER_SUITE_TO_PROVIDER *,ulong,uchar *,ushort *,int)

- ea: `0x1800096c0`
- end: `0x180009874`
- name: `?FindSupportedProvider@CCipherMill@@AEAAKPEAU_CRYPT_CONTEXT_FUNCTION_PROVIDERS@@KPEAUCIPHER_SUITE_TO_PROVIDER@1@KPEAEPEAGH@Z`
- size: `436`
- prototype: `unsigned int(CCipherMill *__hidden this, struct _CRYPT_CONTEXT_FUNCTION_PROVIDERS *, unsigned int, struct CCipherMill::CIPHER_SUITE_TO_PROVIDER *, unsigned int, unsigned __int8 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180044528`

## callees

- `0x1800096c0`
- `0x18000a380`
- `0x18005a10c`

## import_xrefs

- `bcrypt!BCryptFreeBuffer` at `0x180009759`
- `bcrypt!BCryptFreeBuffer` at `0x180009759`
- `bcrypt!BCryptQueryProviderRegistration` at `0x18000973e`
- `bcrypt!BCryptQueryProviderRegistration` at `0x18000973e`

## string_xrefs

- `0x180009844`: `Microsoft SSL Protocol Provider`

## pseudocode

```c
unsigned int __fastcall CCipherMill::FindSupportedProvider(
        CCipherMill *this,
        struct _CRYPT_CONTEXT_FUNCTION_PROVIDERS *a2,
        ULONG a3,
        struct CCipherMill::CIPHER_SUITE_TO_PROVIDER *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned __int16 *a7,
        int a8)
{
  unsigned int v8; // esi
  unsigned int v12; // ebp
  unsigned int v13; // ebx
  PWSTR **p_rgpszProviders; // r14
  NTSTATUS v16; // eax
  const unsigned __int16 *v17; // r12
  __int64 v18; // rbx
  struct ProviderEccCurves *v19; // rdi
  __int64 v20; // rax
  ULONG pcbBuffer; // [rsp+80h] [rbp+8h] BYREF
  int v22; // [rsp+84h] [rbp+Ch]
  PCRYPT_PROVIDER_REG ppBuffer; // [rsp+88h] [rbp+10h] BYREF

  v22 = HIDWORD(this);
  v8 = 0;
  pcbBuffer = 0;
  v12 = -1;
  ppBuffer = 0;
  v13 = 0;
  if ( !a2->cProviders )
    return 1168;
  p_rgpszProviders = &a2->rgpszProviders;
  while ( v12 == -1 )
  {
    ppBuffer = 0;
    p_rgpszProviders = &a2->rgpszProviders;
    v16 = BCryptQueryProviderRegistration(a2->rgpszProviders[v13], a3, 0x10002u, &pcbBuffer, &ppBuffer);
    this = (CCipherMill *)ppBuffer;
    if ( v16 >= 0 && (a3 == 1 && ppBuffer->pUM || a3 == 2 && ppBuffer->pKM) )
      v12 = v13;
    if ( ppBuffer )
      BCryptFreeBuffer(ppBuffer);
    if ( ++v13 >= a2->cProviders )
    {
      if ( v12 == -1 )
        return 1168;
      break;
    }
  }
  v17 = a7;
  if ( a8 && !wcsnicmp((*p_rgpszProviders)[v12], L"Microsoft SSL Protocol Provider", 0x40u) )
  {
    v20 = -1;
    do
      ++v20;
    while ( v17[v20] );
    v17[(unsigned int)(v20 - 5)] = 0;
  }
  v18 = v12;
  while ( v8 < qword_1800AE498 )
  {
    v18 = v12;
    if ( !wcsnicmp(*(const wchar_t **)(qword_1800AE490 + 16LL * v8), (*p_rgpszProviders)[v12], 0x40u) )
    {
      if ( v8 != -1 )
      {
        v19 = (struct ProviderEccCurves *)(*(_QWORD *)qword_1800AE5C8 + 32LL * v8);
        return CCipherMill::InitializeCipherSuite(this, a4, a5, a6, a2->rgpszProviders[v18], v17, v19);
      }
      break;
    }
    ++v8;
  }
  v19 = 0;
  return CCipherMill::InitializeCipherSuite(this, a4, a5, a6, a2->rgpszProviders[v18], v17, v19);
}

```

## disassembly

```asm
0x1800096c0  mov     rax, rsp
0x1800096c3  mov     [rax+18h], rbx
0x1800096c7  mov     [rax+8], rcx
0x1800096cb  push    rbp
0x1800096cc  push    rsi
0x1800096cd  push    rdi
0x1800096ce  push    r12
0x1800096d0  push    r13
0x1800096d2  push    r14
0x1800096d4  push    r15
0x1800096d6  sub     rsp, 40h
0x1800096da  xor     esi, esi
0x1800096dc  or      r12d, 0FFFFFFFFh
0x1800096e0  mov     r13, r9
0x1800096e3  mov     edi, r8d
0x1800096e6  mov     r15, rdx
0x1800096e9  mov     [rax+8], esi
0x1800096ec  mov     ebp, r12d
0x1800096ef  mov     [rax+10h], rsi
0x1800096f3  mov     ebx, esi
0x1800096f5  cmp     [rdx], esi
0x1800096f7  ja      short loc_180009703
0x1800096f9  mov     eax, 490h
0x1800096fe  jmp     loc_1800097FE
0x180009703  lea     r14, [rdx+8]
0x180009707  cmp     ebp, r12d
0x18000970a  jnz     short loc_18000976B
0x18000970c  lea     rdx, [rsp+78h+arg_8]
0x180009714  mov     eax, ebx
0x180009716  mov     [rsp+78h+arg_8], rsi
0x18000971e  lea     r14, [r15+8]
0x180009722  mov     rcx, [r14]
0x180009725  lea     r9, [rsp+78h+pcbBuffer]; pcbBuffer
0x18000972d  mov     [rsp+78h+ppBuffer], rdx; ppBuffer
0x180009732  mov     r8d, 10002h; dwInterface
0x180009738  mov     edx, edi; dwMode
0x18000973a  mov     rcx, [rcx+rax*8]; pszProvider
0x18000973e  call    cs:__imp_BCryptQueryProviderRegistration
0x180009744  mov     rcx, [rsp+78h+arg_8]; pvBuffer
0x18000974c  test    eax, eax
0x18000974e  jns     loc_18000981A
0x180009754  test    rcx, rcx
0x180009757  jz      short loc_18000975F
0x180009759  call    cs:__imp_BCryptFreeBuffer
0x18000975f  inc     ebx
0x180009761  cmp     ebx, [r15]
0x180009764  jb      short loc_180009707
0x180009766  cmp     ebp, r12d
0x180009769  jz      short loc_1800096F9
0x18000976b  mov     r12, [rsp+78h+arg_30]
0x180009773  cmp     [rsp+78h+arg_38], esi
0x18000977a  jnz     loc_180009841
0x180009780  mov     ebx, ebp
0x180009782  cmp     esi, dword ptr cs:qword_1800AE498
0x180009788  jnb     loc_180009816
0x18000978e  mov     rdx, [r14]
0x180009791  mov     r8d, 40h ; '@'; MaxCount
0x180009797  mov     rcx, cs:qword_1800AE490
0x18000979e  mov     eax, esi
0x1800097a0  add     rax, rax
0x1800097a3  mov     ebx, ebp
0x1800097a5  mov     edi, esi
0x1800097a7  mov     rcx, [rcx+rax*8]; String1
0x1800097ab  mov     rdx, [rdx+rbx*8]; String2
0x1800097af  call    _wcsnicmp
0x1800097b4  test    eax, eax
0x1800097b6  jnz     loc_18000986D
0x1800097bc  cmp     esi, 0FFFFFFFFh
0x1800097bf  jz      short loc_180009816
0x1800097c1  mov     rax, cs:qword_1800AE5C8
0x1800097c8  shl     rdi, 5
0x1800097cc  add     rdi, [rax]
0x1800097cf  mov     rax, [r15+8]
0x1800097d3  mov     rdx, r13; struct CCipherMill::CIPHER_SUITE_TO_PROVIDER *
0x1800097d6  mov     r9, [rsp+78h+arg_28]; unsigned __int8 *
0x1800097de  mov     r8d, [rsp+78h+arg_20]; unsigned int
0x1800097e6  mov     [rsp+78h+var_48], rdi; struct ProviderEccCurves *
0x1800097eb  mov     rax, [rax+rbx*8]
0x1800097ef  mov     [rsp+78h+var_50], r12; unsigned __int16 *
0x1800097f4  mov     [rsp+78h+ppBuffer], rax; unsigned __int16 *
0x1800097f9  call    ?InitializeCipherSuite@CCipherMill@@AEAAKPEAUCIPHER_SUITE_TO_PROVIDER@1@KPEAEPEBG2PEAUProviderEccCurves@@@Z; CCipherMill::InitializeCipherSuite(CCipherMill::CIPHER_SUITE_TO_PROVIDER *,ulong,uchar *,ushort const *,ushort const *,ProviderEccCurves *)
0x1800097fe  mov     rbx, [rsp+78h+arg_10]
0x180009806  add     rsp, 40h
0x18000980a  pop     r15
0x18000980c  pop     r14
0x18000980e  pop     r13
0x180009810  pop     r12
0x180009812  pop     rdi
0x180009813  pop     rsi
0x180009814  pop     rbp
0x180009815  retn
0x180009816  xor     edi, edi
0x180009818  jmp     short loc_1800097CF
0x18000981a  cmp     edi, 1
0x18000981d  jz      short loc_180009839
0x18000981f  cmp     edi, 2
0x180009822  jnz     loc_180009754
0x180009828  cmp     [rcx+18h], rsi
0x18000982c  jz      loc_180009754
0x180009832  mov     ebp, ebx
0x180009834  jmp     loc_180009754
0x180009839  cmp     [rcx+10h], rsi
0x18000983d  jnz     short loc_180009832
0x18000983f  jmp     short loc_18000981F
0x180009841  mov     rcx, [r14]
0x180009844  lea     rdx, aMicrosoftSslPr; "Microsoft SSL Protocol Provider"
0x18000984b  mov     eax, ebp
0x18000984d  mov     r8d, 40h ; '@'; MaxCount
0x180009853  mov     rcx, [rcx+rax*8]; String1
0x180009857  call    _wcsnicmp
0x18000985c  test    eax, eax
0x18000985e  jnz     loc_180009780
0x180009864  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009868  jmp     loc_180089A9A
0x18000986d  inc     esi
0x18000986f  jmp     loc_180009782
0x180089a9a  inc     rax
0x180089a9d  cmp     [r12+rax*2], si
0x180089aa2  jnz     short loc_180089A9A
0x180089aa4  add     eax, 0FFFFFFFBh
0x180089aa7  mov     [r12+rax*2], si
0x180089aac  jmp     loc_180009780
```
