# CImage::_WimExtractCallback(ulong,unsigned __int64,__int64,void *)

- ea: `0x18000d300`
- end: `0x18000d5a7`
- name: `?_WimExtractCallback@CImage@@SAKK_K_JPEAX@Z`
- size: `679`
- prototype: `static unsigned int(unsigned int, unsigned __int64, __int64, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800073c0`
- `0x1800092a4`
- `0x18000a688`
- `0x18000d300`
- `0x18000d6b0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000d485`
- `msvcrt!_wcsnicmp` at `0x18000d4b3`
- `msvcrt!_wcsnicmp` at `0x18000d485`
- `msvcrt!_wcsnicmp` at `0x18000d4b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d431`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d572`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d431`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d572`
- `KERNEL32!EnterCriticalSection` at `0x18000d355`
- `KERNEL32!EnterCriticalSection` at `0x18000d355`
- `KERNEL32!LeaveCriticalSection` at `0x18000d586`
- `KERNEL32!LeaveCriticalSection` at `0x18000d586`
- `WdsCommonLib!?WdsDebugOut@@YAXPEBGZZ` at `0x18000d501`
- `WdsCommonLib!?WdsDebugOut@@YAXPEBGZZ` at `0x18000d501`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000d3d6`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000d3d6`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000d514`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000d514`

## pseudocode

```c
__int64 __fastcall CImage::_WimExtractCallback(int a1, const wchar_t *a2, _DWORD *a3, __int64 *a4)
{
  __int64 v4; // rdi
  _DWORD *v5; // r13
  unsigned int v6; // r14d
  wchar_t *v7; // rsi
  size_t v11; // r15
  _QWORD *v12; // rdx
  unsigned int v13; // r13d
  unsigned int v14; // eax
  unsigned __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r8
  _DWORD *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v25; // [rsp+20h] [rbp-28h]
  __int64 v26; // [rsp+28h] [rbp-20h]
  _DWORD *v27; // [rsp+30h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-10h]
  unsigned int v30; // [rsp+98h] [rbp+50h] BYREF
  _DWORD *v31; // [rsp+A0h] [rbp+58h]
  unsigned __int16 *v32; // [rsp+A8h] [rbp+60h] BYREF

  v31 = a3;
  v4 = a4[1];
  v5 = (_DWORD *)a4[3];
  v6 = 0;
  v7 = 0;
  v32 = 0;
  v30 = 0;
  v25 = *a4;
  v26 = v4;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)a4[2];
  v27 = v5;
  EnterCriticalSection(lpCriticalSection);
  if ( a1 != 38009 )
  {
    if ( a1 == 38015 )
    {
      if ( (unsigned int)CDynArray<unsigned short *,CDeallocateNone>::FindString(v4, a2, &v30) )
        CDynArray<unsigned short *,CDeallocateNone>::ClearItem(v4, v30);
      goto LABEL_38;
    }
    if ( a1 != 38022 )
      goto LABEL_38;
  }
  *a3 = 0;
  if ( *v5 )
    goto LABEL_37;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = (_QWORD *)v25;
  v13 = 0;
  v14 = *(_DWORD *)(v25 + 12);
  if ( v14 )
  {
    while ( 1 )
    {
      v30 = 0;
      if ( v13 < v14 )
        v7 = *(wchar_t **)(*v12 + 8LL * v13);
      v15 = -1;
      do
        ++v15;
      while ( v7[v15] );
      v16 = (unsigned int)WdsIdnCompareFilePaths(a2, v7, &v30);
      if ( (unsigned int)ElValidateWin32_4(v16, v17, v18, 3385) )
      {
LABEL_35:
        if ( (_DWORD)v16 )
        {
          *v27 = v16;
LABEL_37:
          v6 = -1;
        }
        break;
      }
      if ( v30 )
      {
        if ( v15 > v11 && v7[v11] == 92 && !_wcsnicmp(a2, v7, v11)
          || v15 && v7[v15 - 1] == 42 && v11 >= v15 && !_wcsnicmp(a2, v7, v15 - 1) )
        {
          v19 = v31;
          *v31 = 1;
        }
        else
        {
          v19 = v31;
        }
        if ( a1 != 38009 )
          goto LABEL_30;
      }
      else
      {
        v19 = v31;
        *v31 = 1;
        if ( a1 != 38009 )
          goto LABEL_30;
        CDynArray<unsigned short *,CDeallocateNone>::ClearItem(v25, v13);
        if ( v7 )
        {
          operator delete(v7);
          v7 = 0;
        }
      }
      if ( *v19 )
      {
        WdsDebugOut(L" Extracting %s...\n", a2);
        LODWORD(v16) = DuplicateStringW(a2, &v32);
        if ( !(unsigned int)ElValidateWin32_4((unsigned int)v16, v20, v21, 3436) )
        {
          LODWORD(v16) = CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(v26, v32);
          if ( !(unsigned int)ElValidateWin32_4((unsigned int)v16, v22, v23, 3439) )
            v32 = 0;
        }
        goto LABEL_35;
      }
LABEL_30:
      v12 = (_QWORD *)v25;
      ++v13;
      v14 = *(_DWORD *)(v25 + 12);
      if ( v13 >= v14 )
        goto LABEL_35;
    }
  }
LABEL_38:
  if ( v32 )
  {
    operator delete(v32);
    v32 = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v6;
}

```

## disassembly

```asm
0x18000d300  mov     [rsp-40h+arg_10], r8
0x18000d305  mov     [rsp-40h+arg_0], ecx
0x18000d309  push    rbp
0x18000d30a  push    rbx
0x18000d30b  push    rsi
0x18000d30c  push    rdi
0x18000d30d  push    r12
0x18000d30f  push    r13
0x18000d311  push    r14
0x18000d313  push    r15
0x18000d315  mov     rbp, rsp
0x18000d318  sub     rsp, 48h
0x18000d31c  mov     rdi, [r9+8]
0x18000d320  xor     eax, eax
0x18000d322  mov     r13, [r9+18h]
0x18000d326  mov     r14d, eax
0x18000d329  mov     esi, eax
0x18000d32b  mov     [rbp+arg_18], rax
0x18000d32f  mov     [rbp+arg_8], eax
0x18000d332  mov     r15d, ecx
0x18000d335  mov     rax, [r9]
0x18000d338  mov     rbx, r8
0x18000d33b  mov     [rbp+var_28], rax
0x18000d33f  mov     r12, rdx
0x18000d342  mov     rax, [r9+10h]
0x18000d346  mov     rcx, rax; lpCriticalSection
0x18000d349  mov     [rbp+var_20], rdi
0x18000d34d  mov     [rbp+lpCriticalSection], rax
0x18000d351  mov     [rbp+var_18], r13
0x18000d355  call    cs:__imp_EnterCriticalSection
0x18000d35c  nop     dword ptr [rax+rax+00h]
0x18000d361  mov     eax, r15d
0x18000d364  sub     eax, 9479h
0x18000d369  jz      short loc_18000D37D
0x18000d36b  sub     eax, 6
0x18000d36e  jz      loc_18000D446
0x18000d374  cmp     eax, 7
0x18000d377  jnz     loc_18000D567
0x18000d37d  xor     ecx, ecx
0x18000d37f  mov     [rbx], ecx
0x18000d381  cmp     [r13+0], ecx
0x18000d385  jnz     loc_18000D563
0x18000d38b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000d38f  inc     r15
0x18000d392  cmp     [r12+r15*2], cx
0x18000d397  jnz     short loc_18000D38F
0x18000d399  mov     rdx, [rbp+var_28]
0x18000d39d  mov     r13d, ecx
0x18000d3a0  mov     eax, [rdx+0Ch]
0x18000d3a3  test    eax, eax
0x18000d3a5  jz      loc_18000D567
0x18000d3ab  mov     [rbp+arg_8], ecx
0x18000d3ae  cmp     r13d, eax
0x18000d3b1  jnb     short loc_18000D3BF
0x18000d3b3  mov     rax, [rdx]
0x18000d3b6  mov     ecx, r13d
0x18000d3b9  mov     rsi, [rax+rcx*8]
0x18000d3bd  xor     ecx, ecx
0x18000d3bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d3c3  inc     rbx
0x18000d3c6  cmp     [rsi+rbx*2], cx
0x18000d3ca  jnz     short loc_18000D3C3
0x18000d3cc  lea     r8, [rbp+arg_8]
0x18000d3d0  mov     rdx, rsi
0x18000d3d3  mov     rcx, r12
0x18000d3d6  call    cs:__imp_WdsIdnCompareFilePaths
0x18000d3dd  nop     dword ptr [rax+rax+00h]
0x18000d3e2  mov     ecx, eax
0x18000d3e4  mov     r9d, 0D39h
0x18000d3ea  mov     edi, eax
0x18000d3ec  call    ElValidateWin32_4
0x18000d3f1  xor     ecx, ecx
0x18000d3f3  test    eax, eax
0x18000d3f5  jnz     loc_18000D559
0x18000d3fb  cmp     [rbp+arg_8], ecx
0x18000d3fe  jnz     short loc_18000D46F
0x18000d400  cmp     [rbp+arg_0], 9479h
0x18000d407  mov     rbx, [rbp+arg_10]
0x18000d40b  mov     dword ptr [rbx], 1
0x18000d411  jnz     loc_18000D4E2
0x18000d417  mov     rcx, [rbp+var_28]
0x18000d41b  mov     edx, r13d
0x18000d41e  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateNone>::ClearItem(ulong)
0x18000d423  xor     ecx, ecx
0x18000d425  test    rsi, rsi
0x18000d428  jz      loc_18000D4DE
0x18000d42e  mov     rcx, rsi
0x18000d431  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d438  nop     dword ptr [rax+rax+00h]
0x18000d43d  xor     ecx, ecx
0x18000d43f  mov     esi, ecx
0x18000d441  jmp     loc_18000D4DE
0x18000d446  lea     r8, [rbp+arg_8]
0x18000d44a  mov     rdx, r12
0x18000d44d  mov     rcx, rdi
0x18000d450  call    ?FindString@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAHPEBGPEAK@Z; CDynArray<ushort *,CDeallocateNone>::FindString(ushort const *,ulong *)
0x18000d455  xor     ebx, ebx
0x18000d457  test    eax, eax
0x18000d459  jz      loc_18000D569
0x18000d45f  mov     edx, [rbp+arg_8]
0x18000d462  mov     rcx, rdi
0x18000d465  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateNone>::ClearItem(ulong)
0x18000d46a  jmp     loc_18000D569
0x18000d46f  cmp     rbx, r15
0x18000d472  jbe     short loc_18000D497
0x18000d474  cmp     word ptr [rsi+r15*2], 5Ch ; '\'
0x18000d47a  jnz     short loc_18000D497
0x18000d47c  mov     r8, r15; MaxCount
0x18000d47f  mov     rdx, rsi; String2
0x18000d482  mov     rcx, r12; String1
0x18000d485  call    cs:__imp__wcsnicmp
0x18000d48c  nop     dword ptr [rax+rax+00h]
0x18000d491  xor     ecx, ecx
0x18000d493  test    eax, eax
0x18000d495  jz      short loc_18000D4C5
0x18000d497  test    rbx, rbx
0x18000d49a  jz      short loc_18000D4D1
0x18000d49c  cmp     word ptr [rsi+rbx*2-2], 2Ah ; '*'
0x18000d4a2  jnz     short loc_18000D4D1
0x18000d4a4  cmp     r15, rbx
0x18000d4a7  jb      short loc_18000D4D1
0x18000d4a9  lea     r8, [rbx-1]; MaxCount
0x18000d4ad  mov     rdx, rsi; String2
0x18000d4b0  mov     rcx, r12; String1
0x18000d4b3  call    cs:__imp__wcsnicmp
0x18000d4ba  nop     dword ptr [rax+rax+00h]
0x18000d4bf  xor     ecx, ecx
0x18000d4c1  test    eax, eax
0x18000d4c3  jnz     short loc_18000D4D1
0x18000d4c5  mov     rbx, [rbp+arg_10]
0x18000d4c9  mov     dword ptr [rbx], 1
0x18000d4cf  jmp     short loc_18000D4D5
0x18000d4d1  mov     rbx, [rbp+arg_10]
0x18000d4d5  cmp     [rbp+arg_0], 9479h
0x18000d4dc  jnz     short loc_18000D4E2
0x18000d4de  cmp     [rbx], ecx
0x18000d4e0  jnz     short loc_18000D4F7
0x18000d4e2  mov     rdx, [rbp+var_28]
0x18000d4e6  inc     r13d
0x18000d4e9  mov     eax, [rdx+0Ch]
0x18000d4ec  cmp     r13d, eax
0x18000d4ef  jb      loc_18000D3AB
0x18000d4f5  jmp     short loc_18000D559
0x18000d4f7  mov     rdx, r12
0x18000d4fa  lea     rcx, aExtractingS; " Extracting %s...\n"
0x18000d501  call    cs:__imp_?WdsDebugOut@@YAXPEBGZZ; WdsDebugOut(ushort const *,...)
0x18000d508  nop     dword ptr [rax+rax+00h]
0x18000d50d  lea     rdx, [rbp+arg_18]
0x18000d511  mov     rcx, r12
0x18000d514  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x18000d51b  nop     dword ptr [rax+rax+00h]
0x18000d520  mov     ecx, eax
0x18000d522  mov     r9d, 0D6Ch
0x18000d528  mov     edi, eax
0x18000d52a  call    ElValidateWin32_4
0x18000d52f  test    eax, eax
0x18000d531  jnz     short loc_18000D559
0x18000d533  mov     rdx, [rbp+arg_18]
0x18000d537  mov     rcx, [rbp+var_20]
0x18000d53b  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x18000d540  mov     r9d, 0D6Fh
0x18000d546  mov     ecx, eax
0x18000d548  mov     edi, eax
0x18000d54a  call    ElValidateWin32_4
0x18000d54f  xor     ecx, ecx
0x18000d551  test    eax, eax
0x18000d553  jnz     short loc_18000D559
0x18000d555  mov     [rbp+arg_18], rcx
0x18000d559  test    edi, edi
0x18000d55b  jz      short loc_18000D567
0x18000d55d  mov     rax, [rbp+var_18]
0x18000d561  mov     [rax], edi
0x18000d563  or      r14d, 0FFFFFFFFh
0x18000d567  xor     ebx, ebx
0x18000d569  mov     rcx, [rbp+arg_18]
0x18000d56d  test    rcx, rcx
0x18000d570  jz      short loc_18000D582
0x18000d572  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d579  nop     dword ptr [rax+rax+00h]
0x18000d57e  mov     [rbp+arg_18], rbx
0x18000d582  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18000d586  call    cs:__imp_LeaveCriticalSection
0x18000d58d  nop     dword ptr [rax+rax+00h]
0x18000d592  mov     eax, r14d
0x18000d595  add     rsp, 48h
0x18000d599  pop     r15
0x18000d59b  pop     r14
0x18000d59d  pop     r13
0x18000d59f  pop     r12
0x18000d5a1  pop     rdi
0x18000d5a2  pop     rsi
0x18000d5a3  pop     rbx
0x18000d5a4  pop     rbp
0x18000d5a5  retn
```
