# RegSetKeyString

- ea: `0x1400097e4`
- end: `0x14000987f`
- name: `RegSetKeyString`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140008b70`
- `0x140009888`

## callees

- `0x1400097e4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x140009810`
- `ADVAPI32!RegOpenKeyExA` at `0x140009810`
- `ADVAPI32!RegSetValueExA` at `0x140009852`
- `ADVAPI32!RegSetValueExA` at `0x140009852`
- `ADVAPI32!RegCloseKey` at `0x14000985f`
- `ADVAPI32!RegCloseKey` at `0x14000985f`

## pseudocode

```c
__int64 __fastcall RegSetKeyString(HKEY a1, const CHAR *a2, __int64 a3, const BYTE *a4)
{
  LSTATUS v5; // ebx
  __int64 v6; // rax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExA(a1, a2, 0, 0x20006u, &hKey);
  if ( !v5 )
  {
    if ( a4 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a4[v6] );
    }
    else
    {
      LODWORD(v6) = 0;
    }
    v5 = RegSetValueExA(hKey, ValueName, 0, 1u, a4, v6 + 1);
    RegCloseKey(hKey);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400097e4  mov     r11, rsp
0x1400097e7  mov     [r11+8], rbx
0x1400097eb  mov     [r11+18h], r8
0x1400097ef  push    rdi
0x1400097f0  sub     rsp, 30h
0x1400097f4  mov     rdi, r9
0x1400097f7  mov     qword ptr [r11+18h], 0
0x1400097ff  lea     rax, [r11+18h]
0x140009803  mov     r9d, 20006h; samDesired
0x140009809  xor     r8d, r8d; ulOptions
0x14000980c  mov     [r11-18h], rax
0x140009810  call    cs:__imp_RegOpenKeyExA
0x140009816  mov     ebx, eax
0x140009818  test    eax, eax
0x14000981a  jnz     short loc_140009865
0x14000981c  test    rdi, rdi
0x14000981f  jz      short loc_140009830
0x140009821  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009825  inc     rax
0x140009828  cmp     byte ptr [rdi+rax], 0
0x14000982c  jnz     short loc_140009825
0x14000982e  jmp     short loc_140009832
0x140009830  xor     eax, eax
0x140009832  mov     rcx, [rsp+38h+hKey]; hKey
0x140009837  lea     rdx, ValueName; lpValueName
0x14000983e  inc     eax
0x140009840  mov     r9d, 1; dwType
0x140009846  mov     [rsp+38h+cbData], eax; cbData
0x14000984a  xor     r8d, r8d; Reserved
0x14000984d  mov     [rsp+38h+lpData], rdi; lpData
0x140009852  call    cs:__imp_RegSetValueExA
0x140009858  mov     rcx, [rsp+38h+hKey]; hKey
0x14000985d  mov     ebx, eax
0x14000985f  call    cs:__imp_RegCloseKey
0x140009865  test    ebx, ebx
0x140009867  jle     short loc_140009872
0x140009869  movzx   ebx, bx
0x14000986c  or      ebx, 80070000h
0x140009872  mov     eax, ebx
0x140009874  mov     rbx, [rsp+38h+arg_0]
0x140009879  add     rsp, 30h
0x14000987d  pop     rdi
0x14000987e  retn
```
