# VerifyDomainName

- ea: `0x18002f4b4`
- end: `0x18002f657`
- name: `VerifyDomainName`
- size: `419`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d6d0`

## callees

- `0x18002c8d4`
- `0x18002f4b4`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f62c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f62c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f604`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f4f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f543`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f4f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f543`
- `KERNEL32!HeapAlloc` at `0x18002f50f`
- `KERNEL32!HeapAlloc` at `0x18002f563`
- `KERNEL32!HeapAlloc` at `0x18002f50f`
- `KERNEL32!HeapAlloc` at `0x18002f563`
- `KERNEL32!GetComputerNameExW` at `0x18002f57d`
- `KERNEL32!GetComputerNameExW` at `0x18002f57d`
- `KERNEL32!GetLastError` at `0x18002f589`
- `KERNEL32!GetLastError` at `0x18002f589`

## string_xrefs

- `0x18002f58f`: `VerifyDomainName: GetComputerNameEx failed - error x%x`
- `0x18002f611`: `VerifyDomainName:RegSetValueEx (%S) failed`

## pseudocode

```c
__int64 __fastcall VerifyDomainName(HKEY hKey)
{
  BYTE *lpData; // rsi
  wchar_t *v3; // rdi
  unsigned int v4; // ebx
  WCHAR *v5; // rax
  DWORD LastError; // eax
  int v7; // eax
  int v8; // eax
  BYTE *v9; // rcx
  int v10; // r10d
  int v11; // r8d
  SIZE_T dwBytes; // [rsp+58h] [rbp+28h] BYREF
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF

  Type = 0;
  lpData = 0;
  LODWORD(dwBytes) = 0;
  if ( (RegQueryValueExW(hKey, L"DomainName", 0, &Type, 0, (LPDWORD)&dwBytes)
     || (v3 = 0, (lpData = (BYTE *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)dwBytes)) != 0)
     && !RegQueryValueExW(hKey, L"DomainName", 0, &Type, lpData, (LPDWORD)&dwBytes))
    && (LODWORD(dwBytes) = 256, v5 = (WCHAR *)HeapAlloc(ghTapisrvHeap, 8u, 0x200u), (v3 = v5) != 0) )
  {
    if ( GetComputerNameExW(ComputerNameDnsDomain, v5, (LPDWORD)&dwBytes) )
    {
      v7 = dwBytes;
      v4 = 1;
      if ( !(_DWORD)dwBytes )
      {
        *v3 = 0;
        v7 = dwBytes;
      }
      v8 = v7 + 1;
      LODWORD(dwBytes) = v8;
      if ( !lpData )
        goto LABEL_21;
      v9 = lpData;
      do
      {
        v10 = *(unsigned __int16 *)&v9[(char *)v3 - (char *)lpData];
        v11 = *(unsigned __int16 *)v9 - v10;
        if ( v11 )
          break;
        v9 += 2;
      }
      while ( v10 );
      if ( v11 )
      {
LABEL_21:
        if ( RegSetValueExW(hKey, L"DomainName", 0, 1u, (const BYTE *)v3, 2 * v8) )
          TRACELogPrint(262146, "VerifyDomainName:RegSetValueEx (%S) failed", v3);
        RegDeleteValueW(hKey, L"TAPISRVSCPGUID");
      }
    }
    else
    {
      v4 = 0;
      LastError = GetLastError();
      TRACELogPrint(262146, "VerifyDomainName: GetComputerNameEx failed - error x%x", LastError);
    }
  }
  else
  {
    v4 = 0;
  }
  ServerFree(lpData);
  ServerFree(v3);
  return v4;
}

```

## disassembly

```asm
0x18002f4b4  mov     r11, rsp
0x18002f4b7  mov     [r11+8], rbx
0x18002f4bb  mov     [r11+20h], rsi
0x18002f4bf  push    rbp
0x18002f4c0  push    rdi
0x18002f4c1  push    r14
0x18002f4c3  mov     rbp, rsp
0x18002f4c6  sub     rsp, 30h
0x18002f4ca  lea     rax, [rbp+dwBytes]
0x18002f4ce  mov     [rbp+Type], 0
0x18002f4d5  xor     esi, esi
0x18002f4d7  mov     [r11-20h], rax
0x18002f4db  lea     r9, [rbp+Type]; lpType
0x18002f4df  mov     [r11-28h], rsi
0x18002f4e3  xor     r8d, r8d; lpReserved
0x18002f4e6  mov     dword ptr [rbp+dwBytes], esi
0x18002f4e9  lea     rdx, gszDomainName; "DomainName"
0x18002f4f0  mov     r14, rcx
0x18002f4f3  call    cs:__imp_RegQueryValueExW
0x18002f4f9  lea     ebx, [rsi+8]
0x18002f4fc  test    eax, eax
0x18002f4fe  jnz     short loc_18002F54D
0x18002f500  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x18002f504  mov     edx, ebx; dwFlags
0x18002f506  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002f50d  xor     edi, edi
0x18002f50f  call    cs:__imp_HeapAlloc
0x18002f515  mov     rsi, rax
0x18002f518  test    rax, rax
0x18002f51b  jnz     short loc_18002F524
0x18002f51d  xor     ebx, ebx
0x18002f51f  jmp     loc_18002F632
0x18002f524  lea     rax, [rbp+dwBytes]
0x18002f528  xor     r8d, r8d; lpReserved
0x18002f52b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f530  lea     r9, [rbp+Type]; lpType
0x18002f534  lea     rdx, gszDomainName; "DomainName"
0x18002f53b  mov     [rsp+30h+lpData], rsi; lpData
0x18002f540  mov     rcx, r14; hKey
0x18002f543  call    cs:__imp_RegQueryValueExW
0x18002f549  test    eax, eax
0x18002f54b  jnz     short loc_18002F51D
0x18002f54d  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002f554  mov     r8d, 200h; dwBytes
0x18002f55a  mov     edx, ebx; dwFlags
0x18002f55c  mov     dword ptr [rbp+dwBytes], 100h
0x18002f563  call    cs:__imp_HeapAlloc
0x18002f569  mov     rdi, rax
0x18002f56c  test    rax, rax
0x18002f56f  jz      short loc_18002F51D
0x18002f571  lea     r8, [rbp+dwBytes]; nSize
0x18002f575  mov     rdx, rax; lpBuffer
0x18002f578  mov     ecx, 2; NameType
0x18002f57d  call    cs:__imp_GetComputerNameExW
0x18002f583  test    eax, eax
0x18002f585  jnz     short loc_18002F5A8
0x18002f587  xor     ebx, ebx
0x18002f589  call    cs:__imp_GetLastError
0x18002f58f  lea     rdx, aVerifydomainna_0; "VerifyDomainName: GetComputerNameEx fai"...
0x18002f596  mov     ecx, 40002h
0x18002f59b  mov     r8d, eax
0x18002f59e  call    TRACELogPrint
0x18002f5a3  jmp     loc_18002F632
0x18002f5a8  mov     eax, dword ptr [rbp+dwBytes]
0x18002f5ab  mov     ebx, 1
0x18002f5b0  test    eax, eax
0x18002f5b2  jnz     short loc_18002F5BA
0x18002f5b4  mov     [rdi], ax
0x18002f5b7  mov     eax, dword ptr [rbp+dwBytes]
0x18002f5ba  add     eax, ebx
0x18002f5bc  mov     dword ptr [rbp+dwBytes], eax
0x18002f5bf  test    rsi, rsi
0x18002f5c2  jz      short loc_18002F5E9
0x18002f5c4  mov     r9, rdi
0x18002f5c7  mov     rcx, rsi
0x18002f5ca  sub     r9, rsi
0x18002f5cd  movzx   r8d, word ptr [rcx]
0x18002f5d1  movzx   r10d, word ptr [rcx+r9]
0x18002f5d6  sub     r8d, r10d
0x18002f5d9  jnz     short loc_18002F5E4
0x18002f5db  add     rcx, 2
0x18002f5df  test    r10d, r10d
0x18002f5e2  jnz     short loc_18002F5CD
0x18002f5e4  test    r8d, r8d
0x18002f5e7  jz      short loc_18002F632
0x18002f5e9  add     eax, eax
0x18002f5eb  lea     rdx, gszDomainName; "DomainName"
0x18002f5f2  mov     dword ptr [rsp+30h+lpcbData], eax; cbData
0x18002f5f6  mov     r9d, ebx; dwType
0x18002f5f9  xor     r8d, r8d; Reserved
0x18002f5fc  mov     [rsp+30h+lpData], rdi; lpData
0x18002f601  mov     rcx, r14; hKey
0x18002f604  call    cs:__imp_RegSetValueExW
0x18002f60a  test    eax, eax
0x18002f60c  jz      short loc_18002F622
0x18002f60e  mov     r8, rdi
0x18002f611  lea     rdx, aVerifydomainna; "VerifyDomainName:RegSetValueEx (%S) fai"...
0x18002f618  mov     ecx, 40002h
0x18002f61d  call    TRACELogPrint
0x18002f622  lea     rdx, gszRegTapisrvSCPGuid; "TAPISRVSCPGUID"
0x18002f629  mov     rcx, r14; hKey
0x18002f62c  call    cs:__imp_RegDeleteValueW
0x18002f632  mov     rcx, rsi; lpMem
0x18002f635  call    ServerFree
0x18002f63a  mov     rcx, rdi; lpMem
0x18002f63d  call    ServerFree
0x18002f642  mov     rsi, [rsp+30h+arg_18]
0x18002f647  mov     eax, ebx
0x18002f649  mov     rbx, [rsp+30h+arg_0]
0x18002f64e  add     rsp, 30h
0x18002f652  pop     r14
0x18002f654  pop     rdi
0x18002f655  pop     rbp
0x18002f656  retn
```
