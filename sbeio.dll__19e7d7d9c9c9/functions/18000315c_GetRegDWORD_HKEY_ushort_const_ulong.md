# GetRegDWORD(HKEY__ *,ushort const *,ulong)

- ea: `0x18000315c`
- end: `0x18000320b`
- name: `?GetRegDWORD@@YAKPEAUHKEY__@@PEBGK@Z`
- size: `175`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800059b0`

## callees

- `0x18000315c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800031ad`
- `ADVAPI32!RegQueryValueExW` at `0x1800031ad`
- `ADVAPI32!RegSetValueExW` at `0x1800031e0`
- `ADVAPI32!RegSetValueExW` at `0x1800031e0`

## pseudocode

```c
__int64 __fastcall GetRegDWORD(HKEY hKey, LPCWSTR lpValueName, unsigned int a3)
{
  LSTATUS v5; // eax
  DWORD v7; // [rsp+30h] [rbp-18h] BYREF
  BYTE lpData[20]; // [rsp+34h] [rbp-14h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD v10; // [rsp+68h] [rbp+20h] BYREF

  if ( !lpValueName || !hKey )
    return a3;
  Data = a3;
  v7 = 0;
  *(_DWORD *)lpData = 0;
  v10 = 4;
  v5 = RegQueryValueExW(hKey, lpValueName, 0, &v7, lpData, &v10);
  if ( (v5 & 0xFFFFFFFD) == 0 )
  {
    if ( v5 == 2 )
    {
      RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    }
    else if ( v7 == 4 )
    {
      return *(unsigned int *)lpData;
    }
  }
  return Data;
}

```

## disassembly

```asm
0x18000315c  mov     r11, rsp
0x18000315f  mov     [r11+8], rbx
0x180003163  push    rdi
0x180003164  sub     rsp, 40h
0x180003168  mov     rdi, rdx
0x18000316b  mov     rbx, rcx
0x18000316e  xor     eax, eax
0x180003170  test    rdx, rdx
0x180003173  jz      loc_1800031FD
0x180003179  test    rcx, rcx
0x18000317c  jz      short loc_1800031FD
0x18000317e  mov     [r11+10h], r8d
0x180003182  mov     [rsp+48h+var_18], eax
0x180003186  mov     [rsp+48h+arg_18], eax
0x18000318a  mov     dword ptr [rsp+48h+var_14], eax
0x18000318e  mov     [rsp+48h+arg_18], 4
0x180003196  lea     rax, [r11+20h]
0x18000319a  mov     [r11-20h], rax
0x18000319e  lea     rax, [r11-14h]
0x1800031a2  mov     [r11-28h], rax
0x1800031a6  lea     r9, [r11-18h]; lpType
0x1800031aa  xor     r8d, r8d; lpReserved
0x1800031ad  call    cs:__imp_RegQueryValueExW
0x1800031b3  test    eax, 0FFFFFFFDh
0x1800031b8  jnz     short loc_1800031F7
0x1800031ba  cmp     eax, 2
0x1800031bd  jnz     short loc_1800031E8
0x1800031bf  mov     [rsp+48h+cbData], 4; cbData
0x1800031c7  lea     rax, [rsp+48h+Data]
0x1800031cc  mov     [rsp+48h+lpData], rax; lpData
0x1800031d1  mov     r9d, 4; dwType
0x1800031d7  xor     r8d, r8d; Reserved
0x1800031da  mov     rdx, rdi; lpValueName
0x1800031dd  mov     rcx, rbx; hKey
0x1800031e0  call    cs:__imp_RegSetValueExW
0x1800031e6  jmp     short loc_1800031F7
0x1800031e8  cmp     [rsp+48h+var_18], 4
0x1800031ed  jnz     short loc_1800031F7
0x1800031ef  mov     eax, dword ptr [rsp+48h+var_14]
0x1800031f3  mov     [rsp+48h+Data], eax
0x1800031f7  mov     eax, [rsp+48h+Data]
0x1800031fb  jmp     short loc_180003200
0x1800031fd  mov     eax, r8d
0x180003200  mov     rbx, [rsp+48h+arg_0]
0x180003205  add     rsp, 40h
0x180003209  pop     rdi
0x18000320a  retn
0x18002a31a  push    rbp
0x18002a31c  sub     rsp, 30h
0x18002a320  mov     rbp, rdx
0x18002a323  add     rsp, 30h
0x18002a327  pop     rbp
0x18002a328  retn
```
