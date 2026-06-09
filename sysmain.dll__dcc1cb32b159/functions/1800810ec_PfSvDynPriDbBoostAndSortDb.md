# PfSvDynPriDbBoostAndSortDb

- ea: `0x1800810ec`
- end: `0x180081438`
- name: `PfSvDynPriDbBoostAndSortDb`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003623c`

## callees

- `0x180008244`
- `0x180028550`
- `0x18003a2ac`
- `0x180048988`
- `0x1800586e4`
- `0x1800810ec`
- `0x1800b644e`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!qsort` at `0x180081404`
- `msvcrt!qsort` at `0x180081404`
- `ntdll!RtlReleaseSRWLockShared` at `0x180081378`
- `ntdll!RtlReleaseSRWLockShared` at `0x180081378`
- `ntdll!RtlAcquireSRWLockShared` at `0x180081328`
- `ntdll!RtlAcquireSRWLockShared` at `0x180081328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008124e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008124e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800811d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800811d3`

## string_xrefs

- `0x180081124`: `MSHTML.DLL`
- `0x180081138`: `JSCRIPT9.DLL`
- `0x18008114d`: `WINDOWS.UI.DLL`
- `0x18008115e`: `WINDOWS.UI.XAML.DLL`
- `0x180081169`: `CLR.DLL`
- `0x180081174`: `MSCORLIB.NI.DLL`
- `0x18008117f`: `SYSTEM.NI.DLL`

## pseudocode

```c
__int64 __fastcall PfSvDynPriDbBoostAndSortDb(unsigned __int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned __int64 v4; // rax
  unsigned int WindowsDir; // ebx
  void *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r13
  __int64 i; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // r12d
  __int64 v14; // rsi
  int v15; // ebx
  char j; // al
  __int64 v17; // r15
  unsigned int k; // r14d
  BOOL v19; // r13d
  __int64 v20; // rcx
  __int64 v21; // rdx
  bool v22; // zf
  __int64 v23; // rax
  __int64 v24; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v25; // [rsp+28h] [rbp-D8h]
  __int64 v26; // [rsp+30h] [rbp-D0h]
  void *Buf1; // [rsp+50h] [rbp-B0h]
  _QWORD v30[8]; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+98h] [rbp-68h]
  int v32; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  int v35; // [rsp+ACh] [rbp-54h]
  const wchar_t *v36; // [rsp+B0h] [rbp-50h]
  int v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+BCh] [rbp-44h]
  __int128 v39; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v40; // [rsp+D0h] [rbp-30h]
  __int128 v41; // [rsp+E0h] [rbp-20h]
  wchar_t pszDest[264]; // [rsp+F0h] [rbp-10h] BYREF

  Buf1 = L"MSHTML.DLL";
  v30[0] = 0;
  v30[1] = L"JSCRIPT9.DLL";
  v30[2] = 0;
  v30[3] = L"WINDOWS.UI.DLL";
  v30[5] = L"WINDOWS.UI.XAML.DLL";
  v30[7] = L"CLR.DLL";
  v33 = L"MSCORLIB.NI.DLL";
  v36 = L"SYSTEM.NI.DLL";
  v4 = 16LL * *(unsigned int *)(a1 + 52);
  v30[4] = 0;
  v30[6] = 0;
  v31 = 0;
  v32 = 1;
  v34 = 0;
  v35 = 1;
  v37 = 0;
  v38 = 1;
  if ( v4 >= 0xFFFFFFFF )
    return 534;
  v6 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (unsigned int)v4);
  if ( !v6 )
    return 8;
  WindowsDir = PfSvGetWindowsDir(pszDest);
  if ( WindowsDir )
  {
LABEL_10:
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v6);
    return WindowsDir;
  }
  v7 = -1;
  do
    ++v7;
  while ( pszDest[v7] );
  v26 = PfScStringInsertEx(*(_QWORD *)&PfSvcGlobals + 96LL, pszDest, v7);
  v8 = v26;
  if ( !v26 )
  {
    WindowsDir = 8;
    goto LABEL_10;
  }
  for ( i = 0; i != 7; ++i )
  {
    v11 = -1;
    v12 = 2 * i;
    do
      ++v11;
    while ( *(_WORD *)(v30[2 * i - 1] + 2 * v11) );
    LODWORD(v30[v12]) = v11;
  }
  v39 = a1;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v40 = 0;
  v41 = 0;
  for ( j = PfDbIteratorGetNext(&v39); j; j = PfDbIteratorGetNext(&v39) )
  {
    v17 = v40;
    if ( v14 == (_QWORD)v40 )
    {
      if ( v15 )
LABEL_29:
        *(_DWORD *)(*((_QWORD *)&v41 + 1) + 16LL) = -1;
    }
    else
    {
      v15 = 0;
      for ( k = 0; k < 7; ++k )
      {
        if ( !HIDWORD(v30[2 * k]) || (*(_BYTE *)(v17 + 64) & 4) != 0 )
        {
          v19 = 0;
          v25 = *(_QWORD *)(v17 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
          v24 = *(_QWORD *)&PfSvcGlobals + 96LL;
          RtlAcquireSRWLockShared(*(_QWORD *)&PfSvcGlobals + 96LL);
          v20 = *(unsigned int *)(v25 + 24);
          v21 = *(_QWORD *)(v24 + 24);
          if ( *(unsigned __int16 *)(v20 + v21) == LODWORD(v30[2 * k]) )
            v19 = memcmp_0((const void *)v30[2 * k - 1], (const void *)(v20 + 2 + v21), 2LL * LODWORD(v30[2 * k])) == 0;
          RtlReleaseSRWLockShared(v24);
          v22 = !v19;
          v8 = v26;
          if ( !v22 )
          {
            if ( (unsigned int)PfScEntryUnderPath(*(_QWORD *)&PfSvcGlobals + 96LL, v25, v26) )
            {
              v15 = 1;
              v14 = v17;
              goto LABEL_29;
            }
          }
        }
      }
      v14 = v17;
    }
    v23 = v13++;
    v23 *= 2;
    *((_QWORD *)v6 + v23) = *((_QWORD *)&v41 + 1);
    *((_QWORD *)v6 + v23 + 1) = v17;
  }
  qsort(v6, v13, 0x10u, PfSvDynPriDbRangeSortCallback);
  *a2 = v6;
  *a3 = v13;
  PfScStringDereferenceEx(*(_QWORD *)&PfSvcGlobals + 96LL, v8, 0);
  return 0;
}

```

## disassembly

```asm
0x1800810ec  mov     [rsp-8+arg_18], rbx
0x1800810f1  push    rbp
0x1800810f2  push    rsi
0x1800810f3  push    rdi
0x1800810f4  push    r12
0x1800810f6  push    r13
0x1800810f8  push    r14
0x1800810fa  push    r15
0x1800810fc  lea     rbp, [rsp-420h]
0x180081104  sub     rsp, 520h
0x18008110b  mov     rax, cs:__security_cookie
0x180081112  xor     rax, rsp
0x180081115  mov     [rbp+450h+var_40], rax
0x18008111c  xor     r15d, r15d
0x18008111f  mov     [rsp+550h+var_508], r8
0x180081124  lea     rax, aMshtmlDll; "MSHTML.DLL"
0x18008112b  mov     [rsp+550h+var_510], rdx
0x180081130  mov     [rsp+550h+Buf1], rax
0x180081135  mov     r14, rcx
0x180081138  lea     rax, aJscript9Dll; "JSCRIPT9.DLL"
0x18008113f  mov     [rsp+550h+var_4F8], r15
0x180081144  mov     [rsp+550h+var_4F0], rax
0x180081149  lea     esi, [r15+1]
0x18008114d  lea     rax, aWindowsUiDll; "WINDOWS.UI.DLL"
0x180081154  mov     [rsp+550h+var_4E8], r15
0x180081159  mov     [rsp+550h+var_4E0], rax
0x18008115e  lea     rax, aWindowsUiXamlD; "WINDOWS.UI.XAML.DLL"
0x180081165  mov     [rbp+450h+var_4D0], rax
0x180081169  lea     rax, aClrDll; "CLR.DLL"
0x180081170  mov     [rbp+450h+var_4C0], rax
0x180081174  lea     rax, aMscorlibNiDll; "MSCORLIB.NI.DLL"
0x18008117b  mov     [rbp+450h+var_4B0], rax
0x18008117f  lea     rax, aSystemNiDll; "SYSTEM.NI.DLL"
0x180081186  mov     [rbp+450h+var_4A0], rax
0x18008118a  mov     eax, [rcx+34h]
0x18008118d  mov     ecx, 0FFFFFFFFh
0x180081192  shl     rax, 4
0x180081196  mov     [rsp+550h+var_4D8], r15
0x18008119b  mov     [rbp+450h+var_4C8], r15
0x18008119f  mov     [rbp+450h+var_4B8], r15d
0x1800811a3  mov     [rbp+450h+var_4B4], esi
0x1800811a6  mov     [rbp+450h+var_4A8], r15d
0x1800811aa  mov     [rbp+450h+var_4A4], esi
0x1800811ad  mov     [rbp+450h+var_498], r15d
0x1800811b1  mov     [rbp+450h+var_494], esi
0x1800811b4  cmp     rax, rcx
0x1800811b7  jb      short loc_1800811C3
0x1800811b9  mov     ebx, 216h
0x1800811be  jmp     loc_180081254
0x1800811c3  mov     rcx, cs:PfSvcGlobals
0x1800811ca  xor     edx, edx; dwFlags
0x1800811cc  mov     r8d, eax; dwBytes
0x1800811cf  mov     rcx, [rcx+58h]; hHeap
0x1800811d3  call    cs:__imp_HeapAlloc
0x1800811d9  mov     rdi, rax
0x1800811dc  test    rax, rax
0x1800811df  jnz     short loc_1800811E6
0x1800811e1  lea     ebx, [rax+8]
0x1800811e4  jmp     short loc_180081254
0x1800811e6  mov     r9d, 104h
0x1800811ec  lea     r8, [rbp+450h+var_250]
0x1800811f3  lea     rcx, [rbp+450h+pszDest]; pszDest
0x1800811f7  call    PfSvGetWindowsDir
0x1800811fc  mov     ebx, eax
0x1800811fe  test    eax, eax
0x180081200  jnz     short loc_18008123E
0x180081202  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180081206  lea     rax, [rbp+450h+pszDest]
0x18008120a  mov     r8, rbx
0x18008120d  inc     r8
0x180081210  cmp     [rax+r8*2], r15w
0x180081215  jnz     short loc_18008120D
0x180081217  mov     rcx, cs:PfSvcGlobals
0x18008121e  lea     rdx, [rbp+450h+pszDest]
0x180081222  add     rcx, 60h ; '`'
0x180081226  xor     r9d, r9d
0x180081229  call    PfScStringInsertEx
0x18008122e  mov     [rsp+550h+var_520], rax
0x180081233  mov     r13, rax
0x180081236  test    rax, rax
0x180081239  jnz     short loc_180081280
0x18008123b  lea     ebx, [rax+8]
0x18008123e  mov     rcx, cs:PfSvcGlobals
0x180081245  mov     r8, rdi; lpMem
0x180081248  xor     edx, edx; dwFlags
0x18008124a  mov     rcx, [rcx+58h]; hHeap
0x18008124e  call    cs:__imp_HeapFree
0x180081254  mov     eax, ebx
0x180081256  mov     rcx, [rbp+450h+var_40]
0x18008125d  xor     rcx, rsp; StackCookie
0x180081260  call    __security_check_cookie
0x180081265  mov     rbx, [rsp+550h+arg_18]
0x18008126d  add     rsp, 520h
0x180081274  pop     r15
0x180081276  pop     r14
0x180081278  pop     r13
0x18008127a  pop     r12
0x18008127c  pop     rdi
0x18008127d  pop     rsi
0x18008127e  pop     rbp
0x18008127f  retn
0x180081280  mov     rax, r15
0x180081283  mov     rdx, rax
0x180081286  mov     rcx, rbx
0x180081289  add     rdx, rdx
0x18008128c  mov     r8, [rsp+rdx*8+550h+Buf1]
0x180081291  inc     rcx
0x180081294  cmp     [r8+rcx*2], r15w
0x180081299  jnz     short loc_180081291
0x18008129b  add     rax, rsi
0x18008129e  mov     dword ptr [rsp+rdx*8+550h+var_4F8], ecx
0x1800812a2  cmp     rax, 7
0x1800812a6  jnz     short loc_180081283
0x1800812a8  xorps   xmm0, xmm0
0x1800812ab  lea     rcx, [rbp+450h+var_490]
0x1800812af  movups  [rbp+450h+var_490], xmm0
0x1800812b3  mov     qword ptr [rbp+450h+var_490], r14
0x1800812b7  mov     r12d, r15d
0x1800812ba  mov     rsi, r15
0x1800812bd  mov     ebx, r15d
0x1800812c0  movups  [rbp+450h+var_480], xmm0
0x1800812c4  movups  [rbp+450h+var_470], xmm0
0x1800812c8  call    PfDbIteratorGetNext
0x1800812cd  jmp     loc_1800813E9
0x1800812d2  mov     r15, qword ptr [rbp+450h+var_480]
0x1800812d6  cmp     rsi, r15
0x1800812d9  jz      loc_1800813B3
0x1800812df  xor     ebx, ebx
0x1800812e1  xor     r14d, r14d
0x1800812e4  cmp     r14d, 7
0x1800812e8  jnb     loc_1800813C4
0x1800812ee  mov     esi, r14d
0x1800812f1  add     rsi, rsi
0x1800812f4  cmp     dword ptr [rsp+rsi*8+550h+var_4F8+4], ebx
0x1800812f8  jz      short loc_180081305
0x1800812fa  test    byte ptr [r15+40h], 4
0x1800812ff  jz      loc_1800813A4
0x180081305  mov     rax, [r15+10h]
0x180081309  xor     r13d, r13d
0x18008130c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180081310  mov     [rsp+550h+var_528], rax
0x180081315  mov     rax, cs:PfSvcGlobals
0x18008131c  add     rax, 60h ; '`'
0x180081320  mov     rcx, rax
0x180081323  mov     [rsp+550h+var_530], rax
0x180081328  call    cs:__imp_RtlAcquireSRWLockShared
0x18008132e  mov     rax, [rsp+550h+var_528]
0x180081333  mov     ecx, [rax+18h]
0x180081336  mov     rax, [rsp+550h+var_530]
0x18008133b  mov     rdx, [rax+18h]
0x18008133f  movzx   eax, word ptr [rcx+rdx]
0x180081343  cmp     eax, dword ptr [rsp+rsi*8+550h+var_4F8]
0x180081347  jnz     short loc_18008136E
0x180081349  mov     r8d, dword ptr [rsp+rsi*8+550h+var_4F8]
0x18008134e  add     rcx, 2
0x180081352  add     rdx, rcx; Buf2
0x180081355  add     r8, r8; Size
0x180081358  mov     rcx, [rsp+rsi*8+550h+Buf1]; Buf1
0x18008135d  call    memcmp_0
0x180081362  test    eax, eax
0x180081364  lea     esi, [r13+1]
0x180081368  cmovz   r13d, esi
0x18008136c  jmp     short loc_180081373
0x18008136e  mov     esi, 1
0x180081373  mov     rcx, [rsp+550h+var_530]
0x180081378  call    cs:__imp_RtlReleaseSRWLockShared
0x18008137e  test    r13d, r13d
0x180081381  mov     r13, [rsp+550h+var_520]
0x180081386  jz      short loc_1800813A4
0x180081388  mov     rcx, cs:PfSvcGlobals
0x18008138f  mov     r8, r13
0x180081392  mov     rdx, [rsp+550h+var_528]
0x180081397  add     rcx, 60h ; '`'
0x18008139b  call    PfScEntryUnderPath
0x1800813a0  test    eax, eax
0x1800813a2  jnz     short loc_1800813AC
0x1800813a4  inc     r14d
0x1800813a7  jmp     loc_1800812E4
0x1800813ac  mov     ebx, esi
0x1800813ae  mov     rsi, r15
0x1800813b1  jmp     short loc_1800813B7
0x1800813b3  test    ebx, ebx
0x1800813b5  jz      short loc_1800813C7
0x1800813b7  mov     rax, qword ptr [rbp+450h+var_470+8]
0x1800813bb  mov     dword ptr [rax+10h], 0FFFFFFFFh
0x1800813c2  jmp     short loc_1800813C7
0x1800813c4  mov     rsi, r15
0x1800813c7  mov     rcx, qword ptr [rbp+450h+var_470+8]
0x1800813cb  mov     eax, r12d
0x1800813ce  inc     r12d
0x1800813d1  add     rax, rax
0x1800813d4  mov     [rdi+rax*8], rcx
0x1800813d8  lea     rcx, [rbp+450h+var_490]
0x1800813dc  mov     [rdi+rax*8+8], r15
0x1800813e1  call    PfDbIteratorGetNext
0x1800813e6  xor     r15d, r15d
0x1800813e9  test    al, al
0x1800813eb  jnz     loc_1800812D2
0x1800813f1  mov     edx, r12d; NumOfElements
0x1800813f4  lea     r9, PfSvDynPriDbRangeSortCallback; CompareFunction
0x1800813fb  mov     r8d, 10h; SizeOfElements
0x180081401  mov     rcx, rdi; Base
0x180081404  call    cs:__imp_qsort
0x18008140a  mov     rax, [rsp+550h+var_510]
0x18008140f  xor     r8d, r8d
0x180081412  mov     rdx, r13
0x180081415  mov     [rax], rdi
0x180081418  mov     rax, [rsp+550h+var_508]
0x18008141d  mov     [rax], r12d
0x180081420  mov     rcx, cs:PfSvcGlobals
0x180081427  add     rcx, 60h ; '`'
0x18008142b  call    PfScStringDereferenceEx
0x180081430  mov     ebx, r15d
0x180081433  jmp     loc_180081254
```
