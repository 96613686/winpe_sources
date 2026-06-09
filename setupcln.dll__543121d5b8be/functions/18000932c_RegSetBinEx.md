# RegSetBinEx

- ea: `0x18000932c`
- end: `0x180009410`
- name: `RegSetBinEx`
- size: `228`
- prototype: `_BOOL8 __fastcall(HKEY, const WCHAR *, const WCHAR *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003080`
- `0x180009418`

## callees

- `0x18000932c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800093e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000938f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000938f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093c6`

## pseudocode

```c
_BOOL8 __fastcall RegSetBinEx(HKEY a1, const WCHAR *a2, const WCHAR *a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  BYTE *v8; // rdi
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  DWORD v12; // [rsp+90h] [rbp+8h] BYREF

  if ( a1 && (v8 = lpData) != 0 )
  {
    if ( a2 )
    {
      hKey = 0;
      v12 = 0;
      v9 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, &v12);
      if ( !v9 )
      {
        v9 = RegSetValueExW(hKey, a3, 0, a4, v8, cbData);
        RegCloseKey(hKey);
      }
    }
    else
    {
      v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
    }
    SetLastError(v9);
    return v9 == 0;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000932c  mov     r11, rsp
0x18000932f  push    rbx
0x180009330  push    rbp
0x180009331  push    rsi
0x180009332  push    rdi
0x180009333  sub     rsp, 68h
0x180009337  mov     esi, r9d
0x18000933a  mov     rbp, r8
0x18000933d  test    rcx, rcx
0x180009340  jz      loc_1800093FA
0x180009346  mov     rdi, [rsp+88h+lpData]
0x18000934e  test    rdi, rdi
0x180009351  jz      loc_1800093FA
0x180009357  xor     r8d, r8d; Reserved
0x18000935a  test    rdx, rdx
0x18000935d  jz      short loc_1800093CE
0x18000935f  lea     rax, [r11+8]
0x180009363  mov     [r11-38h], r8
0x180009367  mov     [r11-48h], rax
0x18000936b  lea     r9, Class; lpClass
0x180009372  lea     rax, [r11-38h]
0x180009376  mov     [r11+8], r8d
0x18000937a  mov     [r11-50h], rax
0x18000937e  mov     [r11-58h], r8
0x180009382  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18000938a  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x18000938f  call    cs:__imp_RegCreateKeyExW
0x180009395  mov     ebx, eax
0x180009397  test    eax, eax
0x180009399  jnz     short loc_1800093E9
0x18000939b  mov     eax, [rsp+88h+cbData]
0x1800093a2  mov     r9d, esi; dwType
0x1800093a5  mov     rcx, [rsp+88h+hKey]; hKey
0x1800093aa  xor     r8d, r8d; Reserved
0x1800093ad  mov     [rsp+88h+samDesired], eax; cbData
0x1800093b1  mov     rdx, rbp; lpValueName
0x1800093b4  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x1800093b9  call    cs:__imp_RegSetValueExW
0x1800093bf  mov     rcx, [rsp+88h+hKey]; hKey
0x1800093c4  mov     ebx, eax
0x1800093c6  call    cs:__imp_RegCloseKey
0x1800093cc  jmp     short loc_1800093E9
0x1800093ce  mov     eax, [rsp+88h+cbData]
0x1800093d5  mov     rdx, rbp; lpValueName
0x1800093d8  mov     [rsp+88h+samDesired], eax; cbData
0x1800093dc  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x1800093e1  call    cs:__imp_RegSetValueExW
0x1800093e7  mov     ebx, eax
0x1800093e9  mov     ecx, ebx; dwErrCode
0x1800093eb  call    cs:__imp_SetLastError
0x1800093f1  xor     eax, eax
0x1800093f3  test    ebx, ebx
0x1800093f5  setz    al
0x1800093f8  jmp     short loc_180009407
0x1800093fa  mov     ecx, 57h ; 'W'; dwErrCode
0x1800093ff  call    cs:__imp_SetLastError
0x180009405  xor     eax, eax
0x180009407  add     rsp, 68h
0x18000940b  pop     rdi
0x18000940c  pop     rsi
0x18000940d  pop     rbp
0x18000940e  pop     rbx
0x18000940f  retn
```
