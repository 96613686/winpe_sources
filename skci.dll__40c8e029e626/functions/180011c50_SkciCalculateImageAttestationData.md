# SkciCalculateImageAttestationData

- ea: `0x180011c50`
- end: `0x180011dcf`
- name: `SkciCalculateImageAttestationData`
- size: `383`
- prototype: `__int64 __fastcall(char, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012660`

## callees

- `0x18001156c`
- `0x180011c50`
- `0x180018d68`
- `0x180033950`
- `0x180033980`
- `0x180047600`

## import_xrefs

- `securekernel!RtlFreeUnicodeString` at `0x180011d86`
- `securekernel!RtlFreeUnicodeString` at `0x180011d86`
- `securekernel!RtlCompareUnicodeString` at `0x180011d72`
- `securekernel!RtlCompareUnicodeString` at `0x180011d72`

## pseudocode

```c
__int64 __fastcall SkciCalculateImageAttestationData(char a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r14d
  __int64 result; // rax
  unsigned int v15; // ecx
  __int128 v16; // xmm0
  int v17; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-49h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-39h] BYREF
  int v20; // [rsp+40h] [rbp-29h] BYREF
  __int128 v21; // [rsp+45h] [rbp-24h]
  int v22; // [rsp+55h] [rbp-14h]

  memset_0(&v20, 0, 0x48u);
  *(_QWORD *)&String2.Length = 2359330;
  String2.Buffer = (wchar_t *)"M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00 \x00W\x00i\x00n\x00d\x00o\x00w\x00s";
  v8 = *(unsigned int *)(a3 + 32);
  String1 = 0;
  if ( (_DWORD)v8 )
    v8 = ((_BYTE)v8 - 1) & 3;
  v9 = a3 + 160 * v8;
  v10 = *(_QWORD *)(v9 + 56);
  if ( !v10 || !*(_DWORD *)(v10 + 48) )
    return 3221225860LL;
  LOBYTE(v7) = *(_BYTE *)(v9 + 92);
  LOBYTE(v6) = 12;
  v11 = CiCompareSigningLevels(v7, v6);
  *(_DWORD *)(a2 + 284) = 0;
  *(_OWORD *)(a2 + 288) = 0;
  v13 = v11;
  result = 0;
  *(_DWORD *)(a2 + 304) = 0;
  *(_OWORD *)(a2 + 312) = 0;
  if ( (a1 & 5) != 0 )
  {
    result = SkciGetCertificateThumbprint(v12, v9 + 40, &v20);
    v15 = result;
    if ( (int)result >= 0 )
    {
      if ( v20 == 32772 )
      {
        v16 = v21;
        *(_DWORD *)(a2 + 284) = 32772;
        v17 = v22;
        *(_OWORD *)(a2 + 288) = v16;
        *(_DWORD *)(a2 + 304) = v17;
      }
      if ( !v13 && *(_DWORD *)(v10 + 56) )
      {
        if ( (int)MincryptGetOpusProgramNameFromAuthenticatedAttributes(v10 + 56, &String1) >= 0 )
        {
          if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
            *(UNICODE_STRING *)(a2 + 312) = String1;
          else
            RtlFreeUnicodeString(&String1);
        }
        return 0;
      }
      return v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011c50  mov     [rsp-8+arg_0], rbx
0x180011c55  push    rbp
0x180011c56  push    rsi
0x180011c57  push    rdi
0x180011c58  push    r14
0x180011c5a  push    r15
0x180011c5c  lea     rbp, [rsp-37h]
0x180011c61  sub     rsp, 0A0h
0x180011c68  mov     rax, cs:__security_cookie
0x180011c6f  xor     rax, rsp
0x180011c72  mov     [rbp+57h+var_30], rax
0x180011c76  mov     rbx, rdx
0x180011c79  mov     rdi, r8
0x180011c7c  xor     edx, edx; Val
0x180011c7e  mov     r15d, ecx
0x180011c81  lea     rcx, [rbp+57h+var_80]; void *
0x180011c85  lea     r8d, [rdx+48h]; Size
0x180011c89  call    memset_0
0x180011c8e  lea     rax, rgbMicrosoftAzureSkCertDomain0_Name+8; "M\x00i\x00c\x00r\x00o\x00s\x00o\x00f"...
0x180011c95  mov     qword ptr [rbp+57h+String2.Length], 240022h
0x180011c9d  mov     [rbp+57h+String2.Buffer], rax
0x180011ca1  xorps   xmm0, xmm0
0x180011ca4  mov     eax, [rdi+20h]
0x180011ca7  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x180011cab  test    eax, eax
0x180011cad  jz      short loc_180011CB4
0x180011caf  dec     eax
0x180011cb1  and     eax, 3
0x180011cb4  lea     rsi, [rax+rax*4]
0x180011cb8  shl     rsi, 5
0x180011cbc  add     rsi, rdi
0x180011cbf  mov     rdi, [rsi+38h]
0x180011cc3  test    rdi, rdi
0x180011cc6  jz      loc_180011DA6
0x180011ccc  cmp     dword ptr [rdi+30h], 0
0x180011cd0  jz      loc_180011DA6
0x180011cd6  mov     cl, [rsi+5Ch]
0x180011cd9  mov     dl, 0Ch
0x180011cdb  call    CiCompareSigningLevels
0x180011ce0  mov     dword ptr [rbx+11Ch], 0
0x180011cea  xorps   xmm0, xmm0
0x180011ced  movups  xmmword ptr [rbx+120h], xmm0
0x180011cf4  mov     r14d, eax
0x180011cf7  xor     eax, eax
0x180011cf9  mov     [rbx+130h], eax
0x180011cff  movups  xmmword ptr [rbx+138h], xmm0
0x180011d06  test    r15b, 5
0x180011d0a  jz      loc_180011DAB
0x180011d10  lea     r8, [rbp+57h+var_80]
0x180011d14  lea     rdx, [rsi+28h]
0x180011d18  call    SkciGetCertificateThumbprint
0x180011d1d  mov     ecx, eax
0x180011d1f  test    eax, eax
0x180011d21  js      loc_180011DAB
0x180011d27  mov     eax, 8004h
0x180011d2c  cmp     [rbp+57h+var_80], eax
0x180011d2f  jnz     short loc_180011D4B
0x180011d31  movups  xmm0, [rbp+57h+var_7B]
0x180011d35  mov     [rbx+11Ch], eax
0x180011d3b  mov     eax, [rbp+57h+var_6B]
0x180011d3e  movups  xmmword ptr [rbx+120h], xmm0
0x180011d45  mov     [rbx+130h], eax
0x180011d4b  test    r14d, r14d
0x180011d4e  jnz     short loc_180011DA2
0x180011d50  cmp     [rdi+38h], r14d
0x180011d54  jbe     short loc_180011DA2
0x180011d56  lea     rdx, [rbp+57h+String1]
0x180011d5a  lea     rcx, [rdi+38h]
0x180011d5e  call    MincryptGetOpusProgramNameFromAuthenticatedAttributes
0x180011d63  test    eax, eax
0x180011d65  js      short loc_180011DA0
0x180011d67  mov     r8b, 1; CaseInSensitive
0x180011d6a  lea     rdx, [rbp+57h+String2]; String2
0x180011d6e  lea     rcx, [rbp+57h+String1]; String1
0x180011d72  call    cs:__imp_RtlCompareUnicodeString
0x180011d79  nop     dword ptr [rax+rax+00h]
0x180011d7e  test    eax, eax
0x180011d80  jnz     short loc_180011D94
0x180011d82  lea     rcx, [rbp+57h+String1]; UnicodeString
0x180011d86  call    cs:__imp_RtlFreeUnicodeString
0x180011d8d  nop     dword ptr [rax+rax+00h]
0x180011d92  jmp     short loc_180011DA0
0x180011d94  movups  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x180011d98  movdqu  xmmword ptr [rbx+138h], xmm0
0x180011da0  xor     ecx, ecx
0x180011da2  mov     eax, ecx
0x180011da4  jmp     short loc_180011DAB
0x180011da6  mov     eax, 0C0000184h
0x180011dab  mov     rcx, [rbp+57h+var_30]
0x180011daf  xor     rcx, rsp; StackCookie
0x180011db2  call    __security_check_cookie
0x180011db7  mov     rbx, [rsp+0C0h+arg_0]
0x180011dbf  add     rsp, 0A0h
0x180011dc6  pop     r15
0x180011dc8  pop     r14
0x180011dca  pop     rdi
0x180011dcb  pop     rsi
0x180011dcc  pop     rbp
0x180011dcd  retn
```
