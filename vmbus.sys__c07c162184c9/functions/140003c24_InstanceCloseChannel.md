# InstanceCloseChannel

- ea: `0x140003c24`
- end: `0x140003d55`
- name: `InstanceCloseChannel`
- size: `305`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140006a70`
- `0x140007310`
- `0x14000b720`
- `0x140027d30`
- `0x140028138`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x14000389c`
- `0x140003c24`
- `0x14000ef68`
- `0x1400103d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140003c4e`
- `ntoskrnl!KeInitializeEvent` at `0x140003c4e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003d13`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003d13`

## pseudocode

```c
__int64 __fastcall InstanceCloseChannel(__int64 a1)
{
  char v3; // si
  _QWORD *v4; // rdi
  __int64 v5; // rdx
  struct _KEVENT Object; // [rsp+30h] [rbp-28h] BYREF

  memset(&Object, 0, sizeof(Object));
  KeInitializeEvent(&Object, NotificationEvent, 0);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 88), (signed __int64)&Object, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x13u,
        (__int64)WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids);
    }
    return 3221225665LL;
  }
  else
  {
    v3 = 0;
    v4 = (_QWORD *)(a1 + 288);
    if ( *(_BYTE *)(a1 + 304) )
    {
      ChClientCloseChannel(*v4);
      *(_BYTE *)(a1 + 304) = 0;
    }
    InstanceWaitLockAcquire(a1);
    v5 = *(unsigned int *)(a1 + 4);
    if ( (_DWORD)v5 )
    {
      v3 = 1;
      ChTeardownGpadl(*v4, v5, InstanceIoctlGpadlTorndown, a1);
    }
    InstanceWaitLockRelease(a1);
    if ( v3 )
    {
      KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
      InstanceWaitLockAcquire(a1);
      *(_DWORD *)(a1 + 4) = 0;
      _InterlockedExchange64((volatile __int64 *)(a1 + 24), 0);
      InstanceWaitLockRelease(a1);
    }
    _InterlockedExchange64((volatile __int64 *)(a1 + 88), 0);
    return 0;
  }
}

```

## disassembly

```asm
0x140003c24  mov     r11, rsp
0x140003c27  mov     [r11+8], rbx
0x140003c2b  mov     [r11+10h], rsi
0x140003c2f  push    rdi
0x140003c30  sub     rsp, 50h
0x140003c34  xorps   xmm0, xmm0
0x140003c37  mov     rbx, rcx
0x140003c3a  xor     eax, eax
0x140003c3c  lea     rcx, [r11-28h]; Event
0x140003c40  movups  xmmword ptr [rsp+58h+Object.Header], xmm0
0x140003c45  xor     r8d, r8d; State
0x140003c48  mov     [r11-18h], rax
0x140003c4c  xor     edx, edx; Type
0x140003c4e  call    cs:__imp_KeInitializeEvent
0x140003c55  nop     dword ptr [rax+rax+00h]
0x140003c5a  lea     rcx, [rsp+58h+Object]
0x140003c5f  xor     eax, eax
0x140003c61  lock cmpxchg [rbx+58h], rcx
0x140003c67  jz      short loc_140003CAA
0x140003c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c70  lea     rax, WPP_GLOBAL_Control
0x140003c77  cmp     rcx, rax
0x140003c7a  jz      short loc_140003CA0
0x140003c7c  test    dword ptr [rcx+2Ch], 800000h
0x140003c83  jz      short loc_140003CA0
0x140003c85  cmp     byte ptr [rcx+29h], 2
0x140003c89  jb      short loc_140003CA0
0x140003c8b  mov     rcx, [rcx+18h]
0x140003c8f  lea     r8, WPP_a886dd093f9a3dd20830e02cab6c0d73_Traceguids
0x140003c96  mov     edx, 13h
0x140003c9b  call    WPP_SF_
0x140003ca0  mov     eax, 0C00000C1h
0x140003ca5  jmp     loc_140003D44
0x140003caa  xor     sil, sil
0x140003cad  lea     rdi, [rbx+120h]
0x140003cb4  cmp     [rbx+130h], sil
0x140003cbb  jz      short loc_140003CCC
0x140003cbd  mov     rcx, [rdi]
0x140003cc0  call    ChClientCloseChannel
0x140003cc5  mov     [rbx+130h], sil
0x140003ccc  mov     rcx, rbx
0x140003ccf  call    InstanceWaitLockAcquire
0x140003cd4  mov     edx, [rbx+4]
0x140003cd7  test    edx, edx
0x140003cd9  jz      short loc_140003CF0
0x140003cdb  mov     rcx, [rdi]
0x140003cde  lea     r8, InstanceIoctlGpadlTorndown
0x140003ce5  mov     r9, rbx
0x140003ce8  mov     sil, 1
0x140003ceb  call    ChTeardownGpadl
0x140003cf0  mov     rcx, rbx
0x140003cf3  call    InstanceWaitLockRelease
0x140003cf8  test    sil, sil
0x140003cfb  jz      short loc_140003D3C
0x140003cfd  xor     r9d, r9d; Alertable
0x140003d00  mov     [rsp+58h+Timeout], 0; Timeout
0x140003d09  xor     r8d, r8d; WaitMode
0x140003d0c  lea     rcx, [rsp+58h+Object]; Object
0x140003d11  xor     edx, edx; WaitReason
0x140003d13  call    cs:__imp_KeWaitForSingleObject
0x140003d1a  nop     dword ptr [rax+rax+00h]
0x140003d1f  mov     rcx, rbx
0x140003d22  call    InstanceWaitLockAcquire
0x140003d27  xor     eax, eax
0x140003d29  mov     dword ptr [rbx+4], 0
0x140003d30  xchg    rax, [rbx+18h]
0x140003d34  mov     rcx, rbx
0x140003d37  call    InstanceWaitLockRelease
0x140003d3c  xor     eax, eax
0x140003d3e  xchg    rax, [rbx+58h]
0x140003d42  xor     eax, eax
0x140003d44  mov     rbx, [rsp+58h+arg_0]
0x140003d49  mov     rsi, [rsp+58h+arg_8]
0x140003d4e  add     rsp, 50h
0x140003d52  pop     rdi
0x140003d53  retn
```
