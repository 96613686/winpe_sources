# VsmmPhuStorepHvPartitionMirrorTeardown

- ea: `0x1400b6730`
- end: `0x1400b68d4`
- name: `VsmmPhuStorepHvPartitionMirrorTeardown`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400b2318`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000918c`
- `0x14000a4e0`
- `0x140021650`
- `0x140024754`
- `0x1400b6730`

## import_xrefs

- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400b687b`
- `ntoskrnl!KeRemoveQueueDpcEx` at `0x1400b687b`
- `ntoskrnl!KeClearEvent` at `0x1400b688a`
- `ntoskrnl!KeClearEvent` at `0x1400b688a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b6835`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b6835`

## pseudocode

```c
NTSTATUS __fastcall VsmmPhuStorepHvPartitionMirrorTeardown(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  struct _KEVENT *v4; // rdi
  int v5; // r9d
  int v6; // [rsp+30h] [rbp-29h] BYREF
  __int64 v7; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v9[16]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v10[16]; // [rsp+70h] [rbp+17h] BYREF
  int *v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]
  __int64 *v13; // [rsp+90h] [rbp+37h]
  __int64 v14; // [rsp+98h] [rbp+3Fh]

  if ( *(_DWORD *)(a1 + 8660) )
  {
    v4 = (struct _KEVENT *)(a1 + 8728);
    if ( *(_DWORD *)(a1 + 8660) != 3 )
      KeWaitForSingleObject((PVOID)(a1 + 8728), Executive, 0, 0, 0);
    v5 = *(_DWORD *)(a1 + 8752);
    if ( v5 < 0 )
      VidTraceErrorStatusPartitionInternal0(
        (unsigned int)"VsmmPhuStorepHvPartitionMirrorTeardown",
        (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
        4134,
        v5,
        a1 + 656);
    LOBYTE(a2) = 1;
    KeRemoveQueueDpcEx(a1 + 8664, a2);
    KeClearEvent(v4);
    _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8660), 0, 3);
    return VidMessagePoolRequiredCountDec(a1, 1);
  }
  else
  {
    result = dword_140064110;
    if ( (unsigned int)dword_140064110 > 4 )
    {
      result = tlgKeywordOn(&dword_140064110, 256);
      if ( (_BYTE)result )
      {
        tlgCreate1Sz_char(v9, "VsmmPhuStorepHvPartitionMirrorTeardown");
        tlgCreate1Sz_char(v10, "onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c");
        v6 = 4114;
        v11 = &v6;
        v7 = *(_QWORD *)(a1 + 648);
        v12 = 4;
        v13 = &v7;
        v14 = 8;
        return tlgWriteTransfer_EtwWriteTransfer(
                 (__int64)&dword_140064110,
                 (unsigned __int8 *)byte_14004F859,
                 0,
                 0,
                 6u,
                 &v8);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400b6730  mov     [rsp-8+arg_8], rbx
0x1400b6735  mov     [rsp-8+arg_10], rdi
0x1400b673a  push    rbp
0x1400b673b  lea     rbp, [rsp-57h]
0x1400b6740  sub     rsp, 0B0h
0x1400b6747  mov     rax, cs:__security_cookie
0x1400b674e  xor     rax, rsp
0x1400b6751  mov     [rbp+57h+var_10], rax
0x1400b6755  mov     eax, [rcx+21D4h]
0x1400b675b  mov     rbx, rcx
0x1400b675e  test    eax, eax
0x1400b6760  jnz     loc_1400B680F
0x1400b6766  mov     eax, cs:dword_140064110
0x1400b676c  cmp     eax, 4
0x1400b676f  jbe     loc_1400B68B2
0x1400b6775  mov     edx, 100h
0x1400b677a  lea     rcx, dword_140064110
0x1400b6781  call    _tlgKeywordOn
0x1400b6786  test    al, al
0x1400b6788  jz      loc_1400B68B2
0x1400b678e  lea     rdx, aVsmmphustoreph_2; "VsmmPhuStorepHvPartitionMirrorTeardown"
0x1400b6795  lea     rcx, [rbp+57h+var_50]
0x1400b6799  call    _tlgCreate1Sz_char
0x1400b679e  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b67a5  lea     rcx, [rbp+57h+var_40]
0x1400b67a9  call    _tlgCreate1Sz_char
0x1400b67ae  lea     rax, [rbp+57h+var_80]
0x1400b67b2  mov     [rbp+57h+var_80], 1012h
0x1400b67b9  mov     [rbp+57h+var_30], rax
0x1400b67bd  lea     rdx, byte_14004F859
0x1400b67c4  mov     rax, [rbx+288h]
0x1400b67cb  lea     rcx, dword_140064110
0x1400b67d2  mov     [rbp+57h+var_78], rax
0x1400b67d6  xor     r9d, r9d
0x1400b67d9  lea     rax, [rbp+57h+var_78]
0x1400b67dd  mov     [rbp+57h+var_28], 4
0x1400b67e5  mov     [rbp+57h+var_20], rax
0x1400b67e9  xor     r8d, r8d
0x1400b67ec  lea     rax, [rbp+57h+var_70]
0x1400b67f0  mov     [rbp+57h+var_18], 8
0x1400b67f8  mov     [rsp+0B0h+var_88], rax
0x1400b67fd  mov     dword ptr [rsp+0B0h+Timeout], 6
0x1400b6805  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b680a  jmp     loc_1400B68B2
0x1400b680f  mov     eax, [rcx+21D4h]
0x1400b6815  lea     rdi, [rcx+2218h]
0x1400b681c  cmp     eax, 3
0x1400b681f  jz      short loc_1400B6841
0x1400b6821  xor     r9d, r9d; Alertable
0x1400b6824  mov     [rsp+0B0h+Timeout], 0; Timeout
0x1400b682d  xor     r8d, r8d; WaitMode
0x1400b6830  xor     edx, edx; WaitReason
0x1400b6832  mov     rcx, rdi; Object
0x1400b6835  call    cs:__imp_KeWaitForSingleObject
0x1400b683c  nop     dword ptr [rax+rax+00h]
0x1400b6841  mov     r9d, [rbx+2230h]
0x1400b6848  test    r9d, r9d
0x1400b684b  jns     short loc_1400B6872
0x1400b684d  lea     rax, [rbx+290h]
0x1400b6854  mov     r8d, 1026h
0x1400b685a  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b6861  mov     [rsp+0B0h+Timeout], rax
0x1400b6866  lea     rcx, aVsmmphustoreph_2; "VsmmPhuStorepHvPartitionMirrorTeardown"
0x1400b686d  call    VidTraceErrorStatusPartitionInternal0
0x1400b6872  lea     rcx, [rbx+21D8h]
0x1400b6879  mov     dl, 1
0x1400b687b  call    cs:__imp_KeRemoveQueueDpcEx
0x1400b6882  nop     dword ptr [rax+rax+00h]
0x1400b6887  mov     rcx, rdi; Event
0x1400b688a  call    cs:__imp_KeClearEvent
0x1400b6891  nop     dword ptr [rax+rax+00h]
0x1400b6896  xor     r8d, r8d
0x1400b6899  lea     eax, [r8+3]
0x1400b689d  lock cmpxchg [rbx+21D4h], r8d
0x1400b68a6  lea     edx, [r8+1]
0x1400b68aa  mov     rcx, rbx
0x1400b68ad  call    VidMessagePoolRequiredCountDec
0x1400b68b2  mov     rcx, [rbp+57h+var_10]
0x1400b68b6  xor     rcx, rsp; StackCookie
0x1400b68b9  call    __security_check_cookie
0x1400b68be  lea     r11, [rsp+0B0h+var_s0]
0x1400b68c6  mov     rbx, [r11+18h]
0x1400b68ca  mov     rdi, [r11+20h]
0x1400b68ce  mov     rsp, r11
0x1400b68d1  pop     rbp
0x1400b68d2  retn
```
