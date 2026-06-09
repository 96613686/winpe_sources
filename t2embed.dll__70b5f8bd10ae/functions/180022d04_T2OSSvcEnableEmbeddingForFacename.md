# T2OSSvcEnableEmbeddingForFacename

- ea: `0x180022d04`
- end: `0x180022de2`
- name: `T2OSSvcEnableEmbeddingForFacename`
- size: `222`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020080`

## callees

- `0x180022d04`

## import_xrefs

- `KERNEL32!RegCloseKey` at `0x180022d9b`
- `KERNEL32!RegCloseKey` at `0x180022d9b`
- `KERNEL32!RegDeleteValueA` at `0x180022d8b`
- `KERNEL32!RegDeleteValueA` at `0x180022d8b`
- `KERNEL32!RegSetValueExA` at `0x180022dd4`
- `KERNEL32!RegSetValueExA` at `0x180022dd4`
- `KERNEL32!RegCreateKeyExA` at `0x180022d71`
- `KERNEL32!RegCreateKeyExA` at `0x180022d71`

## pseudocode

```c
__int64 __fastcall T2OSSvcEnableEmbeddingForFacename(LPCSTR lpValueName, int a2, __int64 a3)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF
  int v9; // [rsp+84h] [rbp+1Ch]
  DWORD v10; // [rsp+88h] [rbp+20h] BYREF

  v9 = HIDWORD(a3);
  hKey = 0;
  Data = 0;
  v10 = 0;
  if ( RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Shared Tools\\t2embed",
         0,
         (LPSTR)&Class,
         0,
         0x2001Fu,
         0,
         &hKey,
         &v10) )
  {
    return 0;
  }
  if ( a2 )
  {
    RegDeleteValueA(hKey, lpValueName);
  }
  else
  {
    Data = 0;
    if ( RegSetValueExA(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u) )
    {
      v6 = 0;
      goto LABEL_6;
    }
  }
  v6 = 1;
LABEL_6:
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180022d04  mov     r11, rsp
0x180022d07  mov     [r11+8], rbx
0x180022d0b  mov     [r11+18h], r8
0x180022d0f  push    rdi
0x180022d10  sub     rsp, 60h
0x180022d14  lea     rax, [r11+20h]
0x180022d18  mov     qword ptr [r11-18h], 0
0x180022d20  mov     [r11-28h], rax
0x180022d24  lea     r9, Class; lpClass
0x180022d2b  lea     rax, [r11-18h]
0x180022d2f  mov     dword ptr [r11+18h], 0
0x180022d37  mov     [r11-30h], rax
0x180022d3b  mov     edi, edx
0x180022d3d  mov     qword ptr [r11-38h], 0
0x180022d45  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Shared Tools\\t2em"...
0x180022d4c  mov     rbx, rcx
0x180022d4f  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180022d57  xor     r8d, r8d; Reserved
0x180022d5a  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180022d62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022d69  mov     dword ptr [r11+20h], 0
0x180022d71  call    cs:__imp_RegCreateKeyExA
0x180022d77  test    eax, eax
0x180022d79  jz      short loc_180022D7F
0x180022d7b  xor     eax, eax
0x180022d7d  jmp     short loc_180022DA3
0x180022d7f  mov     rcx, [rsp+68h+hKey]; hKey
0x180022d84  mov     rdx, rbx; lpValueName
0x180022d87  test    edi, edi
0x180022d89  jz      short loc_180022DAE
0x180022d8b  call    cs:__imp_RegDeleteValueA
0x180022d91  mov     ebx, 1
0x180022d96  mov     rcx, [rsp+68h+hKey]; hKey
0x180022d9b  call    cs:__imp_RegCloseKey
0x180022da1  mov     eax, ebx
0x180022da3  mov     rbx, [rsp+68h+arg_0]
0x180022da8  add     rsp, 60h
0x180022dac  pop     rdi
0x180022dad  retn
0x180022dae  mov     r9d, 4; dwType
0x180022db4  mov     [rsp+68h+Data], 0
0x180022dbf  lea     rax, [rsp+68h+Data]
0x180022dc7  mov     [rsp+68h+samDesired], r9d; cbData
0x180022dcc  xor     r8d, r8d; Reserved
0x180022dcf  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180022dd4  call    cs:__imp_RegSetValueExA
0x180022dda  test    eax, eax
0x180022ddc  jz      short loc_180022D91
0x180022dde  xor     ebx, ebx
0x180022de0  jmp     short loc_180022D96
```
