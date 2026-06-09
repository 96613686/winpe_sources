# ReadNtsConfig(NtpClientConfig *)

- ea: `0x180044a9c`
- end: `0x180044c6c`
- name: `?ReadNtsConfig@@YAJPEAUNtpClientConfig@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(struct NtpClientConfig *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002125c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180044c3b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180044c3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044bdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180044bdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044b00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044b55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044bb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044c17`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044b55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044bb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044c17`

## string_xrefs

- `0x180044af2`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient\Nts`
- `0x180044ac2`: `Failing as we are attempting to call ReadNtsConfig when nts feature is not enabled.\n`

## pseudocode

```c
LSTATUS __fastcall ReadNtsConfig(struct NtpClientConfig *a1)
{
  LSTATUS result; // eax
  bool v3; // cc
  HLOCAL pvData; // rax
  const wchar_t *i; // rcx
  wchar_t *v6; // rax
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+38h] BYREF

  if ( !*((_BYTE *)g_pnpstate + 50) )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failing as we are attempting to call ReadNtsConfig when nts feature is not enabled.\n");
    return -2147467263;
  }
  hkey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient\\Nts",
         0,
         0x20019u,
         &hkey) )
  {
    goto LABEL_18;
  }
  if ( !hkey )
    return 0;
  pdwType = 0;
  pcbData = 4;
  if ( !RegGetValueW(hkey, 0, L"EnableNts", 0xFFFFu, &pdwType, (char *)a1 + 96, &pcbData) && *((_DWORD *)a1 + 24) == 1 )
    *(_DWORD *)a1 |= 0x10u;
  if ( (*(_BYTE *)a1 & 0x10) == 0 )
  {
LABEL_18:
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  pcbData = 0;
  pdwType = 0;
  result = RegGetValueW(hkey, 0, L"NtsServerList", 0xFFFFu, &pdwType, 0, &pcbData);
  v3 = result <= 0;
  if ( !result )
  {
    pvData = LocalAlloc(0x40u, pcbData);
    *((_QWORD *)a1 + 6) = pvData;
    result = RegGetValueW(hkey, 0, L"NtsServerList", 0xFFFFu, &pdwType, pvData, &pcbData);
    v3 = result <= 0;
    if ( !result )
    {
      for ( i = (const wchar_t *)*((_QWORD *)a1 + 6); ; i = v6 + 1 )
      {
        v6 = wcschr(i, 0x20u);
        if ( !v6 )
          break;
        *v6 = 0;
      }
      goto LABEL_18;
    }
  }
  if ( !v3 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180044a9c  push    rbp
0x180044a9e  push    rbx
0x180044a9f  push    rdi
0x180044aa0  mov     rbp, rsp
0x180044aa3  sub     rsp, 40h
0x180044aa7  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180044aae  mov     rbx, rcx
0x180044ab1  cmp     byte ptr [rax+32h], 0
0x180044ab5  jnz     short loc_180044AD8
0x180044ab7  xor     ecx, ecx
0x180044ab9  call    FileLogAllowEntry
0x180044abe  test    al, al
0x180044ac0  jz      short loc_180044ACE
0x180044ac2  lea     rcx, aFailingAsWeAre_2; "Failing as we are attempting to call Re"...
0x180044ac9  call    FileLogAdd
0x180044ace  mov     eax, 80004001h
0x180044ad3  jmp     loc_180044C63
0x180044ad8  lea     rax, [rbp+hkey]
0x180044adc  mov     [rbp+hkey], 0
0x180044ae4  mov     r9d, 20019h; samDesired
0x180044aea  mov     [rsp+40h+phkResult], rax; phkResult
0x180044aef  xor     r8d, r8d; ulOptions
0x180044af2  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services\\W3"...
0x180044af9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044b00  call    cs:__imp_RegOpenKeyExW
0x180044b07  nop     dword ptr [rax+rax+00h]
0x180044b0c  test    eax, eax
0x180044b0e  jnz     loc_180044C4C
0x180044b14  mov     rcx, [rbp+hkey]; hkey
0x180044b18  test    rcx, rcx
0x180044b1b  jz      loc_180044C61
0x180044b21  mov     [rbp+pdwType], eax
0x180044b24  lea     rdi, [rbx+60h]
0x180044b28  lea     rax, [rbp+arg_8]
0x180044b2c  mov     [rbp+arg_8], 4
0x180044b33  mov     [rsp+40h+pcbData], rax; pcbData
0x180044b38  lea     r8, aEnablents; "EnableNts"
0x180044b3f  lea     rax, [rbp+pdwType]
0x180044b43  mov     [rsp+40h+pvData], rdi; pvData
0x180044b48  mov     r9d, 0FFFFh; dwFlags
0x180044b4e  mov     [rsp+40h+phkResult], rax; pdwType
0x180044b53  xor     edx, edx; lpSubKey
0x180044b55  call    cs:__imp_RegGetValueW
0x180044b5c  nop     dword ptr [rax+rax+00h]
0x180044b61  test    eax, eax
0x180044b63  jnz     short loc_180044B6D
0x180044b65  cmp     dword ptr [rdi], 1
0x180044b68  jnz     short loc_180044B6D
0x180044b6a  or      dword ptr [rbx], 10h
0x180044b6d  test    byte ptr [rbx], 10h
0x180044b70  jz      loc_180044C4C
0x180044b76  mov     rcx, [rbp+hkey]; hkey
0x180044b7a  lea     rax, [rbp+arg_8]
0x180044b7e  mov     [rsp+40h+pcbData], rax; pcbData
0x180044b83  lea     r8, aNtsserverlist; "NtsServerList"
0x180044b8a  lea     rax, [rbp+pdwType]
0x180044b8e  mov     [rsp+40h+pvData], 0; pvData
0x180044b97  mov     r9d, 0FFFFh; dwFlags
0x180044b9d  mov     [rsp+40h+phkResult], rax; pdwType
0x180044ba2  xor     edx, edx; lpSubKey
0x180044ba4  mov     [rbp+arg_8], 0
0x180044bab  mov     [rbp+pdwType], 0
0x180044bb2  call    cs:__imp_RegGetValueW
0x180044bb9  nop     dword ptr [rax+rax+00h]
0x180044bbe  test    eax, eax
0x180044bc0  jz      short loc_180044BD5
0x180044bc2  jle     loc_180044C63
0x180044bc8  movzx   eax, ax
0x180044bcb  or      eax, 80070000h
0x180044bd0  jmp     loc_180044C63
0x180044bd5  mov     edx, [rbp+arg_8]; uBytes
0x180044bd8  mov     ecx, 40h ; '@'; uFlags
0x180044bdd  call    cs:__imp_LocalAlloc
0x180044be4  nop     dword ptr [rax+rax+00h]
0x180044be9  lea     rcx, [rbp+arg_8]
0x180044bed  mov     [rbx+30h], rax
0x180044bf1  mov     [rsp+40h+pcbData], rcx; pcbData
0x180044bf6  mov     r9d, 0FFFFh; dwFlags
0x180044bfc  mov     rcx, [rbp+hkey]; hkey
0x180044c00  lea     r8, aNtsserverlist; "NtsServerList"
0x180044c07  mov     [rsp+40h+pvData], rax; pvData
0x180044c0c  xor     edx, edx; lpSubKey
0x180044c0e  lea     rax, [rbp+pdwType]
0x180044c12  mov     [rsp+40h+phkResult], rax; pdwType
0x180044c17  call    cs:__imp_RegGetValueW
0x180044c1e  nop     dword ptr [rax+rax+00h]
0x180044c23  test    eax, eax
0x180044c25  jnz     short loc_180044BC2
0x180044c27  mov     rcx, [rbx+30h]
0x180044c2b  lea     edi, [rax+20h]
0x180044c2e  jmp     short loc_180044C39
0x180044c30  xor     ecx, ecx
0x180044c32  mov     [rax], cx
0x180044c35  lea     rcx, [rax+2]; Str
0x180044c39  mov     edx, edi; Ch
0x180044c3b  call    cs:__imp_wcschr
0x180044c42  nop     dword ptr [rax+rax+00h]
0x180044c47  test    rax, rax
0x180044c4a  jnz     short loc_180044C30
0x180044c4c  mov     rcx, [rbp+hkey]; hKey
0x180044c50  test    rcx, rcx
0x180044c53  jz      short loc_180044C61
0x180044c55  call    cs:__imp_RegCloseKey
0x180044c5c  nop     dword ptr [rax+rax+00h]
0x180044c61  xor     eax, eax
0x180044c63  add     rsp, 40h
0x180044c67  pop     rdi
0x180044c68  pop     rbx
0x180044c69  pop     rbp
0x180044c6a  retn
```
