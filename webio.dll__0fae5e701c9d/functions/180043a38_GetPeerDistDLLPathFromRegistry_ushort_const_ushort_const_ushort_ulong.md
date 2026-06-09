# GetPeerDistDLLPathFromRegistry(ushort const *,ushort const *,ushort *,ulong *)

- ea: `0x180043a38`
- end: `0x180043b1d`
- name: `?GetPeerDistDLLPathFromRegistry@@YAKPEBG0PEAGPEAK@Z`
- size: `229`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042c64`

## callees

- `0x180043a38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043afe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043afe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043a8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043a8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043ac9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043ac9`

## string_xrefs

- `0x180043a53`: `Software\Microsoft\Windows NT\CurrentVersion\PeerDist\Extension`
- `0x180043ab7`: `PeerdistDllName`

## pseudocode

```c
__int64 __fastcall GetPeerDistDLLPathFromRegistry(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v4; // eax
  unsigned int ValueW; // ebx
  HKEY hkey; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *pcbData; // [rsp+58h] [rbp+10h] BYREF

  pcbData = a2;
  hkey = (HKEY)a1;
  v4 = 2 * *a4;
  *a4 = 0;
  LODWORD(pcbData) = v4;
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Extension",
             0,
             0x20119u,
             &hkey);
  if ( !ValueW )
  {
    ValueW = RegGetValueW(hkey, 0, L"PeerdistDllName", 2u, 0, a3, (LPDWORD)&pcbData);
    if ( !ValueW )
    {
      if ( ((unsigned __int8)pcbData & 1) != 0 || !(_DWORD)pcbData )
        ValueW = 13;
      else
        *a4 = ((unsigned int)pcbData >> 1) - 1;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x180043a38  mov     r11, rsp
0x180043a3b  mov     [r11+18h], rbx
0x180043a3f  mov     [r11+20h], rsi
0x180043a43  mov     [r11+10h], rdx
0x180043a47  mov     [r11+8], rcx
0x180043a4b  push    rdi
0x180043a4c  sub     rsp, 40h
0x180043a50  mov     eax, [r9]
0x180043a53  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180043a5a  add     eax, eax
0x180043a5c  mov     dword ptr [r9], 0
0x180043a63  mov     dword ptr [rsp+48h+arg_8], eax
0x180043a67  mov     rdi, r9
0x180043a6a  lea     rax, [r11+8]
0x180043a6e  mov     qword ptr [r11+8], 0
0x180043a76  mov     rsi, r8
0x180043a79  mov     [r11-28h], rax
0x180043a7d  mov     r9d, 20119h; samDesired
0x180043a83  xor     r8d, r8d; ulOptions
0x180043a86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043a8d  call    cs:__imp_RegOpenKeyExW
0x180043a94  nop     dword ptr [rax+rax+00h]
0x180043a99  mov     ebx, eax
0x180043a9b  test    eax, eax
0x180043a9d  jnz     short loc_180043AF4
0x180043a9f  mov     rcx, [rsp+48h+hkey]; hkey
0x180043aa4  lea     rax, [rsp+48h+arg_8]
0x180043aa9  mov     [rsp+48h+pcbData], rax; pcbData
0x180043aae  lea     r9d, [rbx+2]; dwFlags
0x180043ab2  mov     [rsp+48h+pvData], rsi; pvData
0x180043ab7  lea     r8, aPeerdistdllnam; "PeerdistDllName"
0x180043abe  xor     edx, edx; lpSubKey
0x180043ac0  mov     [rsp+48h+pdwType], 0; pdwType
0x180043ac9  call    cs:__imp_RegGetValueW
0x180043ad0  nop     dword ptr [rax+rax+00h]
0x180043ad5  mov     ebx, eax
0x180043ad7  test    eax, eax
0x180043ad9  jnz     short loc_180043AF4
0x180043adb  mov     eax, dword ptr [rsp+48h+arg_8]
0x180043adf  test    al, 1
0x180043ae1  jnz     short loc_180043AEF
0x180043ae3  test    eax, eax
0x180043ae5  jz      short loc_180043AEF
0x180043ae7  shr     eax, 1
0x180043ae9  dec     eax
0x180043aeb  mov     [rdi], eax
0x180043aed  jmp     short loc_180043AF4
0x180043aef  mov     ebx, 0Dh
0x180043af4  mov     rcx, [rsp+48h+hkey]; hKey
0x180043af9  test    rcx, rcx
0x180043afc  jz      short loc_180043B0A
0x180043afe  call    cs:__imp_RegCloseKey
0x180043b05  nop     dword ptr [rax+rax+00h]
0x180043b0a  mov     rsi, [rsp+48h+arg_18]
0x180043b0f  mov     eax, ebx
0x180043b11  mov     rbx, [rsp+48h+arg_10]
0x180043b16  add     rsp, 40h
0x180043b1a  pop     rdi
0x180043b1b  retn
```
