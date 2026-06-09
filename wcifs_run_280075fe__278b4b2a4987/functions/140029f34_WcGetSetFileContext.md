# WcGetSetFileContext

- ea: `0x140029f34`
- end: `0x14002a0c4`
- name: `WcGetSetFileContext`
- size: `400`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001c688`
- `0x140027854`
- `0x140029608`

## callees

- `0x140029f34`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002a00b`
- `ntoskrnl!KeInitializeEvent` at `0x14002a00b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002a01f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002a01f`
- `FLTMGR!FltAllocateContext` at `0x140029f87`
- `FLTMGR!FltAllocateContext` at `0x140029f87`
- `FLTMGR!FltReferenceContext` at `0x140029fb4`
- `FLTMGR!FltReferenceContext` at `0x140029fb4`
- `FLTMGR!FltSetFileContext` at `0x14002a041`
- `FLTMGR!FltSetFileContext` at `0x14002a041`
- `FLTMGR!FltReleaseContext` at `0x14002a05e`
- `FLTMGR!FltReleaseContext` at `0x14002a086`
- `FLTMGR!FltReleaseContext` at `0x14002a0a8`
- `FLTMGR!FltReleaseContext` at `0x14002a05e`
- `FLTMGR!FltReleaseContext` at `0x14002a086`
- `FLTMGR!FltReleaseContext` at `0x14002a0a8`
- `FLTMGR!FltGetInstanceContext` at `0x140029fa4`
- `FLTMGR!FltGetInstanceContext` at `0x140029fa4`

## pseudocode

```c
__int64 __fastcall WcGetSetFileContext(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, int a3, __int64 a4, _QWORD *a5)
{
  NTSTATUS v9; // ebx
  char *v10; // rcx
  NTSTATUS v11; // eax
  PFLT_CONTEXT v12; // rcx
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-28h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-20h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+40h] [rbp-18h] BYREF

  NewContext = 0;
  OldContext = 0;
  Context = 0;
  v9 = FltAllocateContext(Globals, 4u, 0x60u, (POOL_TYPE)512, &NewContext);
  if ( v9 >= 0 )
  {
    FltGetInstanceContext(Instance, &Context);
    FltReferenceContext(Context);
    *(_QWORD *)NewContext = Context;
    *((_DWORD *)NewContext + 22) = a3;
    *((_QWORD *)NewContext + 10) = 0;
    *((_QWORD *)NewContext + 8) = a4;
    v10 = (char *)NewContext;
    *((_DWORD *)NewContext + 2) = 1;
    *((_QWORD *)v10 + 2) = 0;
    *((_DWORD *)v10 + 6) = 0;
    KeInitializeEvent((PRKEVENT)(v10 + 32), SynchronizationEvent, 0);
    ExInitializeRundownProtection((PEX_RUNDOWN_REF)NewContext + 9);
    v11 = FltSetFileContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &OldContext);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v12 = NewContext;
    }
    else
    {
      if ( v11 != -1071906814 )
      {
        *((_QWORD *)NewContext + 8) = 0;
        FltReleaseContext(NewContext);
        goto LABEL_8;
      }
      FltReleaseContext(NewContext);
      v12 = OldContext;
      v9 = 0;
      NewContext = OldContext;
    }
    *a5 = v12;
  }
LABEL_8:
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140029f34  push    rbp
0x140029f36  push    rbx
0x140029f37  push    rsi
0x140029f38  push    rdi
0x140029f39  push    r14
0x140029f3b  push    r15
0x140029f3d  mov     rbp, rsp
0x140029f40  sub     rsp, 58h
0x140029f44  mov     r15, rdx
0x140029f47  mov     [rbp+NewContext], 0
0x140029f4f  mov     edx, 4; ContextType
0x140029f54  mov     [rbp+OldContext], 0
0x140029f5c  mov     rsi, r9
0x140029f5f  mov     [rbp+Context], 0
0x140029f67  mov     r14d, r8d
0x140029f6a  lea     rax, [rbp+NewContext]
0x140029f6e  mov     rdi, rcx
0x140029f71  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x140029f76  mov     rcx, cs:Globals; Filter
0x140029f7d  lea     r8d, [rdx+5Ch]; ContextSize
0x140029f81  mov     r9d, 200h; PoolType
0x140029f87  call    cs:__imp_FltAllocateContext
0x140029f8e  nop     dword ptr [rax+rax+00h]
0x140029f93  mov     ebx, eax
0x140029f95  test    eax, eax
0x140029f97  js      loc_14002A09F
0x140029f9d  lea     rdx, [rbp+Context]; Context
0x140029fa1  mov     rcx, rdi; Instance
0x140029fa4  call    cs:__imp_FltGetInstanceContext
0x140029fab  nop     dword ptr [rax+rax+00h]
0x140029fb0  mov     rcx, [rbp+Context]; Context
0x140029fb4  call    cs:__imp_FltReferenceContext
0x140029fbb  nop     dword ptr [rax+rax+00h]
0x140029fc0  mov     rcx, [rbp+NewContext]
0x140029fc4  mov     ebx, 1
0x140029fc9  mov     rax, [rbp+Context]
0x140029fcd  xor     r8d, r8d; State
0x140029fd0  mov     edx, ebx; Type
0x140029fd2  mov     [rcx], rax
0x140029fd5  mov     rax, [rbp+NewContext]
0x140029fd9  mov     [rax+58h], r14d
0x140029fdd  mov     rax, [rbp+NewContext]
0x140029fe1  mov     qword ptr [rax+50h], 0
0x140029fe9  mov     rax, [rbp+NewContext]
0x140029fed  mov     [rax+40h], rsi
0x140029ff1  mov     rcx, [rbp+NewContext]
0x140029ff5  mov     [rcx+8], ebx
0x140029ff8  mov     qword ptr [rcx+10h], 0
0x14002a000  mov     dword ptr [rcx+18h], 0
0x14002a007  add     rcx, 20h ; ' '; Event
0x14002a00b  call    cs:__imp_KeInitializeEvent
0x14002a012  nop     dword ptr [rax+rax+00h]
0x14002a017  mov     rcx, [rbp+NewContext]
0x14002a01b  add     rcx, 48h ; 'H'; RunRef
0x14002a01f  call    cs:__imp_ExInitializeRundownProtection
0x14002a026  nop     dword ptr [rax+rax+00h]
0x14002a02b  mov     r9, [rbp+NewContext]; NewContext
0x14002a02f  lea     rax, [rbp+OldContext]
0x14002a033  mov     r8d, ebx; Operation
0x14002a036  mov     [rsp+58h+ReturnedContext], rax; OldContext
0x14002a03b  mov     rdx, r15; FileObject
0x14002a03e  mov     rcx, rdi; Instance
0x14002a041  call    cs:__imp_FltSetFileContext
0x14002a048  nop     dword ptr [rax+rax+00h]
0x14002a04d  mov     ebx, eax
0x14002a04f  test    eax, eax
0x14002a051  jns     short loc_14002A094
0x14002a053  cmp     eax, 0C01C0002h
0x14002a058  jnz     short loc_14002A076
0x14002a05a  mov     rcx, [rbp+NewContext]; Context
0x14002a05e  call    cs:__imp_FltReleaseContext
0x14002a065  nop     dword ptr [rax+rax+00h]
0x14002a06a  mov     rcx, [rbp+OldContext]
0x14002a06e  xor     ebx, ebx
0x14002a070  mov     [rbp+NewContext], rcx
0x14002a074  jmp     short loc_14002A098
0x14002a076  mov     rax, [rbp+NewContext]
0x14002a07a  mov     qword ptr [rax+40h], 0
0x14002a082  mov     rcx, [rbp+NewContext]; Context
0x14002a086  call    cs:__imp_FltReleaseContext
0x14002a08d  nop     dword ptr [rax+rax+00h]
0x14002a092  jmp     short loc_14002A09F
0x14002a094  mov     rcx, [rbp+NewContext]
0x14002a098  mov     rax, [rbp+arg_20]
0x14002a09c  mov     [rax], rcx
0x14002a09f  mov     rcx, [rbp+Context]; Context
0x14002a0a3  test    rcx, rcx
0x14002a0a6  jz      short loc_14002A0B4
0x14002a0a8  call    cs:__imp_FltReleaseContext
0x14002a0af  nop     dword ptr [rax+rax+00h]
0x14002a0b4  mov     eax, ebx
0x14002a0b6  add     rsp, 58h
0x14002a0ba  pop     r15
0x14002a0bc  pop     r14
0x14002a0be  pop     rdi
0x14002a0bf  pop     rsi
0x14002a0c0  pop     rbx
0x14002a0c1  pop     rbp
0x14002a0c2  retn
```
