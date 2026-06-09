# StoreCertHash

- ea: `0x180009b34`
- end: `0x180009e4f`
- name: `StoreCertHash`
- size: `795`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180006b6c`
- `0x180007450`
- `0x180008e70`

## callees

- `0x180009b34`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009dfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009dfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009ca0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009d0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009d7c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009ca0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009d0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009d7c`

## string_xrefs

- `0x180009d68`: `isHashConfiguredByAdmin`
- `0x180009bcf`: `System\CurrentControlSet\Services\SstpSvc\Parameters`
- `0x180009c3f`: `Unable to open the SSTPSVC Params Key: %d`
- `0x180009ce1`: `Trying to store sha256 cert hash in registry fails with %d`
- `0x180009d4f`: `Trying to store sha1 cert hash in registry fails with %d`
- `0x180009dbb`: `Trying to store HASH configuration type %d`

## pseudocode

```c
__int64 __fastcall StoreCertHash(__int64 a1, __int64 a2, __int64 a3, const BYTE *a4, BYTE *lpData, unsigned __int8 a6)
{
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // r8
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[2044]; // [rsp+44h] [rbp-BCh] BYREF

  *(_DWORD *)Data = a6;
  hKey = 0;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0xC0) == 0xC0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54);
  if ( !a1 )
    a1 = -2147483646;
  v8 = RegOpenKeyExW((HKEY)a1, L"System\\CurrentControlSet\\Services\\SstpSvc\\Parameters", 0, 0x2001Fu, &hKey);
  v10 = v8;
  if ( !v8 )
  {
    v12 = RegSetValueExW(hKey, L"SHA256CertificateHash", 0, 3u, lpData, 0x20u);
    v10 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v13, v12);
      }
      if ( !(_QWORD)xmmword_1800146E0 )
        goto LABEL_35;
      v14 = L"Trying to store sha256 cert hash in registry fails with %d";
    }
    else
    {
      v15 = RegSetValueExW(hKey, L"SHA1CertificateHash", 0, 3u, a4, 0x14u);
      v10 = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v16, v15);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_35;
        v14 = L"Trying to store sha1 cert hash in registry fails with %d";
      }
      else
      {
        v17 = RegSetValueExW(hKey, L"isHashConfiguredByAdmin", 0, 4u, Data, 4u);
        v10 = v17;
        if ( !v17 )
          goto LABEL_35;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v18, v17);
        }
        if ( !(_QWORD)xmmword_1800146E0 )
          goto LABEL_35;
        v14 = L"Trying to store HASH configuration type %d";
      }
    }
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v22, v14, v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v22);
LABEL_35:
    RegCloseKey(hKey);
    goto LABEL_36;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v9, v8);
    v11 = WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800146E0 )
  {
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v22, L"Unable to open the SSTPSVC Params Key: %d", v10);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v22);
LABEL_36:
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0xC0) == 0xC0 )
    WPP_SF_(v11[2], 59);
  return v10;
}

```

## disassembly

```asm
0x180009b34  mov     [rsp-8+arg_8], rbx
0x180009b39  mov     [rsp-8+arg_10], rsi
0x180009b3e  push    rbp
0x180009b3f  push    rdi
0x180009b40  push    r15
0x180009b42  lea     rbp, [rsp-750h]
0x180009b4a  sub     rsp, 850h
0x180009b51  mov     rax, cs:__security_cookie
0x180009b58  xor     rax, rsp
0x180009b5b  mov     [rbp+760h+var_20], rax
0x180009b62  movzx   eax, [rbp+760h+arg_28]
0x180009b69  mov     rbx, rcx
0x180009b6c  mov     rdi, [rbp+760h+lpData]
0x180009b73  lea     rcx, [rsp+860h+var_81C]; void *
0x180009b78  mov     dword ptr [rsp+860h+Data], eax
0x180009b7c  xor     edx, edx; Val
0x180009b7e  xor     eax, eax
0x180009b80  mov     [rsp+860h+hKey], 0
0x180009b89  mov     r8d, 7FCh; Size
0x180009b8f  mov     [rsp+860h+var_820], eax
0x180009b93  mov     rsi, r9
0x180009b96  call    memset_0
0x180009b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ba2  lea     r15, WPP_GLOBAL_Control
0x180009ba9  cmp     rcx, r15
0x180009bac  jz      short loc_180009BC8
0x180009bae  mov     eax, [rcx+1Ch]
0x180009bb1  and     eax, 0C0h
0x180009bb6  cmp     al, 0C0h
0x180009bb8  jnz     short loc_180009BC8
0x180009bba  mov     rcx, [rcx+10h]
0x180009bbe  mov     edx, 36h ; '6'
0x180009bc3  call    WPP_SF_
0x180009bc8  mov     rax, 0FFFFFFFF80000002h
0x180009bcf  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ss"...
0x180009bd6  test    rbx, rbx
0x180009bd9  mov     r9d, 2001Fh; samDesired
0x180009bdf  cmovz   rbx, rax
0x180009be3  lea     rax, [rsp+860h+hKey]
0x180009be8  mov     rcx, rbx; hKey
0x180009beb  mov     [rsp+860h+phkResult], rax; phkResult
0x180009bf0  xor     r8d, r8d; ulOptions
0x180009bf3  call    cs:__imp_RegOpenKeyExW
0x180009bf9  mov     ebx, eax
0x180009bfb  test    eax, eax
0x180009bfd  jz      short loc_180009C7C
0x180009bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c06  cmp     rcx, r15
0x180009c09  jz      short loc_180009C2F
0x180009c0b  test    byte ptr [rcx+1Ch], 40h
0x180009c0f  jz      short loc_180009C2F
0x180009c11  cmp     byte ptr [rcx+19h], 1
0x180009c15  jb      short loc_180009C2F
0x180009c17  mov     rcx, [rcx+10h]
0x180009c1b  mov     edx, 37h ; '7'
0x180009c20  mov     r9d, eax
0x180009c23  call    WPP_SF_d
0x180009c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c2f  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180009c37  jz      loc_180009E07
0x180009c3d  xor     eax, eax
0x180009c3f  lea     rdx, aUnableToOpenTh; "Unable to open the SSTPSVC Params Key: "...
0x180009c46  mov     r8d, ebx
0x180009c49  mov     word ptr [rsp+860h+var_820], ax
0x180009c4e  lea     rcx, [rsp+860h+var_820]
0x180009c53  call    FormatRRASErrorString
0x180009c58  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009c5f  lea     r8, [rsp+860h+var_820]
0x180009c64  mov     rcx, cs:gSstpCfgEtwContext
0x180009c6b  mov     rax, cs:gSstpCfgTemplateFunc
0x180009c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c77  jmp     loc_180009E00
0x180009c7c  mov     rcx, [rsp+860h+hKey]; hKey
0x180009c81  lea     rdx, aSha256certific; "SHA256CertificateHash"
0x180009c88  mov     [rsp+860h+cbData], 20h ; ' '; cbData
0x180009c90  xor     r8d, r8d; Reserved
0x180009c93  mov     [rsp+860h+phkResult], rdi; lpData
0x180009c98  mov     edi, 3
0x180009c9d  mov     r9d, edi; dwType
0x180009ca0  call    cs:__imp_RegSetValueExW
0x180009ca6  mov     ebx, eax
0x180009ca8  test    eax, eax
0x180009caa  jz      short loc_180009CED
0x180009cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cb3  cmp     rcx, r15
0x180009cb6  jz      short loc_180009CD3
0x180009cb8  test    byte ptr [rcx+1Ch], 40h
0x180009cbc  jz      short loc_180009CD3
0x180009cbe  cmp     byte ptr [rcx+19h], 2
0x180009cc2  jb      short loc_180009CD3
0x180009cc4  mov     rcx, [rcx+10h]
0x180009cc8  lea     edx, [rdi+35h]
0x180009ccb  mov     r9d, eax
0x180009cce  call    WPP_SF_d
0x180009cd3  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180009cdb  jz      loc_180009DF5
0x180009ce1  lea     rdx, aTryingToStoreS; "Trying to store sha256 cert hash in reg"...
0x180009ce8  jmp     loc_180009DC2
0x180009ced  mov     rcx, [rsp+860h+hKey]; hKey
0x180009cf2  lea     rdx, aSha1certificat; "SHA1CertificateHash"
0x180009cf9  mov     [rsp+860h+cbData], 14h; cbData
0x180009d01  mov     r9d, edi; dwType
0x180009d04  xor     r8d, r8d; Reserved
0x180009d07  mov     [rsp+860h+phkResult], rsi; lpData
0x180009d0c  call    cs:__imp_RegSetValueExW
0x180009d12  mov     ebx, eax
0x180009d14  test    eax, eax
0x180009d16  jz      short loc_180009D58
0x180009d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d1f  cmp     rcx, r15
0x180009d22  jz      short loc_180009D41
0x180009d24  test    byte ptr [rcx+1Ch], 40h
0x180009d28  jz      short loc_180009D41
0x180009d2a  cmp     byte ptr [rcx+19h], 2
0x180009d2e  jb      short loc_180009D41
0x180009d30  mov     rcx, [rcx+10h]
0x180009d34  mov     edx, 39h ; '9'
0x180009d39  mov     r9d, eax
0x180009d3c  call    WPP_SF_d
0x180009d41  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180009d49  jz      loc_180009DF5
0x180009d4f  lea     rdx, aTryingToStoreS_0; "Trying to store sha1 cert hash in regis"...
0x180009d56  jmp     short loc_180009DC2
0x180009d58  mov     rcx, [rsp+860h+hKey]; hKey
0x180009d5d  lea     rax, [rsp+860h+Data]
0x180009d62  mov     r9d, 4; dwType
0x180009d68  lea     rdx, aIshashconfigur; "isHashConfiguredByAdmin"
0x180009d6f  mov     [rsp+860h+cbData], r9d; cbData
0x180009d74  xor     r8d, r8d; Reserved
0x180009d77  mov     [rsp+860h+phkResult], rax; lpData
0x180009d7c  call    cs:__imp_RegSetValueExW
0x180009d82  mov     ebx, eax
0x180009d84  test    eax, eax
0x180009d86  jz      short loc_180009DF5
0x180009d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d8f  cmp     rcx, r15
0x180009d92  jz      short loc_180009DB1
0x180009d94  test    byte ptr [rcx+1Ch], 40h
0x180009d98  jz      short loc_180009DB1
0x180009d9a  cmp     byte ptr [rcx+19h], 2
0x180009d9e  jb      short loc_180009DB1
0x180009da0  mov     rcx, [rcx+10h]
0x180009da4  mov     edx, 3Ah ; ':'
0x180009da9  mov     r9d, eax
0x180009dac  call    WPP_SF_d
0x180009db1  cmp     qword ptr cs:xmmword_1800146E0, 0
0x180009db9  jz      short loc_180009DF5
0x180009dbb  lea     rdx, aTryingToStoreH_1; "Trying to store HASH configuration type"...
0x180009dc2  xor     eax, eax
0x180009dc4  lea     rcx, [rsp+860h+var_820]
0x180009dc9  mov     r8d, ebx
0x180009dcc  mov     word ptr [rsp+860h+var_820], ax
0x180009dd1  call    FormatRRASErrorString
0x180009dd6  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180009ddd  lea     r8, [rsp+860h+var_820]
0x180009de2  mov     rcx, cs:gSstpCfgEtwContext
0x180009de9  mov     rax, cs:gSstpCfgTemplateFunc
0x180009df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df5  mov     rcx, [rsp+860h+hKey]; hKey
0x180009dfa  call    cs:__imp_RegCloseKey
0x180009e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e07  cmp     rcx, r15
0x180009e0a  jz      short loc_180009E26
0x180009e0c  mov     eax, [rcx+1Ch]
0x180009e0f  and     eax, 0C0h
0x180009e14  cmp     al, 0C0h
0x180009e16  jnz     short loc_180009E26
0x180009e18  mov     rcx, [rcx+10h]
0x180009e1c  mov     edx, 3Bh ; ';'
0x180009e21  call    WPP_SF_
0x180009e26  mov     eax, ebx
0x180009e28  mov     rcx, [rbp+760h+var_20]
0x180009e2f  xor     rcx, rsp; StackCookie
0x180009e32  call    __security_check_cookie
0x180009e37  lea     r11, [rsp+860h+var_10]
0x180009e3f  mov     rbx, [r11+28h]
0x180009e43  mov     rsi, [r11+30h]
0x180009e47  mov     rsp, r11
0x180009e4a  pop     r15
0x180009e4c  pop     rdi
0x180009e4d  pop     rbp
0x180009e4e  retn
```
