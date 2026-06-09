# UwfCfgCommitFileDeletion(ushort const *,ushort const *)

- ea: `0x180018080`
- end: `0x18001818f`
- name: `?UwfCfgCommitFileDeletion@@YAJPEBG0@Z`
- size: `271`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e320`
- `0x18000f364`
- `0x1800151b0`
- `0x180018080`
- `0x18001aa08`
- `0x18001aa94`
- `0x18001aad4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180018156`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180018164`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180018156`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180018164`

## pseudocode

```c
__int64 __fastcall UwfCfgCommitFileDeletion(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rsi
  unsigned __int16 *v5; // rdi
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r12
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 *v12; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v13; // [rsp+80h] [rbp+40h] BYREF
  __int64 v14; // [rsp+88h] [rbp+48h] BYREF

  anonymous_namespace_::uwfCfgApiBreakpoint();
  v4 = 0;
  v5 = 0;
  v14 = 0;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  if ( a1 && a2 )
  {
    EnsureUwfFeatureState();
    LOBYTE(v7) = 1;
    v6 = anonymous_namespace_::uwfCfgInitialize(0, v7, &v14, &v11, a1, &v10);
    if ( v6 < 0 )
    {
      v4 = v14;
    }
    else
    {
      v8 = v10;
      v6 = CUwfRegKey::QuerySzValue((HKEY *)(v10 + 16), L"DriveLetter", &v12);
      v4 = v14;
      if ( v6 >= 0 )
      {
        v6 = CUwfRegKey::QuerySzValue((HKEY *)(v8 + 16), L"VolumeName", &v13);
        v5 = v13;
        if ( v6 >= 0 )
          v6 = CUwfManagement::CommitFileDeletion((HKEY *)(v4 + 8), v12, v13, a2);
      }
      if ( v12 )
        operator delete[](v12);
      if ( v5 )
        operator delete[](v5);
    }
  }
  else
  {
    v6 = -2147024809;
  }
  anonymous_namespace_::uwfCfgFinalize(v4, v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018080  mov     [rsp-28h+arg_8], rbx
0x180018085  push    rbp
0x180018086  push    rsi
0x180018087  push    rdi
0x180018088  push    r12
0x18001808a  push    r15
0x18001808c  mov     rbp, rsp
0x18001808f  sub     rsp, 40h
0x180018093  mov     r15, rdx
0x180018096  mov     rbx, rcx
0x180018099  call    _anonymous_namespace___uwfCfgApiBreakpoint
0x18001809e  xor     esi, esi
0x1800180a0  xor     edi, edi
0x1800180a2  mov     [rbp+arg_18], rsi
0x1800180a6  mov     [rbp+var_8], rsi
0x1800180aa  mov     [rbp+var_10], rsi
0x1800180ae  mov     [rbp+arg_0], rsi
0x1800180b2  mov     [rbp+arg_10], rdi
0x1800180b6  test    rbx, rbx
0x1800180b9  jnz     short loc_1800180C5
0x1800180bb  mov     ebx, 80070057h
0x1800180c0  jmp     loc_180018170
0x1800180c5  test    r15, r15
0x1800180c8  jz      short loc_1800180BB
0x1800180ca  call    ?EnsureUwfFeatureState@@YAJ_N@Z; EnsureUwfFeatureState(bool)
0x1800180cf  lea     rax, [rbp+var_10]
0x1800180d3  mov     dl, 1
0x1800180d5  mov     [rsp+40h+var_18], rax
0x1800180da  lea     r9, [rbp+var_8]
0x1800180de  lea     r8, [rbp+arg_18]
0x1800180e2  mov     [rsp+40h+var_20], rbx
0x1800180e7  xor     ecx, ecx
0x1800180e9  call    _anonymous_namespace___uwfCfgInitialize
0x1800180ee  mov     ebx, eax
0x1800180f0  test    eax, eax
0x1800180f2  js      short loc_18001816C
0x1800180f4  mov     r12, [rbp+var_10]
0x1800180f8  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1800180fc  lea     rdx, aDriveletter; "DriveLetter"
0x180018103  lea     rcx, [r12+10h]; this
0x180018108  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18001810d  mov     ebx, eax
0x18001810f  mov     rsi, [rbp+arg_18]
0x180018113  test    eax, eax
0x180018115  js      short loc_18001814B
0x180018117  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18001811b  lea     rdx, aVolumename; "VolumeName"
0x180018122  lea     rcx, [r12+10h]; this
0x180018127  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x18001812c  mov     ebx, eax
0x18001812e  mov     rdi, [rbp+arg_10]
0x180018132  test    eax, eax
0x180018134  js      short loc_18001814B
0x180018136  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x18001813a  lea     rcx, [rsi+8]; this
0x18001813e  mov     r9, r15; unsigned __int16 *
0x180018141  mov     r8, rdi; unsigned __int16 *
0x180018144  call    ?CommitFileDeletion@CUwfManagement@@QEAAJPEBG00@Z; CUwfManagement::CommitFileDeletion(ushort const *,ushort const *,ushort const *)
0x180018149  mov     ebx, eax
0x18001814b  cmp     [rbp+arg_0], 0
0x180018150  jz      short loc_18001815C
0x180018152  mov     rcx, [rbp+arg_0]
0x180018156  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001815c  test    rdi, rdi
0x18001815f  jz      short loc_180018170
0x180018161  mov     rcx, rdi
0x180018164  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001816a  jmp     short loc_180018170
0x18001816c  mov     rsi, [rbp+arg_18]
0x180018170  mov     rdx, [rbp+var_8]
0x180018174  mov     rcx, rsi
0x180018177  call    _anonymous_namespace___uwfCfgFinalize
0x18001817c  mov     eax, ebx
0x18001817e  mov     rbx, [rsp+40h+arg_8]
0x180018183  add     rsp, 40h
0x180018187  pop     r15
0x180018189  pop     r12
0x18001818b  pop     rdi
0x18001818c  pop     rsi
0x18001818d  pop     rbp
0x18001818e  retn
```
