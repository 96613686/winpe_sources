# GetQuantileDiscFromKLLSketch(CXVariant *,double,CXVariant *)

- ea: `0x10081abc0`
- end: `0x10081b0a9`
- name: `?GetQuantileDiscFromKLLSketch@@YAXPEAVCXVariant@@N0@Z`
- size: `1257`
- prototype: `void __fastcall(struct CXVariant *, double, struct CXVariant *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10081b790`

## callees

- `0x10081abc0`
- `0x10081b830`
- `0x10081b900`
- `0x10081d100`
- `0x10081d7b0`
- `0x10081de40`
- `0x10081e4e0`
- `0x10081eb10`
- `0x10081f0e0`
- `0x10081f700`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10081ad11`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ad94`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ae17`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ae9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081af20`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081afa7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081b02f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ad11`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ad94`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ae17`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081ae9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081af20`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081afa7`
- `sqldk!??_V@YAXPEAX@Z` at `0x10081b02f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081acf2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ad76`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081adf8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ae7c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081af01`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081af86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081b00e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081acf2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ad76`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081adf8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081ae7c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081af01`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081af86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081b00e`
- `sqldk!SystemThread_TlsIndex` at `0x10081ac21`
- `sqldk!SystemThread_TlsOffset` at `0x10081ac2a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081ac46`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081ac46`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081b077`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10081b077`

## string_xrefs

- `0x10081ace5`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081ad69`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081adeb`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081ae6f`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081aef4`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081af79`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081b001`: `sql\ntdbms\common\sketches\KLLSketch.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall GetQuantileDiscFromKLLSketch(struct CXVariant *a1, double a2, struct CXVariant *a3)
{
  __int64 v4; // rbx
  int v5; // r15d
  __int64 v6; // r14
  __int64 v7; // r10
  struct IMemObj *v8; // r10
  unsigned __int64 v9; // rax
  void *v10; // rdi
  __int16 QuantileDisc; // bx
  unsigned __int64 v12; // rax
  void *v13; // rdi
  int v14; // ebx
  unsigned __int64 v15; // rax
  void *v16; // rdi
  __int64 v17; // rbx
  unsigned __int64 v18; // rax
  void *v19; // rbx
  double v20; // xmm0_8
  unsigned __int64 v21; // rax
  void *v22; // rbx
  double v23; // xmm6_8
  unsigned __int64 v24; // rax
  void *v25; // rbx
  unsigned __int64 v26; // rax
  void *v27; // rbx
  __int128 v28; // [rsp+40h] [rbp-21h] BYREF
  int v29; // [rsp+50h] [rbp-11h]
  struct IMemObj *v30; // [rsp+58h] [rbp-9h] BYREF
  void *v31; // [rsp+60h] [rbp-1h]
  __int64 v32; // [rsp+70h] [rbp+Fh]
  __int64 v33; // [rsp+78h] [rbp+17h]
  __int64 v34; // [rsp+80h] [rbp+1Fh]
  char v35; // [rsp+88h] [rbp+27h]
  __int64 v36; // [rsp+C8h] [rbp+67h] BYREF

  v4 = *((_QWORD *)a1 + 1);
  if ( *(_DWORD *)v4 == -1450139961 && *(_WORD *)(v4 + 42) )
  {
    v5 = *(unsigned __int8 *)(v4 + 16);
    *((_BYTE *)a3 + 1) = v5;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = *(struct IMemObj **)(v7 + 1000);
    switch ( v5 )
    {
      case '0':
      case 'h':
        *((_BYTE *)a3 + 8) = CKLLSketch<unsigned char>::GetQuantileDisc(v8, v4);
        *(_BYTE *)a3 = 0;
        break;
      case '4':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 2 * (*(unsigned __int16 *)(v4 + 20) + 29LL);
        v9 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v9 = -1;
        v10 = operator new[](v9, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v10;
        QuantileDisc = CKLLSketch<short>::GetQuantileDisc(&v30);
        operator delete[](v10);
        *((_WORD *)a3 + 4) = QuantileDisc;
        *(_BYTE *)a3 = 0;
        break;
      case '8':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 2 * (*(unsigned __int16 *)(v4 + 20) + 29LL);
        v12 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v12 = -1;
        v13 = operator new[](v12, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v13;
        v14 = CKLLSketch<long>::GetQuantileDisc(&v30);
        operator delete[](v13);
        *((_DWORD *)a3 + 2) = v14;
        *(_BYTE *)a3 = 0;
        break;
      case ';':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 58 + 2LL * *(unsigned __int16 *)(v4 + 20);
        v18 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v18 = -1;
        v19 = operator new[](v18, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v19;
        v20 = CKLLSketch<float>::GetQuantileDisc(&v30);
        operator delete[](v19);
        *((_DWORD *)a3 + 2) = LODWORD(v20);
        *(_BYTE *)a3 = 0;
        break;
      case '<':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 58 + 2LL * *(unsigned __int16 *)(v4 + 20);
        v26 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v26 = -1;
        v27 = operator new[](v26, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v27;
        CKLLSketch<CSsMoney8>::GetQuantileDisc(&v30, &v36);
        operator delete[](v27);
        *((_QWORD *)a3 + 1) = v36;
        *(_BYTE *)a3 = 0;
        break;
      case '>':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 58 + 2LL * *(unsigned __int16 *)(v4 + 20);
        v21 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v21 = -1;
        v22 = operator new[](v21, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v22;
        v23 = CKLLSketch<double>::GetQuantileDisc(&v30);
        operator delete[](v22);
        *((double *)a3 + 1) = v23;
        *(_BYTE *)a3 = 0;
        break;
      case 'j':
      case 'l':
        CKLLSketch<CSsNumeric>::GetQuantileDisc(&v28, v8, v4);
        *(_OWORD *)((char *)a3 + 8) = v28;
        *((_DWORD *)a3 + 6) = v29;
        *(_BYTE *)a3 = 0;
        break;
      case 'z':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 58 + 2LL * *(unsigned __int16 *)(v4 + 20);
        v24 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v24 = -1;
        v25 = operator new[](v24, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v25;
        CKLLSketch<MONY4>::GetQuantileDisc(&v30, &v36);
        operator delete[](v25);
        *((_DWORD *)a3 + 2) = v36;
        *(_BYTE *)a3 = 0;
        break;
      case '\x7F':
        v30 = v8;
        v35 = 1;
        v32 = v4 + 16;
        v33 = v4 + 56;
        v34 = v4 + 58 + 2LL * *(unsigned __int16 *)(v4 + 20);
        v15 = 2LL * *(unsigned __int16 *)(v4 + 22);
        if ( !is_mul_ok(*(unsigned __int16 *)(v4 + 22), 2u) )
          v15 = -1;
        v16 = operator new[](v15, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v31 = v16;
        v17 = CKLLSketch<__int64>::GetQuantileDisc(&v30);
        operator delete[](v16);
        *((_QWORD *)a3 + 1) = v17;
        *(_BYTE *)a3 = 0;
        break;
      default:
        ex_raise(98, 36, 16, 15);
        *(_BYTE *)a3 = 0;
        break;
    }
  }
  else
  {
    *((_BYTE *)a3 + 1) = 0;
  }
}

```

## disassembly

```asm
0x10081abc0  mov     rax, rsp
0x10081abc3  push    rbp
0x10081abc4  push    r14
0x10081abc6  push    r15
0x10081abc8  lea     rbp, [rax-5Fh]
0x10081abcc  sub     rsp, 0A0h
0x10081abd3  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x10081abdb  mov     [rax+10h], rbx
0x10081abdf  mov     [rax+18h], rsi
0x10081abe3  mov     [rax+20h], rdi
0x10081abe7  movaps  xmmword ptr [rax-28h], xmm6
0x10081abeb  mov     rsi, r8
0x10081abee  movaps  xmm6, xmm1
0x10081abf1  mov     rbx, [rcx+8]
0x10081abf5  cmp     dword ptr [rbx], 0A9909EC7h
0x10081abfb  jnz     loc_10081B082
0x10081ac01  cmp     word ptr [rbx+2Ah], 0
0x10081ac06  jz      loc_10081B082
0x10081ac0c  lea     rdi, [rbx+10h]
0x10081ac10  movzx   r15d, byte ptr [rdi]
0x10081ac14  mov     [r8+1], r15b
0x10081ac18  mov     rdx, gs:58h
0x10081ac21  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10081ac28  mov     ecx, [rax]
0x10081ac2a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10081ac31  mov     r14d, [rax]
0x10081ac34  add     r14, [rdx+rcx*8]
0x10081ac38  mov     r10, [r14+100h]
0x10081ac3f  test    r10, r10
0x10081ac42  jnz     short loc_10081AC53
0x10081ac44  xor     ecx, ecx
0x10081ac46  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10081ac4c  mov     r10, [r14+100h]
0x10081ac53  mov     r10, [r10+3E8h]
0x10081ac5a  lea     eax, [r15-30h]; switch 80 cases
0x10081ac5e  cmp     eax, 4Fh
0x10081ac61  ja      def_10081AC83; jumptable 000000010081AC83 default case, cases 49-51,53-55,57,58,61,63-103,105,107,109-121,123-126
0x10081ac67  cdqe
0x10081ac69  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10081ac70  movzx   eax, ds:(byte_10081B0D4 - 100400000h)[rcx+rax]
0x10081ac78  mov     r8d, ds:(jpt_10081AC83 - 100400000h)[rcx+rax*4]
0x10081ac80  add     r8, rcx
0x10081ac83  jmp     r8; switch jump
0x10081ac86  movaps  xmm2, xmm6; jumptable 000000010081AC83 cases 48,104
0x10081ac89  mov     rdx, rbx
0x10081ac8c  mov     rcx, r10
0x10081ac8f  call    ?GetQuantileDisc@?$CKLLSketch@E@@SAEPEAVIMemObj@@PEAEN@Z; CKLLSketch<uchar>::GetQuantileDisc(IMemObj *,uchar *,double)
0x10081ac94  mov     [rsi+8], al
0x10081ac97  mov     byte ptr [rsi], 0
0x10081ac9a  jmp     loc_10081B087
0x10081ac9f  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 52
0x10081aca3  mov     [rbp+57h+var_30], 1
0x10081aca7  mov     [rbp+57h+var_48], rdi
0x10081acab  lea     rax, [rbx+38h]
0x10081acaf  mov     [rbp+57h+var_40], rax
0x10081acb3  movzx   eax, word ptr [rdi+4]
0x10081acb7  add     rax, 1Dh
0x10081acbb  lea     rcx, [rbx+rax*2]
0x10081acbf  mov     [rbp+57h+var_38], rcx
0x10081acc3  movzx   ecx, word ptr [rdi+6]
0x10081acc7  mov     eax, 2
0x10081accc  mul     rcx
0x10081accf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081acd6  cmovo   rax, rcx
0x10081acda  mov     [rsp+0B0h+var_90], 3
0x10081acdf  mov     r9d, 167h
0x10081ace5  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081acec  mov     rdx, r10
0x10081acef  mov     rcx, rax
0x10081acf2  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081acf8  mov     rdi, rax
0x10081acfb  mov     [rbp+57h+var_58], rax
0x10081acff  movaps  xmm1, xmm6
0x10081ad02  lea     rcx, [rbp+57h+var_60]
0x10081ad06  call    ?GetQuantileDisc@?$CKLLSketch@F@@QEAAFN@Z; CKLLSketch<short>::GetQuantileDisc(double)
0x10081ad0b  movzx   ebx, ax
0x10081ad0e  mov     rcx, rdi
0x10081ad11  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ad17  mov     [rsi+8], bx
0x10081ad1b  mov     byte ptr [rsi], 0
0x10081ad1e  jmp     loc_10081B087
0x10081ad23  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 56
0x10081ad27  mov     [rbp+57h+var_30], 1
0x10081ad2b  mov     [rbp+57h+var_48], rdi
0x10081ad2f  lea     rax, [rbx+38h]
0x10081ad33  mov     [rbp+57h+var_40], rax
0x10081ad37  movzx   eax, word ptr [rdi+4]
0x10081ad3b  add     rax, 1Dh
0x10081ad3f  lea     rcx, [rbx+rax*2]
0x10081ad43  mov     [rbp+57h+var_38], rcx
0x10081ad47  movzx   ecx, word ptr [rdi+6]
0x10081ad4b  mov     eax, 2
0x10081ad50  mul     rcx
0x10081ad53  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ad5a  cmovo   rax, rcx
0x10081ad5e  mov     [rsp+0B0h+var_90], 3
0x10081ad63  mov     r9d, 167h
0x10081ad69  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ad70  mov     rdx, r10
0x10081ad73  mov     rcx, rax
0x10081ad76  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081ad7c  mov     rdi, rax
0x10081ad7f  mov     [rbp+57h+var_58], rax
0x10081ad83  movaps  xmm1, xmm6
0x10081ad86  lea     rcx, [rbp+57h+var_60]
0x10081ad8a  call    ?GetQuantileDisc@?$CKLLSketch@J@@QEAAJN@Z; CKLLSketch<long>::GetQuantileDisc(double)
0x10081ad8f  mov     ebx, eax
0x10081ad91  mov     rcx, rdi
0x10081ad94  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ad9a  mov     [rsi+8], ebx
0x10081ad9d  mov     byte ptr [rsi], 0
0x10081ada0  jmp     loc_10081B087
0x10081ada5  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 127
0x10081ada9  mov     [rbp+57h+var_30], 1
0x10081adad  mov     [rbp+57h+var_48], rdi
0x10081adb1  lea     rax, [rbx+38h]
0x10081adb5  mov     [rbp+57h+var_40], rax
0x10081adb9  movzx   eax, word ptr [rdi+4]
0x10081adbd  add     rbx, 3Ah ; ':'
0x10081adc1  lea     rcx, [rbx+rax*2]
0x10081adc5  mov     [rbp+57h+var_38], rcx
0x10081adc9  movzx   ecx, word ptr [rdi+6]
0x10081adcd  mov     eax, 2
0x10081add2  mul     rcx
0x10081add5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081addc  cmovo   rax, rcx
0x10081ade0  mov     [rsp+0B0h+var_90], 3
0x10081ade5  mov     r9d, 167h
0x10081adeb  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081adf2  mov     rdx, r10
0x10081adf5  mov     rcx, rax
0x10081adf8  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081adfe  mov     rdi, rax
0x10081ae01  mov     [rbp+57h+var_58], rax
0x10081ae05  movaps  xmm1, xmm6
0x10081ae08  lea     rcx, [rbp+57h+var_60]
0x10081ae0c  call    ?GetQuantileDisc@?$CKLLSketch@_J@@QEAA_JN@Z; CKLLSketch<__int64>::GetQuantileDisc(double)
0x10081ae11  mov     rbx, rax
0x10081ae14  mov     rcx, rdi
0x10081ae17  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081ae1d  mov     [rsi+8], rbx
0x10081ae21  mov     byte ptr [rsi], 0
0x10081ae24  jmp     loc_10081B087
0x10081ae29  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 59
0x10081ae2d  mov     [rbp+57h+var_30], 1
0x10081ae31  mov     [rbp+57h+var_48], rdi
0x10081ae35  lea     rax, [rbx+38h]
0x10081ae39  mov     [rbp+57h+var_40], rax
0x10081ae3d  movzx   eax, word ptr [rdi+4]
0x10081ae41  add     rbx, 3Ah ; ':'
0x10081ae45  lea     rcx, [rbx+rax*2]
0x10081ae49  mov     [rbp+57h+var_38], rcx
0x10081ae4d  movzx   ecx, word ptr [rdi+6]
0x10081ae51  mov     eax, 2
0x10081ae56  mul     rcx
0x10081ae59  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081ae60  cmovo   rax, rcx
0x10081ae64  mov     [rsp+0B0h+var_90], 3
0x10081ae69  mov     r9d, 167h
0x10081ae6f  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081ae76  mov     rdx, r10
0x10081ae79  mov     rcx, rax
0x10081ae7c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081ae82  mov     rbx, rax
0x10081ae85  mov     [rbp+57h+var_58], rax
0x10081ae89  movaps  xmm1, xmm6
0x10081ae8c  lea     rcx, [rbp+57h+var_60]
0x10081ae90  call    ?GetQuantileDisc@?$CKLLSketch@M@@QEAAMN@Z; CKLLSketch<float>::GetQuantileDisc(double)
0x10081ae95  movaps  xmm6, xmm0
0x10081ae98  mov     rcx, rbx
0x10081ae9b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081aea1  movss   dword ptr [rsi+8], xmm6
0x10081aea6  mov     byte ptr [rsi], 0
0x10081aea9  jmp     loc_10081B087
0x10081aeae  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 62
0x10081aeb2  mov     [rbp+57h+var_30], 1
0x10081aeb6  mov     [rbp+57h+var_48], rdi
0x10081aeba  lea     rax, [rbx+38h]
0x10081aebe  mov     [rbp+57h+var_40], rax
0x10081aec2  movzx   eax, word ptr [rdi+4]
0x10081aec6  add     rbx, 3Ah ; ':'
0x10081aeca  lea     rcx, [rbx+rax*2]
0x10081aece  mov     [rbp+57h+var_38], rcx
0x10081aed2  movzx   ecx, word ptr [rdi+6]
0x10081aed6  mov     eax, 2
0x10081aedb  mul     rcx
0x10081aede  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081aee5  cmovo   rax, rcx
0x10081aee9  mov     [rsp+0B0h+var_90], 3
0x10081aeee  mov     r9d, 167h
0x10081aef4  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081aefb  mov     rdx, r10
0x10081aefe  mov     rcx, rax
0x10081af01  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081af07  mov     rbx, rax
0x10081af0a  mov     [rbp+57h+var_58], rax
0x10081af0e  movaps  xmm1, xmm6
0x10081af11  lea     rcx, [rbp+57h+var_60]
0x10081af15  call    ?GetQuantileDisc@?$CKLLSketch@N@@QEAANN@Z; CKLLSketch<double>::GetQuantileDisc(double)
0x10081af1a  movaps  xmm6, xmm0
0x10081af1d  mov     rcx, rbx
0x10081af20  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081af26  movsd   qword ptr [rsi+8], xmm6
0x10081af2b  mov     byte ptr [rsi], 0
0x10081af2e  jmp     loc_10081B087
0x10081af33  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 122
0x10081af37  mov     [rbp+57h+var_30], 1
0x10081af3b  mov     [rbp+57h+var_48], rdi
0x10081af3f  lea     rax, [rbx+38h]
0x10081af43  mov     [rbp+57h+var_40], rax
0x10081af47  movzx   eax, word ptr [rdi+4]
0x10081af4b  add     rbx, 3Ah ; ':'
0x10081af4f  lea     rcx, [rbx+rax*2]
0x10081af53  mov     [rbp+57h+var_38], rcx
0x10081af57  movzx   ecx, word ptr [rdi+6]
0x10081af5b  mov     eax, 2
0x10081af60  mul     rcx
0x10081af63  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081af6a  cmovo   rax, rcx
0x10081af6e  mov     [rsp+0B0h+var_90], 3
0x10081af73  mov     r9d, 167h
0x10081af79  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081af80  mov     rdx, r10
0x10081af83  mov     rcx, rax
0x10081af86  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081af8c  mov     rbx, rax
0x10081af8f  mov     [rbp+57h+var_58], rax
0x10081af93  movaps  xmm2, xmm6
0x10081af96  lea     rdx, [rbp+57h+arg_0]
0x10081af9a  lea     rcx, [rbp+57h+var_60]
0x10081af9e  call    ?GetQuantileDisc@?$CKLLSketch@UMONY4@@@@QEAA?AUMONY4@@N@Z; CKLLSketch<MONY4>::GetQuantileDisc(double)
0x10081afa3  nop
0x10081afa4  mov     rcx, rbx
0x10081afa7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081afad  mov     eax, dword ptr [rbp+57h+arg_0]
0x10081afb0  mov     [rsi+8], eax
0x10081afb3  mov     byte ptr [rsi], 0
0x10081afb6  jmp     loc_10081B087
0x10081afbb  mov     [rbp+57h+var_60], r10; jumptable 000000010081AC83 case 60
0x10081afbf  mov     [rbp+57h+var_30], 1
0x10081afc3  mov     [rbp+57h+var_48], rdi
0x10081afc7  lea     rax, [rbx+38h]
0x10081afcb  mov     [rbp+57h+var_40], rax
0x10081afcf  movzx   eax, word ptr [rdi+4]
0x10081afd3  add     rbx, 3Ah ; ':'
0x10081afd7  lea     rcx, [rbx+rax*2]
0x10081afdb  mov     [rbp+57h+var_38], rcx
0x10081afdf  movzx   ecx, word ptr [rdi+6]
0x10081afe3  mov     eax, 2
0x10081afe8  mul     rcx
0x10081afeb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081aff2  cmovo   rax, rcx
0x10081aff6  mov     [rsp+0B0h+var_90], 3
0x10081affb  mov     r9d, 167h
0x10081b001  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081b008  mov     rdx, r10
0x10081b00b  mov     rcx, rax
0x10081b00e  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081b014  mov     rbx, rax
0x10081b017  mov     [rbp+57h+var_58], rax
0x10081b01b  movaps  xmm2, xmm6
0x10081b01e  lea     rdx, [rbp+57h+arg_0]
0x10081b022  lea     rcx, [rbp+57h+var_60]
0x10081b026  call    ?GetQuantileDisc@?$CKLLSketch@VCSsMoney8@@@@QEAA?AVCSsMoney8@@N@Z; CKLLSketch<CSsMoney8>::GetQuantileDisc(double)
0x10081b02b  nop
0x10081b02c  mov     rcx, rbx
0x10081b02f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081b035  mov     rax, [rbp+57h+arg_0]
0x10081b039  mov     [rsi+8], rax
0x10081b03d  mov     byte ptr [rsi], 0
0x10081b040  jmp     short loc_10081B087
0x10081b042  movaps  xmm3, xmm6; jumptable 000000010081AC83 cases 106,108
0x10081b045  mov     r8, rbx
0x10081b048  mov     rdx, r10
0x10081b04b  lea     rcx, [rbp+57h+var_78]
0x10081b04f  call    ?GetQuantileDisc@?$CKLLSketch@VCSsNumeric@@@@SA?AVCSsNumeric@@PEAVIMemObj@@PEAEN@Z; CKLLSketch<CSsNumeric>::GetQuantileDisc(IMemObj *,uchar *,double)
0x10081b054  movups  xmm0, [rbp+57h+var_78]
0x10081b058  movups  xmmword ptr [rsi+8], xmm0
0x10081b05c  mov     eax, [rbp+57h+var_68]
0x10081b05f  mov     [rsi+18h], eax
0x10081b062  mov     byte ptr [rsi], 0
0x10081b065  jmp     short loc_10081B087
0x10081b067  mov     edx, 24h ; '$'; jumptable 000000010081AC83 default case, cases 49-51,53-55,57,58,61,63-103,105,107,109-121,123-126
0x10081b06c  lea     ecx, [rdx+3Eh]
0x10081b06f  lea     r9d, [rdx-15h]
0x10081b073  lea     r8d, [rdx-14h]
0x10081b077  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10081b07d  mov     byte ptr [rsi], 0
0x10081b080  jmp     short loc_10081B087
0x10081b082  mov     byte ptr [r8+1], 0
0x10081b087  lea     r11, [rsp+0B0h+var_10]
0x10081b08f  mov     rbx, [r11+28h]
0x10081b093  mov     rsi, [r11+30h]
0x10081b097  mov     rdi, [r11+38h]
0x10081b09b  movaps  xmm6, xmmword ptr [r11-10h]
0x10081b0a0  mov     rsp, r11
0x10081b0a3  pop     r15
0x10081b0a5  pop     r14
0x10081b0a7  pop     rbp
0x10081b0a8  retn
  ... truncated ...
```
