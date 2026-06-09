# TextLogDeleteCtlTag

- ea: `0x180016cac`
- end: `0x180016d01`
- name: `TextLogDeleteCtlTag`
- size: `85`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`
- `0x180016d08`
- `0x1800177e0`

## callees

- `0x18000f7f0`
- `0x180016cac`

## pseudocode

```c
__int64 __fastcall TextLogDeleteCtlTag(__int64 a1, int a2)
{
  __int64 v2; // r10
  unsigned int v3; // r8d
  __int64 i; // rdx

  v2 = *(_QWORD *)(a1 + 24) - 20LL * (unsigned int)(a2 + 1);
  v3 = *(_QWORD *)(a1 + 24) - (v2 + 20);
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    *(_BYTE *)(i + v2) = *(_BYTE *)(i + v2 + 20);
  return TextLogUpdateEof(a1, 4294967276LL);
}

```

## disassembly

```asm
0x180016cac  sub     rsp, 38h
0x180016cb0  mov     r8, [rcx+18h]
0x180016cb4  lea     eax, [rdx+1]
0x180016cb7  lea     rax, [rax+rax*4]
0x180016cbb  shl     rax, 2
0x180016cbf  mov     r10, r8
0x180016cc2  sub     r10, rax
0x180016cc5  lea     r11, [r10+14h]
0x180016cc9  sub     r8d, r11d
0x180016ccc  xor     edx, edx
0x180016cce  mov     [rsp+38h+var_18], edx
0x180016cd2  cmp     edx, r8d
0x180016cd5  jnb     short loc_180016CE3
0x180016cd7  mov     al, [rdx+r11]
0x180016cdb  mov     [rdx+r10], al
0x180016cdf  inc     edx
0x180016ce1  jmp     short loc_180016CCE
0x180016ce3  mov     edx, 0FFFFFFECh
0x180016ce8  call    TextLogUpdateEof
0x180016ced  mov     [rsp+38h+var_14], eax
0x180016cf1  jmp     short loc_180016CFC
0x180016cf3  mov     eax, 0Dh
0x180016cf8  mov     [rsp+38h+var_14], eax
0x180016cfc  add     rsp, 38h
0x180016d00  retn
```
