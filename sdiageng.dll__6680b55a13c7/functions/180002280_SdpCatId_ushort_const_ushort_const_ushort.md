# SdpCatId(ushort const *,ushort const *,ushort * *)

- ea: `0x180002280`
- end: `0x18000232f`
- name: `?SdpCatId@@YAJPEBG0PEAPEAG@Z`
- size: `175`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180018a9c`
- `0x1800192ac`
- `0x18001955c`
- `0x1800199c4`
- `0x18001b0b4`
- `0x18001c224`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x180026fa0`
- `0x1800278d4`

## pseudocode

```c
__int64 __fastcall SdpCatId(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v4; // r8d
  unsigned int v5; // ebx
  int v6; // eax
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  if ( !a1 )
  {
    v4 = 329;
LABEL_3:
    v5 = -2147024809;
    SdpDebugTrace(1u, L"SdpCatId", v4, -2147024809);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 330;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v4 = 331;
    goto LABEL_3;
  }
  v6 = SdpStrCat(a1, a2, 0x2Fu, &v9);
  v5 = v6;
  if ( v6 >= 0 )
  {
    v7 = 0;
    *a3 = v9;
  }
  else
  {
    SdpDebugTrace(1u, L"SdpCatId", 334, v6);
    v7 = v9;
  }
  if ( v7 )
    operator delete(v7);
  return v5;
}

```

## disassembly

```asm
0x180002280  mov     [rsp+arg_8], rbx
0x180002285  push    rdi
0x180002286  sub     rsp, 20h
0x18000228a  mov     [rsp+28h+arg_0], 0
0x180002293  mov     rdi, r8
0x180002296  test    rcx, rcx
0x180002299  jnz     short loc_1800022BD
0x18000229b  mov     r8d, 149h; int
0x1800022a1  mov     r9d, 80070057h; int
0x1800022a7  lea     rdx, aSdpcatid; "SdpCatId"
0x1800022ae  mov     ecx, 1; Level
0x1800022b3  mov     ebx, r9d
0x1800022b6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800022bb  jmp     short loc_180002322
0x1800022bd  test    rdx, rdx
0x1800022c0  jnz     short loc_1800022CA
0x1800022c2  mov     r8d, 14Ah
0x1800022c8  jmp     short loc_1800022A1
0x1800022ca  test    rdi, rdi
0x1800022cd  jnz     short loc_1800022D7
0x1800022cf  mov     r8d, 14Bh
0x1800022d5  jmp     short loc_1800022A1
0x1800022d7  mov     r8d, 2Fh ; '/'; unsigned __int16
0x1800022dd  lea     r9, [rsp+28h+arg_0]; unsigned __int16 **
0x1800022e2  call    ?SdpStrCat@@YAJPEBG0GPEAPEAG@Z; SdpStrCat(ushort const *,ushort const *,ushort,ushort * *)
0x1800022e7  mov     ebx, eax
0x1800022e9  test    eax, eax
0x1800022eb  jns     short loc_18000230E
0x1800022ed  mov     r9d, eax; int
0x1800022f0  lea     rdx, aSdpcatid; "SdpCatId"
0x1800022f7  mov     r8d, 14Eh; int
0x1800022fd  mov     ecx, 1; Level
0x180002302  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002307  mov     rcx, [rsp+28h+arg_0]
0x18000230c  jmp     short loc_180002318
0x18000230e  mov     rax, [rsp+28h+arg_0]
0x180002313  xor     ecx, ecx; Block
0x180002315  mov     [rdi], rax
0x180002318  test    rcx, rcx
0x18000231b  jz      short loc_180002322
0x18000231d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002322  mov     eax, ebx
0x180002324  mov     rbx, [rsp+28h+arg_8]
0x180002329  add     rsp, 20h
0x18000232d  pop     rdi
0x18000232e  retn
```
