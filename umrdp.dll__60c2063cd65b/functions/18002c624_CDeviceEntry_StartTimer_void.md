# CDeviceEntry::StartTimer(void)

- ea: `0x18002c624`
- end: `0x18002c6be`
- name: `?StartTimer@CDeviceEntry@@AEAAJXZ`
- size: `154`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c6f8`

## callees

- `0x18000b8f8`
- `0x18000f79c`
- `0x18002c624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c65a`
- `KERNEL32!CreateTimerQueueTimer` at `0x18002c650`
- `KERNEL32!CreateTimerQueueTimer` at `0x18002c650`

## pseudocode

```c
__int64 __fastcall CDeviceEntry::StartTimer(void **Parameter)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v1 = 0;
  if ( !CreateTimerQueueTimer(Parameter + 13, 0, CDeviceEntry::static_CreateTimeout, Parameter, 0x1D4C0u, 0, 8u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        21,
        WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
        CurrentThreadActivityIdPrefix,
        v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18002c624  push    rbx
0x18002c626  sub     rsp, 40h
0x18002c62a  mov     r9, rcx; Parameter
0x18002c62d  mov     [rsp+48h+Flags], 8; Flags
0x18002c635  xor     ebx, ebx
0x18002c637  lea     r8, ?static_CreateTimeout@CDeviceEntry@@CAXPEAXE@Z; Callback
0x18002c63e  mov     [rsp+48h+Period], ebx; Period
0x18002c642  add     rcx, 68h ; 'h'; phNewTimer
0x18002c646  xor     edx, edx; TimerQueue
0x18002c648  mov     [rsp+48h+DueTime], 1D4C0h; DueTime
0x18002c650  call    cs:__imp_CreateTimerQueueTimer
0x18002c656  test    eax, eax
0x18002c658  jnz     short loc_18002C6B6
0x18002c65a  call    cs:__imp_GetLastError
0x18002c660  mov     ebx, eax
0x18002c662  test    eax, eax
0x18002c664  jle     short loc_18002C66F
0x18002c666  movzx   ebx, ax
0x18002c669  or      ebx, 80070000h
0x18002c66f  mov     rax, cs:WPP_GLOBAL_Control
0x18002c676  lea     rcx, WPP_GLOBAL_Control
0x18002c67d  cmp     rax, rcx
0x18002c680  jz      short loc_18002C6B6
0x18002c682  test    byte ptr [rax+1Ch], 1
0x18002c686  jz      short loc_18002C6B6
0x18002c688  cmp     byte ptr [rax+19h], 2
0x18002c68c  jb      short loc_18002C6B6
0x18002c68e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c693  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c69a  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c6a1  mov     edx, 15h
0x18002c6a6  mov     [rsp+48h+DueTime], ebx
0x18002c6aa  mov     r9d, eax
0x18002c6ad  mov     rcx, [rcx+10h]
0x18002c6b1  call    WPP_SF_Dd
0x18002c6b6  mov     eax, ebx
0x18002c6b8  add     rsp, 40h
0x18002c6bc  pop     rbx
0x18002c6bd  retn
```
