# RegisterServiceStopCallback(void * *,ushort const *,void *,void (*)(void *,uchar),void *,_SVCHOST_GLOBAL_DATA *)

- ea: `0x18000eab0`
- end: `0x18000eba3`
- name: `?RegisterServiceStopCallback@@YAJPEAPEAXPEBGPEAXP6AX2E@Z2PEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(void **, const unsigned __int16 *, void *, void (*)(void *, unsigned __int8), void *, __int64 (__fastcall **)(void **, const WCHAR *, void *, void (__fastcall *)(void *, unsigned __int8), __int64 *, int))`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800018c0`

## callees

- `0x180007f28`
- `0x18000e204`
- `0x18000eab0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall RegisterServiceStopCallback(
        void **a1,
        const unsigned __int16 *a2,
        void *a3,
        void (*a4)(void *, unsigned __int8),
        void *a5,
        __int64 (__fastcall **a6)(void **, const WCHAR *, void *, void (__fastcall *)(void *, unsigned __int8), __int64 *, int))
{
  unsigned int v7; // ebx
  CPnPNotification *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax

  if ( a1 )
  {
    if ( a6 )
    {
      v10 = a6[24](a1, L"WpdBusEnum", a3, CService::StopServiceCallback, &_Service, 8);
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
        return v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        return v7;
      }
      v9 = 73;
    }
    else
    {
      v7 = -2147418113;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        return v7;
      }
      v9 = 72;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v7);
    return v7;
  }
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, "phCallback");
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000eab0  push    rbx
0x18000eab2  sub     rsp, 40h
0x18000eab6  test    rcx, rcx
0x18000eab9  jnz     short loc_18000EAFA
0x18000eabb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eac2  lea     rax, WPP_GLOBAL_Control
0x18000eac9  cmp     rcx, rax
0x18000eacc  jz      short loc_18000EAF0
0x18000eace  test    byte ptr [rcx+1Ch], 2
0x18000ead2  jz      short loc_18000EAF0
0x18000ead4  mov     rcx, [rcx+10h]
0x18000ead8  lea     r9, aPhcallback; "phCallback"
0x18000eadf  mov     edx, 47h ; 'G'
0x18000eae4  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x18000eaeb  call    WPP_SF_s
0x18000eaf0  mov     eax, 80070057h
0x18000eaf5  jmp     loc_18000EB9D
0x18000eafa  mov     rax, [rsp+48h+arg_28]
0x18000eaff  test    rax, rax
0x18000eb02  jnz     short loc_18000EB29
0x18000eb04  mov     ebx, 8000FFFFh
0x18000eb09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb10  lea     rax, WPP_GLOBAL_Control
0x18000eb17  cmp     rcx, rax
0x18000eb1a  jz      short loc_18000EB9B
0x18000eb1c  test    byte ptr [rcx+1Ch], 2
0x18000eb20  jz      short loc_18000EB9B
0x18000eb22  mov     edx, 48h ; 'H'
0x18000eb27  jmp     short loc_18000EB88
0x18000eb29  mov     rax, [rax+0C0h]
0x18000eb30  lea     rdx, ?_Service@@3VCService@@A; CService _Service
0x18000eb37  mov     [rsp+48h+var_20], 8
0x18000eb3f  lea     r9, ?StopServiceCallback@CService@@KAXPEAXE@Z; CService::StopServiceCallback(void *,uchar)
0x18000eb46  mov     [rsp+48h+var_28], rdx
0x18000eb4b  lea     rdx, ServiceName; "WpdBusEnum"
0x18000eb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb57  mov     ebx, eax
0x18000eb59  test    eax, eax
0x18000eb5b  jle     short loc_18000EB66
0x18000eb5d  movzx   ebx, ax
0x18000eb60  or      ebx, 80070000h
0x18000eb66  test    ebx, ebx
0x18000eb68  jns     short loc_18000EB9B
0x18000eb6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb71  lea     rax, WPP_GLOBAL_Control
0x18000eb78  cmp     rcx, rax
0x18000eb7b  jz      short loc_18000EB9B
0x18000eb7d  test    byte ptr [rcx+1Ch], 2
0x18000eb81  jz      short loc_18000EB9B
0x18000eb83  mov     edx, 49h ; 'I'
0x18000eb88  mov     rcx, [rcx+10h]
0x18000eb8c  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x18000eb93  mov     r9d, ebx
0x18000eb96  call    WPP_SF_d
0x18000eb9b  mov     eax, ebx
0x18000eb9d  add     rsp, 40h
0x18000eba1  pop     rbx
0x18000eba2  retn
```
