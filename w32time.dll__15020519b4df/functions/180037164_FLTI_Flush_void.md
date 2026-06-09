# FLTI_Flush(void)

- ea: `0x180037164`
- end: `0x18003741e`
- name: `?FLTI_Flush@@YAJXZ`
- size: `698`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180018e40`

## callees

- `0x180029b70`
- `0x180037164`
- `0x180037424`
- `0x180037458`
- `0x18004de04`
- `0x18004e520`
- `0x18004ea9c`
- `0x18004eb38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003735a`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800373bb`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003735a`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x1800373bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800371f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800371f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800373e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800373e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003724c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003724c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003721a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003721a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372ad`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003729d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003729d`

## pseudocode

```c
__int64 FLTI_Flush(void)
{
  signed int Current; // edi
  __int64 v1; // rbx
  _BYTE *v2; // rdx
  __int64 v3; // rdi
  signed int v4; // eax
  DWORD v5; // r14d
  HANDLE *v6; // rcx
  DWORD LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  volatile signed __int32 *v11; // rax
  unsigned int v13; // eax
  __int64 v14; // [rsp+30h] [rbp-68h] BYREF
  __int64 v15; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v16[24]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v17[24]; // [rsp+58h] [rbp-40h] BYREF
  int v18; // [rsp+70h] [rbp-28h]
  char v19; // [rsp+A0h] [rbp+8h]
  int v20; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+18h]

  AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(&v14, 0);
  AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(&v15, 0);
  Current = FLTI_GetCurrent(&v15);
  if ( Current < 0 )
    goto LABEL_29;
  v19 = 0;
  v1 = v15;
  v2 = *(_BYTE **)(v15 + 8);
  if ( !*v2 )
  {
LABEL_27:
    Current = 0;
    if ( !v19 )
      goto LABEL_29;
LABEL_28:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)_pflstate + 176));
    goto LABEL_29;
  }
  AutoPtr<FileLogBuffer>::operator=(&v14, v2 + 16);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 2 * v3) );
  *(_QWORD *)(*(_QWORD *)(v14 + 8) + 40LL) = CreateEventW(0, 1, 0, 0);
  if ( *(_QWORD *)(*(_QWORD *)(v14 + 8) + 40LL) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)_pflstate + 176));
    v5 = 2 * v3;
    v6 = (HANDLE *)_pflstate;
    *(_QWORD *)(*(_QWORD *)(v14 + 8) + 32LL) = *((_QWORD *)_pflstate + 6);
    while ( !WriteFile(
               v6[5],
               *(LPCVOID *)(*(_QWORD *)(v14 + 8) + 8LL),
               v5,
               0,
               (LPOVERLAPPED)(*(_QWORD *)(v14 + 8) + 16LL)) )
    {
      LastError = GetLastError();
      Current = LastError;
      if ( LastError != 8 )
      {
        if ( LastError == 997 )
          break;
        if ( LastError != 1784 )
          goto LABEL_15;
      }
      if ( !FLTI_FreeAsManyAsPossible() )
      {
LABEL_15:
        if ( Current > 0 )
          Current = (unsigned __int16)Current | 0x80070000;
        goto LABEL_28;
      }
      v6 = (HANDLE *)_pflstate;
    }
    v19 = 1;
    v8 = _pflstate;
    *((_QWORD *)_pflstate + 6) += v5;
    if ( v8[1] )
      v8[6] %= v8[1];
    AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(&v20, 0);
    AutoPtr<FileLogBuffer>::operator=(*(_QWORD *)(v1 + 8) + 16LL, &v20);
    AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(&v20);
    v21 = _set_se_translator(SeTransFunc);
    Current = 0;
    try
    {
      v9 = *(_QWORD *)(v1 + 8) + 24LL;
      v10 = *(_QWORD **)(*(_QWORD *)(v1 + 8) + 32LL);
      if ( v10 == *(_QWORD **)(*(_QWORD *)(v1 + 8) + 40LL) )
      {
        std::vector<AutoPtr<FileLogBuffer>,MyThrowingAllocator<AutoPtr<FileLogBuffer>>>::_Emplace_reallocate<AutoPtr<FileLogBuffer> const &>(
          v9,
          v10,
          &v14);
      }
      else
      {
        v11 = (volatile signed __int32 *)v14;
        *v10 = v14;
        if ( v11 )
          _InterlockedIncrement(v11);
        *(_QWORD *)(v9 + 8) += 8LL;
      }
    }
    catch ( SeException v17 )
    {
      v13 = v18;
      if ( v18 > 0 )
        v13 = (unsigned __int16)v18 | 0x80070000;
      v20 = v13;
      SeException::~SeException((SeException *)v17);
      Current = v20;
    }
    catch ( std::bad_alloc v16 )
    {
      v20 = -2147024882;
      SeException::~SeException((SeException *)v16);
      Current = v20;
    }
    catch ( ... )
    {
      v20 = -2147418113;
      Current = v20;
    }
    _set_se_translator(v21);
    if ( Current < 0 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v4 = GetLastError();
  Current = v4;
  if ( v4 > 0 )
    Current = (unsigned __int16)v4 | 0x80070000;
LABEL_29:
  AutoPtr<FileLogThreadInfo>::~AutoPtr<FileLogThreadInfo>(&v15);
  AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(&v14);
  return (unsigned int)Current;
}

```

## disassembly

```asm
0x180037164  mov     [rsp+arg_18], rbx
0x180037169  push    rsi
0x18003716a  push    rdi
0x18003716b  push    r14
0x18003716d  sub     rsp, 80h
0x180037174  xor     edx, edx
0x180037176  lea     rcx, [rsp+98h+var_68]
0x18003717b  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x180037180  nop
0x180037181  xor     edx, edx
0x180037183  lea     rcx, [rsp+98h+var_60]
0x180037188  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x18003718d  nop
0x18003718e  lea     rcx, [rsp+98h+var_60]
0x180037193  call    ?FLTI_GetCurrent@@YAJPEAV?$AutoPtr@UFileLogThreadInfo@@@@@Z; FLTI_GetCurrent(AutoPtr<FileLogThreadInfo> *)
0x180037198  mov     edi, eax
0x18003719a  xor     esi, esi
0x18003719c  test    eax, eax
0x18003719e  js      loc_1800373F2
0x1800371a4  mov     [rsp+98h+arg_0], sil
0x1800371ac  mov     rbx, [rsp+98h+var_60]
0x1800371b1  mov     rdx, [rbx+8]
0x1800371b5  cmp     [rdx], sil
0x1800371b8  jz      loc_1800373CB
0x1800371be  add     rdx, 10h
0x1800371c2  lea     rcx, [rsp+98h+var_68]
0x1800371c7  call    ??4?$AutoPtr@UFileLogBuffer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<FileLogBuffer>::operator=(AutoPtr<FileLogBuffer> const &)
0x1800371cc  mov     rax, [rsp+98h+var_68]
0x1800371d1  mov     rcx, [rax+8]
0x1800371d5  mov     rax, [rcx+8]
0x1800371d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800371dd  inc     rdi
0x1800371e0  cmp     [rax+rdi*2], si
0x1800371e4  jnz     short loc_1800371DD
0x1800371e6  xor     r9d, r9d; lpName
0x1800371e9  xor     r8d, r8d; bInitialState
0x1800371ec  lea     edx, [r9+1]; bManualReset
0x1800371f0  xor     ecx, ecx; lpEventAttributes
0x1800371f2  call    cs:__imp_CreateEventW
0x1800371f9  nop     dword ptr [rax+rax+00h]
0x1800371fe  mov     rcx, [rsp+98h+var_68]
0x180037203  mov     rdx, [rcx+8]
0x180037207  mov     [rdx+28h], rax
0x18003720b  mov     rax, [rsp+98h+var_68]
0x180037210  mov     rcx, [rax+8]
0x180037214  cmp     [rcx+28h], rsi
0x180037218  jnz     short loc_18003723E
0x18003721a  call    cs:__imp_GetLastError
0x180037221  nop     dword ptr [rax+rax+00h]
0x180037226  mov     edi, eax
0x180037228  test    eax, eax
0x18003722a  jle     loc_1800373F2
0x180037230  movzx   edi, ax
0x180037233  or      edi, 80070000h
0x180037239  jmp     loc_1800373F2
0x18003723e  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180037245  add     rcx, 0B0h; lpCriticalSection
0x18003724c  call    cs:__imp_EnterCriticalSection
0x180037253  nop     dword ptr [rax+rax+00h]
0x180037258  lea     r14d, [rdi+rdi]
0x18003725c  mov     rax, [rsp+98h+var_68]
0x180037261  mov     rdx, [rax+8]
0x180037265  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18003726c  mov     eax, [rcx+30h]
0x18003726f  mov     [rdx+20h], eax
0x180037272  mov     rax, [rcx+30h]
0x180037276  shr     rax, 20h
0x18003727a  mov     [rdx+24h], eax
0x18003727d  mov     rax, [rsp+98h+var_68]
0x180037282  mov     rdx, [rax+8]
0x180037286  lea     rax, [rdx+10h]
0x18003728a  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x18003728f  xor     r9d, r9d; lpNumberOfBytesWritten
0x180037292  mov     r8d, r14d; nNumberOfBytesToWrite
0x180037295  mov     rdx, [rdx+8]; lpBuffer
0x180037299  mov     rcx, [rcx+28h]; hFile
0x18003729d  call    cs:__imp_WriteFile
0x1800372a4  nop     dword ptr [rax+rax+00h]
0x1800372a9  test    eax, eax
0x1800372ab  jnz     short loc_1800372F6
0x1800372ad  call    cs:__imp_GetLastError
0x1800372b4  nop     dword ptr [rax+rax+00h]
0x1800372b9  mov     edi, eax
0x1800372bb  cmp     eax, 8
0x1800372be  jz      short loc_1800372CE
0x1800372c0  cmp     eax, 3E5h
0x1800372c5  jz      short loc_1800372F6
0x1800372c7  cmp     eax, 6F8h
0x1800372cc  jnz     short loc_1800372E0
0x1800372ce  call    ?FLTI_FreeAsManyAsPossible@@YA_NXZ; FLTI_FreeAsManyAsPossible(void)
0x1800372d3  test    al, al
0x1800372d5  jz      short loc_1800372E0
0x1800372d7  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800372de  jmp     short loc_18003727D
0x1800372e0  test    edi, edi
0x1800372e2  jle     loc_1800373D7
0x1800372e8  movzx   edi, di
0x1800372eb  or      edi, 80070000h
0x1800372f1  jmp     loc_1800373D7
0x1800372f6  mov     [rsp+98h+arg_0], 1
0x1800372fe  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180037305  mov     eax, r14d
0x180037308  add     [rcx+30h], rax
0x18003730c  cmp     [rcx+8], rsi
0x180037310  jz      short loc_180037320
0x180037312  xor     edx, edx
0x180037314  mov     rax, [rcx+30h]
0x180037318  div     qword ptr [rcx+8]
0x18003731c  mov     [rcx+30h], rdx
0x180037320  xor     edx, edx
0x180037322  lea     rcx, [rsp+98h+arg_8]
0x18003732a  call    ??0?$AutoPtr@UFileLogThreadInfo@@@@QEAA@PEAUFileLogThreadInfo@@@Z; AutoPtr<FileLogThreadInfo>::AutoPtr<FileLogThreadInfo>(FileLogThreadInfo *)
0x18003732f  nop
0x180037330  mov     rcx, [rbx+8]
0x180037334  add     rcx, 10h
0x180037338  lea     rdx, [rsp+98h+arg_8]
0x180037340  call    ??4?$AutoPtr@UFileLogBuffer@@@@QEAAAEAV0@AEBV0@@Z; AutoPtr<FileLogBuffer>::operator=(AutoPtr<FileLogBuffer> const &)
0x180037345  nop
0x180037346  lea     rcx, [rsp+98h+arg_8]
0x18003734e  call    ??1?$AutoPtr@UFileLogBuffer@@@@QEAA@XZ; AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(void)
0x180037353  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18003735a  call    cs:__imp__set_se_translator
0x180037361  nop     dword ptr [rax+rax+00h]
0x180037366  mov     [rsp+98h+arg_10], rax
0x18003736e  mov     edi, esi
0x180037370  mov     rcx, [rbx+8]
0x180037374  add     rcx, 18h
0x180037378  mov     rdx, [rcx+8]
0x18003737c  cmp     rdx, [rcx+10h]
0x180037380  jz      short loc_180037399
0x180037382  mov     rax, [rsp+98h+var_68]
0x180037387  mov     [rdx], rax
0x18003738a  test    rax, rax
0x18003738d  jz      short loc_180037392
0x18003738f  lock inc dword ptr [rax]
0x180037392  add     qword ptr [rcx+8], 8
0x180037397  jmp     short loc_1800373A4
0x180037399  lea     r8, [rsp+98h+var_68]
0x18003739e  call    ??$_Emplace_reallocate@AEBV?$AutoPtr@UFileLogBuffer@@@@@?$vector@V?$AutoPtr@UFileLogBuffer@@@@V?$MyThrowingAllocator@V?$AutoPtr@UFileLogBuffer@@@@@@@std@@AEAAPEAV?$AutoPtr@UFileLogBuffer@@@@QEAV2@AEBV2@@Z; std::vector<AutoPtr<FileLogBuffer>,MyThrowingAllocator<AutoPtr<FileLogBuffer>>>::_Emplace_reallocate<AutoPtr<FileLogBuffer> const &>(AutoPtr<FileLogBuffer> * const,AutoPtr<FileLogBuffer> const &)
0x1800373a3  nop
0x1800373a4  jmp     short loc_1800373B3
0x1800373a6  jmp     short loc_1800373AA
0x1800373a8  jmp     short $+2
0x1800373aa  xor     esi, esi
0x1800373ac  mov     edi, [rsp+98h+arg_8]
0x1800373b3  mov     rcx, [rsp+98h+arg_10]
0x1800373bb  call    cs:__imp__set_se_translator
0x1800373c2  nop     dword ptr [rax+rax+00h]
0x1800373c7  test    edi, edi
0x1800373c9  js      short loc_1800373D7
0x1800373cb  mov     edi, esi
0x1800373cd  cmp     [rsp+98h+arg_0], sil
0x1800373d5  jz      short loc_1800373F2
0x1800373d7  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x1800373de  add     rcx, 0B0h; lpCriticalSection
0x1800373e5  call    cs:__imp_LeaveCriticalSection
0x1800373ec  nop     dword ptr [rax+rax+00h]
0x1800373f1  nop
0x1800373f2  lea     rcx, [rsp+98h+var_60]
0x1800373f7  call    ??1?$AutoPtr@UFileLogThreadInfo@@@@QEAA@XZ; AutoPtr<FileLogThreadInfo>::~AutoPtr<FileLogThreadInfo>(void)
0x1800373fc  nop
0x1800373fd  lea     rcx, [rsp+98h+var_68]
0x180037402  call    ??1?$AutoPtr@UFileLogBuffer@@@@QEAA@XZ; AutoPtr<FileLogBuffer>::~AutoPtr<FileLogBuffer>(void)
0x180037407  mov     eax, edi
0x180037409  mov     rbx, [rsp+98h+arg_18]
0x180037411  add     rsp, 80h
0x180037418  pop     r14
0x18003741a  pop     rdi
0x18003741b  pop     rsi
0x18003741c  retn
```
