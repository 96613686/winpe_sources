# WcSetPlaceHolderFlagsSynchronized

- ea: `0x14002898c`
- end: `0x140028ac3`
- name: `WcSetPlaceHolderFlagsSynchronized`
- size: `311`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, struct _FLT_INSTANCE *FltObject, struct _FILE_OBJECT *Object, unsigned int)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140003930`
- `0x140023890`
- `0x140025270`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001bf8`
- `0x140014008`
- `0x140020988`
- `0x14002898c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140028a60`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140028a60`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028a39`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140028a39`
- `FLTMGR!FltReleaseContext` at `0x140028a9c`
- `FLTMGR!FltReleaseContext` at `0x140028ab2`
- `FLTMGR!FltReleaseContext` at `0x140028a9c`
- `FLTMGR!FltReleaseContext` at `0x140028ab2`

## pseudocode

```c
__int64 __fastcall WcSetPlaceHolderFlagsSynchronized(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Object,
        unsigned int a4)
{
  unsigned int v8; // edi
  char ContextFileObject; // al
  struct _EX_RUNDOWN_REF *v10; // rbx
  unsigned int v12; // eax
  PFLT_CONTEXT v13; // [rsp+30h] [rbp-48h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-40h] BYREF

  v8 = 0;
  Context = 0;
  v13 = 0;
  ContextFileObject = WcGetContextFileObject(FltObject, Object, &Context, &v13);
  v10 = (struct _EX_RUNDOWN_REF *)Context;
  if ( ContextFileObject && WcIsPlaceHolder((__int64)Context) )
  {
    if ( WcIsPlaceHolderDirectory((__int64)v10, (__int64)v13) )
    {
      v12 = WcSetPlaceHolderFlags(FltObject, Object, v10, a4);
    }
    else
    {
      if ( (a4 & *(_DWORD *)(v10[8].Count + 12)) == a4 )
        goto LABEL_2;
      if ( ExAcquireRundownProtection(v10 + 9) )
      {
        v8 = WcSetPlaceHolderFlags(FltObject, Object, v10, a4);
        ExReleaseRundownProtection(v10 + 9);
        goto LABEL_2;
      }
      v12 = WcExpandAndWait(CallbackData, FltObject, Object, (__int64)v10, 1, 9);
    }
    v8 = v12;
  }
LABEL_2:
  if ( v10 )
    FltReleaseContext(v10);
  if ( v13 )
    FltReleaseContext(v13);
  return v8;
}

```

## disassembly

```asm
0x14002898c  mov     rax, rsp
0x14002898f  push    rbx
0x140028990  push    rbp
0x140028991  push    rdi
0x140028992  push    r12
0x140028994  push    r13
0x140028996  push    r14
0x140028998  push    r15
0x14002899a  sub     rsp, 40h
0x14002899e  mov     r14, r8
0x1400289a1  mov     r15, rdx
0x1400289a4  mov     ebp, r9d
0x1400289a7  lea     r8, [rax-40h]
0x1400289ab  mov     r13, rcx
0x1400289ae  lea     r9, [rax-48h]
0x1400289b2  xor     edi, edi
0x1400289b4  mov     rdx, r14; FileObject
0x1400289b7  mov     rcx, r15; Instance
0x1400289ba  mov     [rax-40h], rdi
0x1400289be  mov     [rax-48h], rdi
0x1400289c2  call    WcGetContextFileObject
0x1400289c7  mov     rbx, [rsp+78h+Context]
0x1400289cc  test    al, al
0x1400289ce  jnz     short loc_1400289F8
0x1400289d0  test    rbx, rbx
0x1400289d3  jnz     loc_140028A99
0x1400289d9  cmp     [rsp+78h+var_48], 0
0x1400289df  jnz     loc_140028AAD
0x1400289e5  mov     eax, edi
0x1400289e7  add     rsp, 40h
0x1400289eb  pop     r15
0x1400289ed  pop     r14
0x1400289ef  pop     r13
0x1400289f1  pop     r12
0x1400289f3  pop     rdi
0x1400289f4  pop     rbp
0x1400289f5  pop     rbx
0x1400289f6  retn
0x1400289f8  mov     rcx, rbx
0x1400289fb  call    WcIsPlaceHolder
0x140028a00  test    al, al
0x140028a02  jz      short loc_1400289D0
0x140028a04  mov     rdx, [rsp+78h+var_48]
0x140028a09  mov     rcx, rbx
0x140028a0c  call    WcIsPlaceHolderDirectory
0x140028a11  test    al, al
0x140028a13  jz      short loc_140028A28
0x140028a15  mov     r9d, ebp
0x140028a18  mov     r8, rbx
0x140028a1b  mov     rdx, r14
0x140028a1e  mov     rcx, r15
0x140028a21  call    WcSetPlaceHolderFlags
0x140028a26  jmp     short loc_140028A92
0x140028a28  mov     rax, [rbx+40h]
0x140028a2c  mov     ecx, [rax+0Ch]
0x140028a2f  and     ecx, ebp
0x140028a31  cmp     ecx, ebp
0x140028a33  jz      short loc_1400289D0
0x140028a35  lea     rcx, [rbx+48h]; RunRef
0x140028a39  call    cs:__imp_ExAcquireRundownProtection
0x140028a40  nop     dword ptr [rax+rax+00h]
0x140028a45  test    al, al
0x140028a47  jz      short loc_140028A71
0x140028a49  mov     r9d, ebp
0x140028a4c  mov     r8, rbx
0x140028a4f  mov     rdx, r14
0x140028a52  mov     rcx, r15
0x140028a55  call    WcSetPlaceHolderFlags
0x140028a5a  lea     rcx, [rbx+48h]; RunRef
0x140028a5e  mov     edi, eax
0x140028a60  call    cs:__imp_ExReleaseRundownProtection
0x140028a67  nop     dword ptr [rax+rax+00h]
0x140028a6c  jmp     loc_1400289D0
0x140028a71  mov     [rsp+78h+var_50], 9; int
0x140028a79  mov     r9, rbx
0x140028a7c  mov     r8, r14; Object
0x140028a7f  mov     [rsp+78h+var_58], 1; int
0x140028a87  mov     rdx, r15; FltObject
0x140028a8a  mov     rcx, r13; CallbackData
0x140028a8d  call    WcExpandAndWait
0x140028a92  mov     edi, eax
0x140028a94  jmp     loc_1400289D0
0x140028a99  mov     rcx, rbx; Context
0x140028a9c  call    cs:__imp_FltReleaseContext
0x140028aa3  nop     dword ptr [rax+rax+00h]
0x140028aa8  jmp     loc_1400289D9
0x140028aad  mov     rcx, [rsp+78h+var_48]; Context
0x140028ab2  call    cs:__imp_FltReleaseContext
0x140028ab9  nop     dword ptr [rax+rax+00h]
0x140028abe  jmp     loc_1400289E5
```
