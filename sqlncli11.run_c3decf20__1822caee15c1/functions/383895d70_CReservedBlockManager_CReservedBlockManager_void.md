# CReservedBlockManager::CReservedBlockManager(void)

- ea: `0x383895d70`
- end: `0x383895db4`
- name: `??0CReservedBlockManager@@IEAA@XZ`
- size: `68`
- prototype: `CReservedBlockManager *__fastcall(CReservedBlockManager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3838963c0`
- `0x383a98d00`

## callees

- `0x383895d70`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x3838f5216`
- `ADVAPI32!RegQueryValueExW` at `0x3838f5267`
- `ADVAPI32!RegQueryValueExW` at `0x3838f5216`
- `ADVAPI32!RegQueryValueExW` at `0x3838f5267`
- `ADVAPI32!RegOpenKeyW` at `0x383895d9c`
- `ADVAPI32!RegOpenKeyW` at `0x383895d9c`
- `ADVAPI32!RegCloseKey` at `0x3838f5281`
- `ADVAPI32!RegCloseKey` at `0x3838f5281`

## string_xrefs

- `0x383895d8e`: `SOFTWARE\Microsoft\DataAccess\SQLNCLI11`

## pseudocode

```c
CReservedBlockManager *__fastcall CReservedBlockManager::CReservedBlockManager(CReservedBlockManager *this)
{
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+30h] BYREF

  *(_DWORD *)this = 0x100000;
  *((_DWORD *)this + 1) = 500;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\SQLNCLI11", &phkResult) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"ReservedMemorySize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *(_DWORD *)this = ~(g_SystemInfo.dwPageSize - 1) & (g_SystemInfo.dwPageSize + Data - 1);
    cbData = 4;
    if ( !RegQueryValueExW(phkResult, L"MaxReservedBlocks", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)this + 1) = Data;
    RegCloseKey(phkResult);
  }
  return this;
}

```

## disassembly

```asm
0x383895d70  push    rbp
0x383895d72  push    rbx
0x383895d73  mov     rbp, rsp
0x383895d76  sub     rsp, 38h
0x383895d7a  mov     rbx, rcx
0x383895d7d  mov     dword ptr [rcx], 100000h
0x383895d83  mov     dword ptr [rcx+4], 1F4h
0x383895d8a  lea     r8, [rbp+phkResult]; phkResult
0x383895d8e  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\DataAccess\\SQLNCL"...
0x383895d95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383895d9c  call    cs:__imp_RegOpenKeyW
0x383895da2  test    eax, eax
0x383895da4  jz      loc_3838F51EB
0x383895daa  mov     rax, rbx
0x383895dad  add     rsp, 38h
0x383895db1  pop     rbx
0x383895db2  pop     rbp
0x383895db3  retn
0x3838f51eb  mov     rcx, [rbp+phkResult]; hKey
0x3838f51ef  lea     rax, [rbp+cbData]
0x3838f51f3  lea     r9, [rbp+Type]; lpType
0x3838f51f7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x3838f51fc  lea     rax, [rbp+Data]
0x3838f5200  lea     rdx, aReservedmemory; "ReservedMemorySize"
0x3838f5207  xor     r8d, r8d; lpReserved
0x3838f520a  mov     [rbp+cbData], 4
0x3838f5211  mov     [rsp+38h+lpData], rax; lpData
0x3838f5216  call    cs:__imp_RegQueryValueExW
0x3838f521c  test    eax, eax
0x3838f521e  jnz     short loc_3838F523C
0x3838f5220  cmp     [rbp+Type], 4
0x3838f5224  jnz     short loc_3838F523C
0x3838f5226  mov     ecx, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwPageSize; _SYSTEM_INFO g_SystemInfo ...
0x3838f522c  mov     edx, [rbp+Data]
0x3838f522f  dec     edx
0x3838f5231  lea     eax, [rcx-1]
0x3838f5234  not     eax
0x3838f5236  add     edx, ecx
0x3838f5238  and     edx, eax
0x3838f523a  mov     [rbx], edx
0x3838f523c  mov     rcx, [rbp+phkResult]; hKey
0x3838f5240  lea     rax, [rbp+cbData]
0x3838f5244  lea     r9, [rbp+Type]; lpType
0x3838f5248  mov     [rsp+38h+lpcbData], rax; lpcbData
0x3838f524d  lea     rax, [rbp+Data]
0x3838f5251  lea     rdx, aMaxreservedblo; "MaxReservedBlocks"
0x3838f5258  xor     r8d, r8d; lpReserved
0x3838f525b  mov     [rbp+cbData], 4
0x3838f5262  mov     [rsp+38h+lpData], rax; lpData
0x3838f5267  call    cs:__imp_RegQueryValueExW
0x3838f526d  test    eax, eax
0x3838f526f  jnz     short loc_3838F527D
0x3838f5271  cmp     [rbp+Type], 4
0x3838f5275  jnz     short loc_3838F527D
0x3838f5277  mov     eax, [rbp+Data]
0x3838f527a  mov     [rbx+4], eax
0x3838f527d  mov     rcx, [rbp+phkResult]; hKey
0x3838f5281  call    cs:__imp_RegCloseKey
0x3838f5287  nop
0x3838f5288  jmp     loc_383895DAA
```
