# CThemeServer::CopyTheme(void *,void * *,void *,void * *,ushort const *,ushort const *,ushort const *,ulong,ulong,void *,void *)

- ea: `0x18000d524`
- end: `0x18000d71f`
- name: `?CopyTheme@CThemeServer@@QEAAJPEAXPEAPEAX01PEBG22KK00@Z`
- size: `507`
- prototype: `__int64 __fastcall(CThemeServer *this, HANDLE hFileMappingObject, LPHANDLE lpTargetHandle, HANDLE, LPHANDLE lpTargetHandlea, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, HANDLE hSourceHandle, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d37c`

## callees

- `0x180009ea0`
- `0x18000d524`
- `0x18000d91c`
- `0x18000f0a0`
- `0x18000f190`
- `0x18000f2d4`
- `0x18000f700`
- `0x18000f838`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d703`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d54a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d54a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d65e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d69e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d6a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d65e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d69e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d6a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d694`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d6d3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d694`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d6d3`

## pseudocode

```c
__int64 __fastcall CThemeServer::CopyTheme(
        CThemeServer *this,
        HANDLE hFileMappingObject,
        LPHANDLE lpTargetHandle,
        HANDLE a4,
        LPHANDLE lpTargetHandlea,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned int a10,
        HANDLE hSourceHandle,
        void *a12)
{
  char *v16; // rax
  char *v17; // rdi
  unsigned int v18; // r9d
  int ErrorLast; // ebx
  _DWORD *v20; // rbx
  HANDLE CurrentProcess; // rbx
  HANDLE v22; // rax
  HANDLE v23; // rbx
  HANDLE v24; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-58h]
  unsigned __int16 dwDesiredAccessa; // [rsp+20h] [rbp-58h]
  int bInheritHandle; // [rsp+28h] [rbp-50h]
  unsigned int dwOptions; // [rsp+30h] [rbp-48h]

  v16 = (char *)HeapAlloc(s_hHeapToUse, 0, 0x38u);
  v17 = v16;
  if ( !v16 )
    return (unsigned int)-2147024882;
  StringCchCopyA(v16, 8u, "thmfile");
  StringCchCopyA(v17 + 48, 4u, "end");
  *((_QWORD *)v17 + 1) = 0;
  *((_DWORD *)v17 + 10) = -1;
  *((_DWORD *)v17 + 11) = -1;
  *((_QWORD *)v17 + 2) = 0;
  *((_QWORD *)v17 + 3) = 0;
  *((_QWORD *)v17 + 4) = 0;
  ErrorLast = CUxThemeFile::OpenFromHandle((CUxThemeFile *)v17, hFileMappingObject, a4, v18, dwDesiredAccess);
  if ( ErrorLast >= 0 )
  {
    if ( !ThemeMatch((struct CUxThemeFile *)v17, a6, a7, a8, dwDesiredAccessa, bInheritHandle, dwOptions) )
    {
LABEL_12:
      ErrorLast = -2147024891;
      goto LABEL_13;
    }
    ErrorLast = CUxThemeFile::ValidateThemeData((CUxThemeFile *)v17, 1);
    if ( ErrorLast >= 0 )
    {
      v20 = (_DWORD *)*((_QWORD *)v17 + 3);
      if ( (*v20 & 4) == 0 )
        CThemeServer::LoadRemoteTheme(this, a6, a7, a8, a9, hSourceHandle, a12);
      if ( (*v20 & 4) == 0 )
      {
        CurrentProcess = GetCurrentProcess();
        v22 = GetCurrentProcess();
        if ( DuplicateHandle(v22, hFileMappingObject, CurrentProcess, lpTargetHandle, 0xF001Fu, 0, 0)
          && (v23 = GetCurrentProcess(),
              v24 = GetCurrentProcess(),
              DuplicateHandle(v24, a4, v23, lpTargetHandlea, 0xF001Fu, 0, 0)) )
        {
          ErrorLast = 0;
        }
        else
        {
          ErrorLast = MakeErrorLast();
        }
        goto LABEL_13;
      }
      goto LABEL_12;
    }
  }
LABEL_13:
  CThemeSection::~CThemeSection((CThemeSection *)v17);
  HeapFree(s_hHeapToUse, 0, v17);
  return (unsigned int)ErrorLast;
}

```

## disassembly

```asm
0x18000d524  push    rbx
0x18000d526  push    rbp
0x18000d527  push    rsi
0x18000d528  push    rdi
0x18000d529  push    r14
0x18000d52b  push    r15
0x18000d52d  sub     rsp, 48h
0x18000d531  mov     rbp, rdx
0x18000d534  mov     r15, r8
0x18000d537  xor     edx, edx; dwFlags
0x18000d539  mov     r14, rcx
0x18000d53c  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d543  mov     rsi, r9
0x18000d546  lea     r8d, [rdx+38h]; dwBytes
0x18000d54a  call    cs:__imp_HeapAlloc
0x18000d550  mov     rdi, rax
0x18000d553  test    rax, rax
0x18000d556  jz      loc_18000D70B
0x18000d55c  lea     r8, aThmfile; "thmfile"
0x18000d563  mov     edx, 8; unsigned __int64
0x18000d568  mov     rcx, rax; char *
0x18000d56b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000d570  lea     rcx, [rdi+30h]; char *
0x18000d574  mov     edx, 4; unsigned __int64
0x18000d579  lea     r8, aEnd; "end"
0x18000d580  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18000d585  or      eax, 0FFFFFFFFh
0x18000d588  mov     qword ptr [rdi+8], 0
0x18000d590  mov     r8, rsi; HANDLE
0x18000d593  mov     [rdi+28h], eax
0x18000d596  mov     rdx, rbp; hFileMappingObject
0x18000d599  mov     [rdi+2Ch], eax
0x18000d59c  mov     rcx, rdi; this
0x18000d59f  mov     qword ptr [rdi+10h], 0
0x18000d5a7  mov     qword ptr [rdi+18h], 0
0x18000d5af  mov     qword ptr [rdi+20h], 0
0x18000d5b7  call    ?OpenFromHandle@CUxThemeFile@@QEAAJPEAX0KH@Z; CUxThemeFile::OpenFromHandle(void *,void *,ulong,int)
0x18000d5bc  mov     ebx, eax
0x18000d5be  test    eax, eax
0x18000d5c0  js      loc_18000D6EF
0x18000d5c6  mov     r9, [rsp+78h+arg_38]; unsigned __int16 *
0x18000d5ce  mov     rcx, rdi; struct CUxThemeFile *
0x18000d5d1  mov     r8, [rsp+78h+arg_30]; unsigned __int16 *
0x18000d5d9  mov     rdx, [rsp+78h+arg_28]; unsigned __int16 *
0x18000d5e1  call    ?ThemeMatch@@YAHPEAVCUxThemeFile@@PEBG11GHK@Z; ThemeMatch(CUxThemeFile *,ushort const *,ushort const *,ushort const *,ushort,int,ulong)
0x18000d5e6  test    eax, eax
0x18000d5e8  jz      loc_18000D6EA
0x18000d5ee  mov     edx, 1; int
0x18000d5f3  mov     rcx, rdi; this
0x18000d5f6  call    ?ValidateThemeData@CUxThemeFile@@QEAAJH@Z; CUxThemeFile::ValidateThemeData(int)
0x18000d5fb  mov     ebx, eax
0x18000d5fd  test    eax, eax
0x18000d5ff  js      loc_18000D6EF
0x18000d605  mov     rbx, [rdi+18h]
0x18000d609  mov     eax, [rbx]
0x18000d60b  test    al, 4
0x18000d60d  jnz     short loc_18000D654
0x18000d60f  mov     rax, [rsp+78h+arg_58]
0x18000d617  mov     rcx, r14; this
0x18000d61a  mov     r9, [rsp+78h+arg_38]; unsigned __int16 *
0x18000d622  mov     r8, [rsp+78h+arg_30]; unsigned __int16 *
0x18000d62a  mov     rdx, [rsp+78h+arg_28]; unsigned __int16 *
0x18000d632  mov     qword ptr [rsp+78h+dwOptions], rax; void *
0x18000d637  mov     rax, [rsp+78h+hSourceHandle]
0x18000d63f  mov     qword ptr [rsp+78h+bInheritHandle], rax; hSourceHandle
0x18000d644  mov     eax, [rsp+78h+arg_40]
0x18000d64b  mov     [rsp+78h+dwDesiredAccess], eax; unsigned int
0x18000d64f  call    ?LoadRemoteTheme@CThemeServer@@QEAAJPEBG00KPEAX1@Z; CThemeServer::LoadRemoteTheme(ushort const *,ushort const *,ushort const *,ulong,void *,void *)
0x18000d654  mov     eax, [rbx]
0x18000d656  test    al, 4
0x18000d658  jnz     loc_18000D6EA
0x18000d65e  call    cs:__imp_GetCurrentProcess
0x18000d664  mov     rbx, rax
0x18000d667  call    cs:__imp_GetCurrentProcess
0x18000d66d  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000d675  mov     r14d, 0F001Fh
0x18000d67b  mov     rcx, rax; hSourceProcessHandle
0x18000d67e  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18000d686  mov     r9, r15; lpTargetHandle
0x18000d689  mov     [rsp+78h+dwDesiredAccess], r14d; dwDesiredAccess
0x18000d68e  mov     r8, rbx; hTargetProcessHandle
0x18000d691  mov     rdx, rbp; hSourceHandle
0x18000d694  call    cs:__imp_DuplicateHandle
0x18000d69a  test    eax, eax
0x18000d69c  jz      short loc_18000D6E1
0x18000d69e  call    cs:__imp_GetCurrentProcess
0x18000d6a4  mov     rbx, rax
0x18000d6a7  call    cs:__imp_GetCurrentProcess
0x18000d6ad  mov     r9, [rsp+78h+lpTargetHandle]; lpTargetHandle
0x18000d6b5  mov     r8, rbx; hTargetProcessHandle
0x18000d6b8  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000d6c0  mov     rcx, rax; hSourceProcessHandle
0x18000d6c3  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18000d6cb  mov     rdx, rsi; hSourceHandle
0x18000d6ce  mov     [rsp+78h+dwDesiredAccess], r14d; dwDesiredAccess
0x18000d6d3  call    cs:__imp_DuplicateHandle
0x18000d6d9  test    eax, eax
0x18000d6db  jz      short loc_18000D6E1
0x18000d6dd  xor     ebx, ebx
0x18000d6df  jmp     short loc_18000D6EF
0x18000d6e1  call    ?MakeErrorLast@@YAJXZ; MakeErrorLast(void)
0x18000d6e6  mov     ebx, eax
0x18000d6e8  jmp     short loc_18000D6EF
0x18000d6ea  mov     ebx, 80070005h
0x18000d6ef  mov     rcx, rdi; this
0x18000d6f2  call    ??1CThemeSection@@QEAA@XZ; CThemeSection::~CThemeSection(void)
0x18000d6f7  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d6fe  mov     r8, rdi; lpMem
0x18000d701  xor     edx, edx; dwFlags
0x18000d703  call    cs:__imp_HeapFree
0x18000d709  jmp     short loc_18000D710
0x18000d70b  mov     ebx, 8007000Eh
0x18000d710  mov     eax, ebx
0x18000d712  add     rsp, 48h
0x18000d716  pop     r15
0x18000d718  pop     r14
0x18000d71a  pop     rdi
0x18000d71b  pop     rsi
0x18000d71c  pop     rbp
0x18000d71d  pop     rbx
0x18000d71e  retn
```
