# TmpDeletePropagateRequest

- ea: `0x14000d080`
- end: `0x14000d192`
- name: `TmpDeletePropagateRequest`
- size: `274`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cfa8`

## callees

- `0x14000d080`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000d0a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d0a1`
- `ntoskrnl!KeReleaseMutex` at `0x14000d0db`
- `ntoskrnl!KeReleaseMutex` at `0x14000d0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d11a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d13f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d178`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d11a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d13f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d178`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d15f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000d15f`

## pseudocode

```c
void __fastcall TmpDeletePropagateRequest(_QWORD *P)
{
  _QWORD **v2; // r8
  PVOID *v3; // rdx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  KeWaitForSingleObject(&WPP_MAIN_CB.DeviceQueue, Executive, 0, 0, 0);
  v2 = (_QWORD **)P[4];
  if ( v2[1] != P + 4 || (v3 = (PVOID *)P[5], *v3 != P + 4) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.DeviceQueue, 0);
  v4 = (void *)P[43];
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    P[43] = 0;
  }
  v5 = (void *)P[45];
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    P[45] = 0;
  }
  v6 = (void *)P[47];
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    P[47] = 0;
  }
  v7 = (void *)P[8];
  if ( v7 )
  {
    ObfDereferenceObject(v7);
    P[8] = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000d080  push    rbx
0x14000d082  sub     rsp, 30h
0x14000d086  mov     rbx, rcx
0x14000d089  mov     [rsp+38h+Timeout], 0; Timeout
0x14000d092  lea     rcx, WPP_MAIN_CB.DeviceQueue; Object
0x14000d099  xor     r9d, r9d; Alertable
0x14000d09c  xor     r8d, r8d; WaitMode
0x14000d09f  xor     edx, edx; WaitReason
0x14000d0a1  call    cs:__imp_KeWaitForSingleObject
0x14000d0a8  nop     dword ptr [rax+rax+00h]
0x14000d0ad  lea     rax, [rbx+20h]
0x14000d0b1  mov     r8, [rax]
0x14000d0b4  cmp     [r8+8], rax
0x14000d0b8  jnz     loc_14000D18B
0x14000d0be  mov     rdx, [rax+8]
0x14000d0c2  cmp     [rdx], rax
0x14000d0c5  jnz     loc_14000D18B
0x14000d0cb  mov     [rdx], r8
0x14000d0ce  lea     rcx, WPP_MAIN_CB.DeviceQueue; Mutex
0x14000d0d5  mov     [r8+8], rdx
0x14000d0d9  xor     edx, edx; Wait
0x14000d0db  call    cs:__imp_KeReleaseMutex
0x14000d0e2  nop     dword ptr [rax+rax+00h]
0x14000d0e7  mov     rcx, [rbx+158h]; P
0x14000d0ee  test    rcx, rcx
0x14000d0f1  jz      short loc_14000D10C
0x14000d0f3  xor     edx, edx; Tag
0x14000d0f5  call    cs:__imp_ExFreePoolWithTag
0x14000d0fc  nop     dword ptr [rax+rax+00h]
0x14000d101  mov     qword ptr [rbx+158h], 0
0x14000d10c  mov     rcx, [rbx+168h]; P
0x14000d113  test    rcx, rcx
0x14000d116  jz      short loc_14000D131
0x14000d118  xor     edx, edx; Tag
0x14000d11a  call    cs:__imp_ExFreePoolWithTag
0x14000d121  nop     dword ptr [rax+rax+00h]
0x14000d126  mov     qword ptr [rbx+168h], 0
0x14000d131  mov     rcx, [rbx+178h]; P
0x14000d138  test    rcx, rcx
0x14000d13b  jz      short loc_14000D156
0x14000d13d  xor     edx, edx; Tag
0x14000d13f  call    cs:__imp_ExFreePoolWithTag
0x14000d146  nop     dword ptr [rax+rax+00h]
0x14000d14b  mov     qword ptr [rbx+178h], 0
0x14000d156  mov     rcx, [rbx+40h]; Object
0x14000d15a  test    rcx, rcx
0x14000d15d  jz      short loc_14000D173
0x14000d15f  call    cs:__imp_ObfDereferenceObject
0x14000d166  nop     dword ptr [rax+rax+00h]
0x14000d16b  mov     qword ptr [rbx+40h], 0
0x14000d173  xor     edx, edx; Tag
0x14000d175  mov     rcx, rbx; P
0x14000d178  call    cs:__imp_ExFreePoolWithTag
0x14000d17f  nop     dword ptr [rax+rax+00h]
0x14000d184  add     rsp, 30h
0x14000d188  pop     rbx
0x14000d189  retn
0x14000d18b  mov     ecx, 3
0x14000d190  int     29h; Win8: RtlFailFast(ecx)
```
