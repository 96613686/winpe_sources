# TmpNamespaceRename

- ea: `0x14001ea40`
- end: `0x14001eb29`
- name: `TmpNamespaceRename`
- size: `233`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e758`
- `0x14001ec00`

## callees

- `0x14000c664`
- `0x14001b444`
- `0x14001ea40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001eabf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001eabf`
- `ntoskrnl!KeReleaseMutex` at `0x14001eb15`
- `ntoskrnl!KeReleaseMutex` at `0x14002181f`
- `ntoskrnl!KeReleaseMutex` at `0x14001eb15`
- `ntoskrnl!KeReleaseMutex` at `0x14002181f`

## pseudocode

```c
__int64 __fastcall TmpNamespaceRename(PRTL_AVL_TABLE Table, __int64 a2, __int128 *a3)
{
  __int128 *v6; // rdi
  __int64 RestartKey_low; // rax
  __int128 v9; // xmm6
  int v10; // r15d

  v6 = (__int128 *)(a2 + WORD1(Table[1].RestartKey));
  RestartKey_low = LOWORD(Table[1].RestartKey);
  if ( !*(_QWORD *)(RestartKey_low + a2) || *(_BYTE *)(RestartKey_low + a2 + 32) )
  {
    *v6 = *a3;
    return 0;
  }
  else
  {
    KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
    TmpNamespaceRemove(Table, 0, a2);
    v9 = *v6;
    *v6 = *a3;
    v10 = TmpNamespaceInsert(Table, 0);
    if ( v10 < 0 )
    {
      *v6 = v9;
      TmpNamespaceInsert(Table, 0);
    }
    KeReleaseMutex((PRKMUTEX)&Table[1], 0);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x14001ea40  mov     rax, rsp
0x14001ea43  mov     [rax+10h], rbx
0x14001ea47  mov     [rax+18h], rsi
0x14001ea4b  mov     [rax+8], rcx
0x14001ea4f  push    rdi
0x14001ea50  push    r14
0x14001ea52  push    r15
0x14001ea54  sub     rsp, 50h
0x14001ea58  movaps  xmmword ptr [rax-28h], xmm6
0x14001ea5c  mov     r15, r8
0x14001ea5f  mov     rsi, rdx
0x14001ea62  mov     rbx, rcx
0x14001ea65  movzx   edi, word ptr [rcx+0A2h]
0x14001ea6c  add     rdi, rdx
0x14001ea6f  movzx   eax, word ptr [rcx+0A0h]
0x14001ea76  cmp     qword ptr [rax+rdx], 0
0x14001ea7b  jnz     short loc_14001EAA3
0x14001ea7d  movups  xmm0, xmmword ptr [r8]
0x14001ea81  movdqu  xmmword ptr [rdi], xmm0
0x14001ea85  xor     eax, eax
0x14001ea87  lea     r11, [rsp+68h+var_18]
0x14001ea8c  mov     rbx, [r11+28h]
0x14001ea90  mov     rsi, [r11+30h]
0x14001ea94  movaps  xmm6, [rsp+68h+var_28]
0x14001ea99  mov     rsp, r11
0x14001ea9c  pop     r15
0x14001ea9e  pop     r14
0x14001eaa0  pop     rdi
0x14001eaa1  retn
0x14001eaa3  cmp     byte ptr [rax+rdx+20h], 0
0x14001eaa8  jnz     short loc_14001EA7D
0x14001eaaa  mov     [rsp+68h+Timeout], 0; Timeout
0x14001eab3  xor     r9d, r9d; Alertable
0x14001eab6  xor     r8d, r8d; WaitMode
0x14001eab9  xor     edx, edx; WaitReason
0x14001eabb  add     rcx, 68h ; 'h'; Object
0x14001eabf  call    cs:__imp_KeWaitForSingleObject
0x14001eac6  nop     dword ptr [rax+rax+00h]
0x14001eacb  nop
0x14001eacc  mov     r8, rsi
0x14001eacf  xor     edx, edx; Object
0x14001ead1  mov     rcx, rbx; Table
0x14001ead4  call    TmpNamespaceRemove
0x14001ead9  movups  xmm6, xmmword ptr [rdi]
0x14001eadc  movups  [rsp+68h+var_38], xmm6
0x14001eae1  movups  xmm0, xmmword ptr [r15]
0x14001eae5  movdqu  xmmword ptr [rdi], xmm0
0x14001eae9  mov     r8, rsi
0x14001eaec  xor     edx, edx; Object
0x14001eaee  mov     rcx, rbx; Table
0x14001eaf1  call    TmpNamespaceInsert
0x14001eaf6  mov     r15d, eax
0x14001eaf9  test    eax, eax
0x14001eafb  jns     short loc_14001EB0F
0x14001eafd  movdqu  xmmword ptr [rdi], xmm6
0x14001eb01  mov     r8, rsi
0x14001eb04  xor     edx, edx; Object
0x14001eb06  mov     rcx, rbx; Table
0x14001eb09  call    TmpNamespaceInsert
0x14001eb0e  nop
0x14001eb0f  xor     edx, edx; Wait
0x14001eb11  lea     rcx, [rbx+68h]; Mutex
0x14001eb15  call    cs:__imp_KeReleaseMutex
0x14001eb1c  nop     dword ptr [rax+rax+00h]
0x14001eb21  mov     eax, r15d
0x14001eb24  jmp     loc_14001EA87
0x14002180c  push    rbp
0x14002180e  sub     rsp, 30h
0x140021812  mov     rbp, rdx
0x140021815  mov     rcx, [rbp+70h]
0x140021819  add     rcx, 68h ; 'h'; Mutex
0x14002181d  xor     edx, edx; Wait
0x14002181f  call    cs:__imp_KeReleaseMutex
0x140021826  nop     dword ptr [rax+rax+00h]
0x14002182b  nop
0x14002182c  add     rsp, 30h
0x140021830  pop     rbp
0x140021831  retn
```
