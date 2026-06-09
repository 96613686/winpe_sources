# ReadSecurityDescriptor(HKEY__ *,ushort *,bool,bool,CSecDescriptor * *)

- ea: `0x1800459e4`
- end: `0x180045d38`
- name: `?ReadSecurityDescriptor@@YAKPEAUHKEY__@@PEAG_N2PEAPEAVCSecDescriptor@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, __int64, __int64, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800456f8`

## callees

- `0x180034540`
- `0x1800459e4`
- `0x18005f3a0`
- `0x180070740`
- `0x180081210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045c58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045c58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045cc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045abb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045c1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045abb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180045c1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045a2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045af4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045a2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045af4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180045c35`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180045c35`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180045b8c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180045b8c`

## string_xrefs

- `0x180045a7d`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180045caf`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180045d19`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x180045a76`: `ReadSecurityDescriptor`
- `0x180045ca8`: `ReadSecurityDescriptor`
- `0x180045d04`: `ReadSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall ReadSecurityDescriptor(
        HKEY hKey,
        LPCWSTR lpValueName,
        __int64 a3,
        __int64 a4,
        struct CSecDescriptor **a5)
{
  struct CSecDescriptor **v5; // r14
  unsigned int v8; // ebx
  BYTE *lpData; // rsi
  unsigned int v11; // edi
  int v12; // r8d
  struct CSecDescriptor *v13; // rax
  struct CSecDescriptor *v14; // rbx
  HANDLE v15; // rcx
  int v16; // [rsp+30h] [rbp-38h]
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  SIZE_T dwBytes; // [rsp+88h] [rbp+20h] BYREF

  v5 = a5;
  Type = 0;
  LODWORD(dwBytes) = 0;
  *a5 = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, (LPDWORD)&dwBytes);
  if ( !v8 )
  {
    if ( Type != 3 || (unsigned int)dwBytes < 0x28 )
    {
      v8 = 11;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
          (unsigned int)"ReadSecurityDescriptor",
          516,
          0,
          (__int64)L"%ws %!WINERROR!",
          lpValueName,
          11);
      return v8;
    }
    lpData = (BYTE *)HeapAlloc(g_hHeap, 0, (unsigned int)dwBytes);
    if ( !lpData )
      return 14;
    v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, (LPDWORD)&dwBytes);
    if ( v11 )
    {
      if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
        goto LABEL_40;
      v16 = v11;
      v12 = 534;
    }
    else
    {
      if ( Type == 3 )
      {
        if ( *((_DWORD *)lpData + 2) && *((_DWORD *)lpData + 1) )
        {
          if ( IsValidSecurityDescriptor(lpData) )
          {
            if ( (unsigned int)IsValidCOMSecurityDescriptor(lpData, 0) )
            {
              v13 = (struct CSecDescriptor *)HeapAlloc(g_hHeap, 0, 0x10u);
              v14 = v13;
              if ( v13 )
              {
                *((_DWORD *)v13 + 3) = 1;
                *((_DWORD *)v13 + 2) = GetSecurityDescriptorLength(lpData);
                *(_QWORD *)v14 = lpData;
                *v5 = v14;
              }
              else
              {
                v15 = g_hHeap;
                *v5 = 0;
                HeapFree(v15, 0, lpData);
                return 14;
              }
              return v11;
            }
            v11 = 11;
            if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
            {
LABEL_40:
              HeapFree(g_hHeap, 0, lpData);
              return v11;
            }
            v12 = 560;
          }
          else
          {
            v11 = 11;
            if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
              goto LABEL_40;
            v12 = 553;
          }
        }
        else
        {
          v11 = 11;
          if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_40;
          v12 = 547;
        }
      }
      else
      {
        v11 = 11;
        if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
          goto LABEL_40;
        v12 = 541;
      }
      v16 = 11;
    }
    ComTraceMessageT<unsigned __int64,unsigned long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
      (unsigned int)"ReadSecurityDescriptor",
      v12,
      0,
      (__int64)L"%ws %!WINERROR!",
      lpValueName,
      v16);
    goto LABEL_40;
  }
  if ( gfEnableTracing )
  {
    if ( (unsigned __int8)IsWppLevelEnabled(3) )
      ComTraceMessageT<unsigned __int64,unsigned long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\registry.cxx",
        (unsigned int)"ReadSecurityDescriptor",
        510,
        3,
        (__int64)L"%ws %!WINERROR!",
        lpValueName,
        v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800459e4  mov     r11, rsp
0x1800459e7  mov     [r11+8], rbx
0x1800459eb  mov     [r11+20h], r9b
0x1800459ef  mov     [r11+18h], r8b
0x1800459f3  push    rbp
0x1800459f4  push    rsi
0x1800459f5  push    rdi
0x1800459f6  push    r14
0x1800459f8  push    r15
0x1800459fa  sub     rsp, 40h
0x1800459fe  mov     r14, [rsp+68h+arg_20]
0x180045a06  lea     rax, [r11+20h]
0x180045a0a  xor     r15d, r15d
0x180045a0d  mov     [r11-40h], rax
0x180045a11  lea     r9, [r11+18h]; lpType
0x180045a15  mov     [r11+18h], r15d
0x180045a19  xor     r8d, r8d; lpReserved
0x180045a1c  mov     [r11+20h], r15d
0x180045a20  mov     [r14], r15
0x180045a23  mov     rbp, rdx
0x180045a26  mov     rdi, rcx
0x180045a29  mov     [r11-48h], r15
0x180045a2d  call    cs:__imp_RegQueryValueExW
0x180045a33  mov     ebx, eax
0x180045a35  test    eax, eax
0x180045a37  jz      short loc_180045A8E
0x180045a39  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045a40  jz      loc_180045D25
0x180045a46  lea     ecx, [r15+3]
0x180045a4a  call    IsWppLevelEnabled
0x180045a4f  test    al, al
0x180045a51  jz      loc_180045D25
0x180045a57  mov     [rsp+68h+var_38], ebx
0x180045a5b  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x180045a62  mov     [rsp+68h+lpcbData], rbp
0x180045a67  lea     r9d, [r15+3]
0x180045a6b  mov     r8d, 1FEh
0x180045a71  mov     [rsp+68h+lpData], rax
0x180045a76  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x180045a7d  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x180045a84  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180045a89  jmp     loc_180045D25
0x180045a8e  cmp     [rsp+68h+Type], 3
0x180045a96  jnz     loc_180045CD1
0x180045a9c  cmp     dword ptr [rsp+68h+dwBytes], 28h ; '('
0x180045aa4  jb      loc_180045CD1
0x180045aaa  mov     r8d, dword ptr [rsp+68h+dwBytes]; dwBytes
0x180045ab2  xor     edx, edx; dwFlags
0x180045ab4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045abb  call    cs:__imp_HeapAlloc
0x180045ac1  mov     rsi, rax
0x180045ac4  test    rax, rax
0x180045ac7  jnz     short loc_180045AD1
0x180045ac9  lea     eax, [rsi+0Eh]
0x180045acc  jmp     loc_180045D27
0x180045ad1  lea     rax, [rsp+68h+dwBytes]
0x180045ad9  xor     r8d, r8d; lpReserved
0x180045adc  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180045ae1  lea     r9, [rsp+68h+Type]; lpType
0x180045ae9  mov     rdx, rbp; lpValueName
0x180045aec  mov     [rsp+68h+lpData], rsi; lpData
0x180045af1  mov     rcx, rdi; hKey
0x180045af4  call    cs:__imp_RegQueryValueExW
0x180045afa  mov     edi, eax
0x180045afc  test    eax, eax
0x180045afe  jz      short loc_180045B33
0x180045b00  mov     ecx, cs:dword_18014E4B8
0x180045b06  test    ecx, ecx
0x180045b08  jnz     short loc_180045B24
0x180045b0a  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045b11  jz      loc_180045CBB
0x180045b17  call    IsWppLevelEnabled
0x180045b1c  test    al, al
0x180045b1e  jz      loc_180045CBB
0x180045b24  mov     [rsp+68h+var_38], edi
0x180045b28  mov     r8d, 216h
0x180045b2e  jmp     loc_180045C94
0x180045b33  cmp     [rsp+68h+Type], 3
0x180045b3b  jz      short loc_180045B75
0x180045b3d  mov     eax, cs:dword_18014E4B8
0x180045b43  mov     ebx, 0Bh
0x180045b48  mov     edi, ebx
0x180045b4a  test    eax, eax
0x180045b4c  jnz     short loc_180045B6A
0x180045b4e  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045b55  jz      loc_180045CBB
0x180045b5b  xor     ecx, ecx
0x180045b5d  call    IsWppLevelEnabled
0x180045b62  test    al, al
0x180045b64  jz      loc_180045CBB
0x180045b6a  mov     r8d, 21Dh
0x180045b70  jmp     loc_180045C90
0x180045b75  cmp     [rsi+8], r15d
0x180045b79  jz      loc_180045C65
0x180045b7f  cmp     [rsi+4], r15d
0x180045b83  jz      loc_180045C65
0x180045b89  mov     rcx, rsi; pSecurityDescriptor
0x180045b8c  call    cs:__imp_IsValidSecurityDescriptor
0x180045b92  test    eax, eax
0x180045b94  jnz     short loc_180045BCC
0x180045b96  lea     ebx, [rax+0Bh]
0x180045b99  mov     eax, cs:dword_18014E4B8
0x180045b9f  mov     edi, ebx
0x180045ba1  test    eax, eax
0x180045ba3  jnz     short loc_180045BC1
0x180045ba5  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045bac  jz      loc_180045CBB
0x180045bb2  xor     ecx, ecx
0x180045bb4  call    IsWppLevelEnabled
0x180045bb9  test    al, al
0x180045bbb  jz      loc_180045CBB
0x180045bc1  mov     r8d, 229h
0x180045bc7  jmp     loc_180045C90
0x180045bcc  xor     edx, edx; int *
0x180045bce  mov     rcx, rsi; pSecurityDescriptor
0x180045bd1  call    ?IsValidCOMSecurityDescriptor@@YAHPEBU_SECURITY_DESCRIPTOR_RELATIVE@@PEAH@Z; IsValidCOMSecurityDescriptor(_SECURITY_DESCRIPTOR_RELATIVE const *,int *)
0x180045bd6  test    eax, eax
0x180045bd8  jnz     short loc_180045C10
0x180045bda  lea     ebx, [rax+0Bh]
0x180045bdd  mov     eax, cs:dword_18014E4B8
0x180045be3  mov     edi, ebx
0x180045be5  test    eax, eax
0x180045be7  jnz     short loc_180045C05
0x180045be9  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045bf0  jz      loc_180045CBB
0x180045bf6  xor     ecx, ecx
0x180045bf8  call    IsWppLevelEnabled
0x180045bfd  test    al, al
0x180045bff  jz      loc_180045CBB
0x180045c05  mov     r8d, 230h
0x180045c0b  jmp     loc_180045C90
0x180045c10  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045c17  xor     edx, edx; dwFlags
0x180045c19  lea     r8d, [rdx+10h]; dwBytes
0x180045c1d  call    cs:__imp_HeapAlloc
0x180045c23  mov     rbx, rax
0x180045c26  test    rax, rax
0x180045c29  jz      short loc_180045C49
0x180045c2b  mov     rcx, rsi; pSecurityDescriptor
0x180045c2e  mov     dword ptr [rax+0Ch], 1
0x180045c35  call    cs:__imp_GetSecurityDescriptorLength
0x180045c3b  mov     [rbx+8], eax
0x180045c3e  mov     [rbx], rsi
0x180045c41  mov     [r14], rbx
0x180045c44  jmp     loc_180045CCD
0x180045c49  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045c50  mov     r8, rsi; lpMem
0x180045c53  xor     edx, edx; dwFlags
0x180045c55  mov     [r14], r15
0x180045c58  call    cs:__imp_HeapFree
0x180045c5e  mov     edi, 0Eh
0x180045c63  jmp     short loc_180045CCD
0x180045c65  mov     eax, cs:dword_18014E4B8
0x180045c6b  mov     ebx, 0Bh
0x180045c70  mov     edi, ebx
0x180045c72  test    eax, eax
0x180045c74  jnz     short loc_180045C8A
0x180045c76  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045c7d  jz      short loc_180045CBB
0x180045c7f  xor     ecx, ecx
0x180045c81  call    IsWppLevelEnabled
0x180045c86  test    al, al
0x180045c88  jz      short loc_180045CBB
0x180045c8a  mov     r8d, 223h
0x180045c90  mov     [rsp+68h+var_38], ebx
0x180045c94  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x180045c9b  mov     [rsp+68h+lpcbData], rbp
0x180045ca0  xor     r9d, r9d
0x180045ca3  mov     [rsp+68h+lpData], rax
0x180045ca8  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x180045caf  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x180045cb6  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180045cbb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180045cc2  mov     r8, rsi; lpMem
0x180045cc5  xor     edx, edx; dwFlags
0x180045cc7  call    cs:__imp_HeapFree
0x180045ccd  mov     eax, edi
0x180045ccf  jmp     short loc_180045D27
0x180045cd1  mov     eax, cs:dword_18014E4B8
0x180045cd7  mov     ebx, 0Bh
0x180045cdc  test    eax, eax
0x180045cde  jnz     short loc_180045CF4
0x180045ce0  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180045ce7  jz      short loc_180045D25
0x180045ce9  xor     ecx, ecx
0x180045ceb  call    IsWppLevelEnabled
0x180045cf0  test    al, al
0x180045cf2  jz      short loc_180045D25
0x180045cf4  mov     [rsp+68h+var_38], ebx
0x180045cf8  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x180045cff  mov     [rsp+68h+lpcbData], rbp
0x180045d04  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x180045d0b  xor     r9d, r9d
0x180045d0e  mov     [rsp+68h+lpData], rax
0x180045d13  mov     r8d, 204h
0x180045d19  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x180045d20  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180045d25  mov     eax, ebx
0x180045d27  mov     rbx, [rsp+68h+arg_0]
0x180045d2c  add     rsp, 40h
0x180045d30  pop     r15
0x180045d32  pop     r14
0x180045d34  pop     rdi
0x180045d35  pop     rsi
0x180045d36  pop     rbp
0x180045d37  retn
```
