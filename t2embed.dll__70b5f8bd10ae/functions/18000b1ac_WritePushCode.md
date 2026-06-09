# WritePushCode

- ea: `0x18000b1ac`
- end: `0x18000b1e1`
- name: `WritePushCode`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d40`

## callees

- `0x18000b1ac`

## import_xrefs

- `msvcrt!longjmp` at `0x18000b1da`
- `msvcrt!longjmp` at `0x18000b1da`

## pseudocode

```c
__int64 __fastcall WritePushCode(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, __int16 a4)
{
  __int64 result; // rax

  if ( a2 >= a3 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  result = *(_QWORD *)(a1 + 88);
  *(_WORD *)(result + 2LL * a2) = a4;
  return result;
}

```

## disassembly

```asm
0x18000b1ac  sub     rsp, 28h
0x18000b1b0  mov     rax, rcx
0x18000b1b3  cmp     dx, r8w
0x18000b1b7  jnb     short loc_18000B1CA
0x18000b1b9  mov     rax, [rax+58h]
0x18000b1bd  movzx   ecx, dx
0x18000b1c0  mov     [rax+rcx*2], r9w
0x18000b1c5  add     rsp, 28h
0x18000b1c9  retn
0x18000b1ca  mov     rcx, [rcx+88h]
0x18000b1d1  mov     edx, 0D22h; Value
0x18000b1d6  add     rcx, 30h ; '0'; Buf
0x18000b1da  call    cs:__imp_longjmp
```
