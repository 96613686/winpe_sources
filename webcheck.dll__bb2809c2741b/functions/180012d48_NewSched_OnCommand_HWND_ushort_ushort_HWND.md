# NewSched_OnCommand(HWND__ *,ushort,ushort,HWND__ *)

- ea: `0x180012d48`
- end: `0x180012e44`
- name: `?NewSched_OnCommand@@YAHPEAUHWND__@@GG0@Z`
- size: `252`
- prototype: `__int64 __fastcall(HWND, unsigned __int16, unsigned __int16, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012e50`

## callees

- `0x18000c370`
- `0x18000c7a4`
- `0x18000c9c0`
- `0x180012d48`
- `0x180029280`

## import_xrefs

- `USER32!GetDlgItemTextW` at `0x180012e0f`
- `USER32!GetDlgItemTextW` at `0x180012e0f`
- `USER32!EndDialog` at `0x180012e1d`
- `USER32!EndDialog` at `0x180012e1d`
- `USER32!GetWindowLongPtrW` at `0x180012dd0`
- `USER32!GetWindowLongPtrW` at `0x180012dd0`

## pseudocode

```c
__int64 __fastcall NewSched_OnCommand(HWND a1, __int16 a2, __int16 a3, HWND a4)
{
  unsigned int v4; // edi
  HWND v5; // rbx
  INT_PTR v6; // rdx
  LONG_PTR WindowLongPtrW; // rsi
  struct _TASK_TRIGGER v9; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  v5 = a1;
  switch ( a3 )
  {
    case 1:
      memset(&v9, 0, sizeof(v9));
      WindowLongPtrW = GetWindowLongPtrW(a1, 16);
      if ( !(unsigned int)NewSched_ResolveNameConflictHelper(v5, &v9, (struct _GUID *)WindowLongPtrW) )
        return v4;
      NewSched_CreateScheduleHelper(v5, &v9, (struct _GUID *)WindowLongPtrW);
      GetDlgItemTextW(v5, 2106, (LPWSTR)(WindowLongPtrW + 16), 260);
      v6 = 1;
      a1 = v5;
LABEL_10:
      EndDialog(a1, v6);
      return v4;
    case 2:
      v6 = 2;
      goto LABEL_10;
    case 2102:
      if ( a2 == 1024 )
        KeepSpinNumberInRange(a1, 2102, 2103, 1u, 99);
      return 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180012d48  mov     [rsp+arg_8], rbx
0x180012d4d  mov     [rsp+arg_10], rsi
0x180012d52  push    rdi
0x180012d53  sub     rsp, 70h
0x180012d57  mov     rax, cs:__security_cookie
0x180012d5e  xor     rax, rsp
0x180012d61  mov     [rsp+78h+var_18], rax
0x180012d66  xor     edi, edi
0x180012d68  movzx   r9d, r8w
0x180012d6c  mov     rbx, rcx
0x180012d6f  sub     r9d, 1
0x180012d73  jz      short loc_180012DB9
0x180012d75  sub     r9d, 1
0x180012d79  jz      short loc_180012DB2
0x180012d7b  cmp     r9d, 834h
0x180012d82  jnz     loc_180012E23
0x180012d88  mov     eax, 400h
0x180012d8d  cmp     dx, ax
0x180012d90  jnz     short loc_180012DAB
0x180012d92  lea     edx, [r9+2]; nIDDlgItem
0x180012d96  mov     [rsp+78h+var_58], 63h ; 'c'; int
0x180012d9e  lea     r8d, [rdx+1]; int
0x180012da2  lea     r9d, [rdi+1]; uValue
0x180012da6  call    ?KeepSpinNumberInRange@@YAHPEAUHWND__@@HHHH@Z; KeepSpinNumberInRange(HWND__ *,int,int,int,int)
0x180012dab  mov     edi, 1
0x180012db0  jmp     short loc_180012E23
0x180012db2  mov     edx, 2
0x180012db7  jmp     short loc_180012E1D
0x180012db9  xorps   xmm0, xmm0
0x180012dbc  mov     edx, 10h; nIndex
0x180012dc1  movups  xmmword ptr [rsp+78h+var_48.cbTriggerSize], xmm0
0x180012dc6  movups  xmmword ptr [rsp+78h+var_48.wStartHour], xmm0
0x180012dcb  movups  xmmword ptr [rsp+78h+var_48.TriggerType], xmm0
0x180012dd0  call    cs:__imp_GetWindowLongPtrW
0x180012dd6  lea     rdx, [rsp+78h+var_48]; struct _TASK_TRIGGER *
0x180012ddb  mov     rcx, rbx; HWND
0x180012dde  mov     r8, rax; struct _GUID *
0x180012de1  mov     rsi, rax
0x180012de4  call    ?NewSched_ResolveNameConflictHelper@@YAHPEAUHWND__@@PEAU_TASK_TRIGGER@@PEAU_GUID@@@Z; NewSched_ResolveNameConflictHelper(HWND__ *,_TASK_TRIGGER *,_GUID *)
0x180012de9  test    eax, eax
0x180012deb  jz      short loc_180012E23
0x180012ded  mov     r8, rsi; struct _GUID *
0x180012df0  lea     rdx, [rsp+78h+var_48]; struct _TASK_TRIGGER *
0x180012df5  mov     rcx, rbx; hDlg
0x180012df8  call    ?NewSched_CreateScheduleHelper@@YAXPEAUHWND__@@PEAU_TASK_TRIGGER@@PEAU_GUID@@@Z; NewSched_CreateScheduleHelper(HWND__ *,_TASK_TRIGGER *,_GUID *)
0x180012dfd  lea     r8, [rsi+10h]; lpString
0x180012e01  mov     edx, 83Ah; nIDDlgItem
0x180012e06  mov     r9d, 104h; cchMax
0x180012e0c  mov     rcx, rbx; hDlg
0x180012e0f  call    cs:__imp_GetDlgItemTextW
0x180012e15  mov     edx, 1; nResult
0x180012e1a  mov     rcx, rbx; hDlg
0x180012e1d  call    cs:__imp_EndDialog
0x180012e23  mov     eax, edi
0x180012e25  mov     rcx, [rsp+78h+var_18]
0x180012e2a  xor     rcx, rsp; StackCookie
0x180012e2d  call    __security_check_cookie
0x180012e32  lea     r11, [rsp+78h+var_8]
0x180012e37  mov     rbx, [r11+18h]
0x180012e3b  mov     rsi, [r11+20h]
0x180012e3f  mov     rsp, r11
0x180012e42  pop     rdi
0x180012e43  retn
```
