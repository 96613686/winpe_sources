# ReadCVTShort

- ea: `0x18000b728`
- end: `0x18000b8e9`
- name: `ReadCVTShort`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b540`

## callees

- `0x18000b728`
- `0x18000bc10`
- `0x18000bc34`
- `0x18000d53c`
- `0x18001c9ec`

## import_xrefs

- `msvcrt!longjmp` at `0x18000b8ce`
- `msvcrt!longjmp` at `0x18000b8e2`
- `msvcrt!longjmp` at `0x18000b8ce`
- `msvcrt!longjmp` at `0x18000b8e2`

## pseudocode

```c
__int64 __fastcall ReadCVTShort(__int64 a1, unsigned __int64 *a2, unsigned __int64 a3)
{
  unsigned __int8 *v6; // rax
  unsigned __int16 v7; // di
  unsigned __int16 v8; // bx
  unsigned __int16 v9; // cx
  char *v11; // rdx
  __int16 ByteAtPointer; // bx

  CheckReadBoundsTTFConverter(a1, *a2);
  v6 = (unsigned __int8 *)*a2;
  if ( *a2 >= a3 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 96) + 48LL), 3362);
  v7 = *v6;
  *a2 = (unsigned __int64)(v6 + 1);
  if ( (unsigned __int8)v7 < 0xEEu )
  {
    return v7;
  }
  else if ( (unsigned __int8)v7 >= 0xF8u )
  {
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), 1);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), 1);
    CheckReadBoundsTTFConverter(a1, *a2);
    ByteAtPointer = (unsigned __int8)ReadByteAtPointer(*(_QWORD *)(a1 + 96), a2, a3);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), 1);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), (unsigned __int8)ByteAtPointer < 0xEEu);
    return (unsigned __int16)(ByteAtPointer + 238 * v7 + 6750);
  }
  else if ( (unsigned __int8)(v7 + 17) > 8u )
  {
    if ( (_BYTE)v7 != 0xEE )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v11 = (char *)*a2;
    if ( *a2 >= a3 - 1 )
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 96) + 48LL), 3362);
    v9 = (*v11 << 8) | (unsigned __int8)v11[1];
    *a2 = (unsigned __int64)(v11 + 2);
  }
  else
  {
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), v7 >= 0xEFu);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), v7 <= 0xF7u);
    CheckReadBoundsTTFConverter(a1, *a2);
    v8 = (unsigned __int8)ReadByteAtPointer(*(_QWORD *)(a1 + 96), a2, a3);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), 1);
    VerifyConditionInternal(*(_QWORD *)(a1 + 96), v8 < 0xEEu);
    return (unsigned __int16)(-8654 - 238 * v7 - v8);
  }
  return v9;
}

```

## disassembly

```asm
0x18000b728  push    rbx
0x18000b72a  push    rbp
0x18000b72b  push    rsi
0x18000b72c  push    rdi
0x18000b72d  push    r12
0x18000b72f  push    r14
0x18000b731  sub     rsp, 28h
0x18000b735  mov     rbx, rdx
0x18000b738  mov     rbp, r8
0x18000b73b  mov     rdx, [rdx]
0x18000b73e  mov     rsi, rcx
0x18000b741  call    CheckReadBoundsTTFConverter
0x18000b746  mov     rax, [rbx]
0x18000b749  cmp     rax, rbp
0x18000b74c  jnb     loc_18000B8C1
0x18000b752  movzx   edi, byte ptr [rax]
0x18000b755  mov     r12d, 0EEh
0x18000b75b  inc     rax
0x18000b75e  mov     [rbx], rax
0x18000b761  cmp     dil, r12b
0x18000b764  jb      loc_18000B815
0x18000b76a  cmp     dil, 0F8h
0x18000b76e  jnb     loc_18000B84B
0x18000b774  lea     eax, [rdi+11h]
0x18000b777  cmp     al, 8
0x18000b779  ja      loc_18000B81A
0x18000b77f  mov     rcx, [rsi+60h]
0x18000b783  lea     eax, [r12+1]
0x18000b788  xor     r14d, r14d
0x18000b78b  cmp     di, ax
0x18000b78e  mov     edx, r14d
0x18000b791  setnb   dl
0x18000b794  call    VerifyConditionInternal
0x18000b799  mov     rcx, [rsi+60h]
0x18000b79d  lea     eax, [r12+9]
0x18000b7a2  cmp     di, ax
0x18000b7a5  mov     edx, r14d
0x18000b7a8  setbe   dl
0x18000b7ab  call    VerifyConditionInternal
0x18000b7b0  mov     rdx, [rbx]
0x18000b7b3  mov     rcx, rsi
0x18000b7b6  call    CheckReadBoundsTTFConverter
0x18000b7bb  mov     rcx, [rsi+60h]
0x18000b7bf  mov     r8, rbp
0x18000b7c2  mov     rdx, rbx
0x18000b7c5  call    ReadByteAtPointer
0x18000b7ca  mov     rcx, [rsi+60h]
0x18000b7ce  lea     edx, [r14+1]
0x18000b7d2  movzx   ebx, al
0x18000b7d5  call    VerifyConditionInternal
0x18000b7da  mov     rcx, [rsi+60h]
0x18000b7de  cmp     bx, r12w
0x18000b7e2  setb    r14b
0x18000b7e6  mov     edx, r14d
0x18000b7e9  call    VerifyConditionInternal
0x18000b7ee  movsx   eax, r12w
0x18000b7f2  mov     ecx, edi
0x18000b7f4  imul    ecx, eax
0x18000b7f7  mov     eax, 0FFFFDE32h
0x18000b7fc  sub     ax, cx
0x18000b7ff  sub     ax, bx
0x18000b802  movzx   ecx, ax
0x18000b805  movzx   eax, cx
0x18000b808  add     rsp, 28h
0x18000b80c  pop     r14
0x18000b80e  pop     r12
0x18000b810  pop     rdi
0x18000b811  pop     rsi
0x18000b812  pop     rbp
0x18000b813  pop     rbx
0x18000b814  retn
0x18000b815  movzx   ecx, di
0x18000b818  jmp     short loc_18000B805
0x18000b81a  cmp     dil, r12b
0x18000b81d  jz      short loc_18000B824
0x18000b81f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b824  mov     rdx, [rbx]
0x18000b827  lea     rax, [rbp-1]
0x18000b82b  cmp     rdx, rax
0x18000b82e  jnb     loc_18000B8D5
0x18000b834  movsx   eax, byte ptr [rdx]
0x18000b837  movzx   ecx, byte ptr [rdx+1]
0x18000b83b  shl     ax, 8
0x18000b83f  or      cx, ax
0x18000b842  lea     rax, [rdx+2]
0x18000b846  mov     [rbx], rax
0x18000b849  jmp     short loc_18000B805
0x18000b84b  mov     rcx, [rsi+60h]
0x18000b84f  mov     edx, 1
0x18000b854  call    VerifyConditionInternal
0x18000b859  mov     rcx, [rsi+60h]
0x18000b85d  mov     edx, 1
0x18000b862  call    VerifyConditionInternal
0x18000b867  mov     rdx, [rbx]
0x18000b86a  mov     rcx, rsi
0x18000b86d  call    CheckReadBoundsTTFConverter
0x18000b872  mov     rcx, [rsi+60h]
0x18000b876  mov     r8, rbp
0x18000b879  mov     rdx, rbx
0x18000b87c  call    ReadByteAtPointer
0x18000b881  mov     rcx, [rsi+60h]
0x18000b885  mov     edx, 1
0x18000b88a  movzx   ebx, al
0x18000b88d  call    VerifyConditionInternal
0x18000b892  mov     rcx, [rsi+60h]
0x18000b896  xor     r14d, r14d
0x18000b899  cmp     bl, r12b
0x18000b89c  setb    r14b
0x18000b8a0  mov     edx, r14d
0x18000b8a3  call    VerifyConditionInternal
0x18000b8a8  mov     ecx, edi
0x18000b8aa  movsx   edx, r12w
0x18000b8ae  imul    ecx, edx
0x18000b8b1  mov     eax, 1A5Eh
0x18000b8b6  add     cx, bx
0x18000b8b9  add     cx, ax
0x18000b8bc  jmp     loc_18000B805
0x18000b8c1  mov     rcx, [rsi+60h]
0x18000b8c5  mov     edx, 0D22h; Value
0x18000b8ca  add     rcx, 30h ; '0'; Buf
0x18000b8ce  call    cs:__imp_longjmp
0x18000b8d5  mov     rcx, [rsi+60h]
0x18000b8d9  mov     edx, 0D22h; Value
0x18000b8de  add     rcx, 30h ; '0'; Buf
0x18000b8e2  call    cs:__imp_longjmp
```
