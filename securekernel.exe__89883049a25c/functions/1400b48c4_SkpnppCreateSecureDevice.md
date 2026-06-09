# SkpnppCreateSecureDevice

- ea: `0x1400b48c4`
- end: `0x1400b4aba`
- name: `SkpnppCreateSecureDevice`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400b472c`

## callees

- `0x140002ef0`
- `0x1400a0c00`
- `0x1400a0df8`
- `0x1400a18a0`
- `0x1400b4750`
- `0x1400b47d4`
- `0x1400b48c4`
- `0x1400b4ac0`
- `0x1400b521c`

## pseudocode

```c
__int64 __fastcall SkpnppCreateSecureDevice(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  _QWORD *StackBase; // rax
  __int64 v6; // r14
  __int64 v7; // r14
  int v8; // edx
  int v9; // edi
  int v10; // r8d
  _QWORD *v11; // rbx
  int Handle; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  int *v20; // rax
  int v21; // r9d
  int v22; // ecx
  _QWORD v24[7]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+18h] BYREF
  _QWORD *v26; // [rsp+B8h] [rbp+20h] BYREF

  v2 = 0;
  v25 = 0;
  v24[0] = 0;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v6 = StackBase[10];
  else
    v6 = 0;
  v7 = *(_QWORD *)(v6 + 432);
  v26 = 0;
  v9 = SkobCreateObjectEx(0, (__int64)&SkPnpSecureDeviceObjectType, 0, &v26);
  if ( v9 < 0 )
  {
    v22 = (int)v26;
    v11 = 0;
    if ( v26 )
      SkobDereferenceObject((__int64)v26);
    if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 8) != 0 )
      McTemplateK0xxqd_EtwWriteTransfer(v22, v8, v10, a1, v7, 1, v9);
    goto LABEL_22;
  }
  v11 = v26;
  *v26 = 0;
  Handle = SkobCreateHandle((__int64)v11, 0, 0, (__int64)&v25);
  v9 = Handle;
  if ( Handle < 0 )
  {
    if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 8) != 0 )
      McTemplateK0xxqd_EtwWriteTransfer(v14, v13, v15, a1, v7, 2, Handle);
    v2 = v25;
    goto LABEL_22;
  }
  v2 = v25;
  v16 = SkpnppProbeAndWriteSizeT(a2, v25);
  v9 = v16;
  if ( v16 < 0 )
  {
    if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 8) != 0 )
      McTemplateK0xxqd_EtwWriteTransfer(v18, v17, v19, a1, v7, 3, v16);
    goto LABEL_22;
  }
  v9 = SkpnppAttachDevice(a1, v11, v24);
  if ( v9 < 0 )
  {
LABEL_22:
    if ( v2 )
      SkobCloseHandleEx(v2, 0, 0, 0, 0);
    goto LABEL_24;
  }
  if ( v24[0] )
  {
    v20 = *(int **)(v24[0] + 80LL);
    LOBYTE(v21) = 0;
    if ( v20 )
      v21 = *v20;
    if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 4) != 0 )
      McTemplateK0xxsqqqtq_EtwWriteTransfer(
        *(unsigned __int8 *)(v24[0] + 96LL),
        LODWORD(v24[0]) + 104,
        v24[0],
        a1,
        v7,
        v24[0] + 104LL,
        v21,
        *(_DWORD *)(v24[0] + 20LL),
        *(_DWORD *)(v24[0] + 100LL),
        *(_BYTE *)(v24[0] + 96LL),
        *(_DWORD *)(v24[0] + 140LL));
  }
LABEL_24:
  if ( v11 )
    SkobDereferenceObject((__int64)v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400b48c4  mov     rax, rsp
0x1400b48c7  mov     [rax+8], rbx
0x1400b48cb  push    rbp
0x1400b48cc  push    rsi
0x1400b48cd  push    rdi
0x1400b48ce  push    r14
0x1400b48d0  push    r15
0x1400b48d2  sub     rsp, 70h
0x1400b48d6  xor     esi, esi
0x1400b48d8  mov     r15, rdx
0x1400b48db  mov     [rax+18h], rsi
0x1400b48df  mov     rbp, rcx
0x1400b48e2  mov     [rax-38h], rsi
0x1400b48e6  mov     rax, gs:8
0x1400b48ef  test    rax, rax
0x1400b48f2  jz      short loc_1400B48FA
0x1400b48f4  mov     r14, [rax+50h]
0x1400b48f8  jmp     short loc_1400B48FD
0x1400b48fa  xor     r14d, r14d
0x1400b48fd  mov     r14, [r14+1B0h]
0x1400b4904  lea     r9, [rsp+98h+arg_18]
0x1400b490c  xor     r8d, r8d
0x1400b490f  mov     [rsp+98h+arg_18], rsi
0x1400b4917  lea     rdx, SkPnpSecureDeviceObjectType
0x1400b491e  xor     ecx, ecx
0x1400b4920  call    SkobCreateObjectEx
0x1400b4925  mov     edi, eax
0x1400b4927  test    eax, eax
0x1400b4929  js      loc_1400B4A42
0x1400b492f  mov     rbx, [rsp+98h+arg_18]
0x1400b4937  xor     eax, eax
0x1400b4939  mov     [rbx], rax
0x1400b493c  lea     r9, [rsp+98h+arg_10]
0x1400b4944  xor     r8d, r8d
0x1400b4947  xor     edx, edx
0x1400b4949  mov     rcx, rbx
0x1400b494c  call    SkobCreateHandle
0x1400b4951  mov     edi, eax
0x1400b4953  test    eax, eax
0x1400b4955  jns     short loc_1400B4986
0x1400b4957  test    byte ptr cs:Microsoft_Windows_IsolatedUserModeEnableBits, 8
0x1400b495e  jz      short loc_1400B4979
0x1400b4960  mov     [rsp+98h+var_68], eax
0x1400b4964  mov     r9, rbp
0x1400b4967  mov     dword ptr [rsp+98h+var_70], 2
0x1400b496f  mov     [rsp+98h+var_78], r14
0x1400b4974  call    McTemplateK0xxqd_EtwWriteTransfer
0x1400b4979  mov     rsi, [rsp+98h+arg_10]
0x1400b4981  jmp     loc_1400B4A78
0x1400b4986  mov     rsi, [rsp+98h+arg_10]
0x1400b498e  mov     rcx, r15
0x1400b4991  mov     rdx, rsi
0x1400b4994  call    SkpnppProbeAndWriteSizeT
0x1400b4999  mov     edi, eax
0x1400b499b  test    eax, eax
0x1400b499d  jns     short loc_1400B49BD
0x1400b499f  test    byte ptr cs:Microsoft_Windows_IsolatedUserModeEnableBits, 8
0x1400b49a6  jz      loc_1400B4A78
0x1400b49ac  mov     [rsp+98h+var_68], eax
0x1400b49b0  mov     dword ptr [rsp+98h+var_70], 3
0x1400b49b8  jmp     loc_1400B4A6B
0x1400b49bd  lea     r8, [rsp+98h+var_38]
0x1400b49c2  mov     rdx, rbx
0x1400b49c5  mov     rcx, rbp
0x1400b49c8  call    SkpnppAttachDevice
0x1400b49cd  mov     edi, eax
0x1400b49cf  test    eax, eax
0x1400b49d1  js      loc_1400B4A78
0x1400b49d7  mov     r8, [rsp+98h+var_38]
0x1400b49dc  test    r8, r8
0x1400b49df  jz      loc_1400B4A96
0x1400b49e5  mov     rax, [r8+50h]
0x1400b49e9  xor     r9d, r9d
0x1400b49ec  test    rax, rax
0x1400b49ef  jz      short loc_1400B49F4
0x1400b49f1  mov     r9d, [rax]
0x1400b49f4  test    byte ptr cs:Microsoft_Windows_IsolatedUserModeEnableBits, 4
0x1400b49fb  jz      loc_1400B4A96
0x1400b4a01  mov     eax, [r8+8Ch]
0x1400b4a08  lea     rdx, [r8+68h]
0x1400b4a0c  movzx   ecx, byte ptr [r8+60h]
0x1400b4a11  mov     [rsp+98h+var_48], eax
0x1400b4a15  mov     eax, [r8+64h]
0x1400b4a19  mov     [rsp+98h+var_50], ecx
0x1400b4a1d  mov     [rsp+98h+var_58], eax
0x1400b4a21  mov     eax, [r8+14h]
0x1400b4a25  mov     [rsp+98h+var_60], eax
0x1400b4a29  mov     [rsp+98h+var_68], r9d
0x1400b4a2e  mov     r9, rbp
0x1400b4a31  mov     [rsp+98h+var_70], rdx
0x1400b4a36  mov     [rsp+98h+var_78], r14
0x1400b4a3b  call    McTemplateK0xxsqqqtq_EtwWriteTransfer
0x1400b4a40  jmp     short loc_1400B4A96
0x1400b4a42  mov     rcx, [rsp+98h+arg_18]
0x1400b4a4a  xor     ebx, ebx
0x1400b4a4c  test    rcx, rcx
0x1400b4a4f  jz      short loc_1400B4A56
0x1400b4a51  call    SkobDereferenceObject
0x1400b4a56  test    byte ptr cs:Microsoft_Windows_IsolatedUserModeEnableBits, 8
0x1400b4a5d  jz      short loc_1400B4A78
0x1400b4a5f  mov     [rsp+98h+var_68], edi
0x1400b4a63  mov     dword ptr [rsp+98h+var_70], 1
0x1400b4a6b  mov     r9, rbp
0x1400b4a6e  mov     [rsp+98h+var_78], r14
0x1400b4a73  call    McTemplateK0xxqd_EtwWriteTransfer
0x1400b4a78  test    rsi, rsi
0x1400b4a7b  jz      short loc_1400B4A96
0x1400b4a7d  xor     r9d, r9d
0x1400b4a80  mov     [rsp+98h+var_78], 0
0x1400b4a89  xor     r8d, r8d
0x1400b4a8c  xor     edx, edx
0x1400b4a8e  mov     rcx, rsi
0x1400b4a91  call    SkobCloseHandleEx
0x1400b4a96  test    rbx, rbx
0x1400b4a99  jz      short loc_1400B4AA3
0x1400b4a9b  mov     rcx, rbx
0x1400b4a9e  call    SkobDereferenceObject
0x1400b4aa3  mov     rbx, [rsp+98h+arg_0]
0x1400b4aab  mov     eax, edi
0x1400b4aad  add     rsp, 70h
0x1400b4ab1  pop     r15
0x1400b4ab3  pop     r14
0x1400b4ab5  pop     rdi
0x1400b4ab6  pop     rsi
0x1400b4ab7  pop     rbp
0x1400b4ab8  retn
```
