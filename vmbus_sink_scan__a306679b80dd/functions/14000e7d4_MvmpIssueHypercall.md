# MvmpIssueHypercall

- ea: `0x14000e7d4`
- end: `0x14000e877`
- name: `MvmpIssueHypercall`
- size: `163`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aae0`
- `0x14000ada0`
- `0x14000dbc0`
- `0x14000e9f4`

## callees

- `0x14000e6ac`
- `0x14000e7d4`
- `0x140017190`

## pseudocode

```c
__int64 __fastcall MvmpIssueHypercall(__int64 a1, __int64 a2, unsigned __int16 a3, __int64 a4, char a5, __int64 a6)
{
  __int64 result; // rax
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD); // rax
  __int64 v9; // [rsp+30h] [rbp+8h]

  v9 = a3 | (a5 != 0 ? 0x10000 : 0) | (*(_BYTE *)(a1 + 185) != 0 ? 0x80000000 : 0);
  if ( *(_DWORD *)(a1 + 216) == 2 )
  {
    if ( a2 )
      result = MvmpIssueGhcbHypercall(a2, v9, a6);
    else
      result = ((__int64 (__fastcall *)(__int64, __int64, _QWORD))MvmpIssueIsolatedHypercallDirect)(v9, a6, 0);
  }
  else
  {
    v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a1 + 24);
    if ( !v8 )
      v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a1 + 16);
    result = v8(v9, a6, 0);
  }
  *(_WORD *)(a1 + 212) = result;
  return result;
}

```

## disassembly

```asm
0x14000e7d4  push    rbx
0x14000e7d6  sub     rsp, 20h
0x14000e7da  mov     al, [rcx+0B9h]
0x14000e7e0  mov     r10, rdx
0x14000e7e3  neg     al
0x14000e7e5  mov     dword ptr [rsp+28h+arg_0+4], 0
0x14000e7ed  mov     rbx, rcx
0x14000e7f0  sbb     r9d, r9d
0x14000e7f3  and     r9d, 80000000h
0x14000e7fa  neg     [rsp+28h+arg_20]
0x14000e7fe  sbb     eax, eax
0x14000e800  and     eax, 10000h
0x14000e805  or      r9d, eax
0x14000e808  movzx   eax, r8w
0x14000e80c  or      r9d, eax
0x14000e80f  cmp     dword ptr [rcx+0D8h], 2
0x14000e816  mov     dword ptr [rsp+28h+arg_0], r9d
0x14000e81b  jnz     short loc_14000E84A
0x14000e81d  test    rdx, rdx
0x14000e820  jz      short loc_14000E836
0x14000e822  mov     r8, [rsp+28h+arg_28]
0x14000e827  mov     rcx, r10
0x14000e82a  mov     rdx, [rsp+28h+arg_0]
0x14000e82f  call    MvmpIssueGhcbHypercall
0x14000e834  jmp     short loc_14000E869
0x14000e836  mov     rdx, [rsp+28h+arg_28]
0x14000e83b  xor     r8d, r8d
0x14000e83e  mov     rcx, [rsp+28h+arg_0]
0x14000e843  call    MvmpIssueIsolatedHypercallDirect
0x14000e848  jmp     short loc_14000E869
0x14000e84a  mov     rax, [rcx+18h]
0x14000e84e  xor     r8d, r8d
0x14000e851  mov     rdx, [rsp+28h+arg_28]
0x14000e856  test    rax, rax
0x14000e859  jnz     short loc_14000E85F
0x14000e85b  mov     rax, [rcx+10h]
0x14000e85f  mov     rcx, [rsp+28h+arg_0]
0x14000e864  call    _guard_dispatch_icall
0x14000e869  mov     [rbx+0D4h], ax
0x14000e870  add     rsp, 20h
0x14000e874  pop     rbx
0x14000e875  retn
```
