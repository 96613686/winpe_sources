# CEngineLocaleHandler::WordBreakerWithTopResult(ushort const *,long,SRWORDBREAKERFLAGS,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *,bool)

- ea: `0x1800cabd4`
- end: `0x1800cb011`
- name: `?WordBreakerWithTopResult@CEngineLocaleHandler@@IEAAJPEBGJW4SRWORDBREAKERFLAGS@@PEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@_N@Z`
- size: `1085`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ca750`
- `0x1800cabb0`

## callees

- `0x180002aac`
- `0x180004312`
- `0x1800c94c4`
- `0x1800cabd4`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800caeee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800caf00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800caf12`
- `OLEAUT32!__imp_SysFreeString` at `0x1800caeee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800caf00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800caf12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cae4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cae4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cad0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cad0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cacba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cacba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cac41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cac41`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandler::WordBreakerWithTopResult(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        char a6)
{
  __int64 v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  int v12; // ebx
  size_t v13; // r15
  unsigned __int64 v14; // rsi
  char *v15; // rax
  char *v16; // r14
  void *v17; // rdx
  __int64 v18; // r15
  char *v19; // r14
  unsigned int v20; // r13d
  unsigned int v21; // edi
  OLECHAR *v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // r8
  int v25; // eax
  void *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  size_t v31; // r8
  char *v32; // rcx
  void *v33; // rdx
  LPVOID pv; // [rsp+40h] [rbp-49h] BYREF
  void *v36; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-31h] BYREF
  void *v39; // [rsp+60h] [rbp-29h] BYREF
  BSTR v40; // [rsp+68h] [rbp-21h] BYREF
  int v41; // [rsp+70h] [rbp-19h] BYREF
  BSTR v42; // [rsp+78h] [rbp-11h] BYREF
  void *Src; // [rsp+80h] [rbp-9h] BYREF
  __int64 v44; // [rsp+88h] [rbp-1h]
  __int64 v45; // [rsp+90h] [rbp+7h]
  size_t Size; // [rsp+98h] [rbp+Fh]
  unsigned int v47; // [rsp+E8h] [rbp+5Fh] BYREF
  unsigned int v48; // [rsp+F8h] [rbp+6Fh]

  v48 = a4;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v10 = a5;
  if ( !a5 )
    return 2147942487LL;
  v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 160);
  Src = 0;
  v37 = 0;
  v36 = 0;
  v47 = 0;
  v39 = 0;
  v41 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  v12 = CEngineLocaleHandler::EnsureTextNormalizer((CEngineLocaleHandler *)a1);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(a1 + 120) + 8LL))(
            *(_QWORD *)(a1 + 120),
            a2,
            a3,
            a4);
    if ( v12 >= 0 )
      v12 = (*(__int64 (__fastcall **)(_QWORD, void **, unsigned int *, unsigned int *, void **, int *, void **))(**(_QWORD **)(a1 + 120) + 16LL))(
              *(_QWORD *)(a1 + 120),
              &Src,
              &v37,
              &v47,
              &v36,
              &v41,
              &v39);
  }
  LeaveCriticalSection(v11);
  if ( v12 < 0 )
    goto LABEL_56;
  if ( !v47 )
  {
    v12 = 1;
    *(_OWORD *)v10 = 0;
    *(_OWORD *)(v10 + 16) = 0;
    *(_OWORD *)(v10 + 32) = 0;
    goto LABEL_56;
  }
  v13 = 2LL * v37;
  v45 = 8LL * v47;
  v14 = (v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  Size = 12LL * v47;
  v15 = (char *)CoTaskMemAlloc(v45 + ((Size + 7) & 0xFFFFFFFFFFFFFFF8uLL) + v14 + 48);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -2147024882;
    goto LABEL_56;
  }
  v17 = Src;
  *(_DWORD *)v10 = v47;
  *(_QWORD *)(v10 + 40) = v15;
  *(_QWORD *)(v10 + 8) = v15;
  memcpy_0(v15, v17, v13);
  v18 = *(_QWORD *)(v10 + 8);
  v19 = &v16[v14];
  v20 = 0;
  *(_QWORD *)(v10 + 16) = v19;
  if ( !v47 )
    goto LABEL_53;
  v21 = 0;
  while ( v12 >= 0 )
  {
    if ( (v48 & 2) != 0 )
    {
      v22 = 0;
      bstrString = 0;
      v40 = 0;
      v42 = 0;
      v23 = 3LL * v20;
      v44 = v23;
      if ( (*((_BYTE *)v36 + 12 * v20 + 8) & 4) == 0 )
      {
        if ( v18 )
        {
          v28 = -1;
          do
            ++v28;
          while ( *(_WORD *)(v18 + 2 * v28) );
          if ( v28 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BSTR *, BSTR *, BSTR *))(*(_QWORD *)a1 + 48LL))(
                    a1,
                    v18,
                    0,
                    &bstrString,
                    &v40,
                    &v42);
            goto LABEL_32;
          }
        }
        goto LABEL_35;
      }
      pv = 0;
      v24 = *((_QWORD *)v39 + v21);
      if ( !v24 )
        goto LABEL_34;
      v25 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v24 + 184LL))(*((_QWORD *)v39 + v21), 1);
      v12 = v25;
      if ( !a6
        || v25 < 0
        || (v12 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)v39 + v21) + 24LL))(
                    *((_QWORD *)v39 + v21),
                    &pv),
            v12 < 0) )
      {
LABEL_24:
        v26 = pv;
        goto LABEL_25;
      }
      v26 = pv;
      if ( !pv )
        goto LABEL_33;
      v27 = -1;
      do
        ++v27;
      while ( *((_WORD *)pv + v27) );
      if ( v27 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, BSTR *, BSTR *, BSTR *))(*(_QWORD *)a1 + 48LL))(
                a1,
                pv,
                0,
                &bstrString,
                &v40,
                &v42);
        goto LABEL_24;
      }
LABEL_25:
      if ( v26 )
        CoTaskMemFree(v26);
LABEL_32:
      if ( v12 >= 0 )
      {
LABEL_33:
        v22 = bstrString;
LABEL_34:
        v23 = v44;
LABEL_35:
        LODWORD(pv) = 0;
        if ( v22 )
        {
          if ( v40 )
          {
            (*(void (__fastcall **)(__int64, OLECHAR *, BSTR, LPVOID *))(*(_QWORD *)a1 + 56LL))(a1, v22, v40, &pv);
            if ( (_DWORD)pv )
              *((_DWORD *)v36 + v23 + 2) |= 1u;
            goto LABEL_39;
          }
LABEL_40:
          if ( v22 )
            SysFreeString(v22);
        }
        if ( v40 )
          SysFreeString(v40);
        if ( v42 )
          SysFreeString(v42);
        goto LABEL_46;
      }
LABEL_39:
      v22 = bstrString;
      goto LABEL_40;
    }
LABEL_46:
    if ( (*((_BYTE *)v36 + 12 * v20 + 8) & 4) != 0 )
    {
      v30 = v21++;
      *(_QWORD *)&v19[8 * v20] = *((_QWORD *)v39 + v30);
    }
    else
    {
      *(_QWORD *)&v19[8 * v20] = v18;
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(v18 + 2 * v29) );
      v18 += 2 * v29 + 2;
    }
    if ( ++v20 >= v47 )
      break;
  }
  v10 = a5;
LABEL_53:
  v31 = Size;
  v32 = &v19[v45];
  v33 = v36;
  *(_QWORD *)(v10 + 32) = &v19[v45];
  *(_QWORD *)(v10 + 24) = 0;
  memcpy_0(v32, v33, v31);
LABEL_56:
  if ( Src )
    CWinHeap::Free((CWinHeap *)&g_heap, Src);
  if ( v36 )
    CWinHeap::Free((CWinHeap *)&g_heap, v36);
  if ( v39 )
    CWinHeap::Free((CWinHeap *)&g_heap, v39);
  if ( v12 >= 0 )
    return v47 == 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800cabd4  mov     [rsp-8+arg_0], rbx
0x1800cabd9  mov     [rsp-8+arg_18], r9d
0x1800cabde  push    rbp
0x1800cabdf  push    rsi
0x1800cabe0  push    rdi
0x1800cabe1  push    r12
0x1800cabe3  push    r13
0x1800cabe5  push    r14
0x1800cabe7  push    r15
0x1800cabe9  lea     rbp, [rsp-17h]
0x1800cabee  sub     rsp, 0A0h
0x1800cabf5  xor     eax, eax
0x1800cabf7  mov     r13d, r9d
0x1800cabfa  mov     r14d, r8d
0x1800cabfd  mov     r15, rdx
0x1800cac00  mov     r12, rcx
0x1800cac03  test    rdx, rdx
0x1800cac06  jz      loc_1800CAFF1
0x1800cac0c  test    r8d, r8d
0x1800cac0f  jz      loc_1800CAFF1
0x1800cac15  mov     rdi, [rbp+47h+arg_20]
0x1800cac19  test    rdi, rdi
0x1800cac1c  jz      loc_1800CAFF1
0x1800cac22  lea     rsi, [rcx+0A0h]
0x1800cac29  mov     [rbp+47h+Src], rax
0x1800cac2d  mov     rcx, rsi; lpCriticalSection
0x1800cac30  mov     [rbp+47h+var_80], eax
0x1800cac33  mov     [rbp+47h+var_88], rax
0x1800cac37  mov     [rbp+47h+arg_8], eax
0x1800cac3a  mov     [rbp+47h+var_70], rax
0x1800cac3e  mov     [rbp+47h+var_60], eax
0x1800cac41  call    cs:__imp_EnterCriticalSection
0x1800cac47  mov     rcx, r12; this
0x1800cac4a  call    ?EnsureTextNormalizer@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureTextNormalizer(void)
0x1800cac4f  mov     ebx, eax
0x1800cac51  test    eax, eax
0x1800cac53  js      short loc_1800CACB4
0x1800cac55  mov     rcx, [r12+78h]
0x1800cac5a  mov     r9d, r13d
0x1800cac5d  mov     r8d, r14d
0x1800cac60  mov     rdx, r15
0x1800cac63  mov     rax, [rcx]
0x1800cac66  mov     rax, [rax+8]
0x1800cac6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac6f  xor     r13d, r13d
0x1800cac72  mov     ebx, eax
0x1800cac74  test    eax, eax
0x1800cac76  js      short loc_1800CACB7
0x1800cac78  mov     rcx, [r12+78h]
0x1800cac7d  lea     rdx, [rbp+47h+var_70]
0x1800cac81  mov     [rsp+0D0h+var_A0], rdx
0x1800cac86  lea     r9, [rbp+47h+arg_8]
0x1800cac8a  lea     rdx, [rbp+47h+var_60]
0x1800cac8e  mov     [rsp+0D0h+var_A8], rdx
0x1800cac93  lea     r8, [rbp+47h+var_80]
0x1800cac97  mov     rax, [rcx]
0x1800cac9a  lea     rdx, [rbp+47h+var_88]
0x1800cac9e  mov     [rsp+0D0h+var_B0], rdx
0x1800caca3  lea     rdx, [rbp+47h+Src]
0x1800caca7  mov     rax, [rax+10h]
0x1800cacab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cacb0  mov     ebx, eax
0x1800cacb2  jmp     short loc_1800CACB7
0x1800cacb4  xor     r13d, r13d
0x1800cacb7  mov     rcx, rsi; lpCriticalSection
0x1800cacba  call    cs:__imp_LeaveCriticalSection
0x1800cacc0  test    ebx, ebx
0x1800cacc2  js      loc_1800CAFA5
0x1800cacc8  mov     ecx, [rbp+47h+arg_8]
0x1800caccb  test    ecx, ecx
0x1800caccd  jz      loc_1800CAF92
0x1800cacd3  mov     eax, [rbp+47h+var_80]
0x1800cacd6  lea     r15, [rax+rax]
0x1800cacda  mov     eax, ecx
0x1800cacdc  lea     rcx, ds:0[rcx*8]
0x1800cace4  mov     [rbp+47h+var_40], rcx
0x1800cace8  lea     rsi, [r15+7]
0x1800cacec  and     rsi, 0FFFFFFFFFFFFFFF8h
0x1800cacf0  lea     rax, [rax+rax*2]
0x1800cacf4  shl     rax, 2
0x1800cacf8  mov     [rbp+47h+Size], rax
0x1800cacfc  add     rax, 7
0x1800cad00  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800cad04  add     rax, rcx
0x1800cad07  lea     rcx, [rsi+30h]
0x1800cad0b  add     rcx, rax; cb
0x1800cad0e  call    cs:__imp_CoTaskMemAlloc
0x1800cad14  mov     r14, rax
0x1800cad17  test    rax, rax
0x1800cad1a  jz      loc_1800CAF8B
0x1800cad20  mov     ecx, [rbp+47h+arg_8]
0x1800cad23  mov     r8, r15; Size
0x1800cad26  mov     rdx, [rbp+47h+Src]; Src
0x1800cad2a  mov     [rdi], ecx
0x1800cad2c  mov     rcx, rax; void *
0x1800cad2f  mov     [rdi+28h], rax
0x1800cad33  mov     [rdi+8], rax
0x1800cad37  call    memcpy_0
0x1800cad3c  mov     r15, [rdi+8]
0x1800cad40  xor     r9d, r9d
0x1800cad43  add     r14, rsi
0x1800cad46  mov     r13d, r9d
0x1800cad49  mov     [rdi+10h], r14
0x1800cad4d  cmp     [rbp+47h+arg_8], r9d
0x1800cad51  jbe     loc_1800CAF6A
0x1800cad57  mov     edi, r9d
0x1800cad5a  test    ebx, ebx
0x1800cad5c  js      loc_1800CAF66
0x1800cad62  test    byte ptr [rbp+47h+arg_18], 2
0x1800cad66  jz      loc_1800CAF1B
0x1800cad6c  mov     eax, r13d
0x1800cad6f  mov     rcx, r9
0x1800cad72  mov     [rbp+47h+bstrString], rcx
0x1800cad76  mov     [rbp+47h+var_68], r9
0x1800cad7a  mov     [rbp+47h+var_58], r9
0x1800cad7e  lea     rsi, [rax+rax*2]
0x1800cad82  mov     rax, [rbp+47h+var_88]
0x1800cad86  mov     [rbp+47h+var_48], rsi
0x1800cad8a  test    byte ptr [rax+rsi*4+8], 4
0x1800cad8f  jz      loc_1800CAE55
0x1800cad95  mov     rax, [rbp+47h+var_70]
0x1800cad99  mov     esi, edi
0x1800cad9b  mov     [rbp+47h+pv], r9
0x1800cad9f  mov     r8, [rax+rsi*8]
0x1800cada3  test    r8, r8
0x1800cada6  jz      loc_1800CAEA6
0x1800cadac  mov     rax, [r8]
0x1800cadaf  mov     edx, 1
0x1800cadb4  mov     rcx, r8
0x1800cadb7  mov     rax, [rax+0B8h]
0x1800cadbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadc3  xor     r9d, r9d
0x1800cadc6  mov     ebx, eax
0x1800cadc8  cmp     [rbp+47h+arg_28], r9b
0x1800cadcc  jz      short loc_1800CAE44
0x1800cadce  test    eax, eax
0x1800cadd0  js      short loc_1800CAE44
0x1800cadd2  mov     rax, [rbp+47h+var_70]
0x1800cadd6  lea     rdx, [rbp+47h+pv]
0x1800cadda  mov     rcx, [rax+rsi*8]
0x1800cadde  mov     rax, [rcx]
0x1800cade1  mov     rax, [rax+18h]
0x1800cade5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadea  xor     r9d, r9d
0x1800caded  mov     ebx, eax
0x1800cadef  test    eax, eax
0x1800cadf1  js      short loc_1800CAE44
0x1800cadf3  mov     rcx, [rbp+47h+pv]
0x1800cadf7  test    rcx, rcx
0x1800cadfa  jz      loc_1800CAEA2
0x1800cae00  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cae04  inc     rax
0x1800cae07  cmp     [rcx+rax*2], r9w
0x1800cae0c  jnz     short loc_1800CAE04
0x1800cae0e  test    rax, rax
0x1800cae11  jz      short loc_1800CAE48
0x1800cae13  mov     rax, [r12]
0x1800cae17  lea     rdx, [rbp+47h+var_58]
0x1800cae1b  mov     [rsp+0D0h+var_A8], rdx
0x1800cae20  lea     r9, [rbp+47h+bstrString]
0x1800cae24  lea     rdx, [rbp+47h+var_68]
0x1800cae28  xor     r8d, r8d
0x1800cae2b  mov     [rsp+0D0h+var_B0], rdx
0x1800cae30  mov     rdx, rcx
0x1800cae33  mov     rax, [rax+30h]
0x1800cae37  mov     rcx, r12
0x1800cae3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cae3f  mov     ebx, eax
0x1800cae41  xor     r9d, r9d
0x1800cae44  mov     rcx, [rbp+47h+pv]; pv
0x1800cae48  test    rcx, rcx
0x1800cae4b  jz      short loc_1800CAE9E
0x1800cae4d  call    cs:__imp_CoTaskMemFree
0x1800cae53  jmp     short loc_1800CAE9B
0x1800cae55  test    r15, r15
0x1800cae58  jz      short loc_1800CAEAA
0x1800cae5a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cae5e  inc     rax
0x1800cae61  cmp     [r15+rax*2], r9w
0x1800cae66  jnz     short loc_1800CAE5E
0x1800cae68  test    rax, rax
0x1800cae6b  jz      short loc_1800CAEAA
0x1800cae6d  mov     rax, [r12]
0x1800cae71  lea     rcx, [rbp+47h+var_58]
0x1800cae75  mov     [rsp+0D0h+var_A8], rcx
0x1800cae7a  lea     r9, [rbp+47h+bstrString]
0x1800cae7e  lea     rcx, [rbp+47h+var_68]
0x1800cae82  xor     r8d, r8d
0x1800cae85  mov     [rsp+0D0h+var_B0], rcx
0x1800cae8a  mov     rdx, r15
0x1800cae8d  mov     rax, [rax+30h]
0x1800cae91  mov     rcx, r12
0x1800cae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cae99  mov     ebx, eax
0x1800cae9b  xor     r9d, r9d
0x1800cae9e  test    ebx, ebx
0x1800caea0  js      short loc_1800CAEE5
0x1800caea2  mov     rcx, [rbp+47h+bstrString]
0x1800caea6  mov     rsi, [rbp+47h+var_48]
0x1800caeaa  mov     dword ptr [rbp+47h+pv], r9d
0x1800caeae  test    rcx, rcx
0x1800caeb1  jz      short loc_1800CAEF7
0x1800caeb3  mov     r8, [rbp+47h+var_68]
0x1800caeb7  test    r8, r8
0x1800caeba  jz      short loc_1800CAEE9
0x1800caebc  mov     rax, [r12]
0x1800caec0  lea     r9, [rbp+47h+pv]
0x1800caec4  mov     rdx, rcx
0x1800caec7  mov     rcx, r12
0x1800caeca  mov     rax, [rax+38h]
0x1800caece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caed3  xor     r9d, r9d
0x1800caed6  cmp     dword ptr [rbp+47h+pv], r9d
0x1800caeda  jz      short loc_1800CAEE5
0x1800caedc  mov     rax, [rbp+47h+var_88]
0x1800caee0  or      dword ptr [rax+rsi*4+8], 1
0x1800caee5  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800caee9  test    rcx, rcx
0x1800caeec  jz      short loc_1800CAEF7
0x1800caeee  call    cs:__imp_SysFreeString
0x1800caef4  xor     r9d, r9d
0x1800caef7  mov     rcx, [rbp+47h+var_68]; bstrString
0x1800caefb  test    rcx, rcx
0x1800caefe  jz      short loc_1800CAF09
0x1800caf00  call    cs:__imp_SysFreeString
0x1800caf06  xor     r9d, r9d
0x1800caf09  mov     rcx, [rbp+47h+var_58]; bstrString
0x1800caf0d  test    rcx, rcx
0x1800caf10  jz      short loc_1800CAF1B
0x1800caf12  call    cs:__imp_SysFreeString
0x1800caf18  xor     r9d, r9d
0x1800caf1b  mov     rax, [rbp+47h+var_88]
0x1800caf1f  mov     edx, r13d
0x1800caf22  lea     rcx, [rdx+rdx*2]
0x1800caf26  test    byte ptr [rax+rcx*4+8], 4
0x1800caf2b  jnz     short loc_1800CAF49
0x1800caf2d  mov     [r14+rdx*8], r15
0x1800caf31  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800caf35  inc     rax
0x1800caf38  cmp     [r15+rax*2], r9w
0x1800caf3d  jnz     short loc_1800CAF35
0x1800caf3f  lea     r15, [r15+rax*2]
0x1800caf43  add     r15, 2
0x1800caf47  jmp     short loc_1800CAF59
0x1800caf49  mov     rax, [rbp+47h+var_70]
0x1800caf4d  mov     ecx, edi
0x1800caf4f  inc     edi
0x1800caf51  mov     rcx, [rax+rcx*8]
0x1800caf55  mov     [r14+rdx*8], rcx
0x1800caf59  inc     r13d
0x1800caf5c  cmp     r13d, [rbp+47h+arg_8]
0x1800caf60  jb      loc_1800CAD5A
0x1800caf66  mov     rdi, [rbp+47h+arg_20]
0x1800caf6a  mov     rcx, [rbp+47h+var_40]
0x1800caf6e  mov     r8, [rbp+47h+Size]; Size
0x1800caf72  add     rcx, r14; void *
0x1800caf75  mov     rdx, [rbp+47h+var_88]; Src
0x1800caf79  mov     [rdi+20h], rcx
0x1800caf7d  mov     [rdi+18h], r9
0x1800caf81  call    memcpy_0
0x1800caf86  xor     r13d, r13d
0x1800caf89  jmp     short loc_1800CAFA5
0x1800caf8b  mov     ebx, 8007000Eh
0x1800caf90  jmp     short loc_1800CAFA5
0x1800caf92  xorps   xmm0, xmm0
0x1800caf95  mov     ebx, 1
0x1800caf9a  movups  xmmword ptr [rdi], xmm0
0x1800caf9d  movups  xmmword ptr [rdi+10h], xmm0
0x1800cafa1  movups  xmmword ptr [rdi+20h], xmm0
0x1800cafa5  mov     rdx, [rbp+47h+Src]; void *
0x1800cafa9  lea     rdi, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x1800cafb0  test    rdx, rdx
0x1800cafb3  jz      short loc_1800CAFBD
0x1800cafb5  mov     rcx, rdi; this
0x1800cafb8  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800cafbd  mov     rdx, [rbp+47h+var_88]; void *
0x1800cafc1  test    rdx, rdx
0x1800cafc4  jz      short loc_1800CAFCE
0x1800cafc6  mov     rcx, rdi; this
0x1800cafc9  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800cafce  mov     rdx, [rbp+47h+var_70]; void *
0x1800cafd2  test    rdx, rdx
0x1800cafd5  jz      short loc_1800CAFDF
0x1800cafd7  mov     rcx, rdi; this
0x1800cafda  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800cafdf  test    ebx, ebx
0x1800cafe1  js      short loc_1800CAFED
0x1800cafe3  cmp     [rbp+47h+arg_8], r13d
0x1800cafe7  mov     ebx, r13d
0x1800cafea  setbe   bl
0x1800cafed  mov     eax, ebx
0x1800cafef  jmp     short loc_1800CAFF6
0x1800caff1  mov     eax, 80070057h
0x1800caff6  mov     rbx, [rsp+0D0h+arg_0]
0x1800caffe  add     rsp, 0A0h
0x1800cb005  pop     r15
0x1800cb007  pop     r14
0x1800cb009  pop     r13
0x1800cb00b  pop     r12
0x1800cb00d  pop     rdi
  ... truncated ...
```
