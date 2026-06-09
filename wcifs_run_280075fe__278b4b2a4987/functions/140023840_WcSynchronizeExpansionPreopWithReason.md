# WcSynchronizeExpansionPreopWithReason

- ea: `0x140023840`
- end: `0x140023a4c`
- name: `WcSynchronizeExpansionPreopWithReason`
- size: `524`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, int, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x140023150`
- `0x140023c40`
- `0x140024f60`
- `0x140034bb0`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x140001fd0`
- `0x140014008`
- `0x140017ef8`
- `0x140023840`
- `0x14002893c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140023974`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140023974`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140023944`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140023944`
- `FLTMGR!FltReleaseContext` at `0x140023a27`
- `FLTMGR!FltReleaseContext` at `0x140023a3b`
- `FLTMGR!FltReleaseContext` at `0x140023a27`
- `FLTMGR!FltReleaseContext` at `0x140023a3b`

## pseudocode

```c
__int64 __fastcall WcSynchronizeExpansionPreopWithReason(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        struct _EX_RUNDOWN_REF **a6)
{
  struct _EX_RUNDOWN_REF **v6; // r14
  unsigned int v11; // ebx
  char ContextFileObject; // al
  PFLT_CONTEXT v13; // rsi
  struct _EX_RUNDOWN_REF *v14; // rdi
  int v16; // r13d
  NTSTATUS v17; // ebp
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-58h] BYREF
  PFLT_CONTEXT v19; // [rsp+98h] [rbp+10h] BYREF

  v6 = a6;
  v19 = 0;
  Context = 0;
  *a6 = 0;
  v11 = 1;
  ContextFileObject = WcGetContextFileObject(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v19, &Context);
  v13 = Context;
  v14 = (struct _EX_RUNDOWN_REF *)v19;
  if ( ContextFileObject
    && (unsigned __int8)WcIsPlaceHolder(v19)
    && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x100) == 0 )
  {
    if ( WcIsPlaceHolderDirectory((__int64)v14, (__int64)v13) )
    {
      v16 = 2;
      if ( !(unsigned __int8)WcIsSourcedStream(v13) )
        a3 = 0;
    }
    else
    {
      if ( !WcIsPlaceHolderStream((__int64)v14, (__int64)v13) )
        a3 = a4;
      v16 = 1;
    }
    if ( a3 )
    {
      if ( a3 == 1 )
        goto LABEL_26;
      if ( a3 == 2 )
        goto LABEL_30;
      if ( (unsigned int)(a3 - 3) >= 2 )
      {
        v17 = -1073741811;
LABEL_32:
        CallbackData->IoStatus.Status = v17;
        v11 = 4;
        CallbackData->IoStatus.Information = 0;
        goto LABEL_2;
      }
      if ( ExAcquireRundownProtection(v14 + 9) )
      {
        v17 = WcSetPlaceHolderFlagsSynchronized(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32));
        if ( v17 >= 0 )
        {
          v11 = 0;
          *v6 = v14;
          v14 = 0;
          goto LABEL_2;
        }
        ExReleaseRundownProtection(v14 + 9);
        goto LABEL_32;
      }
      if ( a3 == 3 )
      {
LABEL_26:
        if ( (CallbackData->Flags & 2) != 0 )
        {
          v11 = 3;
          goto LABEL_2;
        }
        v17 = WcExpandAndPend(CallbackData, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), v14, v16, a5);
        if ( v17 == 259 )
        {
          v11 = 2;
          goto LABEL_2;
        }
      }
      else
      {
LABEL_30:
        v17 = WcExpandAndWait(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32), v16, a5);
      }
      if ( v17 >= 0 )
        goto LABEL_2;
      goto LABEL_32;
    }
  }
LABEL_2:
  if ( v13 )
    FltReleaseContext(v13);
  if ( v14 )
    FltReleaseContext(v14);
  return v11;
}

```

## disassembly

```asm
0x140023840  mov     r11, rsp
0x140023843  push    rbx
0x140023844  push    rbp
0x140023845  push    rsi
0x140023846  push    rdi
0x140023847  push    r12
0x140023849  push    r13
0x14002384b  push    r14
0x14002384d  push    r15
0x14002384f  sub     rsp, 48h
0x140023853  mov     r14, [rsp+88h+arg_28]
0x14002385b  xor     eax, eax
0x14002385d  mov     rbp, rdx
0x140023860  mov     [r11+10h], rax
0x140023864  mov     r13d, r9d
0x140023867  mov     [r11-58h], rax
0x14002386b  mov     r15d, r8d
0x14002386e  lea     r9, [r11-58h]
0x140023872  mov     [r14], rax
0x140023875  lea     r8, [r11+10h]
0x140023879  mov     rdx, [rdx+20h]; FileObject
0x14002387d  mov     r12, rcx
0x140023880  mov     rcx, [rbp+18h]; Instance
0x140023884  mov     ebx, 1
0x140023889  call    WcGetContextFileObject
0x14002388e  mov     rsi, [rsp+88h+Context]
0x140023893  mov     rdi, [rsp+88h+arg_8]
0x14002389b  test    al, al
0x14002389d  jnz     short loc_1400238C5
0x14002389f  test    rsi, rsi
0x1400238a2  jnz     loc_140023A24
0x1400238a8  test    rdi, rdi
0x1400238ab  jnz     loc_140023A38
0x1400238b1  mov     eax, ebx
0x1400238b3  add     rsp, 48h
0x1400238b7  pop     r15
0x1400238b9  pop     r14
0x1400238bb  pop     r13
0x1400238bd  pop     r12
0x1400238bf  pop     rdi
0x1400238c0  pop     rsi
0x1400238c1  pop     rbp
0x1400238c2  pop     rbx
0x1400238c3  retn
0x1400238c5  mov     rcx, rdi
0x1400238c8  call    WcIsPlaceHolder
0x1400238cd  test    al, al
0x1400238cf  jz      short loc_14002389F
0x1400238d1  mov     rax, [rbp+20h]
0x1400238d5  test    dword ptr [rax+50h], 100h
0x1400238dc  jnz     short loc_14002389F
0x1400238de  mov     rdx, rsi
0x1400238e1  mov     rcx, rdi
0x1400238e4  call    WcIsPlaceHolderDirectory
0x1400238e9  test    al, al
0x1400238eb  jz      short loc_140023905
0x1400238ed  mov     rcx, rsi
0x1400238f0  mov     r13d, 2
0x1400238f6  call    WcIsSourcedStream
0x1400238fb  xor     ecx, ecx
0x1400238fd  test    al, al
0x1400238ff  cmovz   r15d, ecx
0x140023903  jmp     short loc_14002391A
0x140023905  mov     rdx, rsi
0x140023908  mov     rcx, rdi
0x14002390b  call    WcIsPlaceHolderStream
0x140023910  test    al, al
0x140023912  jnz     short loc_140023917
0x140023914  mov     r15d, r13d
0x140023917  mov     r13d, ebx
0x14002391a  test    r15d, r15d
0x14002391d  jz      short loc_14002389F
0x14002391f  mov     ecx, r15d
0x140023922  sub     ecx, ebx
0x140023924  jz      short loc_140023997
0x140023926  sub     ecx, ebx
0x140023928  jz      loc_1400239DF
0x14002392e  sub     ecx, ebx
0x140023930  jz      short loc_140023940
0x140023932  cmp     ecx, ebx
0x140023934  jz      short loc_140023940
0x140023936  mov     ebp, 0C000000Dh
0x14002393b  jmp     loc_140023A0C
0x140023940  lea     rcx, [rdi+48h]; RunRef
0x140023944  call    cs:__imp_ExAcquireRundownProtection
0x14002394b  nop     dword ptr [rax+rax+00h]
0x140023950  test    al, al
0x140023952  jz      short loc_140023991
0x140023954  mov     r8, [rbp+20h]; Object
0x140023958  mov     r9d, 2
0x14002395e  mov     rdx, [rbp+18h]; FltObject
0x140023962  mov     rcx, r12; CallbackData
0x140023965  call    WcSetPlaceHolderFlagsSynchronized
0x14002396a  mov     ebp, eax
0x14002396c  test    eax, eax
0x14002396e  jns     short loc_140023985
0x140023970  lea     rcx, [rdi+48h]; RunRef
0x140023974  call    cs:__imp_ExReleaseRundownProtection
0x14002397b  nop     dword ptr [rax+rax+00h]
0x140023980  jmp     loc_140023A0C
0x140023985  xor     ebx, ebx
0x140023987  mov     [r14], rdi
0x14002398a  xor     edi, edi
0x14002398c  jmp     loc_14002389F
0x140023991  cmp     r15d, 3
0x140023995  jnz     short loc_1400239DF
0x140023997  mov     eax, [r12]
0x14002399b  test    al, 2
0x14002399d  jz      short loc_1400239A9
0x14002399f  mov     ebx, 3
0x1400239a4  jmp     loc_14002389F
0x1400239a9  mov     eax, [rsp+88h+arg_20]
0x1400239b0  mov     r9, rdi
0x1400239b3  mov     r8, [rbp+20h]
0x1400239b7  mov     rcx, r12
0x1400239ba  mov     rdx, [rbp+18h]
0x1400239be  mov     [rsp+88h+var_60], eax
0x1400239c2  mov     [rsp+88h+var_68], r13d
0x1400239c7  call    WcExpandAndPend
0x1400239cc  mov     ebp, eax
0x1400239ce  cmp     eax, 103h
0x1400239d3  jnz     short loc_140023A04
0x1400239d5  mov     ebx, 2
0x1400239da  jmp     loc_14002389F
0x1400239df  mov     eax, [rsp+88h+arg_20]
0x1400239e6  mov     r9, rdi
0x1400239e9  mov     r8, [rbp+20h]; Object
0x1400239ed  mov     rcx, r12; CallbackData
0x1400239f0  mov     rdx, [rbp+18h]; FltObject
0x1400239f4  mov     [rsp+88h+var_60], eax; int
0x1400239f8  mov     [rsp+88h+var_68], r13d; int
0x1400239fd  call    WcExpandAndWait
0x140023a02  mov     ebp, eax
0x140023a04  test    ebp, ebp
0x140023a06  jns     loc_14002389F
0x140023a0c  mov     [r12+18h], ebp
0x140023a11  mov     ebx, 4
0x140023a16  mov     qword ptr [r12+20h], 0
0x140023a1f  jmp     loc_14002389F
0x140023a24  mov     rcx, rsi; Context
0x140023a27  call    cs:__imp_FltReleaseContext
0x140023a2e  nop     dword ptr [rax+rax+00h]
0x140023a33  jmp     loc_1400238A8
0x140023a38  mov     rcx, rdi; Context
0x140023a3b  call    cs:__imp_FltReleaseContext
0x140023a42  nop     dword ptr [rax+rax+00h]
0x140023a47  jmp     loc_1400238B1
```
