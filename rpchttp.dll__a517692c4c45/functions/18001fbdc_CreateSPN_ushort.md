# CreateSPN(ushort *)

- ea: `0x18001fbdc`
- end: `0x18001fc4f`
- name: `?CreateSPN@@YAPEAGPEAG@Z`
- size: `115`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800208cc`
- `0x180023428`

## callees

- `0x18001fbdc`
- `0x18002461d`

## import_xrefs

- `RPCRT4!I_RpcAllocate` at `0x18001fc0e`
- `RPCRT4!I_RpcAllocate` at `0x18001fc0e`

## pseudocode

```c
unsigned __int16 *__fastcall CreateSPN(unsigned __int16 *Src)
{
  __int64 v2; // rax
  int v3; // esi
  unsigned int v4; // eax
  unsigned __int64 v5; // kr00_8
  unsigned __int16 *result; // rax
  unsigned __int16 *v7; // rbx

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  v3 = v2 + 1;
  v5 = (unsigned int)(v2 + 6);
  v4 = 2 * (v2 + 6);
  if ( !is_mul_ok(v5, 2u) )
    v4 = -1;
  result = (unsigned __int16 *)I_RpcAllocate(v4);
  v7 = result;
  if ( result )
  {
    *(_QWORD *)result = 0x740073006F0068LL;
    result[4] = 47;
    memcpy_0(result + 5, Src, (unsigned int)(2 * v3));
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001fbdc  push    rbx
0x18001fbde  push    rbp
0x18001fbdf  push    rsi
0x18001fbe0  push    rdi
0x18001fbe1  sub     rsp, 28h
0x18001fbe5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fbe9  mov     rdi, rcx
0x18001fbec  mov     rax, r8
0x18001fbef  xor     ebp, ebp
0x18001fbf1  inc     rax
0x18001fbf4  cmp     [rcx+rax*2], bp
0x18001fbf8  jnz     short loc_18001FBF1
0x18001fbfa  lea     esi, [rax+1]
0x18001fbfd  mov     eax, 2
0x18001fc02  lea     ecx, [rsi+5]
0x18001fc05  mul     rcx
0x18001fc08  cmovb   rax, r8
0x18001fc0c  mov     ecx, eax; Size
0x18001fc0e  call    cs:__imp_I_RpcAllocate
0x18001fc14  mov     rbx, rax
0x18001fc17  test    rax, rax
0x18001fc1a  jz      short loc_18001FC46
0x18001fc1c  movsd   xmm0, cs:qword_180028780
0x18001fc24  lea     r8d, [rsi+rsi]; Size
0x18001fc28  movsd   qword ptr [rax], xmm0
0x18001fc2c  lea     rcx, [rbx+0Ah]; void *
0x18001fc30  movzx   eax, cs:word_180028788
0x18001fc37  mov     rdx, rdi; Src
0x18001fc3a  mov     [rbx+8], ax
0x18001fc3e  call    memcpy_0
0x18001fc43  mov     rax, rbx
0x18001fc46  add     rsp, 28h
0x18001fc4a  pop     rdi
0x18001fc4b  pop     rsi
0x18001fc4c  pop     rbp
0x18001fc4d  pop     rbx
0x18001fc4e  retn
```
