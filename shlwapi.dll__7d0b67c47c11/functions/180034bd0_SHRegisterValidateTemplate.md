# SHRegisterValidateTemplate

- ea: `0x180034bd0`
- end: `0x180034ccb`
- name: `SHRegisterValidateTemplate`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180012550`
- `0x180013066`
- `0x1800346e8`
- `0x180034738`
- `0x180034bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034c29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034c29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c42`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180034c42`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180034c6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180034c8a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180034c6d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180034c8a`

## pseudocode

```c
__int64 SHRegisterValidateTemplate()
{
  const unsigned __int16 *FileNameW; // rax
  unsigned int v1; // edx
  const struct _EVENT_DESCRIPTOR *v2; // rcx
  unsigned int v3; // r9d
  const unsigned __int16 *v4; // rax
  HMODULE phModule; // [rsp+20h] [rbp-E0h] BYREF
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[128]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v9[140]; // [rsp+B4h] [rbp-4Ch] BYREF
  WCHAR pszPath[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Filename[264]; // [rsp+350h] [rbp+250h] BYREF
  LPCWSTR retaddr; // [rsp+578h] [rbp+478h]

  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    phModule = 0;
    if ( GetModuleHandleExW(6u, retaddr, &phModule) && !GetModuleFileNameW(phModule, pszPath, 0x104u) )
      pszPath[0] = 0;
    v7 = 0;
    memset_0(v8, 0, 0x104u);
    FileNameW = PathFindFileNameW(Filename);
    SHTraceSQMCreateStringStreamEntry((struct _SHSQM_STREAM_ENTRY *)&v7, FileNameW);
    if ( pszPath[0] )
    {
      v4 = PathFindFileNameW(pszPath);
      SHTraceSQMCreateStringStreamEntry((struct _SHSQM_STREAM_ENTRY *)v9, v4);
    }
    SHTraceSQMStream(v2, v1, (struct _SHSQM_STREAM_ENTRY *)&v7, v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180034bd0  mov     [rsp-8+arg_0], rbx
0x180034bd5  push    rbp
0x180034bd6  lea     rbp, [rsp-470h]
0x180034bde  sub     rsp, 570h
0x180034be5  mov     rax, cs:__security_cookie
0x180034bec  xor     rax, rsp
0x180034bef  mov     [rbp+470h+var_10], rax
0x180034bf6  mov     r8d, 104h; nSize
0x180034bfc  lea     rdx, [rbp+470h+Filename]; lpFilename
0x180034c03  xor     ecx, ecx; hModule
0x180034c05  call    cs:__imp_GetModuleFileNameW
0x180034c0b  xor     ebx, ebx
0x180034c0d  test    eax, eax
0x180034c0f  jz      loc_180034CA6
0x180034c15  mov     rdx, [rbp+478h]; lpModuleName
0x180034c1c  lea     r8, [rsp+570h+phModule]; phModule
0x180034c21  lea     ecx, [rbx+6]; dwFlags
0x180034c24  mov     [rsp+570h+phModule], rbx
0x180034c29  call    cs:__imp_GetModuleHandleExW
0x180034c2f  test    eax, eax
0x180034c31  jz      short loc_180034C50
0x180034c33  mov     rcx, [rsp+570h+phModule]; hModule
0x180034c38  lea     rdx, [rbp+470h+pszPath]; lpFilename
0x180034c3c  mov     r8d, 104h; nSize
0x180034c42  call    cs:__imp_GetModuleFileNameW
0x180034c48  test    eax, eax
0x180034c4a  jnz     short loc_180034C50
0x180034c4c  mov     [rbp+470h+pszPath], bx
0x180034c50  xor     edx, edx; Val
0x180034c52  mov     [rsp+570h+var_540], ebx
0x180034c56  mov     r8d, 104h; Size
0x180034c5c  lea     rcx, [rsp+570h+var_53C]; void *
0x180034c61  call    memset_0
0x180034c66  lea     rcx, [rbp+470h+Filename]; pszPath
0x180034c6d  call    cs:__imp_PathFindFileNameW
0x180034c73  mov     rdx, rax; unsigned __int16 *
0x180034c76  lea     rcx, [rsp+570h+var_540]; struct _SHSQM_STREAM_ENTRY *
0x180034c7b  call    ?SHTraceSQMCreateStringStreamEntry@@YAXPEAU_SHSQM_STREAM_ENTRY@@PEBG@Z; SHTraceSQMCreateStringStreamEntry(_SHSQM_STREAM_ENTRY *,ushort const *)
0x180034c80  cmp     [rbp+470h+pszPath], bx
0x180034c84  jz      short loc_180034C9C
0x180034c86  lea     rcx, [rbp+470h+pszPath]; pszPath
0x180034c8a  call    cs:__imp_PathFindFileNameW
0x180034c90  mov     rdx, rax; unsigned __int16 *
0x180034c93  lea     rcx, [rbp+470h+var_4BC]; struct _SHSQM_STREAM_ENTRY *
0x180034c97  call    ?SHTraceSQMCreateStringStreamEntry@@YAXPEAU_SHSQM_STREAM_ENTRY@@PEBG@Z; SHTraceSQMCreateStringStreamEntry(_SHSQM_STREAM_ENTRY *,ushort const *)
0x180034c9c  lea     r8, [rsp+570h+var_540]; struct _SHSQM_STREAM_ENTRY *
0x180034ca1  call    ?SHTraceSQMStream@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_SHSQM_STREAM_ENTRY@@K@Z; SHTraceSQMStream(_EVENT_DESCRIPTOR const *,ulong,_SHSQM_STREAM_ENTRY *,ulong)
0x180034ca6  mov     eax, 1
0x180034cab  mov     rcx, [rbp+470h+var_10]
0x180034cb2  xor     rcx, rsp; StackCookie
0x180034cb5  call    __security_check_cookie
0x180034cba  mov     rbx, [rsp+570h+arg_0]
0x180034cc2  add     rsp, 570h
0x180034cc9  pop     rbp
0x180034cca  retn
```
