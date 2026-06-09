# JoinpDecryptPasswordWithKey

- ea: `0x180026088`
- end: `0x1800262f8`
- name: `JoinpDecryptPasswordWithKey`
- size: `624`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64 *)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027c90`
- `0x180028260`
- `0x180028560`
- `0x1800288a0`
- `0x180028a80`
- `0x180028ee0`
- `0x1800290c0`
- `0x1800293e0`

## callees

- `0x180007710`
- `0x180007c80`
- `0x18001e420`
- `0x180026088`
- `0x180033159`

## import_xrefs

- `ntdll!RtlRunEncodeUnicodeString` at `0x1800262c8`
- `ntdll!RtlRunEncodeUnicodeString` at `0x1800262c8`
- `ntdll!RtlInitUnicodeString` at `0x1800262ba`
- `ntdll!RtlInitUnicodeString` at `0x1800262ba`
- `bcrypt!BCryptDestroyKey` at `0x18002619e`
- `bcrypt!BCryptDestroyKey` at `0x180026222`
- `bcrypt!BCryptDestroyKey` at `0x18002619e`
- `bcrypt!BCryptDestroyKey` at `0x180026222`
- `bcrypt!BCryptHashData` at `0x18002613e`
- `bcrypt!BCryptHashData` at `0x18002615b`
- `bcrypt!BCryptHashData` at `0x18002613e`
- `bcrypt!BCryptHashData` at `0x18002615b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800261c9`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800261c9`
- `bcrypt!BCryptEncrypt` at `0x18002620f`
- `bcrypt!BCryptEncrypt` at `0x18002620f`
- `bcrypt!BCryptFinishHash` at `0x180026178`
- `bcrypt!BCryptFinishHash` at `0x180026178`
- `bcrypt!BCryptCreateHash` at `0x180026119`
- `bcrypt!BCryptCreateHash` at `0x180026119`
- `bcrypt!BCryptDestroyHash` at `0x18002618b`
- `bcrypt!BCryptDestroyHash` at `0x18002618b`
- `CRYPTBASE!SystemFunction029` at `0x1800260e6`
- `CRYPTBASE!SystemFunction029` at `0x1800260e6`

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
  UCHAR Hash[8]; // [rsp+50h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-31h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v19; // [rsp+88h] [rbp-1h]
  UCHAR pbInput[16]; // [rsp+90h] [rbp+7h] BYREF

  hKey = 0;
  v19 = 0;
  Hash[0] = 0;
  *a4 = 0;
  *(_OWORD *)phHash = 0;
  DestinationString = 0;
  if ( a2 )
  {
    *(_OWORD *)pbInput = 0;
    v7 = SystemFunction029(a1, pbInput);
    if ( v7 < 0 )
      return NetpNtStatusToApiStatus(v7);
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], pbInput, 0x10u, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], (PUCHAR)a2, 8u, 0) < 0 )
      __fastfail(7u);
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
0x180026088  push    rbp
0x18002608a  push    rbx
0x18002608b  push    rsi
0x18002608c  push    rdi
0x18002608d  push    r12
0x18002608f  push    r14
0x180026091  push    r15
0x180026093  lea     rbp, [rsp-27h]
0x180026098  sub     rsp, 0B0h
0x18002609f  mov     rax, cs:__security_cookie
0x1800260a6  xor     rax, rsp
0x1800260a9  mov     [rbp+57h+var_40], rax
0x1800260ad  xor     r12d, r12d
0x1800260b0  xor     eax, eax
0x1800260b2  mov     [rbp+57h+hKey], r12
0x1800260b6  xorps   xmm0, xmm0
0x1800260b9  mov     [rbp+57h+var_58], rax
0x1800260bd  mov     rsi, r9
0x1800260c0  mov     [rbp+57h+Hash], r12b
0x1800260c4  mov     r14d, r8d
0x1800260c7  mov     [r9], r12
0x1800260ca  mov     rbx, rdx
0x1800260cd  movups  xmmword ptr [rbp+57h+phHash], xmm0
0x1800260d1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800260d5  test    rdx, rdx
0x1800260d8  jz      loc_1800262D8
0x1800260de  lea     rdx, [rbp+57h+pbInput]
0x1800260e2  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x1800260e6  call    cs:__imp_SystemFunction029
0x1800260ec  test    eax, eax
0x1800260ee  jns     short loc_1800260FC
0x1800260f0  mov     ecx, eax; Status
0x1800260f2  call    NetpNtStatusToApiStatus
0x1800260f7  jmp     loc_1800262DA
0x1800260fc  xor     r9d, r9d; cbHashObject
0x1800260ff  mov     [rsp+0E0h+dwFlags], r12d; dwFlags
0x180026104  mov     [rsp+0E0h+cbSecret], r12d; cbSecret
0x180026109  lea     rdx, [rbp+57h+phHash]; phHash
0x18002610d  xor     r8d, r8d; pbHashObject
0x180026110  mov     [rsp+0E0h+pbSecret], r12; pbSecret
0x180026115  lea     ecx, [r9+21h]; hAlgorithm
0x180026119  call    cs:__imp_BCryptCreateHash
0x18002611f  mov     edi, 7
0x180026124  test    eax, eax
0x180026126  jns     short loc_18002612C
0x180026128  mov     ecx, edi
0x18002612a  int     29h; Win8: RtlFailFast(ecx)
0x18002612c  mov     rcx, [rbp+57h+phHash]; hHash
0x180026130  lea     rdx, [rbp+57h+pbInput]; pbInput
0x180026134  xor     r9d, r9d; dwFlags
0x180026137  lea     r15d, [r9+10h]
0x18002613b  mov     r8d, r15d; cbInput
0x18002613e  call    cs:__imp_BCryptHashData
0x180026144  test    eax, eax
0x180026146  jns     short loc_18002614D
0x180026148  mov     rcx, rdi
0x18002614b  int     29h; Win8: RtlFailFast(ecx)
0x18002614d  mov     rcx, [rbp+57h+phHash]; hHash
0x180026151  xor     r9d, r9d; dwFlags
0x180026154  mov     rdx, rbx; pbInput
0x180026157  lea     r8d, [r9+8]; cbInput
0x18002615b  call    cs:__imp_BCryptHashData
0x180026161  test    eax, eax
0x180026163  jns     short loc_18002616A
0x180026165  mov     rcx, rdi
0x180026168  int     29h; Win8: RtlFailFast(ecx)
0x18002616a  mov     rcx, [rbp+57h+phHash]; hHash
0x18002616e  lea     rdx, [rbp+57h+phHash+8]; pbOutput
0x180026172  xor     r9d, r9d; dwFlags
0x180026175  mov     r8d, r15d; cbOutput
0x180026178  call    cs:__imp_BCryptFinishHash
0x18002617e  test    eax, eax
0x180026180  jns     short loc_180026187
0x180026182  mov     rcx, rdi
0x180026185  int     29h; Win8: RtlFailFast(ecx)
0x180026187  mov     rcx, [rbp+57h+phHash]; hHash
0x18002618b  call    cs:__imp_BCryptDestroyHash
0x180026191  mov     rcx, [rbp+57h+hKey]; hKey
0x180026195  mov     [rbp+57h+phHash], r12
0x180026199  test    rcx, rcx
0x18002619c  jz      short loc_1800261A8
0x18002619e  call    cs:__imp_BCryptDestroyKey
0x1800261a4  mov     [rbp+57h+hKey], r12
0x1800261a8  xor     r9d, r9d; cbKeyObject
0x1800261ab  mov     [rsp+0E0h+dwFlags], r12d; dwFlags
0x1800261b0  lea     rax, [rbp+57h+phHash+8]
0x1800261b4  mov     [rsp+0E0h+cbSecret], r15d; cbSecret
0x1800261b9  xor     r8d, r8d; pbKeyObject
0x1800261bc  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x1800261c1  lea     rdx, [rbp+57h+hKey]; phKey
0x1800261c5  lea     ecx, [r9+71h]; hAlgorithm
0x1800261c9  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800261cf  test    eax, eax
0x1800261d1  jns     short loc_1800261D8
0x1800261d3  mov     rcx, rdi
0x1800261d6  int     29h; Win8: RtlFailFast(ecx)
0x1800261d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800261dc  lea     rax, [rbp+57h+var_80]
0x1800261e0  mov     [rsp+0E0h+var_98], r12d; dwFlags
0x1800261e5  lea     rdx, [rbx+8]; pbInput
0x1800261e9  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x1800261ee  mov     r8d, 204h; cbInput
0x1800261f4  mov     [rsp+0E0h+cbOutput], r8d; cbOutput
0x1800261f9  xor     r9d, r9d; pPaddingInfo
0x1800261fc  mov     qword ptr [rsp+0E0h+dwFlags], rdx; pbOutput
0x180026201  mov     [rsp+0E0h+cbSecret], r12d; cbIV
0x180026206  mov     [rsp+0E0h+pbSecret], r12; pbIV
0x18002620b  mov     [rbp+57h+var_80], r12d
0x18002620f  call    cs:__imp_BCryptEncrypt
0x180026215  test    eax, eax
0x180026217  jns     short loc_18002621E
0x180026219  mov     rcx, rdi
0x18002621c  int     29h; Win8: RtlFailFast(ecx)
0x18002621e  mov     rcx, [rbp+57h+hKey]; hKey
0x180026222  call    cs:__imp_BCryptDestroyKey
0x180026228  mov     ecx, [rbx+208h]
0x18002622e  mov     [rbp+57h+hKey], r12
0x180026232  cmp     ecx, 200h
0x180026238  jbe     short loc_180026244
0x18002623a  mov     eax, 56h ; 'V'
0x18002623f  jmp     loc_1800262DA
0x180026244  add     ecx, 4
0x180026247  call    NetpMemoryAllocate
0x18002624c  mov     [rsi], rax
0x18002624f  mov     rdi, rax
0x180026252  test    rax, rax
0x180026255  jnz     short loc_18002625C
0x180026257  lea     eax, [rdi+8]
0x18002625a  jmp     short loc_1800262DA
0x18002625c  test    r14d, r14d
0x18002625f  jz      short loc_180026265
0x180026261  add     rdi, 2
0x180026265  mov     r8d, [rbx+208h]; Size
0x18002626c  mov     rdx, rbx
0x18002626f  sub     rdx, r8
0x180026272  mov     r15d, 208h
0x180026278  add     rdx, r15; Src
0x18002627b  mov     rcx, rdi; void *
0x18002627e  call    memcpy_0
0x180026283  mov     ecx, [rbx+208h]
0x180026289  shr     rcx, 1
0x18002628c  mov     [rdi+rcx*2], r12w
0x180026291  mov     eax, [rbx+208h]
0x180026297  sub     rbx, rax
0x18002629a  add     rbx, r15
0x18002629d  test    rax, rax
0x1800262a0  jz      short loc_1800262AE
0x1800262a2  mov     [rbx], r12b
0x1800262a5  inc     rbx
0x1800262a8  sub     rax, 1
0x1800262ac  jnz     short loc_1800262A2
0x1800262ae  test    r14d, r14d
0x1800262b1  jz      short loc_1800262D8
0x1800262b3  mov     rdx, rdi; SourceString
0x1800262b6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800262ba  call    cs:__imp_RtlInitUnicodeString
0x1800262c0  lea     rdx, [rbp+57h+DestinationString]; String
0x1800262c4  lea     rcx, [rbp+57h+Hash]; Hash
0x1800262c8  call    cs:__imp_RtlRunEncodeUnicodeString
0x1800262ce  mov     rax, [rsi]
0x1800262d1  movzx   ecx, [rbp+57h+Hash]
0x1800262d5  mov     [rax], cx
0x1800262d8  xor     eax, eax
0x1800262da  mov     rcx, [rbp+57h+var_40]
0x1800262de  xor     rcx, rsp; StackCookie
0x1800262e1  call    __security_check_cookie
0x1800262e6  add     rsp, 0B0h
0x1800262ed  pop     r15
0x1800262ef  pop     r14
0x1800262f1  pop     r12
0x1800262f3  pop     rdi
0x1800262f4  pop     rsi
0x1800262f5  pop     rbx
0x1800262f6  pop     rbp
0x1800262f7  retn
```
