# NewSched_ResolveNameConflictHelper(HWND__ *,_TASK_TRIGGER *,_GUID *)

- ea: `0x18000c9c0`
- end: `0x18000cb2d`
- name: `?NewSched_ResolveNameConflictHelper@@YAHPEAUHWND__@@PEAU_TASK_TRIGGER@@PEAU_GUID@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(HWND, struct _TASK_TRIGGER *, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012d48`
- `0x18002371c`

## callees

- `0x18000becc`
- `0x18000c9c0`
- `0x18001be60`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetLocalTime` at `0x18000ca50`
- `KERNEL32!GetLocalTime` at `0x18000ca50`
- `USER32!GetDlgItemInt` at `0x18000cabf`
- `USER32!GetDlgItemInt` at `0x18000cabf`
- `USER32!GetDlgItem` at `0x18000ca79`
- `USER32!GetDlgItem` at `0x18000ca79`
- `USER32!GetDlgItemTextW` at `0x18000ca0d`
- `USER32!GetDlgItemTextW` at `0x18000ca0d`
- `USER32!SendMessageW` at `0x18000ca8f`
- `USER32!SendMessageW` at `0x18000ca8f`
- `SHLWAPI!StrTrimW` at `0x18000ca1f`
- `SHLWAPI!StrTrimW` at `0x18000ca1f`

## pseudocode

```c
__int64 __fastcall NewSched_ResolveNameConflictHelper(HWND a1, struct _TASK_TRIGGER *a2, struct _GUID *a3)
{
  unsigned int v6; // ebx
  HWND DlgItem; // rax
  int v8; // eax
  BOOL Translated; // [rsp+20h] [rbp-E0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR String[264]; // [rsp+40h] [rbp-C0h] BYREF

  SystemTime = 0;
  GetDlgItemTextW(a1, 2106, String, 260);
  StrTrimW(String, pszTrimChars);
  if ( !String[0] )
  {
    SGMessageBox(a1, 0x2036u, 0x30u);
    return 0;
  }
  *(_OWORD *)&a2->cbTriggerSize = 0;
  v6 = 1;
  *(_OWORD *)&a2->wStartHour = 0;
  *(_OWORD *)&a2->TriggerType = 0;
  a2->cbTriggerSize = 48;
  GetLocalTime(&SystemTime);
  a2->wBeginYear = SystemTime.wYear;
  a2->wBeginMonth = SystemTime.wMonth;
  a2->wBeginDay = SystemTime.wDay;
  DlgItem = GetDlgItem(a1, 2109);
  SendMessageW(DlgItem, 0x1001u, 0, (LPARAM)&SystemTime);
  a2->wStartHour = SystemTime.wHour;
  a2->wStartMinute = SystemTime.wMinute;
  a2->TriggerType = TASK_TIME_TRIGGER_DAILY;
  Translated = 0;
  a2->Type.Daily.DaysInterval = GetDlgItemInt(a1, 2102, &Translated, 0);
  v8 = HandleScheduleNameConflict(String, a2, a1, a3);
  if ( v8 == 2 )
  {
    a2->cbTriggerSize = 0;
  }
  else if ( v8 == 3 )
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c9c0  mov     [rsp-8+arg_18], rbx
0x18000c9c5  push    rbp
0x18000c9c6  push    rsi
0x18000c9c7  push    rdi
0x18000c9c8  push    r14
0x18000c9ca  push    r15
0x18000c9cc  lea     rbp, [rsp-160h]
0x18000c9d4  sub     rsp, 260h
0x18000c9db  mov     rax, cs:__security_cookie
0x18000c9e2  xor     rax, rsp
0x18000c9e5  mov     [rbp+180h+var_30], rax
0x18000c9ec  mov     r14, r8
0x18000c9ef  mov     rdi, rdx
0x18000c9f2  xorps   xmm0, xmm0
0x18000c9f5  lea     r8, [rsp+280h+String]; lpString
0x18000c9fa  mov     edx, 83Ah; nIDDlgItem
0x18000c9ff  mov     r9d, 104h; cchMax
0x18000ca05  movups  xmmword ptr [rsp+280h+SystemTime.wYear], xmm0
0x18000ca0a  mov     rsi, rcx
0x18000ca0d  call    cs:__imp_GetDlgItemTextW
0x18000ca13  lea     rdx, pszTrimChars; " \t"
0x18000ca1a  lea     rcx, [rsp+280h+String]; psz
0x18000ca1f  call    cs:__imp_StrTrimW
0x18000ca25  xor     r15d, r15d
0x18000ca28  cmp     [rsp+280h+String], r15w
0x18000ca2e  jz      loc_18000CAEF
0x18000ca34  xorps   xmm0, xmm0
0x18000ca37  lea     rcx, [rsp+280h+SystemTime]; lpSystemTime
0x18000ca3c  movups  xmmword ptr [rdi], xmm0
0x18000ca3f  lea     ebx, [r15+1]
0x18000ca43  movups  xmmword ptr [rdi+10h], xmm0
0x18000ca47  movups  xmmword ptr [rdi+20h], xmm0
0x18000ca4b  mov     word ptr [rdi], 30h ; '0'
0x18000ca50  call    cs:__imp_GetLocalTime
0x18000ca56  movzx   eax, [rsp+280h+SystemTime.wYear]
0x18000ca5b  mov     edx, 83Dh; nIDDlgItem
0x18000ca60  mov     [rdi+4], ax
0x18000ca64  mov     rcx, rsi; hDlg
0x18000ca67  movzx   eax, [rsp+280h+SystemTime.wMonth]
0x18000ca6c  mov     [rdi+6], ax
0x18000ca70  movzx   eax, [rsp+280h+SystemTime.wDay]
0x18000ca75  mov     [rdi+8], ax
0x18000ca79  call    cs:__imp_GetDlgItem
0x18000ca7f  lea     r9, [rsp+280h+SystemTime]; lParam
0x18000ca84  xor     r8d, r8d; wParam
0x18000ca87  mov     rcx, rax; hWnd
0x18000ca8a  mov     edx, 1001h; Msg
0x18000ca8f  call    cs:__imp_SendMessageW
0x18000ca95  movzx   eax, [rsp+280h+SystemTime.wHour]
0x18000ca9a  lea     r8, [rsp+280h+Translated]; lpTranslated
0x18000ca9f  mov     [rdi+10h], ax
0x18000caa3  xor     r9d, r9d; bSigned
0x18000caa6  movzx   eax, [rsp+280h+SystemTime.wMinute]
0x18000caab  mov     edx, 836h; nIDDlgItem
0x18000cab0  mov     rcx, rsi; hDlg
0x18000cab3  mov     [rdi+12h], ax
0x18000cab7  mov     [rdi+20h], ebx
0x18000caba  mov     [rsp+280h+Translated], r15d
0x18000cabf  call    cs:__imp_GetDlgItemInt
0x18000cac5  mov     r9, r14; struct _GUID *
0x18000cac8  lea     rcx, [rsp+280h+String]; unsigned __int16 *
0x18000cacd  mov     r8, rsi; HWND
0x18000cad0  mov     [rdi+24h], ax
0x18000cad4  mov     rdx, rdi; struct _TASK_TRIGGER *
0x18000cad7  call    ?HandleScheduleNameConflict@@YAHPEBGPEBU_TASK_TRIGGER@@PEAUHWND__@@PEAU_GUID@@@Z; HandleScheduleNameConflict(ushort const *,_TASK_TRIGGER const *,HWND__ *,_GUID *)
0x18000cadc  mov     ecx, eax
0x18000cade  sub     ecx, 2
0x18000cae1  jz      short loc_18000CAE9
0x18000cae3  cmp     ecx, ebx
0x18000cae5  jnz     short loc_18000CB05
0x18000cae7  jmp     short loc_18000CB02
0x18000cae9  mov     [rdi], r15w
0x18000caed  jmp     short loc_18000CB05
0x18000caef  mov     edx, 2036h; unsigned int
0x18000caf4  mov     r8d, 30h ; '0'; unsigned int
0x18000cafa  mov     rcx, rsi; hWnd
0x18000cafd  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x18000cb02  mov     ebx, r15d
0x18000cb05  mov     eax, ebx
0x18000cb07  mov     rcx, [rbp+180h+var_30]
0x18000cb0e  xor     rcx, rsp; StackCookie
0x18000cb11  call    __security_check_cookie
0x18000cb16  mov     rbx, [rsp+280h+arg_18]
0x18000cb1e  add     rsp, 260h
0x18000cb25  pop     r15
0x18000cb27  pop     r14
0x18000cb29  pop     rdi
0x18000cb2a  pop     rsi
0x18000cb2b  pop     rbp
0x18000cb2c  retn
```
