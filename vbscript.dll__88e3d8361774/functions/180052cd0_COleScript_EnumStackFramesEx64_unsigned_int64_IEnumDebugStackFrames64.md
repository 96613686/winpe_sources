# COleScript::EnumStackFramesEx64(unsigned __int64,IEnumDebugStackFrames64 * *)

- ea: `0x180052cd0`
- end: `0x180052d84`
- name: `?EnumStackFramesEx64@COleScript@@UEAAJ_KPEAPEAUIEnumDebugStackFrames64@@@Z`
- size: `180`
- prototype: `int(COleScript *__hidden this, unsigned __int64, struct IEnumDebugStackFrames64 **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180020398`
- `0x180043350`
- `0x180045490`
- `0x18005042c`
- `0x180051770`
- `0x180052cd0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052d12`
- `KERNEL32!GetCurrentThreadId` at `0x180052d12`

## pseudocode

```c
__int64 __fastcall COleScript::EnumStackFramesEx64(
        COleScript *this,
        unsigned __int64 a2,
        struct IEnumDebugStackFrames64 **a3)
{
  int v7; // ebx
  CEnumDebugStackFrames *v8; // rax
  CEnumDebugStackFrames *v9; // rax
  CEnumDebugStackFrames *v10; // rdi
  unsigned int Interface; // ebx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !(unsigned int)COleScript::FDebuggerEnabled((COleScript *)((char *)this - 40)) )
    return 2147549183LL;
  v7 = *((_DWORD *)this + 51);
  if ( GetCurrentThreadId() != v7 || !*((_QWORD *)this + 75) )
    return 2147500037LL;
  v8 = (CEnumDebugStackFrames *)operator new(0x30u);
  if ( !v8 )
    return 2147942414LL;
  v9 = CEnumDebugStackFrames::CEnumDebugStackFrames(v8, a2, *((struct CSession **)this + 75));
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  Interface = CEnumDebugStackFrames::QueryInterface(v9, &IID_IEnumDebugStackFrames64, (void **)a3);
  CEnumDebugStackFrames::Release(v10);
  return Interface;
}

```

## disassembly

```asm
0x180052cd0  push    rbx
0x180052cd2  push    rbp
0x180052cd3  push    rsi
0x180052cd4  push    rdi
0x180052cd5  sub     rsp, 28h
0x180052cd9  mov     rsi, r8
0x180052cdc  mov     rbp, rdx
0x180052cdf  mov     rdi, rcx
0x180052ce2  test    r8, r8
0x180052ce5  jnz     short loc_180052CF1
0x180052ce7  mov     eax, 80004003h
0x180052cec  jmp     loc_180052D7B
0x180052cf1  add     rcx, 0FFFFFFFFFFFFFFD8h; this
0x180052cf5  mov     qword ptr [r8], 0
0x180052cfc  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180052d01  test    eax, eax
0x180052d03  jnz     short loc_180052D0C
0x180052d05  mov     eax, 8000FFFFh
0x180052d0a  jmp     short loc_180052D7B
0x180052d0c  mov     ebx, [rdi+0CCh]
0x180052d12  call    cs:__imp_GetCurrentThreadId
0x180052d18  cmp     eax, ebx
0x180052d1a  jnz     short loc_180052D76
0x180052d1c  cmp     qword ptr [rdi+258h], 0
0x180052d24  jz      short loc_180052D76
0x180052d26  mov     ecx, 30h ; '0'; Size
0x180052d2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052d30  test    rax, rax
0x180052d33  jz      short loc_180052D6F
0x180052d35  mov     r8, [rdi+258h]; struct CSession *
0x180052d3c  mov     rdx, rbp; unsigned __int64
0x180052d3f  mov     rcx, rax; this
0x180052d42  call    ??0CEnumDebugStackFrames@@QEAA@_KPEAVCSession@@@Z; CEnumDebugStackFrames::CEnumDebugStackFrames(unsigned __int64,CSession *)
0x180052d47  mov     rdi, rax
0x180052d4a  test    rax, rax
0x180052d4d  jz      short loc_180052D6F
0x180052d4f  mov     r8, rsi; void **
0x180052d52  lea     rdx, IID_IEnumDebugStackFrames64; struct _GUID *
0x180052d59  mov     rcx, rax; this
0x180052d5c  call    ?QueryInterface@CEnumDebugStackFrames@@UEAAJAEBU_GUID@@PEAPEAX@Z; CEnumDebugStackFrames::QueryInterface(_GUID const &,void * *)
0x180052d61  mov     rcx, rdi; this
0x180052d64  mov     ebx, eax
0x180052d66  call    ?Release@CEnumDebugStackFrames@@UEAAKXZ; CEnumDebugStackFrames::Release(void)
0x180052d6b  mov     eax, ebx
0x180052d6d  jmp     short loc_180052D7B
0x180052d6f  mov     eax, 8007000Eh
0x180052d74  jmp     short loc_180052D7B
0x180052d76  mov     eax, 80004005h
0x180052d7b  add     rsp, 28h
0x180052d7f  pop     rdi
0x180052d80  pop     rsi
0x180052d81  pop     rbp
0x180052d82  pop     rbx
0x180052d83  retn
```
