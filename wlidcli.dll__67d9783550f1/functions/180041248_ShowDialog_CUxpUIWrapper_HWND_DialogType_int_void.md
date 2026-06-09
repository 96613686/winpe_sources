# ShowDialog(CUxpUIWrapper *,HWND__ *,DialogType,int,void * *)

- ea: `0x180041248`
- end: `0x180041375`
- name: `?ShowDialog@@YAJPEAVCUxpUIWrapper@@PEAUHWND__@@W4DialogType@@HPEAPEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800415bc`
- `0x180041b6c`

## callees

- `0x18000324c`
- `0x1800032dc`
- `0x18000cc9c`
- `0x18000e870`
- `0x180041248`
- `0x180053d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041315`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004131f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004131f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18004133d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18004133d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041346`

## pseudocode

```c
__int64 __fastcall ShowDialog(__int64 a1, __int64 a2, int a3)
{
  _DWORD *v6; // rax
  void *v7; // r8
  bool v8; // r9
  void *v9; // rbx
  HANDLE v10; // rax
  void *v11; // rdi
  signed int v12; // eax
  int LastError; // eax
  unsigned int v14; // ebx
  _BYTE v16[8]; // [rsp+20h] [rbp-48h] BYREF
  int *v17; // [rsp+28h] [rbp-40h]
  __int64 v18; // [rsp+30h] [rbp-38h]
  __int64 v19; // [rsp+38h] [rbp-30h]
  int v20; // [rsp+88h] [rbp+20h] BYREF

  v20 = 0;
  v18 = 0;
  v19 = 0;
  v17 = &v20;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\wlidui.cpp",
    "ShowDialog",
    (const char *)0x99,
    0,
    (const unsigned __int16 *)"ShowDialog");
  v6 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v6;
  if ( v6 )
  {
    v6[1] = 0;
    *v6 = a3;
    *((_QWORD *)v6 + 1) = a1;
    *((_QWORD *)v6 + 2) = a2;
    v10 = IDCRLCreateThread((LPTHREAD_START_ROUTINE)ShowDialogWorker, v6, v7, v8);
    v11 = v10;
    if ( v10 )
    {
      if ( WaitForSingleObject(v10, 0xFFFFFFFF) == -1 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v20 = LastError;
        TerminateThread(v11, LastError);
      }
      CloseHandle(v11);
    }
    else
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v20 = v12;
      operator delete(v9);
    }
  }
  else
  {
    v20 = -2147024882;
  }
  v14 = v20;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v16);
  return v14;
}

```

## disassembly

```asm
0x180041248  mov     r11, rsp
0x18004124b  mov     [r11+20h], r9d
0x18004124f  push    rbx
0x180041250  push    rbp
0x180041251  push    rsi
0x180041252  push    rdi
0x180041253  sub     rsp, 48h
0x180041257  mov     rsi, rdx
0x18004125a  mov     dword ptr [r11+20h], 0
0x180041262  lea     rdx, aShowdialog; "ShowDialog"
0x180041269  mov     qword ptr [r11-38h], 0
0x180041271  mov     edi, r8d
0x180041274  mov     [r11-48h], rdx
0x180041278  mov     rbp, rcx
0x18004127b  mov     qword ptr [r11-30h], 0
0x180041283  lea     rax, [r11+20h]
0x180041287  xor     r9d, r9d; unsigned int
0x18004128a  mov     r8d, 99h; char *
0x180041290  mov     [r11-40h], rax
0x180041294  lea     rcx, aClientcoreDsEx_20; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18004129b  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800412a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800412a7  mov     ecx, 18h; unsigned __int64
0x1800412ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800412b1  mov     rbx, rax
0x1800412b4  test    rax, rax
0x1800412b7  jz      loc_18004134E
0x1800412bd  mov     dword ptr [rax+4], 0
0x1800412c4  lea     rcx, ?ShowDialogWorker@@YAKPEAX@Z; lpStartAddress
0x1800412cb  mov     rdx, rax; lpParameter
0x1800412ce  mov     [rax], edi
0x1800412d0  mov     [rax+8], rbp
0x1800412d4  mov     [rax+10h], rsi
0x1800412d8  call    ?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z; IDCRLCreateThread(ulong (*)(void *),void *,int)
0x1800412dd  mov     rdi, rax
0x1800412e0  test    rax, rax
0x1800412e3  jnz     short loc_18004130D
0x1800412e5  call    cs:__imp_GetLastError
0x1800412eb  test    eax, eax
0x1800412ed  jle     short loc_1800412F7
0x1800412ef  movzx   eax, ax
0x1800412f2  or      eax, 80070000h
0x1800412f7  mov     edx, 18h
0x1800412fc  mov     [rsp+68h+arg_18], eax
0x180041303  mov     rcx, rbx; Block
0x180041306  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004130b  jmp     short loc_180041359
0x18004130d  or      ebx, 0FFFFFFFFh
0x180041310  mov     rcx, rdi; hHandle
0x180041313  mov     edx, ebx; dwMilliseconds
0x180041315  call    cs:__imp_WaitForSingleObject
0x18004131b  cmp     eax, ebx
0x18004131d  jnz     short loc_180041343
0x18004131f  call    cs:__imp_GetLastError
0x180041325  test    eax, eax
0x180041327  jle     short loc_180041331
0x180041329  movzx   eax, ax
0x18004132c  or      eax, 80070000h
0x180041331  mov     edx, eax; dwExitCode
0x180041333  mov     [rsp+68h+arg_18], eax
0x18004133a  mov     rcx, rdi; hThread
0x18004133d  call    cs:__imp_TerminateThread
0x180041343  mov     rcx, rdi; hObject
0x180041346  call    cs:__imp_CloseHandle
0x18004134c  jmp     short loc_180041359
0x18004134e  mov     [rsp+68h+arg_18], 8007000Eh
0x180041359  mov     ebx, [rsp+68h+arg_18]
0x180041360  lea     rcx, [rsp+68h+var_48]
0x180041365  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004136a  mov     eax, ebx
0x18004136c  add     rsp, 48h
0x180041370  pop     rdi
0x180041371  pop     rsi
0x180041372  pop     rbp
0x180041373  pop     rbx
0x180041374  retn
```
