# WxpObfuscateKey

- ea: `0x180016eb4`
- end: `0x1800172b1`
- name: `WxpObfuscateKey`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800127a0`

## callees

- `0x180006620`
- `0x18001672c`
- `0x180016e30`
- `0x180016eb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ffc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001728c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ffc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017191`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001728c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180016ff2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800170be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180017187`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180017276`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180016ff2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800170be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180017187`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180017276`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180016fbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017092`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017158`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017231`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180016fbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017092`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017158`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180017231`
- `CRYPTBASE!SystemFunction036` at `0x180016f3f`
- `CRYPTBASE!SystemFunction036` at `0x180017014`
- `CRYPTBASE!SystemFunction036` at `0x1800170d5`
- `CRYPTBASE!SystemFunction036` at `0x1800171a0`
- `CRYPTBASE!SystemFunction036` at `0x1800171b5`
- `CRYPTBASE!SystemFunction036` at `0x180017242`
- `CRYPTBASE!SystemFunction036` at `0x180016f3f`
- `CRYPTBASE!SystemFunction036` at `0x180017014`
- `CRYPTBASE!SystemFunction036` at `0x1800170d5`
- `CRYPTBASE!SystemFunction036` at `0x1800171a0`
- `CRYPTBASE!SystemFunction036` at `0x1800171b5`
- `CRYPTBASE!SystemFunction036` at `0x180017242`

## pseudocode

```c
char __fastcall WxpObfuscateKey(__int64 a1)
{
  __int64 v2; // rax
  HKEY v3; // rbx
  __int64 i; // rdx
  char v5; // r14
  CHAR *v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ecx
  int v9; // edi
  CHAR *v10; // rsi
  unsigned __int64 v11; // rax
  CHAR *v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ecx
  CHAR *v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ecx
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-21h] BYREF
  __int128 RandomBuffer; // [rsp+60h] [rbp-19h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  CHAR Class[16]; // [rsp+80h] [rbp+7h] BYREF

  hKey = 0;
  dwDisposition = 0;
  v22 = 0;
  RandomBuffer = 0;
  v2 = OpenLsaKey();
  v3 = (HKEY)v2;
  if ( v2 )
  {
    for ( i = 0; i != 16; ++i )
      Class[i - 16] = *(_BYTE *)(*((unsigned __int8 *)qword_180022530 + i) + a1);
    WxpDeleteLocalKey();
    v5 = 0;
    Class[8] = 0;
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v6 = Class;
    v7 = 0;
    do
    {
      v8 = (unsigned __int8)Class[v7++ - 16];
      *v6 = a0123456789abcd[(unsigned __int64)v8 >> 4];
      v6 += 2;
      *(v6 - 1) = a0123456789abcd[v8 & 0xF];
    }
    while ( v7 != 4 );
    if ( RegCreateKeyExA(v3, "JD", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
      goto LABEL_28;
    RegSetValueExA(hKey, "Lookup", 0, 3u, (const BYTE *)&RandomBuffer, 6u);
    RegCloseKey(hKey);
    v9 = 0;
    v10 = Class;
    while ( v9 < 4 )
    {
      if ( !SystemFunction036(&RandomBuffer, 0x10u) )
        goto LABEL_28;
      v11 = (unsigned __int8)Class[v9 - 12];
      *v10 = a0123456789abcd[v11 >> 4];
      v10[1] = a0123456789abcd[v11 & 0xF];
      v10 += 2;
      ++v9;
    }
    if ( !RegCreateKeyExA(v3, "Skew1", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "SkewMatrix", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v12 = Class;
    v13 = 0;
    do
    {
      v14 = (unsigned __int8)Class[v13++ - 8];
      *v12 = a0123456789abcd[(unsigned __int64)v14 >> 4];
      v12 += 2;
      *(v12 - 1) = a0123456789abcd[v14 & 0xF];
    }
    while ( v13 != 4 );
    if ( !RegCreateKeyExA(v3, "GBG", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      RegSetValueExA(hKey, "GrafBlumGroup", 0, 3u, (const BYTE *)&RandomBuffer, 9u);
      RegCloseKey(hKey);
    }
    if ( !SystemFunction036(&v22, 8u) || !SystemFunction036(&RandomBuffer, 0x10u) )
      goto LABEL_28;
    v15 = Class;
    v16 = 0;
    do
    {
      v17 = (unsigned __int8)Class[v16++ - 4];
      *v15 = a0123456789abcd[(unsigned __int64)v17 >> 4];
      v15 += 2;
      *(v15 - 1) = a0123456789abcd[v17 & 0xF];
    }
    while ( v16 != 4 );
    if ( !RegCreateKeyExA(v3, "Data", 0, Class, 0, 0x20006u, 0, &hKey, &dwDisposition) )
    {
      if ( !SystemFunction036(&v22, 0x10u) )
      {
        RegCloseKey(hKey);
LABEL_28:
        RegCloseKey(v3);
        LOBYTE(v2) = v5;
        return v2;
      }
      RegSetValueExA(hKey, "Pattern", 0, 3u, (const BYTE *)&RandomBuffer, 0x10u);
      RegCloseKey(hKey);
    }
    v5 = 1;
    goto LABEL_28;
  }
  return v2;
}

```

## disassembly

```asm
0x180016eb4  push    rbp
0x180016eb6  push    rbx
0x180016eb7  push    rsi
0x180016eb8  push    rdi
0x180016eb9  push    r12
0x180016ebb  push    r14
0x180016ebd  lea     rbp, [rsp-2Fh]
0x180016ec2  sub     rsp, 0A8h
0x180016ec9  mov     rax, cs:__security_cookie
0x180016ed0  xor     rax, rsp
0x180016ed3  mov     [rbp+57h+var_40], rax
0x180016ed7  xorps   xmm0, xmm0
0x180016eda  mov     [rbp+57h+hKey], 0
0x180016ee2  xorps   xmm1, xmm1
0x180016ee5  mov     [rbp+57h+dwDisposition], 0
0x180016eec  movups  [rbp+57h+var_60], xmm0
0x180016ef0  mov     rdi, rcx
0x180016ef3  movups  [rbp+57h+RandomBuffer], xmm1
0x180016ef7  call    OpenLsaKey
0x180016efc  mov     rbx, rax
0x180016eff  test    rax, rax
0x180016f02  jz      loc_180017295
0x180016f08  xor     edx, edx
0x180016f0a  lea     rsi, __ImageBase
0x180016f11  lea     r12d, [rdx+10h]
0x180016f15  movzx   eax, byte ptr [rdx+rsi+22530h]
0x180016f1d  mov     cl, [rax+rdi]
0x180016f20  mov     byte ptr [rbp+rdx+57h+var_60], cl
0x180016f24  inc     rdx
0x180016f27  cmp     rdx, r12
0x180016f2a  jnz     short loc_180016F15
0x180016f2c  call    WxpDeleteLocalKey
0x180016f31  xor     r14b, r14b
0x180016f34  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180016f38  mov     edx, r12d; RandomBufferLength
0x180016f3b  mov     [rbp+57h+var_48], r14b
0x180016f3f  call    cs:__imp_SystemFunction036
0x180016f45  test    al, al
0x180016f47  jz      loc_180017289
0x180016f4d  lea     rdx, [rbp+57h+Class]
0x180016f51  xor     r8d, r8d
0x180016f54  movzx   ecx, byte ptr [rbp+r8+57h+var_60]
0x180016f5a  inc     r8
0x180016f5d  mov     eax, ecx
0x180016f5f  and     ecx, 0Fh
0x180016f62  shr     rax, 4
0x180016f66  mov     al, [rax+rsi+22510h]
0x180016f6d  mov     [rdx], al
0x180016f6f  lea     rdx, [rdx+2]
0x180016f73  mov     al, [rcx+rsi+22510h]
0x180016f7a  mov     [rdx-1], al
0x180016f7d  cmp     r8, 4
0x180016f81  jnz     short loc_180016F54
0x180016f83  lea     rax, [rbp+57h+dwDisposition]
0x180016f87  xor     r8d, r8d; Reserved
0x180016f8a  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180016f8f  lea     r9, [rbp+57h+Class]; lpClass
0x180016f93  lea     rax, [rbp+57h+hKey]
0x180016f97  mov     rcx, rbx; hKey
0x180016f9a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180016f9f  lea     rdx, aJd; "JD"
0x180016fa6  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016faf  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x180016fb7  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180016fbf  call    cs:__imp_RegCreateKeyExA
0x180016fc5  test    eax, eax
0x180016fc7  jnz     loc_180017289
0x180016fcd  mov     rcx, [rbp+57h+hKey]; hKey
0x180016fd1  lea     rax, [rbp+57h+RandomBuffer]
0x180016fd5  mov     [rsp+0D0h+samDesired], 6; cbData
0x180016fdd  lea     rdx, aLookup; "Lookup"
0x180016fe4  mov     r9d, 3; dwType
0x180016fea  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180016fef  xor     r8d, r8d; Reserved
0x180016ff2  call    cs:__imp_RegSetValueExA
0x180016ff8  mov     rcx, [rbp+57h+hKey]; hKey
0x180016ffc  call    cs:__imp_RegCloseKey
0x180017002  xor     edi, edi
0x180017004  lea     rsi, [rbp+57h+Class]
0x180017008  cmp     edi, 4
0x18001700b  jge     short loc_180017055
0x18001700d  mov     edx, r12d; RandomBufferLength
0x180017010  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x180017014  call    cs:__imp_SystemFunction036
0x18001701a  test    al, al
0x18001701c  jz      loc_180017289
0x180017022  movsxd  rax, edi
0x180017025  lea     rdx, __ImageBase
0x18001702c  movzx   ecx, byte ptr [rbp+rax+57h+var_60+4]
0x180017031  mov     eax, ecx
0x180017033  and     ecx, 0Fh
0x180017036  shr     rax, 4
0x18001703a  mov     al, [rax+rdx+22510h]
0x180017041  mov     [rsi], al
0x180017043  mov     al, [rcx+rdx+22510h]
0x18001704a  mov     [rsi+1], al
0x18001704d  add     rsi, 2
0x180017051  inc     edi
0x180017053  jmp     short loc_180017008
0x180017055  lea     rax, [rbp+57h+dwDisposition]
0x180017059  mov     esi, 20006h
0x18001705e  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180017063  lea     r9, [rbp+57h+Class]; lpClass
0x180017067  lea     rax, [rbp+57h+hKey]
0x18001706b  xor     r8d, r8d; Reserved
0x18001706e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180017073  lea     rdx, aSkew1; "Skew1"
0x18001707a  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180017083  mov     rcx, rbx; hKey
0x180017086  mov     [rsp+0D0h+samDesired], esi; samDesired
0x18001708a  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180017092  call    cs:__imp_RegCreateKeyExA
0x180017098  test    eax, eax
0x18001709a  jnz     short loc_1800170CE
0x18001709c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800170a0  lea     rax, [rbp+57h+RandomBuffer]
0x1800170a4  mov     [rsp+0D0h+samDesired], r12d; cbData
0x1800170a9  lea     rdx, aSkewmatrix; "SkewMatrix"
0x1800170b0  mov     r9d, 3; dwType
0x1800170b6  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x1800170bb  xor     r8d, r8d; Reserved
0x1800170be  call    cs:__imp_RegSetValueExA
0x1800170c4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800170c8  call    cs:__imp_RegCloseKey
0x1800170ce  mov     edx, r12d; RandomBufferLength
0x1800170d1  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800170d5  call    cs:__imp_SystemFunction036
0x1800170db  test    al, al
0x1800170dd  jz      loc_180017289
0x1800170e3  lea     rdx, [rbp+57h+Class]
0x1800170e7  xor     r8d, r8d
0x1800170ea  lea     rdi, __ImageBase
0x1800170f1  movzx   ecx, byte ptr [rbp+r8+57h+var_60+8]
0x1800170f7  inc     r8
0x1800170fa  mov     eax, ecx
0x1800170fc  and     ecx, 0Fh
0x1800170ff  shr     rax, 4
0x180017103  mov     al, [rax+rdi+22510h]
0x18001710a  mov     [rdx], al
0x18001710c  lea     rdx, [rdx+2]
0x180017110  mov     al, [rcx+rdi+22510h]
0x180017117  mov     [rdx-1], al
0x18001711a  cmp     r8, 4
0x18001711e  jnz     short loc_1800170F1
0x180017120  lea     rax, [rbp+57h+dwDisposition]
0x180017124  xor     r8d, r8d; Reserved
0x180017127  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18001712c  lea     r9, [rbp+57h+Class]; lpClass
0x180017130  lea     rax, [rbp+57h+hKey]
0x180017134  mov     rcx, rbx; hKey
0x180017137  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001713c  lea     rdx, aGbg; "GBG"
0x180017143  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001714c  mov     [rsp+0D0h+samDesired], esi; samDesired
0x180017150  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180017158  call    cs:__imp_RegCreateKeyExA
0x18001715e  test    eax, eax
0x180017160  jnz     short loc_180017197
0x180017162  mov     rcx, [rbp+57h+hKey]; hKey
0x180017166  lea     rax, [rbp+57h+RandomBuffer]
0x18001716a  mov     [rsp+0D0h+samDesired], 9; cbData
0x180017172  lea     rdx, aGrafblumgroup; "GrafBlumGroup"
0x180017179  mov     r9d, 3; dwType
0x18001717f  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180017184  xor     r8d, r8d; Reserved
0x180017187  call    cs:__imp_RegSetValueExA
0x18001718d  mov     rcx, [rbp+57h+hKey]; hKey
0x180017191  call    cs:__imp_RegCloseKey
0x180017197  mov     edx, 8; RandomBufferLength
0x18001719c  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x1800171a0  call    cs:__imp_SystemFunction036
0x1800171a6  test    al, al
0x1800171a8  jz      loc_180017289
0x1800171ae  mov     edx, r12d; RandomBufferLength
0x1800171b1  lea     rcx, [rbp+57h+RandomBuffer]; RandomBuffer
0x1800171b5  call    cs:__imp_SystemFunction036
0x1800171bb  test    al, al
0x1800171bd  jz      loc_180017289
0x1800171c3  lea     rdx, [rbp+57h+Class]
0x1800171c7  xor     r8d, r8d
0x1800171ca  movzx   ecx, byte ptr [rbp+r8+57h+var_60+0Ch]
0x1800171d0  inc     r8
0x1800171d3  mov     eax, ecx
0x1800171d5  and     ecx, 0Fh
0x1800171d8  shr     rax, 4
0x1800171dc  mov     al, [rax+rdi+22510h]
0x1800171e3  mov     [rdx], al
0x1800171e5  lea     rdx, [rdx+2]
0x1800171e9  mov     al, [rcx+rdi+22510h]
0x1800171f0  mov     [rdx-1], al
0x1800171f3  cmp     r8, 4
0x1800171f7  jnz     short loc_1800171CA
0x1800171f9  lea     rax, [rbp+57h+dwDisposition]
0x1800171fd  xor     r8d, r8d; Reserved
0x180017200  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180017205  lea     r9, [rbp+57h+Class]; lpClass
0x180017209  lea     rax, [rbp+57h+hKey]
0x18001720d  mov     rcx, rbx; hKey
0x180017210  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180017215  lea     rdx, aData; "Data"
0x18001721c  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180017225  mov     [rsp+0D0h+samDesired], esi; samDesired
0x180017229  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180017231  call    cs:__imp_RegCreateKeyExA
0x180017237  test    eax, eax
0x180017239  jnz     short loc_180017286
0x18001723b  mov     edx, r12d; RandomBufferLength
0x18001723e  lea     rcx, [rbp+57h+var_60]; RandomBuffer
0x180017242  call    cs:__imp_SystemFunction036
0x180017248  mov     rcx, [rbp+57h+hKey]; hKey
0x18001724c  test    al, al
0x18001724e  jnz     short loc_180017258
0x180017250  call    cs:__imp_RegCloseKey
0x180017256  jmp     short loc_180017289
0x180017258  lea     rax, [rbp+57h+RandomBuffer]
0x18001725c  mov     [rsp+0D0h+samDesired], r12d; cbData
0x180017261  mov     r9d, 3; dwType
0x180017267  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18001726c  xor     r8d, r8d; Reserved
0x18001726f  lea     rdx, aPattern; "Pattern"
0x180017276  call    cs:__imp_RegSetValueExA
0x18001727c  mov     rcx, [rbp+57h+hKey]; hKey
0x180017280  call    cs:__imp_RegCloseKey
0x180017286  mov     r14b, 1
0x180017289  mov     rcx, rbx; hKey
0x18001728c  call    cs:__imp_RegCloseKey
0x180017292  mov     al, r14b
0x180017295  mov     rcx, [rbp+57h+var_40]
0x180017299  xor     rcx, rsp; StackCookie
0x18001729c  call    __security_check_cookie
0x1800172a1  add     rsp, 0A8h
0x1800172a8  pop     r14
0x1800172aa  pop     r12
0x1800172ac  pop     rdi
0x1800172ad  pop     rsi
0x1800172ae  pop     rbx
0x1800172af  pop     rbp
0x1800172b0  retn
```
