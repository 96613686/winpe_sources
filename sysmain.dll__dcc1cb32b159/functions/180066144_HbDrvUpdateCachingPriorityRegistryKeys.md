# HbDrvUpdateCachingPriorityRegistryKeys

- ea: `0x180066144`
- end: `0x18006648c`
- name: `HbDrvUpdateCachingPriorityRegistryKeys`
- size: `840`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a6088`
- `0x1800a6758`

## callees

- `0x180066144`
- `0x1800b644e`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateKey` at `0x1800662a9`
- `ntdll!NtCreateKey` at `0x1800662a9`
- `ntdll!RtlComputeCrc32` at `0x180066359`
- `ntdll!RtlComputeCrc32` at `0x1800663df`
- `ntdll!RtlComputeCrc32` at `0x180066359`
- `ntdll!RtlComputeCrc32` at `0x1800663df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066214`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066464`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066214`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066464`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006641d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006641d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006642f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006642f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066306`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066306`

## pseudocode

```c
__int64 __fastcall HbDrvUpdateCachingPriorityRegistryKeys(int a1, int a2, __int64 a3, int a4)
{
  HKEY v6; // rdx
  unsigned int v8; // ecx
  int v9; // eax
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rdi
  wchar_t *v13; // rdx
  __int64 v14; // rcx
  wchar_t *v15; // rax
  __int16 v16; // cx
  const WCHAR *v17; // r8
  __int64 i; // rcx
  int v19; // ebx
  unsigned int v20; // edx
  __int64 j; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-81h] BYREF
  DWORD pdwType; // [rsp+50h] [rbp-79h] BYREF
  __int128 v26; // [rsp+58h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-59h] BYREF
  UCHAR Buffer[16]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 Buf2; // [rsp+B0h] [rbp-19h] BYREF
  __int128 pvData; // [rsp+B8h] [rbp-11h] BYREF
  __int64 Buf1; // [rsp+C8h] [rbp-1h] BYREF

  pcbData = 0;
  pdwType = 0;
  Buf1 = 0;
  Buf2 = 0;
  v6 = 0;
  KeyHandle = 0;
  v26 = 0;
  memset(&ObjectAttributes, 0, 44);
  pvData = 0;
  *(_OWORD *)Buffer = 0;
  if ( a1 )
  {
    v8 = a2 - 1;
    *(_DWORD *)&Buffer[4] = 3;
    Buffer[12] = 1;
    if ( (unsigned int)(a2 - 1) <= 1 )
      v8 = 1;
    if ( v8 >= 0xF )
      LOWORD(v8) = 15;
    v9 = *(_DWORD *)(a3 + 24);
    WORD2(Buf2) = v8;
    LODWORD(Buf2) = v9;
    v10 = 0;
    if ( a4 == 1 )
      v10 = 0x10000;
    HIDWORD(Buf2) = HIDWORD(Buf2) & 0xFFFEFFFF | v10;
  }
  v11 = 0;
  v12 = 0;
  while ( 1 )
  {
    if ( v6 )
    {
      RegCloseKey(v6);
      KeyHandle = 0;
    }
    v13 = off_1800B8000[v12];
    v26 = 0;
    if ( v13 )
    {
      v14 = 0x7FFF;
      v15 = v13;
      while ( *v15 )
      {
        ++v15;
        if ( !--v14 )
          goto LABEL_18;
      }
      v16 = 2 * v14;
      *((_QWORD *)&v26 + 1) = v13;
      LOWORD(v26) = -2 - v16;
      WORD1(v26) = -v16;
    }
LABEL_18:
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtCreateKey(&KeyHandle, 3u, &ObjectAttributes, 0, 0, 0, 0) >= 0 )
    {
      if ( a1 != 1 || a4 != 1 && !LODWORD(off_1800B8000[v12 + 2]) )
      {
        RegDeleteValueW((HKEY)KeyHandle, off_1800B8000[v12 + 1]);
        goto LABEL_39;
      }
      v17 = off_1800B8000[v12 + 1];
      pcbData = 24;
      if ( RegGetValueW((HKEY)KeyHandle, 0, v17, 0xFFFFu, &pdwType, &pvData, &pcbData) )
        goto LABEL_35;
      if ( pdwType != 3 )
        goto LABEL_35;
      if ( pcbData != 24 )
        goto LABEL_35;
      for ( i = 0; i != 20; *((_BYTE *)&pvData + i++ + 4) ^= pvData )
        ;
      if ( DWORD1(pvData) != 3 )
        goto LABEL_35;
      if ( BYTE12(pvData) > 1u )
        goto LABEL_35;
      v19 = pvData;
      LODWORD(pvData) = 0;
      LODWORD(pvData) = RtlComputeCrc32(0, (PUCHAR)&pvData, 0x18u);
      if ( (_DWORD)pvData != v19 )
        goto LABEL_35;
      v20 = 0;
      if ( BYTE12(pvData) )
      {
        while ( (unsigned int)*((unsigned __int16 *)&Buf1 + 4 * v20 + 2) - 1 <= 0xFD )
        {
          if ( ++v20 >= BYTE12(pvData) )
            goto LABEL_33;
        }
LABEL_35:
        *(_DWORD *)Buffer = 0;
        *(_DWORD *)&Buffer[8] = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
        *(_DWORD *)Buffer = RtlComputeCrc32(0, Buffer, 0x18u);
        for ( j = 0; j != 20; ++j )
          Buffer[j + 4] ^= Buffer[0];
        RegSetValueExW((HKEY)KeyHandle, off_1800B8000[v12 + 1], 0, 3u, Buffer, 0x18u);
        goto LABEL_39;
      }
LABEL_33:
      if ( BYTE12(pvData) != Buffer[12] || memcmp_0(&Buf1, &Buf2, 8u) )
        goto LABEL_35;
    }
LABEL_39:
    ++v11;
    v12 += 3;
    if ( v11 == 2 )
      break;
    v6 = (HKEY)KeyHandle;
  }
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  return 0;
}

```

## disassembly

```asm
0x180066144  push    rbp
0x180066146  push    rbx
0x180066147  push    rsi
0x180066148  push    rdi
0x180066149  push    r12
0x18006614b  push    r13
0x18006614d  push    r14
0x18006614f  push    r15
0x180066151  lea     rbp, [rsp-1Fh]
0x180066156  sub     rsp, 0E8h
0x18006615d  mov     rax, cs:__security_cookie
0x180066164  xor     rax, rsp
0x180066167  mov     [rbp+57h+var_50], rax
0x18006616b  xorps   xmm0, xmm0
0x18006616e  xor     r12d, r12d
0x180066171  mov     r15d, ecx
0x180066174  mov     [rsp+120h+pcbData], r12d
0x180066179  xor     ecx, ecx
0x18006617b  mov     [rbp+57h+pdwType], r12d
0x18006617f  mov     [rbp+57h+Buf1], rcx
0x180066183  mov     eax, edx
0x180066185  mov     [rbp+57h+Buf2], rcx
0x180066189  mov     edx, r12d
0x18006618c  mov     [rsp+120h+KeyHandle], rdx
0x180066191  mov     r14d, r9d
0x180066194  lea     r13d, [rcx+1]
0x180066198  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18006619c  movups  [rbp+57h+var_C8], xmm0
0x1800661a0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800661a4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800661a8  movups  [rbp+57h+pvData], xmm0
0x1800661ac  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1800661b0  test    r15d, r15d
0x1800661b3  jz      short loc_1800661F9
0x1800661b5  lea     ecx, [rax-1]
0x1800661b8  mov     dword ptr [rbp+57h+Buffer+4], 3
0x1800661bf  cmp     ecx, r13d
0x1800661c2  mov     [rbp+57h+Buffer+0Ch], r13b
0x1800661c6  lea     eax, [r12+0Fh]
0x1800661cb  cmovbe  ecx, r13d
0x1800661cf  cmp     ecx, eax
0x1800661d1  cmovnb  ecx, eax
0x1800661d4  mov     eax, [r8+18h]
0x1800661d8  mov     word ptr [rbp+57h+Buf2+4], cx
0x1800661dc  cmp     r9d, r13d
0x1800661df  mov     dword ptr [rbp+57h+Buf2], eax
0x1800661e2  mov     ecx, r12d
0x1800661e5  mov     eax, 10000h
0x1800661ea  cmovz   ecx, eax
0x1800661ed  mov     eax, dword ptr [rbp+57h+Buf2+4]
0x1800661f0  btr     eax, 10h
0x1800661f4  or      ecx, eax
0x1800661f6  mov     dword ptr [rbp+57h+Buf2+4], ecx
0x1800661f9  mov     rsi, r12
0x1800661fc  lea     rbx, off_1800B8000; "\\Registry\\Machine\\System\\CurrentCon"...
0x180066203  mov     rdi, r12
0x180066206  mov     r8d, 2
0x18006620c  test    rdx, rdx
0x18006620f  jz      short loc_180066225
0x180066211  mov     rcx, rdx; hKey
0x180066214  call    cs:__imp_RegCloseKey
0x18006621a  mov     r8d, 2
0x180066220  mov     [rsp+120h+KeyHandle], r12
0x180066225  mov     rdx, [rdi+rbx]
0x180066229  xorps   xmm0, xmm0
0x18006622c  movups  [rbp+57h+var_C8], xmm0
0x180066230  test    rdx, rdx
0x180066233  jz      short loc_180066268
0x180066235  mov     ecx, 7FFFh
0x18006623a  mov     rax, rdx
0x18006623d  cmp     [rax], r12w
0x180066241  jz      short loc_18006624D
0x180066243  add     rax, r8
0x180066246  sub     rcx, r13
0x180066249  jnz     short loc_18006623D
0x18006624b  jmp     short loc_180066268
0x18006624d  add     cx, cx
0x180066250  mov     qword ptr [rbp+57h+var_C8+8], rdx
0x180066254  mov     eax, 0FFFEh
0x180066259  sub     ax, cx
0x18006625c  mov     word ptr [rbp+57h+var_C8], ax
0x180066260  add     ax, r8w
0x180066264  mov     word ptr [rbp+57h+var_C8+2], ax
0x180066268  xor     r9d, r9d; TitleIndex
0x18006626b  mov     [rsp+120h+Disposition], r12; Disposition
0x180066270  lea     rax, [rbp+57h+var_C8]
0x180066274  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x180066279  xorps   xmm0, xmm0
0x18006627c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180066283  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180066287  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18006628b  lea     edx, [r9+3]; DesiredAccess
0x18006628f  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180066296  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18006629b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18006629f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800662a4  mov     [rsp+120h+Class], r12; Class
0x1800662a9  call    cs:__imp_NtCreateKey
0x1800662af  test    eax, eax
0x1800662b1  js      loc_18006643E
0x1800662b7  cmp     r15d, r13d
0x1800662ba  jnz     loc_180066425
0x1800662c0  cmp     r14d, r13d
0x1800662c3  jz      short loc_1800662D0
0x1800662c5  cmp     [rdi+rbx+10h], r12d
0x1800662ca  jz      loc_180066425
0x1800662d0  mov     r8, [rdi+rbx+8]; lpValue
0x1800662d5  lea     rax, [rsp+120h+pcbData]
0x1800662da  mov     rcx, [rsp+120h+KeyHandle]; hkey
0x1800662df  mov     r9d, 0FFFFh; dwFlags
0x1800662e5  mov     [rsp+120h+Disposition], rax; pcbData
0x1800662ea  xor     edx, edx; lpSubKey
0x1800662ec  lea     rax, [rbp+57h+pvData]
0x1800662f0  mov     [rsp+120h+pcbData], 18h
0x1800662f8  mov     qword ptr [rsp+120h+CreateOptions], rax; pvData
0x1800662fd  lea     rax, [rbp+57h+pdwType]
0x180066301  mov     [rsp+120h+Class], rax; pdwType
0x180066306  call    cs:__imp_RegGetValueW
0x18006630c  test    eax, eax
0x18006630e  jnz     loc_1800663B5
0x180066314  cmp     [rbp+57h+pdwType], 3
0x180066318  jnz     loc_1800663B5
0x18006631e  cmp     [rsp+120h+pcbData], 18h
0x180066323  jnz     loc_1800663B5
0x180066329  mov     rcx, r12
0x18006632c  mov     al, byte ptr [rbp+57h+pvData]
0x18006632f  xor     byte ptr [rbp+rcx+57h+pvData+4], al
0x180066333  add     rcx, r13
0x180066336  cmp     rcx, 14h
0x18006633a  jnz     short loc_18006632C
0x18006633c  cmp     dword ptr [rbp+57h+pvData+4], 3
0x180066340  jnz     short loc_1800663B5
0x180066342  cmp     byte ptr [rbp+57h+pvData+0Ch], r13b
0x180066346  ja      short loc_1800663B5
0x180066348  mov     ebx, dword ptr [rbp+57h+pvData]
0x18006634b  lea     r8d, [rcx+4]; Length
0x18006634f  xor     ecx, ecx; InitialCrc
0x180066351  mov     dword ptr [rbp+57h+pvData], r12d
0x180066355  lea     rdx, [rbp+57h+pvData]; Buffer
0x180066359  call    cs:__imp_RtlComputeCrc32
0x18006635f  mov     dword ptr [rbp+57h+pvData], eax
0x180066362  cmp     eax, ebx
0x180066364  jnz     short loc_1800663AE
0x180066366  movzx   r8d, byte ptr [rbp+57h+pvData+0Ch]
0x18006636b  mov     edx, r12d
0x18006636e  test    r8b, r8b
0x180066371  jz      short loc_18006638D
0x180066373  mov     eax, edx
0x180066375  movzx   ecx, word ptr [rbp+rax*8+57h+Buf1+4]
0x18006637a  sub     ecx, r13d
0x18006637d  cmp     ecx, 0FDh
0x180066383  ja      short loc_1800663AE
0x180066385  add     edx, r13d
0x180066388  cmp     edx, r8d
0x18006638b  jb      short loc_180066373
0x18006638d  cmp     r8b, [rbp+57h+Buffer+0Ch]
0x180066391  jnz     short loc_1800663AE
0x180066393  mov     r8d, 8; Size
0x180066399  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18006639d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800663a1  call    memcmp_0
0x1800663a6  test    eax, eax
0x1800663a8  jz      loc_180066437
0x1800663ae  lea     rbx, off_1800B8000; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800663b5  mov     dword ptr [rbp+57h+Buffer], r12d
0x1800663b9  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800663bd  mov     eax, 7FFE0320h
0x1800663c2  mov     r8d, 18h; Length
0x1800663c8  mov     rax, [rax]
0x1800663cb  mov     ecx, ds:7FFE0004h
0x1800663d2  imul    rcx, rax
0x1800663d6  shr     rcx, 18h
0x1800663da  mov     dword ptr [rbp+57h+Buffer+8], ecx
0x1800663dd  xor     ecx, ecx; InitialCrc
0x1800663df  call    cs:__imp_RtlComputeCrc32
0x1800663e5  mov     dword ptr [rbp+57h+Buffer], eax
0x1800663e8  mov     rcx, r12
0x1800663eb  mov     al, [rbp+57h+Buffer]
0x1800663ee  xor     [rbp+rcx+57h+Buffer+4], al
0x1800663f2  add     rcx, r13
0x1800663f5  cmp     rcx, 14h
0x1800663f9  jnz     short loc_1800663EB
0x1800663fb  mov     rdx, [rdi+rbx+8]; lpValueName
0x180066400  lea     rax, [rbp+57h+Buffer]
0x180066404  lea     r9d, [rcx-11h]; dwType
0x180066408  mov     [rsp+120h+CreateOptions], 18h; cbData
0x180066410  mov     rcx, [rsp+120h+KeyHandle]; hKey
0x180066415  xor     r8d, r8d; Reserved
0x180066418  mov     [rsp+120h+Class], rax; lpData
0x18006641d  call    cs:__imp_RegSetValueExW
0x180066423  jmp     short loc_18006643E
0x180066425  mov     rdx, [rdi+rbx+8]; lpValueName
0x18006642a  mov     rcx, [rsp+120h+KeyHandle]; hKey
0x18006642f  call    cs:__imp_RegDeleteValueW
0x180066435  jmp     short loc_18006643E
0x180066437  lea     rbx, off_1800B8000; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006643e  inc     rsi
0x180066441  add     rdi, 18h
0x180066445  mov     r8d, 2
0x18006644b  cmp     rsi, r8
0x18006644e  jz      short loc_18006645A
0x180066450  mov     rdx, [rsp+120h+KeyHandle]
0x180066455  jmp     loc_18006620C
0x18006645a  mov     rcx, [rsp+120h+KeyHandle]; hKey
0x18006645f  test    rcx, rcx
0x180066462  jz      short loc_18006646A
0x180066464  call    cs:__imp_RegCloseKey
0x18006646a  xor     eax, eax
0x18006646c  mov     rcx, [rbp+57h+var_50]
0x180066470  xor     rcx, rsp; StackCookie
0x180066473  call    __security_check_cookie
0x180066478  add     rsp, 0E8h
0x18006647f  pop     r15
0x180066481  pop     r14
0x180066483  pop     r13
0x180066485  pop     r12
0x180066487  pop     rdi
0x180066488  pop     rsi
0x180066489  pop     rbx
0x18006648a  pop     rbp
0x18006648b  retn
```
