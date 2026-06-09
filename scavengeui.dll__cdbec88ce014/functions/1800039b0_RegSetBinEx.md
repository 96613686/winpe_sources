# RegSetBinEx

- ea: `0x1800039b0`
- end: `0x180003a94`
- name: `RegSetBinEx`
- size: `228`
- prototype: `_BOOL8 __fastcall(HKEY, const WCHAR *, const WCHAR *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002360`

## callees

- `0x1800039b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180003a6f`
- `KERNEL32!SetLastError` at `0x180003a83`
- `KERNEL32!SetLastError` at `0x180003a6f`
- `KERNEL32!SetLastError` at `0x180003a83`
- `ADVAPI32!RegCloseKey` at `0x180003a4a`
- `ADVAPI32!RegCloseKey` at `0x180003a4a`
- `ADVAPI32!RegCreateKeyExW` at `0x180003a13`
- `ADVAPI32!RegCreateKeyExW` at `0x180003a13`
- `ADVAPI32!RegSetValueExW` at `0x180003a3d`
- `ADVAPI32!RegSetValueExW` at `0x180003a65`
- `ADVAPI32!RegSetValueExW` at `0x180003a3d`
- `ADVAPI32!RegSetValueExW` at `0x180003a65`

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
0x1800039b0  mov     r11, rsp
0x1800039b3  push    rbx
0x1800039b4  push    rbp
0x1800039b5  push    rsi
0x1800039b6  push    rdi
0x1800039b7  sub     rsp, 68h
0x1800039bb  mov     esi, r9d
0x1800039be  mov     rbp, r8
0x1800039c1  test    rcx, rcx
0x1800039c4  jz      loc_180003A7E
0x1800039ca  mov     rdi, [rsp+88h+lpData]
0x1800039d2  test    rdi, rdi
0x1800039d5  jz      loc_180003A7E
0x1800039db  xor     r8d, r8d; Reserved
0x1800039de  test    rdx, rdx
0x1800039e1  jz      short loc_180003A52
0x1800039e3  lea     rax, [r11+8]
0x1800039e7  mov     [r11-38h], r8
0x1800039eb  mov     [r11-48h], rax
0x1800039ef  lea     r9, Class; lpClass
0x1800039f6  lea     rax, [r11-38h]
0x1800039fa  mov     [r11+8], r8d
0x1800039fe  mov     [r11-50h], rax
0x180003a02  mov     [r11-58h], r8
0x180003a06  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180003a0e  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x180003a13  call    cs:__imp_RegCreateKeyExW
0x180003a19  mov     ebx, eax
0x180003a1b  test    eax, eax
0x180003a1d  jnz     short loc_180003A6D
0x180003a1f  mov     eax, [rsp+88h+cbData]
0x180003a26  mov     r9d, esi; dwType
0x180003a29  mov     rcx, [rsp+88h+hKey]; hKey
0x180003a2e  xor     r8d, r8d; Reserved
0x180003a31  mov     [rsp+88h+samDesired], eax; cbData
0x180003a35  mov     rdx, rbp; lpValueName
0x180003a38  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x180003a3d  call    cs:__imp_RegSetValueExW
0x180003a43  mov     rcx, [rsp+88h+hKey]; hKey
0x180003a48  mov     ebx, eax
0x180003a4a  call    cs:__imp_RegCloseKey
0x180003a50  jmp     short loc_180003A6D
0x180003a52  mov     eax, [rsp+88h+cbData]
0x180003a59  mov     rdx, rbp; lpValueName
0x180003a5c  mov     [rsp+88h+samDesired], eax; cbData
0x180003a60  mov     qword ptr [rsp+88h+dwOptions], rdi; lpData
0x180003a65  call    cs:__imp_RegSetValueExW
0x180003a6b  mov     ebx, eax
0x180003a6d  mov     ecx, ebx; dwErrCode
0x180003a6f  call    cs:__imp_SetLastError
0x180003a75  xor     eax, eax
0x180003a77  test    ebx, ebx
0x180003a79  setz    al
0x180003a7c  jmp     short loc_180003A8B
0x180003a7e  mov     ecx, 57h ; 'W'; dwErrCode
0x180003a83  call    cs:__imp_SetLastError
0x180003a89  xor     eax, eax
0x180003a8b  add     rsp, 68h
0x180003a8f  pop     rdi
0x180003a90  pop     rsi
0x180003a91  pop     rbp
0x180003a92  pop     rbx
0x180003a93  retn
```
