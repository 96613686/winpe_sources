# KLLSketchNeedAccumResize(uchar *,uchar,ulong &)

- ea: `0x100818340`
- end: `0x10081882b`
- name: `?KLLSketchNeedAccumResize@@YAHPEAEEAEAK@Z`
- size: `1259`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1008194b0`

## callees

- `0x100818340`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100818447`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008187c4`
- `sqldk!??_V@YAXPEAX@Z` at `0x100818447`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008187c4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818432`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008184b0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081851b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818589`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008185f7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818665`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008186d3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818741`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008187af`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818432`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008184b0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10081851b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818589`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008185f7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818665`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008186d3`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100818741`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1008187af`
- `sqldk!SystemThread_TlsIndex` at `0x100818376`
- `sqldk!SystemThread_TlsOffset` at `0x100818380`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081839b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10081839b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100818809`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100818809`

## string_xrefs

- `0x100818425`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x1008184a3`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081850e`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x10081857c`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x1008185ea`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100818658`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x1008186c6`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100818734`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x1008187a2`: `sql\ntdbms\common\sketches\KLLSketch.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall KLLSketchNeedAccumResize(unsigned __int8 *a1, unsigned __int8 a2, unsigned int *a3)
{
  int v4; // r15d
  __int64 v6; // rdi
  __int64 v7; // r10
  struct IMemObj *v8; // r10
  unsigned int v9; // esi
  unsigned __int8 *v10; // rdi
  unsigned __int64 v11; // rax
  void *v12; // rax
  __int64 v13; // rbx
  unsigned __int64 v14; // rdi
  bool v15; // cf
  unsigned __int8 *v16; // rdi
  unsigned __int64 v17; // rax
  __int64 v18; // rbx
  unsigned __int64 v19; // rdi
  __int64 result; // rax
  void *v21; // [rsp+40h] [rbp-30h]

  v4 = a2;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(struct IMemObj **)(v7 + 1000);
  v9 = 0;
  switch ( v4 )
  {
    case '0':
    case 'h':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case '4':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case '8':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case ';':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case '<':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case '>':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case 'j':
    case 'l':
      v16 = a1 + 16;
      v17 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v17 = -1;
      v21 = operator new[](v17, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
      v18 = *((_QWORD *)a1 + 6);
      v19 = *((_QWORD *)v16 + 2);
      operator delete[](v21);
      v15 = v19 < v18 + 1;
      goto LABEL_31;
    case 'z':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
      goto LABEL_6;
    case '\x7F':
      v10 = a1 + 16;
      v11 = 2LL * *((unsigned __int16 *)a1 + 11);
      if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
        v11 = -1;
LABEL_6:
      v12 = operator new[](v11, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
      v13 = *((_QWORD *)v10 + 4);
      v14 = *((_QWORD *)v10 + 2);
      operator delete[](v12);
      v15 = v14 < v13 + 1;
LABEL_31:
      LOBYTE(v9) = v15;
      result = v9;
      if ( v9 )
        *a3 += 1024;
      break;
    default:
      utassert_fail(1u, "FALSE", "ApproxAggEsIntrinsic.cpp", 2083, "Invalid switch value");
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x100818340  mov     rax, rsp
0x100818343  push    rbp
0x100818344  push    r14
0x100818346  push    r15
0x100818348  mov     rbp, rsp
0x10081834b  sub     rsp, 70h
0x10081834f  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x100818357  mov     [rax+8], rbx
0x10081835b  mov     [rax+10h], rsi
0x10081835f  mov     [rax+18h], rdi
0x100818363  mov     r14, r8
0x100818366  movzx   r15d, dl
0x10081836a  mov     rbx, rcx
0x10081836d  mov     r10, gs:58h
0x100818376  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10081837d  mov     r9d, [rax]
0x100818380  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100818387  mov     edi, [rax]
0x100818389  add     rdi, [r10+r9*8]
0x10081838d  mov     r10, [rdi+100h]
0x100818394  test    r10, r10
0x100818397  jnz     short loc_1008183A8
0x100818399  xor     ecx, ecx
0x10081839b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1008183a1  mov     r10, [rdi+100h]
0x1008183a8  mov     r10, [r10+3E8h]
0x1008183af  xor     esi, esi
0x1008183b1  lea     eax, [r15-30h]; switch 80 cases
0x1008183b5  cmp     eax, 4Fh
0x1008183b8  ja      def_1008183D9; jumptable 00000001008183D9 default case, cases 49-51,53-55,57,58,61,63-103,105,107,109-121,123-126
0x1008183be  cdqe
0x1008183c0  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1008183c7  movzx   eax, ds:(byte_100818854 - 100400000h)[rdx+rax]
0x1008183cf  mov     ecx, ds:(jpt_1008183D9 - 100400000h)[rdx+rax*4]
0x1008183d6  add     rcx, rdx
0x1008183d9  jmp     rcx; switch jump
0x1008183db  mov     [rbp+var_38], r10; jumptable 00000001008183D9 cases 48,104
0x1008183df  mov     [rbp+var_8], 1
0x1008183e3  lea     rdi, [rbx+10h]
0x1008183e7  mov     [rbp+var_20], rdi
0x1008183eb  lea     rax, [rbx+38h]
0x1008183ef  mov     [rbp+var_18], rax
0x1008183f3  movzx   eax, word ptr [rdi+4]
0x1008183f7  add     rbx, 3Ah ; ':'
0x1008183fb  lea     rcx, [rbx+rax*2]
0x1008183ff  mov     [rbp+var_10], rcx
0x100818403  movzx   ecx, word ptr [rdi+6]
0x100818407  mov     eax, 2
0x10081840c  mul     rcx
0x10081840f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100818416  cmovo   rax, rcx
0x10081841a  mov     byte ptr [rsp+70h+var_50], 3
0x10081841f  mov     r9d, 167h
0x100818425  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081842c  mov     rdx, r10
0x10081842f  mov     rcx, rax
0x100818432  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100818438  mov     [rbp+var_30], rax
0x10081843c  mov     rbx, [rdi+20h]
0x100818440  mov     rdi, [rdi+10h]
0x100818444  mov     rcx, rax
0x100818447  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10081844d  lea     rax, [rbx+1]
0x100818451  cmp     rdi, rax
0x100818454  jmp     loc_1008187D1
0x100818459  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 52
0x10081845d  mov     [rbp+var_8], 1
0x100818461  lea     rdi, [rbx+10h]
0x100818465  mov     [rbp+var_20], rdi
0x100818469  lea     rax, [rbx+38h]
0x10081846d  mov     [rbp+var_18], rax
0x100818471  movzx   eax, word ptr [rdi+4]
0x100818475  add     rbx, 3Ah ; ':'
0x100818479  lea     rcx, [rbx+rax*2]
0x10081847d  mov     [rbp+var_10], rcx
0x100818481  movzx   ecx, word ptr [rdi+6]
0x100818485  mov     eax, 2
0x10081848a  mul     rcx
0x10081848d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100818494  cmovo   rax, rcx
0x100818498  mov     byte ptr [rsp+70h+var_50], 3
0x10081849d  mov     r9d, 167h
0x1008184a3  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x1008184aa  mov     rdx, r10
0x1008184ad  mov     rcx, rax
0x1008184b0  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1008184b6  mov     [rbp+var_30], rax
0x1008184ba  mov     rbx, [rdi+20h]
0x1008184be  mov     rdi, [rdi+10h]
0x1008184c2  jmp     short loc_100818444
0x1008184c4  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 56
0x1008184c8  mov     [rbp+var_8], 1
0x1008184cc  lea     rdi, [rbx+10h]
0x1008184d0  mov     [rbp+var_20], rdi
0x1008184d4  lea     rax, [rbx+38h]
0x1008184d8  mov     [rbp+var_18], rax
0x1008184dc  movzx   eax, word ptr [rdi+4]
0x1008184e0  add     rbx, 3Ah ; ':'
0x1008184e4  lea     rcx, [rbx+rax*2]
0x1008184e8  mov     [rbp+var_10], rcx
0x1008184ec  movzx   ecx, word ptr [rdi+6]
0x1008184f0  mov     eax, 2
0x1008184f5  mul     rcx
0x1008184f8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1008184ff  cmovo   rax, rcx
0x100818503  mov     byte ptr [rsp+70h+var_50], 3
0x100818508  mov     r9d, 167h
0x10081850e  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100818515  mov     rdx, r10
0x100818518  mov     rcx, rax
0x10081851b  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100818521  mov     [rbp+var_30], rax
0x100818525  mov     rbx, [rdi+20h]
0x100818529  mov     rdi, [rdi+10h]
0x10081852d  jmp     loc_100818444
0x100818532  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 127
0x100818536  mov     [rbp+var_8], 1
0x10081853a  lea     rdi, [rbx+10h]
0x10081853e  mov     [rbp+var_20], rdi
0x100818542  lea     rax, [rbx+38h]
0x100818546  mov     [rbp+var_18], rax
0x10081854a  movzx   eax, word ptr [rdi+4]
0x10081854e  add     rbx, 3Ah ; ':'
0x100818552  lea     rcx, [rbx+rax*2]
0x100818556  mov     [rbp+var_10], rcx
0x10081855a  movzx   ecx, word ptr [rdi+6]
0x10081855e  mov     eax, 2
0x100818563  mul     rcx
0x100818566  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10081856d  cmovo   rax, rcx
0x100818571  mov     byte ptr [rsp+70h+var_50], 3
0x100818576  mov     r9d, 167h
0x10081857c  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100818583  mov     rdx, r10
0x100818586  mov     rcx, rax
0x100818589  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081858f  mov     [rbp+var_30], rax
0x100818593  mov     rbx, [rdi+20h]
0x100818597  mov     rdi, [rdi+10h]
0x10081859b  jmp     loc_100818444
0x1008185a0  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 59
0x1008185a4  mov     [rbp+var_8], 1
0x1008185a8  lea     rdi, [rbx+10h]
0x1008185ac  mov     [rbp+var_20], rdi
0x1008185b0  lea     rax, [rbx+38h]
0x1008185b4  mov     [rbp+var_18], rax
0x1008185b8  movzx   eax, word ptr [rdi+4]
0x1008185bc  add     rbx, 3Ah ; ':'
0x1008185c0  lea     rcx, [rbx+rax*2]
0x1008185c4  mov     [rbp+var_10], rcx
0x1008185c8  movzx   ecx, word ptr [rdi+6]
0x1008185cc  mov     eax, 2
0x1008185d1  mul     rcx
0x1008185d4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1008185db  cmovo   rax, rcx
0x1008185df  mov     byte ptr [rsp+70h+var_50], 3
0x1008185e4  mov     r9d, 167h
0x1008185ea  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x1008185f1  mov     rdx, r10
0x1008185f4  mov     rcx, rax
0x1008185f7  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1008185fd  mov     [rbp+var_30], rax
0x100818601  mov     rbx, [rdi+20h]
0x100818605  mov     rdi, [rdi+10h]
0x100818609  jmp     loc_100818444
0x10081860e  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 62
0x100818612  mov     [rbp+var_8], 1
0x100818616  lea     rdi, [rbx+10h]
0x10081861a  mov     [rbp+var_20], rdi
0x10081861e  lea     rax, [rbx+38h]
0x100818622  mov     [rbp+var_18], rax
0x100818626  movzx   eax, word ptr [rdi+4]
0x10081862a  add     rbx, 3Ah ; ':'
0x10081862e  lea     rcx, [rbx+rax*2]
0x100818632  mov     [rbp+var_10], rcx
0x100818636  movzx   ecx, word ptr [rdi+6]
0x10081863a  mov     eax, 2
0x10081863f  mul     rcx
0x100818642  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100818649  cmovo   rax, rcx
0x10081864d  mov     byte ptr [rsp+70h+var_50], 3
0x100818652  mov     r9d, 167h
0x100818658  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081865f  mov     rdx, r10
0x100818662  mov     rcx, rax
0x100818665  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10081866b  mov     [rbp+var_30], rax
0x10081866f  mov     rbx, [rdi+20h]
0x100818673  mov     rdi, [rdi+10h]
0x100818677  jmp     loc_100818444
0x10081867c  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 122
0x100818680  mov     [rbp+var_8], 1
0x100818684  lea     rdi, [rbx+10h]
0x100818688  mov     [rbp+var_20], rdi
0x10081868c  lea     rax, [rbx+38h]
0x100818690  mov     [rbp+var_18], rax
0x100818694  movzx   eax, word ptr [rdi+4]
0x100818698  add     rbx, 3Ah ; ':'
0x10081869c  lea     rcx, [rbx+rax*2]
0x1008186a0  mov     [rbp+var_10], rcx
0x1008186a4  movzx   ecx, word ptr [rdi+6]
0x1008186a8  mov     eax, 2
0x1008186ad  mul     rcx
0x1008186b0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1008186b7  cmovo   rax, rcx
0x1008186bb  mov     byte ptr [rsp+70h+var_50], 3
0x1008186c0  mov     r9d, 167h
0x1008186c6  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x1008186cd  mov     rdx, r10
0x1008186d0  mov     rcx, rax
0x1008186d3  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1008186d9  mov     [rbp+var_30], rax
0x1008186dd  mov     rbx, [rdi+20h]
0x1008186e1  mov     rdi, [rdi+10h]
0x1008186e5  jmp     loc_100818444
0x1008186ea  mov     [rbp+var_38], r10; jumptable 00000001008183D9 case 60
0x1008186ee  mov     [rbp+var_8], 1
0x1008186f2  lea     rdi, [rbx+10h]
0x1008186f6  mov     [rbp+var_20], rdi
0x1008186fa  lea     rax, [rbx+38h]
0x1008186fe  mov     [rbp+var_18], rax
0x100818702  movzx   eax, word ptr [rdi+4]
0x100818706  add     rbx, 3Ah ; ':'
0x10081870a  lea     rcx, [rbx+rax*2]
0x10081870e  mov     [rbp+var_10], rcx
0x100818712  movzx   ecx, word ptr [rdi+6]
0x100818716  mov     eax, 2
0x10081871b  mul     rcx
0x10081871e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100818725  cmovo   rax, rcx
0x100818729  mov     byte ptr [rsp+70h+var_50], 3
0x10081872e  mov     r9d, 167h
0x100818734  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x10081873b  mov     rdx, r10
0x10081873e  mov     rcx, rax
0x100818741  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100818747  mov     [rbp+var_30], rax
0x10081874b  mov     rbx, [rdi+20h]
0x10081874f  mov     rdi, [rdi+10h]
0x100818753  jmp     loc_100818444
0x100818758  mov     [rbp+var_38], r10; jumptable 00000001008183D9 cases 106,108
0x10081875c  mov     [rbp+var_8], 1
0x100818760  lea     rdi, [rbx+10h]
0x100818764  mov     [rbp+var_20], rdi
0x100818768  lea     rax, [rbx+38h]
0x10081876c  mov     [rbp+var_18], rax
0x100818770  movzx   eax, word ptr [rdi+4]
0x100818774  add     rbx, 3Ah ; ':'
0x100818778  lea     rcx, [rbx+rax*2]
0x10081877c  mov     [rbp+var_10], rcx
0x100818780  movzx   ecx, word ptr [rdi+6]
0x100818784  mov     eax, 2
0x100818789  mul     rcx
0x10081878c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100818793  cmovo   rax, rcx
0x100818797  mov     byte ptr [rsp+70h+var_50], 3
0x10081879c  mov     r9d, 167h
0x1008187a2  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x1008187a9  mov     rdx, r10
0x1008187ac  mov     rcx, rax
0x1008187af  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1008187b5  mov     [rbp+var_30], rax
0x1008187b9  mov     rbx, [rdi+20h]
0x1008187bd  mov     rdi, [rdi+10h]
0x1008187c1  mov     rcx, rax
0x1008187c4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1008187ca  lea     rcx, [rbx+1]
0x1008187ce  cmp     rdi, rcx
0x1008187d1  setb    sil
0x1008187d5  mov     eax, esi
0x1008187d7  test    esi, esi
0x1008187d9  jz      short loc_100818811
0x1008187db  add     dword ptr [r14], 400h
0x1008187e2  jmp     short loc_100818811
0x1008187e4  lea     rax, aInvalidSwitchV; jumptable 00000001008183D9 default case, cases 49-51,53-55,57,58,61,63-103,105,107,109-121,123-126
0x1008187eb  mov     [rsp+70h+var_50], rax
0x1008187f0  mov     r9d, 823h
0x1008187f6  lea     r8, aApproxaggesint; "ApproxAggEsIntrinsic.cpp"
0x1008187fd  lea     rdx, aFalse_0; "FALSE"
0x100818804  mov     ecx, 1
0x100818809  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10081880f  mov     eax, esi
0x100818811  lea     r11, [rsp+70h+var_s0]
0x100818816  mov     rbx, [r11+20h]
0x10081881a  mov     rsi, [r11+28h]
0x10081881e  mov     rdi, [r11+30h]
0x100818822  mov     rsp, r11
0x100818825  pop     r15
0x100818827  pop     r14
0x100818829  pop     rbp
0x10081882a  retn
```
