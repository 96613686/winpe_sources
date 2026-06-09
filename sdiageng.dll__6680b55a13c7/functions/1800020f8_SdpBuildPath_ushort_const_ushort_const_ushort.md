# SdpBuildPath(ushort const *,ushort const *,ushort * *)

- ea: `0x1800020f8`
- end: `0x18000227a`
- name: `?SdpBuildPath@@YAJPEBG0PEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `13`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800034c4`
- `0x180005d60`
- `0x18000615c`
- `0x18000787c`
- `0x18000a86c`
- `0x18000bef0`
- `0x18000c144`
- `0x18000c3fc`
- `0x1800101cc`
- `0x180011888`
- `0x180011ba4`
- `0x18001dc28`
- `0x180021914`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x180026fa0`
- `0x1800278d4`

## string_xrefs

- `0x180002125`: `SdpBuildPath`
- `0x18000223c`: `SdpBuildPath`

## pseudocode

```c
__int64 __fastcall SdpBuildPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v6; // r8d
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r11
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  unsigned __int16 v13; // r11
  int v14; // eax
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v17; // [rsp+50h] [rbp+8h] BYREF

  v17 = 0;
  if ( !a1 )
  {
    v6 = 256;
LABEL_3:
    v7 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpBuildPath", v6, -2147024809);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 257;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 258;
    goto LABEL_3;
  }
  v8 = a1;
  v9 = 260;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v7 = v9 == 0 ? 0x80070057 : 0;
  v10 = (260 - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
  {
    v6 = 261;
    goto LABEL_4;
  }
  if ( !v10 )
  {
    v6 = 265;
    goto LABEL_3;
  }
  v11 = 260;
  v12 = a2;
  v13 = a1[v10 - 1] != 92 ? 0x5C : 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v7 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
    v6 = 273;
    goto LABEL_4;
  }
  if ( ((260 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64)) == 0 )
  {
    v6 = 277;
    goto LABEL_3;
  }
  v14 = SdpStrCat(a1, a2, v13, &v17);
  v7 = v14;
  if ( v14 >= 0 )
  {
    v15 = 0;
    *a3 = v17;
  }
  else
  {
    SdpDebugTrace(1u, L"SdpBuildPath", 281, v14);
    v15 = v17;
  }
  if ( v15 )
    operator delete(v15);
  return v7;
}

```

## disassembly

```asm
0x1800020f8  push    rbx
0x1800020fa  push    rbp
0x1800020fb  push    rsi
0x1800020fc  push    rdi
0x1800020fd  sub     rsp, 28h
0x180002101  xor     ebp, ebp
0x180002103  mov     rsi, r8
0x180002106  mov     [rsp+48h+arg_0], rbp
0x18000210b  mov     rdi, rdx
0x18000210e  mov     r10, rcx
0x180002111  test    rcx, rcx
0x180002114  jnz     short loc_18000213B
0x180002116  mov     r8d, 100h; int
0x18000211c  mov     r9d, 80070057h; int
0x180002122  mov     ebx, r9d
0x180002125  lea     rdx, aSdpbuildpath; "SdpBuildPath"
0x18000212c  mov     ecx, 1; Level
0x180002131  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002136  jmp     loc_18000226F
0x18000213b  test    rdi, rdi
0x18000213e  jnz     short loc_180002148
0x180002140  mov     r8d, 101h
0x180002146  jmp     short loc_18000211C
0x180002148  test    rsi, rsi
0x18000214b  jnz     short loc_180002155
0x18000214d  mov     r8d, 102h
0x180002153  jmp     short loc_18000211C
0x180002155  mov     r8d, 104h
0x18000215b  mov     rax, r10
0x18000215e  mov     edx, r8d
0x180002161  cmp     [rax], bp
0x180002164  jz      short loc_180002170
0x180002166  add     rax, 2
0x18000216a  sub     rdx, 1
0x18000216e  jnz     short loc_180002161
0x180002170  mov     rax, rdx
0x180002173  mov     r9d, 80070057h
0x180002179  neg     rax
0x18000217c  mov     rcx, r8
0x18000217f  mov     rax, rdx
0x180002182  sbb     ebx, ebx
0x180002184  sub     rcx, rdx
0x180002187  not     ebx
0x180002189  and     ebx, r9d
0x18000218c  neg     rax
0x18000218f  sbb     r11, r11
0x180002192  and     r11, rcx
0x180002195  test    rdx, rdx
0x180002198  jnz     short loc_1800021A5
0x18000219a  mov     r9d, ebx
0x18000219d  mov     r8d, 105h
0x1800021a3  jmp     short loc_180002125
0x1800021a5  test    r11, r11
0x1800021a8  jnz     short loc_1800021B5
0x1800021aa  mov     r8d, 109h
0x1800021b0  jmp     loc_180002122
0x1800021b5  movzx   eax, word ptr [r10+r11*2-2]
0x1800021bb  mov     rcx, r8
0x1800021be  sub     ax, 5Ch ; '\'
0x1800021c2  neg     ax
0x1800021c5  mov     rax, rdi
0x1800021c8  sbb     r11w, r11w
0x1800021cc  and     r11w, 5Ch
0x1800021d1  cmp     [rax], bp
0x1800021d4  jz      short loc_1800021E0
0x1800021d6  add     rax, 2
0x1800021da  sub     rcx, 1
0x1800021de  jnz     short loc_1800021D1
0x1800021e0  mov     rax, rcx
0x1800021e3  neg     rax
0x1800021e6  mov     rax, rcx
0x1800021e9  sbb     ebx, ebx
0x1800021eb  sub     r8, rcx
0x1800021ee  not     ebx
0x1800021f0  and     ebx, r9d
0x1800021f3  neg     rax
0x1800021f6  sbb     rdx, rdx
0x1800021f9  and     rdx, r8
0x1800021fc  test    rcx, rcx
0x1800021ff  jnz     short loc_18000220F
0x180002201  mov     r9d, ebx
0x180002204  mov     r8d, 111h
0x18000220a  jmp     loc_180002125
0x18000220f  test    rdx, rdx
0x180002212  jnz     short loc_18000221F
0x180002214  mov     r8d, 115h
0x18000221a  jmp     loc_180002122
0x18000221f  lea     r9, [rsp+48h+arg_0]; unsigned __int16 **
0x180002224  movzx   r8d, r11w; unsigned __int16
0x180002228  mov     rdx, rdi; unsigned __int16 *
0x18000222b  mov     rcx, r10; unsigned __int16 *
0x18000222e  call    ?SdpStrCat@@YAJPEBG0GPEAPEAG@Z; SdpStrCat(ushort const *,ushort const *,ushort,ushort * *)
0x180002233  mov     ebx, eax
0x180002235  test    eax, eax
0x180002237  jns     short loc_18000225A
0x180002239  mov     r9d, eax; int
0x18000223c  lea     rdx, aSdpbuildpath; "SdpBuildPath"
0x180002243  mov     r8d, 119h; int
0x180002249  mov     ecx, 1; Level
0x18000224e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002253  mov     rcx, [rsp+48h+arg_0]
0x180002258  jmp     short loc_180002265
0x18000225a  mov     rax, [rsp+48h+arg_0]
0x18000225f  mov     rcx, rbp; Block
0x180002262  mov     [rsi], rax
0x180002265  test    rcx, rcx
0x180002268  jz      short loc_18000226F
0x18000226a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000226f  mov     eax, ebx
0x180002271  add     rsp, 28h
0x180002275  pop     rdi
0x180002276  pop     rsi
0x180002277  pop     rbp
0x180002278  pop     rbx
0x180002279  retn
```
