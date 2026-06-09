# BoundSubscription::OnSubscribeComplete(void)

- ea: `0x18000eaf0`
- end: `0x18000ec1b`
- name: `?OnSubscribeComplete@BoundSubscription@@AEAAXXZ`
- size: `299`
- prototype: `void __fastcall(BoundSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010320`

## callees

- `0x18000c0e8`
- `0x18000c2d8`
- `0x18000cfa0`
- `0x18000eaf0`
- `0x18000f7b0`
- `0x180011938`

## pseudocode

```c
void __fastcall BoundSubscription::OnSubscribeComplete(BoundSubscription *this)
{
  _QWORD *v2; // r8
  _QWORD *v3; // r9
  int v4; // ebx
  _QWORD *v5; // rcx
  _QWORD *v6; // r9

  if ( *((_DWORD *)this + 14) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = (_QWORD *)((char *)this + 72);
      if ( *((_QWORD *)this + 12) >= 8u )
        v2 = (_QWORD *)*v2;
      v3 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
      if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
        v3 = (_QWORD *)*v3;
      WPP_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (_DWORD)v2,
        (_DWORD)v3,
        (__int64)v2,
        (char)this,
        *((_DWORD *)this + 78));
    }
    BoundSubscription::RecordLastError(
      (struct _FILETIME *)this,
      *((_DWORD *)this + 78),
      *((struct WSMAN_OBJECT **)this + 40));
    v4 = *((_DWORD *)this + 78);
    BoundSubscription::ExitSubscribingState(this, v4 != 0);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = (_QWORD *)((char *)this + 72);
        if ( *((_QWORD *)this + 12) >= 8u )
          v5 = (_QWORD *)*v5;
        v6 = (_QWORD *)(*((_QWORD *)this + 8) + 56LL);
        if ( *(_QWORD *)(*((_QWORD *)this + 8) + 80LL) >= 8u )
          v6 = (_QWORD *)*v6;
        WPP_SF_SSqD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v6,
          (__int64)v5,
          (char)this,
          *((_DWORD *)this + 78));
      }
      BoundSubscription::EnterRetryingState(this);
    }
    else
    {
      BoundSubscription::EnterReceivingState(this);
    }
  }
}

```

## disassembly

```asm
0x18000eaf0  mov     [rsp+arg_0], rbx
0x18000eaf5  mov     [rsp+arg_8], rsi
0x18000eafa  push    rdi
0x18000eafb  sub     rsp, 40h
0x18000eaff  cmp     dword ptr [rcx+38h], 0
0x18000eb03  mov     rdi, rcx
0x18000eb06  jz      loc_18000EC0B
0x18000eb0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb13  lea     rsi, WPP_GLOBAL_Control
0x18000eb1a  cmp     rcx, rsi
0x18000eb1d  jz      short loc_18000EB6F
0x18000eb1f  test    byte ptr [rcx+1Ch], 10h
0x18000eb23  jz      short loc_18000EB6F
0x18000eb25  cmp     byte ptr [rcx+19h], 5
0x18000eb29  jb      short loc_18000EB6F
0x18000eb2b  mov     r10d, [rdi+138h]
0x18000eb32  lea     r8, [rdi+48h]
0x18000eb36  cmp     qword ptr [r8+18h], 8
0x18000eb3b  jb      short loc_18000EB40
0x18000eb3d  mov     r8, [r8]
0x18000eb40  mov     r9, [rdi+40h]
0x18000eb44  add     r9, 38h ; '8'
0x18000eb48  cmp     qword ptr [r9+18h], 8
0x18000eb4d  jb      short loc_18000EB52
0x18000eb4f  mov     r9, [r9]
0x18000eb52  mov     rcx, [rcx+10h]
0x18000eb56  mov     edx, 3Ch ; '<'
0x18000eb5b  mov     [rsp+48h+var_18], r10d
0x18000eb60  mov     [rsp+48h+var_20], rdi
0x18000eb65  mov     [rsp+48h+var_28], r8
0x18000eb6a  call    WPP_SF_SSqD
0x18000eb6f  mov     r8, [rdi+140h]; struct WSMAN_OBJECT *
0x18000eb76  mov     rcx, rdi; this
0x18000eb79  mov     edx, [rdi+138h]; unsigned int
0x18000eb7f  call    ?RecordLastError@BoundSubscription@@AEAAXKPEAUWSMAN_OBJECT@@@Z; BoundSubscription::RecordLastError(ulong,WSMAN_OBJECT *)
0x18000eb84  mov     ebx, [rdi+138h]
0x18000eb8a  mov     rcx, rdi; this
0x18000eb8d  test    ebx, ebx
0x18000eb8f  setnz   dl; bool
0x18000eb92  call    ?ExitSubscribingState@BoundSubscription@@AEAAX_N@Z; BoundSubscription::ExitSubscribingState(bool)
0x18000eb97  test    ebx, ebx
0x18000eb99  jnz     short loc_18000EBA5
0x18000eb9b  mov     rcx, rdi; this
0x18000eb9e  call    ?EnterReceivingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterReceivingState(void)
0x18000eba3  jmp     short loc_18000EC0B
0x18000eba5  mov     r8, cs:WPP_GLOBAL_Control
0x18000ebac  cmp     r8, rsi
0x18000ebaf  jz      short loc_18000EC03
0x18000ebb1  test    byte ptr [r8+1Ch], 10h
0x18000ebb6  jz      short loc_18000EC03
0x18000ebb8  cmp     byte ptr [r8+19h], 2
0x18000ebbd  jb      short loc_18000EC03
0x18000ebbf  mov     r10d, [rdi+138h]
0x18000ebc6  lea     rcx, [rdi+48h]
0x18000ebca  cmp     qword ptr [rcx+18h], 8
0x18000ebcf  jb      short loc_18000EBD4
0x18000ebd1  mov     rcx, [rcx]
0x18000ebd4  mov     r9, [rdi+40h]
0x18000ebd8  add     r9, 38h ; '8'
0x18000ebdc  cmp     qword ptr [r9+18h], 8
0x18000ebe1  jb      short loc_18000EBE6
0x18000ebe3  mov     r9, [r9]
0x18000ebe6  mov     [rsp+48h+var_18], r10d
0x18000ebeb  mov     edx, 3Dh ; '='
0x18000ebf0  mov     [rsp+48h+var_20], rdi
0x18000ebf5  mov     [rsp+48h+var_28], rcx
0x18000ebfa  mov     rcx, [r8+10h]
0x18000ebfe  call    WPP_SF_SSqD
0x18000ec03  mov     rcx, rdi; this
0x18000ec06  call    ?EnterRetryingState@BoundSubscription@@AEAAXXZ; BoundSubscription::EnterRetryingState(void)
0x18000ec0b  mov     rbx, [rsp+48h+arg_0]
0x18000ec10  mov     rsi, [rsp+48h+arg_8]
0x18000ec15  add     rsp, 40h
0x18000ec19  pop     rdi
0x18000ec1a  retn
```
