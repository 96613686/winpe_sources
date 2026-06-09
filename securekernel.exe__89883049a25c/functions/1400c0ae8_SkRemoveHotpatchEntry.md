# SkRemoveHotpatchEntry

- ea: `0x1400c0ae8`
- end: `0x1400c0cae`
- name: `SkRemoveHotpatchEntry`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001b520`
- `0x14004ad00`

## callees

- `0x1400024b0`
- `0x140002900`
- `0x14000b084`
- `0x14000f8b0`
- `0x14001df2c`
- `0x1400357c0`
- `0x140037e68`
- `0x140095cd8`
- `0x1400c0ae8`

## pseudocode

```c
__int64 __fastcall SkRemoveHotpatchEntry(__int64 a1)
{
  _QWORD *StackBase; // rdx
  __int64 v3; // rdx
  _QWORD *v4; // rbx
  int v5; // eax
  __int64 result; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  bool v11; // zf
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rbx
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v3 = StackBase[18];
    if ( v3 )
      --*(_WORD *)(v3 + xmmword_140167150);
  }
  RtlAcquireSRWLockShared(&SkpHotpatchReportTree);
  v4 = (_QWORD *)qword_14014C6E8;
  while ( v4 )
  {
    v5 = SkmiCompareNormalPartitions(a1, v4);
    if ( v5 >= 0 )
    {
      if ( v5 <= 0 )
        break;
      v4 = (_QWORD *)v4[1];
    }
    else
    {
      v4 = (_QWORD *)*v4;
    }
  }
  result = RtlReleaseSRWLockShared(&SkpHotpatchReportTree);
  v9 = KeGetPcr()->NtTib.StackBase;
  if ( v9 )
  {
    v10 = v9[18];
    if ( v10 )
    {
      result = xmmword_140167150;
      v11 = (*(_WORD *)(v10 + xmmword_140167150))++ == 0xFFFF;
      if ( v11 )
      {
        result = xmmword_140167160 + v9[17];
        if ( *(_QWORD *)(v10 + xmmword_140167160) != result )
        {
          result = *((_QWORD *)&xmmword_140167150 + 1);
          if ( !*(_WORD *)(v10 + *((_QWORD *)&xmmword_140167150 + 1)) )
            result = SkiCheckForKernelApcDelivery(xmmword_140167160, v10, v7, v8);
        }
      }
    }
  }
  if ( v4 )
  {
    v12 = KeGetPcr()->NtTib.StackBase;
    if ( v12 )
    {
      v13 = v12[18];
      if ( v13 )
        --*(_WORD *)(v13 + xmmword_140167150);
    }
    SkAcquirePushLockExclusive(&SkpHotpatchReportTree);
    v14 = (_QWORD *)qword_14014C6E8;
    if ( qword_14014C6E8 )
    {
      do
      {
        v15 = SkmiCompareNormalPartitions(a1, v14);
        if ( v15 >= 0 )
        {
          if ( v15 <= 0 )
            break;
          v14 = (_QWORD *)v14[1];
        }
        else
        {
          v14 = (_QWORD *)*v14;
        }
      }
      while ( v14 );
      if ( v14 )
      {
        RtlAvlRemoveNode((unsigned __int64 *)&qword_14014C6E8, (__int64)v14);
        --dword_14014C6F0;
        SkFreePool(512, v14);
      }
    }
    result = RtlReleaseSRWLockExclusive(&SkpHotpatchReportTree);
    v18 = KeGetPcr()->NtTib.StackBase;
    if ( v18 )
    {
      v19 = v18[18];
      if ( v19 )
      {
        result = xmmword_140167150;
        v11 = (*(_WORD *)(v19 + xmmword_140167150))++ == 0xFFFF;
        if ( v11 )
        {
          result = xmmword_140167160 + v18[17];
          if ( *(_QWORD *)(v19 + xmmword_140167160) != result )
          {
            result = *((_QWORD *)&xmmword_140167150 + 1);
            if ( !*(_WORD *)(v19 + *((_QWORD *)&xmmword_140167150 + 1)) )
              return SkiCheckForKernelApcDelivery(xmmword_140167160, v19, v16, v17);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400c0ae8  push    rbx
0x1400c0aea  push    rsi
0x1400c0aeb  push    rdi
0x1400c0aec  push    r14
0x1400c0aee  sub     rsp, 28h
0x1400c0af2  mov     rdx, gs:8
0x1400c0afb  xor     esi, esi
0x1400c0afd  mov     rdi, rcx
0x1400c0b00  test    rdx, rdx
0x1400c0b03  jz      short loc_1400C0B1D
0x1400c0b05  mov     rdx, [rdx+90h]
0x1400c0b0c  test    rdx, rdx
0x1400c0b0f  jz      short loc_1400C0B1D
0x1400c0b11  mov     rax, qword ptr cs:xmmword_140167150
0x1400c0b18  dec     word ptr [rdx+rax]
0x1400c0b1c  nop
0x1400c0b1d  lea     rcx, SkpHotpatchReportTree
0x1400c0b24  call    RtlAcquireSRWLockShared
0x1400c0b29  mov     rbx, cs:qword_14014C6E8
0x1400c0b30  jmp     short loc_1400C0B4C
0x1400c0b32  mov     rdx, rbx
0x1400c0b35  mov     rcx, rdi
0x1400c0b38  call    SkmiCompareNormalPartitions
0x1400c0b3d  test    eax, eax
0x1400c0b3f  jns     short loc_1400C0B46
0x1400c0b41  mov     rbx, [rbx]
0x1400c0b44  jmp     short loc_1400C0B4C
0x1400c0b46  jle     short loc_1400C0B51
0x1400c0b48  mov     rbx, [rbx+8]
0x1400c0b4c  test    rbx, rbx
0x1400c0b4f  jnz     short loc_1400C0B32
0x1400c0b51  lea     rcx, SkpHotpatchReportTree
0x1400c0b58  call    RtlReleaseSRWLockShared
0x1400c0b5d  mov     rcx, gs:8
0x1400c0b66  mov     r14d, 1
0x1400c0b6c  test    rcx, rcx
0x1400c0b6f  jz      short loc_1400C0BB6
0x1400c0b71  mov     rdx, [rcx+90h]
0x1400c0b78  test    rdx, rdx
0x1400c0b7b  jz      short loc_1400C0BB6
0x1400c0b7d  nop
0x1400c0b7e  mov     rax, qword ptr cs:xmmword_140167150
0x1400c0b85  add     [rdx+rax], r14w
0x1400c0b8a  jnz     short loc_1400C0BB6
0x1400c0b8c  mov     rax, [rcx+88h]
0x1400c0b93  nop
0x1400c0b94  mov     rcx, qword ptr cs:xmmword_140167160
0x1400c0b9b  add     rax, rcx
0x1400c0b9e  cmp     [rdx+rcx], rax
0x1400c0ba2  jz      short loc_1400C0BB6
0x1400c0ba4  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400c0bab  cmp     [rdx+rax], si
0x1400c0baf  jnz     short loc_1400C0BB6
0x1400c0bb1  call    SkiCheckForKernelApcDelivery
0x1400c0bb6  test    rbx, rbx
0x1400c0bb9  jz      loc_1400C0CA3
0x1400c0bbf  mov     rcx, gs:8
0x1400c0bc8  test    rcx, rcx
0x1400c0bcb  jz      short loc_1400C0BE5
0x1400c0bcd  mov     rcx, [rcx+90h]
0x1400c0bd4  test    rcx, rcx
0x1400c0bd7  jz      short loc_1400C0BE5
0x1400c0bd9  mov     rax, qword ptr cs:xmmword_140167150
0x1400c0be0  dec     word ptr [rcx+rax]
0x1400c0be4  nop
0x1400c0be5  lea     rcx, SkpHotpatchReportTree
0x1400c0bec  call    SkAcquirePushLockExclusive
0x1400c0bf1  mov     rbx, cs:qword_14014C6E8
0x1400c0bf8  test    rbx, rbx
0x1400c0bfb  jz      short loc_1400C0C44
0x1400c0bfd  mov     rdx, rbx
0x1400c0c00  mov     rcx, rdi
0x1400c0c03  call    SkmiCompareNormalPartitions
0x1400c0c08  test    eax, eax
0x1400c0c0a  jns     short loc_1400C0C11
0x1400c0c0c  mov     rbx, [rbx]
0x1400c0c0f  jmp     short loc_1400C0C17
0x1400c0c11  jle     short loc_1400C0C1C
0x1400c0c13  mov     rbx, [rbx+8]
0x1400c0c17  test    rbx, rbx
0x1400c0c1a  jnz     short loc_1400C0BFD
0x1400c0c1c  test    rbx, rbx
0x1400c0c1f  jz      short loc_1400C0C44
0x1400c0c21  mov     rdx, rbx
0x1400c0c24  lea     rcx, qword_14014C6E8
0x1400c0c2b  call    RtlAvlRemoveNode
0x1400c0c30  sub     cs:dword_14014C6F0, r14d
0x1400c0c37  mov     rdx, rbx
0x1400c0c3a  mov     ecx, 200h
0x1400c0c3f  call    SkFreePool
0x1400c0c44  lea     rcx, SkpHotpatchReportTree
0x1400c0c4b  call    RtlReleaseSRWLockExclusive
0x1400c0c50  mov     rcx, gs:8
0x1400c0c59  test    rcx, rcx
0x1400c0c5c  jz      short loc_1400C0CA3
0x1400c0c5e  mov     rdx, [rcx+90h]
0x1400c0c65  test    rdx, rdx
0x1400c0c68  jz      short loc_1400C0CA3
0x1400c0c6a  nop
0x1400c0c6b  mov     rax, qword ptr cs:xmmword_140167150
0x1400c0c72  add     [rdx+rax], r14w
0x1400c0c77  jnz     short loc_1400C0CA3
0x1400c0c79  mov     rax, [rcx+88h]
0x1400c0c80  nop
0x1400c0c81  mov     rcx, qword ptr cs:xmmword_140167160
0x1400c0c88  add     rax, rcx
0x1400c0c8b  cmp     [rdx+rcx], rax
0x1400c0c8f  jz      short loc_1400C0CA3
0x1400c0c91  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400c0c98  cmp     [rdx+rax], si
0x1400c0c9c  jnz     short loc_1400C0CA3
0x1400c0c9e  call    SkiCheckForKernelApcDelivery
0x1400c0ca3  add     rsp, 28h
0x1400c0ca7  pop     r14
0x1400c0ca9  pop     rdi
0x1400c0caa  pop     rsi
0x1400c0cab  pop     rbx
0x1400c0cac  retn
```
