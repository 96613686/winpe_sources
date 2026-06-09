# WcCreateExpansionContext

- ea: `0x140017d98`
- end: `0x140017ef0`
- name: `WcCreateExpansionContext`
- size: `344`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018970`

## callees

- `0x140017d98`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017db6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017db6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017ed6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017ed6`
- `ntoskrnl!KeInitializeEvent` at `0x140017e46`
- `ntoskrnl!KeInitializeEvent` at `0x140017e7f`
- `ntoskrnl!KeInitializeEvent` at `0x140017e46`
- `ntoskrnl!KeInitializeEvent` at `0x140017e7f`
- `FLTMGR!FltCbdqInitialize` at `0x140017e19`
- `FLTMGR!FltCbdqInitialize` at `0x140017e19`

## pseudocode

```c
__int64 __fastcall WcCreateExpansionContext(PFLT_INSTANCE Instance, __int64 a2, __int64 a3, _QWORD *a4)
{
  char *v8; // rax
  _DWORD *v9; // rbx
  NTSTATUS v10; // edi
  signed __int64 v11; // rax

  v8 = (char *)ExAllocateFromNPagedLookasideList(&stru_14000E580);
  v9 = v8;
  if ( v8 )
  {
    v10 = FltCbdqInitialize(
            Instance,
            (PFLT_CALLBACK_DATA_QUEUE)(v8 + 40),
            WcExpansionCsqInsertIo,
            WcExpansionCsqRemoveIo,
            WcExpansionCsqPeekNextIo,
            WcExpansionCsqAcquireLock,
            WcExpansionCsqReleaseLock,
            WcExpansionCsqCompleteCanceledIo);
    if ( v10 < 0 )
    {
      ExFreeToNPagedLookasideList(&stru_14000E580, v9);
    }
    else
    {
      *((_QWORD *)v9 + 22) = v9 + 42;
      *((_QWORD *)v9 + 21) = v9 + 42;
      KeInitializeEvent((PRKEVENT)(v9 + 2), NotificationEvent, 1u);
      v9[46] = 1;
      *((_QWORD *)v9 + 24) = 0;
      v9[50] = 0;
      KeInitializeEvent((PRKEVENT)(v9 + 52), SynchronizationEvent, 0);
      *v9 = 0;
      v9[8] = 0;
      *((_QWORD *)v9 + 30) = a3;
      v9[63] = *(_DWORD *)(a2 + 56);
      v11 = _InterlockedIncrement64((volatile signed __int64 *)(a2 + 48));
      *a4 = v9;
      *((_QWORD *)v9 + 32) = v11;
      v9[62] = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140017d98  push    rbx
0x140017d9a  push    rbp
0x140017d9b  push    rsi
0x140017d9c  push    rdi
0x140017d9d  push    r14
0x140017d9f  sub     rsp, 40h
0x140017da3  mov     rdi, rcx
0x140017da6  mov     r14, r9
0x140017da9  lea     rcx, stru_14000E580; Lookaside
0x140017db0  mov     rbp, r8
0x140017db3  mov     rsi, rdx
0x140017db6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140017dbd  nop     dword ptr [rax+rax+00h]
0x140017dc2  mov     rbx, rax
0x140017dc5  test    rax, rax
0x140017dc8  jnz     short loc_140017DD4
0x140017dca  mov     edi, 0C000009Ah
0x140017dcf  jmp     loc_140017EE2
0x140017dd4  lea     rdx, [rax+28h]; Cbdq
0x140017dd8  mov     rcx, rdi; Instance
0x140017ddb  lea     rax, WcExpansionCsqCompleteCanceledIo
0x140017de2  mov     [rsp+68h+CbdqCompleteCanceledIo], rax; CbdqCompleteCanceledIo
0x140017de7  lea     r9, WcExpansionCsqRemoveIo; CbdqRemoveIo
0x140017dee  lea     rax, WcExpansionCsqReleaseLock
0x140017df5  mov     [rsp+68h+CbdqRelease], rax; CbdqRelease
0x140017dfa  lea     r8, WcExpansionCsqInsertIo; CbdqInsertIo
0x140017e01  lea     rax, WcExpansionCsqAcquireLock
0x140017e08  mov     [rsp+68h+CbdqAcquire], rax; CbdqAcquire
0x140017e0d  lea     rax, WcExpansionCsqPeekNextIo
0x140017e14  mov     [rsp+68h+CbdqPeekNextIo], rax; CbdqPeekNextIo
0x140017e19  call    cs:__imp_FltCbdqInitialize
0x140017e20  nop     dword ptr [rax+rax+00h]
0x140017e25  mov     edi, eax
0x140017e27  test    eax, eax
0x140017e29  js      loc_140017ECC
0x140017e2f  lea     rcx, [rbx+0A8h]
0x140017e36  mov     r8b, 1; State
0x140017e39  mov     [rcx+8], rcx
0x140017e3d  xor     edx, edx; Type
0x140017e3f  mov     [rcx], rcx
0x140017e42  lea     rcx, [rbx+8]; Event
0x140017e46  call    cs:__imp_KeInitializeEvent
0x140017e4d  nop     dword ptr [rax+rax+00h]
0x140017e52  xor     r8d, r8d; State
0x140017e55  mov     dword ptr [rbx+0B8h], 1
0x140017e5f  lea     rcx, [rbx+0D0h]; Event
0x140017e66  mov     qword ptr [rbx+0C0h], 0
0x140017e71  mov     dword ptr [rbx+0C8h], 0
0x140017e7b  lea     edx, [r8+1]; Type
0x140017e7f  call    cs:__imp_KeInitializeEvent
0x140017e86  nop     dword ptr [rax+rax+00h]
0x140017e8b  mov     dword ptr [rbx], 0
0x140017e91  mov     dword ptr [rbx+20h], 0
0x140017e98  mov     [rbx+0F0h], rbp
0x140017e9f  mov     eax, [rsi+38h]
0x140017ea2  mov     [rbx+0FCh], eax
0x140017ea8  mov     eax, 1
0x140017ead  lock xadd [rsi+30h], rax
0x140017eb3  inc     rax
0x140017eb6  mov     [r14], rbx
0x140017eb9  mov     [rbx+100h], rax
0x140017ec0  mov     dword ptr [rbx+0F8h], 0
0x140017eca  jmp     short loc_140017EE2
0x140017ecc  mov     rdx, rbx; Entry
0x140017ecf  lea     rcx, stru_14000E580; Lookaside
0x140017ed6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017edd  nop     dword ptr [rax+rax+00h]
0x140017ee2  mov     eax, edi
0x140017ee4  add     rsp, 40h
0x140017ee8  pop     r14
0x140017eea  pop     rdi
0x140017eeb  pop     rsi
0x140017eec  pop     rbp
0x140017eed  pop     rbx
0x140017eee  retn
```
