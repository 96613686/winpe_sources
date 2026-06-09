# TmpNamespaceRemove

- ea: `0x14000c664`
- end: `0x14000c710`
- name: `TmpNamespaceRemove`
- size: `172`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Object)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c584`
- `0x14000c7e8`
- `0x140012380`
- `0x14001ddf0`
- `0x14001defc`
- `0x14001ea40`
- `0x140020b50`

## callees

- `0x14000c664`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000c693`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c693`
- `ntoskrnl!KeReleaseMutex` at `0x14000c6e2`
- `ntoskrnl!KeReleaseMutex` at `0x14000c6e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c6fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c6fa`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000c6c6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14000c6c6`

## pseudocode

```c
LONG __fastcall TmpNamespaceRemove(PRTL_AVL_TABLE Table, PVOID Object, __int64 a3)
{
  void *v6; // rdx
  BOOLEAN v7; // al
  BOOLEAN v8; // bl
  LONG result; // eax
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF

  v10 = 0;
  KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
  DWORD2(v10) = 0;
  Table->TableContext = &v10;
  v6 = (void *)(LOWORD(Table[1].RestartKey) + a3 + 32);
  *(_QWORD *)&v10 = a3;
  v7 = RtlDeleteElementGenericTableAvl(Table, v6);
  Table->TableContext = 0;
  v8 = v7;
  result = KeReleaseMutex((PRKMUTEX)&Table[1], 0);
  if ( Object )
  {
    if ( v8 )
      return ObfDereferenceObject(Object);
  }
  return result;
}

```

## disassembly

```asm
0x14000c664  push    rbx
0x14000c666  push    rbp
0x14000c667  push    rsi
0x14000c668  push    rdi
0x14000c669  sub     rsp, 48h
0x14000c66d  mov     rbx, r8
0x14000c670  mov     [rsp+68h+Timeout], 0; Timeout
0x14000c679  mov     rbp, rdx
0x14000c67c  mov     rsi, rcx
0x14000c67f  xorps   xmm0, xmm0
0x14000c682  xor     r8d, r8d; WaitMode
0x14000c685  xor     edx, edx; WaitReason
0x14000c687  add     rcx, 68h ; 'h'; Object
0x14000c68b  xor     r9d, r9d; Alertable
0x14000c68e  movups  [rsp+68h+var_38], xmm0
0x14000c693  call    cs:__imp_KeWaitForSingleObject
0x14000c69a  nop     dword ptr [rax+rax+00h]
0x14000c69f  lea     rax, [rsp+68h+var_38]
0x14000c6a4  mov     dword ptr [rsp+68h+var_38+8], 0
0x14000c6ac  mov     [rsi+60h], rax
0x14000c6b0  lea     rdx, [rbx+20h]
0x14000c6b4  movzx   eax, word ptr [rsi+0A0h]
0x14000c6bb  mov     rcx, rsi; Table
0x14000c6be  add     rdx, rax; Buffer
0x14000c6c1  mov     qword ptr [rsp+68h+var_38], rbx
0x14000c6c6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000c6cd  nop     dword ptr [rax+rax+00h]
0x14000c6d2  xor     edx, edx; Wait
0x14000c6d4  mov     qword ptr [rsi+60h], 0
0x14000c6dc  lea     rcx, [rsi+68h]; Mutex
0x14000c6e0  mov     bl, al
0x14000c6e2  call    cs:__imp_KeReleaseMutex
0x14000c6e9  nop     dword ptr [rax+rax+00h]
0x14000c6ee  test    rbp, rbp
0x14000c6f1  jz      short loc_14000C706
0x14000c6f3  test    bl, bl
0x14000c6f5  jz      short loc_14000C706
0x14000c6f7  mov     rcx, rbp; Object
0x14000c6fa  call    cs:__imp_ObfDereferenceObject
0x14000c701  nop     dword ptr [rax+rax+00h]
0x14000c706  add     rsp, 48h
0x14000c70a  pop     rdi
0x14000c70b  pop     rsi
0x14000c70c  pop     rbp
0x14000c70d  pop     rbx
0x14000c70e  retn
```
