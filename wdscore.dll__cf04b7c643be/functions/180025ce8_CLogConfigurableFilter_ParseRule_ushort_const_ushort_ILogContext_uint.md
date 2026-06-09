# CLogConfigurableFilter::ParseRule(ushort const *,ushort *,ILogContext *,uint)

- ea: `0x180025ce8`
- end: `0x18002608b`
- name: `?ParseRule@CLogConfigurableFilter@@IEAAHPEBGPEAGPEAVILogContext@@I@Z`
- size: `931`
- prototype: `int(CLogConfigurableFilter *__hidden this, const unsigned __int16 *, unsigned __int16 *, struct ILogContext *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026110`

## callees

- `0x18001fe2c`
- `0x180025630`
- `0x1800258fc`
- `0x1800259d8`
- `0x180025ce8`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180025e8f`
- `msvcrt!wcstok_s` at `0x180025f62`
- `msvcrt!wcstok_s` at `0x180025e8f`
- `msvcrt!wcstok_s` at `0x180025f62`
- `msvcrt!swscanf_s` at `0x180025eea`
- `msvcrt!swscanf_s` at `0x180025eea`
- `msvcrt!_wcsicmp` at `0x180025d3e`
- `msvcrt!_wcsicmp` at `0x180025d60`
- `msvcrt!_wcsicmp` at `0x180025d9b`
- `msvcrt!_wcsicmp` at `0x180025d3e`
- `msvcrt!_wcsicmp` at `0x180025d60`
- `msvcrt!_wcsicmp` at `0x180025d9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025de4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025de4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e0c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002601e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026043`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026068`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029725`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002974f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029779`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002601e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026043`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026068`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029725`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002974f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025dd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025df8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002600a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002602f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026054`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029711`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002973b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025dd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025df8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002600a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002602f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180026054`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029711`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002973b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029765`

## pseudocode

```c
__int64 __fastcall CLogConfigurableFilter::ParseRule(
        CLogConfigurableFilter *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct ILogContext *a4,
        unsigned int a5)
{
  unsigned int v6; // r14d
  struct tagLOG_FILTER_RULE *v7; // rdi
  int v8; // esi
  unsigned __int16 *v9; // r13
  unsigned __int16 *v10; // r15
  unsigned __int16 *v11; // r12
  unsigned __int64 v12; // rcx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  struct tagLOG_FILTER_RULE *Rule; // rax
  wchar_t *i; // rcx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int j; // edx
  unsigned int v24; // r8d
  unsigned int v25; // edx
  unsigned int k; // ebx
  bool v27; // zf
  HANDLE v28; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  struct ILogContext *v32; // [rsp+28h] [rbp-90h]
  __int64 v33; // [rsp+38h] [rbp-80h]
  wchar_t *Context; // [rsp+50h] [rbp-68h] BYREF
  struct tagLOG_FILTER_RULE *v35; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v36; // [rsp+60h] [rbp-58h]
  unsigned __int16 *v37; // [rsp+68h] [rbp-50h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-48h]

  v6 = 0;
  v7 = 0;
  v35 = 0;
  v8 = 0;
  v9 = 0;
  v36 = 0;
  v10 = 0;
  v37 = 0;
  v11 = 0;
  v38 = 0;
  Context = 0;
  if ( _wcsicmp(a2, L"LOG") )
  {
    if ( _wcsicmp(a2, L"SUPPRESS") )
    {
      v13 = 0;
      goto LABEL_7;
    }
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  v13 = 1;
LABEL_7:
  if ( v13 )
  {
    if ( !_wcsicmp(a3, L"default") )
    {
      *((_DWORD *)this + 10) = v8;
LABEL_40:
      v6 = 1;
      goto LABEL_41;
    }
    if ( a5 <= 0x7FFFFFFF )
    {
      ProcessHeap = GetProcessHeap();
      v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * a5);
      v36 = v9;
      v15 = GetProcessHeap();
      v10 = (unsigned __int16 *)HeapAlloc(v15, 0, 2 * a5);
      v37 = v10;
      v16 = GetProcessHeap();
      v17 = (unsigned __int16 *)HeapAlloc(v16, 0, 2 * a5);
      v11 = v17;
      v38 = v17;
      if ( v9 )
      {
        if ( v10 )
        {
          if ( v17 )
          {
            Rule = CLogConfigurableFilter::CreateRule((CLogConfigurableFilter *)v12);
            v7 = Rule;
            v35 = Rule;
            if ( Rule )
            {
              *(_DWORD *)Rule = v8;
              for ( i = wcstok_s(a3, L",", &Context); i; i = wcstok_s(0, L",", &Context) )
              {
                *v11 = 0;
                *v10 = 0;
                *v9 = 0;
                LODWORD(v33) = a5;
                LODWORD(v32) = a5;
                v20 = swscanf_s(i, L"%s %s \"%[^\"]\"", v9, a5, v10, v32, v11, v33);
                if ( v20 != 3 )
                {
                  if ( v20 != 2 )
                    goto LABEL_41;
                  v21 = -1;
                  do
                    ++v21;
                  while ( v9[v21] );
                  if ( !v21 )
                    goto LABEL_41;
                  v22 = -1;
                  do
                    ++v22;
                  while ( v10[v22] );
                  if ( !v22 )
                    goto LABEL_41;
                }
                if ( !CLogConfigurableFilter::AddClause((CLogConfigurableFilter *)v12, v7, v9, v10, v11, a4) )
                  goto LABEL_41;
              }
              for ( j = 0; ; ++j )
              {
                v24 = *((_DWORD *)this + 4);
                if ( j >= v24 )
                  break;
                v12 = j;
                if ( *(struct tagLOG_FILTER_RULE **)(*((_QWORD *)this + 1) + 8LL * j) == v7 )
                  goto LABEL_40;
              }
              v25 = 0;
              for ( k = 0; ; ++k )
              {
                v27 = k == v24;
                if ( k >= v24 )
                  break;
                if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * k) )
                {
                  v25 = k;
                  v27 = k == v24;
                  break;
                }
              }
              if ( !v27 )
                goto LABEL_39;
              if ( (unsigned int)CPtrList<tagLOG_OUTPUT_STACK *>::SetSize((char *)this + 8, v24 + 1) )
              {
                v25 = k;
LABEL_39:
                v12 = v25;
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * v25) = v7;
                goto LABEL_40;
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( !v6 && v7 )
    CLogConfigurableFilter::DestroyRule((CLogConfigurableFilter *)v12, v7);
  if ( v9 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v9);
  }
  if ( v10 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v10);
  }
  if ( v11 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x180025ce8  mov     rax, rsp
0x180025ceb  mov     [rax+20h], r9
0x180025cef  mov     [rax+18h], r8
0x180025cf3  mov     [rax+8], rcx
0x180025cf7  push    rbx
0x180025cf8  push    rsi
0x180025cf9  push    rdi
0x180025cfa  push    r12
0x180025cfc  push    r13
0x180025cfe  push    r14
0x180025d00  push    r15
0x180025d02  sub     rsp, 80h
0x180025d09  mov     rbx, rdx
0x180025d0c  xor     r14d, r14d
0x180025d0f  mov     [rax-74h], r14d
0x180025d13  xor     edi, edi
0x180025d15  mov     [rax-60h], rdi
0x180025d19  xor     esi, esi
0x180025d1b  xor     r13d, r13d
0x180025d1e  mov     [rax-58h], r13
0x180025d22  xor     r15d, r15d
0x180025d25  mov     [rax-50h], r15
0x180025d29  xor     r12d, r12d
0x180025d2c  mov     [rax-48h], r12
0x180025d30  mov     [rax-68h], rsi
0x180025d34  lea     rdx, aLog; "LOG"
0x180025d3b  mov     rcx, rbx; String1
0x180025d3e  call    cs:__imp__wcsicmp
0x180025d45  nop     dword ptr [rax+rax+00h]
0x180025d4a  xor     r9d, r9d
0x180025d4d  test    eax, eax
0x180025d4f  jnz     short loc_180025D56
0x180025d51  mov     esi, r9d
0x180025d54  jmp     short loc_180025D76
0x180025d56  lea     rdx, aSuppress; "SUPPRESS"
0x180025d5d  mov     rcx, rbx; String1
0x180025d60  call    cs:__imp__wcsicmp
0x180025d67  nop     dword ptr [rax+rax+00h]
0x180025d6c  xor     r9d, r9d
0x180025d6f  test    eax, eax
0x180025d71  jnz     short loc_180025D81
0x180025d73  lea     esi, [rax+1]
0x180025d76  mov     [rsp+0B8h+var_70], esi
0x180025d7a  mov     eax, 1
0x180025d7f  jmp     short loc_180025D84
0x180025d81  mov     eax, r9d
0x180025d84  test    eax, eax
0x180025d86  jz      loc_180025FF3
0x180025d8c  lea     rdx, aDefault; "default"
0x180025d93  mov     rcx, [rsp+0B8h+String1]; String1
0x180025d9b  call    cs:__imp__wcsicmp
0x180025da2  nop     dword ptr [rax+rax+00h]
0x180025da7  test    eax, eax
0x180025da9  jnz     short loc_180025DBB
0x180025dab  mov     rax, [rsp+0B8h+arg_0]
0x180025db3  mov     [rax+28h], esi
0x180025db6  jmp     loc_180025FE8
0x180025dbb  mov     eax, [rsp+0B8h+arg_20]
0x180025dc2  cmp     eax, 7FFFFFFFh
0x180025dc7  ja      loc_180025FF3
0x180025dcd  lea     ebx, [rax+rax]
0x180025dd0  call    cs:__imp_GetProcessHeap
0x180025dd7  nop     dword ptr [rax+rax+00h]
0x180025ddc  mov     rcx, rax; hHeap
0x180025ddf  mov     r8d, ebx; dwBytes
0x180025de2  xor     edx, edx; dwFlags
0x180025de4  call    cs:__imp_HeapAlloc
0x180025deb  nop     dword ptr [rax+rax+00h]
0x180025df0  mov     r13, rax
0x180025df3  mov     [rsp+0B8h+var_58], rax
0x180025df8  call    cs:__imp_GetProcessHeap
0x180025dff  nop     dword ptr [rax+rax+00h]
0x180025e04  mov     rcx, rax; hHeap
0x180025e07  mov     r8d, ebx; dwBytes
0x180025e0a  xor     edx, edx; dwFlags
0x180025e0c  call    cs:__imp_HeapAlloc
0x180025e13  nop     dword ptr [rax+rax+00h]
0x180025e18  mov     r15, rax
0x180025e1b  mov     [rsp+0B8h+var_50], rax
0x180025e20  call    cs:__imp_GetProcessHeap
0x180025e27  nop     dword ptr [rax+rax+00h]
0x180025e2c  mov     rcx, rax; hHeap
0x180025e2f  mov     r8d, ebx; dwBytes
0x180025e32  xor     edx, edx; dwFlags
0x180025e34  call    cs:__imp_HeapAlloc
0x180025e3b  nop     dword ptr [rax+rax+00h]
0x180025e40  mov     r12, rax
0x180025e43  mov     [rsp+0B8h+var_48], rax
0x180025e48  test    r13, r13
0x180025e4b  jz      loc_180025FF3
0x180025e51  test    r15, r15
0x180025e54  jz      loc_180025FF3
0x180025e5a  test    rax, rax
0x180025e5d  jz      loc_180025FF3
0x180025e63  call    ?CreateRule@CLogConfigurableFilter@@IEAAPEAUtagLOG_FILTER_RULE@@XZ; CLogConfigurableFilter::CreateRule(void)
0x180025e68  mov     rdi, rax
0x180025e6b  mov     [rsp+0B8h+var_60], rax
0x180025e70  test    rax, rax
0x180025e73  jz      loc_180025FF3
0x180025e79  mov     [rax], esi
0x180025e7b  lea     r8, [rsp+0B8h+Context]; Context
0x180025e80  lea     rdx, Delimiter; ","
0x180025e87  mov     rcx, [rsp+0B8h+String1]; String
0x180025e8f  call    cs:__imp_wcstok_s
0x180025e96  nop     dword ptr [rax+rax+00h]
0x180025e9b  mov     rcx, rax; Buffer
0x180025e9e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025ea2  mov     rbx, [rsp+0B8h+arg_18]
0x180025eaa  xor     r9d, r9d
0x180025ead  test    rcx, rcx
0x180025eb0  jz      loc_180025F76
0x180025eb6  mov     [r12], r9w
0x180025ebb  mov     [r15], r9w
0x180025ebf  mov     [r13+0], r9w
0x180025ec4  mov     eax, [rsp+0B8h+arg_20]
0x180025ecb  mov     dword ptr [rsp+0B8h+var_80], eax
0x180025ecf  mov     [rsp+0B8h+var_88], r12
0x180025ed4  mov     dword ptr [rsp+0B8h+var_90], eax
0x180025ed8  mov     [rsp+0B8h+var_98], r15
0x180025edd  mov     r9d, eax
0x180025ee0  mov     r8, r13
0x180025ee3  lea     rdx, aSS_0; "%s %s \"%[^\"]\""
0x180025eea  call    cs:__imp_swscanf_s
0x180025ef1  nop     dword ptr [rax+rax+00h]
0x180025ef6  cmp     eax, 3
0x180025ef9  jz      short loc_180025F34
0x180025efb  cmp     eax, 2
0x180025efe  jnz     loc_180025FF3
0x180025f04  mov     rax, rsi
0x180025f07  xor     r9d, r9d
0x180025f0a  inc     rax
0x180025f0d  cmp     [r13+rax*2+0], r9w
0x180025f13  jnz     short loc_180025F0A
0x180025f15  test    rax, rax
0x180025f18  jz      loc_180025FF3
0x180025f1e  mov     rax, rsi
0x180025f21  inc     rax
0x180025f24  cmp     [r15+rax*2], r9w
0x180025f29  jnz     short loc_180025F21
0x180025f2b  test    rax, rax
0x180025f2e  jz      loc_180025FF3
0x180025f34  mov     [rsp+0B8h+var_90], rbx; struct ILogContext *
0x180025f39  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x180025f3e  mov     r9, r15; unsigned __int16 *
0x180025f41  mov     r8, r13; unsigned __int16 *
0x180025f44  mov     rdx, rdi; struct tagLOG_FILTER_RULE *
0x180025f47  call    ?AddClause@CLogConfigurableFilter@@IEAAHPEAUtagLOG_FILTER_RULE@@PEBG11PEAVILogContext@@@Z; CLogConfigurableFilter::AddClause(tagLOG_FILTER_RULE *,ushort const *,ushort const *,ushort const *,ILogContext *)
0x180025f4c  test    eax, eax
0x180025f4e  jz      loc_180025FF3
0x180025f54  lea     r8, [rsp+0B8h+Context]; Context
0x180025f59  lea     rdx, Delimiter; ","
0x180025f60  xor     ecx, ecx; String
0x180025f62  call    cs:__imp_wcstok_s
0x180025f69  nop     dword ptr [rax+rax+00h]
0x180025f6e  mov     rcx, rax
0x180025f71  jmp     loc_180025EAA
0x180025f76  mov     rsi, [rsp+0B8h+arg_0]
0x180025f7e  mov     [rsp+0B8h+var_78], r9d
0x180025f83  mov     edx, r9d
0x180025f86  mov     [rsp+0B8h+var_78], edx
0x180025f8a  mov     r8d, [rsi+10h]
0x180025f8e  cmp     edx, r8d
0x180025f91  jnb     short loc_180025FA3
0x180025f93  mov     ecx, edx
0x180025f95  mov     rax, [rsi+8]
0x180025f99  cmp     [rax+rcx*8], rdi
0x180025f9d  jz      short loc_180025FE8
0x180025f9f  inc     edx
0x180025fa1  jmp     short loc_180025F86
0x180025fa3  mov     edx, r9d
0x180025fa6  mov     ebx, r9d
0x180025fa9  mov     [rsp+0B8h+var_78], ebx
0x180025fad  cmp     ebx, r8d
0x180025fb0  jnb     short loc_180025FC9
0x180025fb2  mov     ecx, ebx
0x180025fb4  mov     rax, [rsi+8]
0x180025fb8  cmp     [rax+rcx*8], r9
0x180025fbc  jnz     short loc_180025FC2
0x180025fbe  mov     edx, ebx
0x180025fc0  jmp     short loc_180025FC6
0x180025fc2  inc     ebx
0x180025fc4  jmp     short loc_180025FA9
0x180025fc6  cmp     ebx, r8d
0x180025fc9  jnz     short loc_180025FDE
0x180025fcb  lea     edx, [r8+1]
0x180025fcf  lea     rcx, [rsi+8]
0x180025fd3  call    ?SetSize@?$CPtrList@PEAUtagLOG_OUTPUT_STACK@@@@QEAAHI@Z; CPtrList<tagLOG_OUTPUT_STACK *>::SetSize(uint)
0x180025fd8  test    eax, eax
0x180025fda  jz      short loc_180025FF3
0x180025fdc  mov     edx, ebx
0x180025fde  mov     ecx, edx; this
0x180025fe0  mov     rax, [rsi+8]
0x180025fe4  mov     [rax+rcx*8], rdi
0x180025fe8  mov     r14d, 1
0x180025fee  mov     [rsp+0B8h+var_74], r14d
0x180025ff3  test    r14d, r14d
0x180025ff6  jnz     short loc_180026005
0x180025ff8  test    rdi, rdi
0x180025ffb  jz      short loc_180026005
0x180025ffd  mov     rdx, rdi; struct tagLOG_FILTER_RULE *
0x180026000  call    ?DestroyRule@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_RULE@@@Z; CLogConfigurableFilter::DestroyRule(tagLOG_FILTER_RULE *)
0x180026005  test    r13, r13
0x180026008  jz      short loc_18002602A
0x18002600a  call    cs:__imp_GetProcessHeap
0x180026011  nop     dword ptr [rax+rax+00h]
0x180026016  mov     rcx, rax; hHeap
0x180026019  mov     r8, r13; lpMem
0x18002601c  xor     edx, edx; dwFlags
0x18002601e  call    cs:__imp_HeapFree
0x180026025  nop     dword ptr [rax+rax+00h]
0x18002602a  test    r15, r15
0x18002602d  jz      short loc_18002604F
0x18002602f  call    cs:__imp_GetProcessHeap
0x180026036  nop     dword ptr [rax+rax+00h]
0x18002603b  mov     rcx, rax; hHeap
0x18002603e  mov     r8, r15; lpMem
0x180026041  xor     edx, edx; dwFlags
0x180026043  call    cs:__imp_HeapFree
0x18002604a  nop     dword ptr [rax+rax+00h]
0x18002604f  test    r12, r12
0x180026052  jz      short loc_180026074
0x180026054  call    cs:__imp_GetProcessHeap
0x18002605b  nop     dword ptr [rax+rax+00h]
0x180026060  mov     rcx, rax; hHeap
0x180026063  mov     r8, r12; lpMem
0x180026066  xor     edx, edx; dwFlags
0x180026068  call    cs:__imp_HeapFree
0x18002606f  nop     dword ptr [rax+rax+00h]
0x180026074  mov     eax, r14d
0x180026077  add     rsp, 80h
0x18002607e  pop     r15
0x180026080  pop     r14
0x180026082  pop     r13
0x180026084  pop     r12
0x180026086  pop     rdi
0x180026087  pop     rsi
0x180026088  pop     rbx
0x180026089  retn
0x1800296e9  push    rbx
0x1800296eb  push    rbp
0x1800296ec  sub     rsp, 48h
0x1800296f0  mov     rbp, rdx
0x1800296f3  cmp     dword ptr [rbp+44h], 0
0x1800296f7  jnz     short loc_180029708
0x1800296f9  mov     rdx, [rbp+58h]; struct tagLOG_FILTER_RULE *
0x1800296fd  test    rdx, rdx
0x180029700  jz      short loc_180029708
0x180029702  call    ?DestroyRule@CLogConfigurableFilter@@IEAAXPEAUtagLOG_FILTER_RULE@@@Z; CLogConfigurableFilter::DestroyRule(tagLOG_FILTER_RULE *)
0x180029707  nop
0x180029708  mov     rbx, [rbp+60h]
0x18002970c  test    rbx, rbx
0x18002970f  jz      short loc_180029732
0x180029711  call    cs:__imp_GetProcessHeap
0x180029718  nop     dword ptr [rax+rax+00h]
0x18002971d  mov     rcx, rax; hHeap
0x180029720  mov     r8, rbx; lpMem
0x180029723  xor     edx, edx; dwFlags
0x180029725  call    cs:__imp_HeapFree
0x18002972c  nop     dword ptr [rax+rax+00h]
0x180029731  nop
0x180029732  mov     rbx, [rbp+68h]
0x180029736  test    rbx, rbx
0x180029739  jz      short loc_18002975C
0x18002973b  call    cs:__imp_GetProcessHeap
0x180029742  nop     dword ptr [rax+rax+00h]
0x180029747  mov     rcx, rax; hHeap
0x18002974a  mov     r8, rbx; lpMem
0x18002974d  xor     edx, edx; dwFlags
0x18002974f  call    cs:__imp_HeapFree
0x180029756  nop     dword ptr [rax+rax+00h]
0x18002975b  nop
0x18002975c  mov     rbx, [rbp+70h]
0x180029760  test    rbx, rbx
0x180029763  jz      short loc_180029786
0x180029765  call    cs:__imp_GetProcessHeap
0x18002976c  nop     dword ptr [rax+rax+00h]
0x180029771  mov     rcx, rax; hHeap
0x180029774  mov     r8, rbx; lpMem
0x180029777  xor     edx, edx; dwFlags
0x180029779  call    cs:__imp_HeapFree
0x180029780  nop     dword ptr [rax+rax+00h]
0x180029785  nop
0x180029786  add     rsp, 48h
0x18002978a  pop     rbp
0x18002978b  pop     rbx
0x18002978c  retn
```
