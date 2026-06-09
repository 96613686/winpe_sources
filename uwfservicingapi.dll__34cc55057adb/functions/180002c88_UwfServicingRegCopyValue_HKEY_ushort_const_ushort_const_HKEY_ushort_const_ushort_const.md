# UwfServicingRegCopyValue(HKEY__ *,ushort const *,ushort const *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x180002c88`
- end: `0x180002da8`
- name: `?UwfServicingRegCopyValue@@YAJPEAUHKEY__@@PEBG1011@Z`
- size: `288`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, HKEY, const unsigned __int16 *lpSubKey, const unsigned __int16 *lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000348c`
- `0x180003540`

## callees

- `0x180002c88`

## import_xrefs

- `msvcrt!malloc` at `0x180002d04`
- `msvcrt!malloc` at `0x180002d04`
- `msvcrt!free` at `0x180002d80`
- `msvcrt!free` at `0x180002d80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002ce1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002d3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002ce1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002d3f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180002d70`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180002d70`

## pseudocode

```c
__int64 __fastcall UwfServicingRegCopyValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HKEY a4,
        const unsigned __int16 *lpSubKey,
        const unsigned __int16 *lpValueName)
{
  LSTATUS ValueW; // eax
  LSTATUS v9; // ebx
  void *pvData; // rdi
  DWORD dwType; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]
  DWORD Size; // [rsp+78h] [rbp+20h] BYREF
  int Size_4; // [rsp+7Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  v13 = HIDWORD(a1);
  Size = 0;
  dwType = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0xFFFFu, &dwType, 0, &Size);
  v9 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = 0;
    if ( Size )
    {
      pvData = malloc(Size);
      if ( !pvData )
      {
        LOWORD(v9) = 8;
        return (unsigned __int16)v9 | 0x80070000;
      }
    }
    v9 = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0xFFFFu, &dwType, pvData, &Size);
    if ( !v9 )
      v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName, dwType, pvData, Size);
    if ( pvData )
      free(pvData);
  }
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002c88  mov     r11, rsp
0x180002c8b  mov     [r11+10h], rbx
0x180002c8f  mov     [r11+18h], rbp
0x180002c93  mov     [r11+20h], r9
0x180002c97  mov     [r11+8], rcx
0x180002c9b  push    rsi
0x180002c9c  push    rdi
0x180002c9d  push    r15
0x180002c9f  sub     rsp, 40h
0x180002ca3  lea     rax, [r11+20h]
0x180002ca7  mov     dword ptr [rsp+58h+Size], 0
0x180002caf  mov     [r11-28h], rax
0x180002cb3  mov     r15, 0FFFFFFFF80000002h
0x180002cba  lea     rax, [r11+8]
0x180002cbe  mov     qword ptr [r11-30h], 0
0x180002cc6  mov     r9d, 0FFFFh; dwFlags
0x180002ccc  mov     [r11-38h], rax
0x180002cd0  mov     rcx, r15; hkey
0x180002cd3  mov     [rsp+58h+dwType], 0
0x180002cdb  mov     rsi, r8
0x180002cde  mov     rbp, rdx
0x180002ce1  call    cs:__imp_RegGetValueW
0x180002ce7  mov     ebx, eax
0x180002ce9  test    eax, eax
0x180002ceb  jz      short loc_180002CF8
0x180002ced  cmp     eax, 0EAh
0x180002cf2  jnz     loc_180002D86
0x180002cf8  mov     eax, dword ptr [rsp+58h+Size]
0x180002cfc  xor     edi, edi
0x180002cfe  test    eax, eax
0x180002d00  jz      short loc_180002D17
0x180002d02  mov     ecx, eax; Size
0x180002d04  call    cs:__imp_malloc
0x180002d0a  mov     rdi, rax
0x180002d0d  test    rax, rax
0x180002d10  jnz     short loc_180002D17
0x180002d12  lea     ebx, [rax+8]
0x180002d15  jmp     short loc_180002D8A
0x180002d17  lea     rax, [rsp+58h+Size]
0x180002d1c  mov     r9d, 0FFFFh; dwFlags
0x180002d22  mov     [rsp+58h+pcbData], rax; pcbData
0x180002d27  mov     r8, rsi; lpValue
0x180002d2a  lea     rax, [rsp+58h+dwType]
0x180002d2f  mov     [rsp+58h+pvData], rdi; pvData
0x180002d34  mov     rdx, rbp; lpSubKey
0x180002d37  mov     [rsp+58h+pdwType], rax; pdwType
0x180002d3c  mov     rcx, r15; hkey
0x180002d3f  call    cs:__imp_RegGetValueW
0x180002d45  mov     ebx, eax
0x180002d47  test    eax, eax
0x180002d49  jnz     short loc_180002D78
0x180002d4b  mov     eax, dword ptr [rsp+58h+Size]
0x180002d4f  mov     rcx, r15; hKey
0x180002d52  mov     r9d, [rsp+58h+dwType]; dwType
0x180002d57  mov     r8, [rsp+58h+lpValueName]; lpValueName
0x180002d5f  mov     rdx, [rsp+58h+lpSubKey]; lpSubKey
0x180002d67  mov     dword ptr [rsp+58h+pvData], eax; cbData
0x180002d6b  mov     [rsp+58h+pdwType], rdi; lpData
0x180002d70  call    cs:__imp_RegSetKeyValueW
0x180002d76  mov     ebx, eax
0x180002d78  test    rdi, rdi
0x180002d7b  jz      short loc_180002D86
0x180002d7d  mov     rcx, rdi; Block
0x180002d80  call    cs:__imp_free
0x180002d86  test    ebx, ebx
0x180002d88  jle     short loc_180002D93
0x180002d8a  movzx   ebx, bx
0x180002d8d  or      ebx, 80070000h
0x180002d93  mov     rbp, [rsp+58h+arg_10]
0x180002d98  mov     eax, ebx
0x180002d9a  mov     rbx, [rsp+58h+arg_8]
0x180002d9f  add     rsp, 40h
0x180002da3  pop     r15
0x180002da5  pop     rdi
0x180002da6  pop     rsi
0x180002da7  retn
```
