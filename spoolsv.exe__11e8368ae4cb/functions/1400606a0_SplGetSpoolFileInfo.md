# SplGetSpoolFileInfo

- ea: `0x1400606a0`
- end: `0x140060910`
- name: `SplGetSpoolFileInfo`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140039b9c`

## callees

- `0x1400041c0`
- `0x14000e590`
- `0x140014eb0`
- `0x1400606a0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400608fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400608fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400606f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400608e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400606f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400608e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006071f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14006071f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006076f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140060861`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14006076f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140060861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400608d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400608d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140060827`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140060827`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1400607f0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1400607f0`

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
0x1400606a0  mov     rax, rsp
0x1400606a3  push    rbx
0x1400606a4  push    rsi
0x1400606a5  push    rdi
0x1400606a6  push    r12
0x1400606a8  push    r14
0x1400606aa  push    r15
0x1400606ac  sub     rsp, 58h
0x1400606b0  xor     esi, esi
0x1400606b2  mov     qword ptr [rax+8], 0
0x1400606ba  mov     [rax-48h], rsi
0x1400606be  mov     rbx, r9
0x1400606c1  mov     r12, rdx
0x1400606c4  mov     rdi, rcx
0x1400606c7  test    rcx, rcx
0x1400606ca  jz      loc_1400608DC
0x1400606d0  cmp     dword ptr [rcx], 6060h
0x1400606d6  jnz     loc_1400608DC
0x1400606dc  cmp     r8d, 1
0x1400606e0  jz      short loc_1400606EA
0x1400606e2  lea     ecx, [rsi+7Ch]
0x1400606e5  jmp     loc_1400608E1
0x1400606ea  cmp     [rsp+88h+arg_20], 18h
0x1400606f2  jnb     short loc_140060712
0x1400606f4  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1400606f9  call    cs:__imp_SetLastError
0x1400606ff  mov     rax, [rsp+88h+arg_28]
0x140060707  mov     dword ptr [rax], 18h
0x14006070d  jmp     loc_1400608E7
0x140060712  test    rbx, rbx
0x140060715  jnz     short loc_14006071F
0x140060717  lea     ecx, [rbx+57h]
0x14006071a  jmp     loc_1400608E1
0x14006071f  call    cs:__imp_GetCurrentProcess
0x140060725  mov     r14, rax
0x140060728  test    rax, rax
0x14006072b  jz      loc_1400608E7
0x140060731  mov     rax, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140060738  cmp     [rdi+8], rax
0x14006073c  jz      loc_140060893
0x140060742  mov     rdx, [rdi+38h]; hSourceHandle
0x140060746  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14006074a  jz      short loc_140060797
0x14006074c  mov     [rsp+88h+dwOptions], 2; dwOptions
0x140060754  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x14006075c  mov     edi, 1
0x140060761  mov     r8, r12; hTargetProcessHandle
0x140060764  mov     [rsp+88h+bInheritHandle], edi; bInheritHandle
0x140060768  mov     rcx, r14; hSourceProcessHandle
0x14006076b  mov     [rsp+88h+dwDesiredAccess], esi; dwDesiredAccess
0x14006076f  call    cs:__imp_DuplicateHandle
0x140060775  mov     esi, eax
0x140060777  test    eax, eax
0x140060779  jz      loc_1400608D1
0x14006077f  mov     rcx, [rsp+88h+TargetHandle]
0x140060787  mov     [rbx+8], rcx
0x14006078b  mov     dword ptr [rbx+10h], 2
0x140060792  jmp     loc_1400608CF
0x140060797  mov     rax, [rax+2A0h]
0x14006079e  lea     rdx, [rsp+88h+lpPathName]
0x1400607a3  xor     r9d, r9d
0x1400607a6  mov     qword ptr [rsp+88h+dwDesiredAccess], rsi
0x1400607ab  xor     r8d, r8d
0x1400607ae  xor     ecx, ecx
0x1400607b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400607b5  mov     esi, eax
0x1400607b7  test    eax, eax
0x1400607b9  jz      loc_1400608D1
0x1400607bf  call    RevertToPrinterSelf
0x1400607c4  mov     ecx, 208h; dwBytes
0x1400607c9  mov     r15, rax
0x1400607cc  call    DllAllocSplMem
0x1400607d1  mov     [rdi+40h], rax
0x1400607d5  test    rax, rax
0x1400607d8  jz      loc_140060882
0x1400607de  mov     rcx, [rsp+88h+lpPathName]; lpPathName
0x1400607e3  lea     rdx, PrefixString; "SPL"
0x1400607ea  mov     r9, rax; lpTempFileName
0x1400607ed  xor     r8d, r8d; uUnique
0x1400607f0  call    cs:__imp_GetTempFileNameW
0x1400607f6  test    eax, eax
0x1400607f8  jz      loc_140060882
0x1400607fe  mov     rcx, [rdi+40h]; lpFileName
0x140060802  xor     r9d, r9d; lpSecurityAttributes
0x140060805  mov     qword ptr [rsp+88h+dwOptions], 0; hTemplateFile
0x14006080e  mov     edx, 0C0000000h; dwDesiredAccess
0x140060813  mov     [rsp+88h+bInheritHandle], 0; dwFlagsAndAttributes
0x14006081b  mov     [rsp+88h+dwDesiredAccess], 2; dwCreationDisposition
0x140060823  lea     r8d, [r9+3]; dwShareMode
0x140060827  call    cs:__imp_CreateFileW
0x14006082d  mov     [rdi+38h], rax
0x140060831  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140060835  jz      short loc_140060882
0x140060837  mov     [rsp+88h+dwOptions], 2; dwOptions
0x14006083f  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x140060847  mov     edi, 1
0x14006084c  mov     r8, r12; hTargetProcessHandle
0x14006084f  mov     [rsp+88h+bInheritHandle], edi; bInheritHandle
0x140060853  mov     rdx, rax; hSourceHandle
0x140060856  mov     rcx, r14; hSourceProcessHandle
0x140060859  mov     [rsp+88h+dwDesiredAccess], 0; dwDesiredAccess
0x140060861  call    cs:__imp_DuplicateHandle
0x140060867  test    eax, eax
0x140060869  jz      short loc_140060882
0x14006086b  mov     rax, [rsp+88h+TargetHandle]
0x140060873  mov     [rbx+8], rax
0x140060877  mov     [rbx], edi
0x140060879  mov     dword ptr [rbx+10h], 2
0x140060880  jmp     short loc_140060884
0x140060882  xor     esi, esi
0x140060884  test    r15, r15
0x140060887  jz      short loc_1400608D1
0x140060889  mov     rcx, r15; hToken
0x14006088c  call    ImpersonatePrinterClient
0x140060891  jmp     short loc_1400608D1
0x140060893  mov     rcx, [rdi+10h]
0x140060897  lea     r8, [rsp+88h+TargetHandle]
0x14006089f  mov     rax, [rax+2A0h]
0x1400608a6  mov     r9, r14
0x1400608a9  xor     edx, edx
0x1400608ab  mov     qword ptr [rsp+88h+dwDesiredAccess], r12
0x1400608b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400608b5  mov     esi, eax
0x1400608b7  test    eax, eax
0x1400608b9  jz      short loc_1400608D1
0x1400608bb  mov     rax, [rsp+88h+TargetHandle]
0x1400608c3  mov     edi, 1
0x1400608c8  mov     [rbx+8], rax
0x1400608cc  mov     [rbx+10h], edi
0x1400608cf  mov     [rbx], edi
0x1400608d1  mov     rcx, r14; hObject
0x1400608d4  call    cs:__imp_CloseHandle
0x1400608da  jmp     short loc_1400608E7
0x1400608dc  mov     ecx, 6; dwErrCode
0x1400608e1  call    cs:__imp_SetLastError
0x1400608e7  mov     r8, [rsp+88h+lpPathName]; lpMem
0x1400608ec  test    r8, r8
0x1400608ef  jz      short loc_140060900
0x1400608f1  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400608f8  xor     edx, edx; dwFlags
0x1400608fa  call    cs:__imp_HeapFree
0x140060900  mov     eax, esi
0x140060902  add     rsp, 58h
0x140060906  pop     r15
0x140060908  pop     r14
0x14006090a  pop     r12
0x14006090c  pop     rdi
0x14006090d  pop     rsi
0x14006090e  pop     rbx
0x14006090f  retn
```
