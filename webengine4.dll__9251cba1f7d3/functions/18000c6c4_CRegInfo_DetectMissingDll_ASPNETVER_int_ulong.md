# CRegInfo::DetectMissingDll(ASPNETVER *,int *,ulong)

- ea: `0x18000c6c4`
- end: `0x18000c7f8`
- name: `?DetectMissingDll@CRegInfo@@CAJPEAVASPNETVER@@PEAHK@Z`
- size: `308`
- prototype: `__int64 __fastcall(struct ASPNETVER *this, int *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000c978`
- `0x18000d534`

## callees

- `0x18000c6c4`
- `0x18000d6c4`
- `0x18000d850`
- `0x180012b30`
- `0x18004d030`
- `0x18004d350`
- `0x18004d754`
- `0x18004f22c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c766`
- `KERNEL32!GetLastError` at `0x18000c766`
- `ADVAPI32!RegCloseKey` at `0x18000c7c9`
- `ADVAPI32!RegCloseKey` at `0x18000c7c9`
- `SHLWAPI!PathFileExistsW` at `0x18000c75c`
- `SHLWAPI!PathFileExistsW` at `0x18000c75c`

## string_xrefs

- `0x18000c73d`: `DllFullPath`

## pseudocode

```c
__int64 __fastcall CRegInfo::DetectMissingDll(struct ASPNETVER *this, int *a2, unsigned int a3)
{
  WCHAR *v4; // rbx
  unsigned int LastWin32Error; // edi
  unsigned int RegValue; // eax
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v12[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  *a2 = 1;
  v4 = 0;
  pszPath = 0;
  LastWin32Error = CRegInfo::OpenVersionKey(this, v11, 0x104u, &hKey, a3);
  if ( !LastWin32Error )
  {
    RegValue = CRegInfo::ReadRegValue(hKey, v11, L"DllFullPath", (unsigned __int16 **)&pszPath, 0);
    v4 = (WCHAR *)pszPath;
    LastWin32Error = RegValue;
    if ( !RegValue )
    {
      if ( PathFileExistsW(pszPath) )
      {
        *a2 = 0;
      }
      else if ( (unsigned __int16)GetLastError() != 2 )
      {
        LastWin32Error = GetLastWin32Error();
        if ( LastWin32Error )
          goto LABEL_10;
      }
      if ( *a2 )
      {
        ASPNETVER::ToString(this, v12, 260);
        XspLogEvent(0x8000040D);
      }
    }
  }
LABEL_10:
  MemFree(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18000c6c4  mov     [rsp-8+arg_10], rbx
0x18000c6c9  mov     [rsp-8+arg_18], rsi
0x18000c6ce  push    rbp
0x18000c6cf  push    rdi
0x18000c6d0  push    r14
0x18000c6d2  lea     rbp, [rsp-370h]
0x18000c6da  sub     rsp, 470h
0x18000c6e1  mov     rax, cs:__security_cookie
0x18000c6e8  xor     rax, rsp
0x18000c6eb  mov     [rbp+380h+var_20], rax
0x18000c6f2  and     [rsp+480h+hKey], 0
0x18000c6f8  lea     r9, [rsp+480h+hKey]; HKEY *
0x18000c6fd  mov     rsi, rdx
0x18000c700  mov     dword ptr [rdx], 1
0x18000c706  mov     [rsp+480h+var_460], r8d; int
0x18000c70b  lea     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x18000c710  xor     ebx, ebx
0x18000c712  mov     r8d, 104h; unsigned __int64
0x18000c718  mov     [rsp+480h+pszPath], rbx
0x18000c71d  mov     r14, rcx
0x18000c720  call    ?OpenVersionKey@CRegInfo@@SAJPEAVASPNETVER@@QEAG_KPEAPEAUHKEY__@@K@Z; CRegInfo::OpenVersionKey(ASPNETVER *,ushort * const,unsigned __int64,HKEY__ * *,ulong)
0x18000c725  mov     edi, eax
0x18000c727  test    eax, eax
0x18000c729  jnz     loc_18000C7B7
0x18000c72f  mov     rcx, [rsp+480h+hKey]; hKey
0x18000c734  lea     r9, [rsp+480h+pszPath]; unsigned __int16 **
0x18000c739  and     [rsp+480h+var_460], ebx
0x18000c73d  lea     r8, aDllfullpath; "DllFullPath"
0x18000c744  lea     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x18000c749  call    ?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z; CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)
0x18000c74e  mov     rbx, [rsp+480h+pszPath]
0x18000c753  mov     edi, eax
0x18000c755  test    eax, eax
0x18000c757  jnz     short loc_18000C7B7
0x18000c759  mov     rcx, rbx; pszPath
0x18000c75c  call    cs:__imp_PathFileExistsW
0x18000c762  test    eax, eax
0x18000c764  jnz     short loc_18000C77F
0x18000c766  call    cs:__imp_GetLastError
0x18000c76c  cmp     ax, 2
0x18000c770  jz      short loc_18000C782
0x18000c772  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000c777  mov     edi, eax
0x18000c779  test    eax, eax
0x18000c77b  jnz     short loc_18000C7B7
0x18000c77d  jmp     short loc_18000C782
0x18000c77f  and     dword ptr [rsi], 0
0x18000c782  cmp     dword ptr [rsi], 0
0x18000c785  jz      short loc_18000C7B7
0x18000c787  mov     r8d, 104h; int
0x18000c78d  lea     rdx, [rbp+380h+var_230]; unsigned __int16 *
0x18000c794  mov     rcx, r14; this
0x18000c797  call    ?ToString@ASPNETVER@@QEAAHPEAGH@Z; ASPNETVER::ToString(ushort *,int)
0x18000c79c  lea     r9, [rbp+380h+var_230]
0x18000c7a3  mov     r8, rbx
0x18000c7a6  lea     rdx, aSS_0; "%s^%s"
0x18000c7ad  mov     ecx, 8000040Dh; dwEventID
0x18000c7b2  call    XspLogEvent
0x18000c7b7  mov     rcx, rbx; lpMem
0x18000c7ba  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000c7bf  mov     rcx, [rsp+480h+hKey]; hKey
0x18000c7c4  test    rcx, rcx
0x18000c7c7  jz      short loc_18000C7CF
0x18000c7c9  call    cs:__imp_RegCloseKey
0x18000c7cf  mov     eax, edi
0x18000c7d1  mov     rcx, [rbp+380h+var_20]
0x18000c7d8  xor     rcx, rsp; StackCookie
0x18000c7db  call    __security_check_cookie
0x18000c7e0  lea     r11, [rsp+480h+var_10]
0x18000c7e8  mov     rbx, [r11+30h]
0x18000c7ec  mov     rsi, [r11+38h]
0x18000c7f0  mov     rsp, r11
0x18000c7f3  pop     r14
0x18000c7f5  pop     rdi
0x18000c7f6  pop     rbp
0x18000c7f7  retn
```
