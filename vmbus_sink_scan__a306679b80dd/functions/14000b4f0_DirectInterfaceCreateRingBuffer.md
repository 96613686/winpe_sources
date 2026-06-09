# DirectInterfaceCreateRingBuffer

- ea: `0x14000b4f0`
- end: `0x14000b711`
- name: `DirectInterfaceCreateRingBuffer`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x140004974`
- `0x14000b4f0`
- `0x14000be98`
- `0x14000ec8c`
- `0x14000edc4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b565`
- `ntoskrnl!KeInitializeEvent` at `0x14000b565`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b622`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b622`

## pseudocode

```c
__int64 __fastcall DirectInterfaceCreateRingBuffer(__int64 a1, int a2, int a3, _QWORD *a4)
{
  __int64 v4; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  int Gpadl; // eax
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 v15; // r8
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  v4 = a1 + 8;
  memset(&Event, 0, sizeof(Event));
  *a4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  InstanceWaitLockAcquire(v4, v9, v10);
  if ( *(_DWORD *)(v4 + 4)
    || _InterlockedCompareExchange64((volatile signed __int64 *)(v4 + 24), (signed __int64)&Event, 0) )
  {
    InstanceWaitLockRelease(v4);
    v13 = -1073741631;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        v15,
        a1,
        v4,
        -1073741631,
        *(_QWORD *)&Event.Header.Lock,
        Event.Header.WaitListHead.Flink,
        Event.Header.WaitListHead.Blink);
    }
  }
  else
  {
    *(_DWORD *)(v4 + 56) = a3;
    InstanceWaitLockRelease(v4);
    Gpadl = ChCreateGpadl(*(_QWORD *)(v4 + 288), a2, (__int64)DirectInterfaceBufferCreatedSync, v4, 1);
    v13 = Gpadl;
    if ( Gpadl >= 0 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( *(_DWORD *)(v4 + 4) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            v14,
            a1,
            v4,
            0,
            *(_QWORD *)&Event.Header.Lock,
            Event.Header.WaitListHead.Flink,
            Event.Header.WaitListHead.Blink);
        }
        v13 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqd(
            WPP_GLOBAL_Control->AttachedDevice,
            23,
            v14,
            a1,
            v4,
            v13,
            *(_QWORD *)&Event.Header.Lock,
            Event.Header.WaitListHead.Flink,
            Event.Header.WaitListHead.Blink);
        }
        v13 = -1073741823;
      }
      ChGetSystemAddressForGpadl(*(_QWORD *)(v4 + 288), *(_DWORD *)(v4 + 4), a4);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        v12,
        a1,
        v4,
        Gpadl,
        *(_QWORD *)&Event.Header.Lock,
        Event.Header.WaitListHead.Flink,
        Event.Header.WaitListHead.Blink);
    }
    _InterlockedExchange64((volatile __int64 *)(v4 + 24), 0);
  }
  return v13;
}

```

## disassembly

```asm
0x14000b4f0  push    rbx
0x14000b4f2  push    rbp
0x14000b4f3  push    rsi
0x14000b4f4  push    rdi
0x14000b4f5  push    r13
0x14000b4f7  push    r14
0x14000b4f9  sub     rsp, 58h
0x14000b4fd  xor     eax, eax
0x14000b4ff  lea     rbx, [rcx+8]
0x14000b503  xorps   xmm0, xmm0
0x14000b506  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14000b50b  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14000b510  mov     [r9], rax
0x14000b513  mov     r14, r9
0x14000b516  mov     edi, r8d
0x14000b519  mov     ebp, edx
0x14000b51b  mov     rsi, rcx
0x14000b51e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b525  lea     r13, WPP_GLOBAL_Control
0x14000b52c  cmp     rcx, r13
0x14000b52f  jz      short loc_14000B55B
0x14000b531  mov     eax, [rcx+2Ch]
0x14000b534  test    al, 10h
0x14000b536  jz      short loc_14000B55B
0x14000b538  cmp     byte ptr [rcx+29h], 4
0x14000b53c  jb      short loc_14000B55B
0x14000b53e  mov     rcx, [rcx+18h]
0x14000b542  lea     r8, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids
0x14000b549  mov     edx, 13h
0x14000b54e  mov     [rsp+88h+Timeout], rbx
0x14000b553  mov     r9, rsi
0x14000b556  call    WPP_SF_qq
0x14000b55b  xor     r8d, r8d; State
0x14000b55e  lea     rcx, [rsp+88h+Event]; Event
0x14000b563  xor     edx, edx; Type
0x14000b565  call    cs:__imp_KeInitializeEvent
0x14000b56c  nop     dword ptr [rax+rax+00h]
0x14000b571  mov     rcx, rbx
0x14000b574  call    InstanceWaitLockAcquire
0x14000b579  cmp     dword ptr [rbx+4], 0
0x14000b57d  jnz     loc_14000B6C1
0x14000b583  lea     rcx, [rsp+88h+Event]
0x14000b588  xor     eax, eax
0x14000b58a  lock cmpxchg [rbx+18h], rcx
0x14000b590  jnz     loc_14000B6C1
0x14000b596  mov     rcx, rbx
0x14000b599  mov     [rbx+38h], edi
0x14000b59c  call    InstanceWaitLockRelease
0x14000b5a1  mov     rcx, [rbx+120h]
0x14000b5a8  lea     r8, DirectInterfaceBufferCreatedSync
0x14000b5af  mov     r9, rbx
0x14000b5b2  mov     dword ptr [rsp+88h+Timeout], 1
0x14000b5ba  mov     edx, ebp
0x14000b5bc  call    ChCreateGpadl
0x14000b5c1  mov     edi, eax
0x14000b5c3  test    eax, eax
0x14000b5c5  jns     short loc_14000B60C
0x14000b5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5ce  cmp     rcx, r13
0x14000b5d1  jz      loc_14000B6B9
0x14000b5d7  mov     edx, [rcx+2Ch]
0x14000b5da  test    dl, 10h
0x14000b5dd  jz      loc_14000B6B9
0x14000b5e3  cmp     byte ptr [rcx+29h], 2
0x14000b5e7  jb      loc_14000B6B9
0x14000b5ed  mov     rcx, [rcx+18h]
0x14000b5f1  mov     edx, 15h
0x14000b5f6  mov     [rsp+88h+var_60], eax
0x14000b5fa  mov     r9, rsi
0x14000b5fd  mov     [rsp+88h+Timeout], rbx
0x14000b602  call    WPP_SF_qqd
0x14000b607  jmp     loc_14000B6B9
0x14000b60c  xor     r9d, r9d; Alertable
0x14000b60f  mov     [rsp+88h+Timeout], 0; Timeout
0x14000b618  xor     r8d, r8d; WaitMode
0x14000b61b  lea     rcx, [rsp+88h+Event]; Object
0x14000b620  xor     edx, edx; WaitReason
0x14000b622  call    cs:__imp_KeWaitForSingleObject
0x14000b629  nop     dword ptr [rax+rax+00h]
0x14000b62e  cmp     dword ptr [rbx+4], 0
0x14000b632  jz      short loc_14000B66F
0x14000b634  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b63b  cmp     rcx, r13
0x14000b63e  jz      short loc_14000B66B
0x14000b640  mov     eax, [rcx+2Ch]
0x14000b643  test    al, 10h
0x14000b645  jz      short loc_14000B66B
0x14000b647  cmp     byte ptr [rcx+29h], 4
0x14000b64b  jb      short loc_14000B66B
0x14000b64d  mov     rcx, [rcx+18h]
0x14000b651  mov     edx, 16h
0x14000b656  mov     [rsp+88h+var_60], 0
0x14000b65e  mov     r9, rsi
0x14000b661  mov     [rsp+88h+Timeout], rbx
0x14000b666  call    WPP_SF_qqd
0x14000b66b  xor     edi, edi
0x14000b66d  jmp     short loc_14000B6A7
0x14000b66f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b676  cmp     rcx, r13
0x14000b679  jz      short loc_14000B6A2
0x14000b67b  mov     eax, [rcx+2Ch]
0x14000b67e  test    al, 10h
0x14000b680  jz      short loc_14000B6A2
0x14000b682  cmp     byte ptr [rcx+29h], 2
0x14000b686  jb      short loc_14000B6A2
0x14000b688  mov     rcx, [rcx+18h]
0x14000b68c  mov     edx, 17h
0x14000b691  mov     [rsp+88h+var_60], edi
0x14000b695  mov     r9, rsi
0x14000b698  mov     [rsp+88h+Timeout], rbx
0x14000b69d  call    WPP_SF_qqd
0x14000b6a2  mov     edi, 0C0000001h
0x14000b6a7  mov     edx, [rbx+4]
0x14000b6aa  mov     r8, r14
0x14000b6ad  mov     rcx, [rbx+120h]
0x14000b6b4  call    ChGetSystemAddressForGpadl
0x14000b6b9  xor     eax, eax
0x14000b6bb  xchg    rax, [rbx+18h]
0x14000b6bf  jmp     short loc_14000B701
0x14000b6c1  mov     rcx, rbx
0x14000b6c4  call    InstanceWaitLockRelease
0x14000b6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6d0  mov     edi, 0C00000C1h
0x14000b6d5  cmp     rcx, r13
0x14000b6d8  jz      short loc_14000B701
0x14000b6da  mov     eax, [rcx+2Ch]
0x14000b6dd  test    al, 10h
0x14000b6df  jz      short loc_14000B701
0x14000b6e1  cmp     byte ptr [rcx+29h], 2
0x14000b6e5  jb      short loc_14000B701
0x14000b6e7  mov     rcx, [rcx+18h]
0x14000b6eb  mov     edx, 14h
0x14000b6f0  mov     [rsp+88h+var_60], edi
0x14000b6f4  mov     r9, rsi
0x14000b6f7  mov     [rsp+88h+Timeout], rbx
0x14000b6fc  call    WPP_SF_qqd
0x14000b701  mov     eax, edi
0x14000b703  add     rsp, 58h
0x14000b707  pop     r14
0x14000b709  pop     r13
0x14000b70b  pop     rdi
0x14000b70c  pop     rsi
0x14000b70d  pop     rbp
0x14000b70e  pop     rbx
0x14000b70f  retn
```
