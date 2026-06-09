# EcbDiskMeasure

- ea: `0x18004f1e8`
- end: `0x18004f3f1`
- name: `EcbDiskMeasure`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180062740`

## callees

- `0x180020ee8`
- `0x18004f1e8`
- `0x18004f3f8`
- `0x18004f55c`
- `0x18004f69c`
- `0x18007157c`
- `0x1800b2284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f235`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f3d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f3d0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f222`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f222`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18004f3b0`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18004f3b0`

## string_xrefs

- `0x18004f247`: `FATAL ERROR:  Could not CreateFile(%ws) error %d\n`

## pseudocode

```c
__int64 __fastcall EcbDiskMeasure(__int64 a1, _DWORD *a2)
{
  HANDLE FileW; // rax
  __int64 LastError; // rdi
  double v6; // xmm6_8
  __int64 v7; // rax
  double v8; // xmm0_8
  int v9; // edi
  void *v10; // rcx
  __int64 v12; // [rsp+80h] [rbp+8h] BYREF

  FileW = CreateFileW((LPCWSTR)(a1 + 32), 0x80000000, 3u, 0, 3u, 0x68000080u, 0);
  *(_QWORD *)(a1 + 560) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    EcbUtilsOut(1, "FATAL ERROR:  Could not CreateFile(%ws) error %d\n", a1 + 32, LastError);
  }
  else
  {
    *(_QWORD *)(a1 + 648) = *(_QWORD *)(a1 + 640);
    EcbDiskLogCompletion(a1, 0, 0);
    v6 = EcbUtilsDblTime();
    v12 = 0;
    v7 = 0;
    while ( v7 < 0x8000000 )
    {
      LODWORD(LastError) = EcbDiskStartRead(a1, &v12, 0x10000u);
      if ( (_DWORD)LastError )
        goto LABEL_20;
      v7 = v12 + 0x10000;
      v12 += 0x10000;
      if ( *a2 )
      {
LABEL_7:
        LODWORD(LastError) = 995;
        goto LABEL_20;
      }
    }
    while ( *(int *)(a1 + 664) > 0 )
    {
      LODWORD(LastError) = EcbDiskAwaitCompletion(a1);
      if ( (_DWORD)LastError )
        goto LABEL_20;
      if ( *a2 )
        goto LABEL_7;
    }
    v8 = EcbUtilsDblTime();
    v9 = 10;
    *(_DWORD *)(a1 + 696) = ((__int64)(*(_QWORD *)(a1 + 640) - *(_QWORD *)(a1 + 648)) >> 4) - 1;
    *(double *)(a1 + 704) = v8 - v6;
    do
    {
      EcbDiskLogCompletion(a1, 0, 0);
      --v9;
    }
    while ( v9 );
    *(_QWORD *)(a1 + 712) = *(_QWORD *)(a1 + 640);
    EcbDiskLogCompletion(a1, 0, 0);
    LODWORD(LastError) = EcbDiskExecuteLongSeekPattern(a1, EcbDiskExecuteLongSeekIters, a2);
    if ( !(_DWORD)LastError )
    {
      *(_DWORD *)(a1 + 720) = ((__int64)(*(_QWORD *)(a1 + 640) - *(_QWORD *)(a1 + 712)) >> 4) - 1;
      while ( *(int *)(a1 + 664) > 0 )
      {
        LODWORD(LastError) = EcbDiskAwaitCompletion(a1);
        if ( (_DWORD)LastError )
          goto LABEL_20;
      }
      LODWORD(LastError) = 0;
    }
  }
LABEL_20:
  v10 = *(void **)(a1 + 560);
  if ( v10 != (void *)-1LL )
  {
    CancelIo(v10);
    while ( *(int *)(a1 + 664) > 0 )
      EcbDiskAwaitCompletion(a1);
    CloseHandle(*(HANDLE *)(a1 + 560));
    *(_QWORD *)(a1 + 560) = -1;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004f1e8  mov     rax, rsp
0x18004f1eb  push    rbx
0x18004f1ec  push    rbp
0x18004f1ed  push    rsi
0x18004f1ee  push    rdi
0x18004f1ef  sub     rsp, 58h
0x18004f1f3  mov     qword ptr [rax-48h], 0
0x18004f1fb  mov     rbp, rdx
0x18004f1fe  mov     rbx, rcx
0x18004f201  mov     dword ptr [rax-50h], 68000080h
0x18004f208  mov     r8d, 3; dwShareMode
0x18004f20e  movaps  xmmword ptr [rax-38h], xmm6
0x18004f212  mov     edx, 80000000h; dwDesiredAccess
0x18004f217  mov     [rax-58h], r8d
0x18004f21b  add     rcx, 20h ; ' '; lpFileName
0x18004f21f  xor     r9d, r9d; lpSecurityAttributes
0x18004f222  call    cs:__imp_CreateFileW
0x18004f228  mov     [rbx+230h], rax
0x18004f22f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f233  jnz     short loc_18004F25A
0x18004f235  call    cs:__imp_GetLastError
0x18004f23b  lea     r8, [rbx+20h]
0x18004f23f  mov     ecx, 1
0x18004f244  mov     r9d, eax
0x18004f247  lea     rdx, aFatalErrorCoul_0; "FATAL ERROR:  Could not CreateFile(%ws)"...
0x18004f24e  mov     edi, eax
0x18004f250  call    EcbUtilsOut
0x18004f255  jmp     loc_18004F3A3
0x18004f25a  mov     rax, [rbx+280h]
0x18004f261  xor     r8d, r8d
0x18004f264  xor     edx, edx
0x18004f266  mov     [rbx+288h], rax
0x18004f26d  mov     rcx, rbx
0x18004f270  call    EcbDiskLogCompletion
0x18004f275  call    EcbUtilsDblTime
0x18004f27a  movaps  xmm6, xmm0
0x18004f27d  mov     [rsp+78h+arg_0], 0
0x18004f289  xor     eax, eax
0x18004f28b  mov     esi, 10000h
0x18004f290  cmp     rax, 8000000h
0x18004f296  jge     short loc_18004F2D7
0x18004f298  mov     r8d, esi
0x18004f29b  lea     rdx, [rsp+78h+arg_0]
0x18004f2a3  mov     rcx, rbx
0x18004f2a6  call    EcbDiskStartRead
0x18004f2ab  mov     edi, eax
0x18004f2ad  test    eax, eax
0x18004f2af  jnz     loc_18004F3A3
0x18004f2b5  mov     rax, [rsp+78h+arg_0]
0x18004f2bd  add     rax, rsi
0x18004f2c0  mov     [rsp+78h+arg_0], rax
0x18004f2c8  cmp     [rbp+0], edi
0x18004f2cb  jz      short loc_18004F290
0x18004f2cd  mov     edi, 3E3h
0x18004f2d2  jmp     loc_18004F3A3
0x18004f2d7  cmp     dword ptr [rbx+298h], 0
0x18004f2de  jle     short loc_18004F2F9
0x18004f2e0  mov     rcx, rbx
0x18004f2e3  call    EcbDiskAwaitCompletion
0x18004f2e8  mov     edi, eax
0x18004f2ea  test    eax, eax
0x18004f2ec  jnz     loc_18004F3A3
0x18004f2f2  cmp     [rbp+0], eax
0x18004f2f5  jz      short loc_18004F2D7
0x18004f2f7  jmp     short loc_18004F2CD
0x18004f2f9  call    EcbUtilsDblTime
0x18004f2fe  mov     rax, [rbx+280h]
0x18004f305  subsd   xmm0, xmm6
0x18004f309  sub     rax, [rbx+288h]
0x18004f310  mov     edi, 0Ah
0x18004f315  sar     rax, 4
0x18004f319  dec     eax
0x18004f31b  mov     [rbx+2B8h], eax
0x18004f321  movsd   qword ptr [rbx+2C0h], xmm0
0x18004f329  xor     r8d, r8d
0x18004f32c  xor     edx, edx
0x18004f32e  mov     rcx, rbx
0x18004f331  call    EcbDiskLogCompletion
0x18004f336  add     edi, 0FFFFFFFFh
0x18004f339  jnz     short loc_18004F329
0x18004f33b  mov     rax, [rbx+280h]
0x18004f342  xor     r8d, r8d
0x18004f345  xor     edx, edx
0x18004f347  mov     [rbx+2C8h], rax
0x18004f34e  mov     rcx, rbx
0x18004f351  call    EcbDiskLogCompletion
0x18004f356  mov     r8, rbp
0x18004f359  lea     rdx, EcbDiskExecuteLongSeekIters
0x18004f360  mov     rcx, rbx
0x18004f363  call    EcbDiskExecuteLongSeekPattern
0x18004f368  mov     edi, eax
0x18004f36a  test    eax, eax
0x18004f36c  jnz     short loc_18004F3A3
0x18004f36e  mov     rax, [rbx+280h]
0x18004f375  sub     rax, [rbx+2C8h]
0x18004f37c  sar     rax, 4
0x18004f380  dec     eax
0x18004f382  mov     [rbx+2D0h], eax
0x18004f388  cmp     dword ptr [rbx+298h], 0
0x18004f38f  jle     short loc_18004F3A1
0x18004f391  mov     rcx, rbx
0x18004f394  call    EcbDiskAwaitCompletion
0x18004f399  mov     edi, eax
0x18004f39b  test    eax, eax
0x18004f39d  jz      short loc_18004F388
0x18004f39f  jmp     short loc_18004F3A3
0x18004f3a1  xor     edi, edi
0x18004f3a3  mov     rcx, [rbx+230h]; hFile
0x18004f3aa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f3ae  jz      short loc_18004F3E1
0x18004f3b0  call    cs:__imp_CancelIo
0x18004f3b6  jmp     short loc_18004F3C0
0x18004f3b8  mov     rcx, rbx
0x18004f3bb  call    EcbDiskAwaitCompletion
0x18004f3c0  cmp     dword ptr [rbx+298h], 0
0x18004f3c7  jg      short loc_18004F3B8
0x18004f3c9  mov     rcx, [rbx+230h]; hObject
0x18004f3d0  call    cs:__imp_CloseHandle
0x18004f3d6  mov     qword ptr [rbx+230h], 0FFFFFFFFFFFFFFFFh
0x18004f3e1  movaps  xmm6, [rsp+78h+var_38]
0x18004f3e6  mov     eax, edi
0x18004f3e8  add     rsp, 58h
0x18004f3ec  pop     rdi
0x18004f3ed  pop     rsi
0x18004f3ee  pop     rbp
0x18004f3ef  pop     rbx
0x18004f3f0  retn
```
