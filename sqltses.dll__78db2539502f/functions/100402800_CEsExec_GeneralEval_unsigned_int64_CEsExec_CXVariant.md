# CEsExec::GeneralEval(unsigned __int64 *,CEsExec *,CXVariant *)

- ea: `0x100402800`
- end: `0x100402980`
- name: `?GeneralEval@CEsExec@@CAXPEA_KPEAV1@PEAVCXVariant@@@Z`
- size: `384`
- prototype: `void __fastcall(unsigned __int64 *, struct CEsExec *, struct CXVariant *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x100401170`
- `0x1004024b0`
- `0x100402800`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100402954`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c96c5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100402954`
- `sqldk!??_V@YAXPEAX@Z` at `0x1004c96c5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c96b2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004c96b2`
- `sqldk!SystemThread_TlsIndex` at `0x1004c9665`
- `sqldk!SystemThread_TlsOffset` at `0x1004c966e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004c9689`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004c9689`
- `api-ms-win-crt-runtime-l1-1-0!_statusfp` at `0x1004187bc`
- `api-ms-win-crt-runtime-l1-1-0!_statusfp` at `0x1004187bc`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x1004c96e5`
- `api-ms-win-crt-runtime-l1-1-0!_clearfp` at `0x1004c96e5`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x1004187d7`
- `api-ms-win-crt-runtime-l1-1-0!_controlfp` at `0x1004187d7`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x1004c96f5`
- `api-ms-win-crt-runtime-l1-1-0!_fpreset` at `0x1004c96f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CEsExec::GeneralEval(unsigned __int64 *a1, struct CEsExec *a2, struct CXVariant *a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r15
  _WORD *v9; // rbx
  __int64 v10; // rax
  void *v11; // rsp
  _WORD *v12; // rsi
  _WORD *v13; // rdx
  _WORD *v14; // rax
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rdi
  _OWORD *v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rdi
  void (__fastcall *i)(struct CEsExec *, _OWORD *); // r8
  char v23; // r15
  __int64 v24; // rbx
  __int64 v25; // rdx
  _QWORD v26[2]; // [rsp+30h] [rbp+0h] BYREF

  v26[1] = -2;
  v6 = *((_QWORD *)a2 + 2);
  if ( (*(_BYTE *)(v6 + 8) & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 10) + 104LL))(*((_QWORD *)a2 + 10));
    v6 = *((_QWORD *)a2 + 2);
  }
  v7 = *(unsigned __int16 *)(v6 + 16);
  v8 = 32 * v7;
  v9 = 0;
  v26[0] = 0;
  if ( 32 * v7 > 0x2000 )
  {
    _mm_lfence();
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
    }
    v9 = operator new[](v8, *(struct IMemObj **)(v25 + 1000), "sql\\ntdbms\\msql\\expr\\runtime\\es.cpp", 244, 3u);
    v12 = v9;
    if ( v9 )
      operator delete[](0);
    v26[0] = v9;
  }
  else
  {
    v10 = v8 + 15;
    if ( v8 + 15 < v8 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    v12 = v26;
  }
  v13 = v12;
  if ( v7 <= 5 )
  {
    v15 = v7 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 != 1 )
              goto LABEL_21;
            v12[65] = 16;
          }
          v12[49] = 16;
        }
        v12[33] = 16;
      }
      v12[17] = 16;
    }
    v12[1] = 16;
  }
  else
  {
    v14 = &v12[v8 / 2 + 1];
    do
    {
      v14 -= 16;
      *v14 = 16;
      --v7;
    }
    while ( v7 );
  }
LABEL_21:
  v19 = v12 - 16;
  *((_QWORD *)a2 + 13) = a1;
  *((_QWORD *)a2 + 3) = v13;
  v20 = *((_QWORD *)a2 + 2);
  v21 = *(_QWORD *)(v20 + 24);
  *((_QWORD *)a2 + 4) = v21;
  if ( (*(_BYTE *)(v20 + 8) & 0x10) != 0 )
  {
    v23 = _statusfp();
    if ( (v23 & 0x1C) != 0 )
    {
      _clearfp();
      if ( (v23 & 0x10) != 0 )
        _fpreset();
    }
    _controlfp(0x9001Fu, 0x8031Fu);
  }
  for ( i = *(void (__fastcall **)(struct CEsExec *, _OWORD *))v21;
        *(_QWORD *)v21;
        i = *(void (__fastcall **)(struct CEsExec *, _OWORD *))v21 )
  {
    v19 -= 2 * *(int *)(v21 + 8);
    i(a2, v19);
    *((_QWORD *)a2 + 4) += 32LL;
    v21 = *((_QWORD *)a2 + 4);
  }
  if ( a3 )
  {
    *(_OWORD *)a3 = *v19;
    *((_OWORD *)a3 + 1) = v19[1];
    *((_WORD *)a3 + 1) &= ~1u;
    *((_BYTE *)a3 + 1) = *(_BYTE *)(*((_QWORD *)a2 + 2) + 80LL);
  }
  operator delete[](v9);
}

```

## disassembly

```asm
0x100402800  push    rbp
0x100402802  push    r12
0x100402804  push    r13
0x100402806  push    r14
0x100402808  push    r15
0x10040280a  sub     rsp, 50h
0x10040280e  lea     rbp, [rsp+30h]
0x100402813  mov     [rbp+40h+var_38], 0FFFFFFFFFFFFFFFEh
0x10040281b  mov     [rbp+40h+arg_0], rbx
0x10040281f  mov     [rbp+40h+arg_8], rsi
0x100402823  mov     [rbp+40h+arg_10], rdi
0x100402827  mov     rax, cs:__security_cookie
0x10040282e  xor     rax, rbp
0x100402831  mov     [rbp+40h+var_30], rax
0x100402835  mov     r13, r8
0x100402838  mov     r14, rdx
0x10040283b  mov     r12, rcx
0x10040283e  mov     rax, [rdx+10h]
0x100402842  test    byte ptr [rax+8], 1
0x100402846  jnz     loc_1004C9645
0x10040284c  movzx   edi, word ptr [rax+10h]
0x100402850  mov     r15d, edi
0x100402853  shl     r15, 5
0x100402857  xor     ebx, ebx
0x100402859  mov     [rbp+40h+var_40], rbx
0x10040285d  cmp     r15, 2000h
0x100402864  ja      loc_1004C9659
0x10040286a  lea     rax, [r15+0Fh]
0x10040286e  cmp     rax, r15
0x100402871  jbe     loc_1004C96D5
0x100402877  and     rax, 0FFFFFFFFFFFFFFF0h
0x10040287b  call    _alloca_probe
0x100402880  sub     rsp, rax
0x100402883  lea     rsi, [rsp+70h+var_40]
0x100402888  mov     rdx, rsi
0x10040288b  mov     ecx, 10h
0x100402890  cmp     rdi, 5
0x100402894  jbe     short loc_1004028B0
0x100402896  lea     rax, [rsi+2]
0x10040289a  add     rax, r15
0x10040289d  nop     dword ptr [rax]
0x1004028a0  lea     rax, [rax-20h]
0x1004028a4  mov     [rax], cx
0x1004028a7  sub     rdi, 1
0x1004028ab  jnz     short loc_1004028A0
0x1004028ad  jmp     short loc_1004028E8
0x1004028b0  sub     rdi, 1
0x1004028b4  jz      short loc_1004028E1
0x1004028b6  sub     rdi, 1
0x1004028ba  jz      short loc_1004028DD
0x1004028bc  sub     rdi, 1
0x1004028c0  jz      short loc_1004028D9
0x1004028c2  sub     rdi, 1
0x1004028c6  jz      short loc_1004028D5
0x1004028c8  cmp     rdi, 1
0x1004028cc  jnz     short loc_1004028E8
0x1004028ce  mov     [rsi+82h], cx
0x1004028d5  mov     [rsi+62h], cx
0x1004028d9  mov     [rsi+42h], cx
0x1004028dd  mov     [rsi+22h], cx
0x1004028e1  mov     [rsi+2], cx
0x1004028e5  jmp     short loc_1004028E8
0x1004028e8  sub     rsi, 20h ; ' '
0x1004028ec  mov     [r14+68h], r12
0x1004028f0  mov     [r14+18h], rdx
0x1004028f4  mov     rax, [r14+10h]
0x1004028f8  mov     rdi, [rax+18h]
0x1004028fc  mov     [r14+20h], rdi
0x100402900  test    byte ptr [rax+8], 10h
0x100402904  jnz     loc_1004187BC
0x10040290a  mov     r8, [rdi]
0x10040290d  test    r8, r8
0x100402910  jz      short loc_100402948
0x100402912  nop
0x100402913  nop
0x100402914  nop
0x100402915  nop
0x100402916  nop
0x100402917  nop
0x100402918  nop
0x100402919  nop
0x10040291a  nop
0x10040291b  nop
0x10040291c  nop
0x10040291d  nop
0x10040291e  nop
0x10040291f  nop
0x100402920  movsxd  rax, dword ptr [rdi+8]
0x100402924  neg     rax
0x100402927  shl     rax, 5
0x10040292b  add     rsi, rax
0x10040292e  mov     rdx, rsi
0x100402931  mov     rcx, r14
0x100402934  call    r8
0x100402937  add     qword ptr [r14+20h], 20h ; ' '
0x10040293c  mov     rdi, [r14+20h]
0x100402940  mov     r8, [rdi]
0x100402943  test    r8, r8
0x100402946  jnz     short loc_100402920
0x100402948  test    r13, r13
0x10040294b  jnz     loc_100421A25
0x100402951  mov     rcx, rbx
0x100402954  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10040295a  mov     rcx, [rbp+40h+var_30]
0x10040295e  xor     rcx, rbp; StackCookie
0x100402961  call    __security_check_cookie
0x100402966  mov     rbx, [rbp+40h+arg_0]
0x10040296a  mov     rsi, [rbp+40h+arg_8]
0x10040296e  mov     rdi, [rbp+40h+arg_10]
0x100402972  lea     rsp, [rbp+20h]
0x100402976  pop     r15
0x100402978  pop     r14
0x10040297a  pop     r13
0x10040297c  pop     r12
0x10040297e  pop     rbp
0x10040297f  retn
0x1004187bc  call    cs:__imp__statusfp
0x1004187c2  mov     r15d, eax
0x1004187c5  test    al, 1Ch
0x1004187c7  jnz     loc_1004C96E5
0x1004187cd  mov     edx, 8031Fh; Mask
0x1004187d2  mov     ecx, 9001Fh; NewValue
0x1004187d7  call    cs:__imp__controlfp
0x1004187dd  nop
0x1004187de  jmp     loc_10040290A
0x100421a25  movups  xmm0, xmmword ptr [rsi]
0x100421a28  movups  xmmword ptr [r13+0], xmm0
0x100421a2d  movups  xmm1, xmmword ptr [rsi+10h]
0x100421a31  movups  xmmword ptr [r13+10h], xmm1
0x100421a36  mov     eax, 0FFFEh
0x100421a3b  and     [r13+2], ax
0x100421a40  mov     rax, [r14+10h]
0x100421a44  movzx   ecx, byte ptr [rax+50h]
0x100421a48  mov     [r13+1], cl
0x100421a4c  jmp     loc_100402951
0x1004c9645  mov     rcx, [rdx+50h]
0x1004c9649  mov     rax, [rcx]
0x1004c964c  call    qword ptr [rax+68h]
0x1004c964f  mov     rax, [r14+10h]
0x1004c9653  jmp     loc_10040284C
0x1004c9659  lfence
0x1004c965c  mov     rdx, gs:58h
0x1004c9665  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004c966c  mov     ecx, [rax]
0x1004c966e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004c9675  mov     ebx, [rax]
0x1004c9677  add     rbx, [rdx+rcx*8]
0x1004c967b  mov     rdx, [rbx+100h]
0x1004c9682  test    rdx, rdx
0x1004c9685  jnz     short loc_1004C9696
0x1004c9687  xor     ecx, ecx
0x1004c9689  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004c968f  mov     rdx, [rbx+100h]
0x1004c9696  mov     [rsp+70h+var_50], 3
0x1004c969b  mov     r9d, 0F4h
0x1004c96a1  lea     r8, aSqlNtdbmsMsqlE_10; "sql\\ntdbms\\msql\\expr\\runtime\\es.cp"...
0x1004c96a8  mov     rdx, [rdx+3E8h]
0x1004c96af  mov     rcx, r15
0x1004c96b2  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004c96b8  mov     rbx, rax
0x1004c96bb  mov     rsi, rax
0x1004c96be  test    rax, rax
0x1004c96c1  jz      short loc_1004C96CB
0x1004c96c3  xor     ecx, ecx
0x1004c96c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004c96cb  mov     [rbp+40h+var_40], rbx
0x1004c96cf  jmp     loc_100402888
0x1004c96d5  mov     rax, 0FFFFFFFFFFFFFF0h
0x1004c96df  jmp     loc_100402877
0x1004c96e5  call    cs:__imp__clearfp
0x1004c96eb  test    r15b, 10h
0x1004c96ef  jz      loc_1004187CD
0x1004c96f5  call    cs:__imp__fpreset
0x1004c96fb  nop
0x1004c96fc  jmp     loc_1004187CD
```
