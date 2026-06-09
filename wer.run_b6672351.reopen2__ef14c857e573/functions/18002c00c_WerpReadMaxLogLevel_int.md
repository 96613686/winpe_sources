# WerpReadMaxLogLevel(int)

- ea: `0x18002c00c`
- end: `0x18002c0f1`
- name: `?WerpReadMaxLogLevel@@YAKH@Z`
- size: `229`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034288`
- `0x1800754b4`

## callees

- `0x18002c00c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c08f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c0cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c04e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c04e`

## pseudocode

```c
__int64 __fastcall WerpReadMaxLogLevel(int a1)
{
  int ValueW; // eax
  bool v3; // cc
  char v4; // bl
  unsigned int v5; // edi
  int pvData; // [rsp+68h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+78h] [rbp+20h] BYREF

  pvData = 1;
  pcbData = 4;
  hkey = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
             0,
             0x101u,
             &hkey);
  v3 = ValueW <= 0;
  if ( ValueW || (ValueW = RegGetValueW(hkey, 0, L"LogLevel", 0x10u, 0, &pvData, &pcbData), v3 = ValueW <= 0, ValueW) )
  {
    if ( !v3 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = 0;
    if ( ValueW < 0 )
    {
      pvData = 1;
      v4 = 1;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = pvData;
  if ( hkey )
    RegCloseKey(hkey);
  if ( v4 )
    return a1 != 0 ? 3 : 1;
  else
    return v5;
}

```

## disassembly

```asm
0x18002c00c  mov     rax, rsp
0x18002c00f  push    rbx
0x18002c010  push    rsi
0x18002c011  push    rdi
0x18002c012  sub     rsp, 40h
0x18002c016  mov     dword ptr [rax+10h], 1
0x18002c01d  mov     esi, ecx
0x18002c01f  mov     dword ptr [rax+18h], 4
0x18002c026  mov     r9d, 101h; samDesired
0x18002c02c  mov     qword ptr [rax+20h], 0
0x18002c034  lea     rax, [rax+20h]
0x18002c038  xor     r8d, r8d; ulOptions
0x18002c03b  mov     [rsp+58h+phkResult], rax; phkResult
0x18002c040  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18002c047  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c04e  call    cs:__imp_RegOpenKeyExW
0x18002c055  nop     dword ptr [rax+rax+00h]
0x18002c05a  test    eax, eax
0x18002c05c  jnz     short loc_18002C09F
0x18002c05e  mov     rcx, [rsp+58h+hkey]; hkey
0x18002c063  lea     rax, [rsp+58h+arg_10]
0x18002c068  mov     [rsp+58h+pcbData], rax; pcbData
0x18002c06d  lea     r8, aLoglevel; "LogLevel"
0x18002c074  lea     rax, [rsp+58h+arg_8]
0x18002c079  mov     r9d, 10h; dwFlags
0x18002c07f  mov     [rsp+58h+pvData], rax; pvData
0x18002c084  xor     edx, edx; lpSubKey
0x18002c086  mov     [rsp+58h+phkResult], 0; pdwType
0x18002c08f  call    cs:__imp_RegGetValueW
0x18002c096  nop     dword ptr [rax+rax+00h]
0x18002c09b  test    eax, eax
0x18002c09d  jz      short loc_18002C0BB
0x18002c09f  jle     short loc_18002C0A9
0x18002c0a1  movzx   eax, ax
0x18002c0a4  or      eax, 80070000h
0x18002c0a9  xor     bl, bl
0x18002c0ab  test    eax, eax
0x18002c0ad  jns     short loc_18002C0BD
0x18002c0af  mov     [rsp+58h+arg_8], 1
0x18002c0b7  mov     bl, 1
0x18002c0b9  jmp     short loc_18002C0BD
0x18002c0bb  xor     bl, bl
0x18002c0bd  mov     rcx, [rsp+58h+hkey]; hKey
0x18002c0c2  mov     edi, [rsp+58h+arg_8]
0x18002c0c6  test    rcx, rcx
0x18002c0c9  jz      short loc_18002C0D7
0x18002c0cb  call    cs:__imp_RegCloseKey
0x18002c0d2  nop     dword ptr [rax+rax+00h]
0x18002c0d7  test    bl, bl
0x18002c0d9  jnz     short loc_18002C0DF
0x18002c0db  mov     eax, edi
0x18002c0dd  jmp     short loc_18002C0E8
0x18002c0df  neg     esi
0x18002c0e1  sbb     eax, eax
0x18002c0e3  and     eax, 2
0x18002c0e6  inc     eax
0x18002c0e8  add     rsp, 40h
0x18002c0ec  pop     rdi
0x18002c0ed  pop     rsi
0x18002c0ee  pop     rbx
0x18002c0ef  retn
```
