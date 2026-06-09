# COleScript::EnumStackFramesEx32(ulong,IEnumDebugStackFrames * *)

- ea: `0x180052c10`
- end: `0x180052cbf`
- name: `?EnumStackFramesEx32@COleScript@@UEAAJKPEAPEAUIEnumDebugStackFrames@@@Z`
- size: `175`
- prototype: `int(COleScript *__hidden this, unsigned int, struct IEnumDebugStackFrames **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180052bf0`

## callees

- `0x180020398`
- `0x180043350`
- `0x180045490`
- `0x18005042c`
- `0x180051770`
- `0x180052c10`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052c4d`
- `KERNEL32!GetCurrentThreadId` at `0x180052c4d`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx32(
        struct CSession **this,
        unsigned int a2,
        struct IEnumDebugStackFrames **a3)
{
  unsigned __int64 v3; // rbp
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)this) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 61);
  if ( GetCurrentThreadId() != v7 || !this[80] )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, v3, this[80]);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180052c10  push    rbx
0x180052c12  push    rbp
0x180052c13  push    rsi
0x180052c14  push    rdi
0x180052c15  sub     rsp, 28h
0x180052c19  mov     ebp, edx
0x180052c1b  mov     rsi, r8
0x180052c1e  mov     rdi, rcx
0x180052c21  test    r8, r8
0x180052c24  jnz     short loc_180052C30
0x180052c26  mov     eax, 80004003h
0x180052c2b  jmp     loc_180052CB6
0x180052c30  mov     qword ptr [r8], 0
0x180052c37  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180052c3c  test    eax, eax
0x180052c3e  jnz     short loc_180052C47
0x180052c40  mov     eax, 8000FFFFh
0x180052c45  jmp     short loc_180052CB6
0x180052c47  mov     ebx, [rdi+0F4h]
0x180052c4d  call    cs:__imp_GetCurrentThreadId
0x180052c53  cmp     eax, ebx
0x180052c55  jnz     short loc_180052CB1
0x180052c57  cmp     qword ptr [rdi+280h], 0
0x180052c5f  jz      short loc_180052CB1
0x180052c61  mov     ecx, 30h ; '0'; Size
0x180052c66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052c6b  test    rax, rax
0x180052c6e  jz      short loc_180052CAA
0x180052c70  mov     r8, [rdi+280h]; struct CSession *
0x180052c77  mov     rdx, rbp; unsigned __int64
0x180052c7a  mov     rcx, rax; this
0x180052c7d  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180052c82  mov     rdi, rax
0x180052c85  test    rax, rax
0x180052c88  jz      short loc_180052CAA
0x180052c8a  mov     r8, rsi; void **
0x180052c8d  lea     rdx, IID_IEnumDebugStackFrames; struct _GUID *
0x180052c94  mov     rcx, rax; this
0x180052c97  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180052c9c  mov     rcx, rdi; this
0x180052c9f  mov     ebx, eax
0x180052ca1  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x180052ca6  mov     eax, ebx
0x180052ca8  jmp     short loc_180052CB6
0x180052caa  mov     eax, 8007000Eh
0x180052caf  jmp     short loc_180052CB6
0x180052cb1  mov     eax, 80004005h
0x180052cb6  add     rsp, 28h
0x180052cba  pop     rdi
0x180052cbb  pop     rsi
0x180052cbc  pop     rbp
0x180052cbd  pop     rbx
0x180052cbe  retn
```
