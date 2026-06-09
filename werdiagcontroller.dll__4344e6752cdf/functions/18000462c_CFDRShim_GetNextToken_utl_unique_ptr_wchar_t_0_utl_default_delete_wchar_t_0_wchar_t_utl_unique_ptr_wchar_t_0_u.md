# CFDRShim::GetNextToken(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,wchar_t,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)

- ea: `0x18000462c`
- end: `0x180004a6a`
- name: `?GetNextToken@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@_W0@Z`
- size: `1086`
- prototype: `__int64 __fastcall(void *, wchar_t **, wchar_t, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180004e1c`

## callees

- `0x180001cd4`
- `0x180003b58`
- `0x18000462c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004776`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180004776`
- `ntdll!DbgPrintEx` at `0x1800046bd`
- `ntdll!DbgPrintEx` at `0x180004836`
- `ntdll!DbgPrintEx` at `0x180004a06`
- `ntdll!DbgPrintEx` at `0x180004a24`
- `ntdll!DbgPrintEx` at `0x180004a4a`
- `ntdll!DbgPrintEx` at `0x1800046bd`
- `ntdll!DbgPrintEx` at `0x180004836`
- `ntdll!DbgPrintEx` at `0x180004a06`
- `ntdll!DbgPrintEx` at `0x180004a24`
- `ntdll!DbgPrintEx` at `0x180004a4a`

## string_xrefs

- `0x180004936`: `WERDIAG: Failed copying string. HRESULT: %08X\n`
- `0x1800049f5`: `WERDIAG: Failed making a copy of the original settings string. HRESULT: %08X\n`
- `0x18000481c`: `WERDIAG: Failed copying characters to pair buffer. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::GetNextToken(void *a1, wchar_t **a2, wchar_t a3, void **a4)
{
  wchar_t *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rsi
  wchar_t **unique_for; // rax
  wchar_t *v12; // r12
  wchar_t *v13; // rcx
  __int64 v14; // r13
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  wchar_t *v17; // r8
  wchar_t *v18; // rcx
  wchar_t *v19; // rax
  wchar_t *v20; // rcx
  wchar_t *v21; // rbx
  void **v22; // rax
  void *v23; // rdx
  void *v24; // rcx
  _WORD *v25; // rdx
  wchar_t *v26; // rax
  _WORD *v27; // rcx
  unsigned __int64 v28; // rbp
  wchar_t **v29; // rax
  wchar_t *v30; // rdx
  wchar_t *v31; // rcx
  wchar_t *v32; // rdx
  __int64 v33; // rax
  wchar_t *v34; // rcx
  wchar_t *v35; // rcx
  void **v36; // rax
  void *v37; // rdx
  void *v38; // rcx
  unsigned __int64 v39; // rax
  wchar_t *v40; // rcx
  void *v42; // [rsp+60h] [rbp+8h] BYREF
  wchar_t v43; // [rsp+70h] [rbp+18h]

  v43 = a3;
  v42 = a1;
  if ( a2 && a4 )
  {
    v6 = *a2;
    if ( *a2 )
    {
      v7 = 0x7FFFFFFF;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v7;
      }
      while ( v7 );
      v8 = v7 == 0 ? 0x80070057 : 0;
      v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
      if ( !v7 )
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed obtaining the length of the input string. HRESULT: %08X\n", v8);
        return v8;
      }
      v10 = v9 + 1;
      unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v42, v9 + 1);
      v12 = *unique_for;
      *unique_for = 0;
      if ( v42 )
        operator delete[](v42);
      if ( !v12 )
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
        return (unsigned int)-2147024882;
      }
      if ( v9 == -1 )
      {
        v8 = -2147024809;
        goto LABEL_80;
      }
      if ( v10 > 0x7FFFFFFF )
      {
        v8 = -2147024809;
        *v12 = 0;
LABEL_80:
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed making a copy of the original settings string. HRESULT: %08X\n", v8);
        goto LABEL_81;
      }
      v13 = *a2;
      v14 = 2147483646;
      v15 = 2147483646;
      v16 = v9 + 1;
      v17 = v12;
      do
      {
        if ( !v15 )
          break;
        if ( !*v13 )
          break;
        *v17++ = *v13++;
        --v15;
        --v16;
      }
      while ( v16 );
      v18 = v17 - 1;
      v8 = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
        v18 = v17;
      *v18 = 0;
      if ( !v16 )
        goto LABEL_80;
      v19 = wcschr(v12, v43);
      v20 = *a2;
      *a2 = 0;
      v21 = v19;
      if ( !v19 )
      {
        if ( v20 )
          operator delete[](v20);
        v22 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v42, v9 + 1);
        v23 = *v22;
        *v22 = 0;
        v24 = *a4;
        *a4 = v23;
        if ( v24 )
          operator delete[](v24);
        if ( v42 )
          operator delete[](v42);
        v25 = *a4;
        if ( *a4 )
        {
          v26 = v12;
          do
          {
            if ( !v14 )
              break;
            if ( !*v26 )
              break;
            *v25++ = *v26++;
            --v14;
            --v10;
          }
          while ( v10 );
          goto LABEL_34;
        }
        goto LABEL_38;
      }
      if ( v9 == 1 )
      {
        if ( v20 )
          operator delete[](v20);
        goto LABEL_42;
      }
      v10 = v19 - v12 + 1;
      if ( v20 )
        operator delete[](v20);
      if ( v10 < v9 )
      {
        v28 = v9 - v10 + 1;
        v29 = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v42, v28);
        v30 = *v29;
        *v29 = 0;
        v31 = *a2;
        *a2 = v30;
        if ( v31 )
          operator delete[](v31);
        if ( v42 )
          operator delete[](v42);
        v32 = *a2;
        if ( !*a2 )
          goto LABEL_38;
        if ( !v28 )
        {
          v8 = -2147024809;
          goto LABEL_63;
        }
        if ( v28 > 0x7FFFFFFF )
        {
          v8 = -2147024809;
          *v32 = 0;
LABEL_63:
          DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying string. HRESULT: %08X\n", v8);
          goto LABEL_81;
        }
        v33 = 2147483646;
        v34 = v21 + 1;
        do
        {
          if ( !v33 )
            break;
          if ( !*v34 )
            break;
          *v32++ = *v34++;
          --v33;
          --v28;
        }
        while ( v28 );
        v35 = v32 - 1;
        v8 = v28 == 0 ? 0x8007007A : 0;
        if ( v28 )
          v35 = v32;
        *v35 = 0;
        if ( !v28 )
          goto LABEL_63;
      }
      if ( v10 <= 1 )
        goto LABEL_42;
      v36 = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v42, v10);
      v37 = *v36;
      *v36 = 0;
      v38 = *a4;
      *a4 = v37;
      if ( v38 )
        operator delete[](v38);
      if ( v42 )
        operator delete[](v42);
      v25 = *a4;
      if ( *a4 )
      {
        if ( v10 <= 0x7FFFFFFF )
        {
          v39 = v10 - 1;
          if ( v10 - 1 <= 0x7FFFFFFE )
          {
            v40 = v12;
            do
            {
              if ( !v39 )
                break;
              if ( !*v40 )
                break;
              *v25++ = *v40++;
              --v39;
              --v10;
            }
            while ( v10 );
LABEL_34:
            v27 = v25 - 1;
            v8 = v10 == 0 ? 0x8007007A : 0;
            if ( v10 )
              v27 = v25;
            *v27 = 0;
            if ( !v10 )
              goto LABEL_37;
LABEL_42:
            v8 = 0;
            goto LABEL_81;
          }
          v8 = -2147024809;
          *v25 = 0;
        }
        else
        {
          *v25 = 0;
          v8 = -2147024809;
        }
LABEL_37:
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying characters to pair buffer. HRESULT: %08X\n", v8);
LABEL_81:
        operator delete[](v12);
        return v8;
      }
LABEL_38:
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
      v8 = -2147024882;
      goto LABEL_81;
    }
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid arguments: String buffer cannot be null\n");
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid arguments: Buffer or separator character cannot be null\n");
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000462c  mov     [rsp+arg_8], rbx
0x180004631  mov     [rsp+arg_10], r8w
0x180004637  mov     [rsp+arg_0], rcx
0x18000463c  push    rbp
0x18000463d  push    rsi
0x18000463e  push    rdi
0x18000463f  push    r12
0x180004641  push    r13
0x180004643  push    r14
0x180004645  push    r15
0x180004647  sub     rsp, 20h
0x18000464b  xor     r13d, r13d
0x18000464e  mov     r15, r9
0x180004651  mov     r14, rdx
0x180004654  test    rdx, rdx
0x180004657  jz      loc_180004A3C
0x18000465d  test    r9, r9
0x180004660  jz      loc_180004A3C
0x180004666  mov     rax, [rdx]
0x180004669  test    rax, rax
0x18000466c  jz      loc_180004A33
0x180004672  mov     ecx, 7FFFFFFFh
0x180004677  mov     edx, ecx
0x180004679  cmp     [rax], r13w
0x18000467d  jz      short loc_180004689
0x18000467f  add     rax, 2
0x180004683  sub     rdx, 1; Level
0x180004687  jnz     short loc_180004679
0x180004689  mov     rax, rdx
0x18000468c  mov     edi, 80070057h
0x180004691  neg     rax
0x180004694  mov     rax, rdx
0x180004697  sbb     ebx, ebx
0x180004699  sub     rcx, rdx
0x18000469c  not     ebx
0x18000469e  and     ebx, edi
0x1800046a0  neg     rax
0x1800046a3  sbb     rbp, rbp
0x1800046a6  and     rbp, rcx
0x1800046a9  test    rdx, rdx
0x1800046ac  jnz     short loc_1800046C8
0x1800046ae  mov     r9d, ebx
0x1800046b1  lea     r8, aWerdiagFailedO_2; "WERDIAG: Failed obtaining the length of"...
0x1800046b8  mov     ecx, 96h; ComponentId
0x1800046bd  call    cs:__imp_DbgPrintEx
0x1800046c3  jmp     loc_180004A2F
0x1800046c8  lea     rsi, [rbp+1]
0x1800046cc  mov     rdx, rsi
0x1800046cf  lea     rcx, [rsp+58h+arg_0]
0x1800046d4  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800046d9  mov     r12, [rax]
0x1800046dc  mov     [rax], r13
0x1800046df  mov     rcx, [rsp+58h+arg_0]; void *
0x1800046e4  test    rcx, rcx
0x1800046e7  jz      short loc_1800046EE
0x1800046e9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800046ee  test    r12, r12
0x1800046f1  jz      loc_180004A16
0x1800046f7  test    rsi, rsi
0x1800046fa  jz      loc_1800049E9
0x180004700  cmp     rsi, 7FFFFFFFh
0x180004707  jbe     short loc_180004710
0x180004709  mov     ebx, edi
0x18000470b  jmp     loc_1800049F0
0x180004710  mov     rcx, [r14]
0x180004713  mov     r13d, 7FFFFFFEh
0x180004719  mov     eax, r13d
0x18000471c  mov     rdx, rsi
0x18000471f  mov     r8, r12
0x180004722  xor     r10d, r10d
0x180004725  test    rax, rax
0x180004728  jz      short loc_180004749
0x18000472a  movzx   r9d, word ptr [rcx]
0x18000472e  test    r9w, r9w
0x180004732  jz      short loc_180004749
0x180004734  mov     [r8], r9w
0x180004738  add     rcx, 2
0x18000473c  add     r8, 2
0x180004740  dec     rax
0x180004743  sub     rdx, 1
0x180004747  jnz     short loc_180004725
0x180004749  mov     rax, rdx
0x18000474c  lea     rcx, [r8-2]
0x180004750  neg     rax
0x180004753  sbb     ebx, ebx
0x180004755  not     ebx
0x180004757  and     ebx, 8007007Ah
0x18000475d  test    rdx, rdx
0x180004760  cmovnz  rcx, r8
0x180004764  mov     [rcx], r10w
0x180004768  jz      loc_1800049F5
0x18000476e  movzx   edx, [rsp+58h+arg_10]; Ch
0x180004773  mov     rcx, r12; Str
0x180004776  call    cs:__imp_wcschr
0x18000477c  mov     rcx, [r14]; void *
0x18000477f  xor     edx, edx
0x180004781  mov     [r14], rdx
0x180004784  mov     rbx, rax
0x180004787  test    rax, rax
0x18000478a  jnz     loc_180004846
0x180004790  xor     r14d, r14d
0x180004793  test    rcx, rcx
0x180004796  jz      short loc_18000479D
0x180004798  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000479d  mov     rdx, rsi
0x1800047a0  lea     rcx, [rsp+58h+arg_0]
0x1800047a5  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800047aa  mov     rdx, [rax]
0x1800047ad  mov     [rax], r14
0x1800047b0  mov     rcx, [r15]; void *
0x1800047b3  mov     [r15], rdx
0x1800047b6  test    rcx, rcx
0x1800047b9  jz      short loc_1800047C0
0x1800047bb  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047c0  mov     rcx, [rsp+58h+arg_0]; void *
0x1800047c5  test    rcx, rcx
0x1800047c8  jz      short loc_1800047CF
0x1800047ca  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800047cf  mov     rdx, [r15]
0x1800047d2  test    rdx, rdx
0x1800047d5  jz      short loc_180004828
0x1800047d7  mov     rax, r12
0x1800047da  test    r13, r13
0x1800047dd  jz      short loc_1800047FB
0x1800047df  movzx   ecx, word ptr [rax]
0x1800047e2  test    cx, cx
0x1800047e5  jz      short loc_1800047FB
0x1800047e7  mov     [rdx], cx
0x1800047ea  add     rax, 2
0x1800047ee  add     rdx, 2
0x1800047f2  dec     r13
0x1800047f5  sub     rsi, 1
0x1800047f9  jnz     short loc_1800047DA
0x1800047fb  mov     rax, rsi
0x1800047fe  lea     rcx, [rdx-2]
0x180004802  neg     rax
0x180004805  sbb     ebx, ebx
0x180004807  not     ebx
0x180004809  and     ebx, 8007007Ah
0x18000480f  test    rsi, rsi
0x180004812  cmovnz  rcx, rdx
0x180004816  mov     [rcx], r14w
0x18000481a  jnz     short loc_180004859
0x18000481c  lea     r8, aWerdiagFailedC; "WERDIAG: Failed copying characters to p"...
0x180004823  jmp     loc_1800049FC
0x180004828  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x18000482f  xor     edx, edx; Level
0x180004831  mov     ecx, 96h; ComponentId
0x180004836  call    cs:__imp_DbgPrintEx
0x18000483c  mov     ebx, 8007000Eh
0x180004841  jmp     loc_180004A0C
0x180004846  cmp     rbp, 1
0x18000484a  jnz     short loc_180004861
0x18000484c  xor     r14d, r14d
0x18000484f  test    rcx, rcx
0x180004852  jz      short loc_180004859
0x180004854  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004859  mov     ebx, r14d
0x18000485c  jmp     loc_180004A0C
0x180004861  mov     rsi, rbx
0x180004864  sub     rsi, r12
0x180004867  sar     rsi, 1
0x18000486a  inc     rsi
0x18000486d  test    rcx, rcx
0x180004870  jz      short loc_180004877
0x180004872  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004877  cmp     rsi, rbp
0x18000487a  jnb     loc_180004942
0x180004880  sub     rbp, rsi
0x180004883  lea     rcx, [rsp+58h+arg_0]
0x180004888  inc     rbp
0x18000488b  mov     rdx, rbp
0x18000488e  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180004893  mov     rdx, [rax]
0x180004896  mov     qword ptr [rax], 0
0x18000489d  mov     rcx, [r14]; void *
0x1800048a0  mov     [r14], rdx
0x1800048a3  test    rcx, rcx
0x1800048a6  jz      short loc_1800048AD
0x1800048a8  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800048ad  mov     rcx, [rsp+58h+arg_0]; void *
0x1800048b2  test    rcx, rcx
0x1800048b5  jz      short loc_1800048BC
0x1800048b7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800048bc  mov     rdx, [r14]
0x1800048bf  xor     r14d, r14d
0x1800048c2  test    rdx, rdx
0x1800048c5  jz      loc_180004828
0x1800048cb  test    rbp, rbp
0x1800048ce  jz      short loc_18000492B
0x1800048d0  cmp     rbp, 7FFFFFFFh
0x1800048d7  jbe     short loc_1800048DD
0x1800048d9  mov     ebx, edi
0x1800048db  jmp     short loc_180004932
0x1800048dd  mov     rax, r13
0x1800048e0  lea     rcx, [rbx+2]
0x1800048e4  test    rax, rax
0x1800048e7  jz      short loc_180004908
0x1800048e9  movzx   r8d, word ptr [rcx]
0x1800048ed  test    r8w, r8w
0x1800048f1  jz      short loc_180004908
0x1800048f3  mov     [rdx], r8w
0x1800048f7  add     rcx, 2
0x1800048fb  add     rdx, 2
0x1800048ff  dec     rax
0x180004902  sub     rbp, 1
0x180004906  jnz     short loc_1800048E4
0x180004908  mov     rax, rbp
0x18000490b  lea     rcx, [rdx-2]
0x18000490f  neg     rax
0x180004912  sbb     ebx, ebx
0x180004914  not     ebx
0x180004916  and     ebx, 8007007Ah
0x18000491c  test    rbp, rbp
0x18000491f  cmovnz  rcx, rdx
0x180004923  mov     [rcx], r14w
0x180004927  jnz     short loc_180004945
0x180004929  jmp     short loc_180004936
0x18000492b  mov     ebx, edi
0x18000492d  test    rbp, rbp
0x180004930  jz      short loc_180004936
0x180004932  mov     [rdx], r14w
0x180004936  lea     r8, aWerdiagFailedC_3; "WERDIAG: Failed copying string. HRESULT"...
0x18000493d  jmp     loc_1800049FC
0x180004942  xor     r14d, r14d
0x180004945  cmp     rsi, 1
0x180004949  jbe     loc_180004859
0x18000494f  mov     rdx, rsi
0x180004952  lea     rcx, [rsp+58h+arg_0]
0x180004957  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18000495c  mov     rdx, [rax]
0x18000495f  mov     [rax], r14
0x180004962  mov     rcx, [r15]; void *
0x180004965  mov     [r15], rdx
0x180004968  test    rcx, rcx
0x18000496b  jz      short loc_180004972
0x18000496d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004972  mov     rcx, [rsp+58h+arg_0]; void *
0x180004977  test    rcx, rcx
0x18000497a  jz      short loc_180004981
0x18000497c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004981  mov     rdx, [r15]
0x180004984  test    rdx, rdx
0x180004987  jz      loc_180004828
0x18000498d  cmp     rsi, 7FFFFFFFh
0x180004994  jbe     short loc_1800049A1
0x180004996  mov     [rdx], r14w
0x18000499a  mov     ebx, edi
0x18000499c  jmp     loc_18000481C
0x1800049a1  lea     rax, [rsi-1]
0x1800049a5  cmp     rax, r13
0x1800049a8  jbe     short loc_1800049B5
0x1800049aa  mov     ebx, edi
0x1800049ac  mov     [rdx], r14w
0x1800049b0  jmp     loc_18000481C
0x1800049b5  mov     rcx, r12
0x1800049b8  test    rax, rax
0x1800049bb  jz      loc_1800047FB
0x1800049c1  movzx   r8d, word ptr [rcx]
0x1800049c5  test    r8w, r8w
0x1800049c9  jz      loc_1800047FB
0x1800049cf  mov     [rdx], r8w
0x1800049d3  add     rcx, 2
0x1800049d7  add     rdx, 2
0x1800049db  dec     rax
0x1800049de  sub     rsi, 1
0x1800049e2  jnz     short loc_1800049B8
0x1800049e4  jmp     loc_1800047FB
0x1800049e9  mov     ebx, edi
0x1800049eb  test    rsi, rsi
0x1800049ee  jz      short loc_1800049F5
0x1800049f0  mov     [r12], r13w
0x1800049f5  lea     r8, aWerdiagFailedM; "WERDIAG: Failed making a copy of the or"...
0x1800049fc  mov     r9d, ebx
0x1800049ff  xor     edx, edx; Level
0x180004a01  mov     ecx, 96h; ComponentId
0x180004a06  call    cs:__imp_DbgPrintEx
0x180004a0c  mov     rcx, r12; void *
0x180004a0f  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004a14  jmp     short loc_180004A2F
0x180004a16  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x180004a1d  xor     edx, edx; Level
0x180004a1f  mov     ecx, 96h; ComponentId
0x180004a24  call    cs:__imp_DbgPrintEx
0x180004a2a  mov     ebx, 8007000Eh
0x180004a2f  mov     eax, ebx
0x180004a31  jmp     short loc_180004A55
0x180004a33  lea     r8, aWerdiagInvalid_8; "WERDIAG: Invalid arguments: String buff"...
0x180004a3a  jmp     short loc_180004A43
0x180004a3c  lea     r8, aWerdiagInvalid_9; "WERDIAG: Invalid arguments: Buffer or s"...
0x180004a43  xor     edx, edx; Level
0x180004a45  mov     ecx, 96h; ComponentId
0x180004a4a  call    cs:__imp_DbgPrintEx
0x180004a50  mov     eax, 80070057h
0x180004a55  mov     rbx, [rsp+58h+arg_8]
0x180004a5a  add     rsp, 20h
0x180004a5e  pop     r15
0x180004a60  pop     r14
0x180004a62  pop     r13
0x180004a64  pop     r12
  ... truncated ...
```
