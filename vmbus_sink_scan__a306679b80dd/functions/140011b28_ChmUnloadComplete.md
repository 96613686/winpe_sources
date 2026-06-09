# ChmUnloadComplete

- ea: `0x140011b28`
- end: `0x140011c37`
- name: `ChmUnloadComplete`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010ff8`

## callees

- `0x140011b28`
- `0x140012268`
- `0x140012a30`
- `0x140012a68`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140011bf1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140011bf1`
- `ntoskrnl!KeSetEvent` at `0x140011c19`
- `ntoskrnl!KeSetEvent` at `0x140011c19`
- `ntoskrnl!ExAcquireFastMutex` at `0x140011b94`
- `ntoskrnl!ExAcquireFastMutex` at `0x140011b94`
- `ntoskrnl!KeResetEvent` at `0x140011ba4`
- `ntoskrnl!KeResetEvent` at `0x140011ba4`

## pseudocode

```c
__int64 __fastcall ChmUnloadComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *i; // rdi
  __int64 v5; // rcx
  struct _KEVENT *v6; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF__guid_id(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      a1 + 128,
      *(_QWORD *)(a1 + 120),
      *(_QWORD *)(a1 + 992) != 0);
  }
  *(_QWORD *)(a1 + 168) = 0;
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 432));
  KeResetEvent((PRKEVENT)(a1 + 56));
  for ( i = *(__int64 **)(a1 + 616); i != (__int64 *)(a1 + 616); i = (__int64 *)*i )
  {
    v5 = i[29];
    *((_BYTE *)i + 733) = 1;
    *((_DWORD *)i + 6) = 0;
    if ( v5 )
    {
      XPartDestroyInterrupt();
      i[29] = 0;
    }
  }
  ExReleaseFastMutex((PFAST_MUTEX)(a1 + 432));
  v6 = *(struct _KEVENT **)(a1 + 992);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 992) = 0;
    KeSetEvent(v6, 0, 0);
  }
  return XPartDeref(a1);
}

```

## disassembly

```asm
0x140011b28  push    rbx
0x140011b2a  push    rbp
0x140011b2b  push    rsi
0x140011b2c  push    rdi
0x140011b2d  sub     rsp, 38h
0x140011b31  mov     rbx, rcx
0x140011b34  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b3b  lea     rax, WPP_GLOBAL_Control
0x140011b42  cmp     rcx, rax
0x140011b45  jz      short loc_140011B7F
0x140011b47  test    dword ptr [rcx+2Ch], 80000h
0x140011b4e  jz      short loc_140011B7F
0x140011b50  cmp     byte ptr [rcx+29h], 4
0x140011b54  jb      short loc_140011B7F
0x140011b56  mov     rcx, [rcx+18h]
0x140011b5a  lea     r9, [rbx+80h]
0x140011b61  xor     eax, eax
0x140011b63  cmp     [rbx+3E0h], rax
0x140011b6a  setnz   al
0x140011b6d  mov     [rsp+58h+var_30], eax
0x140011b71  mov     rax, [rbx+78h]
0x140011b75  mov     [rsp+58h+var_38], rax
0x140011b7a  call    WPP_SF__guid_id
0x140011b7f  lea     rbp, [rbx+1B0h]
0x140011b86  mov     qword ptr [rbx+0A8h], 0
0x140011b91  mov     rcx, rbp; FastMutex
0x140011b94  call    cs:__imp_ExAcquireFastMutex
0x140011b9b  nop     dword ptr [rax+rax+00h]
0x140011ba0  lea     rcx, [rbx+38h]; Event
0x140011ba4  call    cs:__imp_KeResetEvent
0x140011bab  nop     dword ptr [rax+rax+00h]
0x140011bb0  lea     rsi, [rbx+268h]
0x140011bb7  mov     rdi, [rsi]
0x140011bba  jmp     short loc_140011BE9
0x140011bbc  mov     rcx, [rdi+0E8h]
0x140011bc3  mov     byte ptr [rdi+2DDh], 1
0x140011bca  mov     dword ptr [rdi+18h], 0
0x140011bd1  test    rcx, rcx
0x140011bd4  jz      short loc_140011BE6
0x140011bd6  call    XPartDestroyInterrupt
0x140011bdb  mov     qword ptr [rdi+0E8h], 0
0x140011be6  mov     rdi, [rdi]
0x140011be9  cmp     rdi, rsi
0x140011bec  jnz     short loc_140011BBC
0x140011bee  mov     rcx, rbp; FastMutex
0x140011bf1  call    cs:__imp_ExReleaseFastMutex
0x140011bf8  nop     dword ptr [rax+rax+00h]
0x140011bfd  mov     rcx, [rbx+3E0h]; Event
0x140011c04  test    rcx, rcx
0x140011c07  jz      short loc_140011C25
0x140011c09  xor     r8d, r8d; Wait
0x140011c0c  mov     qword ptr [rbx+3E0h], 0
0x140011c17  xor     edx, edx; Increment
0x140011c19  call    cs:__imp_KeSetEvent
0x140011c20  nop     dword ptr [rax+rax+00h]
0x140011c25  mov     rcx, rbx
0x140011c28  call    XPartDeref
0x140011c2d  add     rsp, 38h
0x140011c31  pop     rdi
0x140011c32  pop     rsi
0x140011c33  pop     rbp
0x140011c34  pop     rbx
0x140011c35  retn
```
