# BasepSxsCreateResourceStream

- ea: `0x180004150`
- end: `0x1800041ba`
- name: `BasepSxsCreateResourceStream`
- size: `106`
- prototype: `__int64 __fastcall(__int128 **, _QWORD *, __int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c50`

## callees

- `0x180004150`

## pseudocode

```c
__int64 __fastcall BasepSxsCreateResourceStream(
        __int128 **a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int128 *v7; // rcx
  __int128 v8; // xmm0

  if ( !a2[3] )
    return 3221225738LL;
  if ( !a6 )
    return 3221225609LL;
  *(_QWORD *)(a7 + 40) = a5;
  *(_QWORD *)(a7 + 48) = a6;
  if ( a6 > 0x800000uLL )
    return 3222601762LL;
  *(_QWORD *)(a7 + 32) = a2[1];
  *(_QWORD *)(a7 + 24) = *a2;
  v7 = *a1;
  *(_WORD *)a7 = 257;
  v8 = *v7;
  *(_BYTE *)(a7 + 2) = 1;
  *(_OWORD *)(a7 + 8) = v8;
  return 0;
}

```

## disassembly

```asm
0x180004150  cmp     qword ptr [rdx+18h], 0
0x180004155  mov     r8, rdx
0x180004158  mov     rax, [rsp+arg_30]
0x18000415d  mov     r9, rcx
0x180004160  jz      short loc_1800041AD
0x180004162  mov     edx, [rsp+arg_28]
0x180004166  test    edx, edx
0x180004168  jz      short loc_1800041A6
0x18000416a  mov     rcx, [rsp+arg_20]
0x18000416f  mov     [rax+28h], rcx
0x180004173  mov     [rax+30h], rdx
0x180004177  cmp     rdx, 800000h
0x18000417e  ja      short loc_1800041B4
0x180004180  mov     rcx, [r8+8]
0x180004184  mov     [rax+20h], rcx
0x180004188  mov     rcx, [r8]
0x18000418b  mov     [rax+18h], rcx
0x18000418f  mov     rcx, [r9]
0x180004192  mov     word ptr [rax], 101h
0x180004197  movups  xmm0, xmmword ptr [rcx]
0x18000419a  mov     byte ptr [rax+2], 1
0x18000419e  movups  xmmword ptr [rax+8], xmm0
0x1800041a2  xor     eax, eax
0x1800041a4  retn
0x1800041a6  mov     eax, 0C0000089h
0x1800041ab  retn
0x1800041ad  mov     eax, 0C000010Ah
0x1800041b2  retn
0x1800041b4  mov     eax, 0C0150022h
0x1800041b9  retn
```
