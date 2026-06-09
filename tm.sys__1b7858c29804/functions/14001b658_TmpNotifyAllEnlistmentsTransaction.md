# TmpNotifyAllEnlistmentsTransaction

- ea: `0x14001b658`
- end: `0x14001b881`
- name: `TmpNotifyAllEnlistmentsTransaction`
- size: `553`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c010`
- `0x14000c3c4`
- `0x140011ab4`
- `0x140011c80`
- `0x14001b594`
- `0x14001dbb0`
- `0x14001eb30`
- `0x140020dd4`

## callees

- `0x14000c9ac`
- `0x14001b658`
- `0x14001c010`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001b735`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b814`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b735`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b814`
- `ntoskrnl!KeReleaseMutex` at `0x14001b787`
- `ntoskrnl!KeReleaseMutex` at `0x14001b82d`
- `ntoskrnl!KeReleaseMutex` at `0x14001b787`
- `ntoskrnl!KeReleaseMutex` at `0x14001b82d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b6e1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b85a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b6e1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b85a`
- `ntoskrnl!ObfReferenceObject` at `0x14001b6f4`
- `ntoskrnl!ObfReferenceObject` at `0x14001b6f4`
- `ntoskrnl!DbgPrintEx` at `0x14001b7b3`
- `ntoskrnl!DbgPrintEx` at `0x14001b7b3`

## pseudocode

```c
__int64 __fastcall TmpNotifyAllEnlistmentsTransaction(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 *v4; // rsi
  __int64 *v5; // rdi
  int v6; // ebp
  bool v9; // r13
  __int64 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  size_t Size; // [rsp+28h] [rbp-50h]
  int v16; // [rsp+90h] [rbp+18h]

  v4 = (__int64 *)(a1 + 200);
  v5 = *(__int64 **)(a1 + 200);
  v6 = 0;
  v16 = *(_DWORD *)(a1 + 192);
  *(_DWORD *)(a1 + 236) = 0;
  if ( v5 != (__int64 *)(a1 + 200) )
  {
    do
    {
      if ( (*((_DWORD *)v5 + 13) & 1) == 0 && (a2 & (_DWORD)v5[7]) != 0 )
        ++*(_DWORD *)(a1 + 236);
      v5 = (__int64 *)*v5;
    }
    while ( v5 != v4 );
    v5 = (__int64 *)*v4;
  }
  v9 = ((a4 - 269) & 0xFFFFFFFD) == 0;
  v10 = 0;
  if ( v5 != v4 )
  {
    while ( 1 )
    {
      if ( v10 )
        ObfDereferenceObject(v10);
      v10 = v5 - 15;
      ObfReferenceObject(v5 - 15);
      if ( (*((_DWORD *)v5 + 13) & 1) == 0 && ((_DWORD)v10[22] & a2) != 0 )
        break;
LABEL_22:
      v5 = (__int64 *)*v5;
      if ( v5 == v4 )
      {
LABEL_23:
        ObfDereferenceObject(v10);
        return (unsigned int)v6;
      }
    }
    KeWaitForSingleObject(v10 + 8, Executive, 0, 0, 0);
    v11 = *((unsigned int *)v10 + 78);
    *((_DWORD *)v10 + 42) = a4;
    HIDWORD(v10[v11 + 39]) = a2;
    LODWORD(v10[(unsigned int)(*((_DWORD *)v10 + 78))++ + 40]) = a4;
    if ( *((_DWORD *)v10 + 78) >= 0x14u )
      *((_DWORD *)v10 + 78) = 0;
    KeReleaseMutex((PRKMUTEX)(v10 + 8), 0);
    DbgPrintEx(0x6Cu, 0x80000020, "KTM:  Notifying RM of %d for tx %lx\n", a2, v10[20]);
    LODWORD(Size) = 0;
    v13 = TmpSetNotificationResourceManager(
            (PRKEVENT)v10[19],
            v12,
            (__int64)(v5 - 15),
            (struct _LIST_ENTRY *)v10[23],
            a2,
            Size,
            0);
    if ( v13 >= 0 )
    {
      if ( v6 )
        goto LABEL_19;
    }
    else if ( v6 < 0 )
    {
      goto LABEL_19;
    }
    v6 = v13;
LABEL_19:
    if ( v9 )
    {
      KeWaitForSingleObject(v10 + 8, Executive, 0, 0, 0);
      TmpFinalizeEnlistment(v5 - 15);
      KeReleaseMutex((PRKMUTEX)(v10 + 8), 0);
    }
    else if ( *(_DWORD *)(a1 + 192) != v16 )
    {
      goto LABEL_23;
    }
    goto LABEL_22;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001b658  mov     [rsp+arg_0], rbx
0x14001b65d  mov     [rsp+arg_18], r9d
0x14001b662  mov     byte ptr [rsp+arg_10], r8b
0x14001b667  push    rbp
0x14001b668  push    rsi
0x14001b669  push    rdi
0x14001b66a  push    r12
0x14001b66c  push    r13
0x14001b66e  push    r14
0x14001b670  push    r15
0x14001b672  sub     rsp, 40h
0x14001b676  mov     eax, [rcx+0C0h]
0x14001b67c  lea     rsi, [rcx+0C8h]
0x14001b683  mov     rdi, [rsi]
0x14001b686  xor     ebp, ebp
0x14001b688  mov     [rsp+78h+arg_10], eax
0x14001b68f  mov     r12d, edx
0x14001b692  mov     [rcx+0ECh], ebp
0x14001b698  mov     r14, rcx
0x14001b69b  cmp     rdi, rsi
0x14001b69e  jz      short loc_14001B6BE
0x14001b6a0  mov     eax, [rdi+34h]
0x14001b6a3  test    al, 1
0x14001b6a5  jnz     short loc_14001B6B3
0x14001b6a7  test    [rdi+38h], r12d
0x14001b6ab  jz      short loc_14001B6B3
0x14001b6ad  inc     dword ptr [rcx+0ECh]
0x14001b6b3  mov     rdi, [rdi]
0x14001b6b6  cmp     rdi, rsi
0x14001b6b9  jnz     short loc_14001B6A0
0x14001b6bb  mov     rdi, [rsi]
0x14001b6be  lea     eax, [r9-10Dh]
0x14001b6c5  test    eax, 0FFFFFFFDh
0x14001b6ca  setz    r13b
0x14001b6ce  xor     ebx, ebx
0x14001b6d0  cmp     rdi, rsi
0x14001b6d3  jz      loc_14001B866
0x14001b6d9  test    rbx, rbx
0x14001b6dc  jz      short loc_14001B6ED
0x14001b6de  mov     rcx, rbx; Object
0x14001b6e1  call    cs:__imp_ObfDereferenceObject
0x14001b6e8  nop     dword ptr [rax+rax+00h]
0x14001b6ed  lea     rbx, [rdi-78h]
0x14001b6f1  mov     rcx, rbx; Object
0x14001b6f4  call    cs:__imp_ObfReferenceObject
0x14001b6fb  nop     dword ptr [rax+rax+00h]
0x14001b700  mov     eax, [rbx+0ACh]
0x14001b706  test    al, 1
0x14001b708  jnz     loc_14001B84B
0x14001b70e  mov     eax, [rbx+0B0h]
0x14001b714  test    r12d, eax
0x14001b717  jz      loc_14001B84B
0x14001b71d  lea     r15, [rbx+40h]
0x14001b721  mov     [rsp+78h+Timeout], 0; Timeout
0x14001b72a  mov     rcx, r15; Object
0x14001b72d  xor     r9d, r9d; Alertable
0x14001b730  xor     r8d, r8d; WaitMode
0x14001b733  xor     edx, edx; WaitReason
0x14001b735  call    cs:__imp_KeWaitForSingleObject
0x14001b73c  nop     dword ptr [rax+rax+00h]
0x14001b741  mov     eax, [rbx+138h]
0x14001b747  mov     ecx, [rsp+78h+arg_18]
0x14001b74e  mov     [rbx+0A8h], ecx
0x14001b754  mov     [rbx+rax*8+13Ch], r12d
0x14001b75c  mov     eax, [rbx+138h]
0x14001b762  mov     [rbx+rax*8+140h], ecx
0x14001b769  inc     dword ptr [rbx+138h]
0x14001b76f  cmp     dword ptr [rbx+138h], 14h
0x14001b776  jb      short loc_14001B782
0x14001b778  mov     dword ptr [rbx+138h], 0
0x14001b782  xor     edx, edx; Wait
0x14001b784  mov     rcx, r15; Mutex
0x14001b787  call    cs:__imp_KeReleaseMutex
0x14001b78e  nop     dword ptr [rax+rax+00h]
0x14001b793  mov     rax, [rbx+0A0h]
0x14001b79a  lea     r8, aKtmNotifyingRm; "KTM:  Notifying RM of %d for tx %lx\n"
0x14001b7a1  mov     r9d, r12d
0x14001b7a4  mov     [rsp+78h+Timeout], rax
0x14001b7a9  mov     edx, 80000020h; Level
0x14001b7ae  mov     ecx, 6Ch ; 'l'; ComponentId
0x14001b7b3  call    cs:__imp_DbgPrintEx
0x14001b7ba  nop     dword ptr [rax+rax+00h]
0x14001b7bf  mov     r9, [rbx+0B8h]
0x14001b7c6  mov     r8, rbx
0x14001b7c9  mov     rcx, [rbx+98h]; Event
0x14001b7d0  mov     [rsp+78h+Src], 0; Src
0x14001b7d9  mov     dword ptr [rsp+78h+Size], 0; Size
0x14001b7e1  mov     dword ptr [rsp+78h+Timeout], r12d; int
0x14001b7e6  call    TmpSetNotificationResourceManager
0x14001b7eb  test    eax, eax
0x14001b7ed  jns     short loc_14001B7F5
0x14001b7ef  test    ebp, ebp
0x14001b7f1  js      short loc_14001B7FB
0x14001b7f3  jmp     short loc_14001B7F9
0x14001b7f5  test    ebp, ebp
0x14001b7f7  jnz     short loc_14001B7FB
0x14001b7f9  mov     ebp, eax
0x14001b7fb  test    r13b, r13b
0x14001b7fe  jz      short loc_14001B83B
0x14001b800  xor     r9d, r9d; Alertable
0x14001b803  mov     [rsp+78h+Timeout], 0; Timeout
0x14001b80c  xor     r8d, r8d; WaitMode
0x14001b80f  xor     edx, edx; WaitReason
0x14001b811  mov     rcx, r15; Object
0x14001b814  call    cs:__imp_KeWaitForSingleObject
0x14001b81b  nop     dword ptr [rax+rax+00h]
0x14001b820  mov     rcx, rbx; Object
0x14001b823  call    TmpFinalizeEnlistment
0x14001b828  xor     edx, edx; Wait
0x14001b82a  mov     rcx, r15; Mutex
0x14001b82d  call    cs:__imp_KeReleaseMutex
0x14001b834  nop     dword ptr [rax+rax+00h]
0x14001b839  jmp     short loc_14001B84B
0x14001b83b  mov     eax, [rsp+78h+arg_10]
0x14001b842  cmp     [r14+0C0h], eax
0x14001b849  jnz     short loc_14001B857
0x14001b84b  mov     rdi, [rdi]
0x14001b84e  cmp     rdi, rsi
0x14001b851  jnz     loc_14001B6D9
0x14001b857  mov     rcx, rbx; Object
0x14001b85a  call    cs:__imp_ObfDereferenceObject
0x14001b861  nop     dword ptr [rax+rax+00h]
0x14001b866  mov     rbx, [rsp+78h+arg_0]
0x14001b86e  mov     eax, ebp
0x14001b870  add     rsp, 40h
0x14001b874  pop     r15
0x14001b876  pop     r14
0x14001b878  pop     r13
0x14001b87a  pop     r12
0x14001b87c  pop     rdi
0x14001b87d  pop     rsi
0x14001b87e  pop     rbp
0x14001b87f  retn
```
