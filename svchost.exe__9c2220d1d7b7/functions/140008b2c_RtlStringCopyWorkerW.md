# RtlStringCopyWorkerW

- ea: `0x140008b2c`
- end: `0x140008b7d`
- name: `RtlStringCopyWorkerW`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008858`

## callees

- `0x140008b2c`

## pseudocode

```c
__int64 __fastcall RtlStringCopyWorkerW(_WORD *a1, __int64 a2, __int64 a3, _WORD *a4)
{
  __int64 v4; // r8
  __int64 i; // rax
  _WORD *v6; // rdx
  __int64 result; // rax

  v4 = a2;
  for ( i = 2147483646; v4; --v4 )
  {
    if ( !i )
      break;
    if ( !*a4 )
      break;
    *a1++ = *a4++;
    --i;
  }
  v6 = a1 - 1;
  result = v4 == 0 ? 0x80000005 : 0;
  if ( v4 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x140008b2c  xor     r10d, r10d
0x140008b2f  mov     r8, rdx
0x140008b32  mov     eax, 7FFFFFFEh
0x140008b37  test    rdx, rdx
0x140008b3a  jz      short loc_140008B5E
0x140008b3c  test    rax, rax
0x140008b3f  jz      short loc_140008B5E
0x140008b41  movzx   edx, word ptr [r9]
0x140008b45  test    dx, dx
0x140008b48  jz      short loc_140008B5E
0x140008b4a  mov     [rcx], dx
0x140008b4d  add     r9, 2
0x140008b51  add     rcx, 2
0x140008b55  dec     rax
0x140008b58  sub     r8, 1
0x140008b5c  jnz     short loc_140008B3C
0x140008b5e  mov     rax, r8
0x140008b61  lea     rdx, [rcx-2]
0x140008b65  neg     rax
0x140008b68  sbb     eax, eax
0x140008b6a  not     eax
0x140008b6c  and     eax, 80000005h
0x140008b71  test    r8, r8
0x140008b74  cmovnz  rdx, rcx
0x140008b78  mov     [rdx], r10w
0x140008b7c  retn
```
