# CreateSetupClnClassFactory(_GUID const &,_GUID const &,void * *)

- ea: `0x1800048f0`
- end: `0x180004991`
- name: `?CreateSetupClnClassFactory@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180003040`

## callees

- `0x1800019e4`
- `0x180003b30`
- `0x1800048f0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CreateSetupClnClassFactory(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  CSetupClnClassFactory *v7; // rax
  CSetupClnClassFactory *v8; // rbx
  unsigned int v9; // edi
  __int64 (__fastcall *v10)(CSetupClnClassFactory *, const struct _GUID *, void **); // rax

  if ( !a3 )
    return 2147942487LL;
  v7 = (CSetupClnClassFactory *)operator new(0x20u);
  if ( v7 )
    v8 = CSetupClnClassFactory::CSetupClnClassFactory(v7);
  else
    v8 = 0;
  if ( v8 )
  {
    v10 = **(__int64 (__fastcall ***)(CSetupClnClassFactory *, const struct _GUID *, void **))v8;
    *(struct _GUID *)((char *)v8 + 12) = *a1;
    v9 = v10(v8, a2, a3);
    (*(void (__fastcall **)(CSetupClnClassFactory *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x1800048f0  mov     [rsp+arg_0], rbx
0x1800048f5  mov     [rsp+arg_8], rbp
0x1800048fa  push    rsi
0x1800048fb  push    rdi
0x1800048fc  push    r14
0x1800048fe  sub     rsp, 20h
0x180004902  mov     rsi, r8
0x180004905  mov     rbp, rdx
0x180004908  mov     r14, rcx
0x18000490b  test    r8, r8
0x18000490e  jnz     short loc_180004917
0x180004910  mov     eax, 80070057h
0x180004915  jmp     short loc_18000497E
0x180004917  mov     ecx, 20h ; ' '; Size
0x18000491c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004921  mov     [rsp+38h+arg_10], rax
0x180004926  test    rax, rax
0x180004929  jz      short loc_180004938
0x18000492b  mov     rcx, rax; this
0x18000492e  call    ??0CSetupClnClassFactory@@QEAA@XZ; CSetupClnClassFactory::CSetupClnClassFactory(void)
0x180004933  mov     rbx, rax
0x180004936  jmp     short loc_18000493A
0x180004938  xor     ebx, ebx
0x18000493a  xor     edi, edi
0x18000493c  mov     eax, 8007000Eh
0x180004941  test    rbx, rbx
0x180004944  cmovz   edi, eax
0x180004947  jz      short loc_18000497C
0x180004949  mov     rax, [rbx]
0x18000494c  mov     r8, rsi
0x18000494f  movups  xmm0, xmmword ptr [r14]
0x180004953  mov     rdx, rbp
0x180004956  mov     rcx, rbx
0x180004959  mov     rax, [rax]
0x18000495c  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180004961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004966  mov     edi, eax
0x180004968  test    rbx, rbx
0x18000496b  jz      short loc_18000497C
0x18000496d  mov     rax, [rbx]
0x180004970  mov     rcx, rbx
0x180004973  mov     rax, [rax+10h]
0x180004977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497c  mov     eax, edi
0x18000497e  mov     rbx, [rsp+38h+arg_0]
0x180004983  mov     rbp, [rsp+38h+arg_8]
0x180004988  add     rsp, 20h
0x18000498c  pop     r14
0x18000498e  pop     rdi
0x18000498f  pop     rsi
0x180004990  retn
```
