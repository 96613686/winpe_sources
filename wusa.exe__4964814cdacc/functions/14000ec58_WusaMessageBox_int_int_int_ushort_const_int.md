# WusaMessageBox(int,int,int,ushort const *,int *,...)

- ea: `0x14000ec58`
- end: `0x14000ee80`
- name: `?WusaMessageBox@@YAJHHHPEBGPEAHZZ`
- size: `552`
- prototype: `__int64(DWORD dwMessageId, DWORD, TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons, PCWSTR pszIcon, int *, ...)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005c70`
- `0x1400075b0`
- `0x14000a4bc`
- `0x14000afc0`
- `0x14000c488`
- `0x14000f8f0`
- `0x14000fdf8`

## callees

- `0x14000e280`
- `0x14000ec58`
- `0x140013490`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000ecb7`
- `KERNEL32!GetModuleHandleW` at `0x14000ed33`
- `KERNEL32!GetModuleHandleW` at `0x14000ecb7`
- `KERNEL32!GetModuleHandleW` at `0x14000ed33`
- `KERNEL32!LocalFree` at `0x14000ee0d`
- `KERNEL32!LocalFree` at `0x14000ee20`
- `KERNEL32!LocalFree` at `0x14000ee69`
- `KERNEL32!LocalFree` at `0x14000ee0d`
- `KERNEL32!LocalFree` at `0x14000ee20`
- `KERNEL32!LocalFree` at `0x14000ee69`
- `KERNEL32!GetLastError` at `0x14000ecf2`
- `KERNEL32!GetLastError` at `0x14000ed61`
- `KERNEL32!GetLastError` at `0x14000ecf2`
- `KERNEL32!GetLastError` at `0x14000ed61`
- `KERNEL32!FormatMessageW` at `0x14000ece4`
- `KERNEL32!FormatMessageW` at `0x14000ed57`
- `KERNEL32!FormatMessageW` at `0x14000ece4`
- `KERNEL32!FormatMessageW` at `0x14000ed57`
- `msvcrt!wcsrchr` at `0x14000ed89`
- `msvcrt!wcsrchr` at `0x14000ed89`
- `COMCTL32!__imp_TaskDialog` at `0x14000edc4`
- `COMCTL32!__imp_TaskDialog` at `0x14000edc4`

## string_xrefs

- `0x14000edd0`: `Failed: TaskDialog()`

## pseudocode

```c
__int64 WusaMessageBox(
        DWORD dwMessageId,
        DWORD a2,
        TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons,
        PCWSTR pszIcon,
        int *pnButton,
        ...)
{
  signed int v9; // ebx
  HMODULE ModuleHandleW; // rax
  DWORD v11; // eax
  signed int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  HMODULE v15; // rax
  signed int LastError; // eax
  wchar_t *v17; // rax
  HLOCAL v18; // rdi
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-20h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-18h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-8h] BYREF
  va_list va; // [rsp+C8h] [rbp+68h] BYREF

  va_start(va, pnButton);
  Arguments = 0;
  *(_QWORD *)Buffer = 0;
  v9 = 0;
  *(_QWORD *)lpBuffer = 0;
  if ( dword_140020188 || dword_140020218 || dword_14002021C )
    return (unsigned int)v9;
  va_copy(Arguments, va);
  ModuleHandleW = GetModuleHandleW(0);
  v11 = FormatMessageW(0x900u, ModuleHandleW, dwMessageId, 0, Buffer, 0, &Arguments);
  Arguments = 0;
  if ( v11 )
  {
    v15 = GetModuleHandleW(0);
    if ( FormatMessageW(0x900u, v15, a2, 0, lpBuffer, 0, 0) )
    {
      v17 = wcsrchr(*(const wchar_t **)lpBuffer, 0xDu);
      if ( v17 )
        *v17 = 0;
      v9 = TaskDialog(
             hWndParent,
             0,
             *(PCWSTR *)lpBuffer,
             *(PCWSTR *)lpBuffer,
             *(PCWSTR *)Buffer,
             dwCommonButtons,
             pszIcon,
             pnButton);
      if ( v9 >= 0 )
      {
        if ( dwMessageId != 60006 && dwMessageId != 60017 )
          dword_140020218 = 1;
      }
      else
      {
        WusaLogDebugEventA(L"WusaMessageBox", 250, "Failed: TaskDialog()");
      }
      goto LABEL_22;
    }
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v13 = a2;
    v14 = 236;
  }
  else
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    v13 = dwMessageId;
    v14 = 222;
  }
  if ( v9 >= 0 )
    v9 = -2147467259;
  WusaLogDebugEventA(L"WusaMessageBox", v14, "Failed to get message text for id %u", v13);
LABEL_22:
  if ( *(_QWORD *)lpBuffer )
  {
    LocalFree(*(HLOCAL *)lpBuffer);
    *(_QWORD *)lpBuffer = 0;
  }
  if ( *(_QWORD *)Buffer )
  {
    LocalFree(*(HLOCAL *)Buffer);
    *(_QWORD *)Buffer = 0;
  }
  if ( v9 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v9, (unsigned __int16 **)&hMem);
    v18 = hMem;
    WusaLogDebugEventA(L"WusaMessageBox", 263, "Exit with error code 0X%x (%ls)", v9, (const wchar_t *)hMem);
    if ( v18 )
      LocalFree(v18);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000ec58  push    rbp
0x14000ec5a  push    rbx
0x14000ec5b  push    rsi
0x14000ec5c  push    rdi
0x14000ec5d  push    r12
0x14000ec5f  push    r14
0x14000ec61  push    r15
0x14000ec63  mov     rbp, rsp
0x14000ec66  sub     rsp, 60h
0x14000ec6a  xor     r12d, r12d
0x14000ec6d  mov     r14, r9
0x14000ec70  cmp     cs:dword_140020188, r12d
0x14000ec77  mov     r15d, r8d
0x14000ec7a  mov     esi, edx
0x14000ec7c  mov     [rbp+var_10], r12
0x14000ec80  mov     edi, ecx
0x14000ec82  mov     qword ptr [rbp+Buffer], r12
0x14000ec86  mov     ebx, r12d
0x14000ec89  mov     qword ptr [rbp+var_20], r12
0x14000ec8d  jnz     loc_14000EE6F
0x14000ec93  cmp     cs:dword_140020218, r12d
0x14000ec9a  jnz     loc_14000EE6F
0x14000eca0  cmp     cs:dword_14002021C, r12d
0x14000eca7  jnz     loc_14000EE6F
0x14000ecad  lea     rax, [rbp+arg_28]
0x14000ecb1  xor     ecx, ecx; lpModuleName
0x14000ecb3  mov     [rbp+var_10], rax
0x14000ecb7  call    cs:__imp_GetModuleHandleW
0x14000ecbd  mov     ebx, 900h
0x14000ecc2  xor     r9d, r9d; dwLanguageId
0x14000ecc5  mov     rdx, rax; lpSource
0x14000ecc8  mov     r8d, edi; dwMessageId
0x14000eccb  lea     rax, [rbp+var_10]
0x14000eccf  mov     ecx, ebx; dwFlags
0x14000ecd1  mov     [rsp+60h+Arguments], rax; Arguments
0x14000ecd6  lea     rax, [rbp+Buffer]
0x14000ecda  mov     [rsp+60h+nSize], r12d; nSize
0x14000ecdf  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x14000ece4  call    cs:__imp_FormatMessageW
0x14000ecea  mov     [rbp+var_10], r12
0x14000ecee  test    eax, eax
0x14000ecf0  jnz     short loc_14000ED31
0x14000ecf2  call    cs:__imp_GetLastError
0x14000ecf8  mov     ebx, eax
0x14000ecfa  test    eax, eax
0x14000ecfc  jle     short loc_14000ED07
0x14000ecfe  movzx   ebx, ax
0x14000ed01  or      ebx, 80070000h
0x14000ed07  mov     r9d, edi
0x14000ed0a  mov     edx, 0DEh
0x14000ed0f  test    ebx, ebx
0x14000ed11  lea     r8, aFailedToGetMes_0; "Failed to get message text for id %u"
0x14000ed18  mov     eax, 80004005h
0x14000ed1d  lea     rcx, aWusamessagebox; "WusaMessageBox"
0x14000ed24  cmovns  ebx, eax
0x14000ed27  call    WusaLogDebugEventA
0x14000ed2c  jmp     loc_14000EE04
0x14000ed31  xor     ecx, ecx; lpModuleName
0x14000ed33  call    cs:__imp_GetModuleHandleW
0x14000ed39  mov     [rsp+60h+Arguments], r12; Arguments
0x14000ed3e  xor     r9d, r9d; dwLanguageId
0x14000ed41  mov     rdx, rax; lpSource
0x14000ed44  mov     [rsp+60h+nSize], r12d; nSize
0x14000ed49  lea     rax, [rbp+var_20]
0x14000ed4d  mov     r8d, esi; dwMessageId
0x14000ed50  mov     ecx, ebx; dwFlags
0x14000ed52  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x14000ed57  call    cs:__imp_FormatMessageW
0x14000ed5d  test    eax, eax
0x14000ed5f  jnz     short loc_14000ED80
0x14000ed61  call    cs:__imp_GetLastError
0x14000ed67  mov     ebx, eax
0x14000ed69  test    eax, eax
0x14000ed6b  jle     short loc_14000ED76
0x14000ed6d  movzx   ebx, ax
0x14000ed70  or      ebx, 80070000h
0x14000ed76  mov     r9d, esi
0x14000ed79  mov     edx, 0ECh
0x14000ed7e  jmp     short loc_14000ED0F
0x14000ed80  mov     rcx, qword ptr [rbp+var_20]; Str
0x14000ed84  mov     edx, 0Dh; Ch
0x14000ed89  call    cs:__imp_wcsrchr
0x14000ed8f  test    rax, rax
0x14000ed92  jz      short loc_14000ED98
0x14000ed94  mov     [rax], r12w
0x14000ed98  mov     rax, [rbp+arg_20]
0x14000ed9c  xor     edx, edx; hInstance
0x14000ed9e  mov     r8, qword ptr [rbp+var_20]; pszWindowTitle
0x14000eda2  mov     rcx, cs:hWndParent; hwndOwner
0x14000eda9  mov     r9, r8; pszMainInstruction
0x14000edac  mov     [rsp+60h+pnButton], rax; pnButton
0x14000edb1  mov     rax, qword ptr [rbp+Buffer]
0x14000edb5  mov     [rsp+60h+Arguments], r14; pszIcon
0x14000edba  mov     [rsp+60h+nSize], r15d; dwCommonButtons
0x14000edbf  mov     [rsp+60h+lpBuffer], rax; pszContent
0x14000edc4  call    cs:__imp_TaskDialog
0x14000edca  mov     ebx, eax
0x14000edcc  test    eax, eax
0x14000edce  jns     short loc_14000EDEA
0x14000edd0  lea     r8, aFailedTaskdial; "Failed: TaskDialog()"
0x14000edd7  mov     edx, 0FAh
0x14000eddc  lea     rcx, aWusamessagebox; "WusaMessageBox"
0x14000ede3  call    WusaLogDebugEventA
0x14000ede8  jmp     short loc_14000EE04
0x14000edea  cmp     edi, 0EA66h
0x14000edf0  jz      short loc_14000EE04
0x14000edf2  cmp     edi, 0EA71h
0x14000edf8  jz      short loc_14000EE04
0x14000edfa  mov     cs:dword_140020218, 1
0x14000ee04  mov     rcx, qword ptr [rbp+var_20]; hMem
0x14000ee08  test    rcx, rcx
0x14000ee0b  jz      short loc_14000EE17
0x14000ee0d  call    cs:__imp_LocalFree
0x14000ee13  mov     qword ptr [rbp+var_20], r12
0x14000ee17  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x14000ee1b  test    rcx, rcx
0x14000ee1e  jz      short loc_14000EE2A
0x14000ee20  call    cs:__imp_LocalFree
0x14000ee26  mov     qword ptr [rbp+Buffer], r12
0x14000ee2a  test    ebx, ebx
0x14000ee2c  jns     short loc_14000EE6F
0x14000ee2e  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x14000ee32  mov     [rbp+hMem], r12
0x14000ee36  mov     ecx, ebx; dwMessageId
0x14000ee38  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000ee3d  mov     rdi, [rbp+hMem]
0x14000ee41  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000ee48  mov     r9d, ebx
0x14000ee4b  mov     [rsp+60h+lpBuffer], rdi
0x14000ee50  mov     edx, 107h
0x14000ee55  lea     rcx, aWusamessagebox; "WusaMessageBox"
0x14000ee5c  call    WusaLogDebugEventA
0x14000ee61  test    rdi, rdi
0x14000ee64  jz      short loc_14000EE6F
0x14000ee66  mov     rcx, rdi; hMem
0x14000ee69  call    cs:__imp_LocalFree
0x14000ee6f  mov     eax, ebx
0x14000ee71  add     rsp, 60h
0x14000ee75  pop     r15
0x14000ee77  pop     r14
0x14000ee79  pop     r12
0x14000ee7b  pop     rdi
0x14000ee7c  pop     rsi
0x14000ee7d  pop     rbx
0x14000ee7e  pop     rbp
0x14000ee7f  retn
```
