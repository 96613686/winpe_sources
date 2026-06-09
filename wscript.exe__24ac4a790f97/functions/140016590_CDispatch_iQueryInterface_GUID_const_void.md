# CDispatch::iQueryInterface(_GUID const &,void * *)

- ea: `0x140016590`
- end: `0x1400165d5`
- name: `?iQueryInterface@CDispatch@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `69`
- prototype: `__int64 __fastcall(CDispatch *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140013eb0`
- `0x140013f90`
- `0x140014020`
- `0x1400141d0`

## callees

- `0x140016590`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CDispatch::iQueryInterface(CDispatch *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDispatch.Data4 )
  {
    *a3 = (void *)*((_QWORD *)this + 2);
    (*(void (__fastcall **)(CDispatch *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x140016590  sub     rsp, 28h
0x140016594  mov     rax, [rdx]
0x140016597  cmp     rax, qword ptr cs:IID_IDispatch.Data1
0x14001659e  jnz     short loc_1400165C4
0x1400165a0  mov     rax, [rdx+8]
0x1400165a4  cmp     rax, qword ptr cs:IID_IDispatch.Data4
0x1400165ab  jnz     short loc_1400165C4
0x1400165ad  mov     rax, [rcx+10h]
0x1400165b1  mov     [r8], rax
0x1400165b4  mov     rax, [rcx]
0x1400165b7  mov     rax, [rax+18h]
0x1400165bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165c0  xor     eax, eax
0x1400165c2  jmp     short loc_1400165D0
0x1400165c4  mov     qword ptr [r8], 0
0x1400165cb  mov     eax, 80004002h
0x1400165d0  add     rsp, 28h
0x1400165d4  retn
```
