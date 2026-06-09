# ShowRebaseUpdateDialog(void)

- ea: `0x1400144e0`
- end: `0x1400145ac`
- name: `?ShowRebaseUpdateDialog@@YAJXZ`
- size: `204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x140013490`
- `0x1400144e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140014513`
- `KERNEL32!GetLastError` at `0x140014577`
- `KERNEL32!GetLastError` at `0x140014513`
- `KERNEL32!GetLastError` at `0x140014577`
- `USER32!DialogBoxParamW` at `0x14001456b`
- `USER32!DialogBoxParamW` at `0x14001456b`
- `COMCTL32!InitCommonControlsEx` at `0x140014509`
- `COMCTL32!InitCommonControlsEx` at `0x140014509`

## string_xrefs

- `0x140014528`: `InitCommonControls failed for ICC_LINK_CLASS`
- `0x140014536`: `ShowRebaseUpdateDialog`
- `0x14001458c`: `Failed to show rebase update dialog`

## pseudocode

```c
__int64 ShowRebaseUpdateDialog(void)
{
  unsigned int v0; // ebx
  signed int v1; // eax
  const char *v2; // r8
  __int64 v3; // rdx
  signed int LastError; // eax
  INITCOMMONCONTROLSEX picce; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  if ( !dword_140020188 )
  {
    picce.dwSize = 8;
    picce.dwICC = 0x8000;
    if ( InitCommonControlsEx(&picce) )
    {
      if ( DialogBoxParamW(_Module, (LPCWSTR)0x6A, hWndParent, RebaseUpdateDialogProc, 0) != -1 )
      {
        dword_140020218 = 1;
        return v0;
      }
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v2 = "Failed to show rebase update dialog";
      v3 = 609;
    }
    else
    {
      v1 = GetLastError();
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      v2 = "InitCommonControls failed for ICC_LINK_CLASS";
      v3 = 603;
    }
    if ( (v0 & 0x80000000) == 0 )
      v0 = -2147467259;
    WusaLogDebugEventA(L"ShowRebaseUpdateDialog", v3, v2);
  }
  return v0;
}

```

## disassembly

```asm
0x1400144e0  push    rbx
0x1400144e2  sub     rsp, 30h
0x1400144e6  xor     ebx, ebx
0x1400144e8  cmp     cs:dword_140020188, ebx
0x1400144ee  jnz     loc_1400145A4
0x1400144f4  lea     rcx, [rsp+38h+picce]; picce
0x1400144f9  mov     [rsp+38h+picce.dwSize], 8
0x140014501  mov     [rsp+38h+picce.dwICC], 8000h
0x140014509  call    cs:__imp_InitCommonControlsEx
0x14001450f  test    eax, eax
0x140014511  jnz     short loc_14001454C
0x140014513  call    cs:__imp_GetLastError
0x140014519  mov     ebx, eax
0x14001451b  test    eax, eax
0x14001451d  jle     short loc_140014528
0x14001451f  movzx   ebx, ax
0x140014522  or      ebx, 80070000h
0x140014528  lea     r8, aInitcommoncont; "InitCommonControls failed for ICC_LINK_"...
0x14001452f  mov     edx, 25Bh
0x140014534  test    ebx, ebx
0x140014536  lea     rcx, aShowrebaseupda; "ShowRebaseUpdateDialog"
0x14001453d  mov     eax, 80004005h
0x140014542  cmovns  ebx, eax
0x140014545  call    WusaLogDebugEventA
0x14001454a  jmp     short loc_1400145A4
0x14001454c  mov     r8, cs:hWndParent; hWndParent
0x140014553  lea     r9, ?RebaseUpdateDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x14001455a  mov     rcx, cs:?_Module@@3VAppModule@@A; hInstance
0x140014561  mov     edx, 6Ah ; 'j'; lpTemplateName
0x140014566  mov     [rsp+38h+dwInitParam], rbx; dwInitParam
0x14001456b  call    cs:__imp_DialogBoxParamW
0x140014571  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014575  jnz     short loc_14001459A
0x140014577  call    cs:__imp_GetLastError
0x14001457d  mov     ebx, eax
0x14001457f  test    eax, eax
0x140014581  jle     short loc_14001458C
0x140014583  movzx   ebx, ax
0x140014586  or      ebx, 80070000h
0x14001458c  lea     r8, aFailedToShowRe; "Failed to show rebase update dialog"
0x140014593  mov     edx, 261h
0x140014598  jmp     short loc_140014534
0x14001459a  mov     cs:dword_140020218, 1
0x1400145a4  mov     eax, ebx
0x1400145a6  add     rsp, 30h
0x1400145aa  pop     rbx
0x1400145ab  retn
```
