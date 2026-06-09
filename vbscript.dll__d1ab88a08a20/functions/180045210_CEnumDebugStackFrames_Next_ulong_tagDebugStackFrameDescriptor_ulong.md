# CEnumDebugStackFrames::Next(ulong,tagDebugStackFrameDescriptor *,ulong *)

- ea: `0x180045210`
- end: `0x180045380`
- name: `?Next@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor@@PEAK@Z`
- size: `368`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800450dc`
- `0x180045210`
- `0x180045390`
- `0x1800453d0`
- `0x180052738`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180045265`
- `KERNEL32!GetCurrentThreadId` at `0x180045265`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Next(
        CEnumDebugStackFrames *this,
        int a2,
        struct tagDebugStackFrameDescriptor *a3,
        unsigned int *a4)
{
  int v6; // r14d
  int v8; // ebx
  __int64 result; // rax
  struct tagDebugStackFrameDescriptor *v10; // rbx
  int NextFrame; // r12d
  struct CDebugStackFrame *v12; // rax
  unsigned __int64 v13; // [rsp+20h] [rbp-10h] BYREF
  struct CDebugStackFrame *v14; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  v14 = 0;
  v15 = 0;
  v13 = 0;
  v6 = a2;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 0;
  v8 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v8 )
    return 2147549183LL;
  if ( !a3 || v6 != 1 && !a4 )
    return 2147500035LL;
  result = CEnumDebugStackFrames::NextCommon(this);
  if ( !(_DWORD)result )
  {
    a3->pdsf = (IDebugStackFrame *)*((_QWORD *)this + 4);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 40LL));
    CDebugStackFrame::GetPhysicalStackRange(*((CDebugStackFrame **)this + 4), &v15, &v13);
    v10 = a3 + 1;
    a3->dwMin = v15;
    a3->dwLim = v13;
    a3->punkFinal = 0;
    while ( --v6 )
    {
      NextFrame = CDebugStackFrame::GetNextFrame(*((CDebugStackFrame **)this + 4), &v14);
      CDebugStackFrame::Release(*((CDebugStackFrame **)this + 4));
      v12 = v14;
      *((_QWORD *)this + 4) = v14;
      if ( NextFrame < 0 )
      {
        *((_DWORD *)this + 7) |= 2u;
        break;
      }
      if ( NextFrame )
      {
        *((_DWORD *)this + 7) |= 1u;
        break;
      }
      v10->pdsf = (IDebugStackFrame *)v12;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 40LL));
      CDebugStackFrame::GetPhysicalStackRange(*((CDebugStackFrame **)this + 4), &v15, &v13);
      v10->dwMin = v15;
      v10->dwLim = v13;
      v10->punkFinal = 0;
      ++v10;
    }
    if ( a4 )
      *a4 = v10 - a3;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180045210  mov     [rsp-28h+arg_0], rbx
0x180045215  mov     [rsp-28h+arg_8], rsi
0x18004521a  push    rbp
0x18004521b  push    rdi
0x18004521c  push    r12
0x18004521e  push    r14
0x180045220  push    r15
0x180045222  mov     rbp, rsp
0x180045225  sub     rsp, 30h
0x180045229  mov     [rbp+var_8], 0
0x180045231  mov     rsi, r9
0x180045234  mov     [rbp+arg_18], 0
0x18004523c  mov     r15, r8
0x18004523f  mov     [rbp+var_10], 0
0x180045247  mov     r14d, edx
0x18004524a  mov     rdi, rcx
0x18004524d  test    r9, r9
0x180045250  jz      short loc_180045259
0x180045252  mov     dword ptr [r9], 0
0x180045259  test    r14d, r14d
0x18004525c  jz      loc_18004535F
0x180045262  mov     ebx, [rcx+0Ch]
0x180045265  call    cs:__imp_GetCurrentThreadId
0x18004526c  nop     dword ptr [rax+rax+00h]
0x180045271  cmp     eax, ebx
0x180045273  jz      short loc_18004527F
0x180045275  mov     eax, 8000FFFFh
0x18004527a  jmp     loc_180045361
0x18004527f  test    r15, r15
0x180045282  jz      loc_180045379
0x180045288  cmp     r14d, 1
0x18004528c  jz      short loc_180045297
0x18004528e  test    rsi, rsi
0x180045291  jz      loc_180045379
0x180045297  mov     rcx, rdi; this
0x18004529a  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x18004529f  test    eax, eax
0x1800452a1  jnz     loc_180045361
0x1800452a7  mov     rax, [rdi+20h]
0x1800452ab  mov     [r15], rax
0x1800452ae  mov     rax, [rdi+20h]
0x1800452b2  lock inc dword ptr [rax+28h]
0x1800452b6  mov     rcx, [rdi+20h]; this
0x1800452ba  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800452be  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x1800452c2  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x1800452c7  mov     eax, dword ptr [rbp+arg_18]
0x1800452ca  lea     rbx, [r15+20h]
0x1800452ce  mov     [r15+8], eax
0x1800452d2  mov     eax, dword ptr [rbp+var_10]
0x1800452d5  mov     [r15+0Ch], eax
0x1800452d9  mov     qword ptr [r15+18h], 0
0x1800452e1  dec     r14d
0x1800452e4  test    r14d, r14d
0x1800452e7  jz      short loc_180045351
0x1800452e9  mov     rcx, [rdi+20h]; this
0x1800452ed  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x1800452f1  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x1800452f6  mov     rcx, [rdi+20h]; this
0x1800452fa  mov     r12d, eax
0x1800452fd  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180045302  mov     rax, [rbp+var_8]
0x180045306  mov     [rdi+20h], rax
0x18004530a  test    r12d, r12d
0x18004530d  js      short loc_18004534D
0x18004530f  jnz     short loc_180045347
0x180045311  mov     [rbx], rax
0x180045314  mov     rax, [rdi+20h]
0x180045318  lock inc dword ptr [rax+28h]
0x18004531c  mov     rcx, [rdi+20h]; this
0x180045320  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180045324  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180045328  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x18004532d  mov     eax, dword ptr [rbp+arg_18]
0x180045330  mov     [rbx+8], eax
0x180045333  mov     eax, dword ptr [rbp+var_10]
0x180045336  mov     [rbx+0Ch], eax
0x180045339  mov     qword ptr [rbx+18h], 0
0x180045341  add     rbx, 20h ; ' '
0x180045345  jmp     short loc_1800452E1
0x180045347  or      dword ptr [rdi+1Ch], 1
0x18004534b  jmp     short loc_180045351
0x18004534d  or      dword ptr [rdi+1Ch], 2
0x180045351  test    rsi, rsi
0x180045354  jz      short loc_18004535F
0x180045356  sub     rbx, r15
0x180045359  sar     rbx, 5
0x18004535d  mov     [rsi], ebx
0x18004535f  xor     eax, eax
0x180045361  mov     rbx, [rsp+30h+arg_0]
0x180045366  mov     rsi, [rsp+30h+arg_8]
0x18004536b  add     rsp, 30h
0x18004536f  pop     r15
0x180045371  pop     r14
0x180045373  pop     r12
0x180045375  pop     rdi
0x180045376  pop     rbp
0x180045377  retn
0x180045379  mov     eax, 80004003h
0x18004537e  jmp     short loc_180045361
```
