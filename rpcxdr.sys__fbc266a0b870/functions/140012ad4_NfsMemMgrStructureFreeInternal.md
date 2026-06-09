# NfsMemMgrStructureFreeInternal

- ea: `0x140012ad4`
- end: `0x140012bb4`
- name: `NfsMemMgrStructureFreeInternal`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400129c4`
- `0x140012a60`

## callees

- `0x140012684`
- `0x140012ad4`
- `0x1400151b0`
- `0x140015680`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012b95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b95`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012b81`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012b81`

## pseudocode

```c
__int64 __fastcall NfsMemMgrStructureFreeInternal(__int64 a1, _WORD *a2)
{
  int v4; // ecx
  unsigned int v5; // esi
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _WORD *); // rax

  v4 = *(_DWORD *)(a1 + 152);
  if ( (v4 & 1) != 0 || *(_DWORD *)(a1 + 40) == *(_DWORD *)a2 && ((v4 & 8) != 0 || a2[4] == *(_WORD *)(a1 + 156)) )
  {
    v5 = 0;
    NfsPolMgrpResourceDeallocateInternal(a1);
    v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(a1 + 184);
    if ( v6 )
      v5 = v6(*(_QWORD *)(a1 + 168), *(unsigned int *)(a1 + 40), *(unsigned __int16 *)(a1 + 156), a2);
    NfsMemMgrAllocationPoison(
      *(unsigned int *)(a1 + 40),
      a2,
      *(unsigned __int16 *)(a1 + 156),
      *(unsigned int *)(a1 + 220),
      *(_DWORD *)(a1 + 228));
    if ( (*(_DWORD *)(a1 + 384) & 1) != 0 )
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 288), a2);
    else
      ExFreePoolWithTag(a2, *(_DWORD *)(a1 + 40));
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v5;
}

```

## disassembly

```asm
0x140012ad4  mov     [rsp+arg_0], rbx
0x140012ad9  mov     [rsp+arg_8], rsi
0x140012ade  push    rdi
0x140012adf  sub     rsp, 30h
0x140012ae3  mov     rbx, rcx
0x140012ae6  mov     rdi, rdx
0x140012ae9  mov     ecx, [rcx+98h]
0x140012aef  test    cl, 1
0x140012af2  jnz     short loc_140012B17
0x140012af4  mov     eax, [rdx]
0x140012af6  cmp     [rbx+28h], eax
0x140012af9  jnz     short loc_140012B0D
0x140012afb  test    cl, 8
0x140012afe  jnz     short loc_140012B17
0x140012b00  movzx   eax, word ptr [rbx+9Ch]
0x140012b07  cmp     [rdx+8], ax
0x140012b0b  jz      short loc_140012B17
0x140012b0d  mov     esi, 0C000000Dh
0x140012b12  jmp     loc_140012BA1
0x140012b17  mov     rcx, rbx
0x140012b1a  xor     esi, esi
0x140012b1c  call    NfsPolMgrpResourceDeallocateInternal
0x140012b21  mov     rax, [rbx+0B8h]
0x140012b28  test    rax, rax
0x140012b2b  jz      short loc_140012B49
0x140012b2d  movzx   r8d, word ptr [rbx+9Ch]
0x140012b35  mov     r9, rdi
0x140012b38  mov     edx, [rbx+28h]
0x140012b3b  mov     rcx, [rbx+0A8h]
0x140012b42  call    _guard_dispatch_icall
0x140012b47  mov     esi, eax
0x140012b49  mov     eax, [rbx+0E4h]
0x140012b4f  mov     rdx, rdi
0x140012b52  movzx   r8d, word ptr [rbx+9Ch]
0x140012b5a  mov     r9d, [rbx+0DCh]
0x140012b61  mov     ecx, [rbx+28h]
0x140012b64  mov     [rsp+38h+var_18], eax
0x140012b68  call    NfsMemMgrAllocationPoison
0x140012b6d  mov     eax, [rbx+180h]
0x140012b73  test    al, 1
0x140012b75  jz      short loc_140012B8F
0x140012b77  lea     rcx, [rbx+120h]; Lookaside
0x140012b7e  mov     rdx, rdi; Entry
0x140012b81  call    cs:__imp_ExFreeToLookasideListEx
0x140012b88  nop     dword ptr [rax+rax+00h]
0x140012b8d  jmp     short loc_140012BA1
0x140012b8f  mov     edx, [rbx+28h]; Tag
0x140012b92  mov     rcx, rdi; P
0x140012b95  call    cs:__imp_ExFreePoolWithTag
0x140012b9c  nop     dword ptr [rax+rax+00h]
0x140012ba1  mov     rbx, [rsp+38h+arg_0]
0x140012ba6  mov     eax, esi
0x140012ba8  mov     rsi, [rsp+38h+arg_8]
0x140012bad  add     rsp, 30h
0x140012bb1  pop     rdi
0x140012bb2  retn
```
