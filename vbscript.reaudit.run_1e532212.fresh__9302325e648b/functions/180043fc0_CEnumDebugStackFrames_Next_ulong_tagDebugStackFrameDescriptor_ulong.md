# CEnumDebugStackFrames::Next(ulong,tagDebugStackFrameDescriptor *,ulong *)

- ea: `0x180043fc0`
- end: `0x180044129`
- name: `?Next@CEnumDebugStackFrames@@UEAAJKPEAUtagDebugStackFrameDescriptor@@PEAK@Z`
- size: `361`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int, struct tagDebugStackFrameDescriptor *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180043e84`
- `0x180043fc0`
- `0x180044130`
- `0x180044170`
- `0x180050f54`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180044015`
- `KERNEL32!GetCurrentThreadId` at `0x180044015`

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
0x180043fc0  mov     [rsp-28h+arg_0], rbx
0x180043fc5  mov     [rsp-28h+arg_8], rsi
0x180043fca  push    rbp
0x180043fcb  push    rdi
0x180043fcc  push    r12
0x180043fce  push    r14
0x180043fd0  push    r15
0x180043fd2  mov     rbp, rsp
0x180043fd5  sub     rsp, 30h
0x180043fd9  mov     [rbp+var_8], 0
0x180043fe1  mov     rsi, r9
0x180043fe4  mov     [rbp+arg_18], 0
0x180043fec  mov     r15, r8
0x180043fef  mov     [rbp+var_10], 0
0x180043ff7  mov     r14d, edx
0x180043ffa  mov     rdi, rcx
0x180043ffd  test    r9, r9
0x180044000  jz      short loc_180044009
0x180044002  mov     dword ptr [r9], 0
0x180044009  test    r14d, r14d
0x18004400c  jz      loc_180044109
0x180044012  mov     ebx, [rcx+0Ch]
0x180044015  call    cs:__imp_GetCurrentThreadId
0x18004401b  cmp     eax, ebx
0x18004401d  jz      short loc_180044029
0x18004401f  mov     eax, 8000FFFFh
0x180044024  jmp     loc_18004410B
0x180044029  test    r15, r15
0x18004402c  jz      loc_180044122
0x180044032  cmp     r14d, 1
0x180044036  jz      short loc_180044041
0x180044038  test    rsi, rsi
0x18004403b  jz      loc_180044122
0x180044041  mov     rcx, rdi; this
0x180044044  call    ?NextCommon@CEnumDebugStackFrames@@AEAAJXZ; CEnumDebugStackFrames::NextCommon(void)
0x180044049  test    eax, eax
0x18004404b  jnz     loc_18004410B
0x180044051  mov     rax, [rdi+20h]
0x180044055  mov     [r15], rax
0x180044058  mov     rax, [rdi+20h]
0x18004405c  lock inc dword ptr [rax+28h]
0x180044060  mov     rcx, [rdi+20h]; this
0x180044064  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180044068  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x18004406c  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x180044071  mov     eax, dword ptr [rbp+arg_18]
0x180044074  lea     rbx, [r15+20h]
0x180044078  mov     [r15+8], eax
0x18004407c  mov     eax, dword ptr [rbp+var_10]
0x18004407f  mov     [r15+0Ch], eax
0x180044083  mov     qword ptr [r15+18h], 0
0x18004408b  dec     r14d
0x18004408e  test    r14d, r14d
0x180044091  jz      short loc_1800440FB
0x180044093  mov     rcx, [rdi+20h]; this
0x180044097  lea     rdx, [rbp+var_8]; struct CDebugStackFrame **
0x18004409b  call    ?GetNextFrame@CDebugStackFrame@@QEAAJPEAPEAV1@@Z; CDebugStackFrame::GetNextFrame(CDebugStackFrame * *)
0x1800440a0  mov     rcx, [rdi+20h]; this
0x1800440a4  mov     r12d, eax
0x1800440a7  call    ?Release@CDebugStackFrame@@UEAAKXZ; CDebugStackFrame::Release(void)
0x1800440ac  mov     rax, [rbp+var_8]
0x1800440b0  mov     [rdi+20h], rax
0x1800440b4  test    r12d, r12d
0x1800440b7  js      short loc_1800440F7
0x1800440b9  jnz     short loc_1800440F1
0x1800440bb  mov     [rbx], rax
0x1800440be  mov     rax, [rdi+20h]
0x1800440c2  lock inc dword ptr [rax+28h]
0x1800440c6  mov     rcx, [rdi+20h]; this
0x1800440ca  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800440ce  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x1800440d2  call    ?GetPhysicalStackRange@CDebugStackFrame@@QEAAJPEA_K0@Z; CDebugStackFrame::GetPhysicalStackRange(unsigned __int64 *,unsigned __int64 *)
0x1800440d7  mov     eax, dword ptr [rbp+arg_18]
0x1800440da  mov     [rbx+8], eax
0x1800440dd  mov     eax, dword ptr [rbp+var_10]
0x1800440e0  mov     [rbx+0Ch], eax
0x1800440e3  mov     qword ptr [rbx+18h], 0
0x1800440eb  add     rbx, 20h ; ' '
0x1800440ef  jmp     short loc_18004408B
0x1800440f1  or      dword ptr [rdi+1Ch], 1
0x1800440f5  jmp     short loc_1800440FB
0x1800440f7  or      dword ptr [rdi+1Ch], 2
0x1800440fb  test    rsi, rsi
0x1800440fe  jz      short loc_180044109
0x180044100  sub     rbx, r15
0x180044103  sar     rbx, 5
0x180044107  mov     [rsi], ebx
0x180044109  xor     eax, eax
0x18004410b  mov     rbx, [rsp+30h+arg_0]
0x180044110  mov     rsi, [rsp+30h+arg_8]
0x180044115  add     rsp, 30h
0x180044119  pop     r15
0x18004411b  pop     r14
0x18004411d  pop     r12
0x18004411f  pop     rdi
0x180044120  pop     rbp
0x180044121  retn
0x180044122  mov     eax, 80004003h
0x180044127  jmp     short loc_18004410B
```
