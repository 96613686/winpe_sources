# ReadSecurityDescriptor(HKEY__ *,ushort *,bool,bool,CSecDescriptor * *)

- ea: `0x18003b2b0`
- end: `0x18003b635`
- name: `?ReadSecurityDescriptor@@YAKPEAUHKEY__@@PEAG_N2PEAPEAVCSecDescriptor@@@Z`
- size: `901`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, bool@<r8b>, bool@<r9b>, struct CSecDescriptor **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003afb8`

## callees

- `0x180034260`
- `0x18003b2b0`
- `0x180064614`
- `0x180074d98`
- `0x1800855d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b548`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b548`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b5bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b38d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b38d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003b501`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b2f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b3cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b2f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b3cc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003b51f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003b51f`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b46a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b46a`

## string_xrefs

- `0x18003b34f`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003b5a5`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003b615`: `onecore\com\combase\rpcss\olescm\registry.cxx`
- `0x18003b348`: `ReadSecurityDescriptor`
- `0x18003b59e`: `ReadSecurityDescriptor`
- `0x18003b600`: `ReadSecurityDescriptor`

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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
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
            if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
            if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
              goto LABEL_40;
            v12 = 553;
          }
        }
        else
        {
          v11 = 11;
          if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
            goto LABEL_40;
          v12 = 547;
        }
      }
      else
      {
        v11 = 11;
        if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
0x18003b2b0  mov     r11, rsp
0x18003b2b3  mov     [r11+8], rbx
0x18003b2b7  mov     [r11+20h], r9b
0x18003b2bb  mov     [r11+18h], r8b
0x18003b2bf  push    rbp
0x18003b2c0  push    rsi
0x18003b2c1  push    rdi
0x18003b2c2  push    r14
0x18003b2c4  push    r15
0x18003b2c6  sub     rsp, 40h
0x18003b2ca  mov     r14, [rsp+68h+arg_20]
0x18003b2d2  lea     rax, [r11+20h]
0x18003b2d6  xor     r15d, r15d
0x18003b2d9  mov     [r11-40h], rax
0x18003b2dd  lea     r9, [r11+18h]; lpType
0x18003b2e1  mov     [r11+18h], r15d
0x18003b2e5  xor     r8d, r8d; lpReserved
0x18003b2e8  mov     [r11+20h], r15d
0x18003b2ec  mov     [r14], r15
0x18003b2ef  mov     rbp, rdx
0x18003b2f2  mov     rdi, rcx
0x18003b2f5  mov     [r11-48h], r15
0x18003b2f9  call    cs:__imp_RegQueryValueExW
0x18003b300  nop     dword ptr [rax+rax+00h]
0x18003b305  mov     ebx, eax
0x18003b307  test    eax, eax
0x18003b309  jz      short loc_18003B360
0x18003b30b  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b312  jz      loc_18003B621
0x18003b318  lea     ecx, [r15+3]
0x18003b31c  call    IsWppLevelEnabled
0x18003b321  test    al, al
0x18003b323  jz      loc_18003B621
0x18003b329  mov     [rsp+68h+var_38], ebx
0x18003b32d  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x18003b334  mov     [rsp+68h+lpcbData], rbp
0x18003b339  lea     r9d, [r15+3]
0x18003b33d  mov     r8d, 1FEh
0x18003b343  mov     [rsp+68h+lpData], rax
0x18003b348  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x18003b34f  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003b356  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18003b35b  jmp     loc_18003B621
0x18003b360  cmp     [rsp+68h+Type], 3
0x18003b368  jnz     loc_18003B5CD
0x18003b36e  cmp     dword ptr [rsp+68h+dwBytes], 28h ; '('
0x18003b376  jb      loc_18003B5CD
0x18003b37c  mov     r8d, dword ptr [rsp+68h+dwBytes]; dwBytes
0x18003b384  xor     edx, edx; dwFlags
0x18003b386  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003b38d  call    cs:__imp_HeapAlloc
0x18003b394  nop     dword ptr [rax+rax+00h]
0x18003b399  mov     rsi, rax
0x18003b39c  test    rax, rax
0x18003b39f  jnz     short loc_18003B3A9
0x18003b3a1  lea     eax, [rsi+0Eh]
0x18003b3a4  jmp     loc_18003B623
0x18003b3a9  lea     rax, [rsp+68h+dwBytes]
0x18003b3b1  xor     r8d, r8d; lpReserved
0x18003b3b4  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18003b3b9  lea     r9, [rsp+68h+Type]; lpType
0x18003b3c1  mov     rdx, rbp; lpValueName
0x18003b3c4  mov     [rsp+68h+lpData], rsi; lpData
0x18003b3c9  mov     rcx, rdi; hKey
0x18003b3cc  call    cs:__imp_RegQueryValueExW
0x18003b3d3  nop     dword ptr [rax+rax+00h]
0x18003b3d8  mov     edi, eax
0x18003b3da  test    eax, eax
0x18003b3dc  jz      short loc_18003B411
0x18003b3de  mov     ecx, cs:dword_1801574B8
0x18003b3e4  test    ecx, ecx
0x18003b3e6  jnz     short loc_18003B402
0x18003b3e8  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b3ef  jz      loc_18003B5B1
0x18003b3f5  call    IsWppLevelEnabled
0x18003b3fa  test    al, al
0x18003b3fc  jz      loc_18003B5B1
0x18003b402  mov     [rsp+68h+var_38], edi
0x18003b406  mov     r8d, 216h
0x18003b40c  jmp     loc_18003B58A
0x18003b411  cmp     [rsp+68h+Type], 3
0x18003b419  jz      short loc_18003B453
0x18003b41b  mov     eax, cs:dword_1801574B8
0x18003b421  mov     ebx, 0Bh
0x18003b426  mov     edi, ebx
0x18003b428  test    eax, eax
0x18003b42a  jnz     short loc_18003B448
0x18003b42c  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b433  jz      loc_18003B5B1
0x18003b439  xor     ecx, ecx
0x18003b43b  call    IsWppLevelEnabled
0x18003b440  test    al, al
0x18003b442  jz      loc_18003B5B1
0x18003b448  mov     r8d, 21Dh
0x18003b44e  jmp     loc_18003B586
0x18003b453  cmp     [rsi+8], r15d
0x18003b457  jz      loc_18003B55B
0x18003b45d  cmp     [rsi+4], r15d
0x18003b461  jz      loc_18003B55B
0x18003b467  mov     rcx, rsi; pSecurityDescriptor
0x18003b46a  call    cs:__imp_IsValidSecurityDescriptor
0x18003b471  nop     dword ptr [rax+rax+00h]
0x18003b476  test    eax, eax
0x18003b478  jnz     short loc_18003B4B0
0x18003b47a  lea     ebx, [rax+0Bh]
0x18003b47d  mov     eax, cs:dword_1801574B8
0x18003b483  mov     edi, ebx
0x18003b485  test    eax, eax
0x18003b487  jnz     short loc_18003B4A5
0x18003b489  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b490  jz      loc_18003B5B1
0x18003b496  xor     ecx, ecx
0x18003b498  call    IsWppLevelEnabled
0x18003b49d  test    al, al
0x18003b49f  jz      loc_18003B5B1
0x18003b4a5  mov     r8d, 229h
0x18003b4ab  jmp     loc_18003B586
0x18003b4b0  xor     edx, edx; int *
0x18003b4b2  mov     rcx, rsi; pSecurityDescriptor
0x18003b4b5  call    ?IsValidCOMSecurityDescriptor@@YAHPEBU_SECURITY_DESCRIPTOR_RELATIVE@@PEAH@Z; IsValidCOMSecurityDescriptor(_SECURITY_DESCRIPTOR_RELATIVE const *,int *)
0x18003b4ba  test    eax, eax
0x18003b4bc  jnz     short loc_18003B4F4
0x18003b4be  lea     ebx, [rax+0Bh]
0x18003b4c1  mov     eax, cs:dword_1801574B8
0x18003b4c7  mov     edi, ebx
0x18003b4c9  test    eax, eax
0x18003b4cb  jnz     short loc_18003B4E9
0x18003b4cd  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b4d4  jz      loc_18003B5B1
0x18003b4da  xor     ecx, ecx
0x18003b4dc  call    IsWppLevelEnabled
0x18003b4e1  test    al, al
0x18003b4e3  jz      loc_18003B5B1
0x18003b4e9  mov     r8d, 230h
0x18003b4ef  jmp     loc_18003B586
0x18003b4f4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003b4fb  xor     edx, edx; dwFlags
0x18003b4fd  lea     r8d, [rdx+10h]; dwBytes
0x18003b501  call    cs:__imp_HeapAlloc
0x18003b508  nop     dword ptr [rax+rax+00h]
0x18003b50d  mov     rbx, rax
0x18003b510  test    rax, rax
0x18003b513  jz      short loc_18003B539
0x18003b515  mov     rcx, rsi; pSecurityDescriptor
0x18003b518  mov     dword ptr [rax+0Ch], 1
0x18003b51f  call    cs:__imp_GetSecurityDescriptorLength
0x18003b526  nop     dword ptr [rax+rax+00h]
0x18003b52b  mov     [rbx+8], eax
0x18003b52e  mov     [rbx], rsi
0x18003b531  mov     [r14], rbx
0x18003b534  jmp     loc_18003B5C9
0x18003b539  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003b540  mov     r8, rsi; lpMem
0x18003b543  xor     edx, edx; dwFlags
0x18003b545  mov     [r14], r15
0x18003b548  call    cs:__imp_HeapFree
0x18003b54f  nop     dword ptr [rax+rax+00h]
0x18003b554  mov     edi, 0Eh
0x18003b559  jmp     short loc_18003B5C9
0x18003b55b  mov     eax, cs:dword_1801574B8
0x18003b561  mov     ebx, 0Bh
0x18003b566  mov     edi, ebx
0x18003b568  test    eax, eax
0x18003b56a  jnz     short loc_18003B580
0x18003b56c  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b573  jz      short loc_18003B5B1
0x18003b575  xor     ecx, ecx
0x18003b577  call    IsWppLevelEnabled
0x18003b57c  test    al, al
0x18003b57e  jz      short loc_18003B5B1
0x18003b580  mov     r8d, 223h
0x18003b586  mov     [rsp+68h+var_38], ebx
0x18003b58a  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x18003b591  mov     [rsp+68h+lpcbData], rbp
0x18003b596  xor     r9d, r9d
0x18003b599  mov     [rsp+68h+lpData], rax
0x18003b59e  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x18003b5a5  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003b5ac  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18003b5b1  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003b5b8  mov     r8, rsi; lpMem
0x18003b5bb  xor     edx, edx; dwFlags
0x18003b5bd  call    cs:__imp_HeapFree
0x18003b5c4  nop     dword ptr [rax+rax+00h]
0x18003b5c9  mov     eax, edi
0x18003b5cb  jmp     short loc_18003B623
0x18003b5cd  mov     eax, cs:dword_1801574B8
0x18003b5d3  mov     ebx, 0Bh
0x18003b5d8  test    eax, eax
0x18003b5da  jnz     short loc_18003B5F0
0x18003b5dc  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18003b5e3  jz      short loc_18003B621
0x18003b5e5  xor     ecx, ecx
0x18003b5e7  call    IsWppLevelEnabled
0x18003b5ec  test    al, al
0x18003b5ee  jz      short loc_18003B621
0x18003b5f0  mov     [rsp+68h+var_38], ebx
0x18003b5f4  lea     rax, aWsWinerror; "%ws %!WINERROR!"
0x18003b5fb  mov     [rsp+68h+lpcbData], rbp
0x18003b600  lea     rdx, aReadsecurityde; "ReadSecurityDescriptor"
0x18003b607  xor     r9d, r9d
0x18003b60a  mov     [rsp+68h+lpData], rax
0x18003b60f  mov     r8d, 204h
0x18003b615  lea     rcx, aOnecoreComComb_114; "onecore\\com\\combase\\rpcss\\olescm\\r"...
0x18003b61c  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18003b621  mov     eax, ebx
0x18003b623  mov     rbx, [rsp+68h+arg_0]
0x18003b628  add     rsp, 40h
0x18003b62c  pop     r15
0x18003b62e  pop     r14
0x18003b630  pop     rdi
0x18003b631  pop     rsi
0x18003b632  pop     rbp
0x18003b633  retn
```
