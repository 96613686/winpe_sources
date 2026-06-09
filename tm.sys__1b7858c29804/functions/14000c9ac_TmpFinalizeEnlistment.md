# TmpFinalizeEnlistment

- ea: `0x14000c9ac`
- end: `0x14000cbc6`
- name: `TmpFinalizeEnlistment`
- size: `538`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14001102c`
- `0x140011300`
- `0x14001a000`
- `0x14001aa8c`
- `0x14001b658`
- `0x14001ca60`

## callees

- `0x14000c9ac`
- `0x14000cec8`
- `0x14001b338`
- `0x14001defc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000ca22`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cb9f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ca22`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cb9f`
- `ntoskrnl!KeReleaseMutex` at `0x14000c9f6`
- `ntoskrnl!KeReleaseMutex` at `0x14000cb68`
- `ntoskrnl!KeReleaseMutex` at `0x14000cb7e`
- `ntoskrnl!KeReleaseMutex` at `0x14000c9f6`
- `ntoskrnl!KeReleaseMutex` at `0x14000cb68`
- `ntoskrnl!KeReleaseMutex` at `0x14000cb7e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ca7c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ca8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cb25`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cb34`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cbae`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ca7c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ca8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cb25`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cb34`
- `ntoskrnl!ObfDereferenceObject` at `0x14000cbae`
- `ntoskrnl!ZwClose` at `0x14000cb02`
- `ntoskrnl!ZwClose` at `0x14000cb16`
- `ntoskrnl!ZwClose` at `0x14000cb4c`
- `ntoskrnl!ZwClose` at `0x14000cb02`
- `ntoskrnl!ZwClose` at `0x14000cb16`
- `ntoskrnl!ZwClose` at `0x14000cb4c`

## pseudocode

```c
__int64 __fastcall TmpFinalizeEnlistment(char *Object)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  struct _KMUTANT *v5; // r12
  char **v6; // rcx
  PVOID *v7; // rdx
  _QWORD *v8; // rdi
  void *v9; // rsi
  void *v10; // rcx
  void *v11; // r14
  void *v12; // rcx

  v2 = *((_QWORD *)Object + 20);
  v3 = *((_QWORD *)Object + 19);
  if ( (*((_DWORD *)Object + 43) & 4) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)Object + 43, 4u);
    KeReleaseMutex((PRKMUTEX)(Object + 64), 0);
    TmpAcquireTransactionMutex(v2);
    v5 = (struct _KMUTANT *)(v3 + 40);
    KeWaitForSingleObject((PVOID)(v3 + 40), Executive, 0, 0, 0);
    TmpRemoveTransactionEnlistmentCounts((__int64)Object);
    if ( (*((_DWORD *)Object + 43) & 1) != 0 )
      *(_QWORD *)(v2 + 240) = 0;
    v6 = (char **)*((_QWORD *)Object + 15);
    if ( v6[1] != Object + 120 || (v7 = (PVOID *)*((_QWORD *)Object + 16), *v7 != Object + 120) )
      __fastfail(3u);
    *v7 = v6;
    v6[1] = (char *)v7;
    TmpRemoveEnlistmentResourceManager((__int64)Object);
    ObfDereferenceObject(Object);
    ObfDereferenceObject(Object);
    if ( (*((_DWORD *)Object + 43) & 0x20) != 0 )
    {
      v8 = (_QWORD *)*((_QWORD *)Object + 30);
      if ( v8 )
      {
        v9 = (void *)v8[31];
        v10 = (void *)*((_QWORD *)Object + 31);
        v11 = (void *)v8[30];
        v8[30] = 0;
        *(_QWORD *)(*((_QWORD *)Object + 30) + 248LL) = 0;
        *((_QWORD *)Object + 30) = 0;
        *((_QWORD *)Object + 31) = 0;
        if ( v10 )
          ZwClose(v10);
        if ( v9 )
          ZwClose(v9);
        ObfDereferenceObject(v8);
        ObfDereferenceObject(v11);
      }
    }
    v12 = (void *)*((_QWORD *)Object + 32);
    if ( v12 )
    {
      ZwClose(v12);
      *((_QWORD *)Object + 32) = 0;
    }
    KeReleaseMutex(v5, 0);
    KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v2 + 88) + 32LL), 0);
    KeWaitForSingleObject(Object + 64, Executive, 0, 0, 0);
    ObfDereferenceObject(Object);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c9ac  push    rbx
0x14000c9ae  push    rbp
0x14000c9af  push    rsi
0x14000c9b0  push    rdi
0x14000c9b1  push    r12
0x14000c9b3  push    r14
0x14000c9b5  push    r15
0x14000c9b7  sub     rsp, 30h
0x14000c9bb  mov     eax, [rcx+0ACh]
0x14000c9c1  mov     rbx, rcx
0x14000c9c4  mov     rbp, [rcx+0A0h]
0x14000c9cb  mov     rdi, [rcx+98h]
0x14000c9d2  test    al, 4
0x14000c9d4  jz      short loc_14000C9E8
0x14000c9d6  xor     eax, eax
0x14000c9d8  add     rsp, 30h
0x14000c9dc  pop     r15
0x14000c9de  pop     r14
0x14000c9e0  pop     r12
0x14000c9e2  pop     rdi
0x14000c9e3  pop     rsi
0x14000c9e4  pop     rbp
0x14000c9e5  pop     rbx
0x14000c9e6  retn
0x14000c9e8  lock or dword ptr [rcx+0ACh], 4
0x14000c9f0  xor     edx, edx; Wait
0x14000c9f2  add     rcx, 40h ; '@'; Mutex
0x14000c9f6  call    cs:__imp_KeReleaseMutex
0x14000c9fd  nop     dword ptr [rax+rax+00h]
0x14000ca02  mov     rcx, rbp
0x14000ca05  call    TmpAcquireTransactionMutex
0x14000ca0a  lea     r12, [rdi+28h]
0x14000ca0e  mov     [rsp+68h+Timeout], 0; Timeout
0x14000ca17  mov     rcx, r12; Object
0x14000ca1a  xor     r9d, r9d; Alertable
0x14000ca1d  xor     r8d, r8d; WaitMode
0x14000ca20  xor     edx, edx; WaitReason
0x14000ca22  call    cs:__imp_KeWaitForSingleObject
0x14000ca29  nop     dword ptr [rax+rax+00h]
0x14000ca2e  mov     rcx, rbx
0x14000ca31  call    TmpRemoveTransactionEnlistmentCounts
0x14000ca36  mov     ecx, [rbx+0ACh]
0x14000ca3c  test    cl, 1
0x14000ca3f  jz      short loc_14000CA4C
0x14000ca41  mov     qword ptr [rbp+0F0h], 0
0x14000ca4c  lea     rax, [rbx+78h]
0x14000ca50  mov     rcx, [rax]
0x14000ca53  cmp     [rcx+8], rax
0x14000ca57  jnz     loc_14000CBBF
0x14000ca5d  mov     rdx, [rax+8]
0x14000ca61  cmp     [rdx], rax
0x14000ca64  jnz     loc_14000CBBF
0x14000ca6a  mov     [rdx], rcx
0x14000ca6d  mov     [rcx+8], rdx
0x14000ca71  mov     rcx, rbx
0x14000ca74  call    TmpRemoveEnlistmentResourceManager
0x14000ca79  mov     rcx, rbx; Object
0x14000ca7c  call    cs:__imp_ObfDereferenceObject
0x14000ca83  nop     dword ptr [rax+rax+00h]
0x14000ca88  mov     rcx, rbx; Object
0x14000ca8b  call    cs:__imp_ObfDereferenceObject
0x14000ca92  nop     dword ptr [rax+rax+00h]
0x14000ca97  mov     eax, [rbx+0ACh]
0x14000ca9d  test    al, 20h
0x14000ca9f  jz      loc_14000CB40
0x14000caa5  mov     rdi, [rbx+0F0h]
0x14000caac  test    rdi, rdi
0x14000caaf  jz      loc_14000CB40
0x14000cab5  mov     rsi, [rdi+0F8h]
0x14000cabc  mov     rcx, [rbx+0F8h]; Handle
0x14000cac3  mov     r14, [rdi+0F0h]
0x14000caca  mov     qword ptr [rdi+0F0h], 0
0x14000cad5  mov     rax, [rbx+0F0h]
0x14000cadc  mov     qword ptr [rax+0F8h], 0
0x14000cae7  mov     qword ptr [rbx+0F0h], 0
0x14000caf2  mov     qword ptr [rbx+0F8h], 0
0x14000cafd  test    rcx, rcx
0x14000cb00  jz      short loc_14000CB0E
0x14000cb02  call    cs:__imp_ZwClose
0x14000cb09  nop     dword ptr [rax+rax+00h]
0x14000cb0e  test    rsi, rsi
0x14000cb11  jz      short loc_14000CB22
0x14000cb13  mov     rcx, rsi; Handle
0x14000cb16  call    cs:__imp_ZwClose
0x14000cb1d  nop     dword ptr [rax+rax+00h]
0x14000cb22  mov     rcx, rdi; Object
0x14000cb25  call    cs:__imp_ObfDereferenceObject
0x14000cb2c  nop     dword ptr [rax+rax+00h]
0x14000cb31  mov     rcx, r14; Object
0x14000cb34  call    cs:__imp_ObfDereferenceObject
0x14000cb3b  nop     dword ptr [rax+rax+00h]
0x14000cb40  mov     rcx, [rbx+100h]; Handle
0x14000cb47  test    rcx, rcx
0x14000cb4a  jz      short loc_14000CB63
0x14000cb4c  call    cs:__imp_ZwClose
0x14000cb53  nop     dword ptr [rax+rax+00h]
0x14000cb58  mov     qword ptr [rbx+100h], 0
0x14000cb63  xor     edx, edx; Wait
0x14000cb65  mov     rcx, r12; Mutex
0x14000cb68  call    cs:__imp_KeReleaseMutex
0x14000cb6f  nop     dword ptr [rax+rax+00h]
0x14000cb74  mov     rcx, [rbp+58h]
0x14000cb78  xor     edx, edx; Wait
0x14000cb7a  add     rcx, 20h ; ' '; Mutex
0x14000cb7e  call    cs:__imp_KeReleaseMutex
0x14000cb85  nop     dword ptr [rax+rax+00h]
0x14000cb8a  xor     r9d, r9d; Alertable
0x14000cb8d  mov     [rsp+68h+Timeout], 0; Timeout
0x14000cb96  xor     r8d, r8d; WaitMode
0x14000cb99  lea     rcx, [rbx+40h]; Object
0x14000cb9d  xor     edx, edx; WaitReason
0x14000cb9f  call    cs:__imp_KeWaitForSingleObject
0x14000cba6  nop     dword ptr [rax+rax+00h]
0x14000cbab  mov     rcx, rbx; Object
0x14000cbae  call    cs:__imp_ObfDereferenceObject
0x14000cbb5  nop     dword ptr [rax+rax+00h]
0x14000cbba  jmp     loc_14000C9D6
0x14000cbbf  mov     ecx, 3
0x14000cbc4  int     29h; Win8: RtlFailFast(ecx)
```
