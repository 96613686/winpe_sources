# CEnumDebugStackFrames::Next64(ulong,tagDebugStackFrameDescriptor64 *,ulong *)

- ea: `0x180044f50`
- end: `0x1800450d4`
- name: `?Next64@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor64@@PEAK@Z`
- size: `388`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180044f50`
- `0x1800450dc`
- `0x180045390`
- `0x1800453d0`
- `0x180052738`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180044fa5`
- `KERNEL32!GetCurrentThreadId` at `0x180044fa5`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Next64(
        CEnumDebugStackFrames *this,
        int a2,
        struct tagDebugStackFrameDescriptor64 *a3,
        unsigned int *a4)
{
  int v6; // r14d
  int v8; // ebx
  __int64 result; // rax
  struct tagDebugStackFrameDescriptor64 *v10; // rbx
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
      *a4 = -858993459 * (((char *)v10 - (char *)a3) >> 3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180044f50  mov     [rsp-28h+arg_0], rbx
0x180044f55  mov     [rsp-28h+arg_8], rsi
0x180044f5a  push    rbp
0x180044f5b  push    rdi
0x180044f5c  push    r12
0x180044f5e  push    r14
0x180044f60  push    r15
0x180044f62  mov     rbp, rsp
0x180044f65  sub     rsp, 30h
0x180044f69  mov     [rbp+var_8], 0
0x180044f71  mov     rsi, r9
0x180044f74  mov     [rbp+arg_18], 0
0x180044f7c  mov     r15, r8
0x180044f7f  mov     [rbp+var_10], 0
0x180044f87  mov     r14d, edx
0x180044f8a  mov     rdi, rcx
0x180044f8d  test    r9, r9
0x180044f90  jz      short loc_180044F99
0x180044f92  mov     dword ptr [r9], 0
0x180044f99  test    r14d, r14d
0x180044f9c  jz      loc_1800450B3
0x180044fa2  mov     ebx, [rcx+0Ch]
0x180044fa5  call    cs:__imp_GetCurrentThreadId
0x180044fac  nop     dword ptr [rax+rax+00h]
0x180044fb1  cmp     eax, ebx
0x180044fb3  jz      short loc_180044FBF
0x180044fb5  mov     eax, 8000FFFFh
0x180044fba  jmp     loc_1800450B5
0x180044fbf  test    r15, r15
0x180044fc2  jz      loc_1800450CD
0x180044fc8  cmp     r14d, 1
0x180044fcc  jz      short loc_180044FD7
0x180044fce  test    rsi, rsi
0x180044fd1  jz      loc_1800450CD
0x180044fd7  mov     rcx, rdi; this
0x180044fda  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180044fdf  test    eax, eax
0x180044fe1  jnz     loc_1800450B5
0x180044fe7  mov     rax, [rdi+20h]
0x180044feb  mov     [r15], rax
0x180044fee  mov     rax, [rdi+20h]
0x180044ff2  lock inc dword ptr [rax+28h]
0x180044ff6  mov     rcx, [rdi+20h]; this
0x180044ffa  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180044ffe  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180045002  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180045007  mov     rax, [rbp+arg_18]
0x18004500b  lea     rbx, [r15+28h]
0x18004500f  mov     [r15+8], rax
0x180045013  mov     rax, [rbp+var_10]
0x180045017  mov     [r15+10h], rax
0x18004501b  mov     qword ptr [r15+20h], 0
0x180045023  dec     r14d
0x180045026  test    r14d, r14d
0x180045029  jz      short loc_180045097
0x18004502b  mov     rcx, [rdi+20h]; this
0x18004502f  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x180045033  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180045038  mov     rcx, [rdi+20h]; this
0x18004503c  mov     r12d, eax
0x18004503f  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180045044  mov     rax, [rbp+var_8]
0x180045048  mov     [rdi+20h], rax
0x18004504c  test    r12d, r12d
0x18004504f  js      short loc_180045093
0x180045051  jnz     short loc_18004508D
0x180045053  mov     [rbx], rax
0x180045056  mov     rax, [rdi+20h]
0x18004505a  lock inc dword ptr [rax+28h]
0x18004505e  mov     rcx, [rdi+20h]; this
0x180045062  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180045066  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x18004506a  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x18004506f  mov     rax, [rbp+arg_18]
0x180045073  mov     [rbx+8], rax
0x180045077  mov     rax, [rbp+var_10]
0x18004507b  mov     [rbx+10h], rax
0x18004507f  mov     qword ptr [rbx+20h], 0
0x180045087  add     rbx, 28h ; '('
0x18004508b  jmp     short loc_180045023
0x18004508d  or      dword ptr [rdi+1Ch], 1
0x180045091  jmp     short loc_180045097
0x180045093  or      dword ptr [rdi+1Ch], 2
0x180045097  test    rsi, rsi
0x18004509a  jz      short loc_1800450B3
0x18004509c  sub     rbx, r15
0x18004509f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800450a9  sar     rbx, 3
0x1800450ad  imul    rbx, rax
0x1800450b1  mov     [rsi], ebx
0x1800450b3  xor     eax, eax
0x1800450b5  mov     rbx, [rsp+30h+arg_0]
0x1800450ba  mov     rsi, [rsp+30h+arg_8]
0x1800450bf  add     rsp, 30h
0x1800450c3  pop     r15
0x1800450c5  pop     r14
0x1800450c7  pop     r12
0x1800450c9  pop     rdi
0x1800450ca  pop     rbp
0x1800450cb  retn
0x1800450cd  mov     eax, 80004003h
0x1800450d2  jmp     short loc_1800450B5
```
