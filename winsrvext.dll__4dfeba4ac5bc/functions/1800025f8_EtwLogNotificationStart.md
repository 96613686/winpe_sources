# EtwLogNotificationStart

- ea: `0x1800025f8`
- end: `0x18000267d`
- name: `EtwLogNotificationStart`
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

- `0x1800025f8`
- `0x1800138f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000265e`
- `ntdll!EtwEventWrite` at `0x18000265e`
- `ntdll!EtwEventEnabled` at `0x180002622`
- `ntdll!EtwEventEnabled` at `0x180002622`

## pseudocode

```c
void __fastcall EtwLogNotificationStart(int a1)
{
  _QWORD v1[2]; // [rsp+20h] [rbp-28h] BYREF
  int v2; // [rsp+50h] [rbp+8h] BYREF

  v2 = a1;
  if ( g_EtwRegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(g_EtwRegHandle, WinSrvEvt_Notification_Event_Start) )
    {
      v1[0] = &v2;
      v1[1] = 4;
      EtwEventWrite(g_EtwRegHandle, WinSrvEvt_Notification_Event_Start, 1, v1);
    }
  }
}

```

## disassembly

```asm
0x1800025f8  mov     [rsp+arg_0], ecx
0x1800025fc  sub     rsp, 48h
0x180002600  mov     rax, cs:__security_cookie
0x180002607  xor     rax, rsp
0x18000260a  mov     [rsp+48h+var_18], rax
0x18000260f  mov     rcx, cs:g_EtwRegHandle
0x180002616  test    rcx, rcx
0x180002619  jz      short loc_18000266A
0x18000261b  lea     rdx, WinSrvEvt_Notification_Event_Start
0x180002622  call    cs:__imp_EtwEventEnabled
0x180002629  nop     dword ptr [rax+rax+00h]
0x18000262e  test    al, al
0x180002630  jz      short loc_18000266A
0x180002632  mov     rcx, cs:g_EtwRegHandle
0x180002639  lea     rax, [rsp+48h+arg_0]
0x18000263e  lea     r9, [rsp+48h+var_28]
0x180002643  mov     [rsp+48h+var_28], rax
0x180002648  mov     r8d, 1
0x18000264e  mov     [rsp+48h+var_20], 4
0x180002657  lea     rdx, WinSrvEvt_Notification_Event_Start
0x18000265e  call    cs:__imp_EtwEventWrite
0x180002665  nop     dword ptr [rax+rax+00h]
0x18000266a  mov     rcx, [rsp+48h+var_18]
0x18000266f  xor     rcx, rsp; StackCookie
0x180002672  call    __security_check_cookie
0x180002677  add     rsp, 48h
0x18000267b  retn
```
