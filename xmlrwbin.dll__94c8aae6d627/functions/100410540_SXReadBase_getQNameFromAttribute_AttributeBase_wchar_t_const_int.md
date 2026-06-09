# SXReadBase::getQNameFromAttribute(AttributeBase *,wchar_t const * *,int *)

- ea: `0x100410540`
- end: `0x1004107fe`
- name: `?getQNameFromAttribute@SXReadBase@@QEAAXPEAVAttributeBase@@PEAPEB_WPEAH@Z`
- size: `702`
- prototype: `void __fastcall(SXReadBase *__hidden this, struct AttributeBase *, const wchar_t **, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x100411ba0`

## callees

- `0x100401350`
- `0x100410540`
- `0x100415d60`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004105f4`
- `KERNEL32!HeapAlloc` at `0x100410714`
- `KERNEL32!HeapAlloc` at `0x1004105f4`
- `KERNEL32!HeapAlloc` at `0x100410714`

## pseudocode

```c
void __fastcall SXReadBase::getQNameFromAttribute(
        SXReadBase *this,
        struct AttributeBase *a2,
        const wchar_t **a3,
        int *a4)
{
  int v4; // ebx
  int v9; // ecx
  struct IMalloc *v10; // rcx
  unsigned int v11; // ebx
  SIZE_T v12; // r8
  char *v13; // rax
  char *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rbp
  wchar_t *v19; // rdx
  size_t v20; // r8
  int v21; // ebx
  struct IMalloc *v22; // rcx
  SIZE_T v23; // r8
  char *v24; // rax
  unsigned __int64 v25; // r9

  v4 = 0;
  if ( !*((_QWORD *)a2 + 10) )
  {
    if ( (*(unsigned __int8 (__fastcall **)(struct AttributeBase *))(*(_QWORD *)a2 + 8LL))(a2) )
    {
      v21 = *((_DWORD *)a2 + 34);
      if ( v21 )
        v11 = v21 + 6;
      else
        v11 = 5;
      v22 = (struct IMalloc *)*((_QWORD *)this + 1);
      v23 = 2LL * v11;
      if ( !is_mul_ok(v11, 2u) )
        v23 = -1;
      if ( v22 || (v22 = g_pMalloc) != 0 )
        v24 = (char *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v22->lpVtbl->Alloc)(v22, v23);
      else
        v24 = (char *)HeapAlloc(g_hHeap, 0, v23);
      v14 = v24;
      if ( v24 )
      {
        if ( *((_DWORD *)a2 + 34) )
        {
          if ( v11 >= 6 )
          {
            memmove(v24, CodeStringPtr::xmlnscolon, 0xCu);
            v25 = *((unsigned int *)a2 + 34);
            if ( v11 - 6 >= (unsigned int)v25 && 2 * v25 >= v25 )
            {
              memmove(v14 + 12, *((const void **)a2 + 16), 2 * v25);
              *((_DWORD *)a2 + 22) = v11;
              *((_QWORD *)a2 + 10) = v14;
              goto LABEL_42;
            }
          }
          goto LABEL_43;
        }
        if ( v11 < 5 )
          goto LABEL_43;
        v20 = 10;
        v19 = CodeStringPtr::xmlns;
        goto LABEL_40;
      }
    }
    else
    {
      v9 = *(_DWORD *)(*((_QWORD *)a2 + 14) + 16LL);
      if ( v9 )
      {
        v4 = *(_DWORD *)(*((_QWORD *)a2 + 14) + 16LL);
        if ( *(_DWORD *)(*((_QWORD *)a2 + 13) + 16LL) )
          v4 = v9 + 1;
      }
      v10 = (struct IMalloc *)*((_QWORD *)this + 1);
      v11 = *(_DWORD *)(*((_QWORD *)a2 + 13) + 16LL) + v4;
      v12 = 2LL * v11;
      if ( !is_mul_ok(v11, 2u) )
        v12 = -1;
      if ( v10 || (v10 = g_pMalloc) != 0 )
        v13 = (char *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v10->lpVtbl->Alloc)(v10, v12);
      else
        v13 = (char *)HeapAlloc(g_hHeap, 0, v12);
      v14 = v13;
      if ( v13 )
      {
        v15 = *((_QWORD *)a2 + 14);
        v16 = *((_QWORD *)a2 + 13);
        v17 = *(unsigned int *)(v15 + 16);
        v18 = *(unsigned int *)(v16 + 16);
        if ( (_DWORD)v17 )
        {
          if ( v11 < (unsigned int)v17 || 2 * v17 < v17 )
            goto LABEL_43;
          memmove(v14, (const void *)(v15 + 24), 2 * v17);
          if ( (_DWORD)v18 )
          {
            *(_WORD *)&v14[2 * v17] = 58;
            if ( v11 - (unsigned int)v17 - 1 >= (unsigned int)v18 && 2 * v18 >= v18 )
            {
              memmove(&v14[2 * (unsigned int)(v17 + 1)], (const void *)(*((_QWORD *)a2 + 13) + 24LL), 2 * v18);
              *((_DWORD *)a2 + 22) = v11;
              *((_QWORD *)a2 + 10) = v14;
              goto LABEL_42;
            }
LABEL_43:
            MXRRaiseException(-2147467259);
            __debugbreak();
          }
LABEL_41:
          *((_DWORD *)a2 + 22) = v11;
          *((_QWORD *)a2 + 10) = v14;
          goto LABEL_42;
        }
        v19 = (wchar_t *)(v16 + 24);
        if ( v11 < (unsigned int)v18 )
          goto LABEL_43;
        v20 = 2 * v18;
        if ( 2 * v18 < v18 )
          goto LABEL_43;
LABEL_40:
        memmove(v14, v19, v20);
        goto LABEL_41;
      }
    }
    MXRRaiseException(-2147024882);
    JUMPOUT(0x1004107FDLL);
  }
LABEL_42:
  *a4 = *((_DWORD *)a2 + 22);
  *a3 = (const wchar_t *)*((_QWORD *)a2 + 10);
}

```

## disassembly

```asm
0x100410540  mov     [rsp+arg_0], rbx
0x100410545  mov     [rsp+arg_8], rbp
0x10041054a  mov     [rsp+arg_10], rsi
0x10041054f  push    rdi
0x100410550  push    r12
0x100410552  push    r13
0x100410554  push    r14
0x100410556  push    r15
0x100410558  sub     rsp, 20h
0x10041055c  xor     ebx, ebx
0x10041055e  mov     r12, r9
0x100410561  mov     r13, r8
0x100410564  mov     rdi, rdx
0x100410567  mov     rsi, rcx
0x10041056a  cmp     [rdx+50h], rbx
0x10041056e  jnz     loc_1004107BC
0x100410574  mov     rax, [rdx]
0x100410577  mov     rcx, rdx
0x10041057a  mov     rax, [rax+8]
0x10041057e  call    cs:__guard_dispatch_icall_fptr
0x100410584  test    al, al
0x100410586  jnz     loc_1004106B4
0x10041058c  mov     rax, [rdi+70h]
0x100410590  mov     ecx, [rax+10h]
0x100410593  test    ecx, ecx
0x100410595  jz      short loc_1004105A5
0x100410597  mov     rax, [rdi+68h]
0x10041059b  mov     ebx, ecx
0x10041059d  cmp     dword ptr [rax+10h], 0
0x1004105a1  jz      short loc_1004105A5
0x1004105a3  inc     ebx
0x1004105a5  mov     rax, [rdi+68h]
0x1004105a9  mov     rcx, [rsi+8]
0x1004105ad  add     ebx, [rax+10h]
0x1004105b0  mov     eax, 2
0x1004105b5  mov     edx, ebx
0x1004105b7  mul     rdx
0x1004105ba  mov     r8, rax
0x1004105bd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004105c4  cmovo   r8, rax; dwBytes
0x1004105c8  test    rcx, rcx
0x1004105cb  jz      short loc_1004105DF
0x1004105cd  mov     rax, [rcx]
0x1004105d0  mov     rdx, r8
0x1004105d3  mov     rax, [rax+18h]
0x1004105d7  call    cs:__guard_dispatch_icall_fptr
0x1004105dd  jmp     short loc_1004105FA
0x1004105df  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004105e6  test    rcx, rcx
0x1004105e9  jnz     short loc_1004105CD
0x1004105eb  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004105f2  xor     edx, edx; dwFlags
0x1004105f4  call    cs:__imp_HeapAlloc
0x1004105fa  mov     rsi, rax
0x1004105fd  test    rax, rax
0x100410600  jz      loc_1004107F3
0x100410606  mov     rcx, [rdi+70h]
0x10041060a  mov     rax, [rdi+68h]
0x10041060e  mov     r14d, [rcx+10h]
0x100410612  mov     ebp, [rax+10h]
0x100410615  test    r14d, r14d
0x100410618  jz      short loc_100410692
0x10041061a  lea     rdx, [rcx+18h]; Src
0x10041061e  cmp     ebx, r14d
0x100410621  jb      loc_1004107E8
0x100410627  lea     r15, [r14+r14]
0x10041062b  cmp     r15, r14
0x10041062e  jb      loc_1004107E8
0x100410634  mov     r8, r15; Size
0x100410637  mov     rcx, rsi; void *
0x10041063a  call    memmove
0x10041063f  test    ebp, ebp
0x100410641  jz      loc_1004107B5
0x100410647  mov     eax, 3Ah ; ':'
0x10041064c  mov     [r15+rsi], ax
0x100410651  mov     eax, ebx
0x100410653  mov     rdx, [rdi+68h]
0x100410657  sub     eax, r14d
0x10041065a  dec     eax
0x10041065c  add     rdx, 18h; Src
0x100410660  cmp     eax, ebp
0x100410662  jb      loc_1004107E8
0x100410668  lea     r8, ds:0[rbp*2]; Size
0x100410670  cmp     r8, rbp
0x100410673  jb      loc_1004107E8
0x100410679  lea     eax, [r14+1]
0x10041067d  lea     rcx, [rsi+rax*2]; void *
0x100410681  call    memmove
0x100410686  mov     [rdi+58h], ebx
0x100410689  mov     [rdi+50h], rsi
0x10041068d  jmp     loc_1004107BC
0x100410692  lea     rdx, [rax+18h]
0x100410696  cmp     ebx, ebp
0x100410698  jb      loc_1004107E8
0x10041069e  lea     r8, ds:0[rbp*2]
0x1004106a6  cmp     r8, rbp
0x1004106a9  jb      loc_1004107E8
0x1004106af  jmp     loc_1004107AD
0x1004106b4  mov     ebx, [rdi+88h]
0x1004106ba  test    ebx, ebx
0x1004106bc  jz      short loc_1004106C6
0x1004106be  add     ebx, cs:dword_10042F8A0
0x1004106c4  jmp     short loc_1004106CC
0x1004106c6  mov     ebx, cs:MaxCount
0x1004106cc  mov     rcx, [rsi+8]
0x1004106d0  mov     eax, 2
0x1004106d5  mov     edx, ebx
0x1004106d7  mul     rdx
0x1004106da  mov     r8, rax
0x1004106dd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004106e4  cmovo   r8, rax; dwBytes
0x1004106e8  test    rcx, rcx
0x1004106eb  jz      short loc_1004106FF
0x1004106ed  mov     rax, [rcx]
0x1004106f0  mov     rdx, r8
0x1004106f3  mov     rax, [rax+18h]
0x1004106f7  call    cs:__guard_dispatch_icall_fptr
0x1004106fd  jmp     short loc_10041071A
0x1004106ff  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410706  test    rcx, rcx
0x100410709  jnz     short loc_1004106ED
0x10041070b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410712  xor     edx, edx; dwFlags
0x100410714  call    cs:__imp_HeapAlloc
0x10041071a  mov     rsi, rax
0x10041071d  test    rax, rax
0x100410720  jz      loc_1004107F3
0x100410726  cmp     dword ptr [rdi+88h], 0
0x10041072d  jz      short loc_100410793
0x10041072f  mov     eax, cs:dword_10042F8A0
0x100410735  cmp     ebx, eax
0x100410737  jb      loc_1004107E8
0x10041073d  lea     r8, [rax+rax]; Size
0x100410741  cmp     r8, rax
0x100410744  jb      loc_1004107E8
0x10041074a  mov     rdx, cs:?xmlnscolon@CodeStringPtr@@2UStringPtr@@A; Src
0x100410751  mov     rcx, rsi; void *
0x100410754  call    memmove
0x100410759  mov     r8d, cs:dword_10042F8A0
0x100410760  mov     eax, ebx
0x100410762  mov     r9d, [rdi+88h]
0x100410769  sub     eax, r8d
0x10041076c  lea     rcx, [rsi+r8*2]; void *
0x100410770  cmp     eax, r9d
0x100410773  jb      short loc_1004107E8
0x100410775  lea     r8, [r9+r9]; Size
0x100410779  cmp     r8, r9
0x10041077c  jb      short loc_1004107E8
0x10041077e  mov     rdx, [rdi+80h]; Src
0x100410785  call    memmove
0x10041078a  mov     [rdi+58h], ebx
0x10041078d  mov     [rdi+50h], rsi
0x100410791  jmp     short loc_1004107BC
0x100410793  mov     eax, cs:MaxCount
0x100410799  cmp     ebx, eax
0x10041079b  jb      short loc_1004107E8
0x10041079d  lea     r8, [rax+rax]; Size
0x1004107a1  cmp     r8, rax
0x1004107a4  jb      short loc_1004107E8
0x1004107a6  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Src
0x1004107ad  mov     rcx, rsi; void *
0x1004107b0  call    memmove
0x1004107b5  mov     [rdi+58h], ebx
0x1004107b8  mov     [rdi+50h], rsi
0x1004107bc  mov     eax, [rdi+58h]
0x1004107bf  mov     rbx, [rsp+48h+arg_0]
0x1004107c4  mov     rbp, [rsp+48h+arg_8]
0x1004107c9  mov     rsi, [rsp+48h+arg_10]
0x1004107ce  mov     [r12], eax
0x1004107d2  mov     rax, [rdi+50h]
0x1004107d6  mov     [r13+0], rax
0x1004107da  add     rsp, 20h
0x1004107de  pop     r15
0x1004107e0  pop     r14
0x1004107e2  pop     r13
0x1004107e4  pop     r12
0x1004107e6  pop     rdi
0x1004107e7  retn
0x1004107e8  mov     ecx, 80004005h; int
0x1004107ed  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004107f2  int     3; Trap to Debugger
0x1004107f3  mov     ecx, 8007000Eh; int
0x1004107f8  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
