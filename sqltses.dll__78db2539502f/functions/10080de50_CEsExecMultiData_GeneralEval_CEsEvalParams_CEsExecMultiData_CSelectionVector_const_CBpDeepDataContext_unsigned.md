# CEsExecMultiData::GeneralEval(CEsEvalParams *,CEsExecMultiData *,CSelectionVector const &,CBpDeepDataContext *,unsigned __int64 *,bool *)

- ea: `0x10080de50`
- end: `0x10080e05d`
- name: `?GeneralEval@CEsExecMultiData@@CAXPEAVCEsEvalParams@@PEAV1@AEBVCSelectionVector@@PEAVCBpDeepDataContext@@PEA_KPEA_N@Z`
- size: `525`
- prototype: `void __fastcall(struct CEsEvalParams *, struct CEsExecMultiData *, const struct CSelectionVector *, struct CBpDeepDataContext *, void *, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x100401170`
- `0x100401cc0`
- `0x1004024b0`
- `0x10080de50`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10080df18`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080e031`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080df18`
- `sqldk!??_V@YAXPEAX@Z` at `0x10080e031`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080df05`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10080df05`
- `sqldk!SystemThread_TlsIndex` at `0x10080deb8`
- `sqldk!SystemThread_TlsOffset` at `0x10080dec1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080dedc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10080dedc`
- `api-ms-win-crt-runtime-l1-1-0!_statusfp` at `0x10080df7e`
- `api-ms-win-crt-runtime-l1-1-0!_statusfp` at `0x10080df7e`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x10080df8a`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x10080df8a`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x10080dfa6`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x10080dfa6`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x10080df96`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x10080df96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEsExecMultiData::GeneralEval(
        struct CEsEvalParams *a1,
        struct CEsExecMultiData *a2,
        const struct CSelectionVector *a3,
        struct CBpDeepDataContext *a4,
        _QWORD *a5,
        bool *a6)
{
  unsigned __int64 v10; // rdi
  _QWORD *v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rdx
  _QWORD *v14; // r13
  __int64 v15; // rax
  void *v16; // rsp
  __int64 v17; // rax
  __int64 v18; // rsi
  char v19; // di
  _QWORD *v20; // rdi
  void (__fastcall *i)(_QWORD *, _QWORD *); // r8
  __int64 v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // [rsp+30h] [rbp+0h] BYREF
  _QWORD v25[2]; // [rsp+38h] [rbp+8h] BYREF

  v25[1] = -2;
  v10 = 32LL * *(unsigned __int16 *)(*((_QWORD *)a2 + 2) + 16LL);
  v11 = 0;
  v24 = 0;
  if ( v10 <= 0x2000 )
  {
    v15 = v10 + 15;
    if ( v10 + 15 < v10 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
    v14 = &v24;
  }
  else
  {
    _mm_lfence();
    v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v13 = *(_QWORD *)(v12 + 256);
    if ( !v13 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v13 = *(_QWORD *)(v12 + 256);
    }
    v11 = operator new[](v10, *(struct IMemObj **)(v13 + 1000), "sql\\ntdbms\\msql\\expr\\runtime\\esmd.cpp", 280, 3u);
    v14 = v11;
    if ( v11 )
      operator delete[](0);
    v24 = v11;
  }
  *((_QWORD *)a2 + 15) = a1;
  *((_QWORD *)a2 + 16) = a4;
  *(_QWORD *)(*((_QWORD *)a2 + 18) + 8LL) = a3;
  **((_QWORD **)a2 + 17) = a5;
  v17 = *((_QWORD *)a2 + 2);
  v18 = *(_QWORD *)(v17 + 24);
  *((_QWORD *)a2 + 4) = v18;
  if ( (*(_BYTE *)(v17 + 8) & 0x10) != 0 )
  {
    v19 = _statusfp();
    if ( (v19 & 0x1C) != 0 )
    {
      _clearfp();
      if ( (v19 & 0x10) != 0 )
        _fpreset();
    }
    _controlfp(0x9001Fu, 0x8031Fu);
    v18 = *((_QWORD *)a2 + 4);
  }
  v25[0] = a2;
  v20 = v14 - 4;
  for ( i = *(void (__fastcall **)(_QWORD *, _QWORD *))v18;
        *(_QWORD *)v18;
        i = *(void (__fastcall **)(_QWORD *, _QWORD *))v18 )
  {
    v20 -= 4 * *(int *)(v18 + 8);
    i(v25, v20);
    v22 = *(_QWORD *)(v18 + 40);
    if ( v22 )
      v20[2] = v22;
    *((_QWORD *)a2 + 4) += 48LL;
    v18 = *((_QWORD *)a2 + 4);
  }
  if ( a5 )
  {
    v23 = (_QWORD *)*v20;
    if ( (_QWORD *)*v20 != a5 )
    {
      if ( (v20[1] & 1) != 0 )
        *a5 = *v23;
      else
        memmove(a5, v23, 8LL * *((unsigned int *)a2 + 28));
    }
    *a6 = v20[1] & 1;
  }
  operator delete[](v11);
}

```

## disassembly

```asm
0x10080de50  push    rbp
0x10080de52  push    r12
0x10080de54  push    r13
0x10080de56  push    r14
0x10080de58  push    r15
0x10080de5a  sub     rsp, 50h
0x10080de5e  lea     rbp, [rsp+30h]
0x10080de63  mov     [rbp+40h+var_30], 0FFFFFFFFFFFFFFFEh
0x10080de6b  mov     [rbp+40h+arg_0], rbx
0x10080de6f  mov     [rbp+40h+arg_8], rsi
0x10080de73  mov     [rbp+40h+arg_10], rdi
0x10080de77  mov     rax, cs:__security_cookie
0x10080de7e  xor     rax, rbp
0x10080de81  mov     [rbp+40h+var_28], rax
0x10080de85  mov     rsi, r9
0x10080de88  mov     r15, r8
0x10080de8b  mov     r14, rdx
0x10080de8e  mov     r12, rcx
0x10080de91  mov     rax, [rdx+10h]
0x10080de95  movzx   edi, word ptr [rax+10h]
0x10080de99  shl     rdi, 5
0x10080de9d  xor     ebx, ebx
0x10080de9f  mov     [rbp+40h+var_40], rbx
0x10080dea3  cmp     rdi, 2000h
0x10080deaa  jbe     short loc_10080DF24
0x10080deac  lfence
0x10080deaf  mov     rdx, gs:58h
0x10080deb8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10080debf  mov     ecx, [rax]
0x10080dec1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10080dec8  mov     ebx, [rax]
0x10080deca  add     rbx, [rdx+rcx*8]
0x10080dece  mov     rdx, [rbx+100h]
0x10080ded5  test    rdx, rdx
0x10080ded8  jnz     short loc_10080DEE9
0x10080deda  xor     ecx, ecx
0x10080dedc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10080dee2  mov     rdx, [rbx+100h]
0x10080dee9  mov     [rsp+70h+var_50], 3
0x10080deee  mov     r9d, 118h
0x10080def4  lea     r8, aSqlNtdbmsMsqlE_11; "sql\\ntdbms\\msql\\expr\\runtime\\esmd."...
0x10080defb  mov     rdx, [rdx+3E8h]
0x10080df02  mov     rcx, rdi
0x10080df05  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10080df0b  mov     rbx, rax
0x10080df0e  mov     r13, rax
0x10080df11  test    rax, rax
0x10080df14  jz      short loc_10080DF1E
0x10080df16  xor     ecx, ecx
0x10080df18  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10080df1e  mov     [rbp+40h+var_40], rbx
0x10080df22  jmp     short loc_10080DF48
0x10080df24  lea     rax, [rdi+0Fh]
0x10080df28  cmp     rax, rdi
0x10080df2b  ja      short loc_10080DF37
0x10080df2d  mov     rax, 0FFFFFFFFFFFFFF0h
0x10080df37  and     rax, 0FFFFFFFFFFFFFFF0h
0x10080df3b  call    _alloca_probe
0x10080df40  sub     rsp, rax
0x10080df43  lea     r13, [rsp+70h+var_40]
0x10080df48  mov     [r14+78h], r12
0x10080df4c  mov     [r14+80h], rsi
0x10080df53  mov     rax, [r14+90h]
0x10080df5a  mov     [rax+8], r15
0x10080df5e  mov     rax, [r14+88h]
0x10080df65  mov     r15, [rbp+40h+arg_20]
0x10080df69  mov     [rax], r15
0x10080df6c  mov     rax, [r14+10h]
0x10080df70  mov     rsi, [rax+18h]
0x10080df74  mov     [r14+20h], rsi
0x10080df78  test    byte ptr [rax+8], 10h
0x10080df7c  jz      short loc_10080DFB0
0x10080df7e  call    cs:__imp__statusfp
0x10080df84  mov     edi, eax
0x10080df86  test    al, 1Ch
0x10080df88  jz      short loc_10080DF9C
0x10080df8a  call    cs:__imp__clearfp
0x10080df90  test    dil, 10h
0x10080df94  jz      short loc_10080DF9C
0x10080df96  call    cs:__imp__fpreset
0x10080df9c  mov     edx, 8031Fh; Mask
0x10080dfa1  mov     ecx, 9001Fh; NewValue
0x10080dfa6  call    cs:__imp__controlfp
0x10080dfac  mov     rsi, [r14+20h]
0x10080dfb0  mov     [rbp+40h+var_38], r14
0x10080dfb4  lea     rdi, [r13-20h]
0x10080dfb8  mov     r8, [rsi]
0x10080dfbb  test    r8, r8
0x10080dfbe  jz      short loc_10080DFF6
0x10080dfc0  movsxd  rax, dword ptr [rsi+8]
0x10080dfc4  neg     rax
0x10080dfc7  shl     rax, 5
0x10080dfcb  add     rdi, rax
0x10080dfce  mov     rdx, rdi
0x10080dfd1  lea     rcx, [rbp+40h+var_38]
0x10080dfd5  call    r8
0x10080dfd8  mov     rax, [rsi+28h]
0x10080dfdc  test    rax, rax
0x10080dfdf  jz      short loc_10080DFE5
0x10080dfe1  mov     [rdi+10h], rax
0x10080dfe5  add     qword ptr [r14+20h], 30h ; '0'
0x10080dfea  mov     rsi, [r14+20h]
0x10080dfee  mov     r8, [rsi]
0x10080dff1  test    r8, r8
0x10080dff4  jnz     short loc_10080DFC0
0x10080dff6  test    r15, r15
0x10080dff9  jz      short loc_10080E02E
0x10080dffb  mov     rdx, [rdi]; Src
0x10080dffe  cmp     rdx, r15
0x10080e001  jz      short loc_10080E021
0x10080e003  test    byte ptr [rdi+8], 1
0x10080e007  jz      short loc_10080E011
0x10080e009  mov     rax, [rdx]
0x10080e00c  mov     [r15], rax
0x10080e00f  jmp     short loc_10080E021
0x10080e011  mov     r8d, [r14+70h]
0x10080e015  shl     r8, 3; Size
0x10080e019  mov     rcx, r15; void *
0x10080e01c  call    memmove
0x10080e021  movzx   ecx, byte ptr [rdi+8]
0x10080e025  and     cl, 1
0x10080e028  mov     rax, [rbp+40h+arg_28]
0x10080e02c  mov     [rax], cl
0x10080e02e  mov     rcx, rbx
0x10080e031  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10080e037  mov     rcx, [rbp+40h+var_28]
0x10080e03b  xor     rcx, rbp; StackCookie
0x10080e03e  call    __security_check_cookie
0x10080e043  mov     rbx, [rbp+40h+arg_0]
0x10080e047  mov     rsi, [rbp+40h+arg_8]
0x10080e04b  mov     rdi, [rbp+40h+arg_10]
0x10080e04f  lea     rsp, [rbp+20h]
0x10080e053  pop     r15
0x10080e055  pop     r14
0x10080e057  pop     r13
0x10080e059  pop     r12
0x10080e05b  pop     rbp
0x10080e05c  retn
```
