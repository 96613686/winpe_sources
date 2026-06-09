# AddSingleElementToKLLSketch(uchar *,CXVariant *,uchar)

- ea: `0x100819a80`
- end: `0x100819fcf`
- name: `?AddSingleElementToKLLSketch@@YAXPEAEPEAVCXVariant@@E@Z`
- size: `1359`
- prototype: `void __fastcall(unsigned __int8 *, struct CXVariant *, unsigned __int8)`
- caller_count: `21`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1005837d0`
- `0x100583910`
- `0x100583a30`
- `0x100583b50`
- `0x100583c70`
- `0x100583dc0`
- `0x100583ee0`
- `0x100584030`
- `0x100584160`
- `0x1005842d0`
- `0x100584440`
- `0x100584580`
- `0x1005846c0`
- `0x100584800`
- `0x100584980`
- `0x100584ac0`
- `0x100584c40`
- `0x100584d90`
- `0x10081a050`
- `0x10081b3e0`
- `0x10081b4e0`

## callees

- `0x100819a80`
- `0x10081c930`
- `0x10081cfc0`
- `0x10081d670`
- `0x10081dd00`
- `0x10081e3a0`
- `0x10081e9d0`
- `0x10081efa0`
- `0x10081f5c0`
- `0x10081fc00`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100819f8d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100819f8d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819b87`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819c03`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819c7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819cf7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819d73`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819def`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819e69`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819ee6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819f67`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819b87`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819c03`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819c7d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819cf7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819d73`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819def`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819e69`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819ee6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100819f67`
- `sqldk!SystemThread_TlsIndex` at `0x100819ac7`
- `sqldk!SystemThread_TlsOffset` at `0x100819ad1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100819aec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100819aec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100819fa7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100819fa7`

## string_xrefs

- `0x100819b7a`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819bf6`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819c70`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819cea`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819d66`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819de2`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819e5c`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819ed9`: `sql\ntdbms\common\sketches\KLLSketch.h`
- `0x100819f5a`: `sql\ntdbms\common\sketches\KLLSketch.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AddSingleElementToKLLSketch(unsigned __int8 *a1, struct CXVariant *a2, unsigned __int8 a3)
{
  int v3; // r14d
  __int64 v6; // rdi
  __int64 v7; // r10
  struct IMemObj *v8; // r10
  unsigned __int8 v9; // di
  unsigned __int64 v10; // rax
  void *v11; // rbx
  int v12; // esi
  unsigned __int16 v13; // di
  unsigned __int64 v14; // rax
  unsigned int v15; // edi
  unsigned __int64 v16; // rax
  __int64 v17; // rdi
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rax
  unsigned int v21; // ebx
  unsigned __int64 v22; // rax
  void *v23; // rdi
  void *v24; // rcx
  __int64 v25; // rbx
  unsigned __int64 v26; // rax
  void *v27; // rdi
  __int128 v28; // xmm6
  int v29; // edi
  unsigned __int64 v30; // rax
  __int128 v31; // [rsp+48h] [rbp-19h] BYREF
  int v32; // [rsp+58h] [rbp-9h]
  struct IMemObj *v33; // [rsp+68h] [rbp+7h] BYREF
  void *v34; // [rsp+70h] [rbp+Fh]
  unsigned __int8 *v35; // [rsp+80h] [rbp+1Fh]
  unsigned __int8 *v36; // [rsp+88h] [rbp+27h]
  unsigned __int8 *v37; // [rsp+90h] [rbp+2Fh]
  char v38; // [rsp+98h] [rbp+37h]

  v3 = a3;
  if ( *(_BYTE *)a2 != 3 )
  {
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
    }
    v8 = *(struct IMemObj **)(v7 + 1000);
    switch ( v3 )
    {
      case '0':
      case 'h':
        v9 = *((_BYTE *)a2 + 8);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v10 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v10 = -1;
        v11 = operator new[](v10, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<unsigned char>::Update(&v33, v9);
        goto LABEL_32;
      case '4':
        v13 = *((_WORD *)a2 + 4);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v14 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v14 = -1;
        v11 = operator new[](v14, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<short>::Update(&v33, v13);
        goto LABEL_32;
      case '8':
        v15 = *((_DWORD *)a2 + 2);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v16 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v16 = -1;
        v11 = operator new[](v16, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<long>::Update(&v33, v15);
        goto LABEL_32;
      case ';':
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v19 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v19 = -1;
        v11 = operator new[](v19, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<float>::Update(&v33);
        goto LABEL_32;
      case '<':
        v25 = *((_QWORD *)a2 + 1);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v26 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v26 = -1;
        v27 = operator new[](v26, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v27;
        v12 = CKLLSketch<CSsMoney8>::Update(&v33, v25);
        v24 = v27;
        goto LABEL_33;
      case '>':
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v20 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v20 = -1;
        v11 = operator new[](v20, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<double>::Update(&v33);
        goto LABEL_32;
      case 'j':
      case 'l':
        v28 = *(_OWORD *)((char *)a2 + 8);
        v29 = *((_DWORD *)a2 + 6);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v30 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v30 = -1;
        v11 = operator new[](v30, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v31 = v28;
        v32 = v29;
        v12 = CKLLSketch<CSsNumeric>::Update(&v33, &v31);
        goto LABEL_32;
      case 'z':
        v21 = *((_DWORD *)a2 + 2);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v22 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v22 = -1;
        v23 = operator new[](v22, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v23;
        v12 = CKLLSketch<MONY4>::Update(&v33, v21);
        v24 = v23;
        goto LABEL_33;
      case '\x7F':
        v17 = *((_QWORD *)a2 + 1);
        v33 = v8;
        v38 = 1;
        v35 = a1 + 16;
        v36 = a1 + 56;
        v37 = &a1[2 * *((unsigned __int16 *)a1 + 10) + 58];
        v18 = 2LL * *((unsigned __int16 *)a1 + 11);
        if ( !is_mul_ok(*((unsigned __int16 *)a1 + 11), 2u) )
          v18 = -1;
        v11 = operator new[](v18, v8, "sql\\ntdbms\\common\\sketches\\KLLSketch.h", 359, 3u);
        v34 = v11;
        v12 = CKLLSketch<__int64>::Update(&v33, v17);
LABEL_32:
        v24 = v11;
LABEL_33:
        operator delete[](v24);
        if ( v12 )
          goto LABEL_34;
        return;
      default:
LABEL_34:
        ex_raise(98, 36, 16, 11);
        break;
    }
  }
}

```

## disassembly

```asm
0x100819a80  mov     rax, rsp
0x100819a83  push    rbp
0x100819a84  lea     rbp, [rax-5Fh]
0x100819a88  sub     rsp, 0B0h
0x100819a8f  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x100819a97  mov     [rax+8], rbx
0x100819a9b  mov     [rax+10h], rsi
0x100819a9f  mov     [rax+18h], rdi
0x100819aa3  mov     [rax+20h], r14
0x100819aa7  movaps  xmmword ptr [rax-18h], xmm6
0x100819aab  movzx   r14d, r8b
0x100819aaf  mov     rbx, rdx
0x100819ab2  mov     rsi, rcx
0x100819ab5  cmp     byte ptr [rdx], 3
0x100819ab8  jz      loc_100819FAD
0x100819abe  mov     r10, gs:58h
0x100819ac7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100819ace  mov     r9d, [rax]
0x100819ad1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100819ad8  mov     edi, [rax]
0x100819ada  add     rdi, [r10+r9*8]
0x100819ade  mov     r10, [rdi+100h]
0x100819ae5  test    r10, r10
0x100819ae8  jnz     short loc_100819AF9
0x100819aea  xor     ecx, ecx
0x100819aec  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100819af2  mov     r10, [rdi+100h]
0x100819af9  mov     r10, [r10+3E8h]
0x100819b00  lea     eax, [r14-30h]; switch 80 cases
0x100819b04  cmp     eax, 4Fh
0x100819b07  ja      def_100819B28; jumptable 0000000100819B28 default case, cases 49-51,53-55,57,58,61,63-103,105,107,109-121,123-126
0x100819b0d  cdqe
0x100819b0f  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100819b16  movzx   eax, ds:(byte_100819FF8 - 100400000h)[rdx+rax]
0x100819b1e  mov     ecx, ds:(jpt_100819B28 - 100400000h)[rdx+rax*4]
0x100819b25  add     rcx, rdx
0x100819b28  jmp     rcx; switch jump
0x100819b2a  movzx   edi, byte ptr [rbx+8]; jumptable 0000000100819B28 cases 48,104
0x100819b2e  mov     [rbp+57h+var_50], r10
0x100819b32  mov     [rbp+57h+var_20], 1
0x100819b36  lea     r8, [rsi+10h]
0x100819b3a  mov     [rbp+57h+var_38], r8
0x100819b3e  lea     rax, [rsi+38h]
0x100819b42  mov     [rbp+57h+var_30], rax
0x100819b46  movzx   eax, word ptr [r8+4]
0x100819b4b  add     rax, 1Dh
0x100819b4f  lea     rcx, [rsi+rax*2]
0x100819b53  mov     [rbp+57h+var_28], rcx
0x100819b57  movzx   ecx, word ptr [r8+6]
0x100819b5c  mov     eax, 2
0x100819b61  mul     rcx
0x100819b64  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819b6b  cmovo   rax, rcx
0x100819b6f  mov     [rsp+0B0h+var_90], 3
0x100819b74  mov     r9d, 167h
0x100819b7a  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819b81  mov     rdx, r10
0x100819b84  mov     rcx, rax
0x100819b87  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819b8d  mov     rbx, rax
0x100819b90  mov     [rbp+57h+var_48], rax
0x100819b94  movzx   edx, dil
0x100819b98  lea     rcx, [rbp+57h+var_50]
0x100819b9c  call    ?Update@?$CKLLSketch@E@@QEAA?AW4KLLRETCODE@@E@Z; CKLLSketch<uchar>::Update(uchar)
0x100819ba1  mov     esi, eax
0x100819ba3  jmp     loc_100819F8A
0x100819ba8  movzx   edi, word ptr [rbx+8]; jumptable 0000000100819B28 case 52
0x100819bac  mov     [rbp+57h+var_50], r10
0x100819bb0  mov     [rbp+57h+var_20], 1
0x100819bb4  lea     rdx, [rsi+10h]
0x100819bb8  mov     [rbp+57h+var_38], rdx
0x100819bbc  lea     rax, [rsi+38h]
0x100819bc0  mov     [rbp+57h+var_30], rax
0x100819bc4  movzx   eax, word ptr [rdx+4]
0x100819bc8  add     rax, 1Dh
0x100819bcc  lea     rcx, [rsi+rax*2]
0x100819bd0  mov     [rbp+57h+var_28], rcx
0x100819bd4  movzx   ecx, word ptr [rdx+6]
0x100819bd8  mov     eax, 2
0x100819bdd  mul     rcx
0x100819be0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819be7  cmovo   rax, rcx
0x100819beb  mov     [rsp+0B0h+var_90], 3
0x100819bf0  mov     r9d, 167h
0x100819bf6  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819bfd  mov     rdx, r10
0x100819c00  mov     rcx, rax
0x100819c03  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819c09  mov     rbx, rax
0x100819c0c  mov     [rbp+57h+var_48], rax
0x100819c10  movzx   edx, di
0x100819c13  lea     rcx, [rbp+57h+var_50]
0x100819c17  call    ?Update@?$CKLLSketch@F@@QEAA?AW4KLLRETCODE@@F@Z; CKLLSketch<short>::Update(short)
0x100819c1c  mov     esi, eax
0x100819c1e  jmp     loc_100819F8A
0x100819c23  mov     edi, [rbx+8]; jumptable 0000000100819B28 case 56
0x100819c26  mov     [rbp+57h+var_50], r10
0x100819c2a  mov     [rbp+57h+var_20], 1
0x100819c2e  lea     rdx, [rsi+10h]
0x100819c32  mov     [rbp+57h+var_38], rdx
0x100819c36  lea     rax, [rsi+38h]
0x100819c3a  mov     [rbp+57h+var_30], rax
0x100819c3e  movzx   eax, word ptr [rdx+4]
0x100819c42  add     rax, 1Dh
0x100819c46  lea     rcx, [rsi+rax*2]
0x100819c4a  mov     [rbp+57h+var_28], rcx
0x100819c4e  movzx   ecx, word ptr [rdx+6]
0x100819c52  mov     eax, 2
0x100819c57  mul     rcx
0x100819c5a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819c61  cmovo   rax, rcx
0x100819c65  mov     [rsp+0B0h+var_90], 3
0x100819c6a  mov     r9d, 167h
0x100819c70  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819c77  mov     rdx, r10
0x100819c7a  mov     rcx, rax
0x100819c7d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819c83  mov     rbx, rax
0x100819c86  mov     [rbp+57h+var_48], rax
0x100819c8a  mov     edx, edi
0x100819c8c  lea     rcx, [rbp+57h+var_50]
0x100819c90  call    ?Update@?$CKLLSketch@J@@QEAA?AW4KLLRETCODE@@J@Z; CKLLSketch<long>::Update(long)
0x100819c95  mov     esi, eax
0x100819c97  jmp     loc_100819F8A
0x100819c9c  mov     rdi, [rbx+8]; jumptable 0000000100819B28 case 127
0x100819ca0  mov     [rbp+57h+var_50], r10
0x100819ca4  mov     [rbp+57h+var_20], 1
0x100819ca8  lea     rdx, [rsi+10h]
0x100819cac  mov     [rbp+57h+var_38], rdx
0x100819cb0  lea     rax, [rsi+38h]
0x100819cb4  mov     [rbp+57h+var_30], rax
0x100819cb8  movzx   eax, word ptr [rdx+4]
0x100819cbc  add     rax, 1Dh
0x100819cc0  lea     rcx, [rsi+rax*2]
0x100819cc4  mov     [rbp+57h+var_28], rcx
0x100819cc8  movzx   ecx, word ptr [rdx+6]
0x100819ccc  mov     eax, 2
0x100819cd1  mul     rcx
0x100819cd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819cdb  cmovo   rax, rcx
0x100819cdf  mov     [rsp+0B0h+var_90], 3
0x100819ce4  mov     r9d, 167h
0x100819cea  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819cf1  mov     rdx, r10
0x100819cf4  mov     rcx, rax
0x100819cf7  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819cfd  mov     rbx, rax
0x100819d00  mov     [rbp+57h+var_48], rax
0x100819d04  mov     rdx, rdi
0x100819d07  lea     rcx, [rbp+57h+var_50]
0x100819d0b  call    ?Update@?$CKLLSketch@_J@@QEAA?AW4KLLRETCODE@@_J@Z; CKLLSketch<__int64>::Update(__int64)
0x100819d10  mov     esi, eax
0x100819d12  jmp     loc_100819F8A
0x100819d17  movss   xmm6, dword ptr [rbx+8]; jumptable 0000000100819B28 case 59
0x100819d1c  mov     [rbp+57h+var_50], r10
0x100819d20  mov     [rbp+57h+var_20], 1
0x100819d24  lea     rdx, [rsi+10h]
0x100819d28  mov     [rbp+57h+var_38], rdx
0x100819d2c  lea     rax, [rsi+38h]
0x100819d30  mov     [rbp+57h+var_30], rax
0x100819d34  movzx   eax, word ptr [rdx+4]
0x100819d38  add     rax, 1Dh
0x100819d3c  lea     rcx, [rsi+rax*2]
0x100819d40  mov     [rbp+57h+var_28], rcx
0x100819d44  movzx   ecx, word ptr [rdx+6]
0x100819d48  mov     eax, 2
0x100819d4d  mul     rcx
0x100819d50  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819d57  cmovo   rax, rcx
0x100819d5b  mov     [rsp+0B0h+var_90], 3
0x100819d60  mov     r9d, 167h
0x100819d66  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819d6d  mov     rdx, r10
0x100819d70  mov     rcx, rax
0x100819d73  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819d79  mov     rbx, rax
0x100819d7c  mov     [rbp+57h+var_48], rax
0x100819d80  movaps  xmm1, xmm6
0x100819d83  lea     rcx, [rbp+57h+var_50]
0x100819d87  call    ?Update@?$CKLLSketch@M@@QEAA?AW4KLLRETCODE@@M@Z; CKLLSketch<float>::Update(float)
0x100819d8c  mov     esi, eax
0x100819d8e  jmp     loc_100819F8A
0x100819d93  movsd   xmm6, qword ptr [rbx+8]; jumptable 0000000100819B28 case 62
0x100819d98  mov     [rbp+57h+var_50], r10
0x100819d9c  mov     [rbp+57h+var_20], 1
0x100819da0  lea     rdx, [rsi+10h]
0x100819da4  mov     [rbp+57h+var_38], rdx
0x100819da8  lea     rax, [rsi+38h]
0x100819dac  mov     [rbp+57h+var_30], rax
0x100819db0  movzx   eax, word ptr [rdx+4]
0x100819db4  add     rax, 1Dh
0x100819db8  lea     rcx, [rsi+rax*2]
0x100819dbc  mov     [rbp+57h+var_28], rcx
0x100819dc0  movzx   ecx, word ptr [rdx+6]
0x100819dc4  mov     eax, 2
0x100819dc9  mul     rcx
0x100819dcc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819dd3  cmovo   rax, rcx
0x100819dd7  mov     [rsp+0B0h+var_90], 3
0x100819ddc  mov     r9d, 167h
0x100819de2  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819de9  mov     rdx, r10
0x100819dec  mov     rcx, rax
0x100819def  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819df5  mov     rbx, rax
0x100819df8  mov     [rbp+57h+var_48], rax
0x100819dfc  movaps  xmm1, xmm6
0x100819dff  lea     rcx, [rbp+57h+var_50]
0x100819e03  call    ?Update@?$CKLLSketch@N@@QEAA?AW4KLLRETCODE@@N@Z; CKLLSketch<double>::Update(double)
0x100819e08  mov     esi, eax
0x100819e0a  jmp     loc_100819F8A
0x100819e0f  mov     ebx, [rbx+8]; jumptable 0000000100819B28 case 122
0x100819e12  mov     [rbp+57h+var_50], r10
0x100819e16  mov     [rbp+57h+var_20], 1
0x100819e1a  lea     rdx, [rsi+10h]
0x100819e1e  mov     [rbp+57h+var_38], rdx
0x100819e22  lea     rax, [rsi+38h]
0x100819e26  mov     [rbp+57h+var_30], rax
0x100819e2a  movzx   eax, word ptr [rdx+4]
0x100819e2e  add     rax, 1Dh
0x100819e32  lea     rcx, [rsi+rax*2]
0x100819e36  mov     [rbp+57h+var_28], rcx
0x100819e3a  movzx   ecx, word ptr [rdx+6]
0x100819e3e  mov     eax, 2
0x100819e43  mul     rcx
0x100819e46  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819e4d  cmovo   rax, rcx
0x100819e51  mov     [rsp+0B0h+var_90], 3
0x100819e56  mov     r9d, 167h
0x100819e5c  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819e63  mov     rdx, r10
0x100819e66  mov     rcx, rax
0x100819e69  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819e6f  mov     rdi, rax
0x100819e72  mov     [rbp+57h+var_48], rax
0x100819e76  mov     edx, ebx
0x100819e78  lea     rcx, [rbp+57h+var_50]
0x100819e7c  call    ?Update@?$CKLLSketch@UMONY4@@@@QEAA?AW4KLLRETCODE@@UMONY4@@@Z; CKLLSketch<MONY4>::Update(MONY4)
0x100819e81  mov     esi, eax
0x100819e83  mov     rcx, rdi
0x100819e86  jmp     loc_100819F8D
0x100819e8b  mov     rbx, [rbx+8]; jumptable 0000000100819B28 case 60
0x100819e8f  mov     [rbp+57h+var_50], r10
0x100819e93  mov     [rbp+57h+var_20], 1
0x100819e97  lea     rdx, [rsi+10h]
0x100819e9b  mov     [rbp+57h+var_38], rdx
0x100819e9f  lea     rax, [rsi+38h]
0x100819ea3  mov     [rbp+57h+var_30], rax
0x100819ea7  movzx   eax, word ptr [rdx+4]
0x100819eab  add     rax, 1Dh
0x100819eaf  lea     rcx, [rsi+rax*2]
0x100819eb3  mov     [rbp+57h+var_28], rcx
0x100819eb7  movzx   ecx, word ptr [rdx+6]
0x100819ebb  mov     eax, 2
0x100819ec0  mul     rcx
0x100819ec3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819eca  cmovo   rax, rcx
0x100819ece  mov     [rsp+0B0h+var_90], 3
0x100819ed3  mov     r9d, 167h
0x100819ed9  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819ee0  mov     rdx, r10
0x100819ee3  mov     rcx, rax
0x100819ee6  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819eec  mov     rdi, rax
0x100819eef  mov     [rbp+57h+var_48], rax
0x100819ef3  mov     rdx, rbx
0x100819ef6  lea     rcx, [rbp+57h+var_50]
0x100819efa  call    ?Update@?$CKLLSketch@VCSsMoney8@@@@QEAA?AW4KLLRETCODE@@VCSsMoney8@@@Z; CKLLSketch<CSsMoney8>::Update(CSsMoney8)
0x100819eff  mov     esi, eax
0x100819f01  mov     rcx, rdi
0x100819f04  jmp     loc_100819F8D
0x100819f09  movups  xmm6, xmmword ptr [rbx+8]; jumptable 0000000100819B28 cases 106,108
0x100819f0d  mov     edi, [rbx+18h]
0x100819f10  mov     [rbp+57h+var_50], r10
0x100819f14  mov     [rbp+57h+var_20], 1
0x100819f18  lea     rdx, [rsi+10h]
0x100819f1c  mov     [rbp+57h+var_38], rdx
0x100819f20  lea     rax, [rsi+38h]
0x100819f24  mov     [rbp+57h+var_30], rax
0x100819f28  movzx   eax, word ptr [rdx+4]
0x100819f2c  add     rax, 1Dh
0x100819f30  lea     rcx, [rsi+rax*2]
0x100819f34  mov     [rbp+57h+var_28], rcx
0x100819f38  movzx   ecx, word ptr [rdx+6]
0x100819f3c  mov     eax, 2
0x100819f41  mul     rcx
0x100819f44  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100819f4b  cmovo   rax, rcx
0x100819f4f  mov     [rsp+0B0h+var_90], 3
0x100819f54  mov     r9d, 167h
0x100819f5a  lea     r8, aSqlNtdbmsCommo_0; "sql\\ntdbms\\common\\sketches\\KLLSketc"...
0x100819f61  mov     rdx, r10
0x100819f64  mov     rcx, rax
0x100819f67  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100819f6d  mov     rbx, rax
0x100819f70  mov     [rbp+57h+var_48], rax
0x100819f74  movaps  [rbp+57h+var_70], xmm6
0x100819f78  mov     [rbp+57h+var_60], edi
0x100819f7b  lea     rdx, [rbp+57h+var_70]
0x100819f7f  lea     rcx, [rbp+57h+var_50]
  ... truncated ...
```
