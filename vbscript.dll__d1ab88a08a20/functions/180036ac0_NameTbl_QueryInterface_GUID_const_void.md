# NameTbl::QueryInterface(_GUID const &,void * *)

- ea: `0x180036ac0`
- end: `0x180036b83`
- name: `?QueryInterface@NameTbl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(NameTbl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180036a20`

## callees

- `0x180036ac0`
- `0x18007a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180036b1a`
- `KERNEL32!GetCurrentThreadId` at `0x180036b1a`

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
0x180036ac0  push    rbx
0x180036ac2  push    rsi
0x180036ac3  push    rdi
0x180036ac4  push    r14
0x180036ac6  sub     rsp, 28h
0x180036aca  mov     r14, r8
0x180036acd  mov     rdi, rdx
0x180036ad0  mov     rsi, rcx
0x180036ad3  test    r8, r8
0x180036ad6  jz      loc_180036B7C
0x180036adc  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180036ae3  sub     rax, [rdx]
0x180036ae6  jnz     short loc_180036AF3
0x180036ae8  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180036aef  sub     rax, [rdx+8]
0x180036af3  test    rax, rax
0x180036af6  jnz     short loc_180036B17
0x180036af8  mov     [r14], rsi
0x180036afb  mov     rcx, rsi
0x180036afe  mov     rax, [rsi]
0x180036b01  mov     rax, [rax+8]
0x180036b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b0a  xor     eax, eax
0x180036b0c  add     rsp, 28h
0x180036b10  pop     r14
0x180036b12  pop     rdi
0x180036b13  pop     rsi
0x180036b14  pop     rbx
0x180036b15  retn
0x180036b17  mov     ebx, [rcx+20h]
0x180036b1a  call    cs:__imp_GetCurrentThreadId
0x180036b21  nop     dword ptr [rax+rax+00h]
0x180036b26  cmp     eax, ebx
0x180036b28  jnz     short loc_180036B6E
0x180036b2a  lea     rax, IID_INameTbl
0x180036b31  cmp     rax, rdi
0x180036b34  jz      short loc_180036AF8
0x180036b36  mov     rax, qword ptr cs:IID_IDispatchEx.Data1
0x180036b3d  sub     rax, [rdi]
0x180036b40  jnz     short loc_180036B4D
0x180036b42  mov     rax, qword ptr cs:IID_IDispatchEx.Data4
0x180036b49  sub     rax, [rdi+8]
0x180036b4d  test    rax, rax
0x180036b50  jz      short loc_180036AF8
0x180036b52  mov     rax, qword ptr cs:IID_IDispatch.Data1
0x180036b59  sub     rax, [rdi]
0x180036b5c  jnz     short loc_180036B69
0x180036b5e  mov     rax, qword ptr cs:IID_IDispatch.Data4
0x180036b65  sub     rax, [rdi+8]
0x180036b69  test    rax, rax
0x180036b6c  jz      short loc_180036AF8
0x180036b6e  mov     qword ptr [r14], 0
0x180036b75  mov     eax, 80004002h
0x180036b7a  jmp     short loc_180036B0C
0x180036b7c  mov     eax, 80004003h
0x180036b81  jmp     short loc_180036B0C
```
