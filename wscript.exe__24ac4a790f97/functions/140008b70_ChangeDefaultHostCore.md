# ChangeDefaultHostCore

- ea: `0x140008b70`
- end: `0x140008c68`
- name: `ChangeDefaultHostCore`
- size: `248`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008994`

## callees

- `0x140008b70`
- `0x1400097e4`
- `0x140009888`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x140008ba9`
- `ADVAPI32!RegOpenKeyExA` at `0x140008be2`
- `ADVAPI32!RegOpenKeyExA` at `0x140008ba9`
- `ADVAPI32!RegOpenKeyExA` at `0x140008be2`
- `ADVAPI32!RegCloseKey` at `0x140008bf3`
- `ADVAPI32!RegCloseKey` at `0x140008c40`
- `ADVAPI32!RegCloseKey` at `0x140008bf3`
- `ADVAPI32!RegCloseKey` at `0x140008c40`

## pseudocode

```c
__int64 __fastcall ChangeDefaultHostCore(LPCSTR lpSubKey, const BYTE *a2, int a3)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  __int64 v8; // r8
  LSTATUS v9; // eax
  int v10; // edi
  int v11; // eax
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  v6 = 0;
  v7 = RegOpenKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v7 )
  {
    if ( !a3 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
  }
  else
  {
    if ( !a3 )
      goto LABEL_8;
    phkResult = 0;
    v9 = RegOpenKeyExA(hKey, "ScriptEngine", 0, 0x20019u, &phkResult);
    v10 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v10 = -2147024896;
    }
    else
    {
      RegCloseKey(phkResult);
    }
    if ( v10 >= 0 )
    {
LABEL_8:
      v11 = RegSetKeyString(hKey, "Shell", v8, a2);
      v6 = v11;
      if ( v11 < 0 && (_WORD)v11 == 5 )
        v6 = SetDefaultHostForUser(lpSubKey, a2);
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x140008b70  mov     r11, rsp
0x140008b73  push    rbx
0x140008b74  push    rbp
0x140008b75  push    rsi
0x140008b76  push    rdi
0x140008b77  sub     rsp, 48h
0x140008b7b  mov     rsi, rdx
0x140008b7e  mov     qword ptr [r11+20h], 0
0x140008b86  mov     rdx, rcx; lpSubKey
0x140008b89  lea     rax, [r11+20h]
0x140008b8d  mov     edi, r8d
0x140008b90  mov     [r11-48h], rax
0x140008b94  mov     rbp, rcx
0x140008b97  mov     r9d, 2001Fh; samDesired
0x140008b9d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140008ba4  xor     r8d, r8d; ulOptions
0x140008ba7  xor     ebx, ebx
0x140008ba9  call    cs:__imp_RegOpenKeyExA
0x140008baf  test    eax, eax
0x140008bb1  jnz     loc_140008C48
0x140008bb7  test    edi, edi
0x140008bb9  jz      short loc_140008C08
0x140008bbb  mov     rcx, [rsp+68h+hKey]; hKey
0x140008bc3  lea     rax, [rsp+68h+var_38]
0x140008bc8  mov     r9d, 20019h; samDesired
0x140008bce  mov     [rsp+68h+phkResult], rax; phkResult
0x140008bd3  xor     r8d, r8d; ulOptions
0x140008bd6  mov     [rsp+68h+var_38], rbx
0x140008bdb  lea     rdx, aScriptengine_0; "ScriptEngine"
0x140008be2  call    cs:__imp_RegOpenKeyExA
0x140008be8  mov     edi, eax
0x140008bea  test    eax, eax
0x140008bec  jnz     short loc_140008BFB
0x140008bee  mov     rcx, [rsp+68h+var_38]; hKey
0x140008bf3  call    cs:__imp_RegCloseKey
0x140008bf9  jmp     short loc_140008C02
0x140008bfb  jle     short loc_140008C02
0x140008bfd  mov     edi, 80070000h
0x140008c02  not     edi
0x140008c04  test    edi, edi
0x140008c06  jns     short loc_140008C38
0x140008c08  mov     rcx, [rsp+68h+hKey]
0x140008c10  lea     rdx, aShell; "Shell"
0x140008c17  mov     r9, rsi
0x140008c1a  call    RegSetKeyString
0x140008c1f  mov     ebx, eax
0x140008c21  test    eax, eax
0x140008c23  jns     short loc_140008C38
0x140008c25  cmp     ax, 5
0x140008c29  jnz     short loc_140008C38
0x140008c2b  mov     rdx, rsi
0x140008c2e  mov     rcx, rbp
0x140008c31  call    SetDefaultHostForUser
0x140008c36  mov     ebx, eax
0x140008c38  mov     rcx, [rsp+68h+hKey]; hKey
0x140008c40  call    cs:__imp_RegCloseKey
0x140008c46  jmp     short loc_140008C5D
0x140008c48  test    edi, edi
0x140008c4a  jnz     short loc_140008C5D
0x140008c4c  test    eax, eax
0x140008c4e  jg      short loc_140008C54
0x140008c50  mov     ebx, eax
0x140008c52  jmp     short loc_140008C5D
0x140008c54  movzx   ebx, ax
0x140008c57  or      ebx, 80070000h
0x140008c5d  mov     eax, ebx
0x140008c5f  add     rsp, 48h
0x140008c63  pop     rdi
0x140008c64  pop     rsi
0x140008c65  pop     rbp
0x140008c66  pop     rbx
0x140008c67  retn
```
