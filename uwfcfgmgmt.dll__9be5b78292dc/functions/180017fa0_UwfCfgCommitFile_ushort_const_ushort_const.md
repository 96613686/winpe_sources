# UwfCfgCommitFile(ushort const *,ushort const *)

- ea: `0x180017fa0`
- end: `0x18001806f`
- name: `?UwfCfgCommitFile@@YAJPEBG0@Z`
- size: `207`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e320`
- `0x18000f364`
- `0x180014d80`
- `0x180017fa0`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180018047`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180018047`

## pseudocode

```c
__int64 __fastcall UwfCfgCommitFile(const unsigned __int16 *a1, wchar_t *a2)
{
  __int64 v4; // rdi
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 v10; // [rsp+70h] [rbp+30h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v4 = 0;
  v10 = 0;
  v8 = 0;
  v11 = 0;
  v9 = 0;
  if ( a1 && a2 )
  {
    EnsureUwfFeatureState();
    LOBYTE(v6) = 1;
    v5 = anonymous_namespace_::uwfCfgInitialize(0, v6, &v10, &v8, a1, &v11);
    if ( v5 < 0 )
    {
      v4 = v10;
    }
    else
    {
      v5 = CUwfRegKey::QuerySzValue((HKEY *)(v11 + 16), L"DriveLetter", &v9);
      v4 = v10;
      if ( v5 >= 0 )
        v5 = CUwfManagement::CommitFile((CUwfManagement *)(v10 + 8), v9, a2);
      if ( v9 )
        operator delete[](v9);
    }
  }
  else
  {
    v5 = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v4, v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017fa0  mov     [rsp-18h+arg_8], rbx
0x180017fa5  push    rbp
0x180017fa6  push    rdi
0x180017fa7  push    r14
0x180017fa9  mov     rbp, rsp
0x180017fac  sub     rsp, 40h
0x180017fb0  mov     r14, rdx
0x180017fb3  mov     rbx, rcx
0x180017fb6  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x180017fbb  xor     edi, edi
0x180017fbd  mov     [rbp+arg_10], rdi
0x180017fc1  mov     [rbp+var_10], rdi
0x180017fc5  mov     [rbp+arg_18], rdi
0x180017fc9  mov     [rbp+arg_0], rdi
0x180017fcd  test    rbx, rbx
0x180017fd0  jnz     short loc_180017FD9
0x180017fd2  mov     ebx, 80070057h
0x180017fd7  jmp     short loc_180018053
0x180017fd9  test    r14, r14
0x180017fdc  jz      short loc_180017FD2
0x180017fde  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x180017fe3  lea     rax, [rbp+arg_18]
0x180017fe7  mov     dl, 1
0x180017fe9  mov     [rsp+40h+var_18], rax
0x180017fee  lea     r9, [rbp+var_10]
0x180017ff2  lea     r8, [rbp+arg_10]
0x180017ff6  mov     [rsp+40h+var_20], rbx
0x180017ffb  xor     ecx, ecx
0x180017ffd  call    _anonymous_namespace___uwfCfgInitialize
0x180018002  mov     ebx, eax
0x180018004  test    eax, eax
0x180018006  js      short loc_18001804F
0x180018008  mov     rcx, [rbp+arg_18]
0x18001800c  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x180018010  add     rcx, 10h; this
0x180018014  lea     rdx, aDriveletter; "DriveLetter"
0x18001801b  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180018020  mov     ebx, eax
0x180018022  mov     rdi, [rbp+arg_10]
0x180018026  test    eax, eax
0x180018028  js      short loc_18001803C
0x18001802a  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x18001802e  lea     rcx, [rdi+8]; this
0x180018032  mov     r8, r14; unsigned __int16 *
0x180018035  call    ?CommitFile@CUwfManagement@@QEAAJPEBG0@Z; CUwfManagement::CommitFile(ushort const *,ushort const *)
0x18001803a  mov     ebx, eax
0x18001803c  cmp     [rbp+arg_0], 0
0x180018041  jz      short loc_180018053
0x180018043  mov     rcx, [rbp+arg_0]
0x180018047  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001804d  jmp     short loc_180018053
0x18001804f  mov     rdi, [rbp+arg_10]
0x180018053  mov     rdx, [rbp+var_10]
0x180018057  mov     rcx, rdi
0x18001805a  call    _anonymous_namespace___uwfCfgFinalize
0x18001805f  mov     eax, ebx
0x180018061  mov     rbx, [rsp+40h+arg_8]
0x180018066  add     rsp, 40h
0x18001806a  pop     r14
0x18001806c  pop     rdi
0x18001806d  pop     rbp
0x18001806e  retn
```
