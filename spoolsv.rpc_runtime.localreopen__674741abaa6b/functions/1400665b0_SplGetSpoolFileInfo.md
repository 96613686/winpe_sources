# SplGetSpoolFileInfo

- ea: `0x1400665b0`
- end: `0x140066857`
- name: `SplGetSpoolFileInfo`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x14003d024`

## callees

- `0x140004790`
- `0x14000f600`
- `0x1400161d0`
- `0x1400665b0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006683a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006683a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006681b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140066609`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006681b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066635`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140066635`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006668b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006678f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006668b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006678f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140066808`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006674f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14006674f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140066712`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140066712`

## pseudocode

```c
__int64 __fastcall SplGetSpoolFileInfo(__int64 a1, void *a2, int a3, __int64 a4, unsigned int a5, _DWORD *a6)
{
  unsigned int v6; // esi
  DWORD v10; // ecx
  HANDLE CurrentProcess; // r14
  void *v12; // rdx
  HANDLE v13; // r15
  WCHAR *v14; // rax
  HANDLE FileW; // rax
  LPCWSTR lpPathName[9]; // [rsp+40h] [rbp-48h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+8h] BYREF

  v6 = 0;
  TargetHandle = 0;
  lpPathName[0] = 0;
  if ( !a1 || *(_DWORD *)a1 != 24672 )
  {
    v10 = 6;
    goto LABEL_28;
  }
  if ( a3 == 1 )
  {
    if ( a5 < 0x18 )
    {
      SetLastError(0x7Au);
      *a6 = 24;
      goto LABEL_29;
    }
    if ( !a4 )
    {
      v10 = 87;
      goto LABEL_28;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
      goto LABEL_29;
    if ( *(struct _PROVIDOR **)(a1 + 8) == pLocalProvidor )
    {
      v6 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, HANDLE *, HANDLE, void *))pLocalProvidor + 84))(
             *(_QWORD *)(a1 + 16),
             0,
             &TargetHandle,
             CurrentProcess,
             a2);
      if ( v6 )
      {
        *(_QWORD *)(a4 + 8) = TargetHandle;
        *(_DWORD *)(a4 + 16) = 1;
        goto LABEL_25;
      }
    }
    else
    {
      v12 = *(void **)(a1 + 56);
      if ( v12 == (void *)-1LL )
      {
        v6 = (*((__int64 (__fastcall **)(_QWORD, LPCWSTR *, _QWORD, _QWORD, _QWORD))pLocalProvidor + 84))(
               0,
               lpPathName,
               0,
               0,
               0);
        if ( v6 )
        {
          v13 = RevertToPrinterSelf();
          v14 = (WCHAR *)DllAllocSplMem(0x208u);
          *(_QWORD *)(a1 + 64) = v14;
          if ( v14
            && GetTempFileNameW(lpPathName[0], L"SPL", 0, v14)
            && (FileW = CreateFileW(*(LPCWSTR *)(a1 + 64), 0xC0000000, 3u, 0, 2u, 0, 0),
                *(_QWORD *)(a1 + 56) = FileW,
                FileW != (HANDLE)-1LL)
            && DuplicateHandle(CurrentProcess, FileW, a2, &TargetHandle, 0, 1, 2u) )
          {
            *(_QWORD *)(a4 + 8) = TargetHandle;
            *(_DWORD *)a4 = 1;
            *(_DWORD *)(a4 + 16) = 2;
          }
          else
          {
            v6 = 0;
          }
          if ( v13 )
            ImpersonatePrinterClient(v13);
        }
        goto LABEL_26;
      }
      v6 = DuplicateHandle(CurrentProcess, v12, a2, &TargetHandle, 0, 1, 2u);
      if ( v6 )
      {
        *(_QWORD *)(a4 + 8) = TargetHandle;
        *(_DWORD *)(a4 + 16) = 2;
LABEL_25:
        *(_DWORD *)a4 = 1;
      }
    }
LABEL_26:
    CloseHandle(CurrentProcess);
    goto LABEL_29;
  }
  v10 = 124;
LABEL_28:
  SetLastError(v10);
LABEL_29:
  if ( lpPathName[0] )
    HeapFree(g_hSpoolssHeap, 0, (LPVOID)lpPathName[0]);
  return v6;
}

```

## disassembly

```asm
0x1400665b0  mov     rax, rsp
0x1400665b3  push    rbx
0x1400665b4  push    rsi
0x1400665b5  push    rdi
0x1400665b6  push    r12
0x1400665b8  push    r14
0x1400665ba  push    r15
0x1400665bc  sub     rsp, 58h
0x1400665c0  xor     esi, esi
0x1400665c2  mov     qword ptr [rax+8], 0
0x1400665ca  mov     [rax-48h], rsi
0x1400665ce  mov     rbx, r9
0x1400665d1  mov     r12, rdx
0x1400665d4  mov     rdi, rcx
0x1400665d7  test    rcx, rcx
0x1400665da  jz      loc_140066816
0x1400665e0  cmp     dword ptr [rcx], 6060h
0x1400665e6  jnz     loc_140066816
0x1400665ec  cmp     r8d, 1
0x1400665f0  jz      short loc_1400665FA
0x1400665f2  lea     ecx, [rsi+7Ch]
0x1400665f5  jmp     loc_14006681B
0x1400665fa  cmp     [rsp+88h+arg_20], 18h
0x140066602  jnb     short loc_140066628
0x140066604  mov     ecx, 7Ah ; 'z'; dwErrCode
0x140066609  call    cs:__imp_SetLastError
0x140066610  nop     dword ptr [rax+rax+00h]
0x140066615  mov     rax, [rsp+88h+arg_28]
0x14006661d  mov     dword ptr [rax], 18h
0x140066623  jmp     loc_140066827
0x140066628  test    rbx, rbx
0x14006662b  jnz     short loc_140066635
0x14006662d  lea     ecx, [rbx+57h]
0x140066630  jmp     loc_14006681B
0x140066635  call    cs:__imp_GetCurrentProcess
0x14006663c  nop     dword ptr [rax+rax+00h]
0x140066641  mov     r14, rax
0x140066644  test    rax, rax
0x140066647  jz      loc_140066827
0x14006664d  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140066654  cmp     [rdi+8], rax
0x140066658  jz      loc_1400667C7
0x14006665e  mov     rdx, [rdi+38h]; hSourceHandle
0x140066662  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140066666  jz      short loc_1400666B9
0x140066668  mov     [rsp+88h+dwOptions], 2; dwOptions
0x140066670  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x140066678  mov     edi, 1
0x14006667d  mov     r8, r12; hTargetProcessHandle
0x140066680  mov     [rsp+88h+bInheritHandle], edi; bInheritHandle
0x140066684  mov     rcx, r14; hSourceProcessHandle
0x140066687  mov     [rsp+88h+dwDesiredAccess], esi; dwDesiredAccess
0x14006668b  call    cs:__imp_DuplicateHandle
0x140066692  nop     dword ptr [rax+rax+00h]
0x140066697  mov     esi, eax
0x140066699  test    eax, eax
0x14006669b  jz      loc_140066805
0x1400666a1  mov     rcx, [rsp+88h+TargetHandle]
0x1400666a9  mov     [rbx+8], rcx
0x1400666ad  mov     dword ptr [rbx+10h], 2
0x1400666b4  jmp     loc_140066803
0x1400666b9  mov     rax, [rax+2A0h]
0x1400666c0  lea     rdx, [rsp+88h+lpPathName]
0x1400666c5  xor     r9d, r9d
0x1400666c8  mov     qword ptr [rsp+88h+dwDesiredAccess], rsi
0x1400666cd  xor     r8d, r8d
0x1400666d0  xor     ecx, ecx
0x1400666d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400666d7  mov     esi, eax
0x1400666d9  test    eax, eax
0x1400666db  jz      loc_140066805
0x1400666e1  call    RevertToPrinterSelf
0x1400666e6  mov     ecx, 208h; dwBytes
0x1400666eb  mov     r15, rax
0x1400666ee  call    DllAllocSplMem
0x1400666f3  mov     [rdi+40h], rax
0x1400666f7  test    rax, rax
0x1400666fa  jz      loc_1400667B6
0x140066700  mov     rcx, [rsp+88h+lpPathName]; lpPathName
0x140066705  lea     rdx, PrefixString; "SPL"
0x14006670c  mov     r9, rax; lpTempFileName
0x14006670f  xor     r8d, r8d; uUnique
0x140066712  call    cs:__imp_GetTempFileNameW
0x140066719  nop     dword ptr [rax+rax+00h]
0x14006671e  test    eax, eax
0x140066720  jz      loc_1400667B6
0x140066726  mov     rcx, [rdi+40h]; lpFileName
0x14006672a  xor     r9d, r9d; lpSecurityAttributes
0x14006672d  mov     qword ptr [rsp+88h+dwOptions], 0; hTemplateFile
0x140066736  mov     edx, 0C0000000h; dwDesiredAccess
0x14006673b  mov     [rsp+88h+bInheritHandle], 0; dwFlagsAndAttributes
0x140066743  mov     [rsp+88h+dwDesiredAccess], 2; dwCreationDisposition
0x14006674b  lea     r8d, [r9+3]; dwShareMode
0x14006674f  call    cs:__imp_CreateFileW
0x140066756  nop     dword ptr [rax+rax+00h]
0x14006675b  mov     [rdi+38h], rax
0x14006675f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140066763  jz      short loc_1400667B6
0x140066765  mov     [rsp+88h+dwOptions], 2; dwOptions
0x14006676d  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x140066775  mov     edi, 1
0x14006677a  mov     r8, r12; hTargetProcessHandle
0x14006677d  mov     [rsp+88h+bInheritHandle], edi; bInheritHandle
0x140066781  mov     rdx, rax; hSourceHandle
0x140066784  mov     rcx, r14; hSourceProcessHandle
0x140066787  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x14006678f  call    cs:__imp_DuplicateHandle
0x140066796  nop     dword ptr [rax+rax+00h]
0x14006679b  test    eax, eax
0x14006679d  jz      short loc_1400667B6
0x14006679f  mov     rax, [rsp+88h+TargetHandle]
0x1400667a7  mov     [rbx+8], rax
0x1400667ab  mov     [rbx], edi
0x1400667ad  mov     dword ptr [rbx+10h], 2
0x1400667b4  jmp     short loc_1400667B8
0x1400667b6  xor     esi, esi
0x1400667b8  test    r15, r15
0x1400667bb  jz      short loc_140066805
0x1400667bd  mov     rcx, r15; hToken
0x1400667c0  call    ImpersonatePrinterClient
0x1400667c5  jmp     short loc_140066805
0x1400667c7  mov     rcx, [rdi+10h]
0x1400667cb  lea     r8, [rsp+88h+TargetHandle]
0x1400667d3  mov     rax, [rax+2A0h]
0x1400667da  mov     r9, r14
0x1400667dd  xor     edx, edx
0x1400667df  mov     qword ptr [rsp+88h+dwDesiredAccess], r12
0x1400667e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400667e9  mov     esi, eax
0x1400667eb  test    eax, eax
0x1400667ed  jz      short loc_140066805
0x1400667ef  mov     rax, [rsp+88h+TargetHandle]
0x1400667f7  mov     edi, 1
0x1400667fc  mov     [rbx+8], rax
0x140066800  mov     [rbx+10h], edi
0x140066803  mov     [rbx], edi
0x140066805  mov     rcx, r14; hObject
0x140066808  call    cs:__imp_CloseHandle
0x14006680f  nop     dword ptr [rax+rax+00h]
0x140066814  jmp     short loc_140066827
0x140066816  mov     ecx, 6; dwErrCode
0x14006681b  call    cs:__imp_SetLastError
0x140066822  nop     dword ptr [rax+rax+00h]
0x140066827  mov     r8, [rsp+88h+lpPathName]; lpMem
0x14006682c  test    r8, r8
0x14006682f  jz      short loc_140066846
0x140066831  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140066838  xor     edx, edx; dwFlags
0x14006683a  call    cs:__imp_HeapFree
0x140066841  nop     dword ptr [rax+rax+00h]
0x140066846  mov     eax, esi
0x140066848  add     rsp, 58h
0x14006684c  pop     r15
0x14006684e  pop     r14
0x140066850  pop     r12
0x140066852  pop     rdi
0x140066853  pop     rsi
0x140066854  pop     rbx
0x140066855  retn
```
