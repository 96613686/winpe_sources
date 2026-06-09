# GetKeyingMaterial(_SecHandle &,std::unique_ptr<AeadCryptoWrapper,std::default_delete<AeadCryptoWrapper>> &,int,std::vector<uchar,wil::secure_allocator<uchar>> &)

- ea: `0x180059a80`
- end: `0x180059c35`
- name: `?GetKeyingMaterial@@YAJAEAU_SecHandle@@AEAV?$unique_ptr@VAeadCryptoWrapper@@U?$default_delete@VAeadCryptoWrapper@@@std@@@std@@HAEAV?$vector@EU?$secure_allocator@E@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 __fastcall(PCtxtHandle phContext, __int64 *, char, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005a028`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003f491`
- `0x180059490`
- `0x1800595b0`
- `0x1800595f0`
- `0x180059a80`

## import_xrefs

- `SspiCli!SetContextAttributesW` at `0x180059b15`
- `SspiCli!SetContextAttributesW` at `0x180059b15`
- `SspiCli!FreeContextBuffer` at `0x180059c07`
- `SspiCli!FreeContextBuffer` at `0x180059c07`
- `SspiCli!QueryContextAttributesW` at `0x180059b72`
- `SspiCli!QueryContextAttributesW` at `0x180059b72`

## string_xrefs

- `0x180059ad8`: `EXPORTER-network-time-security`

## pseudocode

```c
__int64 __fastcall GetKeyingMaterial(PCtxtHandle phContext, __int64 *a2, char a3, __int64 a4)
{
  __int64 v6; // r9
  __int16 v7; // cx
  SECURITY_STATUS ContextAttributesW; // edi
  void *v9; // r8
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  void *v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-29h] BYREF
  char v15; // [rsp+28h] [rbp-21h]
  void *Src[2]; // [rsp+30h] [rbp-19h] BYREF
  void **v17; // [rsp+48h] [rbp-1h] BYREF
  _QWORD pBuffer[4]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+70h] [rbp+27h]
  __int16 v20; // [rsp+78h] [rbp+2Fh] BYREF
  char v21; // [rsp+7Ah] [rbp+31h]
  char v22; // [rsp+7Bh] [rbp+32h]
  char v23; // [rsp+7Ch] [rbp+33h]

  v6 = *a2;
  v7 = *(_WORD *)(*a2 + 68);
  v20 = 0;
  v21 = HIBYTE(v7);
  v22 = v7;
  v23 = a3;
  pBuffer[0] = 31;
  pBuffer[2] = 5;
  v19 = 0;
  pBuffer[1] = "EXPORTER-network-time-security";
  pBuffer[3] = &v20;
  LODWORD(v19) = *(_DWORD *)(v6 + 56);
  ContextAttributesW = SetContextAttributesW(phContext, 0x6Au, pBuffer, 0x28u);
  if ( ContextAttributesW < 0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"ParseServerResponse: SetContextAttributes failed with hr: 0x%08X\n",
        (unsigned int)ContextAttributesW);
    return (unsigned int)ContextAttributesW;
  }
  *(_OWORD *)Src = 0;
  v17 = Src;
  wil::scope_exit__lambda_192014dcd78d9c6b26c1dabafd87c483___(&v14, &v17);
  ContextAttributesW = QueryContextAttributesW(phContext, 0x6Bu, Src);
  if ( ContextAttributesW < 0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"ParseServerResponse: QueryContextAttributes failed with hr: 0x%08X\n",
        (unsigned int)ContextAttributesW);
    goto LABEL_15;
  }
  v9 = *(void **)a4;
  v10 = *(_QWORD *)(a4 + 8) - *(_QWORD *)a4;
  if ( LODWORD(Src[0]) < v10 )
  {
    v11 = (__int64)v9 + LODWORD(Src[0]);
LABEL_13:
    *(_QWORD *)(a4 + 8) = v11;
    goto LABEL_14;
  }
  if ( LODWORD(Src[0]) > v10 )
  {
    if ( (unsigned __int64)LODWORD(Src[0]) <= *(_QWORD *)(a4 + 16) - (_QWORD)v9 )
    {
      v11 = std::_Uninitialized_value_construct_n<wil::secure_allocator<unsigned char>>(
              *(_QWORD *)(a4 + 8),
              LODWORD(Src[0]) - v10);
      goto LABEL_13;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Resize_reallocate<std::_Value_init_tag>(a4);
  }
LABEL_14:
  memcpy_0(*(void **)a4, Src[1], LODWORD(Src[0]));
LABEL_15:
  if ( v15 )
  {
    v15 = 0;
    v12 = *(void **)(v14 + 8);
    if ( v12 )
      FreeContextBuffer(v12);
  }
  return (unsigned int)ContextAttributesW;
}

```

## disassembly

```asm
0x180059a80  mov     [rsp-8+arg_10], rbx
0x180059a85  push    rbp
0x180059a86  push    rsi
0x180059a87  push    rdi
0x180059a88  lea     rbp, [rsp-47h]
0x180059a8d  sub     rsp, 90h
0x180059a94  mov     rax, cs:__security_cookie
0x180059a9b  xor     rax, rsp
0x180059a9e  mov     [rbp+57h+var_20], rax
0x180059aa2  mov     rbx, r9
0x180059aa5  mov     rsi, rcx
0x180059aa8  mov     r9, [rdx]
0x180059aab  movzx   ecx, word ptr [r9+44h]
0x180059ab0  mov     [rbp+57h+var_28], 0
0x180059ab6  movzx   eax, cx
0x180059ab9  shr     ax, 8
0x180059abd  mov     [rbp+57h+var_26], al
0x180059ac0  mov     [rbp+57h+var_25], cl
0x180059ac3  mov     [rbp+57h+var_24], r8b
0x180059ac7  xorps   xmm0, xmm0
0x180059aca  xor     eax, eax
0x180059acc  movups  [rbp+57h+pBuffer], xmm0
0x180059ad0  movups  [rbp+57h+var_40], xmm0
0x180059ad4  mov     [rbp+57h+var_30], rax
0x180059ad8  lea     rax, aExporterNetwor; "EXPORTER-network-time-security"
0x180059adf  mov     qword ptr [rbp+57h+pBuffer+8], rax
0x180059ae3  mov     eax, 1Fh
0x180059ae8  mov     word ptr [rbp+57h+pBuffer], ax
0x180059aec  lea     rax, [rbp+57h+var_28]
0x180059af0  mov     qword ptr [rbp+57h+var_40+8], rax
0x180059af4  mov     eax, 5
0x180059af9  mov     word ptr [rbp+57h+var_40], ax
0x180059afd  mov     eax, [r9+38h]
0x180059b01  mov     dword ptr [rbp+57h+var_30], eax
0x180059b04  mov     r9d, 28h ; '('; cbBuffer
0x180059b0a  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x180059b0e  lea     edx, [r9+42h]; ulAttribute
0x180059b12  mov     rcx, rsi; phContext
0x180059b15  call    cs:__imp_SetContextAttributesW
0x180059b1c  nop     dword ptr [rax+rax+00h]
0x180059b21  mov     edi, eax
0x180059b23  test    eax, eax
0x180059b25  jns     short loc_180059B49
0x180059b27  xor     ecx, ecx
0x180059b29  call    FileLogAllowEntry
0x180059b2e  test    al, al
0x180059b30  jz      loc_180059C13
0x180059b36  mov     edx, edi
0x180059b38  lea     rcx, aParseserverres; "ParseServerResponse: SetContextAttribut"...
0x180059b3f  call    FileLogAdd
0x180059b44  jmp     loc_180059C13
0x180059b49  xorps   xmm0, xmm0
0x180059b4c  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180059b50  lea     rax, [rbp+57h+Src]
0x180059b54  mov     [rbp+57h+var_58], rax
0x180059b58  lea     rdx, [rbp+57h+var_58]
0x180059b5c  lea     rcx, [rbp+57h+var_80]
0x180059b60  call    wil__scope_exit__lambda_192014dcd78d9c6b26c1dabafd87c483___
0x180059b65  nop
0x180059b66  lea     r8, [rbp+57h+Src]; pBuffer
0x180059b6a  mov     edx, 6Bh ; 'k'; ulAttribute
0x180059b6f  mov     rcx, rsi; phContext
0x180059b72  call    cs:__imp_QueryContextAttributesW
0x180059b79  nop     dword ptr [rax+rax+00h]
0x180059b7e  mov     edi, eax
0x180059b80  test    eax, eax
0x180059b82  jns     short loc_180059B9F
0x180059b84  xor     ecx, ecx
0x180059b86  call    FileLogAllowEntry
0x180059b8b  test    al, al
0x180059b8d  jz      short loc_180059BF0
0x180059b8f  mov     edx, edi
0x180059b91  lea     rcx, aParseserverres_0; "ParseServerResponse: QueryContextAttrib"...
0x180059b98  call    FileLogAdd
0x180059b9d  jmp     short loc_180059BF0
0x180059b9f  mov     edx, dword ptr [rbp+57h+Src]
0x180059ba2  mov     r8, [rbx]
0x180059ba5  mov     rcx, [rbx+8]
0x180059ba9  sub     rcx, r8
0x180059bac  cmp     rdx, rcx
0x180059baf  jnb     short loc_180059BB7
0x180059bb1  lea     rax, [r8+rdx]
0x180059bb5  jmp     short loc_180059BDB
0x180059bb7  jbe     short loc_180059BDF
0x180059bb9  mov     rax, [rbx+10h]
0x180059bbd  sub     rax, r8
0x180059bc0  cmp     rdx, rax
0x180059bc3  jbe     short loc_180059BCF
0x180059bc5  mov     rcx, rbx
0x180059bc8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180059bcd  jmp     short loc_180059BDF
0x180059bcf  sub     rdx, rcx
0x180059bd2  mov     rcx, [rbx+8]
0x180059bd6  call    ??$_Uninitialized_value_construct_n@U?$secure_allocator@E@wil@@@std@@YAPEAEPEAE_KAEAU?$secure_allocator@E@wil@@@Z; std::_Uninitialized_value_construct_n<wil::secure_allocator<uchar>>(uchar *,unsigned __int64,wil::secure_allocator<uchar> &)
0x180059bdb  mov     [rbx+8], rax
0x180059bdf  mov     r8d, dword ptr [rbp+57h+Src]; Size
0x180059be3  mov     rdx, [rbp+57h+Src+8]; Src
0x180059be7  mov     rcx, [rbx]; void *
0x180059bea  call    memcpy_0
0x180059bef  nop
0x180059bf0  cmp     [rbp+57h+var_78], 0
0x180059bf4  jz      short loc_180059C13
0x180059bf6  mov     rax, [rbp+57h+var_80]
0x180059bfa  mov     [rbp+57h+var_78], 0
0x180059bfe  mov     rcx, [rax+8]; pvContextBuffer
0x180059c02  test    rcx, rcx
0x180059c05  jz      short loc_180059C13
0x180059c07  call    cs:__imp_FreeContextBuffer
0x180059c0e  nop     dword ptr [rax+rax+00h]
0x180059c13  mov     eax, edi
0x180059c15  mov     rcx, [rbp+57h+var_20]
0x180059c19  xor     rcx, rsp; StackCookie
0x180059c1c  call    __security_check_cookie
0x180059c21  mov     rbx, [rsp+0A0h+arg_10]
0x180059c29  add     rsp, 90h
0x180059c30  pop     rdi
0x180059c31  pop     rsi
0x180059c32  pop     rbp
0x180059c33  retn
```
