# BasepSxsCreateResourceStream

- ea: `0x180004310`
- end: `0x18000437a`
- name: `BasepSxsCreateResourceStream`
- size: `106`
- prototype: `__int64 __fastcall(__int128 **, _QWORD *, __int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d40`

## callees

- `0x180004310`

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
0x180004310  cmp     qword ptr [rdx+18h], 0
0x180004315  mov     r8, rdx
0x180004318  mov     rax, [rsp+arg_30]
0x18000431d  mov     r9, rcx
0x180004320  jz      short loc_18000436D
0x180004322  mov     edx, [rsp+arg_28]
0x180004326  test    edx, edx
0x180004328  jz      short loc_180004366
0x18000432a  mov     rcx, [rsp+arg_20]
0x18000432f  mov     [rax+28h], rcx
0x180004333  mov     [rax+30h], rdx
0x180004337  cmp     rdx, 800000h
0x18000433e  ja      short loc_180004374
0x180004340  mov     rcx, [r8+8]
0x180004344  mov     [rax+20h], rcx
0x180004348  mov     rcx, [r8]
0x18000434b  mov     [rax+18h], rcx
0x18000434f  mov     rcx, [r9]
0x180004352  mov     word ptr [rax], 101h
0x180004357  movups  xmm0, xmmword ptr [rcx]
0x18000435a  mov     byte ptr [rax+2], 1
0x18000435e  movups  xmmword ptr [rax+8], xmm0
0x180004362  xor     eax, eax
0x180004364  retn
0x180004366  mov     eax, 0C0000089h
0x18000436b  retn
0x18000436d  mov     eax, 0C000010Ah
0x180004372  retn
0x180004374  mov     eax, 0C0150022h
0x180004379  retn
```
