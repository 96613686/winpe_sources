# CDispatch::iQueryInterface(_GUID const &,void * *)

- ea: `0x180001be0`
- end: `0x180001c28`
- name: `?iQueryInterface@CDispatch@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CDispatch *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005eb0`
- `0x180005f30`
- `0x180005fd0`
- `0x180006060`
- `0x18000c5e0`

## callees

- `0x180001be0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CDispatch::iQueryInterface(CDispatch *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax

  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( v3 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
    *a3 = (void *)*((_QWORD *)this + 2);
    (*(void (__fastcall **)(CDispatch *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x180001be0  sub     rsp, 28h
0x180001be4  mov     rax, [rdx]
0x180001be7  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180001bee  jnz     short loc_180001BFB
0x180001bf0  mov     rax, [rdx+8]
0x180001bf4  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180001bfb  test    rax, rax
0x180001bfe  jnz     short loc_180001C1A
0x180001c00  mov     rax, [rcx+10h]
0x180001c04  mov     [r8], rax
0x180001c07  mov     rax, [rcx]
0x180001c0a  mov     rax, [rax+18h]
0x180001c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c13  xor     eax, eax
0x180001c15  add     rsp, 28h
0x180001c19  retn
0x180001c1a  mov     qword ptr [r8], 0
0x180001c21  mov     eax, 80004002h
0x180001c26  jmp     short loc_180001C15
```
