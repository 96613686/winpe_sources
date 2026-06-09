# FusionpTraceCallCOMSuccessfulExitVaBig(long,char const *,char *)

- ea: `0x180067314`
- end: `0x180067540`
- name: `?FusionpTraceCallCOMSuccessfulExitVaBig@@YAXJPEBDPEAD@Z`
- size: `556`
- prototype: `void __fastcall(DWORD dwMessageId, const char *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180067170`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x180011864`
- `0x180059760`
- `0x180067314`
- `0x18006a110`

## import_xrefs

- `ntdll!_vsnprintf_s` at `0x1800673fc`
- `ntdll!_vsnprintf_s` at `0x1800673fc`
- `ntdll!_snprintf_s` at `0x1800673cb`
- `ntdll!_snprintf_s` at `0x180067481`
- `ntdll!_snprintf_s` at `0x1800673cb`
- `ntdll!_snprintf_s` at `0x180067481`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800674e8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800674e8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800673a3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800673a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067348`

## string_xrefs

- `0x180067408`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n`
- `0x180067415`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n`

## pseudocode

```c
void __fastcall FusionpTraceCallCOMSuccessfulExitVaBig(DWORD dwMessageId, const char *Format, va_list ArgList)
{
  DWORD CurrentThreadId; // r14d
  const char *v7; // rbx
  __int64 v8; // r8
  HANDLE v9; // rbx
  __int64 nSize; // [rsp+28h] [rbp-D8h]
  DWORD v11; // [rsp+48h] [rbp-B8h]
  DWORD v12; // [rsp+50h] [rbp-B0h]
  __int128 v13; // [rsp+70h] [rbp-90h] BYREF
  __int64 v14; // [rsp+80h] [rbp-80h]
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING SearchString; // [rsp+90h] [rbp-70h] BYREF
  char v17[128]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR Buffer[128]; // [rsp+120h] [rbp+20h] BYREF
  char v19[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v14 = 0;
  v13 = 0;
  FusionpGetProcessImageFileName(&SearchString);
  v17[0] = 0;
  Buffer[0] = 0;
  v19[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, dwMessageId, 0, Buffer, 0x80u, 0) )
  {
    _snprintf_s(Buffer, 0x80u, 0x7Fu, "<Untranslatable(non-existed or too long) HRESULT: 0x%08lx>", dwMessageId);
    Buffer[127] = 0;
  }
  v17[0] = 0;
  if ( Format )
  {
    _vsnprintf_s(v17, 0x80u, 0x7Fu, Format, ArgList);
    v7 = "%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n";
    v17[127] = 0;
  }
  else
  {
    v7 = "%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n";
  }
  FusionpGetActiveFrameInfo((struct _FRAME_INFO *)&v13);
  v12 = dwMessageId;
  v11 = CurrentThreadId;
  LODWORD(nSize) = v14;
  _snprintf_s(
    v19,
    0x100u,
    0xFFu,
    v7,
    (_QWORD)v13,
    nSize,
    *((_QWORD *)&v13 + 1),
    64,
    &SearchString,
    v11,
    v12,
    Buffer,
    v17);
  v19[255] = 0;
  FusionpDbgPrintEx(0x80000008, "%s", v19);
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    NumberOfBytesWritten = 0;
    v8 = -1;
    do
      ++v8;
    while ( v19[v8] );
    if ( !WriteFile(hFile, v19, v8 + 1, &NumberOfBytesWritten, 0) )
    {
      v9 = hFile;
      hFile = 0;
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007C800);
      hFile = v9;
    }
  }
}

```

## disassembly

```asm
0x180067314  mov     [rsp-8+arg_18], rbx
0x180067319  push    rbp
0x18006731a  push    rsi
0x18006731b  push    rdi
0x18006731c  push    r14
0x18006731e  push    r15
0x180067320  lea     rbp, [rsp-1B0h]
0x180067328  sub     rsp, 2B0h
0x18006732f  mov     rax, cs:__security_cookie
0x180067336  xor     rax, rsp
0x180067339  mov     [rbp+1D0h+var_30], rax
0x180067340  mov     rsi, r8
0x180067343  mov     rbx, rdx
0x180067346  mov     edi, ecx
0x180067348  call    cs:__imp_GetCurrentThreadId
0x18006734f  nop     dword ptr [rax+rax+00h]
0x180067354  xorps   xmm0, xmm0
0x180067357  lea     rcx, [rbp+1D0h+SearchString]; SearchString
0x18006735b  mov     r14d, eax
0x18006735e  xor     eax, eax
0x180067360  mov     [rbp+1D0h+var_250], rax
0x180067364  movups  [rsp+2D0h+var_260], xmm0
0x180067369  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x18006736e  xor     r15d, r15d
0x180067371  lea     rax, [rbp+1D0h+Buffer]
0x180067375  mov     [rsp+2D0h+Arguments], r15; Arguments
0x18006737a  xor     r9d, r9d; dwLanguageId
0x18006737d  mov     dword ptr [rsp+2D0h+nSize], 80h; nSize
0x180067385  mov     r8d, edi; dwMessageId
0x180067388  xor     edx, edx; lpSource
0x18006738a  mov     [rsp+2D0h+lpBuffer], rax; lpBuffer
0x18006738f  mov     ecx, 10FFh; dwFlags
0x180067394  mov     [rbp+1D0h+var_230], r15b
0x180067398  mov     [rbp+1D0h+Buffer], r15b
0x18006739c  mov     [rbp+1D0h+var_130], r15b
0x1800673a3  call    cs:__imp_FormatMessageA
0x1800673aa  nop     dword ptr [rax+rax+00h]
0x1800673af  test    eax, eax
0x1800673b1  jnz     short loc_1800673DE
0x1800673b3  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x1800673ba  mov     dword ptr [rsp+2D0h+lpBuffer], edi
0x1800673be  mov     edx, 80h; BufferCount
0x1800673c3  lea     r8d, [r15+7Fh]; MaxCount
0x1800673c7  lea     rcx, [rbp+1D0h+Buffer]; Buffer
0x1800673cb  call    cs:__imp__snprintf_s
0x1800673d2  nop     dword ptr [rax+rax+00h]
0x1800673d7  mov     [rbp+1D0h+var_131], r15b
0x1800673de  mov     [rbp+1D0h+var_230], r15b
0x1800673e2  test    rbx, rbx
0x1800673e5  jz      short loc_180067415
0x1800673e7  mov     edx, 80h; BufferCount
0x1800673ec  mov     [rsp+2D0h+lpBuffer], rsi; ArgList
0x1800673f1  mov     r9, rbx; Format
0x1800673f4  lea     rcx, [rbp+1D0h+var_230]; Buffer
0x1800673f8  lea     r8d, [rdx-1]; MaxCount
0x1800673fc  call    cs:__imp__vsnprintf_s
0x180067403  nop     dword ptr [rax+rax+00h]
0x180067408  lea     rbx, aSDFunctionSIub; "%s(%d): [function %s %Iubit process %wZ"...
0x18006740f  mov     [rbp+1D0h+var_1B1], r15b
0x180067413  jmp     short loc_18006741C
0x180067415  lea     rbx, aSDFunctionSIub_1; "%s(%d): [function %s %Iubit process %wZ"...
0x18006741c  lea     rcx, [rsp+2D0h+var_260]; struct _FRAME_INFO *
0x180067421  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x180067426  lea     rax, [rbp+1D0h+var_230]
0x18006742a  mov     edx, 100h; BufferCount
0x18006742f  mov     [rsp+2D0h+var_270], rax
0x180067434  lea     rcx, [rbp+1D0h+var_130]; Buffer
0x18006743b  lea     rax, [rbp+1D0h+Buffer]
0x18006743f  mov     r9, rbx; Format
0x180067442  mov     [rsp+2D0h+var_278], rax
0x180067447  lea     rax, [rbp+1D0h+SearchString]
0x18006744b  mov     [rsp+2D0h+var_280], edi
0x18006744f  lea     r8d, [rdx-1]; MaxCount
0x180067453  mov     [rsp+2D0h+var_288], r14d
0x180067458  mov     [rsp+2D0h+var_290], rax
0x18006745d  mov     rax, qword ptr [rsp+2D0h+var_260+8]
0x180067462  mov     [rsp+2D0h+var_298], 40h ; '@'
0x18006746b  mov     [rsp+2D0h+Arguments], rax
0x180067470  mov     eax, dword ptr [rbp+1D0h+var_250]
0x180067473  mov     dword ptr [rsp+2D0h+nSize], eax
0x180067477  mov     rax, qword ptr [rsp+2D0h+var_260]
0x18006747c  mov     [rsp+2D0h+lpBuffer], rax
0x180067481  call    cs:__imp__snprintf_s
0x180067488  nop     dword ptr [rax+rax+00h]
0x18006748d  lea     r8, [rbp+1D0h+var_130]
0x180067494  mov     [rbp+1D0h+var_31], r15b
0x18006749b  lea     rdx, aS; "%s"
0x1800674a2  mov     ecx, 80000008h; unsigned int
0x1800674a7  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800674ac  mov     rcx, cs:hFile; hFile
0x1800674b3  lea     rax, [rcx-1]
0x1800674b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800674bb  ja      short loc_180067519
0x1800674bd  mov     [rbp+1D0h+NumberOfBytesWritten], r15d
0x1800674c1  lea     rax, [rbp+1D0h+var_130]
0x1800674c8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800674cc  inc     r8
0x1800674cf  cmp     [rax+r8], r15b
0x1800674d3  jnz     short loc_1800674CC
0x1800674d5  inc     r8d; nNumberOfBytesToWrite
0x1800674d8  mov     [rsp+2D0h+lpBuffer], r15; lpOverlapped
0x1800674dd  lea     r9, [rbp+1D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800674e1  lea     rdx, [rbp+1D0h+var_130]; lpBuffer
0x1800674e8  call    cs:__imp_WriteFile
0x1800674ef  nop     dword ptr [rax+rax+00h]
0x1800674f4  test    eax, eax
0x1800674f6  jnz     short loc_180067519
0x1800674f8  mov     rbx, cs:hFile
0x1800674ff  lea     rcx, off_18007C800; struct _CALL_SITE_INFO *
0x180067506  mov     cs:hFile, r15
0x18006750d  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180067512  mov     cs:hFile, rbx
0x180067519  mov     rcx, [rbp+1D0h+var_30]
0x180067520  xor     rcx, rsp; StackCookie
0x180067523  call    __security_check_cookie
0x180067528  mov     rbx, [rsp+2D0h+arg_18]
0x180067530  add     rsp, 2B0h
0x180067537  pop     r15
0x180067539  pop     r14
0x18006753b  pop     rdi
0x18006753c  pop     rsi
0x18006753d  pop     rbp
0x18006753e  retn
```
