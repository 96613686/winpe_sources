# IniRegOpenKeyW

- ea: `0x10045c4b0`
- end: `0x10045c7b3`
- name: `IniRegOpenKeyW`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x10045c7c0`

## callees

- `0x10045ad90`
- `0x10045adf0`
- `0x10045b4f0`
- `0x10045baf0`
- `0x10045bea0`
- `0x10045c380`
- `0x10045c4b0`
- `0x10045cee0`
- `0x10045d030`
- `0x10045d190`
- `0x10045d220`
- `0x100486af0`

## import_xrefs

- `KERNEL32!GetPrivateProfileStringW` at `0x10045c715`
- `KERNEL32!GetPrivateProfileStringW` at `0x10045c715`
- `KERNEL32!HeapFree` at `0x10045c593`
- `KERNEL32!HeapFree` at `0x10045c5ba`
- `KERNEL32!HeapFree` at `0x10045c6d5`
- `KERNEL32!HeapFree` at `0x10045c593`
- `KERNEL32!HeapFree` at `0x10045c5ba`
- `KERNEL32!HeapFree` at `0x10045c6d5`
- `KERNEL32!GetProcessHeap` at `0x10045c583`
- `KERNEL32!GetProcessHeap` at `0x10045c5aa`
- `KERNEL32!GetProcessHeap` at `0x10045c6c5`
- `KERNEL32!GetProcessHeap` at `0x10045c583`
- `KERNEL32!GetProcessHeap` at `0x10045c5aa`
- `KERNEL32!GetProcessHeap` at `0x10045c6c5`
- `ADVAPI32!RegOpenKeyExW` at `0x10045c646`
- `ADVAPI32!RegOpenKeyExW` at `0x10045c795`
- `ADVAPI32!RegOpenKeyExW` at `0x10045c646`
- `ADVAPI32!RegOpenKeyExW` at `0x10045c795`

## pseudocode

```c
LSTATUS __fastcall IniRegOpenKeyW(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  unsigned int v7; // [rsp+30h] [rbp-68h]
  unsigned int v8; // [rsp+34h] [rbp-64h]
  int ValueOverride; // [rsp+38h] [rbp-60h]
  HKEY Path; // [rsp+40h] [rbp-58h]
  void *lpMem; // [rsp+48h] [rbp-50h]
  void *v12; // [rsp+50h] [rbp-48h]
  HKEY hKey[2]; // [rsp+58h] [rbp-40h] BYREF
  int v14; // [rsp+68h] [rbp-30h]
  WCHAR ReturnedString[8]; // [rsp+70h] [rbp-28h] BYREF

  if ( dword_100556D24 )
  {
    if ( a2 && *a2 )
    {
      Path = (HKEY)IniRegMakePath(a1, a2);
      if ( Path )
      {
        lpMem = (void *)IniRegGetString(Path, 0);
        if ( lpMem )
        {
          if ( (unsigned int)IniRegIsNonExistingValue(lpMem) )
            v8 = 2;
          else
            v8 = 0;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
        }
        else
        {
          v8 = 8;
        }
        if ( v8 )
        {
          v5 = GetProcessHeap();
          HeapFree(v5, 0, Path);
        }
        else
        {
          *a3 = Path;
        }
        return IniRegReturnErrorCode(v8);
      }
      else
      {
        return IniRegReturnErrorCode(8);
      }
    }
    else
    {
      return IniRegOpenExistingKeyW(a1, a3);
    }
  }
  else if ( dword_1005570AC || (unsigned int)IsIniRegSetupInitialized() )
  {
    ConfRegCrackHandle(a1, hKey);
    if ( v14 )
    {
      return IniRegReturnErrorCode(2);
    }
    else
    {
      v7 = RegOpenKeyExW(hKey[0], a2, 0, 0xF003Fu, a3);
      if ( v7 && (unsigned int)ConfRegIsNewKeyVirtual(hKey[1], a2) )
      {
        *a3 = 0;
        v7 = 0;
      }
      if ( v7 )
      {
        v12 = (void *)IniRegMakePath(a1, a2);
        if ( v12 )
        {
          ValueOverride = ConfRegFindValueOverride(v12, 0);
          v6 = GetProcessHeap();
          HeapFree(v6, 0, v12);
          if ( ValueOverride != -1 )
          {
            if ( GetPrivateProfileStringW(
                   (&off_10050DBE0)[10 * ValueOverride + 2],
                   0,
                   0,
                   ReturnedString,
                   8u,
                   &word_100557720) )
            {
              *a3 = a1;
              v7 = 0;
            }
          }
        }
      }
      if ( !v7 )
        v7 = WrapHKEYHandleW(a1, a2, a3);
      return IniRegReturnErrorCode(v7);
    }
  }
  else
  {
    return RegOpenKeyExW(a1, a2, 0, 0xF003Fu, a3);
  }
}

```

## disassembly

```asm
0x10045c4b0  mov     [rsp+arg_10], r8
0x10045c4b5  mov     [rsp+lpSubKey], rdx
0x10045c4ba  mov     [rsp+arg_0], rcx
0x10045c4bf  sub     rsp, 98h
0x10045c4c6  mov     rax, cs:__security_cookie
0x10045c4cd  xor     rax, rsp
0x10045c4d0  mov     [rsp+98h+var_18], rax
0x10045c4d8  cmp     cs:dword_100556D24, 0
0x10045c4df  jz      loc_10045C5E5
0x10045c4e5  cmp     [rsp+98h+lpSubKey], 0
0x10045c4ee  jz      short loc_10045C4FF
0x10045c4f0  mov     rax, [rsp+98h+lpSubKey]
0x10045c4f8  movzx   eax, word ptr [rax]
0x10045c4fb  test    eax, eax
0x10045c4fd  jnz     short loc_10045C519
0x10045c4ff  mov     rdx, [rsp+98h+arg_10]
0x10045c507  mov     rcx, [rsp+98h+arg_0]
0x10045c50f  call    IniRegOpenExistingKeyW
0x10045c514  jmp     loc_10045C79B
0x10045c519  mov     rdx, [rsp+98h+lpSubKey]
0x10045c521  mov     rcx, [rsp+98h+arg_0]
0x10045c529  call    IniRegMakePath
0x10045c52e  mov     [rsp+98h+var_58], rax
0x10045c533  cmp     [rsp+98h+var_58], 0
0x10045c539  jnz     short loc_10045C54A
0x10045c53b  mov     ecx, 8
0x10045c540  call    IniRegReturnErrorCode
0x10045c545  jmp     loc_10045C79B
0x10045c54a  xor     edx, edx
0x10045c54c  mov     rcx, [rsp+98h+var_58]
0x10045c551  call    IniRegGetString
0x10045c556  mov     [rsp+98h+lpMem], rax
0x10045c55b  cmp     [rsp+98h+lpMem], 0
0x10045c561  jz      short loc_10045C59B
0x10045c563  mov     rcx, [rsp+98h+lpMem]
0x10045c568  call    IniRegIsNonExistingValue
0x10045c56d  test    eax, eax
0x10045c56f  jz      short loc_10045C57B
0x10045c571  mov     [rsp+98h+var_64], 2
0x10045c579  jmp     short loc_10045C583
0x10045c57b  mov     [rsp+98h+var_64], 0
0x10045c583  call    cs:__imp_GetProcessHeap
0x10045c589  mov     r8, [rsp+98h+lpMem]; lpMem
0x10045c58e  xor     edx, edx; dwFlags
0x10045c590  mov     rcx, rax; hHeap
0x10045c593  call    cs:__imp_HeapFree
0x10045c599  jmp     short loc_10045C5A3
0x10045c59b  mov     [rsp+98h+var_64], 8
0x10045c5a3  cmp     [rsp+98h+var_64], 0
0x10045c5a8  jz      short loc_10045C5C2
0x10045c5aa  call    cs:__imp_GetProcessHeap
0x10045c5b0  mov     r8, [rsp+98h+var_58]; lpMem
0x10045c5b5  xor     edx, edx; dwFlags
0x10045c5b7  mov     rcx, rax; hHeap
0x10045c5ba  call    cs:__imp_HeapFree
0x10045c5c0  jmp     short loc_10045C5D2
0x10045c5c2  mov     rax, [rsp+98h+arg_10]
0x10045c5ca  mov     rcx, [rsp+98h+var_58]
0x10045c5cf  mov     [rax], rcx
0x10045c5d2  mov     ecx, [rsp+98h+var_64]
0x10045c5d6  call    IniRegReturnErrorCode
0x10045c5db  jmp     loc_10045C79B
0x10045c5e0  jmp     loc_10045C79B
0x10045c5e5  cmp     cs:dword_1005570AC, 0
0x10045c5ec  jnz     short loc_10045C5FB
0x10045c5ee  call    IsIniRegSetupInitialized
0x10045c5f3  test    eax, eax
0x10045c5f5  jz      loc_10045C76F
0x10045c5fb  lea     rdx, [rsp+98h+hKey]
0x10045c600  mov     rcx, [rsp+98h+arg_0]
0x10045c608  call    ConfRegCrackHandle
0x10045c60d  cmp     [rsp+98h+var_30], 0
0x10045c612  jz      short loc_10045C623
0x10045c614  mov     ecx, 2
0x10045c619  call    IniRegReturnErrorCode
0x10045c61e  jmp     loc_10045C79B
0x10045c623  mov     rax, [rsp+98h+arg_10]
0x10045c62b  mov     [rsp+98h+phkResult], rax; phkResult
0x10045c630  mov     r9d, 0F003Fh; samDesired
0x10045c636  xor     r8d, r8d; ulOptions
0x10045c639  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x10045c641  mov     rcx, [rsp+98h+hKey]; hKey
0x10045c646  call    cs:__imp_RegOpenKeyExW
0x10045c64c  mov     [rsp+98h+var_68], eax
0x10045c650  cmp     [rsp+98h+var_68], 0
0x10045c655  jz      short loc_10045C684
0x10045c657  mov     rdx, [rsp+98h+lpSubKey]
0x10045c65f  mov     rcx, [rsp+98h+var_38]
0x10045c664  call    ConfRegIsNewKeyVirtual
0x10045c669  test    eax, eax
0x10045c66b  jz      short loc_10045C684
0x10045c66d  mov     rax, [rsp+98h+arg_10]
0x10045c675  mov     qword ptr [rax], 0
0x10045c67c  mov     [rsp+98h+var_68], 0
0x10045c684  cmp     [rsp+98h+var_68], 0
0x10045c689  jz      loc_10045C73A
0x10045c68f  mov     rdx, [rsp+98h+lpSubKey]
0x10045c697  mov     rcx, [rsp+98h+arg_0]
0x10045c69f  call    IniRegMakePath
0x10045c6a4  mov     [rsp+98h+var_48], rax
0x10045c6a9  cmp     [rsp+98h+var_48], 0
0x10045c6af  jz      loc_10045C73A
0x10045c6b5  xor     edx, edx
0x10045c6b7  mov     rcx, [rsp+98h+var_48]
0x10045c6bc  call    ConfRegFindValueOverride
0x10045c6c1  mov     [rsp+98h+var_60], eax
0x10045c6c5  call    cs:__imp_GetProcessHeap
0x10045c6cb  mov     r8, [rsp+98h+var_48]; lpMem
0x10045c6d0  xor     edx, edx; dwFlags
0x10045c6d2  mov     rcx, rax; hHeap
0x10045c6d5  call    cs:__imp_HeapFree
0x10045c6db  cmp     [rsp+98h+var_60], 0FFFFFFFFh
0x10045c6e0  jz      short loc_10045C73A
0x10045c6e2  movsxd  rax, [rsp+98h+var_60]
0x10045c6e7  imul    rax, 50h ; 'P'
0x10045c6eb  lea     rcx, off_10050DBE0; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x10045c6f2  lea     rdx, word_100557720
0x10045c6f9  mov     [rsp+98h+lpFileName], rdx; lpFileName
0x10045c6fe  mov     dword ptr [rsp+98h+phkResult], 8; nSize
0x10045c706  lea     r9, [rsp+98h+ReturnedString]; lpReturnedString
0x10045c70b  xor     r8d, r8d; lpDefault
0x10045c70e  xor     edx, edx; lpKeyName
0x10045c710  mov     rcx, [rcx+rax+20h]; lpAppName
0x10045c715  call    cs:__imp_GetPrivateProfileStringW
0x10045c71b  test    eax, eax
0x10045c71d  jbe     short loc_10045C73A
0x10045c71f  mov     rax, [rsp+98h+arg_10]
0x10045c727  mov     rcx, [rsp+98h+arg_0]
0x10045c72f  mov     [rax], rcx
0x10045c732  mov     [rsp+98h+var_68], 0
0x10045c73a  cmp     [rsp+98h+var_68], 0
0x10045c73f  jnz     short loc_10045C762
0x10045c741  mov     r8, [rsp+98h+arg_10]
0x10045c749  mov     rdx, [rsp+98h+lpSubKey]
0x10045c751  mov     rcx, [rsp+98h+arg_0]
0x10045c759  call    WrapHKEYHandleW
0x10045c75e  mov     [rsp+98h+var_68], eax
0x10045c762  mov     ecx, [rsp+98h+var_68]
0x10045c766  call    IniRegReturnErrorCode
0x10045c76b  jmp     short loc_10045C79B
0x10045c76d  jmp     short loc_10045C79B
0x10045c76f  mov     rax, [rsp+98h+arg_10]
0x10045c777  mov     [rsp+98h+phkResult], rax; phkResult
0x10045c77c  mov     r9d, 0F003Fh; samDesired
0x10045c782  xor     r8d, r8d; ulOptions
0x10045c785  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x10045c78d  mov     rcx, [rsp+98h+arg_0]; hKey
0x10045c795  call    cs:__imp_RegOpenKeyExW
0x10045c79b  mov     rcx, [rsp+98h+var_18]
0x10045c7a3  xor     rcx, rsp; StackCookie
0x10045c7a6  call    __security_check_cookie
0x10045c7ab  add     rsp, 98h
0x10045c7b2  retn
```
