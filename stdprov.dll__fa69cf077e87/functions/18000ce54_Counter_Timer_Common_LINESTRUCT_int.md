# Counter_Timer_Common(_LINESTRUCT *,int)

- ea: `0x18000ce54`
- end: `0x18000cf5d`
- name: `?Counter_Timer_Common@@YAMPEAU_LINESTRUCT@@H@Z`
- size: `265`
- prototype: `float __fastcall(struct _LINESTRUCT *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cb10`

## callees

- `0x18000ce54`
- `0x18000d1d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
float __fastcall Counter_Timer_Common(struct _LINESTRUCT *a1, int a2)
{
  int v2; // r9d
  __int64 *v3; // r8
  float TimeInterval; // xmm3_4
  float v5; // xmm0_4
  float v6; // xmm0_4
  float v7; // xmm4_4
  float v8; // xmm1_4
  float v9; // xmm3_4
  float v10; // xmm2_4

  v2 = a2;
  v3 = (__int64 *)((char *)a1 + 72);
  if ( ((a2 - 542180608) & 0xFCFFFFFF) != 0 )
    TimeInterval = eGetTimeInterval((__int64 *)a1, (__int64 *)a1 + 1, v3);
  else
    TimeInterval = (float)(*((_DWORD *)a1 + 6) - *((_DWORD *)a1 + 4));
  if ( TimeInterval <= 0.0 )
    return 0.0;
  v5 = (float)(*((_DWORD *)a1 + 8) - *((_DWORD *)a1 + 12));
  if ( v2 && v2 != 557909248 )
  {
    v6 = v5 / TimeInterval;
    goto LABEL_10;
  }
  v7 = (float)(int)*v3;
  if ( v7 <= 0.0 )
    return 0.0;
  v6 = (float)(v5 / v7) / TimeInterval;
  if ( v2 != 557909248 )
  {
LABEL_10:
    v8 = v6;
    if ( v2 != 558957824 )
      goto LABEL_12;
  }
  v8 = 1.0 - v6;
LABEL_12:
  if ( ((v2 - 574686464) & 0xFEEFFFFF) == 0 )
  {
    v9 = (float)(int)*((_QWORD *)a1 + 5);
    if ( v9 != 0.0 )
    {
      if ( ((v2 - 591463680) & 0xFFEFFFFF) == 0 )
        v8 = v9 - v8;
      v8 = v8 / v9;
      goto LABEL_17;
    }
    return 0.0;
  }
LABEL_17:
  v10 = fmaxf(0.0, v8 * 100.0);
  if ( v10 > 100.0 && ((v2 - 574686464) & 0xFEEFFFFF) != 0 )
    return FLOAT_100_0;
  return v10;
}

```

## disassembly

```asm
0x18000ce54  sub     rsp, 28h
0x18000ce58  lea     eax, [rdx-20510500h]
0x18000ce5e  mov     r9d, edx
0x18000ce61  lea     r8, [rcx+48h]; __int64 *
0x18000ce65  test    eax, 0FCFFFFFFh
0x18000ce6a  jz      short loc_18000CE7A
0x18000ce6c  lea     rdx, [rcx+8]; __int64 *
0x18000ce70  call    ?eGetTimeInterval@@YAMPEA_J00@Z; eGetTimeInterval(__int64 *,__int64 *,__int64 *)
0x18000ce75  movaps  xmm3, xmm0
0x18000ce78  jmp     short loc_18000CE8A
0x18000ce7a  mov     rax, [rcx+18h]
0x18000ce7e  xorps   xmm3, xmm3
0x18000ce81  sub     rax, [rcx+10h]
0x18000ce85  cvtsi2ss xmm3, rax
0x18000ce8a  xorps   xmm2, xmm2
0x18000ce8d  comiss  xmm2, xmm3
0x18000ce90  jnb     loc_18000CF55
0x18000ce96  mov     rax, [rcx+20h]
0x18000ce9a  xorps   xmm0, xmm0
0x18000ce9d  sub     rax, [rcx+30h]
0x18000cea1  cvtsi2ss xmm0, rax
0x18000cea6  mov     eax, 21410500h
0x18000ceab  test    r9d, r9d
0x18000ceae  jz      short loc_18000CEBB
0x18000ceb0  cmp     r9d, eax
0x18000ceb3  jz      short loc_18000CEBB
0x18000ceb5  divss   xmm0, xmm3
0x18000ceb9  jmp     short loc_18000CED9
0x18000cebb  xorps   xmm4, xmm4
0x18000cebe  cvtsi2ss xmm4, qword ptr [r8]
0x18000cec3  comiss  xmm2, xmm4
0x18000cec6  jnb     loc_18000CF55
0x18000cecc  divss   xmm0, xmm4
0x18000ced0  divss   xmm0, xmm3
0x18000ced4  cmp     r9d, eax
0x18000ced7  jz      short loc_18000CEE5
0x18000ced9  movaps  xmm1, xmm0
0x18000cedc  cmp     r9d, 21510500h
0x18000cee3  jnz     short loc_18000CEF1
0x18000cee5  movss   xmm1, cs:__real@3f800000
0x18000ceed  subss   xmm1, xmm0
0x18000cef1  lea     eax, [r9-22410500h]
0x18000cef8  mov     edx, 0FEEFFFFFh
0x18000cefd  test    edx, eax
0x18000ceff  jnz     short loc_18000CF2D
0x18000cf01  xorps   xmm3, xmm3
0x18000cf04  cvtsi2ss xmm3, qword ptr [rcx+28h]
0x18000cf0a  ucomiss xmm3, xmm2
0x18000cf0d  jp      short loc_18000CF11
0x18000cf0f  jz      short loc_18000CF55
0x18000cf11  lea     eax, [r9-23410500h]
0x18000cf18  test    eax, 0FFEFFFFFh
0x18000cf1d  jnz     short loc_18000CF29
0x18000cf1f  movaps  xmm0, xmm3
0x18000cf22  subss   xmm0, xmm1
0x18000cf26  movaps  xmm1, xmm0
0x18000cf29  divss   xmm1, xmm3
0x18000cf2d  movss   xmm0, cs:__real@42c80000
0x18000cf35  mulss   xmm1, xmm0
0x18000cf39  maxss   xmm2, xmm1
0x18000cf3d  comiss  xmm2, xmm0
0x18000cf40  jbe     short loc_18000CF50
0x18000cf42  lea     eax, [r9-22410500h]
0x18000cf49  test    edx, eax
0x18000cf4b  jz      short loc_18000CF50
0x18000cf4d  movaps  xmm2, xmm0
0x18000cf50  movaps  xmm0, xmm2
0x18000cf53  jmp     short loc_18000CF58
0x18000cf55  xorps   xmm0, xmm0
0x18000cf58  add     rsp, 28h
0x18000cf5c  retn
```
