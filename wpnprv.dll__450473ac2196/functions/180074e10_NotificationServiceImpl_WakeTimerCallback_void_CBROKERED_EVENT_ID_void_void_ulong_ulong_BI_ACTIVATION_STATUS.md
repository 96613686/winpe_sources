# NotificationServiceImpl::WakeTimerCallback(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *)

- ea: `0x180074e10`
- end: `0x180074eec`
- name: `?WakeTimerCallback@NotificationServiceImpl@@KAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z`
- size: `220`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fe2c`
- `0x18001c06c`
- `0x180074e10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180074ea9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180074ea9`

## pseudocode

```c
void __fastcall NotificationServiceImpl::WakeTimerCallback(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v5; // rcx

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( a1 == *(_QWORD *)(a3 + 176) )
    {
      SubmitThreadpoolWork(*(PTP_WORK *)(a3 + 336));
      goto LABEL_12;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
LABEL_12:
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_(v5[2], 283, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
}

```

## disassembly

```asm
0x180074e10  mov     [rsp+arg_0], rbx
0x180074e15  mov     [rsp+arg_8], rbp
0x180074e1a  push    rdi
0x180074e1b  sub     rsp, 20h
0x180074e1f  mov     rbx, r8
0x180074e22  mov     rdi, rcx
0x180074e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e2c  lea     rbp, WPP_GLOBAL_Control
0x180074e33  cmp     rcx, rbp
0x180074e36  jz      short loc_180074E60
0x180074e38  test    byte ptr [rcx+1Ch], 2
0x180074e3c  jz      short loc_180074E60
0x180074e3e  cmp     byte ptr [rcx+19h], 6
0x180074e42  jb      short loc_180074E60
0x180074e44  mov     rcx, [rcx+10h]
0x180074e48  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074e4f  mov     edx, 119h
0x180074e54  call    WPP_SF_
0x180074e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e60  test    rbx, rbx
0x180074e63  jnz     short loc_180074E99
0x180074e65  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180074e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e71  cmp     rcx, rbp
0x180074e74  jz      short loc_180074EDC
0x180074e76  test    byte ptr [rcx+1Ch], 2
0x180074e7a  jz      short loc_180074EB6
0x180074e7c  cmp     byte ptr [rcx+19h], 2
0x180074e80  jb      short loc_180074EB6
0x180074e82  mov     rcx, [rcx+10h]
0x180074e86  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074e8d  mov     edx, 11Ah
0x180074e92  call    WPP_SF_
0x180074e97  jmp     short loc_180074EAF
0x180074e99  cmp     rdi, [rbx+0B0h]
0x180074ea0  jnz     short loc_180074EB6
0x180074ea2  mov     rcx, [rbx+150h]; pwk
0x180074ea9  call    cs:__imp_SubmitThreadpoolWork
0x180074eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180074eb6  cmp     rcx, rbp
0x180074eb9  jz      short loc_180074EDC
0x180074ebb  test    byte ptr [rcx+1Ch], 2
0x180074ebf  jz      short loc_180074EDC
0x180074ec1  cmp     byte ptr [rcx+19h], 6
0x180074ec5  jb      short loc_180074EDC
0x180074ec7  mov     rcx, [rcx+10h]
0x180074ecb  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074ed2  mov     edx, 11Bh
0x180074ed7  call    WPP_SF_
0x180074edc  mov     rbx, [rsp+28h+arg_0]
0x180074ee1  mov     rbp, [rsp+28h+arg_8]
0x180074ee6  add     rsp, 20h
0x180074eea  pop     rdi
0x180074eeb  retn
```
