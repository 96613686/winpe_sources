# CLogManager::RemoveStack(void *)

- ea: `0x18001fda0`
- end: `0x18001fe23`
- name: `?RemoveStack@CLogManager@@UEAAHPEAX@Z`
- size: `131`
- prototype: `__int64 __fastcall(CLogManager *__hidden this, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18001eb04`
- `0x18001f81c`
- `0x18001fb9c`
- `0x18001fda0`
- `0x180022f4c`
- `0x180023474`

## pseudocode

```c
__int64 __fastcall CLogManager::RemoveStack(CLogManager *this, struct tagLOG_OUTPUT_STACK *a2)
{
  __int64 v4; // rcx
  struct tagLOG_OUTPUT_STACK *v5; // rax
  struct tagLOG_OUTPUT_STACK *v6; // rdi

  CMutualExclusionObject::Acquiry((CLogManager *)((char *)this + 40));
  v4 = *((_QWORD *)this + 11);
  *(_DWORD *)(v4 + 12) = 0;
  while ( 1 )
  {
    v5 = (struct tagLOG_OUTPUT_STACK *)CPtrList<tagLOG_OUTPUT_STACK *>::Next(v4);
    v6 = v5;
    if ( !v5 )
      break;
    if ( v5 == a2 && (unsigned int)CLogManager::DestroyStack(this, v5) )
    {
      CPtrList<tagLOG_OUTPUT_STACK *>::Remove(*((_QWORD *)this + 11), v6);
      CPtrList<tagLOG_OUTPUT_STACK *>::Remove(*((_QWORD *)this + 12), v6);
      break;
    }
    v4 = *((_QWORD *)this + 11);
  }
  CMutualExclusionObject::Release((CLogManager *)((char *)this + 40));
  return 1;
}

```

## disassembly

```asm
0x18001fda0  mov     [rsp+arg_0], rcx
0x18001fda5  push    rbx
0x18001fda6  push    rsi
0x18001fda7  push    rdi
0x18001fda8  push    r14
0x18001fdaa  sub     rsp, 28h
0x18001fdae  mov     r14, rdx
0x18001fdb1  mov     rbx, rcx
0x18001fdb4  add     rcx, 28h ; '('; this
0x18001fdb8  call    ?Acquiry@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Acquiry(void)
0x18001fdbd  nop
0x18001fdbe  mov     rcx, [rbx+58h]
0x18001fdc2  mov     dword ptr [rcx+0Ch], 0
0x18001fdc9  call    ?Next@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAPEAUtagLOG_OUTPUT_STACK@@XZ; CPtrList<tagLOG_OUTPUT_STACK *>::Next(void)
0x18001fdce  mov     rdi, rax
0x18001fdd1  test    rax, rax
0x18001fdd4  jz      short loc_18001FE0A
0x18001fdd6  cmp     rax, r14
0x18001fdd9  jnz     short loc_18001FE04
0x18001fddb  mov     rdx, rax; lpMem
0x18001fdde  mov     rcx, rbx; this
0x18001fde1  call    ?DestroyStack@CLogManager@@IEAAHPEAUtagLOG_OUTPUT_STACK@@@Z; CLogManager::DestroyStack(tagLOG_OUTPUT_STACK *)
0x18001fde6  test    eax, eax
0x18001fde8  jz      short loc_18001FE04
0x18001fdea  mov     rdx, rdi
0x18001fded  mov     rcx, [rbx+58h]
0x18001fdf1  call    ?Remove@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHPEAUtagLOG_OUTPUT_STACK@@@Z; CPtrList<tagLOG_OUTPUT_STACK *>::Remove(tagLOG_OUTPUT_STACK *)
0x18001fdf6  mov     rdx, rdi
0x18001fdf9  mov     rcx, [rbx+60h]
0x18001fdfd  call    ?Remove@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHPEAUtagLOG_OUTPUT_STACK@@@Z; CPtrList<tagLOG_OUTPUT_STACK *>::Remove(tagLOG_OUTPUT_STACK *)
0x18001fe02  jmp     short loc_18001FE0A
0x18001fe04  mov     rcx, [rbx+58h]
0x18001fe08  jmp     short loc_18001FDC9
0x18001fe0a  lea     rcx, [rbx+28h]; this
0x18001fe0e  call    ?Release@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Release(void)
0x18001fe13  mov     eax, 1
0x18001fe18  add     rsp, 28h
0x18001fe1c  pop     r14
0x18001fe1e  pop     rdi
0x18001fe1f  pop     rsi
0x18001fe20  pop     rbx
0x18001fe21  retn
0x180029409  push    rbp
0x18002940b  sub     rsp, 20h
0x18002940f  mov     rbp, rdx
0x180029412  mov     rcx, [rbp+50h]
0x180029416  add     rcx, 28h ; '('; this
0x18002941a  add     rsp, 20h
0x18002941e  pop     rbp
0x18002941f  jmp     ?Release@CMutualExclusionObject@@QEAAXXZ; CMutualExclusionObject::Release(void)
```
