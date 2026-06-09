# WcSynchronizeExpansionPreopWithReason

- ea: `0x140023890`
- end: `0x140023a9c`
- name: `WcSynchronizeExpansionPreopWithReason`
- size: `524`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, int, int, int, struct _EX_RUNDOWN_REF **)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x1400231a0`
- `0x140023c90`
- `0x140024fb0`
- `0x140034c00`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140001bc8`
- `0x140001bf8`
- `0x140001fd0`
- `0x140014008`
- `0x140017ef8`
- `0x140023890`
- `0x14002898c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400239c4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400239c4`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140023994`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140023994`
- `FLTMGR!FltReleaseContext` at `0x140023a77`
- `FLTMGR!FltReleaseContext` at `0x140023a8b`
- `FLTMGR!FltReleaseContext` at `0x140023a77`
- `FLTMGR!FltReleaseContext` at `0x140023a8b`

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
  if ( ContextFileObject && WcIsPlaceHolder((__int64)v19) && (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x100) == 0 )
  {
    if ( WcIsPlaceHolderDirectory((__int64)v14, (__int64)v13) )
    {
      v16 = 2;
      if ( !WcIsSourcedStream((__int64)v13) )
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
        v17 = WcSetPlaceHolderFlagsSynchronized(
                CallbackData,
                *(struct _FLT_INSTANCE **)(a2 + 24),
                *(struct _FILE_OBJECT **)(a2 + 32),
                2u);
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
        v17 = WcExpandAndWait(CallbackData, *(PVOID *)(a2 + 24), *(PVOID *)(a2 + 32), (__int64)v14, v16, a5);
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
0x140023890  mov     r11, rsp
0x140023893  push    rbx
0x140023894  push    rbp
0x140023895  push    rsi
0x140023896  push    rdi
0x140023897  push    r12
0x140023899  push    r13
0x14002389b  push    r14
0x14002389d  push    r15
0x14002389f  sub     rsp, 48h
0x1400238a3  mov     r14, [rsp+88h+arg_28]
0x1400238ab  xor     eax, eax
0x1400238ad  mov     rbp, rdx
0x1400238b0  mov     [r11+10h], rax
0x1400238b4  mov     r13d, r9d
0x1400238b7  mov     [r11-58h], rax
0x1400238bb  mov     r15d, r8d
0x1400238be  lea     r9, [r11-58h]
0x1400238c2  mov     [r14], rax
0x1400238c5  lea     r8, [r11+10h]
0x1400238c9  mov     rdx, [rdx+20h]; FileObject
0x1400238cd  mov     r12, rcx
0x1400238d0  mov     rcx, [rbp+18h]; Instance
0x1400238d4  mov     ebx, 1
0x1400238d9  call    WcGetContextFileObject
0x1400238de  mov     rsi, [rsp+88h+Context]
0x1400238e3  mov     rdi, [rsp+88h+arg_8]
0x1400238eb  test    al, al
0x1400238ed  jnz     short loc_140023915
0x1400238ef  test    rsi, rsi
0x1400238f2  jnz     loc_140023A74
0x1400238f8  test    rdi, rdi
0x1400238fb  jnz     loc_140023A88
0x140023901  mov     eax, ebx
0x140023903  add     rsp, 48h
0x140023907  pop     r15
0x140023909  pop     r14
0x14002390b  pop     r13
0x14002390d  pop     r12
0x14002390f  pop     rdi
0x140023910  pop     rsi
0x140023911  pop     rbp
0x140023912  pop     rbx
0x140023913  retn
0x140023915  mov     rcx, rdi
0x140023918  call    WcIsPlaceHolder
0x14002391d  test    al, al
0x14002391f  jz      short loc_1400238EF
0x140023921  mov     rax, [rbp+20h]
0x140023925  test    dword ptr [rax+50h], 100h
0x14002392c  jnz     short loc_1400238EF
0x14002392e  mov     rdx, rsi
0x140023931  mov     rcx, rdi
0x140023934  call    WcIsPlaceHolderDirectory
0x140023939  test    al, al
0x14002393b  jz      short loc_140023955
0x14002393d  mov     rcx, rsi
0x140023940  mov     r13d, 2
0x140023946  call    WcIsSourcedStream
0x14002394b  xor     ecx, ecx
0x14002394d  test    al, al
0x14002394f  cmovz   r15d, ecx
0x140023953  jmp     short loc_14002396A
0x140023955  mov     rdx, rsi
0x140023958  mov     rcx, rdi
0x14002395b  call    WcIsPlaceHolderStream
0x140023960  test    al, al
0x140023962  jnz     short loc_140023967
0x140023964  mov     r15d, r13d
0x140023967  mov     r13d, ebx
0x14002396a  test    r15d, r15d
0x14002396d  jz      short loc_1400238EF
0x14002396f  mov     ecx, r15d
0x140023972  sub     ecx, ebx
0x140023974  jz      short loc_1400239E7
0x140023976  sub     ecx, ebx
0x140023978  jz      loc_140023A2F
0x14002397e  sub     ecx, ebx
0x140023980  jz      short loc_140023990
0x140023982  cmp     ecx, ebx
0x140023984  jz      short loc_140023990
0x140023986  mov     ebp, 0C000000Dh
0x14002398b  jmp     loc_140023A5C
0x140023990  lea     rcx, [rdi+48h]; RunRef
0x140023994  call    cs:__imp_ExAcquireRundownProtection
0x14002399b  nop     dword ptr [rax+rax+00h]
0x1400239a0  test    al, al
0x1400239a2  jz      short loc_1400239E1
0x1400239a4  mov     r8, [rbp+20h]; Object
0x1400239a8  mov     r9d, 2
0x1400239ae  mov     rdx, [rbp+18h]; FltObject
0x1400239b2  mov     rcx, r12; CallbackData
0x1400239b5  call    WcSetPlaceHolderFlagsSynchronized
0x1400239ba  mov     ebp, eax
0x1400239bc  test    eax, eax
0x1400239be  jns     short loc_1400239D5
0x1400239c0  lea     rcx, [rdi+48h]; RunRef
0x1400239c4  call    cs:__imp_ExReleaseRundownProtection
0x1400239cb  nop     dword ptr [rax+rax+00h]
0x1400239d0  jmp     loc_140023A5C
0x1400239d5  xor     ebx, ebx
0x1400239d7  mov     [r14], rdi
0x1400239da  xor     edi, edi
0x1400239dc  jmp     loc_1400238EF
0x1400239e1  cmp     r15d, 3
0x1400239e5  jnz     short loc_140023A2F
0x1400239e7  mov     eax, [r12]
0x1400239eb  test    al, 2
0x1400239ed  jz      short loc_1400239F9
0x1400239ef  mov     ebx, 3
0x1400239f4  jmp     loc_1400238EF
0x1400239f9  mov     eax, [rsp+88h+arg_20]
0x140023a00  mov     r9, rdi
0x140023a03  mov     r8, [rbp+20h]
0x140023a07  mov     rcx, r12
0x140023a0a  mov     rdx, [rbp+18h]
0x140023a0e  mov     [rsp+88h+var_60], eax
0x140023a12  mov     [rsp+88h+var_68], r13d
0x140023a17  call    WcExpandAndPend
0x140023a1c  mov     ebp, eax
0x140023a1e  cmp     eax, 103h
0x140023a23  jnz     short loc_140023A54
0x140023a25  mov     ebx, 2
0x140023a2a  jmp     loc_1400238EF
0x140023a2f  mov     eax, [rsp+88h+arg_20]
0x140023a36  mov     r9, rdi
0x140023a39  mov     r8, [rbp+20h]; Object
0x140023a3d  mov     rcx, r12; CallbackData
0x140023a40  mov     rdx, [rbp+18h]; FltObject
0x140023a44  mov     [rsp+88h+var_60], eax; int
0x140023a48  mov     [rsp+88h+var_68], r13d; int
0x140023a4d  call    WcExpandAndWait
0x140023a52  mov     ebp, eax
0x140023a54  test    ebp, ebp
0x140023a56  jns     loc_1400238EF
0x140023a5c  mov     [r12+18h], ebp
0x140023a61  mov     ebx, 4
0x140023a66  mov     qword ptr [r12+20h], 0
0x140023a6f  jmp     loc_1400238EF
0x140023a74  mov     rcx, rsi; Context
0x140023a77  call    cs:__imp_FltReleaseContext
0x140023a7e  nop     dword ptr [rax+rax+00h]
0x140023a83  jmp     loc_1400238F8
0x140023a88  mov     rcx, rdi; Context
0x140023a8b  call    cs:__imp_FltReleaseContext
0x140023a92  nop     dword ptr [rax+rax+00h]
0x140023a97  jmp     loc_140023901
```
