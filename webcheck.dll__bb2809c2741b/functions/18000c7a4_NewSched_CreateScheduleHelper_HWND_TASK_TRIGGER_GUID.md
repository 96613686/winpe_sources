# NewSched_CreateScheduleHelper(HWND__ *,_TASK_TRIGGER *,_GUID *)

- ea: `0x18000c7a4`
- end: `0x18000c886`
- name: `?NewSched_CreateScheduleHelper@@YAXPEAUHWND__@@PEAU_TASK_TRIGGER@@PEAU_GUID@@@Z`
- size: `226`
- prototype: `void __fastcall(HWND hDlg, struct _TASK_TRIGGER *, struct _GUID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180012d48`
- `0x180023290`
- `0x180023760`

## callees

- `0x180003950`
- `0x18000b3fc`
- `0x18000c7a4`
- `0x18000d9f8`
- `0x180029280`

## import_xrefs

- `USER32!IsDlgButtonChecked` at `0x18000c803`
- `USER32!IsDlgButtonChecked` at `0x18000c803`
- `USER32!GetDlgItemTextW` at `0x18000c829`
- `USER32!GetDlgItemTextW` at `0x18000c829`

## pseudocode

```c
void __fastcall NewSched_CreateScheduleHelper(HWND hDlg, struct _TASK_TRIGGER *a2, struct _GUID *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  WCHAR String[264]; // [rsp+30h] [rbp-448h] BYREF
  unsigned __int16 v9[264]; // [rsp+240h] [rbp-238h] BYREF

  v6 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a3->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a3->Data1 )
    v6 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a3->Data4;
  if ( v6 )
  {
    if ( a2->cbTriggerSize == 48 )
      UpdateScheduleTrigger(a3, a2);
  }
  else
  {
    v7 = 2;
    if ( IsDlgButtonChecked(hDlg, 2188) != 1 )
      v7 = 0;
    GetDlgItemTextW(hDlg, 2106, String, 260);
    StringCchCopyW(v9, 0x104u, String);
    CreateSchedule(v9, v7, a3, a2, 0);
  }
}

```

## disassembly

```asm
0x18000c7a4  mov     [rsp+arg_18], rbx
0x18000c7a9  push    rbp
0x18000c7aa  push    rsi
0x18000c7ab  push    rdi
0x18000c7ac  sub     rsp, 460h
0x18000c7b3  mov     rax, cs:__security_cookie
0x18000c7ba  xor     rax, rsp
0x18000c7bd  mov     [rsp+478h+var_28], rax
0x18000c7c5  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18000c7cc  mov     rdi, r8
0x18000c7cf  mov     rsi, rdx
0x18000c7d2  mov     rbp, rcx
0x18000c7d5  sub     rax, [r8]
0x18000c7d8  jnz     short loc_18000C7E5
0x18000c7da  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18000c7e1  sub     rax, [r8+8]
0x18000c7e5  test    rax, rax
0x18000c7e8  jz      short loc_18000C7FE
0x18000c7ea  mov     eax, 30h ; '0'
0x18000c7ef  cmp     ax, [rdx]
0x18000c7f2  jnz     short loc_18000C863
0x18000c7f4  mov     rcx, rdi; struct _GUID *
0x18000c7f7  call    ?UpdateScheduleTrigger@@YAJPEAU_GUID@@PEAU_TASK_TRIGGER@@@Z; UpdateScheduleTrigger(_GUID *,_TASK_TRIGGER *)
0x18000c7fc  jmp     short loc_18000C863
0x18000c7fe  mov     edx, 88Ch; nIDButton
0x18000c803  call    cs:__imp_IsDlgButtonChecked
0x18000c809  xor     edx, edx
0x18000c80b  lea     r8, [rsp+478h+String]; lpString
0x18000c810  cmp     eax, 1
0x18000c813  mov     ebx, 2
0x18000c818  mov     r9d, 104h; cchMax
0x18000c81e  mov     rcx, rbp; hDlg
0x18000c821  cmovnz  ebx, edx
0x18000c824  mov     edx, 83Ah; nIDDlgItem
0x18000c829  call    cs:__imp_GetDlgItemTextW
0x18000c82f  lea     r8, [rsp+478h+String]; unsigned __int16 *
0x18000c834  mov     edx, 104h; unsigned __int64
0x18000c839  lea     rcx, [rsp+478h+var_238]; unsigned __int16 *
0x18000c841  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c846  mov     r9, rsi; struct _TASK_TRIGGER *
0x18000c849  mov     [rsp+478h+var_458], 0; int
0x18000c851  mov     r8, rdi; struct _GUID *
0x18000c854  lea     rcx, [rsp+478h+var_238]; unsigned __int16 *
0x18000c85c  mov     edx, ebx; unsigned int
0x18000c85e  call    ?CreateSchedule@@YAJPEBGKPEAU_GUID@@PEAU_TASK_TRIGGER@@H@Z; CreateSchedule(ushort const *,ulong,_GUID *,_TASK_TRIGGER *,int)
0x18000c863  mov     rcx, [rsp+478h+var_28]
0x18000c86b  xor     rcx, rsp; StackCookie
0x18000c86e  call    __security_check_cookie
0x18000c873  mov     rbx, [rsp+478h+arg_18]
0x18000c87b  add     rsp, 460h
0x18000c882  pop     rdi
0x18000c883  pop     rsi
0x18000c884  pop     rbp
0x18000c885  retn
```
