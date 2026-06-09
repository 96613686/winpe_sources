# SkpspTlsReplaceVector

- ea: `0x1400afd58`
- end: `0x1400afe89`
- name: `SkpspTlsReplaceVector`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400afb08`

## callees

- `0x140040c7c`
- `0x1400afd58`
- `0x1400afe90`
- `0x1400fc5b8`
- `0x1400fc664`
- `0x1400fc6a0`
- `0x1400fc7c0`
- `0x1400fc808`

## pseudocode

```c
__int64 __fastcall SkpspTlsReplaceVector(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // r13
  _QWORD *v9; // r14
  __int64 ULong64FromUser; // rax
  __int64 v11; // rbx
  unsigned int v12; // eax
  __int64 *v13; // rdi
  __int64 v14; // rcx
  int ULongFromUser; // eax
  __int64 v16; // rax
  int v17; // eax

  v6 = (unsigned int)*a4;
  v7 = 3 * v6;
  v8 = a3 + 16 + 24 * v6;
  v9 = (_QWORD *)(a1 + 88);
  ULong64FromUser = RtlReadULong64FromUser((volatile void *)(a1 + 88));
  v11 = ULong64FromUser;
  if ( ULong64FromUser )
  {
    if ( (_QWORD *)ULong64FromUser == v9 )
    {
      v11 = 0;
      v13 = (__int64 *)(a2 + 8 * v7 + 24);
    }
    else
    {
      v12 = 8 * *(_DWORD *)(a2 + 12);
      if ( v12 && (v11 & 7) != 0 || (v13 = (__int64 *)(a2 + 8 * v7 + 24), v14 = *v13, v12) && (v14 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyToUserFromUser((void *)v14, (void *)v11, v12);
    }
    ULongFromUser = RtlReadULongFromUser((unsigned int *)v8);
    RtlWriteULongToUser((_DWORD *)v8, ULongFromUser | 1);
    RtlWriteULong64ToUser(v9, *v13);
    v16 = RtlReadULong64FromUser((volatile void *)(a1 + 72));
    RtlWriteULong64ToUser((_QWORD *)(v8 + 16), v16);
    RtlWriteULong64ToUser((_QWORD *)(v8 + 8), v11);
    v17 = RtlReadULongFromUser((unsigned int *)v8);
    RtlWriteULongToUser((_DWORD *)v8, v17 ^ 3);
    ++*a4;
  }
  return 0;
}

```

## disassembly

```asm
0x1400afd58  mov     r11, rsp
0x1400afd5b  mov     [r11+8], rbx
0x1400afd5f  mov     [r11+18h], rsi
0x1400afd63  mov     [r11+20h], r9
0x1400afd67  push    rdi
0x1400afd68  push    r12
0x1400afd6a  push    r13
0x1400afd6c  push    r14
0x1400afd6e  push    r15
0x1400afd70  sub     rsp, 30h
0x1400afd74  mov     rdi, rdx
0x1400afd77  mov     r12, rcx
0x1400afd7a  xor     r15d, r15d
0x1400afd7d  mov     eax, [r9]
0x1400afd80  lea     rsi, [rax+rax*2]
0x1400afd84  lea     r13, [r8+10h]
0x1400afd88  lea     r13, [r13+rsi*8+0]
0x1400afd8d  mov     [rsp+58h+arg_8], r13
0x1400afd92  mov     [r11-38h], r15b
0x1400afd96  lea     r14, [rcx+58h]
0x1400afd9a  mov     rcx, r14
0x1400afd9d  call    RtlReadULong64FromUser
0x1400afda2  mov     rbx, rax
0x1400afda5  test    rax, rax
0x1400afda8  jz      loc_1400AFE56
0x1400afdae  cmp     rax, r14
0x1400afdb1  jz      short loc_1400AFDE9
0x1400afdb3  mov     eax, [rdi+0Ch]
0x1400afdb6  shl     eax, 3
0x1400afdb9  test    eax, eax
0x1400afdbb  jz      short loc_1400AFDC2
0x1400afdbd  test    bl, 7
0x1400afdc0  jnz     short loc_1400AFDD6
0x1400afdc2  lea     rdi, [rdi+rsi*8]
0x1400afdc6  add     rdi, 18h
0x1400afdca  mov     rcx, [rdi]; void *
0x1400afdcd  test    eax, eax
0x1400afdcf  jz      short loc_1400AFDDC
0x1400afdd1  test    cl, 7
0x1400afdd4  jz      short loc_1400AFDDC
0x1400afdd6  call    ExRaiseDatatypeMisalignment
0x1400afddc  mov     r8d, eax; Size
0x1400afddf  mov     rdx, rbx; Src
0x1400afde2  call    RtlCopyToUserFromUser
0x1400afde7  jmp     short loc_1400AFDF3
0x1400afde9  xor     ebx, ebx
0x1400afdeb  lea     rdi, [rdi+rsi*8]
0x1400afdef  add     rdi, 18h
0x1400afdf3  mov     rcx, r13
0x1400afdf6  call    RtlReadULongFromUser
0x1400afdfb  or      eax, 1
0x1400afdfe  mov     edx, eax
0x1400afe00  mov     rcx, r13
0x1400afe03  call    RtlWriteULongToUser
0x1400afe08  mov     rdx, [rdi]
0x1400afe0b  mov     rcx, r14
0x1400afe0e  call    RtlWriteULong64ToUser
0x1400afe13  mov     [rsp+58h+var_38], 1
0x1400afe18  lea     rcx, [r12+48h]
0x1400afe1d  call    RtlReadULong64FromUser
0x1400afe22  lea     rcx, [r13+10h]
0x1400afe26  mov     rdx, rax
0x1400afe29  call    RtlWriteULong64ToUser
0x1400afe2e  lea     rcx, [r13+8]
0x1400afe32  mov     rdx, rbx
0x1400afe35  call    RtlWriteULong64ToUser
0x1400afe3a  mov     rcx, r13
0x1400afe3d  call    RtlReadULongFromUser
0x1400afe42  xor     eax, 3
0x1400afe45  mov     edx, eax
0x1400afe47  mov     rcx, r13
0x1400afe4a  call    RtlWriteULongToUser
0x1400afe4f  mov     rax, [rsp+58h+arg_18]
0x1400afe54  inc     dword ptr [rax]
0x1400afe56  jmp     short loc_1400AFE6D
0x1400afe58  mov     r15d, eax
0x1400afe5b  cmp     [rsp+58h+var_38], 0
0x1400afe60  jnz     short loc_1400AFE6D
0x1400afe62  mov     rcx, [rsp+58h+arg_8]
0x1400afe67  call    SkpspTryClearTlsUnknownFlag
0x1400afe6c  nop
0x1400afe6d  mov     eax, r15d
0x1400afe70  mov     rbx, [rsp+58h+arg_0]
0x1400afe75  mov     rsi, [rsp+58h+arg_10]
0x1400afe7a  add     rsp, 30h
0x1400afe7e  pop     r15
0x1400afe80  pop     r14
0x1400afe82  pop     r13
0x1400afe84  pop     r12
0x1400afe86  pop     rdi
0x1400afe87  retn
```
