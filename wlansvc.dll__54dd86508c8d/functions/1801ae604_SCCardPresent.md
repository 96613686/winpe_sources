# SCCardPresent

- ea: `0x1801ae604`
- end: `0x1801ae7c6`
- name: `SCCardPresent`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18011dffc`

## callees

- `0x1801072f4`
- `0x18010801c`
- `0x1801ae604`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ae797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ae797`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae73a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae73a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ae789`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ae698`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ae74b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ae698`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ae74b`
- `ext-ms-win-wlan-scard-l1-1-0!SCardConnectW` at `0x1801ae6fd`
- `ext-ms-win-wlan-scard-l1-1-0!SCardConnectW` at `0x1801ae6fd`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x1801ae64c`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x1801ae64c`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x1801ae7a6`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x1801ae7a6`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x1801ae669`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x1801ae6bd`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x1801ae669`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x1801ae6bd`
- `ext-ms-win-wlan-scard-l1-1-0!SCardDisconnect` at `0x1801ae77e`
- `ext-ms-win-wlan-scard-l1-1-0!SCardDisconnect` at `0x1801ae77e`

## pseudocode

```c
__int64 __fastcall SCCardPresent(wchar_t **a1)
{
  WCHAR *v2; // rsi
  unsigned int v3; // edi
  DWORD v4; // r15d
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  __int64 v7; // rbx
  const WCHAR *v8; // r14
  __int64 v9; // rax
  HANDLE v10; // rax
  wchar_t *v11; // rax
  HANDLE v12; // rax
  SCARDHANDLE hCard[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcchReaders; // [rsp+88h] [rbp+48h] BYREF
  DWORD pdwActiveProtocol; // [rsp+90h] [rbp+50h] BYREF
  SCARDCONTEXT phContext; // [rsp+98h] [rbp+58h] BYREF

  pcchReaders = 0;
  v2 = 0;
  pdwActiveProtocol = 0;
  phContext = 0;
  hCard[0] = 0;
  if ( !(unsigned __int8)IsSCardEstablishContextPresent() )
    goto LABEL_17;
  v3 = SCardEstablishContext(0, 0, 0, &phContext);
  if ( v3 )
    goto LABEL_18;
  v3 = SCardListReadersW(phContext, 0, 0, &pcchReaders);
  if ( v3 )
    goto LABEL_18;
  if ( pcchReaders <= 2 )
  {
LABEL_17:
    v3 = -2146435049;
    goto LABEL_18;
  }
  v4 = 2 * pcchReaders;
  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v4);
  v2 = v6;
  if ( !v6 )
  {
LABEL_6:
    v3 = -2146435066;
    goto LABEL_18;
  }
  v3 = SCardListReadersW(phContext, 0, v6, &pcchReaders);
  if ( !v3 )
  {
    v7 = -1;
    v8 = v2;
    if ( *v2 )
    {
      while ( 1 )
      {
        v3 = SCardConnectW(phContext, v8, 2u, 3u, hCard, &pdwActiveProtocol);
        if ( !v3 )
          break;
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        v8 += v9 + 1;
        if ( !*v8 )
          goto LABEL_18;
      }
    }
    do
      ++v7;
    while ( v8[v7] );
    pcchReaders = v7 + 1;
    v10 = GetProcessHeap();
    v11 = (wchar_t *)HeapAlloc(v10, 8u, 2 * v4);
    *a1 = v11;
    if ( !v11 )
      goto LABEL_6;
    wcscpy_s(v11, pcchReaders, v8);
  }
LABEL_18:
  if ( hCard[0] )
    SCardDisconnect(hCard[0], 0);
  if ( v2 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v2);
  }
  if ( phContext )
    SCardReleaseContext(phContext);
  return v3;
}

```

## disassembly

```asm
0x1801ae604  mov     [rsp-38h+arg_0], rbx
0x1801ae609  push    rbp
0x1801ae60a  push    rsi
0x1801ae60b  push    rdi
0x1801ae60c  push    r12
0x1801ae60e  push    r13
0x1801ae610  push    r14
0x1801ae612  push    r15
0x1801ae614  mov     rbp, rsp
0x1801ae617  sub     rsp, 40h
0x1801ae61b  xor     r13d, r13d
0x1801ae61e  mov     r12, rcx
0x1801ae621  mov     [rbp+pcchReaders], r13d
0x1801ae625  mov     esi, r13d
0x1801ae628  mov     [rbp+arg_10], r13d
0x1801ae62c  mov     [rbp+phContext], r13
0x1801ae630  mov     [rbp+hCard], r13
0x1801ae634  call    IsSCardEstablishContextPresent
0x1801ae639  test    al, al
0x1801ae63b  jz      loc_1801AE76E
0x1801ae641  lea     r9, [rbp+phContext]; phContext
0x1801ae645  xor     r8d, r8d; pvReserved2
0x1801ae648  xor     edx, edx; pvReserved1
0x1801ae64a  xor     ecx, ecx; dwScope
0x1801ae64c  call    cs:__imp_SCardEstablishContext
0x1801ae652  mov     edi, eax
0x1801ae654  test    eax, eax
0x1801ae656  jnz     loc_1801AE773
0x1801ae65c  mov     rcx, [rbp+phContext]; hContext
0x1801ae660  lea     r9, [rbp+pcchReaders]; pcchReaders
0x1801ae664  xor     r8d, r8d; mszReaders
0x1801ae667  xor     edx, edx; mszGroups
0x1801ae669  call    cs:__imp_SCardListReadersW
0x1801ae66f  mov     edi, eax
0x1801ae671  test    eax, eax
0x1801ae673  jnz     loc_1801AE773
0x1801ae679  mov     eax, [rbp+pcchReaders]
0x1801ae67c  cmp     eax, 2
0x1801ae67f  jbe     loc_1801AE76E
0x1801ae685  lea     r15d, [rax+rax]
0x1801ae689  call    cs:__imp_GetProcessHeap
0x1801ae68f  mov     r8d, r15d; dwBytes
0x1801ae692  lea     edx, [rdi+8]; dwFlags
0x1801ae695  mov     rcx, rax; hHeap
0x1801ae698  call    cs:__imp_HeapAlloc
0x1801ae69e  mov     rsi, rax
0x1801ae6a1  test    rax, rax
0x1801ae6a4  jnz     short loc_1801AE6B0
0x1801ae6a6  mov     edi, 80100006h
0x1801ae6ab  jmp     loc_1801AE773
0x1801ae6b0  mov     rcx, [rbp+phContext]; hContext
0x1801ae6b4  lea     r9, [rbp+pcchReaders]; pcchReaders
0x1801ae6b8  mov     r8, rsi; mszReaders
0x1801ae6bb  xor     edx, edx; mszGroups
0x1801ae6bd  call    cs:__imp_SCardListReadersW
0x1801ae6c3  mov     edi, eax
0x1801ae6c5  test    eax, eax
0x1801ae6c7  jnz     loc_1801AE773
0x1801ae6cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801ae6d1  mov     r14, rsi
0x1801ae6d4  cmp     [rsi], r13w
0x1801ae6d8  jz      short loc_1801AE726
0x1801ae6da  mov     rcx, [rbp+phContext]; hContext
0x1801ae6de  lea     rax, [rbp+arg_10]
0x1801ae6e2  mov     [rsp+40h+pdwActiveProtocol], rax; pdwActiveProtocol
0x1801ae6e7  mov     r9d, 3; dwPreferredProtocols
0x1801ae6ed  lea     rax, [rbp+hCard]
0x1801ae6f1  mov     rdx, r14; szReader
0x1801ae6f4  mov     [rsp+40h+phCard], rax; phCard
0x1801ae6f9  lea     r8d, [r9-1]; dwShareMode
0x1801ae6fd  call    cs:__imp_SCardConnectW
0x1801ae703  mov     edi, eax
0x1801ae705  test    eax, eax
0x1801ae707  jz      short loc_1801AE726
0x1801ae709  mov     rax, rbx
0x1801ae70c  inc     rax
0x1801ae70f  cmp     [r14+rax*2], r13w
0x1801ae714  jnz     short loc_1801AE70C
0x1801ae716  lea     r14, [r14+rax*2]
0x1801ae71a  add     r14, 2
0x1801ae71e  cmp     [r14], r13w
0x1801ae722  jnz     short loc_1801AE6DA
0x1801ae724  jmp     short loc_1801AE773
0x1801ae726  inc     rbx
0x1801ae729  cmp     [r14+rbx*2], r13w
0x1801ae72e  jnz     short loc_1801AE726
0x1801ae730  lea     eax, [rbx+1]
0x1801ae733  mov     [rbp+pcchReaders], eax
0x1801ae736  lea     ebx, [r15+r15]
0x1801ae73a  call    cs:__imp_GetProcessHeap
0x1801ae740  mov     r8d, ebx; dwBytes
0x1801ae743  mov     edx, 8; dwFlags
0x1801ae748  mov     rcx, rax; hHeap
0x1801ae74b  call    cs:__imp_HeapAlloc
0x1801ae751  mov     [r12], rax
0x1801ae755  test    rax, rax
0x1801ae758  jz      loc_1801AE6A6
0x1801ae75e  mov     edx, [rbp+pcchReaders]; SizeInWords
0x1801ae761  mov     r8, r14; Source
0x1801ae764  mov     rcx, rax; Destination
0x1801ae767  call    wcscpy_s
0x1801ae76c  jmp     short loc_1801AE773
0x1801ae76e  mov     edi, 80100017h
0x1801ae773  mov     rcx, [rbp+hCard]; hCard
0x1801ae777  test    rcx, rcx
0x1801ae77a  jz      short loc_1801AE784
0x1801ae77c  xor     edx, edx; dwDisposition
0x1801ae77e  call    cs:__imp_SCardDisconnect
0x1801ae784  test    rsi, rsi
0x1801ae787  jz      short loc_1801AE79D
0x1801ae789  call    cs:__imp_GetProcessHeap
0x1801ae78f  mov     r8, rsi; lpMem
0x1801ae792  xor     edx, edx; dwFlags
0x1801ae794  mov     rcx, rax; hHeap
0x1801ae797  call    cs:__imp_HeapFree
0x1801ae79d  mov     rcx, [rbp+phContext]; hContext
0x1801ae7a1  test    rcx, rcx
0x1801ae7a4  jz      short loc_1801AE7AC
0x1801ae7a6  call    cs:__imp_SCardReleaseContext
0x1801ae7ac  mov     rbx, [rsp+40h+arg_0]
0x1801ae7b4  mov     eax, edi
0x1801ae7b6  add     rsp, 40h
0x1801ae7ba  pop     r15
0x1801ae7bc  pop     r14
0x1801ae7be  pop     r13
0x1801ae7c0  pop     r12
0x1801ae7c2  pop     rdi
0x1801ae7c3  pop     rsi
0x1801ae7c4  pop     rbp
0x1801ae7c5  retn
```
