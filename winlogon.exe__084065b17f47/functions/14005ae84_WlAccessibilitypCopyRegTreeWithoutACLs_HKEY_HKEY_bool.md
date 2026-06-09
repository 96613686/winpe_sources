# WlAccessibilitypCopyRegTreeWithoutACLs(HKEY__ *,HKEY__ *,bool)

- ea: `0x14005ae84`
- end: `0x14005b1db`
- name: `?WlAccessibilitypCopyRegTreeWithoutACLs@@YAKPEAUHKEY__@@0_N@Z`
- size: `855`
- prototype: `unsigned int __fastcall(HKEY hKey, HKEY, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14005ad40`

## callees

- `0x1400057f4`
- `0x1400198e0`
- `0x14001a200`
- `0x14005ae84`
- `0x14005b1e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14005af56`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14005af56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005b07b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005b07b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005b04e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005b04e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b19c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b1ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ecbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009eccb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b19c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b1ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009ecbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009eccb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005afff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005afff`

## pseudocode

```c
__int64 __fastcall WlAccessibilitypCopyRegTreeWithoutACLs(HKEY hKey, HKEY a2)
{
  DWORD v4; // edi
  void *v5; // rsi
  unsigned int v6; // ebx
  CUser *v7; // rcx
  __int64 v8; // rdx
  LSTATUS v9; // eax
  HKEY hKeya; // [rsp+68h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-38h] BYREF
  void *v13; // [rsp+78h] [rbp-30h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C0h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+C8h] [rbp+20h] BYREF

  cbMaxSubKeyLen = 0;
  cchName = 0;
  v4 = 0;
  v5 = 0;
  v13 = 0;
  phkResult = 0;
  hKeya = 0;
  v6 = WlAccessibilitypDuplicateKeyValues(hKey, a2);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 25;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids, v6);
    }
  }
  else
  {
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 26;
        goto LABEL_6;
      }
    }
    else
    {
      v5 = WLAlloc(2LL * ++cbMaxSubKeyLen);
      v13 = v5;
      if ( v5 )
      {
        while ( 1 )
        {
          cchName = cbMaxSubKeyLen;
          v9 = RegEnumKeyExW(hKey, v4, (LPWSTR)v5, &cchName, 0, 0, 0, 0);
          v6 = v9;
          if ( v9 == 259 )
          {
            v6 = 0;
            goto LABEL_37;
          }
          if ( v9 )
            break;
          v6 = RegCreateKeyExW(a2, (LPCWSTR)v5, 0, 0, 1u, 0xF003Fu, 0, &phkResult, 0);
          if ( v6 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 28;
              goto LABEL_6;
            }
            goto LABEL_37;
          }
          v6 = RegOpenKeyExW(hKey, (LPCWSTR)v5, 0, 0x20019u, &hKeya);
          if ( v6 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 29;
              goto LABEL_6;
            }
            goto LABEL_37;
          }
          v6 = WlAccessibilitypDuplicateKeyValues(hKeya, phkResult);
          if ( v6 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 30;
              goto LABEL_6;
            }
            goto LABEL_37;
          }
          RegCloseKey(hKeya);
          hKeya = 0;
          RegCloseKey(phkResult);
          phkResult = 0;
          ++v4;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 27;
          goto LABEL_6;
        }
      }
      else
      {
        v6 = 14;
      }
    }
  }
LABEL_37:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v5 )
    UHHeapFree(&v13);
  return v6;
}

```

## disassembly

```asm
0x14005ae84  mov     rax, rsp
0x14005ae87  mov     [rax+8], rbx
0x14005ae8b  mov     [rax+18h], r8b
0x14005ae8f  push    rsi
0x14005ae90  push    rdi
0x14005ae91  push    r12
0x14005ae93  push    r14
0x14005ae95  push    r15
0x14005ae97  sub     rsp, 80h
0x14005ae9e  mov     r15, rdx
0x14005aea1  mov     r14, rcx
0x14005aea4  xor     r12d, r12d
0x14005aea7  mov     [rax+18h], r12d
0x14005aeab  mov     [rax+20h], r12d
0x14005aeaf  mov     edi, r12d
0x14005aeb2  mov     esi, r12d
0x14005aeb5  mov     [rax-30h], r12
0x14005aeb9  mov     [rax-38h], r12
0x14005aebd  mov     [rax-40h], r12
0x14005aec1  call    ?WlAccessibilitypDuplicateKeyValues@@YAKPEAUHKEY__@@0@Z; WlAccessibilitypDuplicateKeyValues(HKEY__ *,HKEY__ *)
0x14005aec6  mov     ebx, eax
0x14005aec8  mov     [rsp+0A8h+var_48], eax
0x14005aecc  test    eax, eax
0x14005aece  jz      short loc_14005AF1B
0x14005aed0  lea     rax, WPP_GLOBAL_Control
0x14005aed7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aede  cmp     rcx, rax
0x14005aee1  jz      loc_14005B192
0x14005aee7  test    dword ptr [rcx+1Ch], 40000h
0x14005aeee  jz      loc_14005B192
0x14005aef4  cmp     byte ptr [rcx+19h], 2
0x14005aef8  jb      loc_14005B192
0x14005aefe  lea     edx, [r12+19h]
0x14005af03  mov     r9d, ebx
0x14005af06  lea     r8, WPP_08fbe39dfd5c3ed1d0f5d3aa8d6e811c_Traceguids
0x14005af0d  mov     rcx, [rcx+10h]
0x14005af11  call    WPP_SF_d
0x14005af16  jmp     loc_14005B192
0x14005af1b  mov     [rsp+0A8h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14005af20  mov     [rsp+0A8h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14005af25  mov     [rsp+0A8h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x14005af2a  mov     [rsp+0A8h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14005af2f  mov     [rsp+0A8h+lpcValues], r12; lpcValues
0x14005af34  mov     [rsp+0A8h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14005af39  lea     rax, [rsp+0A8h+cbMaxSubKeyLen]
0x14005af41  mov     [rsp+0A8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14005af46  mov     [rsp+0A8h+lpcSubKeys], r12; lpcSubKeys
0x14005af4b  xor     r9d, r9d; lpReserved
0x14005af4e  xor     r8d, r8d; lpcchClass
0x14005af51  xor     edx, edx; lpClass
0x14005af53  mov     rcx, r14; hKey
0x14005af56  call    cs:__imp_RegQueryInfoKeyW
0x14005af5c  mov     ebx, eax
0x14005af5e  mov     [rsp+0A8h+var_48], eax
0x14005af62  test    eax, eax
0x14005af64  jz      short loc_14005AF9E
0x14005af66  lea     rax, WPP_GLOBAL_Control
0x14005af6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005af74  cmp     rcx, rax
0x14005af77  jz      loc_14005B192
0x14005af7d  test    dword ptr [rcx+1Ch], 40000h
0x14005af84  jz      loc_14005B192
0x14005af8a  cmp     byte ptr [rcx+19h], 2
0x14005af8e  jb      loc_14005B192
0x14005af94  mov     edx, 1Ah
0x14005af99  jmp     loc_14005AF03
0x14005af9e  mov     eax, [rsp+0A8h+cbMaxSubKeyLen]
0x14005afa5  inc     eax
0x14005afa7  mov     [rsp+0A8h+cbMaxSubKeyLen], eax
0x14005afae  mov     ecx, eax
0x14005afb0  add     rcx, rcx; unsigned __int64
0x14005afb3  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14005afb8  mov     rsi, rax
0x14005afbb  mov     [rsp+0A8h+var_30], rax
0x14005afc0  test    rax, rax
0x14005afc3  jnz     short loc_14005AFCD
0x14005afc5  lea     ebx, [rax+0Eh]
0x14005afc8  jmp     loc_14005B18E
0x14005afcd  mov     eax, [rsp+0A8h+cbMaxSubKeyLen]
0x14005afd4  mov     [rsp+0A8h+cchName], eax
0x14005afdb  mov     [rsp+0A8h+lpcValues], r12; lpftLastWriteTime
0x14005afe0  mov     [rsp+0A8h+lpcbMaxClassLen], r12; lpcchClass
0x14005afe5  mov     [rsp+0A8h+lpcbMaxSubKeyLen], r12; lpClass
0x14005afea  mov     [rsp+0A8h+lpcSubKeys], r12; lpReserved
0x14005afef  lea     r9, [rsp+0A8h+cchName]; lpcchName
0x14005aff7  mov     r8, rsi; lpName
0x14005affa  mov     edx, edi; dwIndex
0x14005affc  mov     rcx, r14; hKey
0x14005afff  call    cs:__imp_RegEnumKeyExW
0x14005b005  mov     ebx, eax
0x14005b007  mov     [rsp+0A8h+var_48], eax
0x14005b00b  cmp     eax, 103h
0x14005b010  jz      loc_14005B18B
0x14005b016  test    eax, eax
0x14005b018  jnz     loc_14005B15F
0x14005b01e  mov     [rsp+0A8h+lpcbMaxValueNameLen], r12; lpdwDisposition
0x14005b023  lea     rax, [rsp+0A8h+phkResult]
0x14005b028  mov     [rsp+0A8h+lpcValues], rax; phkResult
0x14005b02d  mov     [rsp+0A8h+lpcbMaxClassLen], r12; lpSecurityAttributes
0x14005b032  mov     dword ptr [rsp+0A8h+lpcbMaxSubKeyLen], 0F003Fh; samDesired
0x14005b03a  mov     dword ptr [rsp+0A8h+lpcSubKeys], 1; dwOptions
0x14005b042  xor     r9d, r9d; lpClass
0x14005b045  xor     r8d, r8d; Reserved
0x14005b048  mov     rdx, rsi; lpSubKey
0x14005b04b  mov     rcx, r15; hKey
0x14005b04e  call    cs:__imp_RegCreateKeyExW
0x14005b054  mov     ebx, eax
0x14005b056  mov     [rsp+0A8h+var_48], eax
0x14005b05a  test    eax, eax
0x14005b05c  jnz     loc_14005B133
0x14005b062  lea     rax, [rsp+0A8h+hKey]
0x14005b067  mov     [rsp+0A8h+lpcSubKeys], rax; phkResult
0x14005b06c  mov     r9d, 20019h; samDesired
0x14005b072  xor     r8d, r8d; ulOptions
0x14005b075  mov     rdx, rsi; lpSubKey
0x14005b078  mov     rcx, r14; hKey
0x14005b07b  call    cs:__imp_RegOpenKeyExW
0x14005b081  mov     ebx, eax
0x14005b083  mov     [rsp+0A8h+var_48], eax
0x14005b087  test    eax, eax
0x14005b089  jnz     short loc_14005B107
0x14005b08b  mov     rdx, [rsp+0A8h+phkResult]; HKEY
0x14005b090  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14005b095  call    ?WlAccessibilitypDuplicateKeyValues@@YAKPEAUHKEY__@@0@Z; WlAccessibilitypDuplicateKeyValues(HKEY__ *,HKEY__ *)
0x14005b09a  mov     ebx, eax
0x14005b09c  mov     [rsp+0A8h+var_48], eax
0x14005b0a0  test    eax, eax
0x14005b0a2  jnz     short loc_14005B0CF
0x14005b0a4  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14005b0a9  call    cs:__imp_RegCloseKey
0x14005b0af  mov     [rsp+0A8h+hKey], r12
0x14005b0b4  mov     rcx, [rsp+0A8h+phkResult]; hKey
0x14005b0b9  call    cs:__imp_RegCloseKey
0x14005b0bf  mov     [rsp+0A8h+phkResult], r12
0x14005b0c4  inc     edi
0x14005b0c6  mov     [rsp+0A8h+var_44], edi
0x14005b0ca  jmp     loc_14005AFCD
0x14005b0cf  lea     rax, WPP_GLOBAL_Control
0x14005b0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b0dd  cmp     rcx, rax
0x14005b0e0  jz      loc_14005B192
0x14005b0e6  test    dword ptr [rcx+1Ch], 40000h
0x14005b0ed  jz      loc_14005B192
0x14005b0f3  cmp     byte ptr [rcx+19h], 2
0x14005b0f7  jb      loc_14005B192
0x14005b0fd  mov     edx, 1Eh
0x14005b102  jmp     loc_14005AF03
0x14005b107  lea     rax, WPP_GLOBAL_Control
0x14005b10e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b115  cmp     rcx, rax
0x14005b118  jz      short loc_14005B192
0x14005b11a  test    dword ptr [rcx+1Ch], 40000h
0x14005b121  jz      short loc_14005B192
0x14005b123  cmp     byte ptr [rcx+19h], 2
0x14005b127  jb      short loc_14005B192
0x14005b129  mov     edx, 1Dh
0x14005b12e  jmp     loc_14005AF03
0x14005b133  lea     rax, WPP_GLOBAL_Control
0x14005b13a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b141  cmp     rcx, rax
0x14005b144  jz      short loc_14005B192
0x14005b146  test    dword ptr [rcx+1Ch], 40000h
0x14005b14d  jz      short loc_14005B192
0x14005b14f  cmp     byte ptr [rcx+19h], 2
0x14005b153  jb      short loc_14005B192
0x14005b155  mov     edx, 1Ch
0x14005b15a  jmp     loc_14005AF03
0x14005b15f  lea     rax, WPP_GLOBAL_Control
0x14005b166  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b16d  cmp     rcx, rax
0x14005b170  jz      short loc_14005B192
0x14005b172  test    dword ptr [rcx+1Ch], 40000h
0x14005b179  jz      short loc_14005B192
0x14005b17b  cmp     byte ptr [rcx+19h], 2
0x14005b17f  jb      short loc_14005B192
0x14005b181  mov     edx, 1Bh
0x14005b186  jmp     loc_14005AF03
0x14005b18b  mov     ebx, r12d
0x14005b18e  mov     [rsp+0A8h+var_48], ebx
0x14005b192  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14005b197  test    rcx, rcx
0x14005b19a  jz      short loc_14005B1A2
0x14005b19c  call    cs:__imp_RegCloseKey
0x14005b1a2  mov     rcx, [rsp+0A8h+phkResult]; hKey
0x14005b1a7  test    rcx, rcx
0x14005b1aa  jz      short loc_14005B1B2
0x14005b1ac  call    cs:__imp_RegCloseKey
0x14005b1b2  test    rsi, rsi
0x14005b1b5  jz      short loc_14005B1C1
0x14005b1b7  lea     rcx, [rsp+0A8h+var_30]
0x14005b1bc  call    UHHeapFree
0x14005b1c1  mov     eax, ebx
0x14005b1c3  mov     rbx, [rsp+0A8h+arg_0]
0x14005b1cb  add     rsp, 80h
0x14005b1d2  pop     r15
0x14005b1d4  pop     r14
0x14005b1d6  pop     r12
0x14005b1d8  pop     rdi
0x14005b1d9  pop     rsi
0x14005b1da  retn
0x14009eca9  push    rbp
0x14009ecab  sub     rsp, 60h
0x14009ecaf  mov     rbp, rdx
0x14009ecb2  mov     rcx, [rbp+68h]; hKey
0x14009ecb6  test    rcx, rcx
0x14009ecb9  jz      short loc_14009ECC2
0x14009ecbb  call    cs:__imp_RegCloseKey
0x14009ecc1  nop
0x14009ecc2  mov     rcx, [rbp+70h]; hKey
0x14009ecc6  test    rcx, rcx
0x14009ecc9  jz      short loc_14009ECD2
0x14009eccb  call    cs:__imp_RegCloseKey
0x14009ecd1  nop
0x14009ecd2  cmp     qword ptr [rbp+78h], 0
0x14009ecd7  jz      short loc_14009ECE3
0x14009ecd9  lea     rcx, [rbp+78h]
0x14009ecdd  call    UHHeapFree
0x14009ece2  nop
0x14009ece3  add     rsp, 60h
0x14009ece7  pop     rbp
0x14009ece8  retn
```
