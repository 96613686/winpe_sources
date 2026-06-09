# GetRegSettingsString(HKEY__ *,ushort const *,ushort *,ulong)

- ea: `0x140015910`
- end: `0x140015a76`
- name: `?GetRegSettingsString@@YAJPEAUHKEY__@@PEBGPEAGK@Z`
- size: `358`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008854`

## callees

- `0x140015910`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015a4b`
- `KERNEL32!GetLastError` at `0x140015a4b`
- `KERNEL32!MultiByteToWideChar` at `0x140015a3d`
- `KERNEL32!MultiByteToWideChar` at `0x140015a3d`
- `ADVAPI32!RegQueryValueExA` at `0x140015a06`
- `ADVAPI32!RegQueryValueExA` at `0x140015a06`
- `ADVAPI32!RegQueryValueExW` at `0x140015979`
- `ADVAPI32!RegQueryValueExW` at `0x140015979`

## pseudocode

```c
signed int __fastcall GetRegSettingsString(HKEY hKey, const unsigned __int16 *a2, BYTE *lpData, unsigned int a4)
{
  signed int result; // eax
  bool v8; // cc
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  DWORD cbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD Type; // [rsp+34h] [rbp+4h] BYREF

  Type = 0;
  if ( Global::g_fWindowsNT )
  {
    if ( 2 * (unsigned __int64)a4 <= 0xFFFFFFFF )
    {
      cbData = 2 * a4;
      result = RegQueryValueExW(hKey, 0, 0, &Type, lpData, &cbData);
      v8 = result <= 0;
      if ( result )
        goto LABEL_4;
      if ( Type - 1 <= 1 && !*(_WORD *)&lpData[2 * ((unsigned __int64)cbData >> 1) - 2] )
        return 0;
    }
    return -2147221165;
  }
  v9 = a4 + 1;
  v10 = v9 + 15;
  if ( v9 + 15 <= v9 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  cbData = v9;
  result = RegQueryValueExA(hKey, 0, 0, &Type, (LPBYTE)&cbData, &cbData);
  v8 = result <= 0;
  if ( result )
    goto LABEL_4;
  if ( Type - 1 > 1 || *((_BYTE *)&cbData + cbData - 1) )
    return -2147221165;
  if ( MultiByteToWideChar(0, 0, (LPCCH)&cbData, -1, (LPWSTR)lpData, a4) )
    return 0;
  result = GetLastError();
  v8 = result <= 0;
LABEL_4:
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140015910  push    rbp
0x140015912  push    rbx
0x140015913  push    rsi
0x140015914  push    rdi
0x140015915  push    r14
0x140015917  push    r15
0x140015919  sub     rsp, 48h
0x14001591d  lea     rbp, [rsp+30h]
0x140015922  mov     rax, cs:__security_cookie
0x140015929  xor     rax, rbp
0x14001592c  mov     [rbp+40h+var_38], rax
0x140015930  xor     r15d, r15d
0x140015933  mov     ebx, r9d
0x140015936  cmp     cs:?g_fWindowsNT@Global@@2_NA, r15b; bool Global::g_fWindowsNT
0x14001593d  mov     rdi, r8
0x140015940  mov     r14, rcx
0x140015943  mov     [rbp+40h+Type], r15d
0x140015947  jz      short loc_1400159BD
0x140015949  mov     eax, ebx
0x14001594b  mov     ecx, 0FFFFFFFFh
0x140015950  add     rax, rax
0x140015953  cmp     rax, rcx
0x140015956  ja      loc_140015A58
0x14001595c  mov     [rbp+40h+cbData], eax
0x14001595f  lea     r9, [rbp+40h+Type]; lpType
0x140015963  lea     rax, [rbp+40h+cbData]
0x140015967  xor     edx, edx; lpValueName
0x140015969  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14001596e  mov     rcx, r14; hKey
0x140015971  mov     [rsp+70h+lpData], r8; lpData
0x140015976  xor     r8d, r8d; lpReserved
0x140015979  call    cs:__imp_RegQueryValueExW
0x14001597f  test    eax, eax
0x140015981  jz      short loc_140015996
0x140015983  jle     loc_140015A5D
0x140015989  movzx   eax, ax
0x14001598c  or      eax, 80070000h
0x140015991  jmp     loc_140015A5D
0x140015996  mov     eax, [rbp+40h+Type]
0x140015999  dec     eax
0x14001599b  cmp     eax, 1
0x14001599e  ja      loc_140015A58
0x1400159a4  mov     eax, [rbp+40h+cbData]
0x1400159a7  shr     rax, 1
0x1400159aa  cmp     [rdi+rax*2-2], r15w
0x1400159b0  jnz     loc_140015A58
0x1400159b6  xor     eax, eax
0x1400159b8  jmp     loc_140015A5D
0x1400159bd  lea     edx, [rbx+1]
0x1400159c0  mov     eax, edx
0x1400159c2  lea     rcx, [rdx+0Fh]
0x1400159c6  cmp     rcx, rax
0x1400159c9  ja      short loc_1400159D5
0x1400159cb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1400159d5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400159d9  mov     rax, rcx
0x1400159dc  call    _alloca_probe
0x1400159e1  sub     rsp, rcx
0x1400159e4  mov     [rbp+40h+cbData], edx
0x1400159e7  lea     rax, [rbp+40h+cbData]
0x1400159eb  xor     r8d, r8d; lpReserved
0x1400159ee  lea     r9, [rbp+40h+Type]; lpType
0x1400159f2  xor     edx, edx; lpValueName
0x1400159f4  mov     rcx, r14; hKey
0x1400159f7  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1400159fc  lea     rsi, [rsp+70h+cbData]
0x140015a01  mov     [rsp+70h+lpData], rsi; lpData
0x140015a06  call    cs:__imp_RegQueryValueExA
0x140015a0c  test    eax, eax
0x140015a0e  jnz     loc_140015983
0x140015a14  mov     eax, [rbp+40h+Type]
0x140015a17  dec     eax
0x140015a19  cmp     eax, 1
0x140015a1c  ja      short loc_140015A58
0x140015a1e  mov     eax, [rbp+40h+cbData]
0x140015a21  dec     eax
0x140015a23  cmp     [rax+rsi], r15b
0x140015a27  jnz     short loc_140015A58
0x140015a29  mov     dword ptr [rsp+70h+lpcbData], ebx; cchWideChar
0x140015a2d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140015a31  mov     r8, rsi; lpMultiByteStr
0x140015a34  mov     [rsp+70h+lpData], rdi; lpWideCharStr
0x140015a39  xor     edx, edx; dwFlags
0x140015a3b  xor     ecx, ecx; CodePage
0x140015a3d  call    cs:__imp_MultiByteToWideChar
0x140015a43  test    eax, eax
0x140015a45  jnz     loc_1400159B6
0x140015a4b  call    cs:__imp_GetLastError
0x140015a51  test    eax, eax
0x140015a53  jmp     loc_140015983
0x140015a58  mov     eax, 80040153h
0x140015a5d  mov     rcx, [rbp+40h+var_38]
0x140015a61  xor     rcx, rbp; StackCookie
0x140015a64  call    __security_check_cookie
0x140015a69  lea     rsp, [rbp+18h]
0x140015a6d  pop     r15
0x140015a6f  pop     r14
0x140015a71  pop     rdi
0x140015a72  pop     rsi
0x140015a73  pop     rbx
0x140015a74  pop     rbp
0x140015a75  retn
```
