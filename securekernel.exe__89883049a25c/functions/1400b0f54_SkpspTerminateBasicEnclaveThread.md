# SkpspTerminateBasicEnclaveThread

- ea: `0x1400b0f54`
- end: `0x1400b10a6`
- name: `SkpspTerminateBasicEnclaveThread`
- size: `338`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140021428`

## callees

- `0x1400010f0`
- `0x1400024b0`
- `0x140002e40`
- `0x140002ef0`
- `0x140036534`
- `0x140098898`
- `0x1400b0f54`
- `0x1400ee8b0`
- `0x1400eedd0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpspTerminateBasicEnclaveThread(__int64 a1)
{
  PVOID StackBase; // rsi
  __int64 v3; // r14
  __int64 v4; // rax
  PVOID v5; // rbp
  char v7; // bl
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v13[2]; // [rsp+30h] [rbp-98h] BYREF
  __int16 v14; // [rsp+32h] [rbp-96h]
  __int64 v15; // [rsp+38h] [rbp-90h]
  __int64 v16; // [rsp+40h] [rbp-88h]
  __int64 v17; // [rsp+48h] [rbp-80h]

  memset_0(v13, 0, 0x68u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  v12 = 0;
  v3 = *((_QWORD *)StackBase + 10);
  v4 = SkpspReferenceBasicEnclaveThread(v3, a1, &v12);
  v5 = (PVOID)v4;
  if ( !v4 )
    return 3221225485LL;
  if ( (PVOID)v4 != StackBase )
    SkeTerminateEnclaveThread(v4);
  SkobDereferenceObject(v5);
  memset_0(v13, 0, 0x68u);
  v14 = 43;
  v15 = *(_QWORD *)(v3 + 240);
  v16 = a1;
  v17 = 0;
  SkCallNormalMode(v13);
  v7 = SkAcquireSpinLockExclusive(v3 + 4);
  RtlAvlRemoveNode(v3 + 264, v12);
  LOBYTE(v8) = v7;
  SkReleaseSpinLockExclusive(v3 + 4, v8);
  if ( v5 == StackBase )
  {
    v11 = *((_QWORD *)StackBase + 18);
    if ( v11 )
      --*(_WORD *)(v11 + *((_QWORD *)&xmmword_140167150 + 1));
    _InterlockedOr((volatile signed __int32 *)StackBase + 43, 2u);
    SkeExitThreadWithReturn((unsigned int)SkpsTerminateEnclaveThread, -1073741749, v9, v10, v12);
  }
  return 0;
}

```

## disassembly

```asm
0x1400b0f54  mov     [rsp+arg_8], rbx
0x1400b0f59  mov     [rsp+arg_10], rbp
0x1400b0f5e  push    rsi
0x1400b0f5f  push    rdi
0x1400b0f60  push    r14
0x1400b0f62  sub     rsp, 0B0h
0x1400b0f69  mov     rax, cs:__security_cookie
0x1400b0f70  xor     rax, rsp
0x1400b0f73  mov     [rsp+0C8h+var_28], rax
0x1400b0f7b  mov     rbx, rcx
0x1400b0f7e  mov     edi, 68h ; 'h'
0x1400b0f83  mov     r8d, edi; Size
0x1400b0f86  lea     rcx, [rsp+0C8h+var_98]; void *
0x1400b0f8b  xor     edx, edx; Val
0x1400b0f8d  call    memset_0
0x1400b0f92  mov     rsi, gs:8
0x1400b0f9b  lea     r8, [rsp+0C8h+var_A8]
0x1400b0fa0  mov     rdx, rbx
0x1400b0fa3  mov     [rsp+0C8h+var_A8], 0
0x1400b0fac  mov     r14, [rsi+50h]
0x1400b0fb0  mov     rcx, r14
0x1400b0fb3  call    SkpspReferenceBasicEnclaveThread
0x1400b0fb8  mov     rbp, rax
0x1400b0fbb  test    rax, rax
0x1400b0fbe  jnz     short loc_1400B0FCA
0x1400b0fc0  mov     eax, 0C000000Dh
0x1400b0fc5  jmp     loc_1400B107D
0x1400b0fca  cmp     rbp, rsi
0x1400b0fcd  jz      short loc_1400B0FD7
0x1400b0fcf  mov     rcx, rbp
0x1400b0fd2  call    SkeTerminateEnclaveThread
0x1400b0fd7  mov     rcx, rbp
0x1400b0fda  call    SkobDereferenceObject
0x1400b0fdf  mov     r8, rdi; Size
0x1400b0fe2  lea     rcx, [rsp+0C8h+var_98]; void *
0x1400b0fe7  xor     edx, edx; Val
0x1400b0fe9  call    memset_0
0x1400b0fee  mov     eax, 2Bh ; '+'
0x1400b0ff3  lea     rcx, [rsp+0C8h+var_98]
0x1400b0ff8  mov     [rsp+0C8h+var_96], ax
0x1400b0ffd  mov     rax, [r14+0F0h]
0x1400b1004  mov     [rsp+0C8h+var_90], rax
0x1400b1009  mov     [rsp+0C8h+var_88], rbx
0x1400b100e  mov     [rsp+0C8h+var_80], 0
0x1400b1017  call    SkCallNormalMode
0x1400b101c  lea     rcx, [r14+4]
0x1400b1020  call    SkAcquireSpinLockExclusive
0x1400b1025  mov     rdx, [rsp+0C8h+var_A8]
0x1400b102a  lea     rcx, [r14+108h]
0x1400b1031  mov     bl, al
0x1400b1033  call    RtlAvlRemoveNode
0x1400b1038  mov     dl, bl
0x1400b103a  lea     rcx, [r14+4]
0x1400b103e  call    SkReleaseSpinLockExclusive
0x1400b1043  cmp     rbp, rsi
0x1400b1046  jnz     short loc_1400B107B
0x1400b1048  mov     rcx, [rsi+90h]
0x1400b104f  test    rcx, rcx
0x1400b1052  jz      short loc_1400B1060
0x1400b1054  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b105b  dec     word ptr [rcx+rax]
0x1400b105f  nop
0x1400b1060  lock or dword ptr [rsi+0ACh], 2
0x1400b1068  mov     rdx, 0FFFFFFFFC000004Bh
0x1400b106f  lea     rcx, SkpsTerminateEnclaveThread
0x1400b1076  call    SkeExitThreadWithReturn
0x1400b107b  xor     eax, eax
0x1400b107d  mov     rcx, [rsp+0C8h+var_28]
0x1400b1085  xor     rcx, rsp; StackCookie
0x1400b1088  call    __security_check_cookie
0x1400b108d  lea     r11, [rsp+0C8h+var_18]
0x1400b1095  mov     rbx, [r11+28h]
0x1400b1099  mov     rbp, [r11+30h]
0x1400b109d  mov     rsp, r11
0x1400b10a0  pop     r14
0x1400b10a2  pop     rdi
0x1400b10a3  pop     rsi
0x1400b10a4  retn
```
