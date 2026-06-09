# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180003570`
- end: `0x1800035db`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `107`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800026e0`
- `0x180003570`
- `0x180003a28`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1);
    v4 = WPP_GLOBAL_Control;
  }
  svcData = a1;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 11, &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids);
}

```

## disassembly

```asm
0x180003570  mov     [rsp+arg_0], rbx
0x180003575  push    rdi
0x180003576  sub     rsp, 20h
0x18000357a  mov     rbx, rcx
0x18000357d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003584  lea     rdi, WPP_GLOBAL_Control
0x18000358b  cmp     rcx, rdi
0x18000358e  jz      short loc_1800035A9
0x180003590  test    byte ptr [rcx+1Ch], 20h
0x180003594  jz      short loc_1800035A9
0x180003596  mov     rcx, [rcx+10h]
0x18000359a  mov     r9, rbx
0x18000359d  call    WPP_SF_q
0x1800035a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035a9  mov     cs:?svcData@@3U_WEPHOST_SERVICE_DATA@@A, rbx; _WEPHOST_SERVICE_DATA svcData
0x1800035b0  cmp     rcx, rdi
0x1800035b3  jz      short loc_1800035D0
0x1800035b5  test    byte ptr [rcx+1Ch], 20h
0x1800035b9  jz      short loc_1800035D0
0x1800035bb  mov     rcx, [rcx+10h]
0x1800035bf  lea     r8, WPP_3a1233b099da3452b07b65d2eb146164_Traceguids
0x1800035c6  mov     edx, 0Bh
0x1800035cb  call    WPP_SF_
0x1800035d0  mov     rbx, [rsp+28h+arg_0]
0x1800035d5  add     rsp, 20h
0x1800035d9  pop     rdi
0x1800035da  retn
```
