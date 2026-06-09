# VmsVrssPvtFindNblGroup

- ea: `0x140025d10`
- end: `0x140025f75`
- name: `VmsVrssPvtFindNblGroup`
- size: `613`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014a60`
- `0x140024b60`
- `0x140026000`
- `0x14004dcf8`
- `0x1400913d0`

## callees

- `0x140025d10`
- `0x14002e0f0`
- `0x140046f1c`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025d65`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025e99`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025d65`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140025e99`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025edd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025efc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025edd`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140025efc`
- `ntoskrnl!ExAllocatePool2` at `0x140025e14`
- `ntoskrnl!ExAllocatePool2` at `0x140025e14`

## pseudocode

```c
PSLIST_ENTRY __fastcall VmsVrssPvtFindNblGroup(
        __int64 a1,
        __int16 a2,
        int a3,
        unsigned int a4,
        struct _SLIST_ENTRY *a5,
        PSLIST_ENTRY *a6)
{
  struct _SLIST_ENTRY *i; // r10
  char *v10; // rsi
  PSLIST_ENTRY result; // rax
  int v12; // ecx
  signed __int32 v13; // eax
  signed __int32 v14; // edx
  int v15; // edx
  struct _SLIST_ENTRY *Pool2; // r13
  int v17; // edx
  __int64 j; // r12

  for ( i = *a6; i; i = i->Next )
  {
    if ( *((_DWORD *)&i[1].Next[15].Next + 3) == a4 )
      return i;
  }
  v10 = (char *)VmsPlanCpuTable + 5440 * a4 + 576;
  result = ExpInterlockedPopEntrySList((PSLIST_HEADER)v10 + 22);
  if ( result )
    goto LABEL_4;
  v12 = VmsMaxVrssNblGroupPoolCount;
  do
  {
    v13 = *((_DWORD *)v10 + 96);
    v14 = v13 + 1;
    if ( v13 + 1 < 0 || v14 >= v12 )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_ld(
        VmsVrssIfrLog,
        v14,
        3,
        11,
        (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
        *((_DWORD *)v10 + 63),
        *((_DWORD *)v10 + 96));
      goto LABEL_21;
    }
  }
  while ( v13 != _InterlockedCompareExchange((volatile signed __int32 *)v10 + 96, v14, v13) );
  Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(64, 16320, 1349734998);
  if ( !Pool2 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v10 + 96);
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_ld(VmsVrssIfrLog, v15, 3, 12, (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids, 192, 154);
LABEL_21:
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_id(
      VmsVrssIfrLog,
      v17,
      3,
      13,
      (__int64)WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids,
      (char)v10,
      154);
    goto LABEL_15;
  }
  for ( j = 0; j != 127; ExpInterlockedPushEntrySList((PSLIST_HEADER)v10 + 22, &Pool2[8 * j++ + 4]) )
    Pool2[8 * j + 5].Next = (struct _SLIST_ENTRY *)v10;
  ExpInterlockedPushEntrySList((PSLIST_HEADER)v10 + 14, Pool2);
LABEL_15:
  result = ExpInterlockedPopEntrySList((PSLIST_HEADER)v10 + 22);
  if ( result )
  {
LABEL_4:
    result->Next = 0;
    *((_QWORD *)&result[1].Next + 1) = 0;
    result[2].Next = (PSLIST_ENTRY)((char *)result + 24);
    result[4].Next = a5;
    LODWORD(result[3].Next) = 0;
    *((_BYTE *)&result[3].Next + 10) = 0;
    *((_WORD *)&result[3].Next + 4) = a2;
    *((_QWORD *)&result[2].Next + 1) = a1;
    HIDWORD(result[3].Next) = a3;
    result->Next = *a6;
    *a6 = result;
  }
  return result;
}

```

## disassembly

```asm
0x140025d10  push    rbx
0x140025d12  push    rbp
0x140025d13  push    r14
0x140025d15  push    r15
0x140025d17  sub     rsp, 48h
0x140025d1b  mov     rbx, [rsp+68h+arg_28]
0x140025d23  mov     ebp, r8d
0x140025d26  movzx   r14d, dx
0x140025d2a  mov     r15, rcx
0x140025d2d  mov     r10, [rbx]
0x140025d30  test    r10, r10
0x140025d33  jnz     loc_140025E6E
0x140025d39  mov     [rsp+68h+arg_0], rsi
0x140025d3e  mov     rsi, cs:VmsPlanCpuTable
0x140025d45  mov     eax, r9d
0x140025d48  add     rsi, 240h
0x140025d4f  imul    rcx, rax, 1540h
0x140025d56  mov     [rsp+68h+arg_8], rdi
0x140025d5b  add     rsi, rcx
0x140025d5e  lea     rcx, [rsi+160h]; ListHead
0x140025d65  call    cs:__imp_ExpInterlockedPopEntrySList
0x140025d6c  nop     dword ptr [rax+rax+00h]
0x140025d71  test    rax, rax
0x140025d74  jz      short loc_140025DCE
0x140025d76  lea     rcx, [rax+18h]
0x140025d7a  mov     qword ptr [rax], 0
0x140025d81  mov     qword ptr [rcx], 0
0x140025d88  mov     [rax+20h], rcx
0x140025d8c  mov     rcx, [rsp+68h+arg_20]
0x140025d94  mov     [rax+40h], rcx
0x140025d98  mov     dword ptr [rax+30h], 0
0x140025d9f  mov     byte ptr [rax+3Ah], 0
0x140025da3  mov     [rax+38h], r14w
0x140025da8  mov     [rax+28h], r15
0x140025dac  mov     [rax+34h], ebp
0x140025daf  mov     rcx, [rbx]
0x140025db2  mov     [rax], rcx
0x140025db5  mov     [rbx], rax
0x140025db8  mov     rsi, [rsp+68h+arg_0]
0x140025dbd  mov     rdi, [rsp+68h+arg_8]
0x140025dc2  add     rsp, 48h
0x140025dc6  pop     r15
0x140025dc8  pop     r14
0x140025dca  pop     rbp
0x140025dcb  pop     rbx
0x140025dcc  retn
0x140025dce  mov     ecx, cs:VmsMaxVrssNblGroupPoolCount
0x140025dd4  mov     [rsp+68h+arg_10], r12
0x140025ddc  mov     [rsp+68h+var_28], r13
0x140025de1  mov     eax, [rsi+180h]
0x140025de7  lea     edx, [rax+1]
0x140025dea  test    edx, edx
0x140025dec  js      loc_140025F0A
0x140025df2  cmp     edx, ecx
0x140025df4  jge     loc_140025F0A
0x140025dfa  lock cmpxchg [rsi+180h], edx
0x140025e02  jnz     short loc_140025DE1
0x140025e04  mov     edx, 3FC0h
0x140025e09  mov     ecx, 40h ; '@'
0x140025e0e  mov     r8d, 50735256h
0x140025e14  call    cs:__imp_ExAllocatePool2
0x140025e1b  nop     dword ptr [rax+rax+00h]
0x140025e20  mov     r13, rax
0x140025e23  test    rax, rax
0x140025e26  jnz     loc_140025EC0
0x140025e2c  lock dec dword ptr [rsi+180h]
0x140025e33  mov     rcx, cs:VmsVrssIfrLog
0x140025e3a  lea     r12, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x140025e41  mov     [rsp+68h+var_38], 0C000009Ah
0x140025e49  mov     r9d, 0Ch
0x140025e4f  mov     dword ptr [rsp+68h+var_40], 3FC0h
0x140025e57  mov     r8d, 3
0x140025e5d  mov     dl, 2
0x140025e5f  mov     [rsp+68h+var_48], r12
0x140025e64  call    WPP_RECORDER_SF_ld
0x140025e69  jmp     loc_140025F44
0x140025e6e  mov     rax, [r10+10h]
0x140025e72  cmp     [rax+0FCh], r9d
0x140025e79  jz      short loc_140025E83
0x140025e7b  mov     r10, [r10]
0x140025e7e  jmp     loc_140025D30
0x140025e83  mov     rax, r10
0x140025e86  add     rsp, 48h
0x140025e8a  pop     r15
0x140025e8c  pop     r14
0x140025e8e  pop     rbp
0x140025e8f  pop     rbx
0x140025e90  retn
0x140025e92  lea     rcx, [rsi+160h]; ListHead
0x140025e99  call    cs:__imp_ExpInterlockedPopEntrySList
0x140025ea0  nop     dword ptr [rax+rax+00h]
0x140025ea5  mov     r13, [rsp+68h+var_28]
0x140025eaa  mov     r12, [rsp+68h+arg_10]
0x140025eb2  test    rax, rax
0x140025eb5  jz      loc_140025DB8
0x140025ebb  jmp     loc_140025D76
0x140025ec0  xor     r12d, r12d
0x140025ec3  mov     rax, r12
0x140025ec6  lea     rdx, [r13+40h]
0x140025eca  shl     rax, 7
0x140025ece  lea     rcx, [rsi+160h]; ListHead
0x140025ed5  add     rdx, rax; ListEntry
0x140025ed8  mov     [rax+r13+50h], rsi
0x140025edd  call    cs:__imp_ExpInterlockedPushEntrySList
0x140025ee4  nop     dword ptr [rax+rax+00h]
0x140025ee9  inc     r12
0x140025eec  cmp     r12, 7Fh
0x140025ef0  jnz     short loc_140025EC3
0x140025ef2  lea     rcx, [rsi+0E0h]; ListHead
0x140025ef9  mov     rdx, r13; ListEntry
0x140025efc  call    cs:__imp_ExpInterlockedPushEntrySList
0x140025f03  nop     dword ptr [rax+rax+00h]
0x140025f08  jmp     short loc_140025E92
0x140025f0a  mov     eax, [rsi+180h]
0x140025f10  lea     r12, WPP_8833d5a3b0633e58bb871197bf680e05_Traceguids
0x140025f17  mov     ecx, [rsi+0FCh]
0x140025f1d  mov     r9d, 0Bh
0x140025f23  mov     [rsp+68h+var_38], eax
0x140025f27  mov     r8d, 3
0x140025f2d  mov     dword ptr [rsp+68h+var_40], ecx
0x140025f31  mov     dl, 2
0x140025f33  mov     rcx, cs:VmsVrssIfrLog
0x140025f3a  mov     [rsp+68h+var_48], r12
0x140025f3f  call    WPP_RECORDER_SF_ld
0x140025f44  mov     rcx, cs:VmsVrssIfrLog
0x140025f4b  mov     r9d, 0Dh
0x140025f51  mov     [rsp+68h+var_38], 0C000009Ah
0x140025f59  mov     r8d, 3
0x140025f5f  mov     [rsp+68h+var_40], rsi
0x140025f64  mov     dl, 2
0x140025f66  mov     [rsp+68h+var_48], r12
0x140025f6b  call    WPP_RECORDER_SF_id
0x140025f70  jmp     loc_140025E92
```
