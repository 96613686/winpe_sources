# IniRegOpenKeyW

- ea: `0x100401850`
- end: `0x100401968`
- name: `IniRegOpenKeyW`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x100401800`
- `0x1004366d0`

## callees

- `0x100401580`
- `0x1004015b0`
- `0x100401610`
- `0x100401850`
- `0x100401970`
- `0x100401a40`
- `0x100401b70`
- `0x100445f00`
- `0x100447360`
- `0x100448120`
- `0x100448270`
- `0x1004483d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100401917`
- `KERNEL32!HeapFree` at `0x10040193b`
- `KERNEL32!HeapFree` at `0x1004475a3`
- `KERNEL32!HeapFree` at `0x100401917`
- `KERNEL32!HeapFree` at `0x10040193b`
- `KERNEL32!HeapFree` at `0x1004475a3`
- `KERNEL32!GetProcessHeap` at `0x100401907`
- `KERNEL32!GetProcessHeap` at `0x10040192b`
- `KERNEL32!GetProcessHeap` at `0x100447593`
- `KERNEL32!GetProcessHeap` at `0x100401907`
- `KERNEL32!GetProcessHeap` at `0x10040192b`
- `KERNEL32!GetProcessHeap` at `0x100447593`
- `KERNEL32!GetPrivateProfileStringW` at `0x1004475e3`
- `KERNEL32!GetPrivateProfileStringW` at `0x1004475e3`
- `ADVAPI32!RegOpenKeyExW` at `0x100447514`
- `ADVAPI32!RegOpenKeyExW` at `0x100447665`
- `ADVAPI32!RegOpenKeyExW` at `0x100447514`
- `ADVAPI32!RegOpenKeyExW` at `0x100447665`

## pseudocode

```c
LSTATUS __fastcall IniRegOpenKeyW(HKEY a1, const WCHAR *a2, HKEY *a3)
{
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rax
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

  if ( dword_10049F370 )
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
          v4 = GetProcessHeap();
          HeapFree(v4, 0, Path);
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
  else if ( dword_10049F378 || (unsigned int)IsIniRegSetupInitialized() )
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
                   (&off_1004A18F0)[10 * ValueOverride + 2],
                   0,
                   0,
                   ReturnedString,
                   8u,
                   &word_1004D41B0) )
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
0x100401850  mov     [rsp+arg_10], r8
0x100401855  mov     [rsp+lpSubKey], rdx
0x10040185a  mov     [rsp+arg_0], rcx
0x10040185f  sub     rsp, 98h
0x100401866  mov     rax, cs:__security_cookie
0x10040186d  xor     rax, rsp
0x100401870  mov     [rsp+98h+var_18], rax
0x100401878  cmp     cs:dword_10049F370, 0
0x10040187f  jz      loc_1004474B3
0x100401885  cmp     [rsp+98h+lpSubKey], 0
0x10040188e  jz      loc_10044747A
0x100401894  mov     rax, [rsp+98h+lpSubKey]
0x10040189c  movzx   eax, word ptr [rax]
0x10040189f  test    eax, eax
0x1004018a1  jz      loc_10044747A
0x1004018a7  mov     rdx, [rsp+98h+lpSubKey]
0x1004018af  mov     rcx, [rsp+98h+arg_0]
0x1004018b7  call    IniRegMakePath
0x1004018bc  mov     [rsp+98h+var_58], rax
0x1004018c1  cmp     [rsp+98h+var_58], 0
0x1004018c7  jz      loc_100447495
0x1004018cd  xor     edx, edx
0x1004018cf  mov     rcx, [rsp+98h+var_58]
0x1004018d4  call    IniRegGetString
0x1004018d9  mov     [rsp+98h+lpMem], rax
0x1004018de  cmp     [rsp+98h+lpMem], 0
0x1004018e4  jz      loc_1004474A5
0x1004018ea  mov     rcx, [rsp+98h+lpMem]
0x1004018ef  call    IniRegIsNonExistingValue
0x1004018f4  test    eax, eax
0x1004018f6  jz      loc_10040204A
0x1004018fc  mov     [rsp+98h+var_64], 2
0x100401904  jmp     short loc_100401907
0x100401907  call    cs:__imp_GetProcessHeap
0x10040190d  mov     r8, [rsp+98h+lpMem]; lpMem
0x100401912  xor     edx, edx; dwFlags
0x100401914  mov     rcx, rax; hHeap
0x100401917  call    cs:__imp_HeapFree
0x10040191d  jmp     short loc_100401920
0x100401920  cmp     [rsp+98h+var_64], 0
0x100401925  jz      loc_100402058
0x10040192b  call    cs:__imp_GetProcessHeap
0x100401931  mov     r8, [rsp+98h+var_58]; lpMem
0x100401936  xor     edx, edx; dwFlags
0x100401938  mov     rcx, rax; hHeap
0x10040193b  call    cs:__imp_HeapFree
0x100401941  jmp     short loc_100401944
0x100401944  mov     ecx, [rsp+98h+var_64]
0x100401948  call    IniRegReturnErrorCode
0x10040194d  jmp     short loc_100401950
0x100401950  mov     rcx, [rsp+98h+var_18]
0x100401958  xor     rcx, rsp; StackCookie
0x10040195b  call    __security_check_cookie
0x100401960  add     rsp, 98h
0x100401967  retn
0x10040204a  mov     [rsp+98h+var_64], 0
0x100402052  jmp     loc_100401907
0x100402058  mov     rax, [rsp+98h+arg_10]
0x100402060  mov     rcx, [rsp+98h+var_58]
0x100402065  mov     [rax], rcx
0x100402068  jmp     loc_100401944
0x10044747a  mov     rdx, [rsp+98h+arg_10]
0x100447482  mov     rcx, [rsp+98h+arg_0]
0x10044748a  call    IniRegOpenExistingKeyW
0x10044748f  jmp     loc_100401950
0x100447495  mov     ecx, 8
0x10044749a  call    IniRegReturnErrorCode
0x10044749f  jmp     loc_100401950
0x1004474a5  mov     [rsp+98h+var_64], 8
0x1004474ad  jmp     loc_100401920
0x1004474b3  cmp     cs:dword_10049F378, 0
0x1004474ba  jnz     short loc_1004474C9
0x1004474bc  call    IsIniRegSetupInitialized
0x1004474c1  test    eax, eax
0x1004474c3  jz      loc_10044763F
0x1004474c9  lea     rdx, [rsp+98h+hKey]
0x1004474ce  mov     rcx, [rsp+98h+arg_0]
0x1004474d6  call    ConfRegCrackHandle
0x1004474db  cmp     [rsp+98h+var_30], 0
0x1004474e0  jz      short loc_1004474F1
0x1004474e2  mov     ecx, 2
0x1004474e7  call    IniRegReturnErrorCode
0x1004474ec  jmp     loc_100401950
0x1004474f1  mov     rax, [rsp+98h+arg_10]
0x1004474f9  mov     [rsp+98h+phkResult], rax; phkResult
0x1004474fe  mov     r9d, 0F003Fh; samDesired
0x100447504  xor     r8d, r8d; ulOptions
0x100447507  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x10044750f  mov     rcx, [rsp+98h+hKey]; hKey
0x100447514  call    cs:__imp_RegOpenKeyExW
0x10044751a  mov     [rsp+98h+var_68], eax
0x10044751e  cmp     [rsp+98h+var_68], 0
0x100447523  jz      short loc_100447552
0x100447525  mov     rdx, [rsp+98h+lpSubKey]
0x10044752d  mov     rcx, [rsp+98h+var_38]
0x100447532  call    ConfRegIsNewKeyVirtual
0x100447537  test    eax, eax
0x100447539  jz      short loc_100447552
0x10044753b  mov     rax, [rsp+98h+arg_10]
0x100447543  mov     qword ptr [rax], 0
0x10044754a  mov     [rsp+98h+var_68], 0
0x100447552  cmp     [rsp+98h+var_68], 0
0x100447557  jz      loc_100447608
0x10044755d  mov     rdx, [rsp+98h+lpSubKey]
0x100447565  mov     rcx, [rsp+98h+arg_0]
0x10044756d  call    IniRegMakePath
0x100447572  mov     [rsp+98h+var_48], rax
0x100447577  cmp     [rsp+98h+var_48], 0
0x10044757d  jz      loc_100447608
0x100447583  xor     edx, edx
0x100447585  mov     rcx, [rsp+98h+var_48]
0x10044758a  call    ConfRegFindValueOverride
0x10044758f  mov     [rsp+98h+var_60], eax
0x100447593  call    cs:__imp_GetProcessHeap
0x100447599  mov     r8, [rsp+98h+var_48]; lpMem
0x10044759e  xor     edx, edx; dwFlags
0x1004475a0  mov     rcx, rax; hHeap
0x1004475a3  call    cs:__imp_HeapFree
0x1004475a9  cmp     [rsp+98h+var_60], 0FFFFFFFFh
0x1004475ae  jz      short loc_100447608
0x1004475b0  movsxd  rax, [rsp+98h+var_60]
0x1004475b5  imul    rax, 50h ; 'P'
0x1004475b9  lea     rcx, off_1004A18F0; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1004475c0  lea     rdx, word_1004D41B0
0x1004475c7  mov     [rsp+98h+lpFileName], rdx; lpFileName
0x1004475cc  mov     dword ptr [rsp+98h+phkResult], 8; nSize
0x1004475d4  lea     r9, [rsp+98h+ReturnedString]; lpReturnedString
0x1004475d9  xor     r8d, r8d; lpDefault
0x1004475dc  xor     edx, edx; lpKeyName
0x1004475de  mov     rcx, [rcx+rax+20h]; lpAppName
0x1004475e3  call    cs:__imp_GetPrivateProfileStringW
0x1004475e9  test    eax, eax
0x1004475eb  jbe     short loc_100447608
0x1004475ed  mov     rax, [rsp+98h+arg_10]
0x1004475f5  mov     rcx, [rsp+98h+arg_0]
0x1004475fd  mov     [rax], rcx
0x100447600  mov     [rsp+98h+var_68], 0
0x100447608  cmp     [rsp+98h+var_68], 0
0x10044760d  jnz     short loc_100447630
0x10044760f  mov     r8, [rsp+98h+arg_10]
0x100447617  mov     rdx, [rsp+98h+lpSubKey]
0x10044761f  mov     rcx, [rsp+98h+arg_0]
0x100447627  call    WrapHKEYHandleW
0x10044762c  mov     [rsp+98h+var_68], eax
0x100447630  mov     ecx, [rsp+98h+var_68]
0x100447634  call    IniRegReturnErrorCode
0x100447639  jmp     loc_100401950
0x10044763f  mov     rax, [rsp+98h+arg_10]
0x100447647  mov     [rsp+98h+phkResult], rax; phkResult
0x10044764c  mov     r9d, 0F003Fh; samDesired
0x100447652  xor     r8d, r8d; ulOptions
0x100447655  mov     rdx, [rsp+98h+lpSubKey]; lpSubKey
0x10044765d  mov     rcx, [rsp+98h+arg_0]; hKey
0x100447665  call    cs:__imp_RegOpenKeyExW
0x10044766b  nop
0x10044766c  jmp     loc_100401950
```
