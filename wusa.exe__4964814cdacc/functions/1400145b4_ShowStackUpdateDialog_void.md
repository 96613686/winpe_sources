# ShowStackUpdateDialog(void)

- ea: `0x1400145b4`
- end: `0x140014680`
- name: `?ShowStackUpdateDialog@@YAJXZ`
- size: `204`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000c488`

## callees

- `0x140013490`
- `0x1400145b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400145e7`
- `KERNEL32!GetLastError` at `0x14001464b`
- `KERNEL32!GetLastError` at `0x1400145e7`
- `KERNEL32!GetLastError` at `0x14001464b`
- `USER32!DialogBoxParamW` at `0x14001463f`
- `USER32!DialogBoxParamW` at `0x14001463f`
- `COMCTL32!InitCommonControlsEx` at `0x1400145dd`
- `COMCTL32!InitCommonControlsEx` at `0x1400145dd`

## string_xrefs

- `0x1400145fc`: `InitCommonControls failed for ICC_LINK_CLASS`
- `0x14001460a`: `ShowStackUpdateDialog`
- `0x140014660`: `Failed to show stack update dialog`

## pseudocode

```c
__int64 ShowStackUpdateDialog(void)
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
      if ( DialogBoxParamW(_Module, (LPCWSTR)0x67, hWndParent, StackUpdateDialogProc, 0) != -1 )
      {
        dword_140020218 = 1;
        return v0;
      }
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      v2 = "Failed to show stack update dialog";
      v3 = 508;
    }
    else
    {
      v1 = GetLastError();
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      v2 = "InitCommonControls failed for ICC_LINK_CLASS";
      v3 = 502;
    }
    if ( (v0 & 0x80000000) == 0 )
      v0 = -2147467259;
    WusaLogDebugEventA(L"ShowStackUpdateDialog", v3, v2);
  }
  return v0;
}

```

## disassembly

```asm
0x1400145b4  push    rbx
0x1400145b6  sub     rsp, 30h
0x1400145ba  xor     ebx, ebx
0x1400145bc  cmp     cs:dword_140020188, ebx
0x1400145c2  jnz     loc_140014678
0x1400145c8  lea     rcx, [rsp+38h+picce]; picce
0x1400145cd  mov     [rsp+38h+picce.dwSize], 8
0x1400145d5  mov     [rsp+38h+picce.dwICC], 8000h
0x1400145dd  call    cs:__imp_InitCommonControlsEx
0x1400145e3  test    eax, eax
0x1400145e5  jnz     short loc_140014620
0x1400145e7  call    cs:__imp_GetLastError
0x1400145ed  mov     ebx, eax
0x1400145ef  test    eax, eax
0x1400145f1  jle     short loc_1400145FC
0x1400145f3  movzx   ebx, ax
0x1400145f6  or      ebx, 80070000h
0x1400145fc  lea     r8, aInitcommoncont; "InitCommonControls failed for ICC_LINK_"...
0x140014603  mov     edx, 1F6h
0x140014608  test    ebx, ebx
0x14001460a  lea     rcx, aShowstackupdat; "ShowStackUpdateDialog"
0x140014611  mov     eax, 80004005h
0x140014616  cmovns  ebx, eax
0x140014619  call    WusaLogDebugEventA
0x14001461e  jmp     short loc_140014678
0x140014620  mov     r8, cs:hWndParent; hWndParent
0x140014627  lea     r9, ?StackUpdateDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x14001462e  mov     rcx, cs:?_Module@@3VAppModule@@A; hInstance
0x140014635  mov     edx, 67h ; 'g'; lpTemplateName
0x14001463a  mov     [rsp+38h+dwInitParam], rbx; dwInitParam
0x14001463f  call    cs:__imp_DialogBoxParamW
0x140014645  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014649  jnz     short loc_14001466E
0x14001464b  call    cs:__imp_GetLastError
0x140014651  mov     ebx, eax
0x140014653  test    eax, eax
0x140014655  jle     short loc_140014660
0x140014657  movzx   ebx, ax
0x14001465a  or      ebx, 80070000h
0x140014660  lea     r8, aFailedToShowSt; "Failed to show stack update dialog"
0x140014667  mov     edx, 1FCh
0x14001466c  jmp     short loc_140014608
0x14001466e  mov     cs:dword_140020218, 1
0x140014678  mov     eax, ebx
0x14001467a  add     rsp, 30h
0x14001467e  pop     rbx
0x14001467f  retn
```
