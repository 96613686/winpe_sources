# UdfSeqCacheFlushCache

- ea: `0x14001a060`
- end: `0x14001a22c`
- name: `UdfSeqCacheFlushCache`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003b730`

## callees

- `0x140009f60`
- `0x140009ff4`
- `0x14000cad4`
- `0x14001093c`
- `0x14001a060`
- `0x14001c080`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14001a21f`
- `ntoskrnl!ExRaiseStatus` at `0x14001a21f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a0e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a18e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a19d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a0e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a18e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a19d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a200`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001a200`

## pseudocode

```c
void __fastcall UdfSeqCacheFlushCache(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebp
  __int64 v9; // r8
  _DWORD v10[34]; // [rsp+30h] [rbp-88h] BYREF

  memset(v10, 0, 0x40u);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0x1Du) )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 15, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
  }
  UdfAcquireResource(a1, a3 + 344, 0, 0);
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 104) + 4LL) & 0x10) != 0 )
  {
    ExReleaseResourceLite((PERESOURCE)(a3 + 344));
  }
  else
  {
    v8 = -1;
    UdfAcquireResource(a1, a3 + 448, 0, 0);
    if ( *(_DWORD *)(a3 + 40LL * *(unsigned int *)(a3 + 16) + 28) < *(_DWORD *)(a3 + 8)
      && !*(_WORD *)(a3 + 40LL * *(unsigned int *)(a3 + 16) + 24) )
    {
      UdfSeqCacheMarkActiveBufferForWrite(a3, a4);
    }
    v9 = *(unsigned int *)(a3 + 16);
    while ( (*(_BYTE *)(a3 + 40LL * (unsigned int)v9 + 24) & 0xB) == 0 )
    {
      if ( (_DWORD)v9 )
        v9 = (unsigned int)(v9 - 1);
      else
        v9 = 7;
      if ( (_DWORD)v9 == *(_DWORD *)(a3 + 16) )
        goto LABEL_19;
    }
    v8 = v9;
    if ( (_DWORD)v9 != -1 )
    {
      UdfSeqCacheInsertFlushWaitBlock(a3, v10, v9);
      LOBYTE(v10[14]) = 1;
    }
LABEL_19:
    ExReleaseResourceLite((PERESOURCE)(a3 + 448));
    ExReleaseResourceLite((PERESOURCE)(a3 + 344));
    if ( v8 != -1 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          16,
          WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
          v8,
          v10[10]);
      }
      KeWaitForSingleObject(&v10[4], Executive, 0, 0, 0);
      if ( v10[11] == -2147483626 )
      {
        *(_DWORD *)(a1 + 24) = -2147483626;
        ExRaiseStatus(-2147483626);
      }
    }
  }
}

```

## disassembly

```asm
0x14001a060  push    rbx
0x14001a062  push    rbp
0x14001a063  push    rsi
0x14001a064  push    rdi
0x14001a065  push    r12
0x14001a067  push    r13
0x14001a069  push    r14
0x14001a06b  push    r15
0x14001a06d  sub     rsp, 78h
0x14001a071  mov     rbx, rdx
0x14001a074  mov     rdi, r8
0x14001a077  xor     edx, edx; Val
0x14001a079  mov     r14, rcx
0x14001a07c  lea     rcx, [rsp+0B8h+var_88]; void *
0x14001a081  mov     r15, r9
0x14001a084  lea     r8d, [rdx+40h]; Size
0x14001a088  call    memset
0x14001a08d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a094  lea     rax, WPP_GLOBAL_Control
0x14001a09b  cmp     rcx, rax
0x14001a09e  jz      short loc_14001A0BC
0x14001a0a0  bt      dword ptr [rcx+2Ch], 1Dh
0x14001a0a5  jnb     short loc_14001A0BC
0x14001a0a7  mov     rcx, [rcx+18h]
0x14001a0ab  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14001a0b2  mov     edx, 0Fh
0x14001a0b7  call    WPP_SF_
0x14001a0bc  lea     rsi, [rdi+158h]
0x14001a0c3  xor     r9d, r9d
0x14001a0c6  mov     rdx, rsi
0x14001a0c9  xor     r8d, r8d
0x14001a0cc  mov     rcx, r14
0x14001a0cf  call    UdfAcquireResource
0x14001a0d4  mov     rax, [rbx+68h]
0x14001a0d8  xor     ebx, ebx
0x14001a0da  mov     ecx, [rax+4]
0x14001a0dd  and     ecx, 10h
0x14001a0e0  test    ecx, ecx
0x14001a0e2  jz      short loc_14001A105
0x14001a0e4  mov     rcx, rsi; Resource
0x14001a0e7  call    cs:__imp_ExReleaseResourceLite
0x14001a0ee  nop     dword ptr [rax+rax+00h]
0x14001a0f3  add     rsp, 78h
0x14001a0f7  pop     r15
0x14001a0f9  pop     r14
0x14001a0fb  pop     r13
0x14001a0fd  pop     r12
0x14001a0ff  pop     rdi
0x14001a100  pop     rsi
0x14001a101  pop     rbp
0x14001a102  pop     rbx
0x14001a103  retn
0x14001a105  lea     r12, [rdi+1C0h]
0x14001a10c  or      r13d, 0FFFFFFFFh
0x14001a110  mov     rdx, r12
0x14001a113  xor     r9d, r9d
0x14001a116  xor     r8d, r8d
0x14001a119  mov     rcx, r14
0x14001a11c  mov     ebp, r13d
0x14001a11f  call    UdfAcquireResource
0x14001a124  mov     eax, [rdi+10h]
0x14001a127  lea     rcx, [rax+rax*4]
0x14001a12b  mov     eax, [rdi+8]
0x14001a12e  cmp     [rdi+rcx*8+1Ch], eax
0x14001a132  jnb     short loc_14001A146
0x14001a134  cmp     bx, [rdi+rcx*8+18h]
0x14001a139  jnz     short loc_14001A146
0x14001a13b  mov     rdx, r15
0x14001a13e  mov     rcx, rdi
0x14001a141  call    UdfSeqCacheMarkActiveBufferForWrite
0x14001a146  mov     edx, [rdi+10h]
0x14001a149  mov     r8d, edx
0x14001a14c  mov     eax, r8d
0x14001a14f  lea     rcx, [rax+rax*4]
0x14001a153  test    byte ptr [rdi+rcx*8+18h], 0Bh
0x14001a158  jnz     short loc_14001A171
0x14001a15a  test    r8d, r8d
0x14001a15d  jz      short loc_14001A164
0x14001a15f  add     r8d, r13d
0x14001a162  jmp     short loc_14001A16A
0x14001a164  mov     r8d, 7
0x14001a16a  cmp     r8d, edx
0x14001a16d  jnz     short loc_14001A14C
0x14001a16f  jmp     short loc_14001A18B
0x14001a171  mov     ebp, r8d
0x14001a174  cmp     r8d, r13d
0x14001a177  jz      short loc_14001A18B
0x14001a179  lea     rdx, [rsp+0B8h+var_88]
0x14001a17e  mov     rcx, rdi
0x14001a181  call    UdfSeqCacheInsertFlushWaitBlock
0x14001a186  mov     [rsp+0B8h+var_50], 1
0x14001a18b  mov     rcx, r12; Resource
0x14001a18e  call    cs:__imp_ExReleaseResourceLite
0x14001a195  nop     dword ptr [rax+rax+00h]
0x14001a19a  mov     rcx, rsi; Resource
0x14001a19d  call    cs:__imp_ExReleaseResourceLite
0x14001a1a4  nop     dword ptr [rax+rax+00h]
0x14001a1a9  cmp     ebp, r13d
0x14001a1ac  jz      loc_14001A0F3
0x14001a1b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a1b9  lea     rax, WPP_GLOBAL_Control
0x14001a1c0  cmp     rcx, rax
0x14001a1c3  jz      short loc_14001A1EE
0x14001a1c5  test    dword ptr [rcx+2Ch], 20000000h
0x14001a1cc  jz      short loc_14001A1EE
0x14001a1ce  mov     eax, [rsp+0B8h+var_60]
0x14001a1d2  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x14001a1d9  mov     rcx, [rcx+18h]
0x14001a1dd  mov     edx, 10h
0x14001a1e2  mov     r9d, ebp
0x14001a1e5  mov     dword ptr [rsp+0B8h+Timeout], eax
0x14001a1e9  call    WPP_SF_dd
0x14001a1ee  xor     r9d, r9d; Alertable
0x14001a1f1  mov     [rsp+0B8h+Timeout], rbx; Timeout
0x14001a1f6  xor     r8d, r8d; WaitMode
0x14001a1f9  lea     rcx, [rsp+0B8h+Object]; Object
0x14001a1fe  xor     edx, edx; WaitReason
0x14001a200  call    cs:__imp_KeWaitForSingleObject
0x14001a207  nop     dword ptr [rax+rax+00h]
0x14001a20c  mov     ecx, 80000016h; Status
0x14001a211  cmp     [rsp+0B8h+var_5C], ecx
0x14001a215  jnz     loc_14001A0F3
0x14001a21b  mov     [r14+18h], ecx
0x14001a21f  call    cs:__imp_ExRaiseStatus
```
