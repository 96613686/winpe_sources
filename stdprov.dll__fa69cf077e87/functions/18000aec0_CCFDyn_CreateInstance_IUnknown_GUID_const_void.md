# CCFDyn::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000aec0`
- end: `0x18000af70`
- name: `?CreateInstance@CCFDyn@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `176`
- prototype: `__int64 __fastcall(CCFDyn *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000aec0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CCFDyn::CreateInstance(CCFDyn *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  __int64 v6; // rax
  __int64 v8; // rax
  __int64 v9; // rdi
  int v10; // ebx

  *a4 = 0;
  if ( a2 )
  {
    v6 = *(_QWORD *)&IID_IUnknown.Data1 - *(_QWORD *)&a3->Data1;
    if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a3->Data1 )
      v6 = *(_QWORD *)IID_IUnknown.Data4 - *(_QWORD *)a3->Data4;
    if ( v6 )
      return 2147746064LL;
  }
  v8 = (*(__int64 (__fastcall **)(CCFDyn *))(*(_QWORD *)this + 48LL))(this);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v9)(v9, a3, a4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v10 >= 0 )
    _InterlockedIncrement(&lObj);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000aec0  mov     [rsp+arg_0], rbx
0x18000aec5  mov     [rsp+arg_8], rsi
0x18000aeca  push    rdi
0x18000aecb  sub     rsp, 20h
0x18000aecf  mov     qword ptr [r9], 0
0x18000aed6  mov     rsi, r9
0x18000aed9  mov     rbx, r8
0x18000aedc  test    rdx, rdx
0x18000aedf  jz      short loc_18000AF04
0x18000aee1  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18000aee8  sub     rax, [r8]
0x18000aeeb  jnz     short loc_18000AEF8
0x18000aeed  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18000aef4  sub     rax, [r8+8]
0x18000aef8  test    rax, rax
0x18000aefb  jz      short loc_18000AF04
0x18000aefd  mov     eax, 80040110h
0x18000af02  jmp     short loc_18000AF60
0x18000af04  mov     rax, [rcx]
0x18000af07  mov     rax, [rax+30h]
0x18000af0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af10  mov     rdi, rax
0x18000af13  test    rax, rax
0x18000af16  jnz     short loc_18000AF1F
0x18000af18  mov     eax, 8007000Eh
0x18000af1d  jmp     short loc_18000AF60
0x18000af1f  mov     rax, [rax]
0x18000af22  mov     rcx, rdi
0x18000af25  mov     rax, [rax+8]
0x18000af29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2e  mov     rax, [rdi]
0x18000af31  mov     r8, rsi
0x18000af34  mov     rdx, rbx
0x18000af37  mov     rcx, rdi
0x18000af3a  mov     rax, [rax]
0x18000af3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af42  mov     rcx, [rdi]
0x18000af45  mov     ebx, eax
0x18000af47  mov     rax, [rcx+10h]
0x18000af4b  mov     rcx, rdi
0x18000af4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af53  test    ebx, ebx
0x18000af55  js      short loc_18000AF5E
0x18000af57  lock inc cs:?lObj@@3JA; long lObj
0x18000af5e  mov     eax, ebx
0x18000af60  mov     rbx, [rsp+28h+arg_0]
0x18000af65  mov     rsi, [rsp+28h+arg_8]
0x18000af6a  add     rsp, 20h
0x18000af6e  pop     rdi
0x18000af6f  retn
```
