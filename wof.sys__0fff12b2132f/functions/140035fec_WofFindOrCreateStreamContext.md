# WofFindOrCreateStreamContext

- ea: `0x140035fec`
- end: `0x14003615a`
- name: `WofFindOrCreateStreamContext`
- size: `366`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140024448`
- `0x1400338e0`

## callees

- `0x140011640`
- `0x1400119c0`
- `0x140035fec`

## import_xrefs

- `FLTMGR!FltSetStreamContext` at `0x1400360bd`
- `FLTMGR!FltSetStreamContext` at `0x1400360bd`
- `FLTMGR!FltReferenceContext` at `0x14003606b`
- `FLTMGR!FltReferenceContext` at `0x14003606b`
- `FLTMGR!FltReleaseContext` at `0x14003612c`
- `FLTMGR!FltReleaseContext` at `0x14003613e`
- `FLTMGR!FltReleaseContext` at `0x14003612c`
- `FLTMGR!FltReleaseContext` at `0x14003613e`
- `FLTMGR!FltAllocateContext` at `0x14003603e`
- `FLTMGR!FltAllocateContext` at `0x14003603e`

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
0x140035fec  push    rbp
0x140035fee  push    rbx
0x140035fef  push    rsi
0x140035ff0  push    rdi
0x140035ff1  push    r14
0x140035ff3  push    r15
0x140035ff5  mov     rbp, rsp
0x140035ff8  sub     rsp, 48h
0x140035ffc  mov     rsi, r8
0x140035fff  mov     edi, r9d
0x140036002  mov     r8d, cs:dword_140018440
0x140036009  lea     rax, [rbp+NewContext]
0x14003600d  mov     r14, rdx
0x140036010  mov     [rbp+NewContext], 0
0x140036018  mov     r15, rcx
0x14003601b  mov     [rbp+OldContext], 0
0x140036023  mov     rcx, cs:WofGlobal; Filter
0x14003602a  add     r8, 40h ; '@'; ContextSize
0x14003602e  mov     edx, 8; ContextType
0x140036033  mov     [rsp+48h+ReturnedContext], rax; ReturnedContext
0x140036038  mov     r9d, 200h; PoolType
0x14003603e  call    cs:__imp_FltAllocateContext
0x140036045  nop     dword ptr [rax+rax+00h]
0x14003604a  test    eax, eax
0x14003604c  js      loc_1400360E7
0x140036052  mov     r8d, cs:dword_140018440
0x140036059  xor     edx, edx; Val
0x14003605b  mov     rcx, [rbp+NewContext]; void *
0x14003605f  add     r8, 40h ; '@'; Size
0x140036063  call    memset
0x140036068  mov     rcx, rsi; Context
0x14003606b  call    cs:__imp_FltReferenceContext
0x140036072  nop     dword ptr [rax+rax+00h]
0x140036077  mov     rax, [rbp+NewContext]
0x14003607b  mov     [rax], rsi
0x14003607e  mov     rcx, [rbp+NewContext]
0x140036082  mov     eax, [rcx+8]
0x140036085  or      eax, 4000004h
0x14003608a  mov     [rcx+8], eax
0x14003608d  mov     rax, [rbp+NewContext]
0x140036091  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x140036098  cmp     edi, 4
0x14003609b  jb      short loc_1400360F5
0x14003609d  mov     rax, [rbp+NewContext]
0x1400360a1  mov     r8d, 1; Operation
0x1400360a7  mov     rdx, r14; FileObject
0x1400360aa  mov     rcx, r15; Instance
0x1400360ad  mov     [rax+0Ch], edi
0x1400360b0  lea     rax, [rbp+OldContext]
0x1400360b4  mov     r9, [rbp+NewContext]; NewContext
0x1400360b8  mov     [rsp+48h+ReturnedContext], rax; OldContext
0x1400360bd  call    cs:__imp_FltSetStreamContext
0x1400360c4  nop     dword ptr [rax+rax+00h]
0x1400360c9  mov     ebx, eax
0x1400360cb  test    eax, eax
0x1400360cd  js      short loc_14003613A
0x1400360cf  mov     rax, [rsi+8]
0x1400360d3  lock inc dword ptr [rax+0B0h]
0x1400360da  mov     rcx, [rbp+NewContext]
0x1400360de  mov     rax, [rbp+arg_20]
0x1400360e2  mov     [rax], rcx
0x1400360e5  mov     eax, ebx
0x1400360e7  add     rsp, 48h
0x1400360eb  pop     r15
0x1400360ed  pop     r14
0x1400360ef  pop     rdi
0x1400360f0  pop     rsi
0x1400360f1  pop     rbx
0x1400360f2  pop     rbp
0x1400360f3  retn
0x1400360f5  imul    rax, rdi, 1A8h
0x1400360fc  lea     rdx, WPP_MAIN_CB.Queue+10h
0x140036103  cmp     byte ptr [rax+rdx], 0
0x140036107  jz      short loc_14003609D
0x140036109  mov     rcx, [rbp+NewContext]
0x14003610d  mov     rax, [rax+rdx+98h]
0x140036115  add     rcx, 40h ; '@'
0x140036119  call    _guard_dispatch_icall
0x14003611e  mov     ebx, eax
0x140036120  test    eax, eax
0x140036122  jns     loc_14003609D
0x140036128  mov     rcx, [rbp+NewContext]; Context
0x14003612c  call    cs:__imp_FltReleaseContext
0x140036133  nop     dword ptr [rax+rax+00h]
0x140036138  jmp     short loc_1400360E5
0x14003613a  mov     rcx, [rbp+NewContext]; Context
0x14003613e  call    cs:__imp_FltReleaseContext
0x140036145  nop     dword ptr [rax+rax+00h]
0x14003614a  cmp     ebx, 0C01C0002h
0x140036150  jnz     short loc_1400360E5
0x140036152  mov     rcx, [rbp+OldContext]
0x140036156  xor     ebx, ebx
0x140036158  jmp     short loc_1400360DE
```
