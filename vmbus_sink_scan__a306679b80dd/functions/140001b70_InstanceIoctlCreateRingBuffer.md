# InstanceIoctlCreateRingBuffer

- ea: `0x140001b70`
- end: `0x140001e1b`
- name: `InstanceIoctlCreateRingBuffer`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400041b4`

## callees

- `0x140001b70`
- `0x140002ed0`
- `0x14000389c`
- `0x14000ec8c`
- `0x140017000`
- `0x140017190`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001d04`
- `ntoskrnl!KeSetEvent` at `0x140001da3`
- `ntoskrnl!KeSetEvent` at `0x140001da3`
- `ntoskrnl!KeInitializeEvent` at `0x140001cf8`
- `ntoskrnl!KeInitializeEvent` at `0x140001cf8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d21`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001d21`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001daf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001daf`

## pseudocode

```c
__int64 __fastcall InstanceIoctlCreateRingBuffer(__int64 a1, __int64 a2)
{
  __int16 v4; // ax
  int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rax
  _DWORD *v10; // [rsp+30h] [rbp-78h] BYREF
  __int64 v11; // [rsp+38h] [rbp-70h] BYREF
  __int64 v12; // [rsp+40h] [rbp-68h] BYREF
  _KEVENT Event; // [rsp+48h] [rbp-60h] BYREF
  _OWORD v14[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v15; // [rsp+80h] [rbp-28h]

  v12 = 0;
  memset(&Event, 0, sizeof(Event));
  memset(v14, 0, sizeof(v14));
  v10 = 0;
  v15 = 0;
  v11 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount > 0x33 )
    {
      LOWORD(v14[0]) = *(_WORD *)(WdfStructures + 408);
      goto LABEL_7;
    }
    v4 = -1;
  }
  else
  {
    v4 = 40;
  }
  LOWORD(v14[0]) = v4;
LABEL_7:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 2128))(
    WdfDriverGlobals,
    a2,
    v14);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _DWORD **, __int64 *))(WdfFunctions_01033 + 2152))(
         WdfDriverGlobals,
         a2,
         8,
         &v10,
         &v12);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v5;
    }
    v7 = 13;
LABEL_12:
    WPP_SF_(v6->AttachedDevice, v7, WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *, _QWORD))(WdfFunctions_01033 + 2160))(
         WdfDriverGlobals,
         a2,
         4,
         &v11,
         0);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v5;
    }
    v7 = 14;
    goto LABEL_12;
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  KeEnterCriticalRegion();
  KeWaitForSingleObject((PVOID)(a1 + 32), Executive, 0, 0, 0);
  if ( *(_DWORD *)(a1 + 4)
    || _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 24), (signed __int64)&Event, 0) )
  {
    KeSetEvent((PRKEVENT)(a1 + 32), 0, 0);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids);
    }
    return 3221225665LL;
  }
  else
  {
    v9 = v11;
    *(_DWORD *)(a1 + 56) = v10[1];
    *(_QWORD *)(a1 + 16) = v9;
    *(_QWORD *)(a1 + 8) = a2;
    InstanceWaitLockRelease(a1);
    result = ChCreateGpadl(*(_QWORD *)(a1 + 288), *v10, (unsigned int)BufferCreated, a1, 1);
    if ( (int)result >= 0 )
      return 259;
    else
      _InterlockedExchange64((volatile __int64 *)(a1 + 24), 0);
  }
  return result;
}

```

## disassembly

```asm
0x140001b70  mov     r11, rsp
0x140001b73  mov     [r11+18h], rbx
0x140001b77  push    rbp
0x140001b78  push    rsi
0x140001b79  push    rdi
0x140001b7a  sub     rsp, 90h
0x140001b81  mov     rax, cs:__security_cookie
0x140001b88  xor     rax, rsp
0x140001b8b  mov     [rsp+0A8h+var_20], rax
0x140001b93  xor     ebp, ebp
0x140001b95  xor     eax, eax
0x140001b97  cmp     cs:WdfClientVersionHigherThanFramework, al
0x140001b9d  xorps   xmm1, xmm1
0x140001ba0  xorps   xmm0, xmm0
0x140001ba3  mov     [r11-68h], rbp
0x140001ba7  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140001bac  mov     [r11-50h], rax
0x140001bb0  mov     rsi, rdx
0x140001bb3  movups  [rsp+0A8h+var_48], xmm1
0x140001bb8  mov     rdi, rcx
0x140001bbb  mov     [r11-78h], rbp
0x140001bbf  movups  [rsp+0A8h+var_38], xmm1
0x140001bc4  mov     [r11-28h], rax
0x140001bc8  mov     [r11-70h], rbp
0x140001bcc  jz      short loc_140001BF3
0x140001bce  cmp     cs:WdfStructureCount, 33h ; '3'
0x140001bd5  jbe     short loc_140001BEC
0x140001bd7  mov     rax, cs:WdfStructures
0x140001bde  movzx   ecx, word ptr [rax+198h]
0x140001be5  mov     word ptr [rsp+0A8h+var_48], cx
0x140001bea  jmp     short loc_140001BFD
0x140001bec  mov     eax, 0FFFFh
0x140001bf1  jmp     short loc_140001BF8
0x140001bf3  mov     eax, 28h ; '('
0x140001bf8  mov     word ptr [rsp+0A8h+var_48], ax
0x140001bfd  mov     rax, cs:WdfFunctions_01033
0x140001c04  lea     r8, [rsp+0A8h+var_48]
0x140001c09  mov     rcx, cs:WdfDriverGlobals
0x140001c10  mov     rax, [rax+850h]
0x140001c17  call    _guard_dispatch_icall
0x140001c1c  mov     rax, cs:WdfFunctions_01033
0x140001c23  lea     rcx, [rsp+0A8h+var_68]
0x140001c28  mov     [rsp+0A8h+Timeout], rcx
0x140001c2d  lea     r9, [rsp+0A8h+var_78]
0x140001c32  mov     rcx, cs:WdfDriverGlobals
0x140001c39  mov     r8d, 8
0x140001c3f  mov     rdx, rsi
0x140001c42  mov     rax, [rax+868h]
0x140001c49  call    _guard_dispatch_icall
0x140001c4e  mov     ebx, eax
0x140001c50  test    eax, eax
0x140001c52  jns     short loc_140001C92
0x140001c54  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c5b  lea     rdx, WPP_GLOBAL_Control
0x140001c62  cmp     rcx, rdx
0x140001c65  jz      short loc_140001C8B
0x140001c67  test    dword ptr [rcx+2Ch], 800000h
0x140001c6e  jz      short loc_140001C8B
0x140001c70  cmp     byte ptr [rcx+29h], 2
0x140001c74  jb      short loc_140001C8B
0x140001c76  mov     edx, 0Dh
0x140001c7b  mov     rcx, [rcx+18h]
0x140001c7f  lea     r8, WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids
0x140001c86  call    WPP_SF_
0x140001c8b  mov     eax, ebx
0x140001c8d  jmp     loc_140001DF7
0x140001c92  mov     rax, cs:WdfFunctions_01033
0x140001c99  lea     r9, [rsp+0A8h+var_70]
0x140001c9e  mov     rcx, cs:WdfDriverGlobals
0x140001ca5  mov     r8d, 4
0x140001cab  mov     rdx, rsi
0x140001cae  mov     [rsp+0A8h+Timeout], rbp
0x140001cb3  mov     rax, [rax+870h]
0x140001cba  call    _guard_dispatch_icall
0x140001cbf  mov     ebx, eax
0x140001cc1  test    eax, eax
0x140001cc3  jns     short loc_140001CEE
0x140001cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ccc  lea     rdx, WPP_GLOBAL_Control
0x140001cd3  cmp     rcx, rdx
0x140001cd6  jz      short loc_140001C8B
0x140001cd8  test    dword ptr [rcx+2Ch], 800000h
0x140001cdf  jz      short loc_140001C8B
0x140001ce1  cmp     byte ptr [rcx+29h], 2
0x140001ce5  jb      short loc_140001C8B
0x140001ce7  mov     edx, 0Eh
0x140001cec  jmp     short loc_140001C7B
0x140001cee  xor     r8d, r8d; State
0x140001cf1  lea     rcx, [rsp+0A8h+Event]; Event
0x140001cf6  xor     edx, edx; Type
0x140001cf8  call    cs:__imp_KeInitializeEvent
0x140001cff  nop     dword ptr [rax+rax+00h]
0x140001d04  call    cs:__imp_KeEnterCriticalRegion
0x140001d0b  nop     dword ptr [rax+rax+00h]
0x140001d10  xor     r9d, r9d; Alertable
0x140001d13  mov     [rsp+0A8h+Timeout], rbp; Timeout
0x140001d18  xor     r8d, r8d; WaitMode
0x140001d1b  lea     rcx, [rdi+20h]; Object
0x140001d1f  xor     edx, edx; WaitReason
0x140001d21  call    cs:__imp_KeWaitForSingleObject
0x140001d28  nop     dword ptr [rax+rax+00h]
0x140001d2d  cmp     [rdi+4], ebp
0x140001d30  jnz     short loc_140001D9A
0x140001d32  lea     rcx, [rsp+0A8h+Event]
0x140001d37  xor     eax, eax
0x140001d39  lock cmpxchg [rdi+18h], rcx
0x140001d3f  jnz     short loc_140001D9A
0x140001d41  mov     rax, [rsp+0A8h+var_78]
0x140001d46  mov     ecx, [rax+4]
0x140001d49  mov     rax, [rsp+0A8h+var_70]
0x140001d4e  mov     [rdi+38h], ecx
0x140001d51  mov     rcx, rdi
0x140001d54  mov     [rdi+10h], rax
0x140001d58  mov     [rdi+8], rsi
0x140001d5c  call    InstanceWaitLockRelease
0x140001d61  mov     rdx, [rsp+0A8h+var_78]
0x140001d66  lea     r8, BufferCreated
0x140001d6d  mov     rcx, [rdi+120h]
0x140001d74  mov     r9, rdi
0x140001d77  mov     dword ptr [rsp+0A8h+Timeout], 1
0x140001d7f  mov     edx, [rdx]
0x140001d81  call    ChCreateGpadl
0x140001d86  test    eax, eax
0x140001d88  jns     short loc_140001D93
0x140001d8a  mov     rcx, rbp
0x140001d8d  xchg    rcx, [rdi+18h]
0x140001d91  jmp     short loc_140001DF7
0x140001d93  mov     eax, 103h
0x140001d98  jmp     short loc_140001DF7
0x140001d9a  xor     r8d, r8d; Wait
0x140001d9d  lea     rcx, [rdi+20h]; Event
0x140001da1  xor     edx, edx; Increment
0x140001da3  call    cs:__imp_KeSetEvent
0x140001daa  nop     dword ptr [rax+rax+00h]
0x140001daf  call    cs:__imp_KeLeaveCriticalRegion
0x140001db6  nop     dword ptr [rax+rax+00h]
0x140001dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001dc2  lea     rdx, WPP_GLOBAL_Control
0x140001dc9  cmp     rcx, rdx
0x140001dcc  jz      short loc_140001DF2
0x140001dce  test    dword ptr [rcx+2Ch], 800000h
0x140001dd5  jz      short loc_140001DF2
0x140001dd7  cmp     byte ptr [rcx+29h], 2
0x140001ddb  jb      short loc_140001DF2
0x140001ddd  mov     rcx, [rcx+18h]
0x140001de1  lea     r8, WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids
0x140001de8  mov     edx, 0Fh
0x140001ded  call    WPP_SF_
0x140001df2  mov     eax, 0C00000C1h
0x140001df7  mov     rcx, [rsp+0A8h+var_20]
0x140001dff  xor     rcx, rsp; StackCookie
0x140001e02  call    __security_check_cookie
0x140001e07  mov     rbx, [rsp+0A8h+arg_10]
0x140001e0f  add     rsp, 90h
0x140001e16  pop     rdi
0x140001e17  pop     rsi
0x140001e18  pop     rbp
0x140001e19  retn
```
