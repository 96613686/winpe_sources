# CSafeArray::operator=(CSafeArray &)

- ea: `0x18002cde0`
- end: `0x18002ce53`
- name: `??4CSafeArray@@QEAAAEAV0@AEAV0@@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180037c90`

## callees

- `0x1800056c0`
- `0x18002cde0`
- `0x18002ce60`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002ce27`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18002ce27`

## pseudocode

```c
__int64 __fastcall CSafeArray::operator=(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax

  CSafeArray::Empty((CSafeArray *)a1);
  *(_DWORD *)a1 = *(_DWORD *)a2;
  *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 4);
  *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
  *(_DWORD *)(a1 + 12) = *(_DWORD *)(a2 + 12);
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 20);
  v4 = SafeArrayCopy(*(SAFEARRAY **)(a2 + 32), (SAFEARRAY **)(a1 + 32));
  if ( v4 == -2147024882 )
    _ThrowMemoryException_();
  if ( v4 )
    *(_DWORD *)(a1 + 12) = 1;
  return a1;
}

```

## disassembly

```asm
0x18002cde0  mov     [rsp+arg_0], rbx
0x18002cde5  push    rdi
0x18002cde6  sub     rsp, 20h
0x18002cdea  mov     rbx, rdx
0x18002cded  mov     rdi, rcx
0x18002cdf0  call    ?Empty@CSafeArray@@QEAAXXZ; CSafeArray::Empty(void)
0x18002cdf5  mov     eax, [rbx]
0x18002cdf7  lea     rdx, [rdi+20h]; ppsaOut
0x18002cdfb  mov     [rdi], eax
0x18002cdfd  mov     eax, [rbx+4]
0x18002ce00  mov     [rdi+4], eax
0x18002ce03  mov     eax, [rbx+8]
0x18002ce06  mov     [rdi+8], eax
0x18002ce09  mov     eax, [rbx+0Ch]
0x18002ce0c  mov     [rdi+0Ch], eax
0x18002ce0f  mov     eax, [rbx+10h]
0x18002ce12  mov     [rdi+10h], eax
0x18002ce15  mov     rax, [rbx+18h]
0x18002ce19  mov     [rdi+18h], rax
0x18002ce1d  mov     eax, [rbx+14h]
0x18002ce20  mov     [rdi+14h], eax
0x18002ce23  mov     rcx, [rbx+20h]; psa
0x18002ce27  call    cs:__imp_SafeArrayCopy
0x18002ce2d  cmp     eax, 8007000Eh
0x18002ce32  jnz     short loc_18002CE3A
0x18002ce34  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x18002ce3a  test    eax, eax
0x18002ce3c  jz      short loc_18002CE45
0x18002ce3e  mov     dword ptr [rdi+0Ch], 1
0x18002ce45  mov     rbx, [rsp+28h+arg_0]
0x18002ce4a  mov     rax, rdi
0x18002ce4d  add     rsp, 20h
0x18002ce51  pop     rdi
0x18002ce52  retn
```
