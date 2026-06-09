# CJob::GetRunTimes(_SYSTEMTIME * const,_SYSTEMTIME * const,ushort *,_SYSTEMTIME * *)

- ea: `0x180025390`
- end: `0x1800254f8`
- name: `?GetRunTimes@CJob@@UEAAJQEAU_SYSTEMTIME@@0PEAGPEAPEAU2@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CJob *this, struct _SYSTEMTIME *const, struct _SYSTEMTIME *const, unsigned __int16 *, struct _SYSTEMTIME **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006d00`
- `0x180025390`
- `0x180025500`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800254a5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800254a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002546a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002546a`

## pseudocode

```c
__int64 __fastcall CJob::GetRunTimes(
        CJob *this,
        struct _SYSTEMTIME *const a2,
        struct _SYSTEMTIME *const a3,
        unsigned __int16 *a4,
        struct _SYSTEMTIME **a5)
{
  unsigned __int16 v5; // r15
  unsigned int RunTimesP; // ebx
  unsigned __int16 v8; // si
  __int64 v9; // rcx
  struct _SYSTEMTIME *v10; // rax
  unsigned __int16 v11; // ax
  void ***v12; // rbx
  unsigned __int16 v13; // r8
  unsigned __int16 v14; // dx
  unsigned __int16 *v16; // [rsp+30h] [rbp-71h]
  void **v17; // [rsp+40h] [rbp-61h] BYREF
  void ***v18; // [rsp+48h] [rbp-59h]
  void ***v19; // [rsp+50h] [rbp-51h]
  __int64 v20; // [rsp+58h] [rbp-49h]
  __int64 v21; // [rsp+60h] [rbp-41h]
  __int64 v22; // [rsp+68h] [rbp-39h]
  __int128 v23; // [rsp+70h] [rbp-31h]
  int v24; // [rsp+80h] [rbp-21h]
  __int64 v25; // [rsp+88h] [rbp-19h]
  __int128 v26; // [rsp+90h] [rbp-11h]
  int v27; // [rsp+A0h] [rbp-1h]
  int v28; // [rsp+A4h] [rbp+3h]
  __int16 v29; // [rsp+A8h] [rbp+7h]
  __int64 v30; // [rsp+ACh] [rbp+Bh]
  int v31; // [rsp+B4h] [rbp+13h]

  v5 = *a4;
  v17 = &CRun::`vftable';
  v21 = 0x7FFFFFFFFFFFFFFFLL;
  v22 = 0x7FFFFFFFFFFFFFFFLL;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v20 = 0;
  v18 = &v17;
  v19 = &v17;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = -1;
  if ( (unsigned __int16)(v5 - 1) > 0x59Fu )
  {
    RunTimesP = -2147024809;
  }
  else
  {
    *a5 = 0;
    *a4 = 0;
    RunTimesP = CJob::GetRunTimesP(this, a2, a3, a4, v5, (struct CTimeRunList *)&v17, v16);
    if ( RunTimesP )
    {
      *a4 = 0;
    }
    else
    {
      v8 = *a4;
      v9 = *a4;
      *a4 = 0;
      v10 = (struct _SYSTEMTIME *)CoTaskMemAlloc(16 * v9);
      *a5 = v10;
      if ( v10 )
      {
        v11 = *a4;
        if ( *a4 >= v8 )
        {
          v14 = *a4;
        }
        else
        {
          v12 = v18;
          v13 = *a4;
          do
          {
            if ( !*((_DWORD *)v12 + 6) )
            {
              v14 = v13;
              if ( !*((_DWORD *)v12 + 7) )
                break;
            }
            FileTimeToSystemTime((const FILETIME *)v12 + 3, &(*a5)[v11]);
            v11 = ++*a4;
            v12 = (void ***)v12[1];
            v13 = *a4;
            v14 = *a4;
          }
          while ( *a4 < v8 );
        }
        RunTimesP = v14 < v5;
      }
      else
      {
        RunTimesP = -2147024882;
      }
    }
  }
  CRunList::~CRunList((CRunList *)&v17);
  return RunTimesP;
}

```

## disassembly

```asm
0x180025390  push    rbp
0x180025392  push    rbx
0x180025393  push    rsi
0x180025394  push    rdi
0x180025395  push    r14
0x180025397  push    r15
0x180025399  lea     rbp, [rsp-27h]
0x18002539e  sub     rsp, 0C8h
0x1800253a5  movzx   r15d, word ptr [r9]
0x1800253a9  lea     rax, ??_7CRun@@6B@; const CRun::`vftable'
0x1800253b0  mov     [rbp+4Fh+var_B0], rax
0x1800253b4  xorps   xmm0, xmm0
0x1800253b7  mov     rax, cs:qword_180054A68
0x1800253be  mov     rdi, r9
0x1800253c1  mov     [rbp+4Fh+var_90], rax
0x1800253c5  mov     r9d, 59Fh
0x1800253cb  mov     [rbp+4Fh+var_88], rax
0x1800253cf  xor     eax, eax
0x1800253d1  mov     [rbp+4Fh+var_48], ax
0x1800253d5  mov     [rbp+4Fh+var_44], rax
0x1800253d9  mov     [rbp+4Fh+var_3C], eax
0x1800253dc  mov     [rbp+4Fh+var_98], rax
0x1800253e0  lea     rax, [rbp+4Fh+var_B0]
0x1800253e4  mov     [rbp+4Fh+var_A8], rax
0x1800253e8  lea     rax, [rbp+4Fh+var_B0]
0x1800253ec  mov     [rbp+4Fh+var_A0], rax
0x1800253f0  lea     eax, [r15-1]
0x1800253f4  movdqa  [rbp+4Fh+var_80], xmm0
0x1800253f9  mov     [rbp+4Fh+var_70], 0
0x180025400  mov     [rbp+4Fh+var_68], 0
0x180025408  movdqa  [rbp+4Fh+var_60], xmm0
0x18002540d  mov     [rbp+4Fh+var_50], 0
0x180025414  mov     [rbp+4Fh+var_4C], 0FFFFFFFFh
0x18002541b  cmp     ax, r9w
0x18002541f  ja      loc_1800254D8
0x180025425  mov     r14, [rbp+4Fh+arg_20]
0x180025429  xor     eax, eax
0x18002542b  mov     r9, rdi; unsigned __int16 *
0x18002542e  mov     qword ptr [r14], 0
0x180025435  mov     [rdi], ax
0x180025438  lea     rax, [rbp+4Fh+var_B0]
0x18002543c  mov     [rsp+0F0h+var_C8], rax; struct CTimeRunList *
0x180025441  mov     [rsp+0F0h+var_D0], r15w; unsigned __int16
0x180025447  call    ?GetRunTimesP@CJob@@QEAAJPEBU_SYSTEMTIME@@0PEAGGPEAVCTimeRunList@@1@Z; CJob::GetRunTimesP(_SYSTEMTIME const *,_SYSTEMTIME const *,ushort *,ushort,CTimeRunList *,ushort *)
0x18002544c  mov     ebx, eax
0x18002544e  test    eax, eax
0x180025450  jz      short loc_18002545C
0x180025452  xor     ecx, ecx
0x180025454  mov     [rdi], cx
0x180025457  jmp     loc_1800254DD
0x18002545c  movzx   esi, word ptr [rdi]
0x18002545f  xor     eax, eax
0x180025461  mov     ecx, esi
0x180025463  mov     [rdi], ax
0x180025466  shl     rcx, 4; cb
0x18002546a  call    cs:__imp_CoTaskMemAlloc
0x180025470  mov     [r14], rax
0x180025473  test    rax, rax
0x180025476  jz      short loc_1800254D1
0x180025478  movzx   eax, word ptr [rdi]
0x18002547b  cmp     ax, si
0x18002547e  jnb     short loc_1800254C3
0x180025480  mov     rbx, [rbp+4Fh+var_A8]
0x180025484  movzx   r8d, ax
0x180025488  lea     rcx, [rbx+18h]; lpFileTime
0x18002548c  cmp     dword ptr [rcx], 0
0x18002548f  jnz     short loc_18002549B
0x180025491  cmp     dword ptr [rbx+1Ch], 0
0x180025495  movzx   edx, r8w
0x180025499  jz      short loc_1800254C6
0x18002549b  movzx   edx, ax
0x18002549e  shl     rdx, 4
0x1800254a2  add     rdx, [r14]; lpSystemTime
0x1800254a5  call    cs:__imp_FileTimeToSystemTime
0x1800254ab  inc     word ptr [rdi]
0x1800254ae  movzx   eax, word ptr [rdi]
0x1800254b1  mov     rbx, [rbx+8]
0x1800254b5  movzx   r8d, ax
0x1800254b9  movzx   edx, ax
0x1800254bc  cmp     ax, si
0x1800254bf  jb      short loc_180025488
0x1800254c1  jmp     short loc_1800254C6
0x1800254c3  movzx   edx, ax
0x1800254c6  xor     ebx, ebx
0x1800254c8  cmp     dx, r15w
0x1800254cc  setb    bl
0x1800254cf  jmp     short loc_1800254DD
0x1800254d1  mov     ebx, 8007000Eh
0x1800254d6  jmp     short loc_1800254DD
0x1800254d8  mov     ebx, 80070057h
0x1800254dd  lea     rcx, [rbp+4Fh+var_B0]; this
0x1800254e1  call    ??1CRunList@@QEAA@XZ; CRunList::~CRunList(void)
0x1800254e6  mov     eax, ebx
0x1800254e8  add     rsp, 0C8h
0x1800254ef  pop     r15
0x1800254f1  pop     r14
0x1800254f3  pop     rdi
0x1800254f4  pop     rsi
0x1800254f5  pop     rbx
0x1800254f6  pop     rbp
0x1800254f7  retn
```
