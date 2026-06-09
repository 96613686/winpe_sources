# RPCSplGetSaveFileInfo

- ea: `0x14000d420`
- end: `0x14000d6b5`
- name: `RPCSplGetSaveFileInfo`
- size: `661`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, LPHANDLE lpTargetHandle, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001b90`
- `0x140001b9c`
- `0x140006894`
- `0x140007298`
- `0x1400085d8`
- `0x14000cfd0`
- `0x14000d420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000d5f3`
- `KERNEL32!GetLastError` at `0x14000d61b`
- `KERNEL32!GetLastError` at `0x14000d63e`
- `KERNEL32!GetLastError` at `0x14000d5f3`
- `KERNEL32!GetLastError` at `0x14000d61b`
- `KERNEL32!GetLastError` at `0x14000d63e`
- `KERNEL32!CloseHandle` at `0x14000d613`
- `KERNEL32!CloseHandle` at `0x14000d636`
- `KERNEL32!CloseHandle` at `0x14000d613`
- `KERNEL32!CloseHandle` at `0x14000d636`
- `KERNEL32!LocalFree` at `0x14000d660`
- `KERNEL32!LocalFree` at `0x14000d660`
- `KERNEL32!CreateFileW` at `0x14000d574`
- `KERNEL32!CreateFileW` at `0x14000d574`
- `KERNEL32!OpenProcess` at `0x14000d5b3`
- `KERNEL32!OpenProcess` at `0x14000d5b3`
- `KERNEL32!DuplicateHandle` at `0x14000d5e9`
- `KERNEL32!DuplicateHandle` at `0x14000d5e9`
- `KERNEL32!GetCurrentProcess` at `0x14000d5c4`
- `KERNEL32!GetCurrentProcess` at `0x14000d5c4`
- `WINSPOOL!GetPrintOutputInfo` at `0x14000d48e`
- `WINSPOOL!GetPrintOutputInfo` at `0x14000d48e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d696`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000d696`
- `RPCRT4!RpcRevertToSelf` at `0x14000d62d`
- `RPCRT4!RpcRevertToSelf` at `0x14000d62d`
- `RPCRT4!RpcImpersonateClient` at `0x14000d589`
- `RPCRT4!RpcImpersonateClient` at `0x14000d589`

## pseudocode

```c
RPC_STATUS __fastcall RPCSplGetSaveFileInfo(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        LPHANDLE lpTargetHandle,
        void **a6)
{
  signed int v6; // ebx
  void **v11; // r14
  __int64 v12; // rax
  unsigned __int64 v13; // rdi
  _WORD *v14; // rax
  _WORD *v15; // rdx
  LPCWSTR v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // rcx
  HANDLE FileW; // rsi
  int v20; // eax
  HANDLE v21; // rdi
  HANDLE CurrentProcess; // rax
  signed int v23; // eax
  void *v24; // rcx
  signed int v25; // eax
  signed int LastError; // eax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-10h] BYREF
  int Reply; // [rsp+88h] [rbp+38h] BYREF

  v6 = -2147024809;
  Reply = -2147024809;
  if ( !a2 )
    goto LABEL_42;
  if ( !lpTargetHandle )
    goto LABEL_42;
  v11 = a6;
  if ( !a6 )
    goto LABEL_42;
  TLoad64BitDllsMgr::IncUIRefCnt(pGLdrObj);
  lpFileName[0] = 0;
  Reply = GetPrintOutputInfo(a4, a2, 0, lpFileName);
  if ( Reply >= 0 && lpFileName[0] )
  {
    v12 = -1;
    do
      ++v12;
    while ( lpFileName[0][v12] );
    v13 = (unsigned int)(v12 + 1);
    v14 = operator new[](2 * v13);
    *v11 = v14;
    v15 = v14;
    if ( v14 )
    {
      if ( v13 )
      {
        if ( v13 > 0x7FFFFFFF )
        {
          *v14 = 0;
        }
        else
        {
          v16 = lpFileName[0];
          v17 = 2147483646;
          do
          {
            if ( !v17 )
              break;
            if ( !*v16 )
              break;
            *v15++ = *v16++;
            --v17;
            --v13;
          }
          while ( v13 );
          v18 = v15 - 1;
          if ( v13 )
            v18 = v15;
          v6 = v13 == 0 ? 0x8007007A : 0;
          *v18 = 0;
        }
      }
      Reply = v6;
      if ( v6 >= 0 )
      {
        Reply = CheckClientProcessAndEncryptFile(a3, (unsigned __int16 *)lpFileName[0]);
        if ( Reply >= 0 )
        {
          FileW = CreateFileW(lpFileName[0], 0x40000000u, 0, 0, 2u, 0, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Reply = LastError;
          }
          else
          {
            v20 = RpcImpersonateClient(0);
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            Reply = v20;
            if ( v20 >= 0 )
            {
              v21 = OpenProcess(0x40u, 1, a3);
              if ( v21 )
              {
                CurrentProcess = GetCurrentProcess();
                if ( !DuplicateHandle(CurrentProcess, FileW, v21, lpTargetHandle, 0, 0, 2u) )
                {
                  v23 = GetLastError();
                  if ( v23 > 0 )
                    v23 = (unsigned __int16)v23 | 0x80070000;
                  v24 = *v11;
                  Reply = v23;
                  operator delete(v24);
                  *v11 = 0;
                }
                CloseHandle(v21);
              }
              else
              {
                v25 = GetLastError();
                if ( v25 > 0 )
                  v25 = (unsigned __int16)v25 | 0x80070000;
                Reply = v25;
              }
              RpcRevertToSelf();
            }
            CloseHandle(FileW);
          }
        }
      }
    }
    else
    {
      Reply = -2147024882;
    }
    LocalFree((HLOCAL)lpFileName[0]);
  }
  TLoad64BitDllsMgr::DecUIRefCnt(pGLdrObj);
  v6 = Reply;
  if ( Reply < 0 )
LABEL_42:
    SplWow64Telemetry::WriteDbgTraceError("RPCSplGetSaveFileInfo", L"Failed. hr: 0x%x", (unsigned int)v6);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x14000d420  mov     [rsp-28h+arg_0], rbx
0x14000d425  mov     [rsp-28h+arg_10], rsi
0x14000d42a  push    rbp
0x14000d42b  push    rdi
0x14000d42c  push    r12
0x14000d42e  push    r13
0x14000d430  push    r14
0x14000d432  mov     rbp, rsp
0x14000d435  sub     rsp, 50h
0x14000d439  xor     eax, eax
0x14000d43b  mov     ebx, 80070057h
0x14000d440  mov     [rbp+Reply], ebx
0x14000d443  mov     rsi, r9
0x14000d446  mov     r12d, r8d
0x14000d449  mov     rdi, rdx
0x14000d44c  mov     r13, rcx
0x14000d44f  test    rdx, rdx
0x14000d452  jz      loc_14000D679
0x14000d458  cmp     [rbp+lpTargetHandle], rax
0x14000d45c  jz      loc_14000D679
0x14000d462  mov     r14, [rbp+arg_28]
0x14000d466  test    r14, r14
0x14000d469  jz      loc_14000D679
0x14000d46f  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000d476  call    ?IncUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::IncUIRefCnt(void)
0x14000d47b  xor     ecx, ecx
0x14000d47d  lea     r9, [rbp+lpFileName]
0x14000d481  mov     [rbp+lpFileName], rcx
0x14000d485  xor     r8d, r8d
0x14000d488  mov     rcx, rsi
0x14000d48b  mov     rdx, rdi
0x14000d48e  call    cs:__imp_GetPrintOutputInfo
0x14000d494  xor     esi, esi
0x14000d496  mov     [rbp+Reply], eax
0x14000d499  test    eax, eax
0x14000d49b  js      loc_14000D666
0x14000d4a1  mov     rcx, [rbp+lpFileName]
0x14000d4a5  test    rcx, rcx
0x14000d4a8  jz      loc_14000D666
0x14000d4ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d4b2  inc     rax
0x14000d4b5  cmp     [rcx+rax*2], si
0x14000d4b9  jnz     short loc_14000D4B2
0x14000d4bb  inc     eax
0x14000d4bd  mov     edi, eax
0x14000d4bf  lea     rcx, [rax+rax]; unsigned __int64
0x14000d4c3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000d4c8  mov     [r14], rax
0x14000d4cb  mov     rdx, rax
0x14000d4ce  test    rax, rax
0x14000d4d1  jz      loc_14000D655
0x14000d4d7  test    rdi, rdi
0x14000d4da  jz      short loc_14000D532
0x14000d4dc  cmp     rdi, 7FFFFFFFh
0x14000d4e3  ja      short loc_14000D52F
0x14000d4e5  mov     rcx, [rbp+lpFileName]
0x14000d4e9  mov     eax, 7FFFFFFEh
0x14000d4ee  test    rax, rax
0x14000d4f1  jz      short loc_14000D512
0x14000d4f3  movzx   r8d, word ptr [rcx]
0x14000d4f7  test    r8w, r8w
0x14000d4fb  jz      short loc_14000D512
0x14000d4fd  mov     [rdx], r8w
0x14000d501  add     rcx, 2
0x14000d505  add     rdx, 2
0x14000d509  dec     rax
0x14000d50c  sub     rdi, 1
0x14000d510  jnz     short loc_14000D4EE
0x14000d512  test    rdi, rdi
0x14000d515  lea     rcx, [rdx-2]
0x14000d519  cmovnz  rcx, rdx
0x14000d51d  neg     rdi
0x14000d520  sbb     ebx, ebx
0x14000d522  not     ebx
0x14000d524  and     ebx, 8007007Ah
0x14000d52a  mov     [rcx], si
0x14000d52d  jmp     short loc_14000D532
0x14000d52f  mov     [rax], si
0x14000d532  mov     [rbp+Reply], ebx
0x14000d535  test    ebx, ebx
0x14000d537  js      loc_14000D65C
0x14000d53d  mov     rdx, [rbp+lpFileName]; unsigned __int16 *
0x14000d541  mov     ecx, r12d; unsigned int
0x14000d544  call    ?CheckClientProcessAndEncryptFile@@YAJKPEAG@Z; CheckClientProcessAndEncryptFile(ulong,ushort *)
0x14000d549  mov     [rbp+Reply], eax
0x14000d54c  test    eax, eax
0x14000d54e  js      loc_14000D65C
0x14000d554  mov     rcx, [rbp+lpFileName]; lpFileName
0x14000d558  xor     r9d, r9d; lpSecurityAttributes
0x14000d55b  mov     [rsp+50h+hTemplateFile], rsi; hTemplateFile
0x14000d560  xor     r8d, r8d; dwShareMode
0x14000d563  mov     [rsp+50h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x14000d567  mov     edx, 40000000h; dwDesiredAccess
0x14000d56c  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x14000d574  call    cs:__imp_CreateFileW
0x14000d57a  mov     rsi, rax
0x14000d57d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d581  jz      loc_14000D63E
0x14000d587  xor     ecx, ecx; BindingHandle
0x14000d589  call    cs:__imp_RpcImpersonateClient
0x14000d58f  mov     ebx, 80070000h
0x14000d594  test    eax, eax
0x14000d596  jle     short loc_14000D59D
0x14000d598  movzx   eax, ax
0x14000d59b  or      eax, ebx
0x14000d59d  mov     [rbp+Reply], eax
0x14000d5a0  test    eax, eax
0x14000d5a2  js      loc_14000D633
0x14000d5a8  mov     edx, 1; bInheritHandle
0x14000d5ad  mov     r8d, r12d; dwProcessId
0x14000d5b0  lea     ecx, [rdx+3Fh]; dwDesiredAccess
0x14000d5b3  call    cs:__imp_OpenProcess
0x14000d5b9  xor     r12d, r12d
0x14000d5bc  mov     rdi, rax
0x14000d5bf  test    rax, rax
0x14000d5c2  jz      short loc_14000D61B
0x14000d5c4  call    cs:__imp_GetCurrentProcess
0x14000d5ca  mov     r9, [rbp+lpTargetHandle]; lpTargetHandle
0x14000d5ce  mov     r8, rdi; hTargetProcessHandle
0x14000d5d1  mov     dword ptr [rsp+50h+hTemplateFile], 2; dwOptions
0x14000d5d9  mov     rcx, rax; hSourceProcessHandle
0x14000d5dc  mov     [rsp+50h+dwFlagsAndAttributes], r12d; bInheritHandle
0x14000d5e1  mov     rdx, rsi; hSourceHandle
0x14000d5e4  mov     [rsp+50h+dwCreationDisposition], r12d; dwDesiredAccess
0x14000d5e9  call    cs:__imp_DuplicateHandle
0x14000d5ef  test    eax, eax
0x14000d5f1  jnz     short loc_14000D610
0x14000d5f3  call    cs:__imp_GetLastError
0x14000d5f9  test    eax, eax
0x14000d5fb  jle     short loc_14000D602
0x14000d5fd  movzx   eax, ax
0x14000d600  or      eax, ebx
0x14000d602  mov     rcx, [r14]; Block
0x14000d605  mov     [rbp+Reply], eax
0x14000d608  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d60d  mov     [r14], r12
0x14000d610  mov     rcx, rdi; hObject
0x14000d613  call    cs:__imp_CloseHandle
0x14000d619  jmp     short loc_14000D62D
0x14000d61b  call    cs:__imp_GetLastError
0x14000d621  test    eax, eax
0x14000d623  jle     short loc_14000D62A
0x14000d625  movzx   eax, ax
0x14000d628  or      eax, ebx
0x14000d62a  mov     [rbp+Reply], eax
0x14000d62d  call    cs:__imp_RpcRevertToSelf
0x14000d633  mov     rcx, rsi; hObject
0x14000d636  call    cs:__imp_CloseHandle
0x14000d63c  jmp     short loc_14000D65C
0x14000d63e  call    cs:__imp_GetLastError
0x14000d644  test    eax, eax
0x14000d646  jle     short loc_14000D650
0x14000d648  movzx   eax, ax
0x14000d64b  or      eax, 80070000h
0x14000d650  mov     [rbp+Reply], eax
0x14000d653  jmp     short loc_14000D65C
0x14000d655  mov     [rbp+Reply], 8007000Eh
0x14000d65c  mov     rcx, [rbp+lpFileName]; hMem
0x14000d660  call    cs:__imp_LocalFree
0x14000d666  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000d66d  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x14000d672  mov     ebx, [rbp+Reply]
0x14000d675  test    ebx, ebx
0x14000d677  jns     short loc_14000D68F
0x14000d679  mov     r8d, ebx
0x14000d67c  lea     rdx, aFailedHr0xX; "Failed. hr: 0x%x"
0x14000d683  lea     rcx, aRpcsplgetsavef; "RPCSplGetSaveFileInfo"
0x14000d68a  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000d68f  lea     rdx, [rbp+Reply]; Reply
0x14000d693  mov     rcx, r13; pAsync
0x14000d696  call    cs:__imp_RpcAsyncCompleteCall
0x14000d69c  lea     r11, [rsp+50h+var_s0]
0x14000d6a1  mov     rbx, [r11+30h]
0x14000d6a5  mov     rsi, [r11+40h]
0x14000d6a9  mov     rsp, r11
0x14000d6ac  pop     r14
0x14000d6ae  pop     r13
0x14000d6b0  pop     r12
0x14000d6b2  pop     rdi
0x14000d6b3  pop     rbp
0x14000d6b4  retn
```
