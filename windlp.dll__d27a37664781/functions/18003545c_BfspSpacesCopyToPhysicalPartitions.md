# BfspSpacesCopyToPhysicalPartitions

- ea: `0x18003545c`
- end: `0x1800358d8`
- name: `BfspSpacesCopyToPhysicalPartitions`
- size: `1148`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180034fc8`

## callees

- `0x180001df8`
- `0x18000200c`
- `0x180031598`
- `0x180033eb0`
- `0x1800347c4`
- `0x18003538c`
- `0x18003545c`
- `0x180035c20`
- `0x1800366b8`
- `0x180037220`
- `0x180037ea8`
- `0x180039394`
- `0x18003c464`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035687`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003570c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035687`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003570c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035737`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180035737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035786`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800354e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800354e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035794`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800356c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035513`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800356c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003575f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003585a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800354d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003575f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003585a`

## string_xrefs

- `0x180035532`: `ServiceSpaces: %s does not exist`
- `0x1800357d5`: `ServiceSpaces: Failed to create path %s. Last error = %#x`
- `0x180035829`: `ServiceSpaces: Skipping non-Windows %s`
- `0x180035868`: `ServiceSpaces: Failed to copy %s to %s. Last Error = %#x`
- `0x18003587f`: `ServiceSpaces: Skipping %s`
- `0x1800356ac`: `CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x`
- `0x180035700`: `CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x`
- `0x18003572b`: `CreatePath: Unable to create [%s]; GLE = 0x%x`
- `0x180035768`: `CreatePath: Unable to get attributes for [%s]; GLE = 0x%x`
- `0x180035753`: `CreatePath: Existing path [%s] is not a directory; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall BfspSpacesCopyToPhysicalPartitions(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r15
  DWORD LastError; // r14d
  _WORD *v9; // r13
  __int64 v10; // rax
  WCHAR *v11; // rsi
  HANDLE v12; // rax
  HANDLE v13; // rax
  int v15; // r12d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned int v18; // edi
  unsigned int v19; // ebx
  __int64 v20; // rcx
  DWORD v21; // ebx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // r12
  __int64 v24; // rax
  WCHAR *v25; // rdi
  int v26; // r15d
  const wchar_t *v27; // rcx
  wchar_t *v28; // rax
  DWORD v29; // eax
  DWORD v30; // eax
  wchar_t *v31; // r9
  const wchar_t *v32; // r8
  DWORD FileAttributesW; // eax
  HANDLE ProcessHeap; // rax
  DWORD v35; // eax
  unsigned int FirmwareType; // eax
  __int64 v37; // [rsp+20h] [rbp-E0h]
  wchar_t *v38; // [rsp+30h] [rbp-D0h]
  unsigned int v39; // [rsp+38h] [rbp-C8h]
  int v40; // [rsp+3Ch] [rbp-C4h]
  int v41; // [rsp+40h] [rbp-C0h]
  wchar_t pszSrc[264]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = a5;
  LastError = 0;
  v9 = (_WORD *)BfspEnvExpandString(a1, a3);
  if ( !v9 )
  {
    LastError = GetLastError();
    goto LABEL_7;
  }
  v10 = BfspEnvExpandString(a1, a2);
  v11 = (WCHAR *)v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    goto LABEL_5;
  }
  if ( (unsigned int)BfspFileExists(v10) )
  {
    v15 = 0;
    v40 = 0;
    v16 = -1;
    do
      ++v16;
    while ( v9[v16] );
    v39 = 0;
    v17 = v16 - 1;
    v18 = 0;
    if ( v16 )
    {
      while ( v9[v17] != 92 )
      {
        ++v18;
        --v17;
        v39 = v18;
        if ( v18 >= v16 )
          goto LABEL_18;
      }
      v15 = 1;
      v40 = 1;
    }
LABEL_18:
    v19 = 0;
    v41 = 0;
    if ( !*(_DWORD *)(a5 + 8) )
      goto LABEL_5;
    while ( 1 )
    {
      LODWORD(v37) = *(_DWORD *)(v5 + 12LL * v19 + 20);
      StringCchPrintfW(
        pszSrc,
        0x104u,
        L"\\\\?\\Harddisk%uPartition%u\\%s",
        *(unsigned int *)(v5 + 12LL * v19 + 16),
        v37,
        v9,
        v38);
      if ( !v15 )
        goto LABEL_51;
      v20 = -1;
      v21 = 0;
      do
        ++v20;
      while ( pszSrc[v20] );
      v22 = v20 + ~(unsigned __int64)v18;
      v23 = v22;
      if ( 2 * v22 >= 0x208 )
        _report_rangecheckfailure();
      pszSrc[v22] = 0;
      v38 = 0;
      if ( pszSrc[0] )
      {
        v24 = PrepareUnicodePathEx(pszSrc);
        v25 = (WCHAR *)v24;
        if ( v24 )
        {
          v26 = 1;
          v27 = (const wchar_t *)v24;
          while ( 1 )
          {
            v28 = wcschr_0(v27, 0x5Cu);
            v38 = v28;
            if ( !v28 )
              break;
            *v28 = 0;
            if ( !CreateDirectoryW(v25, 0) )
            {
              v29 = GetLastError();
              v21 = v29;
              if ( v29 == 5 || v29 == 183 )
              {
                v21 = 0;
              }
              else
              {
                LODWORD(v37) = v29;
                LibLog(
                  &g_WdsLibLog,
                  50331648,
                  L"CreatePath: Unable to create intermediate path [%s]; GLE = 0x%x",
                  v25,
                  v37);
                SetLastError(v21);
                v26 = 0;
              }
            }
            *v38 = 92;
            v27 = ++v38;
            if ( v26 != 1 )
            {
              v30 = GetLastError();
              v31 = pszSrc;
              v32 = L"CreatePath: Unable to create parent directory for [%s]; GLE = 0x%x";
              goto LABEL_42;
            }
          }
          if ( CreateDirectoryW(v25, 0) )
            goto LABEL_44;
          v30 = GetLastError();
          v21 = v30;
          if ( v30 != 183 )
          {
            v31 = v25;
            v32 = L"CreatePath: Unable to create [%s]; GLE = 0x%x";
            goto LABEL_43;
          }
          FileAttributesW = GetFileAttributesW(v25);
          if ( FileAttributesW == -1 )
          {
            v30 = GetLastError();
            v31 = v25;
            v32 = L"CreatePath: Unable to get attributes for [%s]; GLE = 0x%x";
LABEL_42:
            v21 = v30;
LABEL_43:
            LODWORD(v37) = v30;
            LibLog(&g_WdsLibLog, 50331648, v32, v31, v37);
            goto LABEL_44;
          }
          if ( (FileAttributesW & 0x10) != 0 )
          {
            v21 = 0;
          }
          else
          {
            LODWORD(v37) = 183;
            LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Existing path [%s] is not a directory; GLE = 0x%x", v25, v37);
          }
LABEL_44:
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          v5 = a5;
        }
        else
        {
          v21 = GetLastError();
        }
        SetLastError(v21);
        if ( !v21 )
          goto LABEL_50;
      }
      else
      {
        SetLastError(0x57u);
      }
      v35 = GetLastError();
      BfspLogMessage(3, L"ServiceSpaces: Failed to create path %s. Last error = %#x", pszSrc, v35);
LABEL_50:
      v19 = v41;
      v18 = v39;
      pszSrc[v23] = 92;
      v15 = v40;
LABEL_51:
      if ( a4
        && (unsigned int)BfspFileExists(pszSrc)
        && (FirmwareType = BfspGetFirmwareType(), !(unsigned int)BfspIsWindowsBinary(pszSrc, a4, FirmwareType)) )
      {
        BfspLogMessage(3, L"ServiceSpaces: Skipping non-Windows %s", pszSrc);
      }
      else if ( (unsigned int)BfspShouldFileBeCopied(v11) )
      {
        if ( !(unsigned int)BfspCopyFile(v11, pszSrc) )
        {
          LODWORD(v37) = GetLastError();
          BfspLogMessage(3, L"ServiceSpaces: Failed to copy %s to %s. Last Error = %#x", v11, pszSrc, v37);
        }
      }
      else
      {
        BfspLogMessage(3, L"ServiceSpaces: Skipping %s", pszSrc);
      }
      v41 = ++v19;
      if ( v19 >= *(_DWORD *)(v5 + 8) )
        goto LABEL_5;
    }
  }
  BfspLogMessage(4, L"ServiceSpaces: %s does not exist", v11);
  LastError = 2;
LABEL_5:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v9);
  if ( v11 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v11);
  }
LABEL_7:
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x18003545c  push    rbp
0x18003545e  push    rbx
0x18003545f  push    rsi
0x180035460  push    rdi
0x180035461  push    r12
0x180035463  push    r13
0x180035465  push    r14
0x180035467  push    r15
0x180035469  lea     rbp, [rsp-188h]
0x180035471  sub     rsp, 288h
0x180035478  mov     rax, cs:__security_cookie
0x18003547f  xor     rax, rsp
0x180035482  mov     [rbp+1C0h+var_50], rax
0x180035489  mov     r15, [rbp+1C0h+arg_20]
0x180035490  mov     rdi, rdx
0x180035493  mov     rdx, r8
0x180035496  mov     [rsp+2C0h+var_270], r15
0x18003549b  mov     [rsp+2C0h+var_278], r9
0x1800354a0  mov     rbx, rcx
0x1800354a3  call    BfspEnvExpandString
0x1800354a8  xor     r14d, r14d
0x1800354ab  mov     r13, rax
0x1800354ae  test    rax, rax
0x1800354b1  jnz     short loc_1800354BE
0x1800354b3  call    cs:__imp_GetLastError
0x1800354b9  mov     r14d, eax
0x1800354bc  jmp     short loc_180035507
0x1800354be  mov     rdx, rdi
0x1800354c1  mov     rcx, rbx
0x1800354c4  call    BfspEnvExpandString
0x1800354c9  mov     rsi, rax
0x1800354cc  test    rax, rax
0x1800354cf  jnz     short loc_180035520
0x1800354d1  call    cs:__imp_GetLastError
0x1800354d7  mov     r14d, eax
0x1800354da  call    cs:__imp_GetProcessHeap
0x1800354e0  mov     r8, r13; lpMem
0x1800354e3  xor     edx, edx; dwFlags
0x1800354e5  mov     rcx, rax; hHeap
0x1800354e8  call    cs:__imp_HeapFree
0x1800354ee  test    rsi, rsi
0x1800354f1  jz      short loc_180035507
0x1800354f3  call    cs:__imp_GetProcessHeap
0x1800354f9  mov     r8, rsi; lpMem
0x1800354fc  xor     edx, edx; dwFlags
0x1800354fe  mov     rcx, rax; hHeap
0x180035501  call    cs:__imp_HeapFree
0x180035507  test    r14d, r14d
0x18003550a  jz      loc_1800358AA
0x180035510  mov     ecx, r14d; dwErrCode
0x180035513  call    cs:__imp_SetLastError
0x180035519  xor     eax, eax
0x18003551b  jmp     loc_1800358AF
0x180035520  mov     rcx, rsi
0x180035523  call    BfspFileExists
0x180035528  xor     r8d, r8d
0x18003552b  test    eax, eax
0x18003552d  jnz     short loc_180035549
0x18003552f  mov     r8, rsi
0x180035532  lea     rdx, aServicespacesS_1; "ServiceSpaces: %s does not exist"
0x180035539  lea     ecx, [rax+4]
0x18003553c  call    BfspLogMessage
0x180035541  mov     r14d, 2
0x180035547  jmp     short loc_1800354DA
0x180035549  mov     r12d, r8d
0x18003554c  mov     [rsp+2C0h+var_284], r8d
0x180035551  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035555  inc     rcx
0x180035558  cmp     [r13+rcx*2+0], r8w
0x18003555e  jnz     short loc_180035555
0x180035560  mov     [rsp+2C0h+var_288], r8d
0x180035565  lea     rdx, [rcx-1]
0x180035569  mov     edi, r8d
0x18003556c  mov     eax, 5Ch ; '\'
0x180035571  test    rcx, rcx
0x180035574  jz      short loc_1800355A0
0x180035576  cmp     [r13+rdx*2+0], ax
0x18003557c  jz      short loc_180035595
0x18003557e  inc     edi
0x180035580  dec     rdx
0x180035583  mov     eax, edi
0x180035585  cmp     rax, rcx
0x180035588  mov     [rsp+2C0h+var_288], edi
0x18003558c  mov     eax, 5Ch ; '\'
0x180035591  jb      short loc_180035576
0x180035593  jmp     short loc_1800355A0
0x180035595  mov     r12d, 1
0x18003559b  mov     [rsp+2C0h+var_284], r12d
0x1800355a0  mov     ebx, r8d
0x1800355a3  mov     [rsp+2C0h+var_280], ebx
0x1800355a7  cmp     [r15+8], r8d
0x1800355ab  jbe     loc_1800354DA
0x1800355b1  mov     eax, ebx
0x1800355b3  lea     r8, aHarddiskUparti; "\\\\?\\Harddisk%uPartition%u\\%s"
0x1800355ba  mov     [rsp+2C0h+var_298], r13
0x1800355bf  lea     rcx, [rsp+2C0h+pszSrc]; unsigned __int16 *
0x1800355c4  mov     edx, 104h; unsigned __int64
0x1800355c9  lea     r9, [rax+rax*2]
0x1800355cd  mov     eax, [r15+r9*4+14h]
0x1800355d2  mov     r9d, [r15+r9*4+10h]
0x1800355d7  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800355db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800355e0  test    r12d, r12d
0x1800355e3  jz      loc_1800357F9
0x1800355e9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800355ed  lea     rax, [rsp+2C0h+pszSrc]
0x1800355f2  xor     ebx, ebx
0x1800355f4  inc     rcx
0x1800355f7  cmp     [rax+rcx*2], bx
0x1800355fb  jnz     short loc_1800355F4
0x1800355fd  mov     eax, edi
0x1800355ff  not     rax
0x180035602  add     rax, rcx
0x180035605  lea     r12, [rax+rax]
0x180035609  cmp     r12, 208h
0x180035610  jnb     loc_1800358D2
0x180035616  mov     [rsp+r12+2C0h+pszSrc], bx
0x18003561c  mov     [rsp+2C0h+var_290], rbx
0x180035621  cmp     bx, [rsp+2C0h+pszSrc]
0x180035626  jz      loc_1800357B7
0x18003562c  lea     rdx, [rsp+2C0h+var_290]
0x180035631  lea     rcx, [rsp+2C0h+pszSrc]; pszSrc
0x180035636  call    PrepareUnicodePathEx
0x18003563b  mov     rdi, rax
0x18003563e  test    rax, rax
0x180035641  jz      loc_1800357A1
0x180035647  mov     rcx, [rsp+2C0h+var_290]
0x18003564c  mov     r15d, 1
0x180035652  test    rcx, rcx
0x180035655  jz      short loc_18003565D
0x180035657  add     rcx, 2
0x18003565b  jmp     short loc_180035660
0x18003565d  mov     rcx, rdi; Str
0x180035660  mov     [rsp+2C0h+var_290], rcx
0x180035665  mov     edx, 5Ch ; '\'; Ch
0x18003566a  call    wcschr_0
0x18003566f  xor     ecx, ecx
0x180035671  mov     [rsp+2C0h+var_290], rax
0x180035676  xor     edx, edx; lpSecurityAttributes
0x180035678  test    rax, rax
0x18003567b  jz      loc_180035709
0x180035681  mov     [rax], cx
0x180035684  mov     rcx, rdi; lpPathName
0x180035687  call    cs:__imp_CreateDirectoryW
0x18003568d  test    eax, eax
0x18003568f  jnz     short loc_1800356D3
0x180035691  call    cs:__imp_GetLastError
0x180035697  mov     ebx, eax
0x180035699  cmp     eax, 5
0x18003569c  jz      short loc_1800356D1
0x18003569e  cmp     eax, 0B7h
0x1800356a3  jz      short loc_1800356D1
0x1800356a5  mov     r9, rdi
0x1800356a8  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800356ac  lea     r8, aCreatepathUnab; "CreatePath: Unable to create intermedia"...
0x1800356b3  mov     edx, 3000000h
0x1800356b8  lea     rcx, g_WdsLibLog
0x1800356bf  call    LibLog
0x1800356c4  mov     ecx, ebx; dwErrCode
0x1800356c6  call    cs:__imp_SetLastError
0x1800356cc  xor     r15d, r15d
0x1800356cf  jmp     short loc_1800356D3
0x1800356d1  xor     ebx, ebx
0x1800356d3  mov     rax, [rsp+2C0h+var_290]
0x1800356d8  mov     word ptr [rax], 5Ch ; '\'
0x1800356dd  mov     rcx, [rsp+2C0h+var_290]
0x1800356e2  add     rcx, 2
0x1800356e6  mov     [rsp+2C0h+var_290], rcx
0x1800356eb  cmp     r15d, 1
0x1800356ef  jz      loc_180035665
0x1800356f5  call    cs:__imp_GetLastError
0x1800356fb  lea     r9, [rsp+2C0h+pszSrc]
0x180035700  lea     r8, aCreatepathUnab_2; "CreatePath: Unable to create parent dir"...
0x180035707  jmp     short loc_18003576F
0x180035709  mov     rcx, rdi; lpPathName
0x18003570c  call    cs:__imp_CreateDirectoryW
0x180035712  xor     r15d, r15d
0x180035715  test    eax, eax
0x180035717  jnz     short loc_180035786
0x180035719  call    cs:__imp_GetLastError
0x18003571f  mov     ebx, eax
0x180035721  cmp     eax, 0B7h
0x180035726  jz      short loc_180035734
0x180035728  mov     r9, rdi
0x18003572b  lea     r8, aCreatepathUnab_1; "CreatePath: Unable to create [%s]; GLE "...
0x180035732  jmp     short loc_180035771
0x180035734  mov     rcx, rdi; lpFileName
0x180035737  call    cs:__imp_GetFileAttributesW
0x18003573d  cmp     eax, 0FFFFFFFFh
0x180035740  jz      short loc_18003575F
0x180035742  test    al, 10h
0x180035744  jz      short loc_18003574B
0x180035746  mov     ebx, r15d
0x180035749  jmp     short loc_180035786
0x18003574b  mov     dword ptr [rsp+2C0h+var_2A0], 0B7h
0x180035753  lea     r8, aCreatepathExis; "CreatePath: Existing path [%s] is not a"...
0x18003575a  mov     r9, rdi
0x18003575d  jmp     short loc_180035775
0x18003575f  call    cs:__imp_GetLastError
0x180035765  mov     r9, rdi
0x180035768  lea     r8, aCreatepathUnab_0; "CreatePath: Unable to get attributes fo"...
0x18003576f  mov     ebx, eax
0x180035771  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180035775  mov     edx, 3000000h
0x18003577a  lea     rcx, g_WdsLibLog
0x180035781  call    LibLog
0x180035786  call    cs:__imp_GetProcessHeap
0x18003578c  mov     r8, rdi; lpMem
0x18003578f  xor     edx, edx; dwFlags
0x180035791  mov     rcx, rax; hHeap
0x180035794  call    cs:__imp_HeapFree
0x18003579a  mov     r15, [rsp+2C0h+var_270]
0x18003579f  jmp     short loc_1800357A9
0x1800357a1  call    cs:__imp_GetLastError
0x1800357a7  mov     ebx, eax
0x1800357a9  mov     ecx, ebx; dwErrCode
0x1800357ab  call    cs:__imp_SetLastError
0x1800357b1  test    ebx, ebx
0x1800357b3  jz      short loc_1800357E1
0x1800357b5  jmp     short loc_1800357C2
0x1800357b7  mov     ecx, 57h ; 'W'; dwErrCode
0x1800357bc  call    cs:__imp_SetLastError
0x1800357c2  call    cs:__imp_GetLastError
0x1800357c8  lea     r8, [rsp+2C0h+pszSrc]
0x1800357cd  mov     ecx, 3
0x1800357d2  mov     r9d, eax
0x1800357d5  lea     rdx, aServicespacesF; "ServiceSpaces: Failed to create path %s"...
0x1800357dc  call    BfspLogMessage
0x1800357e1  mov     ebx, [rsp+2C0h+var_280]
0x1800357e5  mov     eax, 5Ch ; '\'
0x1800357ea  mov     edi, [rsp+2C0h+var_288]
0x1800357ee  mov     [rsp+r12+2C0h+pszSrc], ax
0x1800357f4  mov     r12d, [rsp+2C0h+var_284]
0x1800357f9  cmp     [rsp+2C0h+var_278], r14
0x1800357fe  jz      short loc_180035832
0x180035800  lea     rcx, [rsp+2C0h+pszSrc]
0x180035805  call    BfspFileExists
0x18003580a  test    eax, eax
0x18003580c  jz      short loc_180035832
0x18003580e  call    BfspGetFirmwareType
0x180035813  mov     rdx, [rsp+2C0h+var_278]
0x180035818  lea     rcx, [rsp+2C0h+pszSrc]
0x18003581d  mov     r8d, eax
0x180035820  call    BfspIsWindowsBinary
0x180035825  test    eax, eax
0x180035827  jnz     short loc_180035832
0x180035829  lea     rdx, aServicespacesS_0; "ServiceSpaces: Skipping non-Windows %s"
0x180035830  jmp     short loc_180035886
0x180035832  mov     r8d, 1
0x180035838  lea     rdx, [rsp+2C0h+pszSrc]
0x18003583d  mov     rcx, rsi; Str
0x180035840  call    BfspShouldFileBeCopied
0x180035845  test    eax, eax
0x180035847  jz      short loc_18003587F
0x180035849  lea     rdx, [rsp+2C0h+pszSrc]; LPCWSTR
0x18003584e  mov     rcx, rsi; lpFileName
0x180035851  call    BfspCopyFile
0x180035856  test    eax, eax
0x180035858  jnz     short loc_180035895
0x18003585a  call    cs:__imp_GetLastError
0x180035860  lea     r9, [rsp+2C0h+pszSrc]
0x180035865  mov     r8, rsi
0x180035868  lea     rdx, aServicespacesF_0; "ServiceSpaces: Failed to copy %s to %s."...
0x18003586f  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180035873  mov     ecx, 3
0x180035878  call    BfspLogMessage
0x18003587d  jmp     short loc_180035895
0x18003587f  lea     rdx, aServicespacesS; "ServiceSpaces: Skipping %s"
0x180035886  lea     r8, [rsp+2C0h+pszSrc]
0x18003588b  mov     ecx, 3
0x180035890  call    BfspLogMessage
0x180035895  inc     ebx
0x180035897  mov     [rsp+2C0h+var_280], ebx
0x18003589b  cmp     ebx, [r15+8]
0x18003589f  jb      loc_1800355B1
0x1800358a5  jmp     loc_1800354DA
0x1800358aa  mov     eax, 1
0x1800358af  mov     rcx, [rbp+1C0h+var_50]
0x1800358b6  xor     rcx, rsp; StackCookie
0x1800358b9  call    __security_check_cookie
0x1800358be  add     rsp, 288h
0x1800358c5  pop     r15
0x1800358c7  pop     r14
0x1800358c9  pop     r13
0x1800358cb  pop     r12
0x1800358cd  pop     rdi
0x1800358ce  pop     rsi
0x1800358cf  pop     rbx
0x1800358d0  pop     rbp
0x1800358d1  retn
0x1800358d2  call    __report_rangecheckfailure
```
