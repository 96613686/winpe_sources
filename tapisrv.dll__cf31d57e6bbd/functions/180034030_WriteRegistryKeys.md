# WriteRegistryKeys

- ea: `0x180034030`
- end: `0x18003414e`
- name: `WriteRegistryKeys`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032ad0`

## callees

- `0x180034030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034134`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034134`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003413e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800340bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800340bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800340e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034124`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800340e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034124`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003407a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003407a`
- `KERNEL32!lstrlenW` at `0x1800340fa`
- `KERNEL32!lstrlenW` at `0x1800340fa`

## string_xrefs

- `0x1800340f0`: `TSEC.DLL`
- `0x180034104`: `MapperDll`

## pseudocode

```c
__int64 __fastcall WriteRegistryKeys(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // ebx
  int v4; // eax
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  int v8; // [rsp+7Ch] [rbp+2Ch]
  int Data; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  Data = a3;
  v8 = HIDWORD(a2);
  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  v3 = -2147483576;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Telephony",
          0,
          0xF003Fu,
          &hKey) )
  {
    if ( !RegCreateKeyExW(hKey, L"Server", 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition) )
    {
      if ( !RegSetValueExW(phkResult, L"DisableSharing", 0, 4u, (const BYTE *)&Data, 4u) )
      {
        v4 = lstrlenW(L"TSEC.DLL");
        v3 = RegSetValueExW(phkResult, L"MapperDll", 0, 1u, (const BYTE *)L"TSEC.DLL", 2 * v4 + 2) != 0 ? 0x80000048 : 0;
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180034030  mov     r11, rsp
0x180034033  mov     [r11+18h], r8d
0x180034037  mov     [r11+10h], rdx
0x18003403b  mov     [r11+8], rcx
0x18003403f  push    rbp
0x180034040  push    rbx
0x180034041  push    rdi
0x180034042  mov     rbp, rsp
0x180034045  sub     rsp, 50h
0x180034049  xor     edi, edi
0x18003404b  lea     rax, [rbp+hKey]
0x18003404f  mov     r9d, 0F003Fh; samDesired
0x180034055  mov     [rbp+hKey], rdi
0x180034059  xor     r8d, r8d; ulOptions
0x18003405c  mov     [rbp+arg_0], rdi
0x180034060  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180034067  mov     [rbp+dwDisposition], edi
0x18003406a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034071  mov     [r11-48h], rax
0x180034075  mov     ebx, 80000048h
0x18003407a  call    cs:__imp_RegOpenKeyExW
0x180034080  test    eax, eax
0x180034082  jnz     loc_180034144
0x180034088  mov     rcx, [rbp+hKey]; hKey
0x18003408c  lea     rax, [rbp+dwDisposition]
0x180034090  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180034095  lea     rdx, aServer; "Server"
0x18003409c  lea     rax, [rbp+arg_0]
0x1800340a0  xor     r9d, r9d; lpClass
0x1800340a3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800340a8  xor     r8d, r8d; Reserved
0x1800340ab  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800340b0  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x1800340b8  mov     [rsp+50h+dwOptions], edi; dwOptions
0x1800340bc  call    cs:__imp_RegCreateKeyExW
0x1800340c2  test    eax, eax
0x1800340c4  jnz     short loc_18003413A
0x1800340c6  mov     rcx, [rbp+arg_0]; hKey
0x1800340ca  lea     r9d, [rdi+4]; dwType
0x1800340ce  lea     rax, [rbp+Data]
0x1800340d2  mov     [rsp+50h+samDesired], r9d; cbData
0x1800340d7  xor     r8d, r8d; Reserved
0x1800340da  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800340df  lea     rdx, aDisablesharing; "DisableSharing"
0x1800340e6  call    cs:__imp_RegSetValueExW
0x1800340ec  test    eax, eax
0x1800340ee  jnz     short loc_180034130
0x1800340f0  lea     rdi, Data; "TSEC.DLL"
0x1800340f7  mov     rcx, rdi; lpString
0x1800340fa  call    cs:__imp_lstrlenW
0x180034100  mov     rcx, [rbp+arg_0]; hKey
0x180034104  lea     rdx, aMapperdll; "MapperDll"
0x18003410b  mov     r9d, 1; dwType
0x180034111  xor     r8d, r8d; Reserved
0x180034114  lea     eax, ds:2[rax*2]
0x18003411b  mov     [rsp+50h+samDesired], eax; cbData
0x18003411f  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x180034124  call    cs:__imp_RegSetValueExW
0x18003412a  neg     eax
0x18003412c  sbb     ecx, ecx
0x18003412e  and     ebx, ecx
0x180034130  mov     rcx, [rbp+arg_0]; hKey
0x180034134  call    cs:__imp_RegCloseKey
0x18003413a  mov     rcx, [rbp+hKey]; hKey
0x18003413e  call    cs:__imp_RegCloseKey
0x180034144  mov     eax, ebx
0x180034146  add     rsp, 50h
0x18003414a  pop     rdi
0x18003414b  pop     rbx
0x18003414c  pop     rbp
0x18003414d  retn
```
