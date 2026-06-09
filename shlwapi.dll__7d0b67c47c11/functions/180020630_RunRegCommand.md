# RunRegCommand

- ea: `0x180020630`
- end: `0x18002073c`
- name: `RunRegCommand`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800205a0`

## callees

- `0x18000eaf0`
- `0x180012550`
- `0x180013066`
- `0x18001ee10`
- `0x180020630`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x1800206f5`
- `SHELL32!ShellExecuteExW` at `0x1800206f5`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x1800206a3`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x1800206a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002070f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002071a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002070f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002071a`

## pseudocode

```c
__int64 __fastcall RunRegCommand(HWND a1, HKEY a2, const unsigned __int16 *a3)
{
  HRESULT Error; // ebx
  unsigned int v6; // [rsp+20h] [rbp-E0h]
  PWSTR ppszApplication; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszParameters; // [rsp+38h] [rbp-C8h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszCmdTemplate[1024]; // [rsp+B0h] [rbp-50h] BYREF

  Error = -2147467259;
  if ( (unsigned int)Reg_GetCommand(a2, a3, &psz, pszCmdTemplate, v6) )
  {
    ppszParameters = 0;
    ppszApplication = 0;
    Error = SHEvaluateSystemCommandTemplate(pszCmdTemplate, &ppszApplication, 0, &ppszParameters);
    if ( Error >= 0 )
    {
      pExecInfo.cbSize = 112;
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.lpFile = ppszApplication;
      pExecInfo.lpParameters = ppszParameters;
      pExecInfo.hwnd = a1;
      pExecInfo.nShow = 1;
      pExecInfo.fMask = 0x4000000;
      if ( ShellExecuteExW(&pExecInfo) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      CoTaskMemFree(ppszApplication);
      CoTaskMemFree(ppszParameters);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180020630  push    rbp
0x180020632  push    rbx
0x180020633  push    rdi
0x180020634  lea     rbp, [rsp-7C0h]
0x18002063c  sub     rsp, 8C0h
0x180020643  mov     rax, cs:__security_cookie
0x18002064a  xor     rax, rsp
0x18002064d  mov     [rbp+7D0h+var_20], rax
0x180020654  mov     r10, r8
0x180020657  lea     r9, [rbp+7D0h+pszCmdTemplate]; unsigned __int16 *
0x18002065b  mov     rax, rdx
0x18002065e  lea     r8, psz; unsigned __int16 *
0x180020665  mov     rdi, rcx
0x180020668  mov     rdx, r10; unsigned __int16 *
0x18002066b  mov     rcx, rax; HKEY
0x18002066e  mov     ebx, 80004005h
0x180020673  call    ?Reg_GetCommand@@YAHPEAUHKEY__@@PEBG1PEAGK@Z; Reg_GetCommand(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180020678  test    eax, eax
0x18002067a  jz      loc_180020720
0x180020680  lea     r9, [rsp+8D0h+ppszParameters]; ppszParameters
0x180020685  mov     [rsp+8D0h+ppszParameters], 0
0x18002068e  xor     r8d, r8d; ppszCommandLine
0x180020691  mov     [rsp+8D0h+ppszApplication], 0
0x18002069a  lea     rdx, [rsp+8D0h+ppszApplication]; ppszApplication
0x18002069f  lea     rcx, [rbp+7D0h+pszCmdTemplate]; pszCmdTemplate
0x1800206a3  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1800206a9  mov     ebx, eax
0x1800206ab  test    eax, eax
0x1800206ad  js      short loc_180020720
0x1800206af  xor     edx, edx; Val
0x1800206b1  mov     [rsp+8D0h+pExecInfo.cbSize], 70h ; 'p'
0x1800206b9  lea     rcx, [rsp+8D0h+pExecInfo.fMask]; void *
0x1800206be  lea     r8d, [rdx+6Ch]; Size
0x1800206c2  call    memset_0
0x1800206c7  mov     rax, [rsp+8D0h+ppszApplication]
0x1800206cc  lea     rcx, [rsp+8D0h+pExecInfo]; pExecInfo
0x1800206d1  mov     [rsp+8D0h+pExecInfo.lpFile], rax
0x1800206d6  mov     rax, [rsp+8D0h+ppszParameters]
0x1800206db  mov     [rsp+8D0h+pExecInfo.lpParameters], rax
0x1800206e0  mov     [rsp+8D0h+pExecInfo.hwnd], rdi
0x1800206e5  mov     [rsp+8D0h+pExecInfo.nShow], 1
0x1800206ed  mov     [rsp+8D0h+pExecInfo.fMask], 4000000h
0x1800206f5  call    cs:__imp_ShellExecuteExW
0x1800206fb  test    eax, eax
0x1800206fd  jz      short loc_180020703
0x1800206ff  xor     ebx, ebx
0x180020701  jmp     short loc_18002070A
0x180020703  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180020708  mov     ebx, eax
0x18002070a  mov     rcx, [rsp+8D0h+ppszApplication]; pv
0x18002070f  call    cs:__imp_CoTaskMemFree
0x180020715  mov     rcx, [rsp+8D0h+ppszParameters]; pv
0x18002071a  call    cs:__imp_CoTaskMemFree
0x180020720  mov     eax, ebx
0x180020722  mov     rcx, [rbp+7D0h+var_20]
0x180020729  xor     rcx, rsp; StackCookie
0x18002072c  call    __security_check_cookie
0x180020731  add     rsp, 8C0h
0x180020738  pop     rdi
0x180020739  pop     rbx
0x18002073a  pop     rbp
0x18002073b  retn
```
