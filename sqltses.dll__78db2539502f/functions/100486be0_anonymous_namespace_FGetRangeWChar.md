# _anonymous_namespace_::FGetRangeWChar

- ea: `0x100486be0`
- end: `0x100486de8`
- name: `_anonymous_namespace_::FGetRangeWChar`
- size: `520`
- prototype: `__int64 __usercall@<rax>(CTypeInfo *this@<rcx>, void *, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100486df0`
- `0x100488290`

## callees

- `0x100401cc0`
- `0x100475080`
- `0x100486be0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100486dba`
- `sqldk!??_V@YAXPEAX@Z` at `0x100486dc4`
- `sqldk!??_V@YAXPEAX@Z` at `0x100486dba`
- `sqldk!??_V@YAXPEAX@Z` at `0x100486dc4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486cb5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486ce7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486cb5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100486ce7`
- `sqldk!SystemThread_TlsIndex` at `0x100486c50`
- `sqldk!SystemThread_TlsOffset` at `0x100486c59`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100486c74`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100486c74`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall anonymous_namespace_::FGetRangeWChar(
        CTypeInfo *this,
        int a2,
        wchar_t *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        _DWORD *a7,
        _DWORD *a8)
{
  unsigned int v11; // esi
  int v12; // ebx
  __int64 v14; // rbx
  __int64 v15; // rdi
  struct IMemObj *v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // rax
  wchar_t *v19; // rsi
  unsigned __int64 v20; // rax
  wchar_t *v21; // rbp
  BOOL v22; // edi
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  bool v25; // [rsp+60h] [rbp-58h] BYREF
  unsigned int Size; // [rsp+64h] [rbp-54h] BYREF
  unsigned int Size_4; // [rsp+68h] [rbp-50h] BYREF
  __int64 v28; // [rsp+70h] [rbp-48h]
  wchar_t *v29; // [rsp+78h] [rbp-40h]
  wchar_t *v30; // [rsp+80h] [rbp-38h]
  bool v31; // [rsp+D8h] [rbp+20h] BYREF

  v28 = -2;
  v11 = a6 >> 1;
  if ( a6 >> 1 < a4 )
  {
    _mm_lfence();
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v15 = *(_QWORD *)(v14 + 256);
    if ( !v15 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v15 = *(_QWORD *)(v14 + 256);
    }
    v16 = *(struct IMemObj **)(v15 + 1000);
    v17 = v11;
    v18 = 2LL * v11;
    if ( !is_mul_ok(v11, 2u) )
      v18 = -1;
    v19 = (wchar_t *)operator new[](v18, v16, "sql\\ntdbms\\msql\\typesystem\\es_util.cpp", 472, 6u);
    v29 = v19;
    v20 = 2 * v17;
    if ( !is_mul_ok(v17, 2u) )
      v20 = -1;
    v21 = (wchar_t *)operator new[](v20, v16, "sql\\ntdbms\\msql\\typesystem\\es_util.cpp", 473, 6u);
    v30 = v21;
    CTypeInfo::GetUnicodeRange(this, a3, a6, a6, v19, (int *)&Size, &v31, v21, (int *)&Size_4, &v25, 0);
    *a8 = 1;
    if ( a2 )
    {
      v22 = v31;
      if ( v31 )
      {
        v23 = Size;
        memmove(a5, v19, Size);
        *a7 = v23;
      }
    }
    else
    {
      v22 = v25;
      if ( v25 )
      {
        v24 = Size_4;
        memmove(a5, v21, Size_4);
        *a7 = v24;
      }
    }
    operator delete[](v21);
    operator delete[](v19);
    return v22;
  }
  else
  {
    v12 = 2 * a4;
    memmove(a5, a3, 2 * a4);
    *a7 = v12;
    return 1;
  }
}

```

## disassembly

```asm
0x100486be0  mov     rax, rsp
0x100486be3  push    rsi
0x100486be4  push    rdi
0x100486be5  push    r12
0x100486be7  push    r13
0x100486be9  push    r14
0x100486beb  sub     rsp, 90h
0x100486bf2  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100486bfa  mov     [rax+8], rbx
0x100486bfe  mov     [rax+10h], rbp
0x100486c02  mov     r14, r8
0x100486c05  mov     r12d, edx
0x100486c08  mov     r13, rcx
0x100486c0b  mov     esi, [rsp+0B8h+arg_28]
0x100486c12  shr     esi, 1
0x100486c14  cmp     esi, r9d
0x100486c17  jb      short loc_100486C44
0x100486c19  lea     ebx, [r9+r9]
0x100486c1d  mov     r8d, ebx; Size
0x100486c20  mov     rdx, r14; Src
0x100486c23  mov     rcx, [rsp+0B8h+arg_20]; void *
0x100486c2b  call    memmove
0x100486c30  mov     rcx, [rsp+0B8h+arg_30]
0x100486c38  mov     [rcx], ebx
0x100486c3a  mov     eax, 1
0x100486c3f  jmp     loc_100486DCC
0x100486c44  lfence
0x100486c47  mov     rdx, gs:58h
0x100486c50  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100486c57  mov     ecx, [rax]
0x100486c59  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100486c60  mov     ebx, [rax]
0x100486c62  add     rbx, [rdx+rcx*8]
0x100486c66  mov     rdi, [rbx+100h]
0x100486c6d  test    rdi, rdi
0x100486c70  jnz     short loc_100486C81
0x100486c72  xor     ecx, ecx
0x100486c74  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100486c7a  mov     rdi, [rbx+100h]
0x100486c81  mov     rdi, [rdi+3E8h]
0x100486c88  mov     ebx, esi
0x100486c8a  mov     eax, 2
0x100486c8f  mul     rbx
0x100486c92  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x100486c99  cmovo   rax, rbp
0x100486c9d  mov     byte ptr [rsp+0B8h+var_98], 6
0x100486ca2  mov     r9d, 1D8h
0x100486ca8  lea     r8, aSqlNtdbmsMsqlT_5; "sql\\ntdbms\\msql\\typesystem\\es_util."...
0x100486caf  mov     rdx, rdi
0x100486cb2  mov     rcx, rax
0x100486cb5  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100486cbb  mov     rsi, rax
0x100486cbe  mov     [rsp+0B8h+var_40], rax
0x100486cc3  mov     eax, 2
0x100486cc8  mul     rbx
0x100486ccb  cmovo   rax, rbp
0x100486ccf  mov     byte ptr [rsp+0B8h+var_98], 6
0x100486cd4  mov     r9d, 1D9h
0x100486cda  lea     r8, aSqlNtdbmsMsqlT_5; "sql\\ntdbms\\msql\\typesystem\\es_util."...
0x100486ce1  mov     rdx, rdi
0x100486ce4  mov     rcx, rax
0x100486ce7  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x100486ced  mov     rbp, rax
0x100486cf0  mov     [rsp+0B8h+var_38], rax
0x100486cf8  mov     [rsp+0B8h+var_68], 0; unsigned int
0x100486d00  lea     rax, [rsp+0B8h+var_58]
0x100486d05  mov     [rsp+0B8h+var_70], rax; bool *
0x100486d0a  lea     rax, [rsp+0B8h+Size+4]
0x100486d0f  mov     [rsp+0B8h+var_78], rax; int *
0x100486d14  mov     [rsp+0B8h+var_80], rbp; wchar_t *
0x100486d19  lea     rax, [rsp+0B8h+arg_18]
0x100486d21  mov     [rsp+0B8h+var_88], rax; bool *
0x100486d26  lea     rax, [rsp+0B8h+Size]
0x100486d2b  mov     [rsp+0B8h+var_90], rax; int *
0x100486d30  mov     [rsp+0B8h+var_98], rsi; wchar_t *
0x100486d35  mov     r9d, [rsp+0B8h+arg_28]; int
0x100486d3d  mov     r8d, r9d; int
0x100486d40  mov     rdx, r14; Src
0x100486d43  mov     rcx, r13; this
0x100486d46  call    ?GetUnicodeRange@CTypeInfo@@QEBAXPEA_WHH0PEAHPEA_N012I@Z; CTypeInfo::GetUnicodeRange(wchar_t *,int,int,wchar_t *,int *,bool *,wchar_t *,int *,bool *,uint)
0x100486d4b  mov     rax, [rsp+0B8h+arg_38]
0x100486d53  mov     dword ptr [rax], 1
0x100486d59  test    r12d, r12d
0x100486d5c  jz      short loc_100486D8D
0x100486d5e  movzx   edi, [rsp+0B8h+arg_18]
0x100486d66  test    edi, edi
0x100486d68  jz      short loc_100486DB7
0x100486d6a  mov     ebx, dword ptr [rsp+0B8h+Size]
0x100486d6e  mov     r8d, ebx; Size
0x100486d71  mov     rdx, rsi; Src
0x100486d74  mov     rcx, [rsp+0B8h+arg_20]; void *
0x100486d7c  call    memmove
0x100486d81  mov     rax, [rsp+0B8h+arg_30]
0x100486d89  mov     [rax], ebx
0x100486d8b  jmp     short loc_100486DB7
0x100486d8d  movzx   edi, [rsp+0B8h+var_58]
0x100486d92  test    edi, edi
0x100486d94  jz      short loc_100486DB7
0x100486d96  mov     ebx, dword ptr [rsp+0B8h+Size+4]
0x100486d9a  mov     r8d, ebx; Size
0x100486d9d  mov     rdx, rbp; Src
0x100486da0  mov     rcx, [rsp+0B8h+arg_20]; void *
0x100486da8  call    memmove
0x100486dad  mov     rcx, [rsp+0B8h+arg_30]
0x100486db5  mov     [rcx], ebx
0x100486db7  mov     rcx, rbp
0x100486dba  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100486dc0  nop
0x100486dc1  mov     rcx, rsi
0x100486dc4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100486dca  mov     eax, edi
0x100486dcc  lea     r11, [rsp+0B8h+var_28]
0x100486dd4  mov     rbx, [r11+30h]
0x100486dd8  mov     rbp, [r11+38h]
0x100486ddc  mov     rsp, r11
0x100486ddf  pop     r14
0x100486de1  pop     r13
0x100486de3  pop     r12
0x100486de5  pop     rdi
0x100486de6  pop     rsi
0x100486de7  retn
```
