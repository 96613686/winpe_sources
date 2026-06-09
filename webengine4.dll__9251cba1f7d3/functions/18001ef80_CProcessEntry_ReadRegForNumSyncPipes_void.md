# CProcessEntry::ReadRegForNumSyncPipes(void)

- ea: `0x18001ef80`
- end: `0x18001f05a`
- name: `?ReadRegForNumSyncPipes@CProcessEntry@@CAHXZ`
- size: `218`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dc88`

## callees

- `0x18001ef80`
- `0x180020948`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18001f015`
- `KERNEL32!GetSystemInfo` at `0x18001f015`
- `ADVAPI32!RegCloseKey` at `0x18001effb`
- `ADVAPI32!RegCloseKey` at `0x18001effb`
- `ADVAPI32!RegOpenKeyExW` at `0x18001efb2`
- `ADVAPI32!RegOpenKeyExW` at `0x18001efb2`
- `ADVAPI32!RegQueryValueExW` at `0x18001efed`
- `ADVAPI32!RegQueryValueExW` at `0x18001efed`

## pseudocode

```c
__int64 CProcessEntry::ReadRegForNumSyncPipes(void)
{
  int v0; // edi
  int v1; // ebx
  int v2; // ecx
  DWORD_PTR dwActiveProcessorMask; // rax
  __int64 v4; // rdx
  int v5; // ecx
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF
  int Data; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v0 = 4;
  v1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    cbData = 4;
    RegQueryValueExW(hKey, L"SyncPipesPerCPU", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    v2 = Data;
    if ( (unsigned int)(Data - 1) > 0x63 )
      v2 = 4;
    v0 = v2;
  }
  GetSystemInfo(&SystemInfo);
  dwActiveProcessorMask = SystemInfo.dwActiveProcessorMask;
  v4 = 32;
  do
  {
    v5 = v1 + 1;
    if ( (dwActiveProcessorMask & 1) == 0 )
      v5 = v1;
    dwActiveProcessorMask >>= 1;
    v1 = v5;
    --v4;
  }
  while ( v4 );
  SystemInfo.dwActiveProcessorMask = dwActiveProcessorMask;
  return (unsigned int)(v0 * v5 / (int)CProcessTableManager::NumActiveCPUs());
}

```

## disassembly

```asm
0x18001ef80  mov     r11, rsp
0x18001ef83  mov     [r11+20h], rbx
0x18001ef87  push    rdi
0x18001ef88  sub     rsp, 60h
0x18001ef8c  lea     rax, [r11+18h]
0x18001ef90  mov     r9d, 20019h; samDesired
0x18001ef96  xor     r8d, r8d; ulOptions
0x18001ef99  mov     [r11-48h], rax
0x18001ef9d  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18001efa4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001efab  mov     edi, 4
0x18001efb0  xor     ebx, ebx
0x18001efb2  call    cs:__imp_RegOpenKeyExW
0x18001efb8  test    eax, eax
0x18001efba  jnz     short loc_18001F010
0x18001efbc  mov     rcx, [rsp+68h+hKey]; hKey
0x18001efc4  lea     rax, [rsp+68h+cbData]
0x18001efc9  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001efce  lea     rdx, aSyncpipespercp; "SyncPipesPerCPU"
0x18001efd5  lea     rax, [rsp+68h+Data]
0x18001efda  mov     [rsp+68h+Data], ebx
0x18001efde  xor     r9d, r9d; lpType
0x18001efe1  mov     [rsp+68h+lpData], rax; lpData
0x18001efe6  xor     r8d, r8d; lpReserved
0x18001efe9  mov     [rsp+68h+cbData], edi
0x18001efed  call    cs:__imp_RegQueryValueExW
0x18001eff3  mov     rcx, [rsp+68h+hKey]; hKey
0x18001effb  call    cs:__imp_RegCloseKey
0x18001f001  mov     ecx, [rsp+68h+Data]
0x18001f005  lea     eax, [rcx-1]
0x18001f008  cmp     eax, 63h ; 'c'
0x18001f00b  cmova   ecx, edi
0x18001f00e  mov     edi, ecx
0x18001f010  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18001f015  call    cs:__imp_GetSystemInfo
0x18001f01b  mov     rax, [rsp+68h+SystemInfo.dwActiveProcessorMask]
0x18001f020  mov     edx, 20h ; ' '
0x18001f025  test    al, 1
0x18001f027  lea     ecx, [rbx+1]
0x18001f02a  cmovz   ecx, ebx
0x18001f02d  shr     rax, 1
0x18001f030  mov     ebx, ecx
0x18001f032  sub     rdx, 1
0x18001f036  jnz     short loc_18001F025
0x18001f038  mov     [rsp+68h+SystemInfo.dwActiveProcessorMask], rax
0x18001f03d  call    ?NumActiveCPUs@CProcessTableManager@@SAHXZ; CProcessTableManager::NumActiveCPUs(void)
0x18001f042  imul    ebx, edi
0x18001f045  mov     ecx, eax
0x18001f047  mov     eax, ebx
0x18001f049  mov     rbx, [rsp+68h+arg_18]
0x18001f051  cdq
0x18001f052  idiv    ecx
0x18001f054  add     rsp, 60h
0x18001f058  pop     rdi
0x18001f059  retn
```
