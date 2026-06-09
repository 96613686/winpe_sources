# WcGetSetFileContext

- ea: `0x140029f84`
- end: `0x14002a114`
- name: `WcGetSetFileContext`
- size: `400`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, int, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001c688`
- `0x1400278a4`
- `0x140029658`

## callees

- `0x140029f84`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002a05b`
- `ntoskrnl!KeInitializeEvent` at `0x14002a05b`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002a06f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002a06f`
- `FLTMGR!FltAllocateContext` at `0x140029fd7`
- `FLTMGR!FltAllocateContext` at `0x140029fd7`
- `FLTMGR!FltReferenceContext` at `0x14002a004`
- `FLTMGR!FltReferenceContext` at `0x14002a004`
- `FLTMGR!FltSetFileContext` at `0x14002a091`
- `FLTMGR!FltSetFileContext` at `0x14002a091`
- `FLTMGR!FltReleaseContext` at `0x14002a0ae`
- `FLTMGR!FltReleaseContext` at `0x14002a0d6`
- `FLTMGR!FltReleaseContext` at `0x14002a0f8`
- `FLTMGR!FltReleaseContext` at `0x14002a0ae`
- `FLTMGR!FltReleaseContext` at `0x14002a0d6`
- `FLTMGR!FltReleaseContext` at `0x14002a0f8`
- `FLTMGR!FltGetInstanceContext` at `0x140029ff4`
- `FLTMGR!FltGetInstanceContext` at `0x140029ff4`

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
0x140029f84  push    rbp
0x140029f86  push    rbx
0x140029f87  push    rsi
0x140029f88  push    rdi
0x140029f89  push    r14
0x140029f8b  push    r15
0x140029f8d  mov     rbp, rsp
0x140029f90  sub     rsp, 58h
0x140029f94  mov     r15, rdx
0x140029f97  mov     [rbp+NewContext], 0
0x140029f9f  mov     edx, 4; ContextType
0x140029fa4  mov     [rbp+OldContext], 0
0x140029fac  mov     rsi, r9
0x140029faf  mov     [rbp+Context], 0
0x140029fb7  mov     r14d, r8d
0x140029fba  lea     rax, [rbp+NewContext]
0x140029fbe  mov     rdi, rcx
0x140029fc1  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x140029fc6  mov     rcx, cs:Globals; Filter
0x140029fcd  lea     r8d, [rdx+5Ch]; ContextSize
0x140029fd1  mov     r9d, 200h; PoolType
0x140029fd7  call    cs:__imp_FltAllocateContext
0x140029fde  nop     dword ptr [rax+rax+00h]
0x140029fe3  mov     ebx, eax
0x140029fe5  test    eax, eax
0x140029fe7  js      loc_14002A0EF
0x140029fed  lea     rdx, [rbp+Context]; Context
0x140029ff1  mov     rcx, rdi; Instance
0x140029ff4  call    cs:__imp_FltGetInstanceContext
0x140029ffb  nop     dword ptr [rax+rax+00h]
0x14002a000  mov     rcx, [rbp+Context]; Context
0x14002a004  call    cs:__imp_FltReferenceContext
0x14002a00b  nop     dword ptr [rax+rax+00h]
0x14002a010  mov     rcx, [rbp+NewContext]
0x14002a014  mov     ebx, 1
0x14002a019  mov     rax, [rbp+Context]
0x14002a01d  xor     r8d, r8d; State
0x14002a020  mov     edx, ebx; Type
0x14002a022  mov     [rcx], rax
0x14002a025  mov     rax, [rbp+NewContext]
0x14002a029  mov     [rax+58h], r14d
0x14002a02d  mov     rax, [rbp+NewContext]
0x14002a031  mov     qword ptr [rax+50h], 0
0x14002a039  mov     rax, [rbp+NewContext]
0x14002a03d  mov     [rax+40h], rsi
0x14002a041  mov     rcx, [rbp+NewContext]
0x14002a045  mov     [rcx+8], ebx
0x14002a048  mov     qword ptr [rcx+10h], 0
0x14002a050  mov     dword ptr [rcx+18h], 0
0x14002a057  add     rcx, 20h ; ' '; Event
0x14002a05b  call    cs:__imp_KeInitializeEvent
0x14002a062  nop     dword ptr [rax+rax+00h]
0x14002a067  mov     rcx, [rbp+NewContext]
0x14002a06b  add     rcx, 48h ; 'H'; RunRef
0x14002a06f  call    cs:__imp_ExInitializeRundownProtection
0x14002a076  nop     dword ptr [rax+rax+00h]
0x14002a07b  mov     r9, [rbp+NewContext]; NewContext
0x14002a07f  lea     rax, [rbp+OldContext]
0x14002a083  mov     r8d, ebx; Operation
0x14002a086  mov     [rsp+58h+ReturnedContext], rax; OldContext
0x14002a08b  mov     rdx, r15; FileObject
0x14002a08e  mov     rcx, rdi; Instance
0x14002a091  call    cs:__imp_FltSetFileContext
0x14002a098  nop     dword ptr [rax+rax+00h]
0x14002a09d  mov     ebx, eax
0x14002a09f  test    eax, eax
0x14002a0a1  jns     short loc_14002A0E4
0x14002a0a3  cmp     eax, 0C01C0002h
0x14002a0a8  jnz     short loc_14002A0C6
0x14002a0aa  mov     rcx, [rbp+NewContext]; Context
0x14002a0ae  call    cs:__imp_FltReleaseContext
0x14002a0b5  nop     dword ptr [rax+rax+00h]
0x14002a0ba  mov     rcx, [rbp+OldContext]
0x14002a0be  xor     ebx, ebx
0x14002a0c0  mov     [rbp+NewContext], rcx
0x14002a0c4  jmp     short loc_14002A0E8
0x14002a0c6  mov     rax, [rbp+NewContext]
0x14002a0ca  mov     qword ptr [rax+40h], 0
0x14002a0d2  mov     rcx, [rbp+NewContext]; Context
0x14002a0d6  call    cs:__imp_FltReleaseContext
0x14002a0dd  nop     dword ptr [rax+rax+00h]
0x14002a0e2  jmp     short loc_14002A0EF
0x14002a0e4  mov     rcx, [rbp+NewContext]
0x14002a0e8  mov     rax, [rbp+arg_20]
0x14002a0ec  mov     [rax], rcx
0x14002a0ef  mov     rcx, [rbp+Context]; Context
0x14002a0f3  test    rcx, rcx
0x14002a0f6  jz      short loc_14002A104
0x14002a0f8  call    cs:__imp_FltReleaseContext
0x14002a0ff  nop     dword ptr [rax+rax+00h]
0x14002a104  mov     eax, ebx
0x14002a106  add     rsp, 58h
0x14002a10a  pop     r15
0x14002a10c  pop     r14
0x14002a10e  pop     rdi
0x14002a10f  pop     rsi
0x14002a110  pop     rbx
0x14002a111  pop     rbp
0x14002a112  retn
```
