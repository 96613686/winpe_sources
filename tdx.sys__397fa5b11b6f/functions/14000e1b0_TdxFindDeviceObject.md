# TdxFindDeviceObject

- ea: `0x14000e1b0`
- end: `0x14000e222`
- name: `TdxFindDeviceObject`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000db08`
- `0x14000eba0`

## callees

- `0x14000e1b0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e1f8`
- `ntoskrnl!RtlCompareMemory` at `0x14000e1f8`

## pseudocode

```c
__int64 *__fastcall TdxFindDeviceObject(__int64 **a1, __int64 a2, int a3)
{
  __int64 *i; // rbx
  __int64 Source2; // [rsp+38h] [rbp+10h] BYREF

  Source2 = a2;
  for ( i = *a1; i != (__int64 *)a1; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 5) == a3 && (i[38] & 8) == 0 && RtlCompareMemory(i + 3, &Source2, 8u) == 8 )
      return i;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e1b0  mov     [rsp+arg_0], rbx
0x14000e1b5  mov     [rsp+arg_10], rsi
0x14000e1ba  mov     [rsp+Source2], rdx
0x14000e1bf  push    rdi
0x14000e1c0  sub     rsp, 20h
0x14000e1c4  mov     rbx, [rcx]
0x14000e1c7  mov     esi, r8d
0x14000e1ca  mov     rdi, rcx
0x14000e1cd  nop     dword ptr [rax]
0x14000e1d0  cmp     rbx, rdi
0x14000e1d3  jz      short loc_14000E21E
0x14000e1d5  cmp     [rbx+14h], esi
0x14000e1d8  jnz     short loc_14000E1E4
0x14000e1da  mov     eax, [rbx+130h]
0x14000e1e0  test    al, 8
0x14000e1e2  jz      short loc_14000E1E9
0x14000e1e4  mov     rbx, [rbx]
0x14000e1e7  jmp     short loc_14000E1D0
0x14000e1e9  lea     rcx, [rbx+18h]; Source1
0x14000e1ed  mov     r8d, 8; Length
0x14000e1f3  lea     rdx, [rsp+28h+Source2]; Source2
0x14000e1f8  call    cs:__imp_RtlCompareMemory
0x14000e1ff  nop     dword ptr [rax+rax+00h]
0x14000e204  cmp     rax, 8
0x14000e208  jnz     short loc_14000E1E4
0x14000e20a  mov     rax, rbx
0x14000e20d  mov     rbx, [rsp+28h+arg_0]
0x14000e212  mov     rsi, [rsp+28h+arg_10]
0x14000e217  add     rsp, 20h
0x14000e21b  pop     rdi
0x14000e21c  retn
0x14000e21e  xor     eax, eax
0x14000e220  jmp     short loc_14000E20D
```
