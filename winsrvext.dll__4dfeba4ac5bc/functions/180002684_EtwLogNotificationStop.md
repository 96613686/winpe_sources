# EtwLogNotificationStop

- ea: `0x180002684`
- end: `0x180002709`
- name: `EtwLogNotificationStop`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003650`
- `0x180003bc0`
- `0x180003c40`

## callees

- `0x180002684`
- `0x1800138f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800026ea`
- `ntdll!EtwEventWrite` at `0x1800026ea`
- `ntdll!EtwEventEnabled` at `0x1800026ae`
- `ntdll!EtwEventEnabled` at `0x1800026ae`

## pseudocode

```c
void __fastcall EtwLogNotificationStop(int a1)
{
  _QWORD v1[2]; // [rsp+20h] [rbp-28h] BYREF
  int v2; // [rsp+50h] [rbp+8h] BYREF

  v2 = a1;
  if ( g_EtwRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_Notification_Event_Stop) )
    {
      v1[0] = &v2;
      v1[1] = 4;
      EtwEventWrite(g_EtwRegHandle, WinSrvEvt_Notification_Event_Stop, 1, v1);
    }
  }
}

```

## disassembly

```asm
0x180002684  mov     [rsp+arg_0], ecx
0x180002688  sub     rsp, 48h
0x18000268c  mov     rax, cs:__security_cookie
0x180002693  xor     rax, rsp
0x180002696  mov     [rsp+48h+var_18], rax
0x18000269b  mov     rcx, cs:g_EtwRegHandle
0x1800026a2  test    rcx, rcx
0x1800026a5  jz      short loc_1800026F6
0x1800026a7  lea     rdx, WinSrvEvt_Notification_Event_Stop
0x1800026ae  call    cs:__imp_EtwEventEnabled
0x1800026b5  nop     dword ptr [rax+rax+00h]
0x1800026ba  test    al, al
0x1800026bc  jz      short loc_1800026F6
0x1800026be  mov     rcx, cs:g_EtwRegHandle
0x1800026c5  lea     rax, [rsp+48h+arg_0]
0x1800026ca  lea     r9, [rsp+48h+var_28]
0x1800026cf  mov     [rsp+48h+var_28], rax
0x1800026d4  mov     r8d, 1
0x1800026da  mov     [rsp+48h+var_20], 4
0x1800026e3  lea     rdx, WinSrvEvt_Notification_Event_Stop
0x1800026ea  call    cs:__imp_EtwEventWrite
0x1800026f1  nop     dword ptr [rax+rax+00h]
0x1800026f6  mov     rcx, [rsp+48h+var_18]
0x1800026fb  xor     rcx, rsp; StackCookie
0x1800026fe  call    __security_check_cookie
0x180002703  add     rsp, 48h
0x180002707  retn
```
