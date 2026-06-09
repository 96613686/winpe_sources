# OverrideServerSpecificSZValues(void)

- ea: `0x18003bafc`
- end: `0x18003bc0e`
- name: `?OverrideServerSpecificSZValues@@YAJXZ`
- size: `274`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800498b8`

## callees

- `0x18003bafc`
- `0x180049da0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bbd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bb2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bb2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bbef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bbef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bbae`

## pseudocode

```c
__int64 OverrideServerSpecificSZValues(void)
{
  LSTATUS v0; // eax
  signed int StringNtpServer; // ebx
  const BYTE *lpData; // rdi
  __int64 v3; // rax
  int v4; // eax
  bool v5; // sf
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 2u, &hKey);
  StringNtpServer = v0;
  if ( v0 > 0 )
    StringNtpServer = (unsigned __int16)v0 | 0x80070000;
  if ( StringNtpServer >= 0 )
  {
    lpData = (const BYTE *)L"time.windows.com,0x8";
    hMem = 0;
    StringNtpServer = GetStringNtpServer((unsigned __int16 **)&hMem, (const struct SzValueEntries *)&lpSubKey);
    if ( StringNtpServer >= 0 )
    {
      lpData = (const BYTE *)hMem;
      StringNtpServer = 0;
    }
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&lpData[2 * v3] );
    v4 = RegSetValueExW(hKey, L"NtpServer", 0, 1u, lpData, 2 * v3 + 2);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 && !StringNtpServer )
      StringNtpServer = v4;
    if ( hMem )
      LocalFree(hMem);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)StringNtpServer;
}

```

## disassembly

```asm
0x18003bafc  mov     r11, rsp
0x18003baff  mov     [r11+18h], rbx
0x18003bb03  mov     [r11+20h], rsi
0x18003bb07  push    rdi
0x18003bb08  sub     rsp, 30h
0x18003bb0c  mov     rdx, cs:lpSubKey; lpSubKey
0x18003bb13  lea     rax, [r11+10h]
0x18003bb17  xor     esi, esi
0x18003bb19  mov     [r11-18h], rax
0x18003bb1d  xor     r8d, r8d; ulOptions
0x18003bb20  mov     [r11+10h], rsi
0x18003bb24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bb2b  lea     r9d, [rsi+2]; samDesired
0x18003bb2f  call    cs:__imp_RegOpenKeyExW
0x18003bb36  nop     dword ptr [rax+rax+00h]
0x18003bb3b  mov     ebx, eax
0x18003bb3d  test    eax, eax
0x18003bb3f  jle     short loc_18003BB4A
0x18003bb41  movzx   ebx, ax
0x18003bb44  or      ebx, 80070000h
0x18003bb4a  test    ebx, ebx
0x18003bb4c  js      loc_18003BBE5
0x18003bb52  mov     rdi, cs:lpData
0x18003bb59  lea     rdx, lpSubKey; struct SzValueEntries *
0x18003bb60  lea     rcx, [rsp+38h+hMem]; unsigned __int16 **
0x18003bb65  mov     [rsp+38h+hMem], rsi
0x18003bb6a  call    ?GetStringNtpServer@@YAJPEAPEAGPEBUSzValueEntries@@@Z; GetStringNtpServer(ushort * *,SzValueEntries const *)
0x18003bb6f  mov     ebx, eax
0x18003bb71  test    eax, eax
0x18003bb73  js      short loc_18003BB7C
0x18003bb75  mov     rdi, [rsp+38h+hMem]
0x18003bb7a  mov     ebx, esi
0x18003bb7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003bb80  inc     rax
0x18003bb83  cmp     [rdi+rax*2], si
0x18003bb87  jnz     short loc_18003BB80
0x18003bb89  mov     rdx, cs:lpValueName; lpValueName
0x18003bb90  lea     eax, ds:2[rax*2]
0x18003bb97  mov     rcx, [rsp+38h+hKey]; hKey
0x18003bb9c  mov     r9d, 1; dwType
0x18003bba2  mov     [rsp+38h+cbData], eax; cbData
0x18003bba6  xor     r8d, r8d; Reserved
0x18003bba9  mov     [rsp+38h+lpData], rdi; lpData
0x18003bbae  call    cs:__imp_RegSetValueExW
0x18003bbb5  nop     dword ptr [rax+rax+00h]
0x18003bbba  test    eax, eax
0x18003bbbc  jle     short loc_18003BBC8
0x18003bbbe  movzx   eax, ax
0x18003bbc1  or      eax, 80070000h
0x18003bbc6  test    eax, eax
0x18003bbc8  jns     short loc_18003BBCF
0x18003bbca  test    ebx, ebx
0x18003bbcc  cmovz   ebx, eax
0x18003bbcf  mov     rcx, [rsp+38h+hMem]; hMem
0x18003bbd4  test    rcx, rcx
0x18003bbd7  jz      short loc_18003BBE5
0x18003bbd9  call    cs:__imp_LocalFree
0x18003bbe0  nop     dword ptr [rax+rax+00h]
0x18003bbe5  mov     rcx, [rsp+38h+hKey]; hKey
0x18003bbea  test    rcx, rcx
0x18003bbed  jz      short loc_18003BBFB
0x18003bbef  call    cs:__imp_RegCloseKey
0x18003bbf6  nop     dword ptr [rax+rax+00h]
0x18003bbfb  mov     rsi, [rsp+38h+arg_18]
0x18003bc00  mov     eax, ebx
0x18003bc02  mov     rbx, [rsp+38h+arg_10]
0x18003bc07  add     rsp, 30h
0x18003bc0b  pop     rdi
0x18003bc0c  retn
```
