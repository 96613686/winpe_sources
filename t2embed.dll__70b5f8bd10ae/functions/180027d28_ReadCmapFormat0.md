# ReadCmapFormat0

- ea: `0x180027d28`
- end: `0x180027dd1`
- name: `ReadCmapFormat0`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f298`

## callees

- `0x180015190`
- `0x1800164e0`
- `0x180017480`
- `0x180027d28`

## pseudocode

```c
__int64 __fastcall ReadCmapFormat0(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, _WORD *a5)
{
  unsigned int CmapSubtable; // esi
  _WORD *v7; // rbx
  __int64 result; // rax
  _DWORD v9[14]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 v10; // [rsp+88h] [rbp+10h] BYREF

  v10 = 0;
  v9[0] = 0;
  CmapSubtable = FindCmapSubtable(a1, 3, a3, a4);
  if ( !CmapSubtable )
    return 1006;
  v7 = a5;
  result = ReadGeneric(a1, (__int64)a5, 6u, (unsigned __int8 *)CMAP_FORMAT0_CONTROL, CmapSubtable, &v10);
  if ( (_WORD)result )
    return result;
  if ( *v7 )
    return 1006;
  else
    return ReadGenericRepeat(a1, (__int64)(v7 + 3), (unsigned __int8 *)BYTE_CONTROL, CmapSubtable + v10, v9, 0x100u, 1u);
}

```

## disassembly

```asm
0x180027d28  mov     rax, rsp
0x180027d2b  mov     [rax+10h], dx
0x180027d2f  push    rbx
0x180027d30  push    rbp
0x180027d31  push    rsi
0x180027d32  push    rdi
0x180027d33  sub     rsp, 58h
0x180027d37  xor     ebp, ebp
0x180027d39  mov     rdi, rcx
0x180027d3c  mov     [rax+10h], bp
0x180027d40  mov     [rax-38h], ebp
0x180027d43  lea     edx, [rbp+3]
0x180027d46  call    FindCmapSubtable
0x180027d4b  mov     esi, eax
0x180027d4d  test    eax, eax
0x180027d4f  jz      short loc_180027DC3
0x180027d51  mov     rbx, [rsp+78h+arg_20]
0x180027d59  lea     rax, [rsp+78h+arg_8]
0x180027d61  mov     [rsp+78h+var_50], rax
0x180027d66  lea     r8d, [rbp+6]
0x180027d6a  mov     rdx, rbx
0x180027d6d  mov     dword ptr [rsp+78h+var_58], esi
0x180027d71  lea     r9, CMAP_FORMAT0_CONTROL
0x180027d78  mov     rcx, rdi
0x180027d7b  call    ReadGeneric
0x180027d80  test    ax, ax
0x180027d83  jnz     short loc_180027DC8
0x180027d85  cmp     [rbx], bp
0x180027d88  jnz     short loc_180027DC3
0x180027d8a  movzx   r9d, [rsp+78h+arg_8]
0x180027d93  lea     rax, [rsp+78h+var_38]
0x180027d98  mov     [rsp+78h+var_48], 1
0x180027d9f  lea     rdx, [rbx+6]
0x180027da3  add     r9d, esi
0x180027da6  mov     word ptr [rsp+78h+var_50], 100h
0x180027dad  lea     r8, BYTE_CONTROL
0x180027db4  mov     [rsp+78h+var_58], rax
0x180027db9  mov     rcx, rdi
0x180027dbc  call    ReadGenericRepeat
0x180027dc1  jmp     short loc_180027DC8
0x180027dc3  mov     eax, 3EEh
0x180027dc8  add     rsp, 58h
0x180027dcc  pop     rdi
0x180027dcd  pop     rsi
0x180027dce  pop     rbp
0x180027dcf  pop     rbx
0x180027dd0  retn
```
