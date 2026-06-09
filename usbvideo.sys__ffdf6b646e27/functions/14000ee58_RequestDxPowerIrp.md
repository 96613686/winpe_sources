# RequestDxPowerIrp

- ea: `0x14000ee58`
- end: `0x14000ef81`
- name: `RequestDxPowerIrp`
- size: `297`
- prototype: `__int64 __fastcall(PVOID Context, POWER_STATE PowerState)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ec44`
- `0x14000ed70`

## callees

- `0x14000ee58`
- `0x14001ab4c`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x14000eedf`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000eedf`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ef3e`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000ef3e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000eeab`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000eeab`

## pseudocode

```c
__int64 __fastcall RequestDxPowerIrp(struct _IO_REMOVE_LOCK *Context, POWER_STATE PowerState)
{
  unsigned int v4; // edi
  PDEVICE_OBJECT v5; // rcx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context);
  v4 = IoAcquireRemoveLockEx(Context + 24, PowerIrpCompletion, File, 1u, 0x20u);
  if ( !v4 )
  {
    v4 = PoRequestPowerIrp(
           (PDEVICE_OBJECT)Context->Common.RemoveEvent.Header.WaitListHead.Blink[2].Flink,
           2u,
           PowerState,
           (PREQUEST_POWER_COMPLETE)PowerIrpCompletion,
           Context,
           0);
    if ( (v4 & 0x80000000) == 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        return v4;
      v7 = 157;
LABEL_13:
      WPP_SF_qD(v5->AttachedDevice, v7, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, Context, v4);
      return v4;
    }
    IoReleaseRemoveLockEx(Context + 24, PowerIrpCompletion, 0x20u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 156;
      goto LABEL_13;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000ee58  push    rbx
0x14000ee5a  push    rbp
0x14000ee5b  push    rsi
0x14000ee5c  push    rdi
0x14000ee5d  push    r14
0x14000ee5f  sub     rsp, 30h
0x14000ee63  mov     ebx, edx
0x14000ee65  mov     rsi, rcx
0x14000ee68  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee6f  lea     r14, WPP_GLOBAL_Control
0x14000ee76  cmp     rcx, r14
0x14000ee79  jz      short loc_14000EE85
0x14000ee7b  cmp     byte ptr [rcx+29h], 5
0x14000ee7f  jnb     loc_14000EF11
0x14000ee85  lea     rbp, [rsi+300h]
0x14000ee8c  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x14000ee94  mov     rcx, rbp; RemoveLock
0x14000ee97  lea     r8, File; File
0x14000ee9e  mov     r9d, 1; Line
0x14000eea4  lea     rdx, PowerIrpCompletion; Tag
0x14000eeab  call    cs:__imp_IoAcquireRemoveLockEx
0x14000eeb2  nop     dword ptr [rax+rax+00h]
0x14000eeb7  mov     edi, eax
0x14000eeb9  test    eax, eax
0x14000eebb  jnz     short loc_14000EF03
0x14000eebd  mov     rcx, [rsi+18h]
0x14000eec1  lea     r9, PowerIrpCompletion; CompletionFunction
0x14000eec8  mov     [rsp+58h+Irp], 0; Irp
0x14000eed1  mov     r8d, ebx; PowerState
0x14000eed4  mov     dl, 2; MinorFunction
0x14000eed6  mov     qword ptr [rsp+58h+RemlockSize], rsi; Context
0x14000eedb  mov     rcx, [rcx+20h]; DeviceObject
0x14000eedf  call    cs:__imp_PoRequestPowerIrp
0x14000eee6  nop     dword ptr [rax+rax+00h]
0x14000eeeb  mov     edi, eax
0x14000eeed  test    eax, eax
0x14000eeef  js      short loc_14000EF2E
0x14000eef1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eef8  cmp     rcx, r14
0x14000eefb  jz      short loc_14000EF03
0x14000eefd  cmp     byte ptr [rcx+29h], 4
0x14000ef01  jnb     short loc_14000EF63
0x14000ef03  mov     eax, edi
0x14000ef05  add     rsp, 30h
0x14000ef09  pop     r14
0x14000ef0b  pop     rdi
0x14000ef0c  pop     rsi
0x14000ef0d  pop     rbp
0x14000ef0e  pop     rbx
0x14000ef0f  retn
0x14000ef11  mov     rcx, [rcx+18h]
0x14000ef15  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14000ef1c  mov     edx, 9Bh
0x14000ef21  mov     r9, rsi
0x14000ef24  call    WPP_SF_q
0x14000ef29  jmp     loc_14000EE85
0x14000ef2e  mov     r8d, 20h ; ' '; RemlockSize
0x14000ef34  lea     rdx, PowerIrpCompletion; Tag
0x14000ef3b  mov     rcx, rbp; RemoveLock
0x14000ef3e  call    cs:__imp_IoReleaseRemoveLockEx
0x14000ef45  nop     dword ptr [rax+rax+00h]
0x14000ef4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef51  cmp     rcx, r14
0x14000ef54  jz      short loc_14000EF03
0x14000ef56  cmp     byte ptr [rcx+29h], 2
0x14000ef5a  jb      short loc_14000EF03
0x14000ef5c  mov     edx, 9Ch
0x14000ef61  jmp     short loc_14000EF68
0x14000ef63  mov     edx, 9Dh
0x14000ef68  mov     rcx, [rcx+18h]
0x14000ef6c  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14000ef73  mov     r9, rsi
0x14000ef76  mov     [rsp+58h+RemlockSize], edi
0x14000ef7a  call    WPP_SF_qD
0x14000ef7f  jmp     short loc_14000EF03
```
