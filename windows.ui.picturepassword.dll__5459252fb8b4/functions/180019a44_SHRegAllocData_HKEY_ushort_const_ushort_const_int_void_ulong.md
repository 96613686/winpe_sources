# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180019a44`
- end: `0x180019bb7`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `371`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019968`

## callees

- `0x180002610`
- `0x180019a44`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019afc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019b77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019ae5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019b4a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019ae5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019b4a`

## string_xrefs

- `0x180019ad9`: `bgPath`
- `0x180019b32`: `bgPath`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  int v5; // esi
  LSTATUS v6; // eax
  int v7; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  hkey = a1;
  if ( a2 && *a2 )
  {
    v5 = 1;
    v6 = RegOpenKeyExW(a1, a2, 0, 1u, &hkey);
    a1 = hkey;
    v7 = v6;
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
  if ( v7 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(a1, 0, L"bgPath", 2u, 0, Src, &pcbData);
  v7 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v7 )
      {
        if ( RegGetValueW(hkey, 0, L"bgPath", 2u, 0, pvData, &pcbData) )
        {
          v7 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v7 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v7 = 14;
    }
  }
  if ( v5 )
    RegCloseKey(hkey);
  if ( v7 )
  {
LABEL_18:
    *a5 = 0;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019a44  mov     [rsp-8+arg_10], rbx
0x180019a49  mov     [rsp-8+arg_18], rsi
0x180019a4e  push    rbp
0x180019a4f  push    rdi
0x180019a50  push    r14
0x180019a52  lea     rbp, [rsp-60h]
0x180019a57  sub     rsp, 160h
0x180019a5e  mov     rax, cs:__security_cookie
0x180019a65  xor     rax, rsp
0x180019a68  mov     [rbp+70h+var_20], rax
0x180019a6c  mov     rdi, [rbp+70h+arg_20]
0x180019a73  xor     r14d, r14d
0x180019a76  mov     [rsp+170h+hkey], rcx
0x180019a7b  test    rdx, rdx
0x180019a7e  jz      short loc_180019AA9
0x180019a80  cmp     [rdx], r14w
0x180019a84  jz      short loc_180019AA9
0x180019a86  lea     rax, [rsp+170h+hkey]
0x180019a8b  xor     r8d, r8d; ulOptions
0x180019a8e  lea     esi, [r14+1]
0x180019a92  mov     [rsp+170h+phkResult], rax; phkResult
0x180019a97  mov     r9d, esi; samDesired
0x180019a9a  call    cs:__imp_RegOpenKeyExW
0x180019aa0  mov     rcx, [rsp+170h+hkey]; hkey
0x180019aa5  mov     ebx, eax
0x180019aa7  jmp     short loc_180019AAF
0x180019aa9  mov     ebx, r14d
0x180019aac  mov     esi, r14d
0x180019aaf  test    ebx, ebx
0x180019ab1  jnz     loc_180019B81
0x180019ab7  lea     rax, [rsp+170h+var_130]
0x180019abc  mov     [rsp+170h+var_130], 100h
0x180019ac4  mov     [rsp+170h+pcbData], rax; pcbData
0x180019ac9  lea     r9d, [rbx+2]; dwFlags
0x180019acd  lea     rax, [rsp+170h+Src]
0x180019ad2  xor     edx, edx; lpSubKey
0x180019ad4  mov     [rsp+170h+pvData], rax; pvData
0x180019ad9  lea     r8, Value; "bgPath"
0x180019ae0  mov     [rsp+170h+phkResult], r14; pdwType
0x180019ae5  call    cs:__imp_RegGetValueW
0x180019aeb  mov     ebx, eax
0x180019aed  test    eax, eax
0x180019aef  jz      short loc_180019AF8
0x180019af1  cmp     eax, 0EAh
0x180019af6  jnz     short loc_180019B6E
0x180019af8  mov     ecx, [rsp+170h+var_130]; cb
0x180019afc  call    cs:__imp_CoTaskMemAlloc
0x180019b02  mov     [rdi], rax
0x180019b05  test    rax, rax
0x180019b08  jz      short loc_180019B69
0x180019b0a  test    ebx, ebx
0x180019b0c  jnz     short loc_180019B22
0x180019b0e  mov     r8d, [rsp+170h+var_130]; Size
0x180019b13  lea     rdx, [rsp+170h+Src]; Src
0x180019b18  mov     rcx, rax; void *
0x180019b1b  call    memcpy_0
0x180019b20  jmp     short loc_180019B6E
0x180019b22  lea     rcx, [rsp+170h+var_130]
0x180019b27  mov     r9d, 2; dwFlags
0x180019b2d  mov     [rsp+170h+pcbData], rcx; pcbData
0x180019b32  lea     r8, Value; "bgPath"
0x180019b39  mov     rcx, [rsp+170h+hkey]; hkey
0x180019b3e  xor     edx, edx; lpSubKey
0x180019b40  mov     [rsp+170h+pvData], rax; pvData
0x180019b45  mov     [rsp+170h+phkResult], r14; pdwType
0x180019b4a  call    cs:__imp_RegGetValueW
0x180019b50  test    eax, eax
0x180019b52  jnz     short loc_180019B59
0x180019b54  mov     ebx, r14d
0x180019b57  jmp     short loc_180019B6E
0x180019b59  mov     rcx, [rdi]; pv
0x180019b5c  mov     ebx, 3EBh
0x180019b61  call    cs:__imp_CoTaskMemFree
0x180019b67  jmp     short loc_180019B6E
0x180019b69  mov     ebx, 0Eh
0x180019b6e  test    esi, esi
0x180019b70  jz      short loc_180019B7D
0x180019b72  mov     rcx, [rsp+170h+hkey]; hKey
0x180019b77  call    cs:__imp_RegCloseKey
0x180019b7d  test    ebx, ebx
0x180019b7f  jz      short loc_180019B91
0x180019b81  mov     [rdi], r14
0x180019b84  test    ebx, ebx
0x180019b86  jle     short loc_180019B91
0x180019b88  movzx   ebx, bx
0x180019b8b  or      ebx, 80070000h
0x180019b91  mov     eax, ebx
0x180019b93  mov     rcx, [rbp+70h+var_20]
0x180019b97  xor     rcx, rsp; StackCookie
0x180019b9a  call    __security_check_cookie
0x180019b9f  lea     r11, [rsp+170h+var_10]
0x180019ba7  mov     rbx, [r11+30h]
0x180019bab  mov     rsi, [r11+38h]
0x180019baf  mov     rsp, r11
0x180019bb2  pop     r14
0x180019bb4  pop     rdi
0x180019bb5  pop     rbp
0x180019bb6  retn
```
