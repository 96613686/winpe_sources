# CEnumDebugStackFrames::Next64(ulong,tagDebugStackFrameDescriptor64 *,ulong *)

- ea: `0x180043d00`
- end: `0x180043e7d`
- name: `?Next64@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor64@@PEAK@Z`
- size: `381`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180043d00`
- `0x180043e84`
- `0x180044130`
- `0x180044170`
- `0x180050f54`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180043d55`
- `KERNEL32!GetCurrentThreadId` at `0x180043d55`

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
0x180043d00  mov     [rsp-28h+arg_0], rbx
0x180043d05  mov     [rsp-28h+arg_8], rsi
0x180043d0a  push    rbp
0x180043d0b  push    rdi
0x180043d0c  push    r12
0x180043d0e  push    r14
0x180043d10  push    r15
0x180043d12  mov     rbp, rsp
0x180043d15  sub     rsp, 30h
0x180043d19  mov     [rbp+var_8], 0
0x180043d21  mov     rsi, r9
0x180043d24  mov     [rbp+arg_18], 0
0x180043d2c  mov     r15, r8
0x180043d2f  mov     [rbp+var_10], 0
0x180043d37  mov     r14d, edx
0x180043d3a  mov     rdi, rcx
0x180043d3d  test    r9, r9
0x180043d40  jz      short loc_180043D49
0x180043d42  mov     dword ptr [r9], 0
0x180043d49  test    r14d, r14d
0x180043d4c  jz      loc_180043E5D
0x180043d52  mov     ebx, [rcx+0Ch]
0x180043d55  call    cs:__imp_GetCurrentThreadId
0x180043d5b  cmp     eax, ebx
0x180043d5d  jz      short loc_180043D69
0x180043d5f  mov     eax, 8000FFFFh
0x180043d64  jmp     loc_180043E5F
0x180043d69  test    r15, r15
0x180043d6c  jz      loc_180043E76
0x180043d72  cmp     r14d, 1
0x180043d76  jz      short loc_180043D81
0x180043d78  test    rsi, rsi
0x180043d7b  jz      loc_180043E76
0x180043d81  mov     rcx, rdi; this
0x180043d84  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180043d89  test    eax, eax
0x180043d8b  jnz     loc_180043E5F
0x180043d91  mov     rax, [rdi+20h]
0x180043d95  mov     [r15], rax
0x180043d98  mov     rax, [rdi+20h]
0x180043d9c  lock inc dword ptr [rax+28h]
0x180043da0  mov     rcx, [rdi+20h]; this
0x180043da4  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180043da8  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180043dac  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180043db1  mov     rax, [rbp+arg_18]
0x180043db5  lea     rbx, [r15+28h]
0x180043db9  mov     [r15+8], rax
0x180043dbd  mov     rax, [rbp+var_10]
0x180043dc1  mov     [r15+10h], rax
0x180043dc5  mov     qword ptr [r15+20h], 0
0x180043dcd  dec     r14d
0x180043dd0  test    r14d, r14d
0x180043dd3  jz      short loc_180043E41
0x180043dd5  mov     rcx, [rdi+20h]; this
0x180043dd9  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x180043ddd  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x180043de2  mov     rcx, [rdi+20h]; this
0x180043de6  mov     r12d, eax
0x180043de9  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x180043dee  mov     rax, [rbp+var_8]
0x180043df2  mov     [rdi+20h], rax
0x180043df6  test    r12d, r12d
0x180043df9  js      short loc_180043E3D
0x180043dfb  jnz     short loc_180043E37
0x180043dfd  mov     [rbx], rax
0x180043e00  mov     rax, [rdi+20h]
0x180043e04  lock inc dword ptr [rax+28h]
0x180043e08  mov     rcx, [rdi+20h]; this
0x180043e0c  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180043e10  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180043e14  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180043e19  mov     rax, [rbp+arg_18]
0x180043e1d  mov     [rbx+8], rax
0x180043e21  mov     rax, [rbp+var_10]
0x180043e25  mov     [rbx+10h], rax
0x180043e29  mov     qword ptr [rbx+20h], 0
0x180043e31  add     rbx, 28h ; '('
0x180043e35  jmp     short loc_180043DCD
0x180043e37  or      dword ptr [rdi+1Ch], 1
0x180043e3b  jmp     short loc_180043E41
0x180043e3d  or      dword ptr [rdi+1Ch], 2
0x180043e41  test    rsi, rsi
0x180043e44  jz      short loc_180043E5D
0x180043e46  sub     rbx, r15
0x180043e49  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180043e53  sar     rbx, 3
0x180043e57  imul    rbx, rax
0x180043e5b  mov     [rsi], ebx
0x180043e5d  xor     eax, eax
0x180043e5f  mov     rbx, [rsp+30h+arg_0]
0x180043e64  mov     rsi, [rsp+30h+arg_8]
0x180043e69  add     rsp, 30h
0x180043e6d  pop     r15
0x180043e6f  pop     r14
0x180043e71  pop     r12
0x180043e73  pop     rdi
0x180043e74  pop     rbp
0x180043e75  retn
0x180043e76  mov     eax, 80004003h
0x180043e7b  jmp     short loc_180043E5F
```
