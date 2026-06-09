# WofFindOrCreateStreamContext

- ea: `0x14003603c`
- end: `0x1400361aa`
- name: `WofFindOrCreateStreamContext`
- size: `366`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140024448`
- `0x140033930`

## callees

- `0x140011640`
- `0x1400119c0`
- `0x14003603c`

## import_xrefs

- `FLTMGR!FltSetStreamContext` at `0x14003610d`
- `FLTMGR!FltSetStreamContext` at `0x14003610d`
- `FLTMGR!FltReferenceContext` at `0x1400360bb`
- `FLTMGR!FltReferenceContext` at `0x1400360bb`
- `FLTMGR!FltReleaseContext` at `0x14003617c`
- `FLTMGR!FltReleaseContext` at `0x14003618e`
- `FLTMGR!FltReleaseContext` at `0x14003617c`
- `FLTMGR!FltReleaseContext` at `0x14003618e`
- `FLTMGR!FltAllocateContext` at `0x14003608e`
- `FLTMGR!FltAllocateContext` at `0x14003608e`

## pseudocode

```c
NTSTATUS __fastcall WofFindOrCreateStreamContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT Context,
        unsigned int a4,
        _QWORD *a5)
{
  __int64 v6; // rdi
  NTSTATUS result; // eax
  NTSTATUS v10; // ebx
  PFLT_CONTEXT v11; // rcx
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-18h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+38h] [rbp-10h] BYREF

  v6 = a4;
  NewContext = 0;
  OldContext = 0;
  result = FltAllocateContext(WofGlobal, 8u, (unsigned int)dword_140018440 + 64LL, (POOL_TYPE)512, &NewContext);
  if ( result >= 0 )
  {
    memset(NewContext, 0, (unsigned int)dword_140018440 + 64LL);
    FltReferenceContext(Context);
    *(_QWORD *)NewContext = Context;
    *((_DWORD *)NewContext + 2) |= 0x4000004u;
    *((_DWORD *)NewContext + 3) = -1;
    if ( (unsigned int)v6 < 4
      && *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v6)
      && (v10 = (*((__int64 (__fastcall **)(char *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v6 + 19))((char *)NewContext + 64),
          v10 < 0) )
    {
      FltReleaseContext(NewContext);
    }
    else
    {
      *((_DWORD *)NewContext + 3) = v6;
      v10 = FltSetStreamContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &OldContext);
      if ( v10 < 0 )
      {
        FltReleaseContext(NewContext);
        if ( v10 != -1071906814 )
          return v10;
        v11 = OldContext;
        v10 = 0;
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)Context + 1) + 176LL));
        v11 = NewContext;
      }
      *a5 = v11;
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x14003603c  push    rbp
0x14003603e  push    rbx
0x14003603f  push    rsi
0x140036040  push    rdi
0x140036041  push    r14
0x140036043  push    r15
0x140036045  mov     rbp, rsp
0x140036048  sub     rsp, 48h
0x14003604c  mov     rsi, r8
0x14003604f  mov     edi, r9d
0x140036052  mov     r8d, cs:dword_140018440
0x140036059  lea     rax, [rbp+NewContext]
0x14003605d  mov     r14, rdx
0x140036060  mov     [rbp+NewContext], 0
0x140036068  mov     r15, rcx
0x14003606b  mov     [rbp+OldContext], 0
0x140036073  mov     rcx, cs:WofGlobal; Filter
0x14003607a  add     r8, 40h ; '@'; ContextSize
0x14003607e  mov     edx, 8; ContextType
0x140036083  mov     [rsp+48h+ReturnedContext], rax; ReturnedContext
0x140036088  mov     r9d, 200h; PoolType
0x14003608e  call    cs:__imp_FltAllocateContext
0x140036095  nop     dword ptr [rax+rax+00h]
0x14003609a  test    eax, eax
0x14003609c  js      loc_140036137
0x1400360a2  mov     r8d, cs:dword_140018440
0x1400360a9  xor     edx, edx; Val
0x1400360ab  mov     rcx, [rbp+NewContext]; void *
0x1400360af  add     r8, 40h ; '@'; Size
0x1400360b3  call    memset
0x1400360b8  mov     rcx, rsi; Context
0x1400360bb  call    cs:__imp_FltReferenceContext
0x1400360c2  nop     dword ptr [rax+rax+00h]
0x1400360c7  mov     rax, [rbp+NewContext]
0x1400360cb  mov     [rax], rsi
0x1400360ce  mov     rcx, [rbp+NewContext]
0x1400360d2  mov     eax, [rcx+8]
0x1400360d5  or      eax, 4000004h
0x1400360da  mov     [rcx+8], eax
0x1400360dd  mov     rax, [rbp+NewContext]
0x1400360e1  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x1400360e8  cmp     edi, 4
0x1400360eb  jb      short loc_140036145
0x1400360ed  mov     rax, [rbp+NewContext]
0x1400360f1  mov     r8d, 1; Operation
0x1400360f7  mov     rdx, r14; FileObject
0x1400360fa  mov     rcx, r15; Instance
0x1400360fd  mov     [rax+0Ch], edi
0x140036100  lea     rax, [rbp+OldContext]
0x140036104  mov     r9, [rbp+NewContext]; NewContext
0x140036108  mov     [rsp+48h+ReturnedContext], rax; OldContext
0x14003610d  call    cs:__imp_FltSetStreamContext
0x140036114  nop     dword ptr [rax+rax+00h]
0x140036119  mov     ebx, eax
0x14003611b  test    eax, eax
0x14003611d  js      short loc_14003618A
0x14003611f  mov     rax, [rsi+8]
0x140036123  lock inc dword ptr [rax+0B0h]
0x14003612a  mov     rcx, [rbp+NewContext]
0x14003612e  mov     rax, [rbp+arg_20]
0x140036132  mov     [rax], rcx
0x140036135  mov     eax, ebx
0x140036137  add     rsp, 48h
0x14003613b  pop     r15
0x14003613d  pop     r14
0x14003613f  pop     rdi
0x140036140  pop     rsi
0x140036141  pop     rbx
0x140036142  pop     rbp
0x140036143  retn
0x140036145  imul    rax, rdi, 1A8h
0x14003614c  lea     rdx, WPP_MAIN_CB.Queue+10h
0x140036153  cmp     byte ptr [rax+rdx], 0
0x140036157  jz      short loc_1400360ED
0x140036159  mov     rcx, [rbp+NewContext]
0x14003615d  mov     rax, [rax+rdx+98h]
0x140036165  add     rcx, 40h ; '@'
0x140036169  call    _guard_dispatch_icall
0x14003616e  mov     ebx, eax
0x140036170  test    eax, eax
0x140036172  jns     loc_1400360ED
0x140036178  mov     rcx, [rbp+NewContext]; Context
0x14003617c  call    cs:__imp_FltReleaseContext
0x140036183  nop     dword ptr [rax+rax+00h]
0x140036188  jmp     short loc_140036135
0x14003618a  mov     rcx, [rbp+NewContext]; Context
0x14003618e  call    cs:__imp_FltReleaseContext
0x140036195  nop     dword ptr [rax+rax+00h]
0x14003619a  cmp     ebx, 0C01C0002h
0x1400361a0  jnz     short loc_140036135
0x1400361a2  mov     rcx, [rbp+OldContext]
0x1400361a6  xor     ebx, ebx
0x1400361a8  jmp     short loc_14003612E
```
