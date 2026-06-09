# CheckEduRestartPolicyEnabled(bool *)

- ea: `0x18000e884`
- end: `0x18000e965`
- name: `?CheckEduRestartPolicyEnabled@@YAJPEA_N@Z`
- size: `225`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000d040`

## callees

- `0x18000e884`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e944`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e944`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e8aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e8aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8e6`

## string_xrefs

- `0x18000e896`: `UpdatePolicy.dll`
- `0x18000e8ce`: `ReadPolicyWithFallback`

## pseudocode

```c
__int64 __fastcall CheckEduRestartPolicyEnabled(bool *a1)
{
  int v2; // edi
  HMODULE Library; // rbx
  signed int LastError; // eax
  bool v5; // sf
  FARPROC ProcAddress; // rsi
  signed int v7; // eax
  bool v8; // sf
  __int64 v9; // rcx
  FARPROC v10; // rax
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = 0;
  v12 = 0;
  Library = LoadLibraryExW(L"UpdatePolicy.dll", 0, 0x800u);
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError > 0 )
      v5 = 1;
    if ( v5 )
      goto LABEL_13;
  }
  ProcAddress = GetProcAddress(Library, "ReadPolicyWithFallback");
  if ( !ProcAddress )
  {
    v7 = GetLastError();
    v8 = v7 < 0;
    if ( v7 > 0 )
      v8 = 1;
    if ( v8 )
      goto LABEL_13;
  }
  v2 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(40, &v12);
  if ( v2 < 0 )
  {
LABEL_13:
    v9 = v12;
  }
  else
  {
    v9 = v12;
    if ( *(_DWORD *)(v12 + 4) == 1 && *(_DWORD *)(v12 + 24) == 1 )
      *a1 = 1;
  }
  if ( v9 )
  {
    if ( Library )
    {
      v10 = GetProcAddress(Library, "ReleaseEnterprisePolicyValue");
      if ( v10 )
        ((void (__fastcall *)(__int64 *))v10)(&v12);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e884  push    rbx
0x18000e886  push    rsi
0x18000e887  push    rdi
0x18000e888  push    r14
0x18000e88a  sub     rsp, 28h
0x18000e88e  mov     r14, rcx
0x18000e891  mov     byte ptr [rcx], 0
0x18000e894  xor     edi, edi
0x18000e896  lea     rcx, LibFileName; "UpdatePolicy.dll"
0x18000e89d  xor     edx, edx; hFile
0x18000e89f  mov     [rsp+48h+arg_0], rdi
0x18000e8a4  mov     r8d, 800h; dwFlags
0x18000e8aa  call    cs:__imp_LoadLibraryExW
0x18000e8b0  mov     rbx, rax
0x18000e8b3  test    rax, rax
0x18000e8b6  jnz     short loc_18000E8CE
0x18000e8b8  call    cs:__imp_GetLastError
0x18000e8be  test    eax, eax
0x18000e8c0  jle     short loc_18000E8CC
0x18000e8c2  movzx   eax, ax
0x18000e8c5  or      eax, 80070000h
0x18000e8ca  test    eax, eax
0x18000e8cc  js      short loc_18000E92B
0x18000e8ce  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x18000e8d5  mov     rcx, rbx; hModule
0x18000e8d8  call    cs:__imp_GetProcAddress
0x18000e8de  mov     rsi, rax
0x18000e8e1  test    rax, rax
0x18000e8e4  jnz     short loc_18000E8FC
0x18000e8e6  call    cs:__imp_GetLastError
0x18000e8ec  test    eax, eax
0x18000e8ee  jle     short loc_18000E8FA
0x18000e8f0  movzx   eax, ax
0x18000e8f3  or      eax, 80070000h
0x18000e8f8  test    eax, eax
0x18000e8fa  js      short loc_18000E92B
0x18000e8fc  lea     rdx, [rsp+48h+arg_0]
0x18000e901  mov     ecx, 28h ; '('
0x18000e906  mov     rax, rsi
0x18000e909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90e  mov     edi, eax
0x18000e910  test    eax, eax
0x18000e912  js      short loc_18000E92B
0x18000e914  mov     rcx, [rsp+48h+arg_0]
0x18000e919  cmp     dword ptr [rcx+4], 1
0x18000e91d  jnz     short loc_18000E930
0x18000e91f  cmp     dword ptr [rcx+18h], 1
0x18000e923  jnz     short loc_18000E930
0x18000e925  mov     byte ptr [r14], 1
0x18000e929  jmp     short loc_18000E930
0x18000e92b  mov     rcx, [rsp+48h+arg_0]
0x18000e930  test    rcx, rcx
0x18000e933  jz      short loc_18000E959
0x18000e935  test    rbx, rbx
0x18000e938  jz      short loc_18000E959
0x18000e93a  lea     rdx, aReleaseenterpr; "ReleaseEnterprisePolicyValue"
0x18000e941  mov     rcx, rbx; hModule
0x18000e944  call    cs:__imp_GetProcAddress
0x18000e94a  test    rax, rax
0x18000e94d  jz      short loc_18000E959
0x18000e94f  lea     rcx, [rsp+48h+arg_0]
0x18000e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e959  mov     eax, edi
0x18000e95b  add     rsp, 28h
0x18000e95f  pop     r14
0x18000e961  pop     rdi
0x18000e962  pop     rsi
0x18000e963  pop     rbx
0x18000e964  retn
```
