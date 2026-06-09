# WcSetPlaceHolderFlagsSynchronized

- ea: `0x14002893c`
- end: `0x140028a73`
- name: `WcSetPlaceHolderFlagsSynchronized`
- size: `311`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PVOID FltObject, PVOID Object)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x140003930`
- `0x140023840`
- `0x140025220`
- `0x140026de0`
- `0x140027854`
- `0x140027f24`

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140001bf8`
- `0x140014008`
- `0x140020988`
- `0x14002893c`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140028a10`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140028a10`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400289e9`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400289e9`
- `FLTMGR!FltReleaseContext` at `0x140028a4c`
- `FLTMGR!FltReleaseContext` at `0x140028a62`
- `FLTMGR!FltReleaseContext` at `0x140028a4c`
- `FLTMGR!FltReleaseContext` at `0x140028a62`

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
      v12 = WcExpandAndWait(CallbackData, FltObject, Object, 1, 9);
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
0x14002893c  mov     rax, rsp
0x14002893f  push    rbx
0x140028940  push    rbp
0x140028941  push    rdi
0x140028942  push    r12
0x140028944  push    r13
0x140028946  push    r14
0x140028948  push    r15
0x14002894a  sub     rsp, 40h
0x14002894e  mov     r14, r8
0x140028951  mov     r15, rdx
0x140028954  mov     ebp, r9d
0x140028957  lea     r8, [rax-40h]
0x14002895b  mov     r13, rcx
0x14002895e  lea     r9, [rax-48h]
0x140028962  xor     edi, edi
0x140028964  mov     rdx, r14; FileObject
0x140028967  mov     rcx, r15; Instance
0x14002896a  mov     [rax-40h], rdi
0x14002896e  mov     [rax-48h], rdi
0x140028972  call    WcGetContextFileObject
0x140028977  mov     rbx, [rsp+78h+Context]
0x14002897c  test    al, al
0x14002897e  jnz     short loc_1400289A8
0x140028980  test    rbx, rbx
0x140028983  jnz     loc_140028A49
0x140028989  cmp     [rsp+78h+var_48], 0
0x14002898f  jnz     loc_140028A5D
0x140028995  mov     eax, edi
0x140028997  add     rsp, 40h
0x14002899b  pop     r15
0x14002899d  pop     r14
0x14002899f  pop     r13
0x1400289a1  pop     r12
0x1400289a3  pop     rdi
0x1400289a4  pop     rbp
0x1400289a5  pop     rbx
0x1400289a6  retn
0x1400289a8  mov     rcx, rbx
0x1400289ab  call    WcIsPlaceHolder
0x1400289b0  test    al, al
0x1400289b2  jz      short loc_140028980
0x1400289b4  mov     rdx, [rsp+78h+var_48]
0x1400289b9  mov     rcx, rbx
0x1400289bc  call    WcIsPlaceHolderDirectory
0x1400289c1  test    al, al
0x1400289c3  jz      short loc_1400289D8
0x1400289c5  mov     r9d, ebp
0x1400289c8  mov     r8, rbx
0x1400289cb  mov     rdx, r14
0x1400289ce  mov     rcx, r15
0x1400289d1  call    WcSetPlaceHolderFlags
0x1400289d6  jmp     short loc_140028A42
0x1400289d8  mov     rax, [rbx+40h]
0x1400289dc  mov     ecx, [rax+0Ch]
0x1400289df  and     ecx, ebp
0x1400289e1  cmp     ecx, ebp
0x1400289e3  jz      short loc_140028980
0x1400289e5  lea     rcx, [rbx+48h]; RunRef
0x1400289e9  call    cs:__imp_ExAcquireRundownProtection
0x1400289f0  nop     dword ptr [rax+rax+00h]
0x1400289f5  test    al, al
0x1400289f7  jz      short loc_140028A21
0x1400289f9  mov     r9d, ebp
0x1400289fc  mov     r8, rbx
0x1400289ff  mov     rdx, r14
0x140028a02  mov     rcx, r15
0x140028a05  call    WcSetPlaceHolderFlags
0x140028a0a  lea     rcx, [rbx+48h]; RunRef
0x140028a0e  mov     edi, eax
0x140028a10  call    cs:__imp_ExReleaseRundownProtection
0x140028a17  nop     dword ptr [rax+rax+00h]
0x140028a1c  jmp     loc_140028980
0x140028a21  mov     [rsp+78h+var_50], 9; int
0x140028a29  mov     r9, rbx
0x140028a2c  mov     r8, r14; Object
0x140028a2f  mov     [rsp+78h+var_58], 1; int
0x140028a37  mov     rdx, r15; FltObject
0x140028a3a  mov     rcx, r13; CallbackData
0x140028a3d  call    WcExpandAndWait
0x140028a42  mov     edi, eax
0x140028a44  jmp     loc_140028980
0x140028a49  mov     rcx, rbx; Context
0x140028a4c  call    cs:__imp_FltReleaseContext
0x140028a53  nop     dword ptr [rax+rax+00h]
0x140028a58  jmp     loc_140028989
0x140028a5d  mov     rcx, [rsp+78h+var_48]; Context
0x140028a62  call    cs:__imp_FltReleaseContext
0x140028a69  nop     dword ptr [rax+rax+00h]
0x140028a6e  jmp     loc_140028995
```
