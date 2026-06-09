# _anonymous_namespace_::FGetRangeFromLOB

- ea: `0x100486df0`
- end: `0x10048716a`
- name: `_anonymous_namespace_::FGetRangeFromLOB`
- size: `890`
- prototype: `__int64 __usercall@<rax>(CTypeInfo *this@<rcx>, size_t, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100409500`

## callees

- `0x1004011fc`
- `0x100401cc0`
- `0x100421b80`
- `0x100486be0`
- `0x100486df0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100487102`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048710c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100487147`
- `sqldk!??_V@YAXPEAX@Z` at `0x100487102`
- `sqldk!??_V@YAXPEAX@Z` at `0x10048710c`
- `sqldk!??_V@YAXPEAX@Z` at `0x100487147`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486e88`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100487025`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048704c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486e88`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100487025`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10048704c`
- `sqldk!SystemThread_TlsIndex` at `0x100486e2a`
- `sqldk!SystemThread_TlsOffset` at `0x100486e33`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100486e4e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100486e4e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100486eca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100486eca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::FGetRangeFromLOB(
        CTypeInfo *this,
        __int64 a2,
        __int64 a3,
        char *a4,
        size_t a5,
        __int64 a6,
        int a7,
        _DWORD *a8)
{
  __int64 v11; // rbx
  __int64 v12; // rax
  struct IMemObj *v13; // r13
  size_t v14; // rsi
  unsigned int v15; // edi
  void *v16; // r12
  unsigned int v17; // ebp
  bool v18; // cc
  __int64 v19; // rcx
  char *v20; // rcx
  int v21; // edx
  bool v22; // zf
  unsigned __int16 v23; // dx
  unsigned int v24; // edi
  char *v25; // r13
  char *v26; // rdi
  char v27; // al
  __int64 v28; // rcx
  unsigned int v30; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-64h] BYREF
  struct IMemObj *v32; // [rsp+58h] [rbp-60h]
  __int64 v33; // [rsp+60h] [rbp-58h]
  void *v34; // [rsp+68h] [rbp-50h]
  char *v35; // [rsp+70h] [rbp-48h]
  char *v36; // [rsp+78h] [rbp-40h]
  bool v37; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+10h] BYREF
  size_t Size; // [rsp+D0h] [rbp+18h] BYREF

  v38 = a2;
  v33 = -2;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = *(struct IMemObj **)(v12 + 1000);
  v32 = v13;
  v14 = (unsigned int)a5;
  v15 = a5 + 2;
  v16 = operator new[]((unsigned int)(a5 + 2), v13, "sql\\ntdbms\\msql\\typesystem\\es_util.cpp", 541, 6u);
  v34 = v16;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, void *, _QWORD, size_t *))(*(_QWORD *)a3 + 24LL))(
         a3,
         0,
         v16,
         v15,
         &Size) )
  {
    ex_raise(71, 2, 20, 99);
  }
  v17 = 1;
  LODWORD(v38) = 0;
  v18 = (unsigned int)Size <= (unsigned int)v14;
  _mm_lfence();
  if ( v18 )
  {
    LODWORD(v14) = Size;
    memmove(a4, v16, (unsigned int)Size);
    goto LABEL_31;
  }
  memmove(a4, v16, v14);
  v19 = *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)this);
  if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsBinary + v19) )
  {
    v22 = *((_BYTE *)&CTypeInfo::sxm_rgfIsWString + v19) == 0;
    _mm_lfence();
    if ( !v22 )
    {
      v17 = anonymous_namespace_::FGetRangeWChar(this, a4, v14, (__int64)&v38, (__int64)a8);
      LODWORD(v14) = v38;
      goto LABEL_31;
    }
    v23 = *((_WORD *)this + 8);
    if ( v23 == 0xFFFF
      || *((_BYTE *)&CTypeInfo::sxm_rgfIsLargeObject + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *(unsigned __int8 *)this)) )
    {
      v23 = 8100;
    }
    v24 = v23;
    v25 = (char *)operator new[](v23, v13, "sql\\ntdbms\\msql\\typesystem\\es_util.cpp", 619, 6u);
    v35 = v25;
    v26 = (char *)operator new[](v24, v32, "sql\\ntdbms\\msql\\typesystem\\es_util.cpp", 620, 6u);
    v36 = v26;
    CTypeInfo::GetMbcsRange(this, a4, v14 - 1, v14, v25, (int *)&v30, (bool *)&a5, v26, (int *)&v31, &v37);
    *a8 = 1;
    if ( a7 )
    {
      v17 = (unsigned __int8)a5;
      if ( (_BYTE)a5 )
      {
        LODWORD(v14) = v30;
        memmove(a4, v25, v30);
LABEL_30:
        operator delete[](v26);
        operator delete[](v25);
        goto LABEL_31;
      }
    }
    else
    {
      v17 = v37;
      if ( v37 )
      {
        LODWORD(v14) = v31;
        memmove(a4, v26, v31);
        goto LABEL_30;
      }
    }
    LODWORD(v14) = v38;
    goto LABEL_30;
  }
  if ( !a7 )
  {
    v20 = &a4[v14 - 1];
    v21 = v14;
    if ( (_DWORD)v14 )
    {
      while ( *v20 == -1 )
      {
        --v20;
        if ( !--v21 )
          goto LABEL_14;
      }
      ++*v20;
    }
LABEL_14:
    if ( v21 )
    {
      if ( v21 != (_DWORD)v14 )
        memset_0(v20 + 1, 0, (unsigned int)(v14 - v21));
      *a8 = 0;
    }
    else
    {
      v17 = 0;
    }
  }
LABEL_31:
  v27 = *(_BYTE *)this;
  v28 = a6;
  *(_WORD *)(a6 + 2) = 0;
  *(_BYTE *)v28 = 3;
  *(_BYTE *)(v28 + 1) = v27;
  *(_QWORD *)(v28 + 8) = 0;
  *(_QWORD *)(v28 + 16) = 0;
  *(_DWORD *)(v28 + 24) = 0;
  if ( v17 )
  {
    *(_QWORD *)(v28 + 8) = a4;
    *(_QWORD *)(v28 + 16) = (unsigned int)v14;
    *(_BYTE *)v28 = 0;
  }
  operator delete[](v16);
  return v17;
}

```

## disassembly

```asm
0x100486df0  mov     [rsp+arg_8], rdx
0x100486df5  push    rbp
0x100486df6  push    rsi
0x100486df7  push    rdi
0x100486df8  push    r12
0x100486dfa  push    r13
0x100486dfc  push    r14
0x100486dfe  push    r15
0x100486e00  sub     rsp, 80h
0x100486e07  mov     [rsp+0B8h+var_58], 0FFFFFFFFFFFFFFFEh
0x100486e10  mov     [rsp+0B8h+arg_18], rbx
0x100486e18  mov     r14, r9
0x100486e1b  mov     rbp, r8
0x100486e1e  mov     r15, rcx
0x100486e21  mov     r10, gs:58h
0x100486e2a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100486e31  mov     edx, [rax]
0x100486e33  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100486e3a  mov     ebx, [rax]
0x100486e3c  add     rbx, [r10+rdx*8]
0x100486e40  mov     rax, [rbx+100h]
0x100486e47  test    rax, rax
0x100486e4a  jnz     short loc_100486E5B
0x100486e4c  xor     ecx, ecx
0x100486e4e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100486e54  mov     rax, [rbx+100h]
0x100486e5b  mov     r13, [rax+3E8h]
0x100486e62  mov     [rsp+0B8h+var_60], r13
0x100486e67  mov     esi, dword ptr [rsp+0B8h+arg_20]
0x100486e6e  lea     edi, [rsi+2]
0x100486e71  mov     ecx, edi
0x100486e73  mov     byte ptr [rsp+0B8h+var_98], 6
0x100486e78  mov     r9d, 21Dh
0x100486e7e  lea     r8, aSqlNtdbmsMsqlT_5; "sql\\ntdbms\\msql\\typesystem\\es_util."...
0x100486e85  mov     rdx, r13
0x100486e88  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100486e8e  mov     r12, rax
0x100486e91  mov     [rsp+0B8h+var_50], rax
0x100486e96  xor     ebx, ebx
0x100486e98  mov     r10, [rbp+0]
0x100486e9c  lea     rax, [rsp+0B8h+Size]
0x100486ea4  mov     [rsp+0B8h+var_98], rax
0x100486ea9  mov     r9d, edi
0x100486eac  mov     r8, r12
0x100486eaf  mov     edx, ebx
0x100486eb1  mov     rcx, rbp
0x100486eb4  call    qword ptr [r10+18h]
0x100486eb8  test    eax, eax
0x100486eba  jz      short loc_100486ED0
0x100486ebc  lea     edx, [rbx+2]
0x100486ebf  lea     ecx, [rbx+47h]
0x100486ec2  lea     r9d, [rbx+63h]
0x100486ec6  lea     r8d, [rbx+14h]
0x100486eca  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100486ed0  mov     ebp, 1
0x100486ed5  mov     dword ptr [rsp+0B8h+arg_8], ebx
0x100486edc  mov     rdx, r12; Src
0x100486edf  mov     rcx, r14; void *
0x100486ee2  cmp     dword ptr [rsp+0B8h+Size], esi
0x100486ee9  lfence
0x100486eec  ja      short loc_100486F02
0x100486eee  mov     esi, dword ptr [rsp+0B8h+Size]
0x100486ef5  mov     r8d, esi; Size
0x100486ef8  call    memmove
0x100486efd  jmp     loc_100487112
0x100486f02  mov     r8, rsi; Size
0x100486f05  call    memmove
0x100486f0a  movzx   eax, byte ptr [r15]
0x100486f0e  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100486f15  movzx   ecx, byte ptr [rax+r8+45AE60h]
0x100486f1e  cmp     [rcx+r8+45BE40h], bl
0x100486f26  jz      short loc_100486F85
0x100486f28  cmp     [rsp+0B8h+arg_30], ebx
0x100486f2f  jnz     loc_100487112
0x100486f35  lea     rcx, [rsi-1]
0x100486f39  add     rcx, r14
0x100486f3c  mov     edx, esi
0x100486f3e  test    esi, esi
0x100486f40  jz      short loc_100486F57
0x100486f42  movzx   eax, byte ptr [rcx]
0x100486f45  cmp     al, 0FFh
0x100486f47  jnz     short loc_100486F53
0x100486f49  dec     rcx
0x100486f4c  add     edx, 0FFFFFFFFh
0x100486f4f  jnz     short loc_100486F42
0x100486f51  jmp     short loc_100486F57
0x100486f53  inc     al
0x100486f55  mov     [rcx], al
0x100486f57  test    edx, edx
0x100486f59  jz      short loc_100486F7E
0x100486f5b  cmp     edx, esi
0x100486f5d  jz      short loc_100486F6F
0x100486f5f  mov     r8d, esi
0x100486f62  sub     r8d, edx; Size
0x100486f65  inc     rcx; void *
0x100486f68  xor     edx, edx; Val
0x100486f6a  call    memset_0
0x100486f6f  mov     rax, [rsp+0B8h+arg_38]
0x100486f77  mov     [rax], ebx
0x100486f79  jmp     loc_100487112
0x100486f7e  mov     ebp, ebx
0x100486f80  jmp     loc_100487112
0x100486f85  cmp     [rcx+r8+4642E0h], bl
0x100486f8d  lfence
0x100486f90  jz      short loc_100486FE0
0x100486f92  mov     r9d, dword ptr [rsp+0B8h+Size]
0x100486f9a  shr     r9d, 1
0x100486f9d  mov     rax, [rsp+0B8h+arg_38]
0x100486fa5  mov     [rsp+0B8h+var_80], rax; __int64
0x100486faa  lea     rax, [rsp+0B8h+arg_8]
0x100486fb2  mov     [rsp+0B8h+var_88], rax; __int64
0x100486fb7  mov     dword ptr [rsp+0B8h+var_90], esi; int
0x100486fbb  mov     [rsp+0B8h+var_98], r14; void *
0x100486fc0  mov     r8, r12
0x100486fc3  mov     edx, [rsp+0B8h+arg_30]
0x100486fca  mov     rcx, r15; this
0x100486fcd  call    _anonymous_namespace___FGetRangeWChar
0x100486fd2  mov     ebp, eax
0x100486fd4  mov     esi, dword ptr [rsp+0B8h+arg_8]
0x100486fdb  jmp     loc_100487112
0x100486fe0  movzx   edx, word ptr [r15+10h]
0x100486fe5  mov     eax, 0FFFFh
0x100486fea  cmp     dx, ax
0x100486fed  jz      short loc_100487006
0x100486fef  movzx   eax, byte ptr [r15]
0x100486ff3  movzx   ecx, byte ptr [rax+r8+45AE60h]
0x100486ffc  cmp     [rcx+r8+4F3B00h], bl
0x100487004  jz      short loc_10048700B
0x100487006  mov     edx, 1FA4h
0x10048700b  movzx   edi, dx
0x10048700e  mov     byte ptr [rsp+0B8h+var_98], 6
0x100487013  mov     r9d, 26Bh
0x100487019  lea     r8, aSqlNtdbmsMsqlT_5; "sql\\ntdbms\\msql\\typesystem\\es_util."...
0x100487020  mov     rdx, r13
0x100487023  mov     ecx, edi
0x100487025  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10048702b  mov     r13, rax
0x10048702e  mov     [rsp+0B8h+var_48], rax
0x100487033  mov     byte ptr [rsp+0B8h+var_98], 6
0x100487038  mov     r9d, 26Ch
0x10048703e  lea     r8, aSqlNtdbmsMsqlT_5; "sql\\ntdbms\\msql\\typesystem\\es_util."...
0x100487045  mov     rdx, [rsp+0B8h+var_60]
0x10048704a  mov     ecx, edi
0x10048704c  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100487052  mov     rdi, rax
0x100487055  mov     [rsp+0B8h+var_40], rax
0x10048705a  lea     r8d, [rsi-1]; int
0x10048705e  lea     rax, [rsp+0B8h+arg_0]
0x100487066  mov     [rsp+0B8h+var_70], rax; bool *
0x10048706b  lea     rax, [rsp+0B8h+var_68+4]
0x100487070  mov     [rsp+0B8h+var_78], rax; int *
0x100487075  mov     [rsp+0B8h+var_80], rdi; char *
0x10048707a  lea     rax, [rsp+0B8h+arg_20]
0x100487082  mov     [rsp+0B8h+var_88], rax; bool *
0x100487087  lea     rax, [rsp+0B8h+var_68]
0x10048708c  mov     [rsp+0B8h+var_90], rax; int *
0x100487091  mov     [rsp+0B8h+var_98], r13; char *
0x100487096  mov     r9d, esi; int
0x100487099  mov     rdx, r14; char *
0x10048709c  mov     rcx, r15; this
0x10048709f  call    ?GetMbcsRange@CTypeInfo@@QEBAXPEADHH0PEAHPEA_N012@Z; CTypeInfo::GetMbcsRange(char *,int,int,char *,int *,bool *,char *,int *,bool *)
0x1004870a4  mov     rax, [rsp+0B8h+arg_38]
0x1004870ac  mov     [rax], ebp
0x1004870ae  cmp     [rsp+0B8h+arg_30], 0
0x1004870b6  jz      short loc_1004870D8
0x1004870b8  movzx   ebp, byte ptr [rsp+0B8h+arg_20]
0x1004870c0  test    ebp, ebp
0x1004870c2  jz      short loc_1004870F8
0x1004870c4  mov     esi, dword ptr [rsp+0B8h+var_68]
0x1004870c8  mov     r8d, esi; Size
0x1004870cb  mov     rdx, r13; Src
0x1004870ce  mov     rcx, r14; void *
0x1004870d1  call    memmove
0x1004870d6  jmp     short loc_1004870FF
0x1004870d8  movzx   ebp, [rsp+0B8h+arg_0]
0x1004870e0  test    ebp, ebp
0x1004870e2  jz      short loc_1004870F8
0x1004870e4  mov     esi, dword ptr [rsp+0B8h+var_68+4]
0x1004870e8  mov     r8d, esi; Size
0x1004870eb  mov     rdx, rdi; Src
0x1004870ee  mov     rcx, r14; void *
0x1004870f1  call    memmove
0x1004870f6  jmp     short loc_1004870FF
0x1004870f8  mov     esi, dword ptr [rsp+0B8h+arg_8]
0x1004870ff  mov     rcx, rdi
0x100487102  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100487108  nop
0x100487109  mov     rcx, r13
0x10048710c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100487112  movzx   eax, byte ptr [r15]
0x100487116  mov     rcx, [rsp+0B8h+arg_28]
0x10048711e  mov     [rcx+2], bx
0x100487122  mov     byte ptr [rcx], 3
0x100487125  mov     [rcx+1], al
0x100487128  mov     [rcx+8], rbx
0x10048712c  mov     [rcx+10h], rbx
0x100487130  mov     [rcx+18h], ebx
0x100487133  test    ebp, ebp
0x100487135  jz      short loc_100487144
0x100487137  mov     [rcx+8], r14
0x10048713b  mov     eax, esi
0x10048713d  mov     [rcx+10h], rax
0x100487141  mov     byte ptr [rcx], 0
0x100487144  mov     rcx, r12
0x100487147  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10048714d  mov     eax, ebp
0x10048714f  mov     rbx, [rsp+0B8h+arg_18]
0x100487157  add     rsp, 80h
0x10048715e  pop     r15
0x100487160  pop     r14
0x100487162  pop     r13
0x100487164  pop     r12
0x100487166  pop     rdi
0x100487167  pop     rsi
0x100487168  pop     rbp
0x100487169  retn
```
