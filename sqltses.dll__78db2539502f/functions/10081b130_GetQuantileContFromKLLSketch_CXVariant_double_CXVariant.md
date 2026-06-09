# GetQuantileContFromKLLSketch(CXVariant *,double,CXVariant *)

- ea: `0x10081b130`
- end: `0x10081b3ae`
- name: `?GetQuantileContFromKLLSketch@@YAXPEAVCXVariant@@N0@Z`
- size: `638`
- prototype: `void __fastcall(struct CXVariant *, double, struct CXVariant *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10081b6d0`

## callees

- `0x10081b130`
- `0x100820df0`
- `0x100820e80`
- `0x100821840`
- `0x10083e6e7`
- `0x10083e6f3`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081b371`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081b371`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081b23c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081b23c`
- `sqldk!SystemThread_TlsIndex` at `0x10081b18d`
- `sqldk!SystemThread_TlsOffset` at `0x10081b196`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081b1b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081b1b1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081b1dc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081b1dc`

## string_xrefs

- `0x10081b22f`: `sql\ntdbms\common\sketches\KLLSketch.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GetQuantileContFromKLLSketch(struct CXVariant *a1, double a2, struct CXVariant *a3)
{
  __int64 v4; // rdi
  char v5; // bp
  __int64 v6; // rsi
  __int64 v7; // rax
  struct IMemObj *v8; // rsi
  unsigned __int16 *v9; // r15
  __int64 v10; // r12
  unsigned __int64 v11; // rax
  void *v12; // rsi
  __int64 v13; // rcx
  double v14; // xmm6_8
  double v15; // xmm6_8
  double v16; // xmm0_8
  double v17; // xmm7_8
  double v18; // xmm1_8
  __int64 v19; // rbp
  double v20; // xmm0_8
  double v21; // xmm4_8
  double ItemForQueryWeightCont; // xmm6_8
  char v23; // [rsp+38h] [rbp-90h] BYREF
  _QWORD v24[6]; // [rsp+40h] [rbp-88h] BYREF
  char v25; // [rsp+70h] [rbp-58h]
  int v26; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+20h] BYREF

  v4 = *((_QWORD *)a1 + 1);
  if ( *(_DWORD *)v4 == -1450139961 && *(_WORD *)(v4 + 42) )
  {
    v5 = *(_BYTE *)(v4 + 16);
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = *(struct IMemObj **)(v7 + 1000);
    if ( v5 != 62 )
      ex_raise(98, 36, 16, 16);
    v24[0] = v8;
    v25 = 1;
    v24[3] = v4 + 16;
    v9 = (unsigned __int16 *)(v4 + 56);
    v24[4] = v4 + 56;
    v10 = v4 + 2 * (*(unsigned __int16 *)(v4 + 20) + 29LL);
    v24[5] = v10;
    v11 = 2LL * *(unsigned __int16 *)(v4 + 22);
    if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
      v11 = -1;
    v12 = operator new[](v11, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
    v24[1] = v12;
    v13 = *(_QWORD *)(v4 + 48) - 1LL;
    if ( v13 < 0 )
      v14 = (double)(int)(v13 & 1 | ((unsigned __int64)v13 >> 1))
          + (double)(int)(v13 & 1 | ((unsigned __int64)v13 >> 1));
    else
      v14 = (double)(int)v13;
    v15 = v14 * a2;
    v16 = ceil_0(v15);
    v17 = v16;
    v18 = v16;
    if ( v16 >= 9.223372036854776e18 )
      v18 = v16 - 9.223372036854776e18;
    v19 = *(unsigned __int16 *)(v4 + 58);
    if ( (_WORD)v19 == *(_WORD *)(v4 + 40) )
    {
      v20 = floor_0(v15);
      Sort<double>(v10 + 8LL * *v9, v10 + 8 * v19);
      ItemForQueryWeightCont = (1.0 - v21) * *(double *)(v10 + 8 * (*v9 + (unsigned __int64)(unsigned __int16)(int)v17))
                             + *(double *)(v10 + 8 * (*v9 + (unsigned __int64)(unsigned __int16)(int)v20)) * v21;
    }
    else
    {
      CKLLSketch<double>::InitLevelIndexCounters(v24, v12);
      v26 = 0;
      v27 = 0;
      ItemForQueryWeightCont = CKLLSketch<double>::GetItemForQueryWeightCont(
                                 (unsigned int)v24,
                                 (_DWORD)v12,
                                 (unsigned int)&v23,
                                 (int)v18 + 1,
                                 (__int64)&v27,
                                 (__int64)&v26);
    }
    operator delete[](v12);
    *((double *)a3 + 1) = ItemForQueryWeightCont;
    *(_WORD *)a3 = 15872;
  }
  else
  {
    *((_BYTE *)a3 + 1) = 0;
  }
}

```

## disassembly

```asm
0x10081b130  mov     rax, rsp
0x10081b133  push    rsi
0x10081b134  push    rdi
0x10081b135  push    r12
0x10081b137  push    r14
0x10081b139  push    r15
0x10081b13b  sub     rsp, 0A0h
0x10081b142  mov     [rsp+0C8h+var_98], 0FFFFFFFFFFFFFFFEh
0x10081b14b  mov     [rax+10h], rbx
0x10081b14f  mov     [rax+18h], rbp
0x10081b153  movaps  xmmword ptr [rax-38h], xmm6
0x10081b157  movaps  xmmword ptr [rax-48h], xmm7
0x10081b15b  mov     rbx, r8
0x10081b15e  movaps  xmm7, xmm1
0x10081b161  mov     rdi, [rcx+8]
0x10081b165  cmp     dword ptr [rdi], 0A9909EC7h
0x10081b16b  jnz     loc_10081B383
0x10081b171  cmp     word ptr [rdi+2Ah], 0
0x10081b176  jz      loc_10081B383
0x10081b17c  lea     r14, [rdi+10h]
0x10081b180  movzx   ebp, byte ptr [r14]
0x10081b184  mov     rdx, gs:58h
0x10081b18d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10081b194  mov     ecx, [rax]
0x10081b196  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10081b19d  mov     esi, [rax]
0x10081b19f  add     rsi, [rdx+rcx*8]
0x10081b1a3  mov     rax, [rsi+100h]
0x10081b1aa  test    rax, rax
0x10081b1ad  jnz     short loc_10081B1BE
0x10081b1af  xor     ecx, ecx
0x10081b1b1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10081b1b7  mov     rax, [rsi+100h]
0x10081b1be  mov     rsi, [rax+3E8h]
0x10081b1c5  cmp     bpl, 3Eh ; '>'
0x10081b1c9  jz      short loc_10081B1E2
0x10081b1cb  mov     edx, 24h ; '$'
0x10081b1d0  lea     ecx, [rdx+3Eh]
0x10081b1d3  mov     r9d, 10h
0x10081b1d9  mov     r8d, r9d
0x10081b1dc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10081b1e2  mov     [rsp+0C8h+var_88], rsi
0x10081b1e7  mov     [rsp+0C8h+var_58], 1
0x10081b1ec  mov     [rsp+0C8h+var_70], r14
0x10081b1f1  lea     r15, [rdi+38h]
0x10081b1f5  mov     [rsp+0C8h+var_68], r15
0x10081b1fa  movzx   eax, word ptr [r14+4]
0x10081b1ff  add     rax, 1Dh
0x10081b203  lea     r12, [rdi+rax*2]
0x10081b207  mov     [rsp+0C8h+var_60], r12
0x10081b20c  movzx   ecx, word ptr [r14+6]
0x10081b211  mov     eax, 2
0x10081b216  mul     rcx
0x10081b219  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081b220  cmovo   rax, rcx
0x10081b224  mov     byte ptr [rsp+0C8h+var_A8], 3
0x10081b229  mov     r9d, 167h
0x10081b22f  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081b236  mov     rdx, rsi
0x10081b239  mov     rcx, rax
0x10081b23c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081b242  mov     rsi, rax
0x10081b245  mov     [rsp+0C8h+var_80], rax
0x10081b24a  mov     rcx, [r14+20h]
0x10081b24e  sub     rcx, 1
0x10081b252  xorps   xmm6, xmm6
0x10081b255  js      short loc_10081B25E
0x10081b257  cvtsi2sd xmm6, rcx
0x10081b25c  jmp     short loc_10081B273
0x10081b25e  mov     rax, rcx
0x10081b261  shr     rax, 1
0x10081b264  and     ecx, 1
0x10081b267  or      rax, rcx
0x10081b26a  cvtsi2sd xmm6, rax
0x10081b26f  addsd   xmm6, xmm6
0x10081b273  mulsd   xmm6, xmm7
0x10081b277  movaps  xmm0, xmm6; X
0x10081b27a  call    ceil_0
0x10081b27f  movaps  xmm7, xmm0
0x10081b282  xor     eax, eax
0x10081b284  movaps  xmm1, xmm0
0x10081b287  movsd   xmm2, cs:__real@43e0000000000000
0x10081b28f  comisd  xmm0, xmm2
0x10081b293  jb      short loc_10081B2AC
0x10081b295  subsd   xmm1, xmm2
0x10081b299  comisd  xmm1, xmm2
0x10081b29d  jnb     short loc_10081B2AC
0x10081b29f  mov     rcx, 8000000000000000h
0x10081b2a9  mov     rax, rcx
0x10081b2ac  cvttsd2si rdi, xmm1
0x10081b2b1  add     rdi, rax
0x10081b2b4  movzx   ebp, word ptr [r15+2]
0x10081b2b9  cmp     bp, [r14+18h]
0x10081b2be  jnz     short loc_10081B31D
0x10081b2c0  movaps  xmm0, xmm6; X
0x10081b2c3  call    floor_0
0x10081b2c8  movaps  xmm3, xmm0
0x10081b2cb  movaps  xmm4, xmm7
0x10081b2ce  subsd   xmm4, xmm6
0x10081b2d2  lea     rdx, [r12+rbp*8]
0x10081b2d6  movzx   eax, word ptr [r15]
0x10081b2da  lea     rcx, [r12+rax*8]
0x10081b2de  call    ??$Sort@N@@YAXPEAN0@Z; Sort<double>(double *,double *)
0x10081b2e3  movzx   edx, word ptr [r15]
0x10081b2e7  cvttsd2si eax, xmm3
0x10081b2eb  movzx   ecx, ax
0x10081b2ee  add     rcx, rdx
0x10081b2f1  movsd   xmm0, qword ptr [r12+rcx*8]
0x10081b2f7  cvttsd2si eax, xmm7
0x10081b2fb  movzx   ecx, ax
0x10081b2fe  add     rcx, rdx
0x10081b301  movsd   xmm6, cs:__real@3ff0000000000000
0x10081b309  subsd   xmm6, xmm4
0x10081b30d  mulsd   xmm6, qword ptr [r12+rcx*8]
0x10081b313  mulsd   xmm0, xmm4
0x10081b317  addsd   xmm6, xmm0
0x10081b31b  jmp     short loc_10081B36E
0x10081b31d  mov     rdx, rsi
0x10081b320  lea     rcx, [rsp+0C8h+var_88]
0x10081b325  call    ?InitLevelIndexCounters@?$CKLLSketch@N@@AEAAXPEAF@Z; CKLLSketch<double>::InitLevelIndexCounters(short *)
0x10081b32a  xor     eax, eax
0x10081b32c  mov     [rsp+0C8h+arg_0], eax
0x10081b333  mov     [rsp+0C8h+arg_18], rax
0x10081b33b  lea     rax, [rsp+0C8h+arg_0]
0x10081b343  mov     [rsp+0C8h+var_A0], rax
0x10081b348  lea     rax, [rsp+0C8h+arg_18]
0x10081b350  mov     [rsp+0C8h+var_A8], rax
0x10081b355  lea     r9, [rdi+1]
0x10081b359  lea     r8, [rsp+0C8h+var_90]
0x10081b35e  mov     rdx, rsi
0x10081b361  lea     rcx, [rsp+0C8h+var_88]
0x10081b366  call    ?GetItemForQueryWeightCont@?$CKLLSketch@N@@AEAANPEAFAEAN_JAEA_JAEAK@Z; CKLLSketch<double>::GetItemForQueryWeightCont(short *,double &,__int64,__int64 &,ulong &)
0x10081b36b  movaps  xmm6, xmm0
0x10081b36e  mov     rcx, rsi
0x10081b371  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081b377  movsd   qword ptr [rbx+8], xmm6
0x10081b37c  mov     word ptr [rbx], 3E00h
0x10081b381  jmp     short loc_10081B388
0x10081b383  mov     byte ptr [r8+1], 0
0x10081b388  lea     r11, [rsp+0C8h+var_28]
0x10081b390  mov     rbx, [r11+38h]
0x10081b394  mov     rbp, [r11+40h]
0x10081b398  movaps  xmm6, xmmword ptr [r11-10h]
0x10081b39d  movaps  xmm7, xmmword ptr [r11-20h]
0x10081b3a2  mov     rsp, r11
0x10081b3a5  pop     r15
0x10081b3a7  pop     r14
0x10081b3a9  pop     r12
0x10081b3ab  pop     rdi
0x10081b3ac  pop     rsi
0x10081b3ad  retn
```
