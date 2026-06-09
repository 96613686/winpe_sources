# WimFSFInitializeCompletionContextOnStack

- ea: `0x1400106a8`
- end: `0x140010750`
- name: `WimFSFInitializeCompletionContextOnStack`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002e1f4`
- `0x14003da08`

## callees

- `0x14000d3fc`
- `0x1400106a8`
- `0x1400119c0`

## pseudocode

```c
__int64 __fastcall WimFSFInitializeCompletionContextOnStack(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  memset((void *)a3, 0, 0x120u);
  *(_OWORD *)(a3 + 24) = *a1;
  *(_OWORD *)(a3 + 40) = a1[1];
  *(_OWORD *)(a3 + 56) = a1[2];
  *(_OWORD *)(a3 + 72) = a1[3];
  *(_OWORD *)(a3 + 88) = a1[4];
  *(_OWORD *)(a3 + 104) = a1[5];
  *(_OWORD *)(a3 + 120) = a1[6];
  *(_OWORD *)(a3 + 136) = a1[7];
  *(_DWORD *)(a3 + 144) |= 1u;
  *(_DWORD *)(a3 + 16) = 1;
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    return WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b091599abfd73b8a76031cd442416986_Traceguids, a3);
  return result;
}

```

## disassembly

```asm
0x1400106a8  mov     [rsp+arg_0], rbx
0x1400106ad  push    rdi
0x1400106ae  sub     rsp, 20h
0x1400106b2  mov     rdi, r8
0x1400106b5  mov     rbx, rcx
0x1400106b8  mov     rcx, rdi; void *
0x1400106bb  xor     edx, edx; Val
0x1400106bd  mov     r8d, 120h; Size
0x1400106c3  call    memset
0x1400106c8  movups  xmm0, xmmword ptr [rbx]
0x1400106cb  movups  xmmword ptr [rdi+18h], xmm0
0x1400106cf  movups  xmm1, xmmword ptr [rbx+10h]
0x1400106d3  movups  xmmword ptr [rdi+28h], xmm1
0x1400106d7  movups  xmm0, xmmword ptr [rbx+20h]
0x1400106db  movups  xmmword ptr [rdi+38h], xmm0
0x1400106df  movups  xmm1, xmmword ptr [rbx+30h]
0x1400106e3  movups  xmmword ptr [rdi+48h], xmm1
0x1400106e7  movups  xmm0, xmmword ptr [rbx+40h]
0x1400106eb  movups  xmmword ptr [rdi+58h], xmm0
0x1400106ef  movups  xmm1, xmmword ptr [rbx+50h]
0x1400106f3  movups  xmmword ptr [rdi+68h], xmm1
0x1400106f7  movups  xmm0, xmmword ptr [rbx+60h]
0x1400106fb  movups  xmmword ptr [rdi+78h], xmm0
0x1400106ff  movups  xmm1, xmmword ptr [rbx+70h]
0x140010703  movups  xmmword ptr [rdi+88h], xmm1
0x14001070a  or      dword ptr [rdi+90h], 1
0x140010711  mov     dword ptr [rdi+10h], 1
0x140010718  mov     rcx, cs:WPP_GLOBAL_Control
0x14001071f  mov     eax, [rcx+2Ch]
0x140010722  test    al, 20h
0x140010724  jz      short loc_140010744
0x140010726  cmp     byte ptr [rcx+29h], 5
0x14001072a  jb      short loc_140010744
0x14001072c  mov     rcx, [rcx+18h]
0x140010730  lea     r8, WPP_b091599abfd73b8a76031cd442416986_Traceguids
0x140010737  mov     edx, 0Ah
0x14001073c  mov     r9, rdi
0x14001073f  call    WPP_SF_q
0x140010744  mov     rbx, [rsp+28h+arg_0]
0x140010749  add     rsp, 20h
0x14001074d  pop     rdi
0x14001074e  retn
```
