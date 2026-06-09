# EnsureDirectory(ushort const *)

- ea: `0x180073330`
- end: `0x1800733e7`
- name: `?EnsureDirectory@@YAJPEBG@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180018ab0`
- `0x18007dec0`
- `0x18007df9c`
- `0x18007e6fc`

## callees

- `0x1800068f0`
- `0x18006f180`
- `0x180073330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007334b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007334b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007333d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007333d`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18007339f`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18007339f`

## string_xrefs

- `0x18007336d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180073387`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800733c8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall EnsureDirectory(LPCWSTR pszPath)
{
  DWORD LastError; // ebx
  __int64 v3; // rcx
  int v5; // eax

  if ( !PathFileExistsW(pszPath) )
  {
    LastError = GetLastError();
    if ( LastError - 2 > 1 )
    {
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Log_UnistoreHREvent_0(
        LastError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        683);
      if ( !LastError )
        Log_AssertionEvent(
          v3,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          683);
      return LastError;
    }
    v5 = SHCreateDirectoryExW(0, pszPath, 0);
    LastError = v5;
    if ( v5 != 183 && v5 != 80 && v5 )
    {
      if ( v5 > 0 )
        LastError = (unsigned __int16)v5 | 0x80070000;
      Log_UnistoreHREvent_0(
        LastError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        691);
      return LastError;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180073330  mov     [rsp+arg_0], rbx
0x180073335  push    rdi
0x180073336  sub     rsp, 30h
0x18007333a  mov     rdi, rcx
0x18007333d  call    cs:__imp_PathFileExistsW
0x180073343  test    eax, eax
0x180073345  jnz     loc_1800733DA
0x18007334b  call    cs:__imp_GetLastError
0x180073351  mov     ebx, eax
0x180073353  add     eax, 0FFFFFFFEh
0x180073356  cmp     eax, 1
0x180073359  jbe     short loc_180073397
0x18007335b  test    ebx, ebx
0x18007335d  jle     short loc_180073368
0x18007335f  movzx   ebx, bx
0x180073362  or      ebx, 80070000h
0x180073368  mov     edi, 2ABh
0x18007336d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180073374  mov     r9d, edi
0x180073377  xor     edx, edx
0x180073379  mov     ecx, ebx
0x18007337b  call    Log_UnistoreHREvent_0
0x180073380  test    ebx, ebx
0x180073382  jnz     short loc_180073393
0x180073384  mov     r8d, edi
0x180073387  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007338e  call    Log_AssertionEvent
0x180073393  mov     eax, ebx
0x180073395  jmp     short loc_1800733DC
0x180073397  xor     r8d, r8d; psa
0x18007339a  mov     rdx, rdi; pszPath
0x18007339d  xor     ecx, ecx; hwnd
0x18007339f  call    cs:__imp_SHCreateDirectoryExW
0x1800733a5  mov     ebx, eax
0x1800733a7  cmp     eax, 0B7h
0x1800733ac  jz      short loc_1800733DA
0x1800733ae  cmp     eax, 50h ; 'P'
0x1800733b1  jz      short loc_1800733DA
0x1800733b3  test    eax, eax
0x1800733b5  jz      short loc_1800733DA
0x1800733b7  jle     short loc_1800733C2
0x1800733b9  movzx   ebx, ax
0x1800733bc  or      ebx, 80070000h
0x1800733c2  mov     r9d, 2B3h
0x1800733c8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800733cf  xor     edx, edx
0x1800733d1  mov     ecx, ebx
0x1800733d3  call    Log_UnistoreHREvent_0
0x1800733d8  jmp     short loc_180073393
0x1800733da  xor     eax, eax
0x1800733dc  mov     rbx, [rsp+38h+arg_0]
0x1800733e1  add     rsp, 30h
0x1800733e5  pop     rdi
0x1800733e6  retn
```
