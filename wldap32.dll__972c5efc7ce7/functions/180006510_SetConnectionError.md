# SetConnectionError

- ea: `0x180006510`
- end: `0x180006b18`
- name: `SetConnectionError`
- size: `1544`
- prototype: ``
- caller_count: `104`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800013c0`
- `0x180003840`
- `0x180004740`
- `0x180004e60`
- `0x180005170`
- `0x1800057a0`
- `0x180006d80`
- `0x18000a358`
- `0x18000b990`
- `0x18000bbf0`
- `0x18000bf40`
- `0x18000e0d0`
- `0x1800112b0`
- `0x1800153c0`
- `0x180015640`
- `0x180015bd8`
- `0x18001611c`
- `0x180016360`
- `0x1800164a0`
- `0x180017780`
- `0x1800188d0`
- `0x180018cc0`
- `0x180019f88`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18001d470`
- `0x18001da40`
- `0x18001de00`
- `0x18001f1d0`
- `0x180021454`
- `0x180026b50`
- `0x180028a60`
- `0x180029e70`
- `0x18002a4f0`
- `0x18002ab9c`
- `0x18002abe0`
- `0x18002b754`
- `0x18002c860`
- `0x18002c940`
- `0x18002ca20`
- `0x18002d1a8`
- `0x1800308f8`
- `0x180038678`
- `0x180039f4c`
- `0x18003a274`
- `0x18003a640`
- `0x18003a750`
- `0x18003a8b0`
- `0x18003a9b0`
- `0x18003abb0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000da50`
- `0x18000dee8`
- `0x18001ce90`
- `0x180032ee4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000686c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006925`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000686c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006925`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006579`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006599`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006599`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006995`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000671e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000671e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800068b4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000667c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000667c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000663d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000663d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800066eb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800067a2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800066eb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800067a2`

## pseudocode

```c
void __fastcall SetConnectionError(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rdi
  CHAR *lpMultiByteStr; // r15
  PCHAR v6; // rcx
  _DWORD *Value; // rsi
  _DWORD *v8; // rax
  __int64 v9; // r14
  const WCHAR *v10; // r8
  unsigned int v11; // eax
  int cbMultiByte; // ebp
  unsigned int v13; // r12d
  int v14; // ecx
  unsigned int v15; // eax
  int j; // esi
  __int64 v17; // r15
  unsigned int StringW; // eax
  unsigned int v19; // edx
  int i; // esi
  unsigned __int64 v21; // rbp
  unsigned int v22; // r13d
  WCHAR *v23; // rax
  WCHAR *v24; // r14
  int v25; // ecx
  unsigned int v26; // eax
  __int64 Buffer; // [rsp+80h] [rbp+8h] BYREF
  __int64 cchBufferMax; // [rsp+90h] [rbp+18h]

  cchBufferMax = a3;
  v4 = a2;
  if ( GlobalTlsLastErrorIndex != -1 )
  {
    Value = TlsGetValue(GlobalTlsLastErrorIndex);
    if ( !Value )
    {
      v8 = (_DWORD *)ldapMalloc(16, 1817471076);
      Value = v8;
      if ( !v8 )
        goto LABEL_2;
      TlsSetValue(GlobalTlsLastErrorIndex, v8);
    }
    *Value = v4;
  }
LABEL_2:
  if ( !a1 )
    return;
  lpMultiByteStr = 0;
  *(_DWORD *)(a1 + 1020) = v4;
  if ( (unsigned int)v4 > 0x61 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
      LDAPClientPrint(0x8000000, "ldap SetConnectionError does not have text for message 0x%x.\n", v4);
    v6 = ldap_err2string(0x50u);
    goto LABEL_9;
  }
  EnterCriticalSection(&LoadResLock);
  if ( LdapErrorStringsW )
  {
    LeaveCriticalSection(&LoadResLock);
  }
  else
  {
    Buffer = 0;
    LdapErrorStringsW = ldapMalloc(784, 1920091468);
    if ( !LdapErrorStringsW )
    {
LABEL_31:
      FreeErrorStringTableW();
      goto LABEL_32;
    }
    for ( i = 0; i < 98; ++i )
    {
      v17 = 8LL * i;
      if ( !*(_QWORD *)(v17 + LdapErrorStringsW) )
      {
        StringW = LoadStringW(GlobalLdapDllInstance, i + 1000, (LPWSTR)&Buffer, 0);
        if ( StringW )
        {
          v19 = StringW + 1;
          LODWORD(cchBufferMax) = StringW + 1;
          if ( StringW + 1 >= StringW )
          {
            v21 = 2LL * v19;
            if ( v21 <= 0xFFFFFFFF )
            {
              v22 = v21 + 8;
              if ( (int)v21 + 8 < (unsigned int)v21 )
              {
                v24 = 0;
                v22 = -1;
              }
              else
              {
                v23 = (WCHAR *)HeapAlloc(LdapHeap, 8u, v22);
                v19 = cchBufferMax;
                v24 = v23;
              }
              v25 = g_fTracingOn;
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
              {
                LDAPClientPrint(
                  8,
                  "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                  v22,
                  (_DWORD)v24,
                  1920091468);
                v25 = g_fTracingOn;
                v19 = cchBufferMax;
              }
              v26 = LdapAllocatedHeap;
              if ( v24 )
              {
                *(_DWORD *)v24 = 1920091468;
                *((_DWORD *)v24 + 1) = v21;
                v24 += 4;
                v26 += v21;
                LdapAllocatedHeap = v26;
              }
              if ( v25 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
              {
                LDAPClientPrint(
                  8,
                  "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                  v21,
                  (_DWORD)v24,
                  1920091468,
                  v26);
                v19 = cchBufferMax;
              }
              *(_QWORD *)(v17 + LdapErrorStringsW) = v24;
              if ( !v24 )
              {
                lpMultiByteStr = 0;
                goto LABEL_31;
              }
              LoadStringW(GlobalLdapDllInstance, i + 1000, v24, v19);
            }
          }
        }
      }
    }
    LeaveCriticalSection(&LoadResLock);
    lpMultiByteStr = 0;
  }
  EnterCriticalSection(&LoadResLock);
  if ( LdapErrorStrings )
  {
LABEL_7:
    LeaveCriticalSection(&LoadResLock);
    v6 = (PCHAR)MultiByteStr;
    if ( *(_QWORD *)(8 * v4 + LdapErrorStrings) )
    {
      _mm_lfence();
      v6 = *(PCHAR *)(8 * v4 + LdapErrorStrings);
    }
    goto LABEL_9;
  }
  LdapErrorStrings = ldapMalloc(784, 1920091468);
  if ( LdapErrorStrings )
  {
    for ( j = 0; j < 98; ++j )
    {
      v9 = 8LL * j;
      if ( !*(_QWORD *)(v9 + LdapErrorStrings) )
      {
        v10 = *(const WCHAR **)(v9 + LdapErrorStringsW);
        if ( v10 )
        {
          v11 = WideCharToMultiByte(0, 0x400u, v10, -1, 0, 0, 0, 0);
          cbMultiByte = v11;
          if ( v11 > 1 )
          {
            v13 = v11 + 8;
            if ( v11 + 8 < v11 )
              v13 = -1;
            else
              lpMultiByteStr = (CHAR *)HeapAlloc(LdapHeap, 8u, v13);
            v14 = g_fTracingOn;
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            {
              LDAPClientPrint(
                8,
                "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                v13,
                (_DWORD)lpMultiByteStr,
                1920091468);
              v14 = g_fTracingOn;
            }
            v15 = LdapAllocatedHeap;
            if ( lpMultiByteStr )
            {
              *(_DWORD *)lpMultiByteStr = 1920091468;
              *((_DWORD *)lpMultiByteStr + 1) = cbMultiByte;
              lpMultiByteStr += 8;
              v15 += cbMultiByte;
              LdapAllocatedHeap = v15;
            }
            if ( v14 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
              LDAPClientPrint(
                8,
                "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                cbMultiByte,
                (_DWORD)lpMultiByteStr,
                1920091468,
                v15);
            *(_QWORD *)(v9 + LdapErrorStrings) = lpMultiByteStr;
            if ( !lpMultiByteStr )
              goto LABEL_29;
            WideCharToMultiByte(0, 0x400u, *(LPCWCH *)(v9 + LdapErrorStringsW), -1, lpMultiByteStr, cbMultiByte, 0, 0);
            lpMultiByteStr = 0;
          }
        }
      }
    }
    goto LABEL_7;
  }
LABEL_29:
  FreeErrorStringTable();
LABEL_32:
  LeaveCriticalSection(&LoadResLock);
  v6 = (PCHAR)MultiByteStr;
LABEL_9:
  *(_QWORD *)(a1 + 1032) = v6;
  *(_QWORD *)(a1 + 1024) = lpMultiByteStr;
  if ( !*v6 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
      LDAPClientPrint(0x8000000, "ldap SetConnectionError does not have text for message 0x%x.\n", v4);
    *(_QWORD *)(a1 + 1032) = ldap_err2string(0x50u);
  }
}

```

## disassembly

```asm
0x180006510  mov     [rsp+cchBufferMax], r8
0x180006515  push    rbx
0x180006516  push    rsi
0x180006517  push    rdi
0x180006518  push    r13
0x18000651a  sub     rsp, 58h
0x18000651e  mov     rbx, rcx
0x180006521  mov     edi, edx
0x180006523  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180006529  mov     r13d, 0FFFFFFFFh
0x18000652f  cmp     ecx, r13d
0x180006532  jnz     loc_18000663D
0x180006538  test    rbx, rbx
0x18000653b  jz      loc_180006632
0x180006541  mov     [rsp+78h+var_38], r15
0x180006546  xor     r15d, r15d
0x180006549  mov     [rbx+3FCh], edi
0x18000654f  test    edi, edi
0x180006551  js      loc_180006A8A
0x180006557  cmp     edi, 62h ; 'b'
0x18000655a  jnb     loc_180006A8A
0x180006560  mov     [rsp+78h+arg_8], rbp
0x180006568  lea     rcx, LoadResLock; lpCriticalSection
0x18000656f  mov     [rsp+78h+var_28], r12
0x180006574  mov     [rsp+78h+var_30], r14
0x180006579  call    cs:__imp_EnterCriticalSection
0x180006580  nop     dword ptr [rax+rax+00h]
0x180006585  cmp     cs:LdapErrorStringsW, r15
0x18000658c  jz      loc_1800069A9
0x180006592  lea     rcx, LoadResLock; lpCriticalSection
0x180006599  call    cs:__imp_LeaveCriticalSection
0x1800065a0  nop     dword ptr [rax+rax+00h]
0x1800065a5  lea     rcx, LoadResLock; lpCriticalSection
0x1800065ac  call    cs:__imp_EnterCriticalSection
0x1800065b3  nop     dword ptr [rax+rax+00h]
0x1800065b8  cmp     cs:LdapErrorStrings, 0
0x1800065c0  jz      loc_180006A21
0x1800065c6  lea     rcx, LoadResLock; lpCriticalSection
0x1800065cd  call    cs:__imp_LeaveCriticalSection
0x1800065d4  nop     dword ptr [rax+rax+00h]
0x1800065d9  mov     rax, cs:LdapErrorStrings
0x1800065e0  lea     rdx, ds:0[rdi*8]
0x1800065e8  lea     rcx, MultiByteStr
0x1800065ef  cmp     qword ptr [rdx+rax], 0
0x1800065f4  jz      short loc_180006604
0x1800065f6  lfence
0x1800065f9  mov     rax, cs:LdapErrorStrings
0x180006600  mov     rcx, [rdx+rax]
0x180006604  mov     r14, [rsp+78h+var_30]
0x180006609  mov     r12, [rsp+78h+var_28]
0x18000660e  mov     rbp, [rsp+78h+arg_8]
0x180006616  mov     [rbx+408h], rcx
0x18000661d  mov     [rbx+400h], r15
0x180006624  cmp     byte ptr [rcx], 0
0x180006627  mov     r15, [rsp+78h+var_38]
0x18000662c  jz      loc_180006ACF
0x180006632  add     rsp, 58h
0x180006636  pop     r13
0x180006638  pop     rdi
0x180006639  pop     rsi
0x18000663a  pop     rbx
0x18000663b  retn
0x18000663d  call    cs:__imp_TlsGetValue
0x180006644  nop     dword ptr [rax+rax+00h]
0x180006649  mov     rsi, rax
0x18000664c  test    rax, rax
0x18000664f  jz      short loc_180006658
0x180006651  mov     [rsi], edi
0x180006653  jmp     loc_180006538
0x180006658  mov     edx, 6C546864h
0x18000665d  mov     ecx, 10h
0x180006662  call    ldapMalloc
0x180006667  mov     rsi, rax
0x18000666a  test    rax, rax
0x18000666d  jz      loc_180006538
0x180006673  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180006679  mov     rdx, rax; lpTlsValue
0x18000667c  call    cs:__imp_TlsSetValue
0x180006683  nop     dword ptr [rax+rax+00h]
0x180006688  jmp     short loc_180006651
0x180006690  cmp     esi, 62h ; 'b'
0x180006693  jge     loc_1800065C6
0x180006699  movsxd  rax, esi
0x18000669c  lea     r14, ds:0[rax*8]
0x1800066a4  mov     rax, cs:LdapErrorStrings
0x1800066ab  cmp     qword ptr [r14+rax], 0
0x1800066b0  jnz     loc_1800067B1
0x1800066b6  mov     rax, cs:LdapErrorStringsW
0x1800066bd  mov     r8, [r14+rax]; lpWideCharStr
0x1800066c1  test    r8, r8
0x1800066c4  jz      loc_1800067B1
0x1800066ca  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800066cf  mov     edx, 400h; dwFlags
0x1800066d4  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x1800066d9  xor     ecx, ecx; CodePage
0x1800066db  mov     [rsp+78h+cbMultiByte], r15d; cbMultiByte
0x1800066e0  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800066e6  mov     [rsp+78h+lpMultiByteStr], r15; lpMultiByteStr
0x1800066eb  call    cs:__imp_WideCharToMultiByte
0x1800066f2  nop     dword ptr [rax+rax+00h]
0x1800066f7  mov     ebp, eax
0x1800066f9  cmp     eax, 1
0x1800066fc  jbe     loc_1800067B1
0x180006702  lea     r12d, [rax+8]
0x180006706  cmp     r12d, eax
0x180006709  jb      loc_1800067B8
0x18000670f  mov     rcx, cs:LdapHeap; hHeap
0x180006716  mov     edx, 8; dwFlags
0x18000671b  mov     r8d, r12d; dwBytes
0x18000671e  call    cs:__imp_HeapAlloc
0x180006725  nop     dword ptr [rax+rax+00h]
0x18000672a  mov     r15, rax
0x18000672d  mov     ecx, cs:g_fTracingOn
0x180006733  test    ecx, ecx
0x180006735  jnz     loc_1800067EE
0x18000673b  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180006741  test    r15, r15
0x180006744  jz      short loc_18000675D
0x180006746  mov     dword ptr [r15], 7272454Ch
0x18000674d  mov     [r15+4], ebp
0x180006751  add     r15, 8
0x180006755  add     eax, ebp
0x180006757  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18000675d  test    ecx, ecx
0x18000675f  jnz     loc_180006A48
0x180006765  mov     rax, cs:LdapErrorStrings
0x18000676c  mov     [r14+rax], r15
0x180006770  test    r15, r15
0x180006773  jz      short loc_1800067C0
0x180006775  mov     r8, cs:LdapErrorStringsW
0x18000677c  xor     eax, eax
0x18000677e  mov     [rsp+78h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180006783  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180006789  mov     [rsp+78h+lpDefaultChar], rax; lpDefaultChar
0x18000678e  mov     edx, 400h; dwFlags
0x180006793  mov     [rsp+78h+cbMultiByte], ebp; cbMultiByte
0x180006797  xor     ecx, ecx; CodePage
0x180006799  mov     r8, [r14+r8]; lpWideCharStr
0x18000679d  mov     [rsp+78h+lpMultiByteStr], r15; lpMultiByteStr
0x1800067a2  call    cs:__imp_WideCharToMultiByte
0x1800067a9  nop     dword ptr [rax+rax+00h]
0x1800067ae  xor     r15d, r15d
0x1800067b1  inc     esi
0x1800067b3  jmp     loc_180006690
0x1800067b8  mov     r12d, r13d
0x1800067bb  jmp     loc_18000672D
0x1800067c0  call    FreeErrorStringTable
0x1800067c5  jmp     short loc_1800067CF
0x1800067c7  xor     r15d, r15d
0x1800067ca  call    FreeErrorStringTableW
0x1800067cf  lea     rcx, LoadResLock; lpCriticalSection
0x1800067d6  call    cs:__imp_LeaveCriticalSection
0x1800067dd  nop     dword ptr [rax+rax+00h]
0x1800067e2  lea     rcx, MultiByteStr
0x1800067e9  jmp     loc_180006604
0x1800067ee  cmp     cs:g_fProviderEnabled, 0
0x1800067f5  jz      loc_18000673B
0x1800067fb  test    byte ptr cs:g_ulTraceFlags, 8
0x180006802  jz      loc_18000673B
0x180006808  mov     r9, r15
0x18000680b  mov     dword ptr [rsp+78h+lpMultiByteStr], 7272454Ch
0x180006813  mov     r8d, r12d
0x180006816  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18000681d  mov     ecx, 8
0x180006822  call    LDAPClientPrint
0x180006827  mov     ecx, cs:g_fTracingOn
0x18000682d  jmp     loc_18000673B
0x180006832  cmp     esi, 62h ; 'b'
0x180006835  jge     loc_18000698E
0x18000683b  movsxd  rax, esi
0x18000683e  lea     r15, ds:0[rax*8]
0x180006846  mov     rax, cs:LdapErrorStringsW
0x18000684d  cmp     qword ptr [r15+rax], 0
0x180006852  jnz     short loc_18000688A
0x180006854  mov     rcx, cs:GlobalLdapDllInstance; hInstance
0x18000685b  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180006863  xor     r9d, r9d; cchBufferMax
0x180006866  lea     edx, [rsi+3E8h]; uID
0x18000686c  call    cs:__imp_LoadStringW
0x180006873  nop     dword ptr [rax+rax+00h]
0x180006878  test    eax, eax
0x18000687a  jz      short loc_18000688A
0x18000687c  lea     edx, [rax+1]
0x18000687f  mov     dword ptr [rsp+78h+cchBufferMax], edx
0x180006886  cmp     edx, eax
0x180006888  jnb     short loc_18000688E
0x18000688a  inc     esi
0x18000688c  jmp     short loc_180006832
0x18000688e  mov     ebp, edx
0x180006890  add     rbp, rbp
0x180006893  cmp     rbp, r13
0x180006896  ja      short loc_18000688A
0x180006898  lea     r13d, [rbp+8]
0x18000689c  cmp     r13d, ebp
0x18000689f  jb      loc_18000693C
0x1800068a5  mov     rcx, cs:LdapHeap; hHeap
0x1800068ac  mov     edx, 8; dwFlags
0x1800068b1  mov     r8d, r13d; dwBytes
0x1800068b4  call    cs:__imp_HeapAlloc
0x1800068bb  nop     dword ptr [rax+rax+00h]
0x1800068c0  mov     edx, dword ptr [rsp+78h+cchBufferMax]
0x1800068c7  mov     r14, rax
0x1800068ca  mov     ecx, cs:g_fTracingOn
0x1800068d0  test    ecx, ecx
0x1800068d2  jnz     short loc_180006947
0x1800068d4  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x1800068da  test    r14, r14
0x1800068dd  jz      short loc_1800068F6
0x1800068df  mov     dword ptr [r14], 7272454Ch
0x1800068e6  mov     [r14+4], ebp
0x1800068ea  add     r14, 8
0x1800068ee  add     eax, ebp
0x1800068f0  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x1800068f6  test    ecx, ecx
0x1800068f8  jnz     loc_1800069D8
0x1800068fe  mov     rax, cs:LdapErrorStringsW
0x180006905  mov     [r15+rax], r14
0x180006909  test    r14, r14
0x18000690c  jz      loc_1800067C7
0x180006912  mov     rcx, cs:GlobalLdapDllInstance; hInstance
0x180006919  mov     r9d, edx; cchBufferMax
0x18000691c  lea     edx, [rsi+3E8h]; uID
0x180006922  mov     r8, r14; lpBuffer
0x180006925  call    cs:__imp_LoadStringW
0x18000692c  nop     dword ptr [rax+rax+00h]
0x180006931  mov     r13d, 0FFFFFFFFh
0x180006937  jmp     loc_18000688A
0x18000693c  xor     r14d, r14d
0x18000693f  mov     r13d, 0FFFFFFFFh
0x180006945  jmp     short loc_1800068CA
0x180006947  cmp     cs:g_fProviderEnabled, 0
0x18000694e  jz      short loc_1800068D4
0x180006950  test    byte ptr cs:g_ulTraceFlags, 8
0x180006957  jz      loc_1800068D4
0x18000695d  mov     r9, r14
0x180006960  mov     dword ptr [rsp+78h+lpMultiByteStr], 7272454Ch
0x180006968  mov     r8d, r13d
0x18000696b  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x180006972  mov     ecx, 8
0x180006977  call    LDAPClientPrint
0x18000697c  mov     ecx, cs:g_fTracingOn
0x180006982  mov     edx, dword ptr [rsp+78h+cchBufferMax]
0x180006989  jmp     loc_1800068D4
0x18000698e  lea     rcx, LoadResLock; lpCriticalSection
0x180006995  call    cs:__imp_LeaveCriticalSection
0x18000699c  nop     dword ptr [rax+rax+00h]
0x1800069a1  xor     r15d, r15d
0x1800069a4  jmp     loc_1800065A5
0x1800069a9  mov     edx, 7272454Ch
0x1800069ae  mov     [rsp+78h+Buffer], r15
0x1800069b6  mov     ecx, 310h
0x1800069bb  call    ldapMalloc
0x1800069c0  mov     cs:LdapErrorStringsW, rax
0x1800069c7  test    rax, rax
0x1800069ca  jz      loc_1800067CA
0x1800069d0  mov     esi, r15d
0x1800069d3  jmp     loc_180006832
0x1800069d8  cmp     cs:g_fProviderEnabled, 0
0x1800069df  jz      loc_1800068FE
0x1800069e5  test    byte ptr cs:g_ulTraceFlags, 8
0x1800069ec  jz      loc_1800068FE
0x1800069f2  mov     [rsp+78h+cbMultiByte], eax
0x1800069f6  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x1800069fd  mov     r9, r14
0x180006a00  mov     dword ptr [rsp+78h+lpMultiByteStr], 7272454Ch
0x180006a08  mov     r8d, ebp
0x180006a0b  mov     ecx, 8
0x180006a10  call    LDAPClientPrint
0x180006a15  mov     edx, dword ptr [rsp+78h+cchBufferMax]
0x180006a1c  jmp     loc_1800068FE
0x180006a21  mov     edx, 7272454Ch
0x180006a26  mov     ecx, 310h
0x180006a2b  call    ldapMalloc
0x180006a30  mov     cs:LdapErrorStrings, rax
0x180006a37  test    rax, rax
0x180006a3a  jz      loc_1800067C0
0x180006a40  mov     esi, r15d
0x180006a43  jmp     loc_180006690
0x180006a48  cmp     cs:g_fProviderEnabled, 0
0x180006a4f  jz      loc_180006765
0x180006a55  test    byte ptr cs:g_ulTraceFlags, 8
0x180006a5c  jz      loc_180006765
0x180006a62  mov     [rsp+78h+cbMultiByte], eax
0x180006a66  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x180006a6d  mov     r9, r15
0x180006a70  mov     dword ptr [rsp+78h+lpMultiByteStr], 7272454Ch
0x180006a78  mov     r8d, ebp
0x180006a7b  mov     ecx, 8
0x180006a80  call    LDAPClientPrint
0x180006a85  jmp     loc_180006765
0x180006a8a  cmp     cs:g_fTracingOn, r15d
0x180006a91  jz      short loc_180006ABD
0x180006a93  cmp     cs:g_fProviderEnabled, r15d
0x180006a9a  jz      short loc_180006ABD
0x180006a9c  test    cs:g_ulTraceFlags, 8000000h
0x180006aa7  jz      short loc_180006ABD
0x180006aa9  mov     r8d, edi
0x180006aac  lea     rdx, aLdapSetconnect; "ldap SetConnectionError does not have t"...
0x180006ab3  mov     ecx, 8000000h
0x180006ab8  call    LDAPClientPrint
  ... truncated ...
```
