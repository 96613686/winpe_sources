# InputTape::ReplacedText(ushort,ushort,ushort * *)

- ea: `0x1800bb0c0`
- end: `0x1800bb181`
- name: `?ReplacedText@InputTape@@UEBAJGGPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(InputTape *__hidden this, unsigned __int16, unsigned __int16, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c6aa0`

## callees

- `0x180004312`
- `0x1800bb0c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb0e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb0e4`

## pseudocode

```c
__int64 __fastcall InputTape::ReplacedText(
        InputTape *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int16 **a4)
{
  unsigned __int16 v4; // si
  __int64 v7; // rbp
  void *v8; // rdi
  __int64 v10; // rcx
  int i; // edx
  __int64 v12; // rcx

  v4 = a3;
  v7 = a2;
  v8 = CoTaskMemAlloc(2LL * a3 + 2);
  if ( !v8 )
    return 2147942414LL;
  v10 = *((_QWORD *)this + 2);
  if ( *(_WORD *)(v10 + 2 * v7) == 32 )
  {
    do
    {
      if ( !v4 )
        break;
      LOWORD(v7) = v7 + 1;
      --v4;
    }
    while ( *(_WORD *)(v10 + 2LL * (unsigned __int16)v7) == 32 );
  }
  memcpy_0(v8, (const void *)(v10 + 2LL * (unsigned __int16)v7), 2LL * v4);
  *((_WORD *)v8 + v4) = 0;
  for ( i = v4 - 1; *((_WORD *)v8 + i) == 32; *((_WORD *)v8 + v12) = 0 )
  {
    if ( i < 0 )
      break;
    v12 = i--;
  }
  *a4 = (unsigned __int16 *)v8;
  return 0;
}

```

## disassembly

```asm
0x1800bb0c0  push    rbx
0x1800bb0c2  push    rbp
0x1800bb0c3  push    rsi
0x1800bb0c4  push    rdi
0x1800bb0c5  push    r13
0x1800bb0c7  push    r14
0x1800bb0c9  push    r15
0x1800bb0cb  sub     rsp, 20h
0x1800bb0cf  movzx   esi, r8w
0x1800bb0d3  mov     rbx, rcx
0x1800bb0d6  mov     r14, r9
0x1800bb0d9  movzx   ebp, dx
0x1800bb0dc  lea     rcx, ds:2[rsi*2]; cb
0x1800bb0e4  call    cs:__imp_CoTaskMemAlloc
0x1800bb0ea  xor     r15d, r15d
0x1800bb0ed  mov     rdi, rax
0x1800bb0f0  test    rax, rax
0x1800bb0f3  jnz     short loc_1800BB0FC
0x1800bb0f5  mov     eax, 8007000Eh
0x1800bb0fa  jmp     short loc_1800BB172
0x1800bb0fc  mov     rcx, [rbx+10h]
0x1800bb100  mov     r13d, 1
0x1800bb106  cmp     word ptr [rcx+rbp*2], 20h ; ' '
0x1800bb10b  jnz     short loc_1800BB128
0x1800bb10d  test    si, si
0x1800bb110  jz      short loc_1800BB128
0x1800bb112  mov     eax, 0FFFFh
0x1800bb117  add     bp, r13w
0x1800bb11b  add     si, ax
0x1800bb11e  movzx   eax, bp
0x1800bb121  cmp     word ptr [rcx+rax*2], 20h ; ' '
0x1800bb126  jz      short loc_1800BB10D
0x1800bb128  movzx   eax, si
0x1800bb12b  lea     rbx, [rax+rax]
0x1800bb12f  movzx   eax, bp
0x1800bb132  mov     r8, rbx; Size
0x1800bb135  lea     rdx, [rcx+rax*2]; Src
0x1800bb139  mov     rcx, rdi; void *
0x1800bb13c  call    memcpy_0
0x1800bb141  movzx   eax, si
0x1800bb144  mov     [rbx+rdi], r15w
0x1800bb149  cmp     word ptr [rdi+rax*2-2], 20h ; ' '
0x1800bb14f  lea     edx, [rax-1]
0x1800bb152  jnz     short loc_1800BB16D
0x1800bb154  test    edx, edx
0x1800bb156  js      short loc_1800BB16D
0x1800bb158  movsxd  rcx, edx
0x1800bb15b  sub     edx, r13d
0x1800bb15e  movsxd  rax, edx
0x1800bb161  mov     [rdi+rcx*2], r15w
0x1800bb166  cmp     word ptr [rdi+rax*2], 20h ; ' '
0x1800bb16b  jz      short loc_1800BB154
0x1800bb16d  mov     [r14], rdi
0x1800bb170  xor     eax, eax
0x1800bb172  add     rsp, 20h
0x1800bb176  pop     r15
0x1800bb178  pop     r14
0x1800bb17a  pop     r13
0x1800bb17c  pop     rdi
0x1800bb17d  pop     rsi
0x1800bb17e  pop     rbp
0x1800bb17f  pop     rbx
0x1800bb180  retn
```
