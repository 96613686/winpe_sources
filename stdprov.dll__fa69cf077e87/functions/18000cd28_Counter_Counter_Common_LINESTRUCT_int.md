# Counter_Counter_Common(_LINESTRUCT *,int)

- ea: `0x18000cd28`
- end: `0x18000cd97`
- name: `?Counter_Counter_Common@@YAMPEAU_LINESTRUCT@@H@Z`
- size: `111`
- prototype: `float __fastcall(struct _LINESTRUCT *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cb10`

## callees

- `0x18000cd28`
- `0x18000d1d0`

## pseudocode

```c
float __fastcall Counter_Counter_Common(struct _LINESTRUCT *a1, int a2)
{
  __int64 v2; // rax
  __int64 v3; // r9
  int v4; // r9d
  int v5; // r10d
  float TimeInterval; // xmm3_4
  float result; // xmm0_4

  v2 = *((_QWORD *)a1 + 6);
  v3 = *((_QWORD *)a1 + 4) - v2;
  if ( a2 != 1 )
  {
    if ( *((_QWORD *)a1 + 4) < v2 && v3 > 4294901760LL )
      return 0.0;
    v3 = (unsigned int)v3;
  }
  if ( v3 <= 0 )
    return 0.0;
  TimeInterval = eGetTimeInterval((__int64 *)a1, (__int64 *)a1 + 1, (__int64 *)a1 + 9);
  if ( TimeInterval <= 0.0 )
    return 0.0;
  result = (float)v4 / TimeInterval;
  if ( v5 )
  {
    if ( result > 1500000000.0 )
      return 0.0;
  }
  return result;
}

```

## disassembly

```asm
0x18000cd28  sub     rsp, 28h
0x18000cd2c  mov     rax, [rcx+30h]
0x18000cd30  xor     r10d, r10d
0x18000cd33  mov     r9, [rcx+20h]
0x18000cd37  xorps   xmm2, xmm2
0x18000cd3a  sub     r9, rax
0x18000cd3d  cmp     edx, 1
0x18000cd40  jz      short loc_18000CD5B
0x18000cd42  cmp     [rcx+20h], rax
0x18000cd46  jge     short loc_18000CD58
0x18000cd48  mov     eax, 0FFFF0000h
0x18000cd4d  cmp     r9, rax
0x18000cd50  jg      short loc_18000CD8F
0x18000cd52  mov     r10d, 1
0x18000cd58  mov     r9d, r9d
0x18000cd5b  test    r9, r9
0x18000cd5e  jle     short loc_18000CD8F
0x18000cd60  lea     r8, [rcx+48h]; __int64 *
0x18000cd64  lea     rdx, [rcx+8]; __int64 *
0x18000cd68  call    ?eGetTimeInterval@@YAMPEA_J00@Z; eGetTimeInterval(__int64 *,__int64 *,__int64 *)
0x18000cd6d  movaps  xmm3, xmm0
0x18000cd70  comiss  xmm2, xmm3
0x18000cd73  jnb     short loc_18000CD8F
0x18000cd75  xorps   xmm0, xmm0
0x18000cd78  cvtsi2ss xmm0, r9
0x18000cd7d  divss   xmm0, xmm3
0x18000cd81  test    r10d, r10d
0x18000cd84  jz      short loc_18000CD92
0x18000cd86  comiss  xmm0, cs:__real@4eb2d05e
0x18000cd8d  jbe     short loc_18000CD92
0x18000cd8f  xorps   xmm0, xmm0
0x18000cd92  add     rsp, 28h
0x18000cd96  retn
```
