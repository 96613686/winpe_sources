# BfspCopyFile

- ea: `0x180033eb0`
- end: `0x1800340f3`
- name: `BfspCopyFile`
- size: `579`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180032518`
- `0x18003379c`
- `0x1800348e0`
- `0x18003545c`

## callees

- `0x180031b50`
- `0x180033eb0`
- `0x180035ae0`
- `0x1800366b8`
- `0x180038b44`
- `0x180038c34`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800340b3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800340b3`
- `RPCRT4!UuidCreate` at `0x180033eef`
- `RPCRT4!UuidCreate` at `0x180033eef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033ffe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033f13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033ffe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033f24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033f24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003400c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003400c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800340bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034039`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033fb8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033ff8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033fb8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033ff8`

## string_xrefs

- `0x180033fdc`: `BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.`
- `0x180034071`: `BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspCopyFile(LPCWSTR lpFileName, LPCWSTR a2)
{
  const WCHAR *v2; // r14
  __int64 v4; // rax
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v7; // r12
  DWORD LastError; // eax
  HANDLE v9; // rax
  unsigned int v10; // edi
  unsigned int v11; // esi
  DWORD v12; // eax
  DWORD v13; // ebx
  DWORD v14; // ecx
  __int64 v16; // [rsp+20h] [rbp-69h]
  __int64 v17; // [rsp+28h] [rbp-61h]
  __int64 v18; // [rsp+30h] [rbp-59h]
  UUID Uuid; // [rsp+90h] [rbp+7h] BYREF

  v2 = lpFileName;
  Uuid = 0;
  UuidCreate(&Uuid);
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 2 * v4 + 80;
  ProcessHeap = GetProcessHeap();
  v7 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v5);
  if ( v7 )
  {
    StringCbPrintfW(
      v7,
      v5,
      L"%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      a2,
      Uuid.Data1,
      Uuid.Data2,
      Uuid.Data3,
      Uuid.Data4[0],
      Uuid.Data4[1],
      Uuid.Data4[2],
      Uuid.Data4[3],
      Uuid.Data4[4],
      Uuid.Data4[5],
      Uuid.Data4[6],
      Uuid.Data4[7]);
    if ( MoveFileExW(a2, v7, 0) && !DeleteFileEx2((__int64)v7, 0) )
    {
      LastError = GetLastError();
      BfspLogMessage(3, L"BfspCopyFile failed to delete temporary file (%s)! Last Error = %#x.", v7, LastError);
      MoveFileExW(v7, 0, 4u);
    }
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v7);
    v2 = lpFileName;
  }
  v10 = 0;
  do
  {
    v11 = CopyFileWithAttributesEx2(v2, a2, 0, 0, 0);
    if ( v11 )
      break;
    v12 = GetLastError();
    v13 = v12;
    if ( (v12 == 5 || v12 - 32 <= 1) && ((BfspPrintFileOwnerProcess(v2), v13 == 5) || v13 == 32) || v13 == 33 )
      BfspPrintFileOwnerProcess(a2);
    LODWORD(v18) = v13;
    ++v10;
    LODWORD(v17) = 60;
    LODWORD(v16) = v10;
    BfspLogMessage(4, L"BfspCopyFile(%s, %s) failed! (Attempt %d of %d) Last Error = %#x", v2, a2, v16, v17, v18);
    if ( v10 < 0x3C )
    {
      v14 = *((_DWORD *)BfspRetryWaitInMilliseconds + v10 / 0xA);
      if ( v14 )
        Sleep(v14);
    }
    SetLastError(v13);
  }
  while ( v10 < 0x3C );
  return v11;
}

```

## disassembly

```asm
0x180033eb0  mov     [rsp-8+arg_10], rbx
0x180033eb5  push    rbp
0x180033eb6  push    rsi
0x180033eb7  push    rdi
0x180033eb8  push    r12
0x180033eba  push    r13
0x180033ebc  push    r14
0x180033ebe  push    r15
0x180033ec0  lea     rbp, [rsp-27h]
0x180033ec5  sub     rsp, 0B0h
0x180033ecc  mov     rax, cs:__security_cookie
0x180033ed3  xor     rax, rsp
0x180033ed6  mov     [rbp+57h+var_40], rax
0x180033eda  mov     r14, rcx
0x180033edd  mov     [rbp+57h+var_58], rcx
0x180033ee1  xorps   xmm0, xmm0
0x180033ee4  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180033ee8  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180033eec  mov     r13, rdx
0x180033eef  call    cs:__imp_UuidCreate
0x180033ef5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033ef9  xor     r15d, r15d
0x180033efc  inc     rax
0x180033eff  cmp     [r13+rax*2+0], r15w
0x180033f05  jnz     short loc_180033EFC
0x180033f07  lea     rbx, ds:50h[rax*2]
0x180033f0f  mov     [rbp+57h+cbDest], rbx
0x180033f13  call    cs:__imp_GetProcessHeap
0x180033f19  mov     r8, rbx; dwBytes
0x180033f1c  mov     edx, 8; dwFlags
0x180033f21  mov     rcx, rax; hHeap
0x180033f24  call    cs:__imp_HeapAlloc
0x180033f2a  mov     r12, rax
0x180033f2d  test    rax, rax
0x180033f30  jz      loc_180034016
0x180033f36  movzx   ecx, [rbp+57h+Uuid.Data4+7]
0x180033f3a  movzx   r8d, [rbp+57h+Uuid.Data4+6]
0x180033f3f  movzx   r9d, [rbp+57h+Uuid.Data4+5]
0x180033f44  movzx   r10d, [rbp+57h+Uuid.Data4+4]
0x180033f49  movzx   r11d, [rbp+57h+Uuid.Data4+3]
0x180033f4e  movzx   ebx, [rbp+57h+Uuid.Data4+2]
0x180033f52  movzx   edi, [rbp+57h+Uuid.Data4+1]
0x180033f56  movzx   esi, [rbp+57h+Uuid.Data4]
0x180033f5a  movzx   r14d, [rbp+57h+Uuid.Data3]
0x180033f5f  movzx   r15d, [rbp+57h+Uuid.Data2]
0x180033f64  mov     eax, [rbp+57h+Uuid.Data1]
0x180033f67  mov     rdx, [rbp+57h+cbDest]; cbDest
0x180033f6b  mov     [rsp+0E0h+var_70], ecx
0x180033f6f  mov     rcx, r12; pszDest
0x180033f72  mov     [rsp+0E0h+var_78], r8d
0x180033f77  lea     r8, aWs8x4x4x2x2x2x; "%ws.{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x180033f7e  mov     [rsp+0E0h+var_80], r9d
0x180033f83  mov     r9, r13
0x180033f86  mov     [rsp+0E0h+var_88], r10d
0x180033f8b  mov     [rsp+0E0h+var_90], r11d
0x180033f90  mov     [rsp+0E0h+var_98], ebx
0x180033f94  mov     [rsp+0E0h+var_A0], edi
0x180033f98  mov     [rsp+0E0h+var_A8], esi
0x180033f9c  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x180033fa1  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x180033fa6  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180033faa  call    StringCbPrintfW
0x180033faf  xor     r8d, r8d; dwFlags
0x180033fb2  mov     rdx, r12; lpNewFileName
0x180033fb5  mov     rcx, r13; lpExistingFileName
0x180033fb8  call    cs:__imp_MoveFileExW
0x180033fbe  xor     r15d, r15d
0x180033fc1  test    eax, eax
0x180033fc3  jz      short loc_180033FFE
0x180033fc5  xor     edx, edx
0x180033fc7  mov     rcx, r12
0x180033fca  call    DeleteFileEx2
0x180033fcf  test    eax, eax
0x180033fd1  jnz     short loc_180033FFE
0x180033fd3  call    cs:__imp_GetLastError
0x180033fd9  mov     r8, r12
0x180033fdc  lea     rdx, aBfspcopyfileFa; "BfspCopyFile failed to delete temporary"...
0x180033fe3  mov     r9d, eax
0x180033fe6  lea     ecx, [r15+3]
0x180033fea  call    BfspLogMessage
0x180033fef  xor     edx, edx; lpNewFileName
0x180033ff1  lea     r8d, [r15+4]; dwFlags
0x180033ff5  mov     rcx, r12; lpExistingFileName
0x180033ff8  call    cs:__imp_MoveFileExW
0x180033ffe  call    cs:__imp_GetProcessHeap
0x180034004  mov     r8, r12; lpMem
0x180034007  xor     edx, edx; dwFlags
0x180034009  mov     rcx, rax; hHeap
0x18003400c  call    cs:__imp_HeapFree
0x180034012  mov     r14, [rbp+57h+var_58]
0x180034016  mov     edi, r15d
0x180034019  xor     r9d, r9d
0x18003401c  mov     [rsp+0E0h+var_C0], r15
0x180034021  xor     r8d, r8d
0x180034024  mov     rdx, r13
0x180034027  mov     rcx, r14
0x18003402a  call    CopyFileWithAttributesEx2
0x18003402f  mov     esi, eax
0x180034031  test    eax, eax
0x180034033  jnz     loc_1800340CA
0x180034039  call    cs:__imp_GetLastError
0x18003403f  mov     ebx, eax
0x180034041  cmp     eax, 5
0x180034044  jz      short loc_18003404E
0x180034046  lea     ecx, [rax-20h]
0x180034049  cmp     ecx, 1
0x18003404c  ja      short loc_180034060
0x18003404e  mov     rcx, r14; lpFileName
0x180034051  call    BfspPrintFileOwnerProcess
0x180034056  cmp     ebx, 5
0x180034059  jz      short loc_180034065
0x18003405b  cmp     ebx, 20h ; ' '
0x18003405e  jz      short loc_180034065
0x180034060  cmp     ebx, 21h ; '!'
0x180034063  jnz     short loc_18003406D
0x180034065  mov     rcx, r13; lpFileName
0x180034068  call    BfspPrintFileOwnerProcess
0x18003406d  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x180034071  lea     rdx, aBfspcopyfileSS; "BfspCopyFile(%s, %s) failed! (Attempt %"...
0x180034078  inc     edi
0x18003407a  mov     dword ptr [rsp+0E0h+var_B8], 3Ch ; '<'
0x180034082  mov     r9, r13
0x180034085  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180034089  mov     r8, r14
0x18003408c  mov     ecx, 4
0x180034091  call    BfspLogMessage
0x180034096  cmp     edi, 3Ch ; '<'
0x180034099  jnb     short loc_1800340B9
0x18003409b  mov     eax, 0CCCCCCCDh
0x1800340a0  lea     rcx, BfspRetryWaitInMilliseconds
0x1800340a7  mul     edi
0x1800340a9  shr     edx, 3
0x1800340ac  mov     ecx, [rcx+rdx*4]; dwMilliseconds
0x1800340af  test    ecx, ecx
0x1800340b1  jz      short loc_1800340B9
0x1800340b3  call    cs:__imp_Sleep
0x1800340b9  mov     ecx, ebx; dwErrCode
0x1800340bb  call    cs:__imp_SetLastError
0x1800340c1  cmp     edi, 3Ch ; '<'
0x1800340c4  jb      loc_180034019
0x1800340ca  mov     eax, esi
0x1800340cc  mov     rcx, [rbp+57h+var_40]
0x1800340d0  xor     rcx, rsp; StackCookie
0x1800340d3  call    __security_check_cookie
0x1800340d8  mov     rbx, [rsp+0E0h+arg_10]
0x1800340e0  add     rsp, 0B0h
0x1800340e7  pop     r15
0x1800340e9  pop     r14
0x1800340eb  pop     r13
0x1800340ed  pop     r12
0x1800340ef  pop     rdi
0x1800340f0  pop     rsi
0x1800340f1  pop     rbp
0x1800340f2  retn
```
