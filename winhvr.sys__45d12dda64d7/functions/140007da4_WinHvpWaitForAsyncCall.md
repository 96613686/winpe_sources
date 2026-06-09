# WinHvpWaitForAsyncCall

- ea: `0x140007da4`
- end: `0x140007e2e`
- name: `WinHvpWaitForAsyncCall`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ef0`
- `0x140004a00`
- `0x140008420`
- `0x140009750`
- `0x14001c8e0`
- `0x14001f990`
- `0x140024020`
- `0x140024110`

## callees

- `0x140007da4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140007de2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007de2`

## pseudocode

```c
__int64 __fastcall WinHvpWaitForAsyncCall(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  struct _KEVENT *v6; // rcx

  if ( a1 )
    v6 = (struct _KEVENT *)(a1 + 160);
  else
    v6 = &WinHvpGlobalAsyncEvent;
  KeWaitForSingleObject(v6, Executive, 0, 0, 0);
  if ( !a1 )
    return (unsigned int)WinHvpGlobalAsyncStatus;
  if ( a2 )
    *a2 = *(_QWORD *)(a1 + 248);
  if ( a3 )
    *a3 = *(_DWORD *)(a1 + 256);
  return *(unsigned int *)(a1 + 240);
}

```

## disassembly

```asm
0x140007da4  mov     [rsp+arg_0], rbx
0x140007da9  mov     [rsp+arg_8], rsi
0x140007dae  push    rdi
0x140007daf  sub     rsp, 30h
0x140007db3  mov     rdi, r8
0x140007db6  mov     rsi, rdx
0x140007db9  mov     rbx, rcx
0x140007dbc  test    rcx, rcx
0x140007dbf  jz      short loc_140007DCA
0x140007dc1  add     rcx, 0A0h
0x140007dc8  jmp     short loc_140007DD1
0x140007dca  lea     rcx, WinHvpGlobalAsyncEvent; Object
0x140007dd1  xor     r9d, r9d; Alertable
0x140007dd4  mov     [rsp+38h+Timeout], 0; Timeout
0x140007ddd  xor     r8d, r8d; WaitMode
0x140007de0  xor     edx, edx; WaitReason
0x140007de2  call    cs:__imp_KeWaitForSingleObject
0x140007de9  nop     dword ptr [rax+rax+00h]
0x140007dee  test    rbx, rbx
0x140007df1  jz      short loc_140007E17
0x140007df3  test    rsi, rsi
0x140007df6  jz      short loc_140007E02
0x140007df8  mov     rax, [rbx+0F8h]
0x140007dff  mov     [rsi], rax
0x140007e02  test    rdi, rdi
0x140007e05  jz      short loc_140007E0F
0x140007e07  mov     eax, [rbx+100h]
0x140007e0d  mov     [rdi], eax
0x140007e0f  mov     eax, [rbx+0F0h]
0x140007e15  jmp     short loc_140007E1D
0x140007e17  mov     eax, cs:WinHvpGlobalAsyncStatus
0x140007e1d  mov     rbx, [rsp+38h+arg_0]
0x140007e22  mov     rsi, [rsp+38h+arg_8]
0x140007e27  add     rsp, 30h
0x140007e2b  pop     rdi
0x140007e2c  retn
```
