# WofFindOrCreateTransactionContext

- ea: `0x140022c28`
- end: `0x140022cee`
- name: `WofFindOrCreateTransactionContext`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400338e0`

## callees

- `0x140022c28`
- `0x1400236d4`

## import_xrefs

- `FLTMGR!FltSetTransactionContext` at `0x140022ca8`
- `FLTMGR!FltSetTransactionContext` at `0x140022ca8`
- `FLTMGR!FltGetTransactionContext` at `0x140022c5d`
- `FLTMGR!FltGetTransactionContext` at `0x140022c5d`
- `FLTMGR!FltReleaseContext` at `0x140022cbd`
- `FLTMGR!FltReleaseContext` at `0x140022cbd`

## pseudocode

```c
NTSTATUS __fastcall WofFindOrCreateTransactionContext(__int64 a1, struct _KTRANSACTION *a2, PFLT_CONTEXT *a3)
{
  __int64 v4; // rcx
  NTSTATUS result; // eax
  __int64 v8; // rcx
  PFLT_CONTEXT v9; // rdi
  NTSTATUS v10; // ebx
  PFLT_CONTEXT OldContext; // [rsp+40h] [rbp+8h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+58h] [rbp+20h] BYREF

  OldContext = 0;
  v4 = *(_QWORD *)(a1 + 16);
  NewContext = 0;
  result = FltGetTransactionContext(*(PFLT_INSTANCE *)(v4 + 16), a2, &OldContext);
  if ( result >= 0 )
  {
    *a3 = OldContext;
    return result;
  }
  result = WofCreateTransactionContext(&NewContext);
  if ( result >= 0 )
  {
    v8 = *(_QWORD *)(a1 + 16);
    v9 = NewContext;
    v10 = FltSetTransactionContext(
            *(PFLT_INSTANCE *)(v8 + 16),
            a2,
            FLT_SET_CONTEXT_KEEP_IF_EXISTS,
            NewContext,
            &OldContext);
    if ( v10 < 0 )
    {
      FltReleaseContext(v9);
      if ( v10 != -1071906814 )
        return v10;
      v9 = OldContext;
      v10 = 0;
    }
    *a3 = v9;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x140022c28  mov     rax, rsp
0x140022c2b  mov     [rax+10h], rbx
0x140022c2f  mov     [rax+18h], rsi
0x140022c33  push    rdi
0x140022c34  sub     rsp, 30h
0x140022c38  mov     rdi, rcx
0x140022c3b  mov     qword ptr [rax+8], 0
0x140022c43  mov     rcx, [rcx+10h]
0x140022c47  mov     rsi, r8
0x140022c4a  lea     r8, [rax+8]; Context
0x140022c4e  mov     qword ptr [rax+20h], 0
0x140022c56  mov     rbx, rdx
0x140022c59  mov     rcx, [rcx+10h]; Instance
0x140022c5d  call    cs:__imp_FltGetTransactionContext
0x140022c64  nop     dword ptr [rax+rax+00h]
0x140022c69  test    eax, eax
0x140022c6b  js      short loc_140022C77
0x140022c6d  mov     rcx, [rsp+38h+arg_0]
0x140022c72  mov     [rsi], rcx
0x140022c75  jmp     short loc_140022CDD
0x140022c77  lea     rcx, [rsp+38h+NewContext]
0x140022c7c  call    WofCreateTransactionContext
0x140022c81  test    eax, eax
0x140022c83  js      short loc_140022CDD
0x140022c85  mov     rcx, [rdi+10h]
0x140022c89  lea     rax, [rsp+38h+arg_0]
0x140022c8e  mov     rdi, [rsp+38h+NewContext]
0x140022c93  mov     r8d, 1; Operation
0x140022c99  mov     r9, rdi; NewContext
0x140022c9c  mov     [rsp+38h+OldContext], rax; OldContext
0x140022ca1  mov     rdx, rbx; Transaction
0x140022ca4  mov     rcx, [rcx+10h]; Instance
0x140022ca8  call    cs:__imp_FltSetTransactionContext
0x140022caf  nop     dword ptr [rax+rax+00h]
0x140022cb4  mov     ebx, eax
0x140022cb6  test    eax, eax
0x140022cb8  jns     short loc_140022CD8
0x140022cba  mov     rcx, rdi; Context
0x140022cbd  call    cs:__imp_FltReleaseContext
0x140022cc4  nop     dword ptr [rax+rax+00h]
0x140022cc9  cmp     ebx, 0C01C0002h
0x140022ccf  jnz     short loc_140022CDB
0x140022cd1  mov     rdi, [rsp+38h+arg_0]
0x140022cd6  xor     ebx, ebx
0x140022cd8  mov     [rsi], rdi
0x140022cdb  mov     eax, ebx
0x140022cdd  mov     rbx, [rsp+38h+arg_8]
0x140022ce2  mov     rsi, [rsp+38h+arg_10]
0x140022ce7  add     rsp, 30h
0x140022ceb  pop     rdi
0x140022cec  retn
```
