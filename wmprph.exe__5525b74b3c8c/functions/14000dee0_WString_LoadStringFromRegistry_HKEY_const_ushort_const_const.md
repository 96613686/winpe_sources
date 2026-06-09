# WString::LoadStringFromRegistry(HKEY__ * const,ushort const * const)

- ea: `0x14000dee0`
- end: `0x14000e042`
- name: `?LoadStringFromRegistry@WString@@QEAAJQEAUHKEY__@@QEBG@Z`
- size: `354`
- prototype: `__int64 __fastcall(WString *__hidden this, HKEY hKey, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140005c60`

## callees

- `0x14000d978`
- `0x14000da00`
- `0x14000dd98`
- `0x14000de4c`
- `0x14000dea0`
- `0x14000dee0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14000df42`
- `ADVAPI32!RegQueryValueExW` at `0x14000dfa4`
- `ADVAPI32!RegQueryValueExW` at `0x14000e001`
- `ADVAPI32!RegQueryValueExW` at `0x14000df42`
- `ADVAPI32!RegQueryValueExW` at `0x14000dfa4`
- `ADVAPI32!RegQueryValueExW` at `0x14000e001`

## pseudocode

```c
__int64 __fastcall WString::LoadStringFromRegistry(unsigned __int16 **this, HKEY hKey, const unsigned __int16 *a3)
{
  unsigned int v6; // edi
  unsigned int v7; // eax
  bool v8; // zf
  unsigned int v9; // ecx
  LSTATUS v10; // eax
  unsigned __int16 *lpData; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF
  const unsigned __int16 *cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD lpcbData; // [rsp+88h] [rbp+48h] BYREF

  cbData = a3;
  WString::DeleteString(this);
  if ( !hKey )
    return 2147942487LL;
  Type = 0;
  LODWORD(cbData) = 0;
  v6 = -2147024809;
  if ( !RegQueryValueExW(hKey, L"PerceivedType", 0, &Type, 0, (LPDWORD)&cbData) && (Type - 1 <= 1 || Type == 7) )
  {
    v7 = (unsigned int)cbData >> 1;
    v8 = (*((_BYTE *)this + 12) & 0x20) == 0;
    LODWORD(cbData) = (unsigned int)cbData >> 1;
    if ( !v8 )
    {
      v9 = *((_DWORD *)this + 2);
      if ( v7 >= v9 )
      {
        LODWORD(cbData) = *((_DWORD *)this + 2);
        v7 = v9;
      }
      lpcbData = 2 * v7;
      v10 = RegQueryValueExW(hKey, L"PerceivedType", 0, 0, (LPBYTE)*this, &lpcbData);
      if ( *((int *)this + 2) > 0 )
        (*this)[*((int *)this + 2) - 1] = 0;
      if ( v10 )
        return v6;
      goto LABEL_17;
    }
    lpData = WString::InternalAllocate((WString *)this, v7);
    if ( lpData )
    {
      lpcbData = 2 * (_DWORD)cbData;
      if ( !RegQueryValueExW(hKey, L"PerceivedType", 0, 0, (LPBYTE)lpData, &lpcbData) )
      {
        WString::InternalAttach((WString *)this, lpData);
LABEL_17:
        if ( Type == 2 )
          return (unsigned int)WString::ExpandEnvironmentStringsW(this);
        else
          return 0;
      }
      WString::InternalFree((WString *)this, &lpData);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14000dee0  mov     [rsp-28h+cbData], r8
0x14000dee5  push    rbp
0x14000dee6  push    rbx
0x14000dee7  push    rsi
0x14000dee8  push    rdi
0x14000dee9  push    r14
0x14000deeb  mov     rbp, rsp
0x14000deee  sub     rsp, 40h
0x14000def2  mov     r14, rdx
0x14000def5  mov     rbx, rcx
0x14000def8  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x14000defd  test    r14, r14
0x14000df00  jnz     short loc_14000DF0C
0x14000df02  mov     eax, 80070057h
0x14000df07  jmp     loc_14000E037
0x14000df0c  lea     rax, [rbp+cbData]
0x14000df10  mov     [rbp+Type], 0
0x14000df17  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14000df1c  lea     r9, [rbp+Type]; lpType
0x14000df20  xor     r8d, r8d; lpReserved
0x14000df23  mov     [rsp+40h+lpData], 0; lpData
0x14000df2c  lea     rdx, ValueName; "PerceivedType"
0x14000df33  mov     dword ptr [rbp+cbData], 0
0x14000df3a  mov     rcx, r14; hKey
0x14000df3d  mov     edi, 80070057h
0x14000df42  call    cs:__imp_RegQueryValueExW
0x14000df48  test    eax, eax
0x14000df4a  jnz     loc_14000E035
0x14000df50  mov     ecx, [rbp+Type]
0x14000df53  lea     eax, [rcx-1]
0x14000df56  cmp     eax, 1
0x14000df59  jbe     short loc_14000DF64
0x14000df5b  cmp     ecx, 7
0x14000df5e  jnz     loc_14000E035
0x14000df64  mov     eax, dword ptr [rbp+cbData]
0x14000df67  shr     eax, 1
0x14000df69  test    byte ptr [rbx+0Ch], 20h
0x14000df6d  mov     dword ptr [rbp+cbData], eax
0x14000df70  jz      short loc_14000DFC5
0x14000df72  mov     ecx, [rbx+8]
0x14000df75  cmp     eax, ecx
0x14000df77  jb      short loc_14000DF7E
0x14000df79  mov     dword ptr [rbp+cbData], ecx
0x14000df7c  mov     eax, ecx
0x14000df7e  add     eax, eax
0x14000df80  lea     rdx, ValueName; "PerceivedType"
0x14000df87  mov     [rbp+arg_18], eax
0x14000df8a  xor     r9d, r9d; lpType
0x14000df8d  lea     rax, [rbp+arg_18]
0x14000df91  xor     r8d, r8d; lpReserved
0x14000df94  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14000df99  mov     rcx, r14; hKey
0x14000df9c  mov     rax, [rbx]
0x14000df9f  mov     [rsp+40h+lpData], rax; lpData
0x14000dfa4  call    cs:__imp_RegQueryValueExW
0x14000dfaa  cmp     dword ptr [rbx+8], 0
0x14000dfae  jle     short loc_14000DFBF
0x14000dfb0  movsxd  r8, dword ptr [rbx+8]
0x14000dfb4  xor     ecx, ecx
0x14000dfb6  mov     rdx, [rbx]
0x14000dfb9  mov     [rdx+r8*2-2], cx
0x14000dfbf  test    eax, eax
0x14000dfc1  jnz     short loc_14000E035
0x14000dfc3  jmp     short loc_14000E021
0x14000dfc5  mov     edx, eax; int
0x14000dfc7  mov     rcx, rbx; this
0x14000dfca  call    ?InternalAllocate@WString@@IEBAPEAGH@Z; WString::InternalAllocate(int)
0x14000dfcf  mov     [rbp+var_10], rax
0x14000dfd3  mov     rsi, rax
0x14000dfd6  test    rax, rax
0x14000dfd9  jz      short loc_14000E035
0x14000dfdb  mov     eax, dword ptr [rbp+cbData]
0x14000dfde  lea     rdx, ValueName; "PerceivedType"
0x14000dfe5  add     eax, eax
0x14000dfe7  xor     r9d, r9d; lpType
0x14000dfea  mov     [rbp+arg_18], eax
0x14000dfed  xor     r8d, r8d; lpReserved
0x14000dff0  lea     rax, [rbp+arg_18]
0x14000dff4  mov     rcx, r14; hKey
0x14000dff7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14000dffc  mov     [rsp+40h+lpData], rsi; lpData
0x14000e001  call    cs:__imp_RegQueryValueExW
0x14000e007  mov     rcx, rbx; this
0x14000e00a  test    eax, eax
0x14000e00c  jz      short loc_14000E019
0x14000e00e  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x14000e012  call    ?InternalFree@WString@@IEBAXAEAPEAG@Z; WString::InternalFree(ushort * &)
0x14000e017  jmp     short loc_14000E035
0x14000e019  mov     rdx, rsi; unsigned __int16 *
0x14000e01c  call    ?InternalAttach@WString@@IEAAXPEAG@Z; WString::InternalAttach(ushort *)
0x14000e021  cmp     [rbp+Type], 2
0x14000e025  jz      short loc_14000E02B
0x14000e027  xor     edi, edi
0x14000e029  jmp     short loc_14000E035
0x14000e02b  mov     rcx, rbx; this
0x14000e02e  call    ?ExpandEnvironmentStringsW@WString@@QEAAJXZ; WString::ExpandEnvironmentStringsW(void)
0x14000e033  mov     edi, eax
0x14000e035  mov     eax, edi
0x14000e037  add     rsp, 40h
0x14000e03b  pop     r14
0x14000e03d  pop     rdi
0x14000e03e  pop     rsi
0x14000e03f  pop     rbx
0x14000e040  pop     rbp
0x14000e041  retn
```
