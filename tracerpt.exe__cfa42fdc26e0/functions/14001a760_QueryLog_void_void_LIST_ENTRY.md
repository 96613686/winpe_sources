# QueryLog(void *,void *,_LIST_ENTRY *)

- ea: `0x14001a760`
- end: `0x14001ab71`
- name: `?QueryLog@@YAJPEAX0PEAU_LIST_ENTRY@@@Z`
- size: `1041`
- prototype: `__int64 __fastcall(void *, void *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x14001a3b0`

## callees

- `0x140009c78`
- `0x140016808`
- `0x14001a2a8`
- `0x14001a314`
- `0x14001a760`
- `0x14001ac30`
- `0x14002c8cc`
- `0x14002c930`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a83a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a891`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a9dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ab39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a83a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a891`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a9dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ab39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a82c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a849`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a883`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a9ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aa18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aa4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ab2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a82c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a849`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a883`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a9ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aa18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aa4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ab2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a857`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001aa27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001aa5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a857`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001aa27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001aa5e`
- `pdh!PdhAddCounterW` at `0x14001aa07`
- `pdh!PdhAddCounterW` at `0x14001aa07`
- `pdh!PdhExpandWildCardPathHW` at `0x14001a818`
- `pdh!PdhExpandWildCardPathHW` at `0x14001a818`

## pseudocode

```c
__int64 __fastcall QueryLog(void *a1, void *a2, struct _LIST_ENTRY *a3)
{
  struct _LIST_ENTRY *v3; // r12
  void *v4; // rdi
  WCHAR *v5; // rsi
  char v6; // r14
  unsigned int v7; // r15d
  unsigned int v8; // ebp
  const unsigned __int16 *v9; // r8
  WCHAR *v10; // rbx
  PDH_STATUS v11; // edi
  HANDLE ProcessHeap; // rax
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  WCHAR *v15; // rax
  unsigned int v16; // r13d
  HANDLE v17; // rax
  __int64 result; // rax
  WCHAR *v19; // r14
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v20; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v21; // rdi
  LPWSTR szCounterName; // r15
  _QWORD **v23; // r15
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  _QWORD *v26; // r12
  _QWORD *v27; // rbx
  _QWORD *v28; // rax
  unsigned __int16 *szObjectName; // rdx
  __int64 v30; // rbx
  HANDLE v31; // rax
  WCHAR *v32; // r14
  PDH_STATUS v33; // eax
  HANDLE v34; // rax
  struct _LIST_ENTRY **v35; // rax
  struct _LIST_ENTRY **v36; // rbx
  HANDLE v37; // rax
  struct _LIST_ENTRY *v38; // rax
  struct _LIST_ENTRY *Flink; // r10
  struct _LIST_ENTRY *v40; // rcx
  struct _LIST_ENTRY *v41; // r11
  struct _LIST_ENTRY *Blink; // rdx
  signed __int64 v43; // r9
  int v44; // eax
  int v45; // r8d
  __int64 v46; // rax
  HANDLE v47; // rax
  char v48; // [rsp+30h] [rbp-10A8h]
  int v49; // [rsp+34h] [rbp-10A4h]
  DWORD pcchPathListLength; // [rsp+38h] [rbp-10A0h] BYREF
  void *v51; // [rsp+40h] [rbp-1098h]
  WCHAR *v52; // [rsp+48h] [rbp-1090h]
  struct _LIST_ENTRY *v53; // [rsp+50h] [rbp-1088h]
  PDH_HCOUNTER phCounter; // [rsp+58h] [rbp-1080h] BYREF
  __int64 v55; // [rsp+60h] [rbp-1078h]
  _QWORD *v56; // [rsp+68h] [rbp-1070h]
  _QWORD *v57; // [rsp+70h] [rbp-1068h]
  PDH_HQUERY hQuery; // [rsp+78h] [rbp-1060h]
  _UNICODE_STRING v59; // [rsp+80h] [rbp-1058h] BYREF
  WCHAR szWildCardPath[2048]; // [rsp+90h] [rbp-1048h] BYREF

  v3 = a3;
  hQuery = a2;
  v4 = a1;
  v53 = a3;
  v51 = a1;
  v5 = 0;
  v6 = 0;
  v55 = *((_QWORD *)g_TraceContext + 1086);
  v7 = 0;
  v49 = 0;
  v8 = 8;
  phCounter = 0;
  while ( 2 )
  {
    v48 = v6;
    v9 = L"\\\\*\\*(*)\\*";
    if ( !v6 )
      v9 = L"\\\\*\\*\\*";
    StringCchPrintfW(szWildCardPath, 0x800u, v9);
    v10 = 0;
    pcchPathListLength = 0;
    while ( 1 )
    {
      v11 = PdhExpandWildCardPathHW(v4, szWildCardPath, v10, &pcchPathListLength, 0);
      if ( v11 != -2147481646 )
        break;
      if ( v10 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
      }
      v13 = 2LL * (pcchPathListLength + 1);
      v14 = GetProcessHeap();
      v15 = (WCHAR *)HeapAlloc(v14, 8u, v13);
      v4 = v51;
      v10 = v15;
      if ( !v15 )
      {
        v11 = 8;
        v16 = 8;
LABEL_15:
        if ( v6 )
        {
          result = 0;
          if ( v11 != -1073738812 )
            return v16;
          return result;
        }
        goto LABEL_56;
      }
    }
    if ( v11 )
    {
      if ( v10 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
      }
    }
    else
    {
      v5 = v10;
    }
    v16 = v11;
    if ( v11 )
      goto LABEL_15;
    v19 = v5;
    *(_QWORD *)(v55 + 8LL * v7 + 40) = v5;
    if ( !v5 )
    {
LABEL_54:
      if ( v48 )
        return v16;
      v49 = ++v7;
LABEL_56:
      v4 = v51;
      v6 = 1;
      continue;
    }
    break;
  }
  while ( 1 )
  {
    if ( !*v19 )
    {
LABEL_53:
      v7 = v49;
      goto LABEL_54;
    }
    v20 = ParsePdhCounterPath(v19);
    v21 = v20;
    if ( !v20 )
      return v8;
    szCounterName = v20->szCounterName;
    v52 = szCounterName;
    TranslateCouterPathToLangNeutral(v20, v19);
    if ( g_TraceContext && qword_140082288 )
    {
      v23 = (_QWORD **)*((_QWORD *)qword_140082288 + 8);
      if ( v23 )
      {
        v24 = *v23;
        if ( v23 == *v23 )
        {
LABEL_34:
          v30 = -1;
          do
            ++v30;
          while ( v19[v30] );
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v21);
          v32 = &v19[v30];
          goto LABEL_52;
        }
        while ( 1 )
        {
          v25 = (_QWORD *)*v24;
          v26 = v24 + 4;
          v27 = (_QWORD *)v24[4];
          v57 = (_QWORD *)*v24;
          if ( v24 + 4 != v27 )
            break;
LABEL_32:
          v24 = v25;
          if ( v23 == v25 )
          {
            v3 = v53;
            goto LABEL_34;
          }
        }
        while ( 1 )
        {
          v28 = (_QWORD *)*v27;
          szObjectName = v21->szObjectName;
          v59 = *(_UNICODE_STRING *)(v27 + 17);
          v56 = v28;
          if ( EqualString(&v59, szObjectName, 1) )
          {
            if ( !IsExCounter((struct _TRACERPT_COUNTER_TABLE *)v27, v21->szCounterName)
              && IsInclusiveInstance((struct _TRACERPT_COUNTER_TABLE *)v27, v21->szInstanceName) )
            {
              break;
            }
          }
          v27 = v56;
          if ( v26 == v56 )
          {
            v25 = v57;
            goto LABEL_32;
          }
        }
        v3 = v53;
      }
      szCounterName = v52;
    }
    v33 = PdhAddCounterW(hQuery, v19, 0, &phCounter);
    v16 = 0;
    if ( v33 )
      break;
    v34 = GetProcessHeap();
    v35 = (struct _LIST_ENTRY **)HeapAlloc(v34, 8u, 0x78u);
    v36 = v35;
    if ( !v35 )
      goto LABEL_60;
    v35[2] = (struct _LIST_ENTRY *)phCounter;
    v35[3] = (struct _LIST_ENTRY *)v21;
    *((_DWORD *)v35 + 10) = 128;
    v37 = GetProcessHeap();
    v38 = (struct _LIST_ENTRY *)HeapAlloc(v37, 8u, 0x1400u);
    if ( !v38 )
    {
      CleanupPdhRptEntry((struct _PDHRPT_COUNTER_ENTRY *)v36);
      return v8;
    }
    v36[4] = v38;
    v36[14] = (struct _LIST_ENTRY *)szCounterName;
    Flink = v3->Flink;
    v40 = v3->Flink;
    if ( v3 == v3->Flink )
    {
LABEL_48:
      *v36 = Flink;
      v36[1] = v3;
      Flink->Blink = (struct _LIST_ENTRY *)v36;
      v3->Flink = (struct _LIST_ENTRY *)v36;
    }
    else
    {
      while ( 1 )
      {
        v41 = v40->Flink;
        Blink = v40[1].Blink->Blink;
        v43 = (char *)v36[3]->Blink - (char *)Blink;
        do
        {
          v44 = *(unsigned __int16 *)((char *)&Blink->Flink + v43);
          v45 = LOWORD(Blink->Flink) - v44;
          if ( v45 )
            break;
          Blink = (struct _LIST_ENTRY *)((char *)Blink + 2);
        }
        while ( v44 );
        if ( !v45 )
          break;
        v40 = v40->Flink;
        if ( v3 == v41 )
          goto LABEL_48;
      }
      *v36 = v41;
      v36[1] = v40;
      v40->Flink = (struct _LIST_ENTRY *)v36;
      (*v36)->Blink = (struct _LIST_ENTRY *)v36;
    }
    v46 = -1;
    do
      ++v46;
    while ( v19[v46] );
    v32 = &v19[v46];
LABEL_52:
    v19 = v32 + 1;
    if ( !v19 )
      goto LABEL_53;
  }
  v8 = v33;
LABEL_60:
  v47 = GetProcessHeap();
  HeapFree(v47, 0, v21);
  return v8;
}

```

## disassembly

```asm
0x14001a760  mov     [rsp+arg_18], rbx
0x14001a765  push    rbp
0x14001a766  push    rsi
0x14001a767  push    rdi
0x14001a768  push    r12
0x14001a76a  push    r13
0x14001a76c  push    r14
0x14001a76e  push    r15
0x14001a770  mov     eax, 10A0h
0x14001a775  call    _alloca_probe
0x14001a77a  sub     rsp, rax
0x14001a77d  mov     rax, cs:__security_cookie
0x14001a784  xor     rax, rsp
0x14001a787  mov     [rsp+10D8h+var_48], rax
0x14001a78f  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001a796  mov     r12, r8
0x14001a799  mov     [rsp+10D8h+hQuery], rdx
0x14001a79e  mov     rdi, rcx
0x14001a7a1  xor     edx, edx
0x14001a7a3  mov     [rsp+10D8h+var_1088], r8
0x14001a7a8  mov     [rsp+10D8h+var_1098], rcx
0x14001a7ad  mov     esi, edx
0x14001a7af  mov     rax, [rax+21F0h]
0x14001a7b6  mov     r14b, dl
0x14001a7b9  mov     [rsp+10D8h+var_1078], rax
0x14001a7be  mov     r15d, edx
0x14001a7c1  mov     [rsp+10D8h+var_10A4], edx
0x14001a7c5  lea     ebp, [rdx+8]
0x14001a7c8  mov     [rsp+10D8h+phCounter], rdx
0x14001a7cd  lea     rax, asc_140048E60; "\\\\*\\*\\*"
0x14001a7d4  mov     [rsp+10D8h+var_10A8], r14b
0x14001a7d9  test    r14b, r14b
0x14001a7dc  lea     r8, asc_140048E48; "\\\\*\\*(*)\\*"
0x14001a7e3  mov     edx, 800h; unsigned __int64
0x14001a7e8  lea     rcx, [rsp+10D8h+szWildCardPath]; unsigned __int16 *
0x14001a7f0  cmovz   r8, rax; unsigned __int16 *
0x14001a7f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001a7f9  xor     edx, edx
0x14001a7fb  mov     ebx, edx
0x14001a7fd  mov     [rsp+10D8h+pcchPathListLength], edx
0x14001a801  mov     [rsp+10D8h+dwFlags], edx; dwFlags
0x14001a805  lea     r9, [rsp+10D8h+pcchPathListLength]; pcchPathListLength
0x14001a80a  lea     rdx, [rsp+10D8h+szWildCardPath]; szWildCardPath
0x14001a812  mov     r8, rbx; mszExpandedPathList
0x14001a815  mov     rcx, rdi; hDataSource
0x14001a818  call    cs:__imp_PdhExpandWildCardPathHW
0x14001a81e  mov     edi, eax
0x14001a820  cmp     eax, 800007D2h
0x14001a825  jnz     short loc_14001A873
0x14001a827  test    rbx, rbx
0x14001a82a  jz      short loc_14001A840
0x14001a82c  call    cs:__imp_GetProcessHeap
0x14001a832  mov     r8, rbx; lpMem
0x14001a835  xor     edx, edx; dwFlags
0x14001a837  mov     rcx, rax; hHeap
0x14001a83a  call    cs:__imp_HeapFree
0x14001a840  mov     ebx, [rsp+10D8h+pcchPathListLength]
0x14001a844  inc     ebx
0x14001a846  add     rbx, rbx
0x14001a849  call    cs:__imp_GetProcessHeap
0x14001a84f  mov     r8, rbx; dwBytes
0x14001a852  mov     edx, ebp; dwFlags
0x14001a854  mov     rcx, rax; hHeap
0x14001a857  call    cs:__imp_HeapAlloc
0x14001a85d  mov     rdi, [rsp+10D8h+var_1098]
0x14001a862  xor     edx, edx
0x14001a864  mov     rbx, rax
0x14001a867  test    rax, rax
0x14001a86a  jnz     short loc_14001A801
0x14001a86c  mov     edi, ebp
0x14001a86e  mov     r13d, ebp
0x14001a871  jmp     short loc_14001A8A0
0x14001a873  xor     edx, edx
0x14001a875  test    edi, edi
0x14001a877  jnz     short loc_14001A87E
0x14001a879  mov     rsi, rbx
0x14001a87c  jmp     short loc_14001A899
0x14001a87e  test    rbx, rbx
0x14001a881  jz      short loc_14001A899
0x14001a883  call    cs:__imp_GetProcessHeap
0x14001a889  mov     r8, rbx; lpMem
0x14001a88c  xor     edx, edx; dwFlags
0x14001a88e  mov     rcx, rax; hHeap
0x14001a891  call    cs:__imp_HeapFree
0x14001a897  xor     edx, edx
0x14001a899  mov     r13d, edi
0x14001a89c  test    edi, edi
0x14001a89e  jz      short loc_14001A8BA
0x14001a8a0  test    r14b, r14b
0x14001a8a3  jz      loc_14001AAFF
0x14001a8a9  cmp     edi, 0C0000BC4h
0x14001a8af  mov     eax, edx
0x14001a8b1  cmovnz  eax, r13d
0x14001a8b5  jmp     loc_14001AB46
0x14001a8ba  mov     rcx, [rsp+10D8h+var_1078]
0x14001a8bf  mov     r14, rsi
0x14001a8c2  mov     eax, r15d
0x14001a8c5  mov     [rcx+rax*8+28h], rsi
0x14001a8ca  test    rsi, rsi
0x14001a8cd  jz      loc_14001AAF1
0x14001a8d3  cmp     [r14], dx
0x14001a8d7  jz      loc_14001AAEC
0x14001a8dd  mov     rcx, r14; szFullPathBuffer
0x14001a8e0  call    ?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; ParsePdhCounterPath(ushort *)
0x14001a8e5  mov     rdi, rax
0x14001a8e8  test    rax, rax
0x14001a8eb  jz      loc_14001AB3F
0x14001a8f1  mov     r15, [rax+28h]
0x14001a8f5  mov     rdx, r14; unsigned __int16 *
0x14001a8f8  mov     rcx, rax; struct _PDH_COUNTER_PATH_ELEMENTS_W *
0x14001a8fb  mov     [rsp+10D8h+var_1090], r15
0x14001a900  call    ?TranslateCouterPathToLangNeutral@@YAXPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; TranslateCouterPathToLangNeutral(_PDH_COUNTER_PATH_ELEMENTS_W *,ushort *)
0x14001a905  xor     ecx, ecx
0x14001a907  cmp     cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA, rcx; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001a90e  jz      loc_14001A9F7
0x14001a914  mov     rax, cs:qword_140082288
0x14001a91b  test    rax, rax
0x14001a91e  jz      loc_14001A9F7
0x14001a924  mov     r15, [rax+40h]
0x14001a928  test    r15, r15
0x14001a92b  jz      loc_14001A9F2
0x14001a931  mov     rax, [r15]
0x14001a934  cmp     r15, rax
0x14001a937  jz      loc_14001A9C0
0x14001a93d  mov     rcx, [rax]
0x14001a940  lea     r12, [rax+20h]
0x14001a944  mov     rbx, [r12]
0x14001a948  mov     [rsp+10D8h+var_1068], rcx
0x14001a94d  cmp     r12, rbx
0x14001a950  jz      short loc_14001A9B1
0x14001a952  movups  xmm0, xmmword ptr [rbx+88h]
0x14001a959  mov     rax, [rbx]
0x14001a95c  lea     rcx, [rsp+10D8h+var_1058]; struct _UNICODE_STRING
0x14001a964  mov     rdx, [rdi+8]; unsigned __int16 *
0x14001a968  mov     r8b, 1; unsigned __int8
0x14001a96b  movdqu  xmmword ptr [rsp+10D8h+var_1058.Length], xmm0
0x14001a974  mov     [rsp+10D8h+var_1070], rax
0x14001a979  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14001a97e  test    al, al
0x14001a980  jz      short loc_14001A9A2
0x14001a982  mov     rdx, [rdi+28h]; unsigned __int16 *
0x14001a986  mov     rcx, rbx; struct _TRACERPT_COUNTER_TABLE *
0x14001a989  call    ?IsExCounter@@YAHPEAU_TRACERPT_COUNTER_TABLE@@PEAG@Z; IsExCounter(_TRACERPT_COUNTER_TABLE *,ushort *)
0x14001a98e  test    eax, eax
0x14001a990  jnz     short loc_14001A9A2
0x14001a992  mov     rdx, [rdi+10h]; unsigned __int16 *
0x14001a996  mov     rcx, rbx; struct _TRACERPT_COUNTER_TABLE *
0x14001a999  call    ?IsInclusiveInstance@@YAHPEAU_TRACERPT_COUNTER_TABLE@@PEAG@Z; IsInclusiveInstance(_TRACERPT_COUNTER_TABLE *,ushort *)
0x14001a99e  test    eax, eax
0x14001a9a0  jnz     short loc_14001A9ED
0x14001a9a2  mov     rbx, [rsp+10D8h+var_1070]
0x14001a9a7  cmp     r12, rbx
0x14001a9aa  jnz     short loc_14001A952
0x14001a9ac  mov     rcx, [rsp+10D8h+var_1068]
0x14001a9b1  mov     rax, rcx
0x14001a9b4  cmp     r15, rcx
0x14001a9b7  jnz     short loc_14001A93D
0x14001a9b9  mov     r12, [rsp+10D8h+var_1088]
0x14001a9be  xor     ecx, ecx
0x14001a9c0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001a9c4  inc     rbx
0x14001a9c7  cmp     [r14+rbx*2], cx
0x14001a9cc  jnz     short loc_14001A9C4
0x14001a9ce  call    cs:__imp_GetProcessHeap
0x14001a9d4  mov     r8, rdi; lpMem
0x14001a9d7  xor     edx, edx; dwFlags
0x14001a9d9  mov     rcx, rax; hHeap
0x14001a9dc  call    cs:__imp_HeapFree
0x14001a9e2  xor     edx, edx
0x14001a9e4  lea     r14, [r14+rbx*2]
0x14001a9e8  jmp     loc_14001AAE2
0x14001a9ed  mov     r12, [rsp+10D8h+var_1088]
0x14001a9f2  mov     r15, [rsp+10D8h+var_1090]
0x14001a9f7  mov     rcx, [rsp+10D8h+hQuery]; hQuery
0x14001a9fc  lea     r9, [rsp+10D8h+phCounter]; phCounter
0x14001aa01  xor     r8d, r8d; dwUserData
0x14001aa04  mov     rdx, r14; szFullCounterPath
0x14001aa07  call    cs:__imp_PdhAddCounterW
0x14001aa0d  xor     r13d, r13d
0x14001aa10  test    eax, eax
0x14001aa12  jnz     loc_14001AB29
0x14001aa18  call    cs:__imp_GetProcessHeap
0x14001aa1e  lea     r8d, [r13+78h]; dwBytes
0x14001aa22  mov     edx, ebp; dwFlags
0x14001aa24  mov     rcx, rax; hHeap
0x14001aa27  call    cs:__imp_HeapAlloc
0x14001aa2d  mov     rbx, rax
0x14001aa30  test    rax, rax
0x14001aa33  jz      loc_14001AB2B
0x14001aa39  mov     rcx, [rsp+10D8h+phCounter]
0x14001aa3e  mov     [rax+10h], rcx
0x14001aa42  mov     [rax+18h], rdi
0x14001aa46  mov     dword ptr [rax+28h], 80h
0x14001aa4d  call    cs:__imp_GetProcessHeap
0x14001aa53  mov     r8d, 1400h; dwBytes
0x14001aa59  mov     edx, ebp; dwFlags
0x14001aa5b  mov     rcx, rax; hHeap
0x14001aa5e  call    cs:__imp_HeapAlloc
0x14001aa64  xor     edx, edx
0x14001aa66  test    rax, rax
0x14001aa69  jz      loc_14001AB1F
0x14001aa6f  mov     [rbx+20h], rax
0x14001aa73  mov     [rbx+70h], r15
0x14001aa77  mov     r10, [r12]
0x14001aa7b  mov     rcx, r10
0x14001aa7e  cmp     r12, r10
0x14001aa81  jz      short loc_14001AAC1
0x14001aa83  mov     rax, [rbx+18h]
0x14001aa87  mov     rdi, [rax+8]
0x14001aa8b  mov     rax, [rcx+18h]
0x14001aa8f  mov     r9, rdi
0x14001aa92  mov     r11, [rcx]
0x14001aa95  mov     rdx, [rax+8]
0x14001aa99  sub     r9, rdx
0x14001aa9c  movzx   r8d, word ptr [rdx]
0x14001aaa0  movzx   eax, word ptr [rdx+r9]
0x14001aaa5  sub     r8d, eax
0x14001aaa8  jnz     short loc_14001AAB2
0x14001aaaa  add     rdx, 2
0x14001aaae  test    eax, eax
0x14001aab0  jnz     short loc_14001AA9C
0x14001aab2  xor     edx, edx
0x14001aab4  test    r8d, r8d
0x14001aab7  jz      short loc_14001AB0C
0x14001aab9  mov     rcx, r11
0x14001aabc  cmp     r12, r11
0x14001aabf  jnz     short loc_14001AA8B
0x14001aac1  mov     [rbx], r10
0x14001aac4  mov     [rbx+8], r12
0x14001aac8  mov     [r10+8], rbx
0x14001aacc  mov     [r12], rbx
0x14001aad0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001aad4  inc     rax
0x14001aad7  cmp     [r14+rax*2], dx
0x14001aadc  jnz     short loc_14001AAD4
0x14001aade  lea     r14, [r14+rax*2]
0x14001aae2  add     r14, 2
0x14001aae6  jnz     loc_14001A8D3
0x14001aaec  mov     r15d, [rsp+10D8h+var_10A4]
0x14001aaf1  cmp     [rsp+10D8h+var_10A8], dl
0x14001aaf5  jnz     short loc_14001AB43
0x14001aaf7  inc     r15d
0x14001aafa  mov     [rsp+10D8h+var_10A4], r15d
0x14001aaff  mov     rdi, [rsp+10D8h+var_1098]
0x14001ab04  mov     r14b, 1
0x14001ab07  jmp     loc_14001A7CD
0x14001ab0c  mov     [rbx], r11
0x14001ab0f  mov     [rbx+8], rcx
0x14001ab13  mov     [rcx], rbx
0x14001ab16  mov     rax, [rbx]
0x14001ab19  mov     [rax+8], rbx
0x14001ab1d  jmp     short loc_14001AAD0
0x14001ab1f  mov     rcx, rbx; struct _PDHRPT_COUNTER_ENTRY *
0x14001ab22  call    ?CleanupPdhRptEntry@@YAXPEAU_PDHRPT_COUNTER_ENTRY@@@Z; CleanupPdhRptEntry(_PDHRPT_COUNTER_ENTRY *)
0x14001ab27  jmp     short loc_14001AB3F
0x14001ab29  mov     ebp, eax
0x14001ab2b  call    cs:__imp_GetProcessHeap
0x14001ab31  mov     r8, rdi; lpMem
0x14001ab34  xor     edx, edx; dwFlags
0x14001ab36  mov     rcx, rax; hHeap
0x14001ab39  call    cs:__imp_HeapFree
0x14001ab3f  mov     eax, ebp
0x14001ab41  jmp     short loc_14001AB46
0x14001ab43  mov     eax, r13d
0x14001ab46  mov     rcx, [rsp+10D8h+var_48]
0x14001ab4e  xor     rcx, rsp; StackCookie
0x14001ab51  call    __security_check_cookie
0x14001ab56  mov     rbx, [rsp+10D8h+arg_18]
0x14001ab5e  add     rsp, 10A0h
0x14001ab65  pop     r15
0x14001ab67  pop     r14
0x14001ab69  pop     r13
0x14001ab6b  pop     r12
0x14001ab6d  pop     rdi
0x14001ab6e  pop     rsi
0x14001ab6f  pop     rbp
0x14001ab70  retn
```
