# SsipGetDllName

- ea: `0x18002ac54`
- end: `0x18002af39`
- name: `SsipGetDllName`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b2b8`

## callees

- `0x1800061a0`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x18001874c`
- `0x18002ac54`
- `0x18002b7d8`
- `0x18002b840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ad16`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002ad16`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002ad2d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002ad2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ad79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aedc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aedc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002adca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002adca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae37`

## string_xrefs

- `0x18002ad09`: `System\CurrentControlSet\Control\SecurityProviders\SSI\Providers\`
- `0x18002adc0`: `DllName`
- `0x18002ae30`: `DllName`

## pseudocode

```c
__int64 __fastcall SsipGetDllName(unsigned __int16 *a1, DWORD *a2, BYTE **a3)
{
  BYTE *v3; // rdi
  __int64 v7; // rbx
  __int64 Memory; // rax
  void *v9; // r14
  PVOID *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  BYTE *v15; // rax
  int v16; // edx
  int v17; // r8d
  DWORD v18; // eax
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  v3 = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, a1);
  v7 = (*a1 >> 1) + 134;
  *a3 = 0;
  *a2 = 0;
  Memory = DigestAllocateMemory((unsigned int)(2 * v7));
  v9 = (void *)Memory;
  if ( Memory )
  {
    _o_wcscpy_s(Memory, v7, L"System\\CurrentControlSet\\Control\\SecurityProviders\\SSI\\Providers\\");
    _o_wcsncat_s(v9, v7, *((_QWORD *)a1 + 1), (unsigned __int64)*a1 >> 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, v12, v9);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v9, 0, 0x20019u, &hKey) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_35;
      v14 = 62;
    }
    else
    {
      cbData = 0;
      if ( RegQueryValueExW(hKey, L"DllName", 0, &Type, 0, &cbData) )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        v14 = 65;
      }
      else
      {
        v15 = (BYTE *)DigestAllocateMemory(cbData);
        v3 = v15;
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
          v11 = -2146893056;
          goto LABEL_36;
        }
        if ( !RegQueryValueExW(hKey, L"DllName", 0, &Type, v15, &cbData) && Type == 1 )
        {
          v11 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v17, (_DWORD)v3, cbData);
          v18 = cbData;
          *a3 = v3;
          v3 = 0;
          *a2 = v18;
          goto LABEL_36;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_35:
          v11 = -1073741811;
LABEL_36:
          DigestFreeMemory(v9);
          v10 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_37;
        }
        v14 = 64;
      }
    }
    WPP_SF_(v13[2], v14, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    goto LABEL_35;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = -2146893056;
LABEL_37:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v3 )
  {
    DigestFreeMemory(v3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && *((char *)v10 + 28) < 0 )
    WPP_SF_d(v10[2], 67, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002ac54  push    rbp
0x18002ac56  push    rbx
0x18002ac57  push    rsi
0x18002ac58  push    rdi
0x18002ac59  push    r12
0x18002ac5b  push    r14
0x18002ac5d  push    r15
0x18002ac5f  mov     rbp, rsp
0x18002ac62  sub     rsp, 30h
0x18002ac66  xor     edi, edi
0x18002ac68  mov     r15, r8
0x18002ac6b  mov     [rbp+cbData], edi
0x18002ac6e  mov     r12, rdx
0x18002ac71  mov     [rbp+Type], edi
0x18002ac74  mov     rsi, rcx
0x18002ac77  mov     [rbp+hKey], rdi
0x18002ac7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac82  lea     rax, WPP_GLOBAL_Control
0x18002ac89  cmp     rcx, rax
0x18002ac8c  jz      short loc_18002ACAA
0x18002ac8e  test    byte ptr [rcx+1Ch], 80h
0x18002ac92  jz      short loc_18002ACAA
0x18002ac94  mov     rcx, [rcx+10h]
0x18002ac98  lea     edx, [rdi+3Bh]
0x18002ac9b  mov     r9, rsi
0x18002ac9e  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002aca5  call    WPP_SF_Z
0x18002acaa  movzx   ebx, word ptr [rsi]
0x18002acad  shr     ebx, 1
0x18002acaf  add     ebx, 86h
0x18002acb5  mov     [r15], rdi
0x18002acb8  mov     [r12], edi
0x18002acbc  lea     ecx, [rbx+rbx]; Size
0x18002acbf  call    DigestAllocateMemory
0x18002acc4  mov     r14, rax
0x18002acc7  test    rax, rax
0x18002acca  jnz     short loc_18002AD09
0x18002accc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acd3  lea     rsi, WPP_GLOBAL_Control
0x18002acda  cmp     rcx, rsi
0x18002acdd  jz      short loc_18002ACFF
0x18002acdf  test    byte ptr [rcx+1Ch], 1
0x18002ace3  jz      short loc_18002ACFF
0x18002ace5  mov     rcx, [rcx+10h]
0x18002ace9  lea     edx, [rax+3Ch]
0x18002acec  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002acf3  call    WPP_SF_
0x18002acf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acff  mov     ebx, 80090300h
0x18002ad04  jmp     loc_18002AED0
0x18002ad09  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Sec"...
0x18002ad10  mov     rdx, rbx
0x18002ad13  mov     rcx, r14
0x18002ad16  call    cs:__imp__o_wcscpy_s
0x18002ad1c  movzx   r9d, word ptr [rsi]
0x18002ad20  mov     rdx, rbx
0x18002ad23  mov     r8, [rsi+8]
0x18002ad27  mov     rcx, r14
0x18002ad2a  shr     r9, 1
0x18002ad2d  call    cs:__imp__o_wcsncat_s
0x18002ad33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad3a  lea     rsi, WPP_GLOBAL_Control
0x18002ad41  cmp     rcx, rsi
0x18002ad44  jz      short loc_18002AD5D
0x18002ad46  test    byte ptr [rcx+1Ch], 4
0x18002ad4a  jz      short loc_18002AD5D
0x18002ad4c  mov     rcx, [rcx+10h]
0x18002ad50  mov     edx, 3Dh ; '='
0x18002ad55  mov     r9, r14
0x18002ad58  call    WPP_SF_S
0x18002ad5d  lea     rax, [rbp+hKey]
0x18002ad61  mov     r9d, 20019h; samDesired
0x18002ad67  xor     r8d, r8d; ulOptions
0x18002ad6a  mov     [rsp+30h+phkResult], rax; phkResult
0x18002ad6f  mov     rdx, r14; lpSubKey
0x18002ad72  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ad79  call    cs:__imp_RegOpenKeyExW
0x18002ad7f  test    eax, eax
0x18002ad81  jz      short loc_18002ADA7
0x18002ad83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad8a  cmp     rcx, rsi
0x18002ad8d  jz      loc_18002AEBC
0x18002ad93  test    byte ptr [rcx+1Ch], 1
0x18002ad97  jz      loc_18002AEBC
0x18002ad9d  mov     edx, 3Eh ; '>'
0x18002ada2  jmp     loc_18002AEAC
0x18002ada7  mov     rcx, [rbp+hKey]; hKey
0x18002adab  lea     rax, [rbp+cbData]
0x18002adaf  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002adb4  lea     r9, [rbp+Type]; lpType
0x18002adb8  xor     r8d, r8d; lpReserved
0x18002adbb  mov     [rsp+30h+phkResult], rdi; lpData
0x18002adc0  lea     rdx, aDllname; "DllName"
0x18002adc7  mov     [rbp+cbData], edi
0x18002adca  call    cs:__imp_RegQueryValueExW
0x18002add0  test    eax, eax
0x18002add2  jnz     loc_18002AE95
0x18002add8  mov     ecx, [rbp+cbData]; Size
0x18002addb  call    DigestAllocateMemory
0x18002ade0  mov     rdi, rax
0x18002ade3  test    rax, rax
0x18002ade6  jnz     short loc_18002AE17
0x18002ade8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adef  cmp     rcx, rsi
0x18002adf2  jz      short loc_18002AE0D
0x18002adf4  test    byte ptr [rcx+1Ch], 1
0x18002adf8  jz      short loc_18002AE0D
0x18002adfa  mov     rcx, [rcx+10h]
0x18002adfe  lea     edx, [rax+3Fh]
0x18002ae01  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002ae08  call    WPP_SF_
0x18002ae0d  mov     ebx, 80090300h
0x18002ae12  jmp     loc_18002AEC1
0x18002ae17  mov     rcx, [rbp+hKey]; hKey
0x18002ae1b  lea     rax, [rbp+cbData]
0x18002ae1f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002ae24  lea     r9, [rbp+Type]; lpType
0x18002ae28  xor     r8d, r8d; lpReserved
0x18002ae2b  mov     [rsp+30h+phkResult], rdi; lpData
0x18002ae30  lea     rdx, aDllname; "DllName"
0x18002ae37  call    cs:__imp_RegQueryValueExW
0x18002ae3d  test    eax, eax
0x18002ae3f  jnz     short loc_18002AE7C
0x18002ae41  cmp     [rbp+Type], 1
0x18002ae45  jnz     short loc_18002AE7C
0x18002ae47  xor     ebx, ebx
0x18002ae49  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae50  cmp     rcx, rsi
0x18002ae53  jz      short loc_18002AE6E
0x18002ae55  test    byte ptr [rcx+1Ch], 4
0x18002ae59  jz      short loc_18002AE6E
0x18002ae5b  mov     eax, [rbp+cbData]
0x18002ae5e  mov     r9, rdi
0x18002ae61  mov     rcx, [rcx+10h]
0x18002ae65  mov     dword ptr [rsp+30h+phkResult], eax
0x18002ae69  call    WPP_SF_Sd
0x18002ae6e  mov     eax, [rbp+cbData]
0x18002ae71  mov     [r15], rdi
0x18002ae74  xor     edi, edi
0x18002ae76  mov     [r12], eax
0x18002ae7a  jmp     short loc_18002AEC1
0x18002ae7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae83  cmp     rcx, rsi
0x18002ae86  jz      short loc_18002AEBC
0x18002ae88  test    byte ptr [rcx+1Ch], 1
0x18002ae8c  jz      short loc_18002AEBC
0x18002ae8e  mov     edx, 40h ; '@'
0x18002ae93  jmp     short loc_18002AEAC
0x18002ae95  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae9c  cmp     rcx, rsi
0x18002ae9f  jz      short loc_18002AEBC
0x18002aea1  test    byte ptr [rcx+1Ch], 1
0x18002aea5  jz      short loc_18002AEBC
0x18002aea7  mov     edx, 41h ; 'A'
0x18002aeac  mov     rcx, [rcx+10h]
0x18002aeb0  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002aeb7  call    WPP_SF_
0x18002aebc  mov     ebx, 0C000000Dh
0x18002aec1  mov     rcx, r14; hMem
0x18002aec4  call    DigestFreeMemory
0x18002aec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aed0  mov     rax, [rbp+hKey]
0x18002aed4  test    rax, rax
0x18002aed7  jz      short loc_18002AEF1
0x18002aed9  mov     rcx, rax; hKey
0x18002aedc  call    cs:__imp_RegCloseKey
0x18002aee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aee9  mov     [rbp+hKey], 0
0x18002aef1  test    rdi, rdi
0x18002aef4  jz      short loc_18002AF05
0x18002aef6  mov     rcx, rdi; hMem
0x18002aef9  call    DigestFreeMemory
0x18002aefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af05  cmp     rcx, rsi
0x18002af08  jz      short loc_18002AF28
0x18002af0a  test    byte ptr [rcx+1Ch], 80h
0x18002af0e  jz      short loc_18002AF28
0x18002af10  mov     rcx, [rcx+10h]
0x18002af14  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002af1b  mov     edx, 43h ; 'C'
0x18002af20  mov     r9d, ebx
0x18002af23  call    WPP_SF_d
0x18002af28  mov     eax, ebx
0x18002af2a  add     rsp, 30h
0x18002af2e  pop     r15
0x18002af30  pop     r14
0x18002af32  pop     r12
0x18002af34  pop     rdi
0x18002af35  pop     rsi
0x18002af36  pop     rbx
0x18002af37  pop     rbp
0x18002af38  retn
```
