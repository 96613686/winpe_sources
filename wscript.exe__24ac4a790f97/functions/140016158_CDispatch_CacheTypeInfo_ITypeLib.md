# CDispatch::CacheTypeInfo(ITypeLib *)

- ea: `0x140016158`
- end: `0x14001620b`
- name: `?CacheTypeInfo@CDispatch@@QEAAJPEAUITypeLib@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(CDispatch *__hidden this, struct ITypeLib *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000eedc`
- `0x140016350`

## callees

- `0x140016158`
- `0x140018010`

## pseudocode

```c
__int64 __fastcall CDispatch::CacheTypeInfo(CDispatch *this, struct ITypeLib *a2)
{
  struct ITypeLibVtbl *lpVtbl; // rax
  __int64 result; // rax
  int v5; // edi
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v7 = 0;
  result = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, __int64 *))lpVtbl->GetTypeInfoOfGuid)(
             a2,
             *(_QWORD *)(*((_QWORD *)this + 5) + 40LL),
             &v7);
  if ( (int)result >= 0 )
  {
    v6 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v7 + 64LL))(v7, 0xFFFFFFFFLL, &v6);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 112LL))(
             v7,
             v6,
             *((_QWORD *)this + 5) + 56LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v5 >= 0 )
        *((_BYTE *)this + 48) = 1;
    }
    else
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x140016158  mov     [rsp+arg_10], rbx
0x14001615d  push    rdi
0x14001615e  sub     rsp, 20h
0x140016162  mov     rax, [rdx]
0x140016165  lea     r8, [rsp+28h+arg_8]
0x14001616a  mov     r9, rdx
0x14001616d  mov     [rsp+28h+arg_8], 0
0x140016176  mov     rdx, [rcx+28h]
0x14001617a  mov     rbx, rcx
0x14001617d  mov     rcx, r9
0x140016180  mov     rax, [rax+30h]
0x140016184  mov     rdx, [rdx+28h]
0x140016188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001618d  test    eax, eax
0x14001618f  js      short loc_140016200
0x140016191  mov     rcx, [rsp+28h+arg_8]
0x140016196  lea     r8, [rsp+28h+arg_0]
0x14001619b  mov     [rsp+28h+arg_0], 0
0x1400161a3  or      edx, 0FFFFFFFFh
0x1400161a6  mov     rax, [rcx]
0x1400161a9  mov     rax, [rax+40h]
0x1400161ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161b2  mov     rcx, [rsp+28h+arg_8]
0x1400161b7  mov     edi, eax
0x1400161b9  test    eax, eax
0x1400161bb  jns     short loc_1400161CB
0x1400161bd  mov     rdx, [rcx]
0x1400161c0  mov     rax, [rdx+10h]
0x1400161c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161c9  jmp     short loc_1400161FE
0x1400161cb  mov     rax, [rcx]
0x1400161ce  mov     r8, [rbx+28h]
0x1400161d2  mov     edx, [rsp+28h+arg_0]
0x1400161d6  add     r8, 38h ; '8'
0x1400161da  mov     rax, [rax+70h]
0x1400161de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161e3  mov     rcx, [rsp+28h+arg_8]
0x1400161e8  mov     edi, eax
0x1400161ea  mov     rdx, [rcx]
0x1400161ed  mov     rax, [rdx+10h]
0x1400161f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400161f6  test    edi, edi
0x1400161f8  js      short loc_1400161FE
0x1400161fa  mov     byte ptr [rbx+30h], 1
0x1400161fe  mov     eax, edi
0x140016200  mov     rbx, [rsp+28h+arg_10]
0x140016205  add     rsp, 20h
0x140016209  pop     rdi
0x14001620a  retn
```
