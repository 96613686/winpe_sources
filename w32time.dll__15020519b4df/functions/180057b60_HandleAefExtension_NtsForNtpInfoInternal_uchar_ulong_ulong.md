# HandleAefExtension(NtsForNtpInfoInternal &,uchar *,ulong,ulong)

- ea: `0x180057b60`
- end: `0x180057d65`
- name: `?HandleAefExtension@@YAJAEAUNtsForNtpInfoInternal@@PEAEKK@Z`
- size: `517`
- prototype: `__int64 __fastcall(AeadCryptoWrapper **, unsigned __int8 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180057d6c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180057b60`
- `0x18005a960`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180057bac`
- `WS2_32!__imp_ntohs` at `0x180057c06`
- `WS2_32!__imp_ntohs` at `0x180057c98`
- `WS2_32!__imp_ntohs` at `0x180057bac`
- `WS2_32!__imp_ntohs` at `0x180057c06`
- `WS2_32!__imp_ntohs` at `0x180057c98`

## string_xrefs

- `0x180057b97`: `HandleAefExtension: The packet is not large enough to contain an AEFHeader: %d < %d\n`
- `0x180057bcf`: `HandleAefExtension: cbHeaderLength is : %d\n`
- `0x180057bf6`: `HandleAefExtension: The packet is not large enough to contain the AEF extensions field: packet size: %d < offsetNeeded: %d\n`
- `0x180057c23`: `HandleAefExtension: cbNonceLength is : %d\n`
- `0x180057c64`: `HandleAefExtension: The packet is not large enough to contain the nonce: %d < %d\n`
- `0x180057c88`: `HandleAefExtension: The packet does not make sense based on cbHeaderLength: %d <= %d`
- `0x180057cb9`: `HandleAefExtension: cbCipherLength is : %d\n`
- `0x180057cf5`: `HandleAefExtension: The packet is not large enough to contain the ciphertext: %d < %d\n`
- `0x180057d10`: `HandleAefExtension: The packet does not make sense based on cbHeaderLength: %d != %d`

## pseudocode

```c
__int64 __fastcall HandleAefExtension(AeadCryptoWrapper **a1, unsigned __int8 *a2, __int64 a3, unsigned int a4)
{
  unsigned int v7; // edi
  unsigned int v8; // ebp
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  __int64 v11; // rdx
  const wchar_t *v12; // rcx
  unsigned int v13; // r15d

  if ( a4 < 0x5C )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"HandleAefExtension: The packet is not large enough to contain an AEFHeader: %d < %d\n", a4, 92);
    return 2147942487LL;
  }
  v7 = ntohs(*((_WORD *)a2 + 43));
  if ( (unsigned __int8)FileLogAllowEntry(200) )
    FileLogAdd(L"HandleAefExtension: cbHeaderLength is : %d\n", v7);
  if ( a4 < v7 + 84 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"HandleAefExtension: The packet is not large enough to contain the AEF extensions field: packet size: %d < offsetNeeded: %d\n",
        a4,
        v7 + 84);
    return 2147942487LL;
  }
  v8 = ntohs(*((_WORD *)a2 + 44));
  if ( (unsigned __int8)FileLogAllowEntry(200) )
    FileLogAdd(L"HandleAefExtension: cbNonceLength is : %d\n", v8);
  v9 = ((v8 & 3) != 0 ? 4 - (v8 & 3) : 0) + v8 + 8;
  v10 = v9 + 84;
  if ( a4 < v9 + 84 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
    {
      v11 = a4;
      v12 = L"HandleAefExtension: The packet is not large enough to contain the nonce: %d < %d\n";
LABEL_25:
      FileLogAdd(v12, v11, v10);
      return 2147942487LL;
    }
    return 2147942487LL;
  }
  if ( v7 <= v9 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"HandleAefExtension: The packet does not make sense based on cbHeaderLength: %d <= %d", v7, v9);
    return 2147942487LL;
  }
  v13 = ntohs(*((_WORD *)a2 + 45));
  if ( (unsigned __int8)FileLogAllowEntry(200) )
    FileLogAdd(L"HandleAefExtension: cbCipherLength is : %d\n", v13);
  v10 = v13 + ((v13 & 3) != 0 ? 4 - (v13 & 3) : 0) + v9;
  if ( a4 < v10 + 84 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"HandleAefExtension: The packet is not large enough to contain the ciphertext: %d < %d\n",
        a4,
        v10 + 84);
    return 2147942487LL;
  }
  if ( v7 != v10 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
    {
      v11 = v7;
      v12 = L"HandleAefExtension: The packet does not make sense based on cbHeaderLength: %d != %d";
      goto LABEL_25;
    }
    return 2147942487LL;
  }
  return AeadCryptoWrapper::Decrypt(a1[26], a2 + 92, a2, 0x54u, &a2[v9 + 84], v13);
}

```

## disassembly

```asm
0x180057b60  push    rbx
0x180057b62  push    rbp
0x180057b63  push    rsi
0x180057b64  push    rdi
0x180057b65  push    r12
0x180057b67  push    r13
0x180057b69  push    r14
0x180057b6b  push    r15
0x180057b6d  sub     rsp, 38h
0x180057b71  mov     ebx, r9d
0x180057b74  mov     rsi, rdx
0x180057b77  mov     r13, rcx
0x180057b7a  cmp     r9d, 5Ch ; '\'
0x180057b7e  jnb     short loc_180057BA8
0x180057b80  xor     ecx, ecx
0x180057b82  call    FileLogAllowEntry
0x180057b87  test    al, al
0x180057b89  jz      loc_180057D1F
0x180057b8f  mov     r8d, 5Ch ; '\'
0x180057b95  mov     edx, ebx
0x180057b97  lea     rcx, aHandleaefexten_7; "HandleAefExtension: The packet is not l"...
0x180057b9e  call    FileLogAdd
0x180057ba3  jmp     loc_180057D1F
0x180057ba8  movzx   ecx, word ptr [rdx+56h]; netshort
0x180057bac  call    cs:__imp_ntohs
0x180057bb3  nop     dword ptr [rax+rax+00h]
0x180057bb8  movzx   edi, ax
0x180057bbb  mov     r14d, 0C8h
0x180057bc1  mov     ecx, r14d
0x180057bc4  call    FileLogAllowEntry
0x180057bc9  test    al, al
0x180057bcb  jz      short loc_180057BDB
0x180057bcd  mov     edx, edi
0x180057bcf  lea     rcx, aHandleaefexten_0; "HandleAefExtension: cbHeaderLength is :"...
0x180057bd6  call    FileLogAdd
0x180057bdb  lea     ebp, [rdi+54h]
0x180057bde  cmp     ebx, ebp
0x180057be0  jnb     short loc_180057C02
0x180057be2  xor     ecx, ecx
0x180057be4  call    FileLogAllowEntry
0x180057be9  test    al, al
0x180057beb  jz      loc_180057D1F
0x180057bf1  mov     r8d, ebp
0x180057bf4  mov     edx, ebx
0x180057bf6  lea     rcx, aHandleaefexten_3; "HandleAefExtension: The packet is not l"...
0x180057bfd  jmp     loc_180057D1A
0x180057c02  movzx   ecx, word ptr [rsi+58h]; netshort
0x180057c06  call    cs:__imp_ntohs
0x180057c0d  nop     dword ptr [rax+rax+00h]
0x180057c12  movzx   ebp, ax
0x180057c15  mov     ecx, r14d
0x180057c18  call    FileLogAllowEntry
0x180057c1d  test    al, al
0x180057c1f  jz      short loc_180057C2F
0x180057c21  mov     edx, ebp
0x180057c23  lea     rcx, aHandleaefexten_2; "HandleAefExtension: cbNonceLength is : "...
0x180057c2a  call    FileLogAdd
0x180057c2f  mov     eax, ebp
0x180057c31  and     eax, 3
0x180057c34  mov     r12d, 4
0x180057c3a  mov     ecx, r12d
0x180057c3d  sub     ecx, eax
0x180057c3f  neg     eax
0x180057c41  sbb     eax, eax
0x180057c43  and     eax, ecx
0x180057c45  add     ebp, 8
0x180057c48  add     ebp, eax
0x180057c4a  lea     r14d, [rbp+54h]
0x180057c4e  cmp     ebx, r14d
0x180057c51  jnb     short loc_180057C70
0x180057c53  xor     ecx, ecx
0x180057c55  call    FileLogAllowEntry
0x180057c5a  test    al, al
0x180057c5c  jz      loc_180057D1F
0x180057c62  mov     edx, ebx
0x180057c64  lea     rcx, aHandleaefexten_5; "HandleAefExtension: The packet is not l"...
0x180057c6b  jmp     loc_180057D17
0x180057c70  cmp     edi, ebp
0x180057c72  ja      short loc_180057C94
0x180057c74  xor     ecx, ecx
0x180057c76  call    FileLogAllowEntry
0x180057c7b  test    al, al
0x180057c7d  jz      loc_180057D1F
0x180057c83  mov     r8d, ebp
0x180057c86  mov     edx, edi
0x180057c88  lea     rcx, aHandleaefexten_4; "HandleAefExtension: The packet does not"...
0x180057c8f  jmp     loc_180057D1A
0x180057c94  movzx   ecx, word ptr [rsi+5Ah]; netshort
0x180057c98  call    cs:__imp_ntohs
0x180057c9f  nop     dword ptr [rax+rax+00h]
0x180057ca4  movzx   r15d, ax
0x180057ca8  mov     ecx, 0C8h
0x180057cad  call    FileLogAllowEntry
0x180057cb2  test    al, al
0x180057cb4  jz      short loc_180057CC5
0x180057cb6  mov     edx, r15d
0x180057cb9  lea     rcx, aHandleaefexten_6; "HandleAefExtension: cbCipherLength is :"...
0x180057cc0  call    FileLogAdd
0x180057cc5  mov     eax, r15d
0x180057cc8  and     eax, 3
0x180057ccb  sub     r12d, eax
0x180057cce  neg     eax
0x180057cd0  sbb     eax, eax
0x180057cd2  and     eax, r12d
0x180057cd5  lea     r14d, [rax+rbp]
0x180057cd9  add     r14d, r15d
0x180057cdc  lea     r12d, [r14+54h]
0x180057ce0  cmp     ebx, r12d
0x180057ce3  jnb     short loc_180057CFE
0x180057ce5  xor     ecx, ecx
0x180057ce7  call    FileLogAllowEntry
0x180057cec  test    al, al
0x180057cee  jz      short loc_180057D1F
0x180057cf0  mov     r8d, r12d
0x180057cf3  mov     edx, ebx
0x180057cf5  lea     rcx, aHandleaefexten; "HandleAefExtension: The packet is not l"...
0x180057cfc  jmp     short loc_180057D1A
0x180057cfe  cmp     edi, r14d
0x180057d01  jz      short loc_180057D26
0x180057d03  xor     ecx, ecx
0x180057d05  call    FileLogAllowEntry
0x180057d0a  test    al, al
0x180057d0c  jz      short loc_180057D1F
0x180057d0e  mov     edx, edi
0x180057d10  lea     rcx, aHandleaefexten_1; "HandleAefExtension: The packet does not"...
0x180057d17  mov     r8d, r14d
0x180057d1a  call    FileLogAdd
0x180057d1f  mov     eax, 80070057h
0x180057d24  jmp     short loc_180057D53
0x180057d26  mov     ecx, ebp
0x180057d28  add     rcx, 54h ; 'T'
0x180057d2c  add     rcx, rsi
0x180057d2f  lea     rdx, [rsi+5Ch]; unsigned __int8 *
0x180057d33  mov     [rsp+78h+var_50], r15d; unsigned int
0x180057d38  mov     [rsp+78h+var_58], rcx; unsigned __int8 *
0x180057d3d  mov     r9d, 54h ; 'T'; unsigned int
0x180057d43  mov     r8, rsi; unsigned __int8 *
0x180057d46  mov     rcx, [r13+0D0h]; this
0x180057d4d  call    ?Decrypt@AeadCryptoWrapper@@UEAAJPEAE0K0K@Z; AeadCryptoWrapper::Decrypt(uchar *,uchar *,ulong,uchar *,ulong)
0x180057d52  nop
0x180057d53  add     rsp, 38h
0x180057d57  pop     r15
0x180057d59  pop     r14
0x180057d5b  pop     r13
0x180057d5d  pop     r12
0x180057d5f  pop     rdi
0x180057d60  pop     rsi
0x180057d61  pop     rbp
0x180057d62  pop     rbx
0x180057d63  retn
```
