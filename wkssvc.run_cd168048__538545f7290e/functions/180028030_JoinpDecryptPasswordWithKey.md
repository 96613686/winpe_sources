# JoinpDecryptPasswordWithKey

- ea: `0x180028030`
- end: `0x1800282d3`
- name: `JoinpDecryptPasswordWithKey`
- size: `675`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029fc0`
- `0x18002a610`
- `0x18002a930`
- `0x18002ac90`
- `0x18002ae70`
- `0x18002b330`
- `0x18002b510`
- `0x18002b870`

## callees

- `0x180007cd4`
- `0x1800081b0`
- `0x18001fbd0`
- `0x180028000`
- `0x180028030`
- `0x180036191`

## import_xrefs

- `ntdll!RtlRunEncodeUnicodeString` at `0x180028297`
- `ntdll!RtlRunEncodeUnicodeString` at `0x180028297`
- `ntdll!RtlInitUnicodeString` at `0x180028283`
- `ntdll!RtlInitUnicodeString` at `0x180028283`
- `bcrypt!BCryptDestroyKey` at `0x180028147`
- `bcrypt!BCryptDestroyKey` at `0x1800281e0`
- `bcrypt!BCryptDestroyKey` at `0x180028147`
- `bcrypt!BCryptDestroyKey` at `0x1800281e0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002817b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18002817b`
- `bcrypt!BCryptEncrypt` at `0x1800281c7`
- `bcrypt!BCryptEncrypt` at `0x1800281c7`
- `bcrypt!BCryptFinishHash` at `0x180028115`
- `bcrypt!BCryptFinishHash` at `0x180028115`
- `bcrypt!BCryptCreateHash` at `0x1800280c8`
- `bcrypt!BCryptCreateHash` at `0x1800280c8`
- `bcrypt!BCryptDestroyHash` at `0x18002812e`
- `bcrypt!BCryptDestroyHash` at `0x18002812e`
- `CRYPTBASE!SystemFunction029` at `0x18002808f`
- `CRYPTBASE!SystemFunction029` at `0x18002808f`

## pseudocode

```c
__int64 __fastcall JoinpDecryptPasswordWithKey(__int64 a1, __int64 a2, int a3, __int64 *a4)
{
  NTSTATUS v7; // eax
  unsigned int v9; // ecx
  __int64 v10; // rax
  void *v11; // rdi
  __int64 v12; // rax
  _BYTE *i; // rbx
  UCHAR Hash[8]; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-21h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v19; // [rsp+88h] [rbp+Fh]
  __int128 v20; // [rsp+90h] [rbp+17h] BYREF

  hKey = 0;
  v19 = 0;
  Hash[0] = 0;
  *a4 = 0;
  *(_OWORD *)phHash = 0;
  DestinationString = 0;
  if ( a2 )
  {
    v20 = 0;
    v7 = SystemFunction029(a1, &v20);
    if ( v7 < 0 )
      return NetpNtStatusToApiStatus(v7);
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    CngRsa32Compat_MD5Update(phHash, &v20, 16);
    CngRsa32Compat_MD5Update(phHash, a2, 8);
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyHash(phHash[0]);
    phHash[0] = 0;
    if ( hKey )
    {
      BCryptDestroyKey(hKey);
      hKey = 0;
    }
    if ( BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x71, &hKey, 0, 0, (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    pcbResult = 0;
    if ( BCryptEncrypt(hKey, (PUCHAR)(a2 + 8), 0x204u, 0, 0, 0, (PUCHAR)(a2 + 8), 0x204u, &pcbResult, 0) < 0 )
      __fastfail(7u);
    BCryptDestroyKey(hKey);
    v9 = *(_DWORD *)(a2 + 520);
    hKey = 0;
    if ( v9 > 0x200 )
      return 86;
    v10 = NetpMemoryAllocate(v9 + 4);
    *a4 = v10;
    v11 = (void *)v10;
    if ( !v10 )
      return 8;
    if ( a3 )
      v11 = (void *)(v10 + 2);
    memcpy_0(v11, (const void *)(a2 - *(unsigned int *)(a2 + 520) + 520), *(unsigned int *)(a2 + 520));
    *((_WORD *)v11 + ((unsigned __int64)*(unsigned int *)(a2 + 520) >> 1)) = 0;
    v12 = *(unsigned int *)(a2 + 520);
    for ( i = (_BYTE *)(a2 - v12 + 520); v12; --v12 )
      *i++ = 0;
    if ( a3 )
    {
      RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
      RtlRunEncodeUnicodeString(Hash, &DestinationString);
      *(_WORD *)*a4 = Hash[0];
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028030  mov     [rsp-8+arg_10], rbx
0x180028035  push    rbp
0x180028036  push    rsi
0x180028037  push    rdi
0x180028038  push    r12
0x18002803a  push    r14
0x18002803c  lea     rbp, [rsp-37h]
0x180028041  sub     rsp, 0B0h
0x180028048  mov     rax, cs:__security_cookie
0x18002804f  xor     rax, rsp
0x180028052  mov     [rbp+57h+var_30], rax
0x180028056  xor     r12d, r12d
0x180028059  xor     eax, eax
0x18002805b  mov     [rbp+57h+hKey], r12
0x18002805f  xorps   xmm0, xmm0
0x180028062  mov     [rbp+57h+var_48], rax
0x180028066  mov     rsi, r9
0x180028069  mov     [rbp+57h+Hash], r12b
0x18002806d  mov     r14d, r8d
0x180028070  mov     [r9], r12
0x180028073  mov     rbx, rdx
0x180028076  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x18002807a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002807e  test    rdx, rdx
0x180028081  jz      loc_1800282AD
0x180028087  lea     rdx, [rbp+57h+var_40]
0x18002808b  movups  [rbp+57h+var_40], xmm0
0x18002808f  call    cs:__imp_SystemFunction029
0x180028096  nop     dword ptr [rax+rax+00h]
0x18002809b  test    eax, eax
0x18002809d  jns     short loc_1800280AB
0x18002809f  mov     ecx, eax; Status
0x1800280a1  call    NetpNtStatusToApiStatus
0x1800280a6  jmp     loc_1800282AF
0x1800280ab  xor     r9d, r9d; cbHashObject
0x1800280ae  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x1800280b3  mov     [rsp+0D0h+cbSecret], r12d; cbSecret
0x1800280b8  lea     rdx, [rbp+57h+phHash]; phHash
0x1800280bc  xor     r8d, r8d; pbHashObject
0x1800280bf  mov     [rsp+0D0h+pbSecret], r12; pbSecret
0x1800280c4  lea     ecx, [r9+21h]; hAlgorithm
0x1800280c8  call    cs:__imp_BCryptCreateHash
0x1800280cf  nop     dword ptr [rax+rax+00h]
0x1800280d4  mov     edi, 7
0x1800280d9  test    eax, eax
0x1800280db  jns     short loc_1800280E1
0x1800280dd  mov     ecx, edi
0x1800280df  int     29h; Win8: RtlFailFast(ecx)
0x1800280e1  mov     r8d, 10h
0x1800280e7  lea     rdx, [rbp+57h+var_40]
0x1800280eb  lea     rcx, [rbp+57h+phHash]
0x1800280ef  call    CngRsa32Compat_MD5Update
0x1800280f4  mov     r8d, 8
0x1800280fa  lea     rcx, [rbp+57h+phHash]
0x1800280fe  mov     rdx, rbx
0x180028101  call    CngRsa32Compat_MD5Update
0x180028106  mov     rcx, [rbp+57h+phHash]; hHash
0x18002810a  lea     rdx, [rbp+57h+phHash+8]; pbOutput
0x18002810e  xor     r9d, r9d; dwFlags
0x180028111  lea     r8d, [r9+10h]; cbOutput
0x180028115  call    cs:__imp_BCryptFinishHash
0x18002811c  nop     dword ptr [rax+rax+00h]
0x180028121  test    eax, eax
0x180028123  jns     short loc_18002812A
0x180028125  mov     rcx, rdi
0x180028128  int     29h; Win8: RtlFailFast(ecx)
0x18002812a  mov     rcx, [rbp+57h+phHash]; hHash
0x18002812e  call    cs:__imp_BCryptDestroyHash
0x180028135  nop     dword ptr [rax+rax+00h]
0x18002813a  mov     rcx, [rbp+57h+hKey]; hKey
0x18002813e  mov     [rbp+57h+phHash], r12
0x180028142  test    rcx, rcx
0x180028145  jz      short loc_180028157
0x180028147  call    cs:__imp_BCryptDestroyKey
0x18002814e  nop     dword ptr [rax+rax+00h]
0x180028153  mov     [rbp+57h+hKey], r12
0x180028157  xor     r9d, r9d; cbKeyObject
0x18002815a  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x18002815f  lea     rax, [rbp+57h+phHash+8]
0x180028163  mov     [rsp+0D0h+cbSecret], 10h; cbSecret
0x18002816b  xor     r8d, r8d; pbKeyObject
0x18002816e  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x180028173  lea     rdx, [rbp+57h+hKey]; phKey
0x180028177  lea     ecx, [r9+71h]; hAlgorithm
0x18002817b  call    cs:__imp_BCryptGenerateSymmetricKey
0x180028182  nop     dword ptr [rax+rax+00h]
0x180028187  test    eax, eax
0x180028189  jns     short loc_180028190
0x18002818b  mov     rcx, rdi
0x18002818e  int     29h; Win8: RtlFailFast(ecx)
0x180028190  mov     rcx, [rbp+57h+hKey]; hKey
0x180028194  lea     rax, [rbp+57h+var_70]
0x180028198  mov     [rsp+0D0h+var_88], r12d; dwFlags
0x18002819d  lea     rdx, [rbx+8]; pbInput
0x1800281a1  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x1800281a6  mov     r8d, 204h; cbInput
0x1800281ac  mov     [rsp+0D0h+cbOutput], r8d; cbOutput
0x1800281b1  xor     r9d, r9d; pPaddingInfo
0x1800281b4  mov     qword ptr [rsp+0D0h+dwFlags], rdx; pbOutput
0x1800281b9  mov     [rsp+0D0h+cbSecret], r12d; cbIV
0x1800281be  mov     [rsp+0D0h+pbSecret], r12; pbIV
0x1800281c3  mov     [rbp+57h+var_70], r12d
0x1800281c7  call    cs:__imp_BCryptEncrypt
0x1800281ce  nop     dword ptr [rax+rax+00h]
0x1800281d3  test    eax, eax
0x1800281d5  jns     short loc_1800281DC
0x1800281d7  mov     rcx, rdi
0x1800281da  int     29h; Win8: RtlFailFast(ecx)
0x1800281dc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800281e0  call    cs:__imp_BCryptDestroyKey
0x1800281e7  nop     dword ptr [rax+rax+00h]
0x1800281ec  mov     ecx, [rbx+208h]
0x1800281f2  mov     [rbp+57h+hKey], r12
0x1800281f6  cmp     ecx, 200h
0x1800281fc  jbe     short loc_180028208
0x1800281fe  mov     eax, 56h ; 'V'
0x180028203  jmp     loc_1800282AF
0x180028208  add     ecx, 4
0x18002820b  call    NetpMemoryAllocate
0x180028210  mov     [rsi], rax
0x180028213  mov     rdi, rax
0x180028216  test    rax, rax
0x180028219  jnz     short loc_180028223
0x18002821b  lea     eax, [rdi+8]
0x18002821e  jmp     loc_1800282AF
0x180028223  test    r14d, r14d
0x180028226  jz      short loc_18002822C
0x180028228  add     rdi, 2
0x18002822c  mov     r8d, [rbx+208h]; Size
0x180028233  mov     rdx, rbx
0x180028236  sub     rdx, r8
0x180028239  mov     rcx, rdi; void *
0x18002823c  add     rdx, 208h; Src
0x180028243  call    memcpy_0
0x180028248  mov     ecx, [rbx+208h]
0x18002824e  shr     rcx, 1
0x180028251  mov     [rdi+rcx*2], r12w
0x180028256  mov     eax, [rbx+208h]
0x18002825c  sub     rbx, rax
0x18002825f  add     rbx, 208h
0x180028266  test    rax, rax
0x180028269  jz      short loc_180028277
0x18002826b  mov     [rbx], r12b
0x18002826e  inc     rbx
0x180028271  sub     rax, 1
0x180028275  jnz     short loc_18002826B
0x180028277  test    r14d, r14d
0x18002827a  jz      short loc_1800282AD
0x18002827c  mov     rdx, rdi; SourceString
0x18002827f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180028283  call    cs:__imp_RtlInitUnicodeString
0x18002828a  nop     dword ptr [rax+rax+00h]
0x18002828f  lea     rdx, [rbp+57h+DestinationString]; String
0x180028293  lea     rcx, [rbp+57h+Hash]; Hash
0x180028297  call    cs:__imp_RtlRunEncodeUnicodeString
0x18002829e  nop     dword ptr [rax+rax+00h]
0x1800282a3  mov     rax, [rsi]
0x1800282a6  movzx   ecx, [rbp+57h+Hash]
0x1800282aa  mov     [rax], cx
0x1800282ad  xor     eax, eax
0x1800282af  mov     rcx, [rbp+57h+var_30]
0x1800282b3  xor     rcx, rsp; StackCookie
0x1800282b6  call    __security_check_cookie
0x1800282bb  mov     rbx, [rsp+0D0h+arg_10]
0x1800282c3  add     rsp, 0B0h
0x1800282ca  pop     r14
0x1800282cc  pop     r12
0x1800282ce  pop     rdi
0x1800282cf  pop     rsi
0x1800282d0  pop     rbp
0x1800282d1  retn
```
