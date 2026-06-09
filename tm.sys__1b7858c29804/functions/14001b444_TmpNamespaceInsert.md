# TmpNamespaceInsert

- ea: `0x14001b444`
- end: `0x14001b561`
- name: `TmpNamespaceInsert`
- size: `285`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table, PVOID Object)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c584`
- `0x14000cbf8`
- `0x1400109a4`
- `0x140014c50`
- `0x140015c8c`
- `0x14001b390`
- `0x14001b3d0`
- `0x14001ea40`

## callees

- `0x14001b444`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001b48f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b48f`
- `ntoskrnl!KeReleaseMutex` at `0x14001b4ec`
- `ntoskrnl!KeReleaseMutex` at `0x14001b510`
- `ntoskrnl!KeReleaseMutex` at `0x14001b4ec`
- `ntoskrnl!KeReleaseMutex` at `0x14001b510`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b524`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b54e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b524`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b54e`
- `ntoskrnl!ObfReferenceObject` at `0x14001b46b`
- `ntoskrnl!ObfReferenceObject` at `0x14001b46b`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14001b4d3`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14001b4d3`

## pseudocode

```c
__int64 __fastcall TmpNamespaceInsert(PRTL_AVL_TABLE Table, PVOID Object, __int64 a3)
{
  __int64 v6; // rdx
  __int128 v8; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 NewElement; // [rsp+70h] [rbp+8h] BYREF

  NewElement = 0;
  v8 = 0;
  if ( Object )
    ObfReferenceObject(Object);
  KeWaitForSingleObject(&Table[1], Executive, 0, 0, 0);
  if ( BYTE4(Table[1].RestartKey) )
  {
    KeReleaseMutex((PRKMUTEX)&Table[1], 0);
    if ( Object )
      ObfDereferenceObject(Object);
    return TmpShutdownOccurred != 0 ? -1073741077 : -1072103339;
  }
  else
  {
    v6 = LOWORD(Table[1].RestartKey) + 32LL;
    DWORD2(v8) = 0;
    *(_QWORD *)&v8 = a3;
    Table->TableContext = &v8;
    RtlInsertElementGenericTableAvl(Table, (PVOID)(a3 + v6), 0, &NewElement);
    Table->TableContext = 0;
    KeReleaseMutex((PRKMUTEX)&Table[1], 0);
    if ( NewElement )
    {
      return 0;
    }
    else
    {
      if ( Object )
        ObfDereferenceObject(Object);
      return 3221225525LL;
    }
  }
}

```

## disassembly

```asm
0x14001b444  push    rbx
0x14001b446  push    rbp
0x14001b447  push    rsi
0x14001b448  push    rdi
0x14001b449  sub     rsp, 48h
0x14001b44d  mov     [rsp+68h+NewElement], 0
0x14001b452  xorps   xmm0, xmm0
0x14001b455  mov     rbp, r8
0x14001b458  mov     rbx, rdx
0x14001b45b  mov     rdi, rcx
0x14001b45e  movups  [rsp+68h+var_38], xmm0
0x14001b463  test    rdx, rdx
0x14001b466  jz      short loc_14001B477
0x14001b468  mov     rcx, rdx; Object
0x14001b46b  call    cs:__imp_ObfReferenceObject
0x14001b472  nop     dword ptr [rax+rax+00h]
0x14001b477  lea     rsi, [rdi+68h]
0x14001b47b  mov     [rsp+68h+Timeout], 0; Timeout
0x14001b484  mov     rcx, rsi; Object
0x14001b487  xor     r9d, r9d; Alertable
0x14001b48a  xor     r8d, r8d; WaitMode
0x14001b48d  xor     edx, edx; WaitReason
0x14001b48f  call    cs:__imp_KeWaitForSingleObject
0x14001b496  nop     dword ptr [rax+rax+00h]
0x14001b49b  cmp     byte ptr [rdi+0A4h], 0
0x14001b4a2  jnz     short loc_14001B50B
0x14001b4a4  movzx   edx, word ptr [rdi+0A0h]
0x14001b4ab  lea     rax, [rsp+68h+var_38]
0x14001b4b0  add     rdx, 20h ; ' '
0x14001b4b4  mov     dword ptr [rsp+68h+var_38+8], 0
0x14001b4bc  add     rdx, rbp; Buffer
0x14001b4bf  mov     qword ptr [rsp+68h+var_38], rbp
0x14001b4c4  lea     r9, [rsp+68h+NewElement]; NewElement
0x14001b4c9  mov     [rdi+60h], rax
0x14001b4cd  xor     r8d, r8d; BufferSize
0x14001b4d0  mov     rcx, rdi; Table
0x14001b4d3  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14001b4da  nop     dword ptr [rax+rax+00h]
0x14001b4df  xor     edx, edx; Wait
0x14001b4e1  mov     qword ptr [rdi+60h], 0
0x14001b4e9  mov     rcx, rsi; Mutex
0x14001b4ec  call    cs:__imp_KeReleaseMutex
0x14001b4f3  nop     dword ptr [rax+rax+00h]
0x14001b4f8  cmp     [rsp+68h+NewElement], 0
0x14001b4fd  jz      short loc_14001B546
0x14001b4ff  xor     eax, eax
0x14001b501  add     rsp, 48h
0x14001b505  pop     rdi
0x14001b506  pop     rsi
0x14001b507  pop     rbp
0x14001b508  pop     rbx
0x14001b509  retn
0x14001b50b  xor     edx, edx; Wait
0x14001b50d  mov     rcx, rsi; Mutex
0x14001b510  call    cs:__imp_KeReleaseMutex
0x14001b517  nop     dword ptr [rax+rax+00h]
0x14001b51c  test    rbx, rbx
0x14001b51f  jz      short loc_14001B530
0x14001b521  mov     rcx, rbx; Object
0x14001b524  call    cs:__imp_ObfDereferenceObject
0x14001b52b  nop     dword ptr [rax+rax+00h]
0x14001b530  mov     al, cs:TmpShutdownOccurred
0x14001b536  neg     al
0x14001b538  sbb     eax, eax
0x14001b53a  and     eax, 0FFE70296h
0x14001b53f  add     eax, 0C0190055h
0x14001b544  jmp     short loc_14001B501
0x14001b546  test    rbx, rbx
0x14001b549  jz      short loc_14001B55A
0x14001b54b  mov     rcx, rbx; Object
0x14001b54e  call    cs:__imp_ObfDereferenceObject
0x14001b555  nop     dword ptr [rax+rax+00h]
0x14001b55a  mov     eax, 0C0000035h
0x14001b55f  jmp     short loc_14001B501
```
