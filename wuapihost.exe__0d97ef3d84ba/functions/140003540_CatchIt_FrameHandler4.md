# CatchIt___FrameHandler4_

- ea: `0x140003540`
- end: `0x14000361e`
- name: `CatchIt___FrameHandler4_`
- size: `222`
- prototype: `__int64 __usercall@<rax>(struct EHExceptionRecord *@<rcx>, unsigned __int64 *@<rdx>, struct FH4::FuncInfo4 *, struct FH4::HandlerType4 *, __int64, __int64, int, int, int, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140003624`
- `0x140003b64`

## callees

- `0x14000251c`
- `0x1400026cc`
- `0x140002a80`
- `0x140003478`
- `0x140003540`

## pseudocode

```c
void __fastcall CatchIt___FrameHandler4_(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        struct _CONTEXT *a3,
        struct _xDISPATCHER_CONTEXT *a4,
        struct FH4::FuncInfo4 *a5,
        struct FH4::HandlerType4 *a6,
        __int64 a7,
        int *a8,
        int a9,
        int a10,
        int a11,
        char a12)
{
  unsigned __int64 *EstablisherFrame; // rax
  unsigned __int64 *v16; // r15
  struct FH4::HandlerType4 *v17; // rbp
  __int64 v18; // rbx
  int v19; // edi
  int v20; // esi
  __int64 ImageBase; // rax
  unsigned __int64 v22; // [rsp+A8h] [rbp+10h] BYREF
  struct _CONTEXT *v23; // [rsp+B0h] [rbp+18h]

  v23 = a3;
  v22 = 0;
  EstablisherFrame = __FrameHandler4::GetEstablisherFrame(a2, a4, a5, &v22);
  v16 = EstablisherFrame;
  v17 = a6;
  if ( a7 )
    BuildCatchObjectInternal___FrameHandler4_(a1, EstablisherFrame, a6);
  v18 = *((int *)v17 + 4);
  v19 = a8[2];
  v20 = *a8;
  ImageBase = GetImageBase();
  __FrameHandler4::UnwindNestedFrames(a2, a1, v23, v16, (void *)(v18 + ImageBase), a5, v20, v19, v17, a4, a12);
}

```

## disassembly

```asm
0x140003540  mov     rax, rsp
0x140003543  mov     [rax+8], rbx
0x140003547  mov     [rax+18h], r8
0x14000354b  push    rbp
0x14000354c  push    rsi
0x14000354d  push    rdi
0x14000354e  push    r12
0x140003550  push    r13
0x140003552  push    r14
0x140003554  push    r15
0x140003556  sub     rsp, 60h
0x14000355a  mov     r8, [rsp+98h+arg_20]; struct FH4::FuncInfo4 *
0x140003562  mov     r12, r9
0x140003565  mov     r13, rdx
0x140003568  mov     qword ptr [rax+10h], 0
0x140003570  mov     r14, rcx
0x140003573  lea     r9, [rax+10h]; unsigned __int64 *
0x140003577  mov     rdx, r12; struct _xDISPATCHER_CONTEXT *
0x14000357a  mov     rcx, r13; unsigned __int64 *
0x14000357d  call    ?GetEstablisherFrame@__FrameHandler4@@SAPEA_KPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@0@Z; __FrameHandler4::GetEstablisherFrame(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,unsigned __int64 *)
0x140003582  mov     r9, [rsp+98h+arg_30]
0x14000358a  mov     r15, rax
0x14000358d  mov     rbp, [rsp+98h+arg_28]
0x140003595  test    r9, r9
0x140003598  jz      short loc_1400035A8
0x14000359a  mov     r8, rbp
0x14000359d  mov     rdx, rax
0x1400035a0  mov     rcx, r14
0x1400035a3  call    BuildCatchObjectInternal___FrameHandler4_
0x1400035a8  mov     rcx, [rsp+98h+arg_38]
0x1400035b0  movsxd  rbx, dword ptr [rbp+10h]
0x1400035b4  mov     edi, [rcx+8]
0x1400035b7  mov     esi, [rcx]
0x1400035b9  call    _GetImageBase
0x1400035be  mov     cl, [rsp+98h+arg_58]
0x1400035c5  add     rax, rbx
0x1400035c8  mov     r8, [rsp+98h+arg_10]; struct _CONTEXT *
0x1400035d0  mov     r9, r15; unsigned __int64 *
0x1400035d3  mov     [rsp+98h+var_48], cl; char
0x1400035d7  mov     rdx, r14; struct EHExceptionRecord *
0x1400035da  mov     rcx, [rsp+98h+arg_20]
0x1400035e2  mov     [rsp+98h+var_50], r12; struct _xDISPATCHER_CONTEXT *
0x1400035e7  mov     [rsp+98h+var_58], rbp; struct FH4::HandlerType4 *
0x1400035ec  mov     [rsp+98h+var_60], edi; int
0x1400035f0  mov     [rsp+98h+var_68], esi; int
0x1400035f4  mov     [rsp+98h+var_70], rcx; struct FH4::FuncInfo4 *
0x1400035f9  mov     rcx, r13; unsigned __int64 *
0x1400035fc  mov     [rsp+98h+var_78], rax; void *
0x140003601  call    ?UnwindNestedFrames@__FrameHandler4@@SAXPEA_KPEAUEHExceptionRecord@@PEAU_CONTEXT@@0PEAXPEAUFuncInfo4@FH4@@HHPEAUHandlerType4@5@PEAU_xDISPATCHER_CONTEXT@@E@Z; __FrameHandler4::UnwindNestedFrames(unsigned __int64 *,EHExceptionRecord *,_CONTEXT *,unsigned __int64 *,void *,FH4::FuncInfo4 *,int,int,FH4::HandlerType4 *,_xDISPATCHER_CONTEXT *,uchar)
0x140003606  mov     rbx, [rsp+98h+arg_0]
0x14000360e  add     rsp, 60h
0x140003612  pop     r15
0x140003614  pop     r14
0x140003616  pop     r13
0x140003618  pop     r12
0x14000361a  pop     rdi
0x14000361b  pop     rsi
0x14000361c  pop     rbp
0x14000361d  retn
```
