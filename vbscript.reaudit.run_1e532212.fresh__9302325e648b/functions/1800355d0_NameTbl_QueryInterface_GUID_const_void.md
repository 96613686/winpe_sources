# NameTbl::QueryInterface(_GUID const &,void * *)

- ea: `0x1800355d0`
- end: `0x18003568c`
- name: `?QueryInterface@NameTbl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180035530`

## callees

- `0x1800355d0`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180035629`
- `KERNEL32!GetCurrentThreadId` at `0x180035629`

## pseudocode

```c
__int64 __fastcall NameTbl::QueryInterface(NameTbl *this, const struct _GUID *a2, void **a3)
{
  __int64 v6; // rax
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax

  if ( !a3 )
    return 2147500035LL;
  v6 = *(_QWORD *)&IID_IUnknown.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 )
    v6 = *(_QWORD *)IID_IUnknown.Data4 - *(_QWORD *)a2->Data4;
  if ( !v6 )
    goto LABEL_5;
  v8 = *((_DWORD *)this + 8);
  if ( GetCurrentThreadId() != v8 )
    goto LABEL_14;
  if ( &IID_INameTbl == a2 )
    goto LABEL_5;
  v9 = *(_QWORD *)&IID_IDispatchEx.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IDispatchEx.Data1 == *(_QWORD *)&a2->Data1 )
    v9 = *(_QWORD *)IID_IDispatchEx.Data4 - *(_QWORD *)a2->Data4;
  if ( !v9 )
    goto LABEL_5;
  v10 = *(_QWORD *)&IID_IDispatch.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&IID_IDispatch.Data1 == *(_QWORD *)&a2->Data1 )
    v10 = *(_QWORD *)IID_IDispatch.Data4 - *(_QWORD *)a2->Data4;
  if ( v10 )
  {
LABEL_14:
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_5:
    *a3 = this;
    (*(void (__fastcall **)(NameTbl *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x1800355d0  push    rbx
0x1800355d2  push    rsi
0x1800355d3  push    rdi
0x1800355d4  push    r14
0x1800355d6  sub     rsp, 28h
0x1800355da  mov     r14, r8
0x1800355dd  mov     rdi, rdx
0x1800355e0  mov     rsi, rcx
0x1800355e3  test    r8, r8
0x1800355e6  jz      loc_180035685
0x1800355ec  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x1800355f3  sub     rax, [rdx]
0x1800355f6  jnz     short loc_180035603
0x1800355f8  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x1800355ff  sub     rax, [rdx+8]
0x180035603  test    rax, rax
0x180035606  jnz     short loc_180035626
0x180035608  mov     [r14], rsi
0x18003560b  mov     rcx, rsi
0x18003560e  mov     rax, [rsi]
0x180035611  mov     rax, [rax+8]
0x180035615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003561a  xor     eax, eax
0x18003561c  add     rsp, 28h
0x180035620  pop     r14
0x180035622  pop     rdi
0x180035623  pop     rsi
0x180035624  pop     rbx
0x180035625  retn
0x180035626  mov     ebx, [rcx+20h]
0x180035629  call    cs:__imp_GetCurrentThreadId
0x18003562f  cmp     eax, ebx
0x180035631  jnz     short loc_180035677
0x180035633  lea     rax, IID_INameTbl
0x18003563a  cmp     rax, rdi
0x18003563d  jz      short loc_180035608
0x18003563f  mov     rax, qword ptr cs:IID_IDispatchEx.Data1
0x180035646  sub     rax, [rdi]
0x180035649  jnz     short loc_180035656
0x18003564b  mov     rax, qword ptr cs:IID_IDispatchEx.Data4
0x180035652  sub     rax, [rdi+8]
0x180035656  test    rax, rax
0x180035659  jz      short loc_180035608
0x18003565b  mov     rax, qword ptr cs:IID_IDispatch.Data1
0x180035662  sub     rax, [rdi]
0x180035665  jnz     short loc_180035672
0x180035667  mov     rax, qword ptr cs:IID_IDispatch.Data4
0x18003566e  sub     rax, [rdi+8]
0x180035672  test    rax, rax
0x180035675  jz      short loc_180035608
0x180035677  mov     qword ptr [r14], 0
0x18003567e  mov     eax, 80004002h
0x180035683  jmp     short loc_18003561C
0x180035685  mov     eax, 80004003h
0x18003568a  jmp     short loc_18003561C
```
