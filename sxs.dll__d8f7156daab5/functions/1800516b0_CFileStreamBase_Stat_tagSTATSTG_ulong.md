# CFileStreamBase::Stat(tagSTATSTG *,ulong)

- ea: `0x1800516b0`
- end: `0x1800518e3`
- name: `?Stat@CFileStreamBase@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `563`
- prototype: `int(CFileStreamBase *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18002e98c`
- `0x1800516b0`
- `0x18005cc58`
- `0x18005d2b0`
- `0x180067170`
- `0x18006a0f5`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x1800517fb`
- `ntdll!RtlPopFrame` at `0x1800517fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800518d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800518d2`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180051779`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180051779`

## string_xrefs

- `0x180051869`: `SXS.DLL: %s() does not handle STATFLAG_NONE; returning E_NOTIMPL.\n`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::Stat(CFileStreamBase *this, struct tagSTATSTG *a2, int a3)
{
  const char *v6; // rcx
  unsigned int v7; // ebx
  DWORD LastError; // edi
  int v10; // ecx
  int v11; // [rsp+20h] [rbp-39h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-31h] BYREF
  __int64 v13; // [rsp+40h] [rbp-19h]
  int v14; // [rsp+48h] [rbp-11h]
  int *v15; // [rsp+50h] [rbp-9h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp-1h] BYREF

  v11 = -2147023537;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180072220;
  Frame.Flags = 1;
  v15 = &v11;
  Frame.Previous = 0;
  v13 = 544438355;
  v14 = 475;
  CFrame::BaseEnter((CFrame *)&Frame);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( a2 )
    memset_0(a2, 0, 0x50u);
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v14 = 481;
LABEL_13:
    FusionpTraceParameterCheck(v6);
    *v15 = -2147024809;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v14 = 482;
    goto LABEL_13;
  }
  if ( (a3 & 1) != 0 )
  {
    if ( *((_QWORD *)this + 2) == -1 )
    {
      *v15 = -2147023537;
    }
    else
    {
      SetLastError(0);
      if ( GetFileInformationByHandle(*((HANDLE *)this + 2), &FileInformation) )
      {
        *((_DWORD *)a2 + 4) = FileInformation.nFileSizeLow;
        *((_DWORD *)a2 + 5) = FileInformation.nFileSizeHigh;
        *((_QWORD *)a2 + 3) = FileInformation.ftLastWriteTime;
        *((_QWORD *)a2 + 4) = FileInformation.ftCreationTime;
        *((_QWORD *)a2 + 5) = FileInformation.ftLastAccessTime;
        *(_QWORD *)a2 = 0;
        *((_DWORD *)a2 + 2) = 2;
        *((_DWORD *)a2 + 12) = *((_DWORD *)this + 6);
        *((_DWORD *)a2 + 13) = 1;
        *((_QWORD *)a2 + 9) = 0;
        v11 = 0;
        *(GUID *)((char *)a2 + 56) = GUID_NULL;
      }
      else
      {
        CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&Frame);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078220);
      }
    }
  }
  else
  {
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: %s() does not handle STATFLAG_NONE; returning E_NOTIMPL.\n",
      "CFileStreamBase::Stat");
    v11 = -2147467263;
  }
LABEL_9:
  v7 = v11;
  if ( g_FusionEnterExitTracingEnabled )
  {
    LastError = GetLastError();
    v10 = *v15;
    if ( *v15 < 0 )
      FusionpTraceCOMFailure(v10, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v10, 0);
    SetLastError(LastError);
  }
  RtlPopFrame(&Frame);
  return v7;
}

```

## disassembly

```asm
0x1800516b0  mov     [rsp-8+arg_10], rbx
0x1800516b5  push    rbp
0x1800516b6  push    rsi
0x1800516b7  push    rdi
0x1800516b8  lea     rbp, [rsp-47h]
0x1800516bd  sub     rsp, 0A0h
0x1800516c4  mov     rax, cs:__security_cookie
0x1800516cb  xor     rax, rsp
0x1800516ce  mov     [rbp+57h+var_20], rax
0x1800516d2  lea     rax, qword_180072220
0x1800516d9  mov     [rbp+57h+var_90], 8007054Fh
0x1800516e0  mov     [rbp+57h+Frame.Context], rax
0x1800516e4  mov     rdi, rcx
0x1800516e7  lea     rax, [rbp+57h+var_90]
0x1800516eb  mov     [rbp+57h+Frame.Flags], 1
0x1800516f2  lea     rcx, [rbp+57h+Frame]; this
0x1800516f6  mov     [rbp+57h+var_60], rax
0x1800516fa  mov     esi, r8d
0x1800516fd  mov     [rbp+57h+Frame.Previous], 0
0x180051705  mov     rbx, rdx
0x180051708  mov     [rbp+57h+var_70], 20737853h
0x180051710  mov     [rbp+57h+var_68], 1DBh
0x180051717  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005171c  xorps   xmm0, xmm0
0x18005171f  xor     eax, eax
0x180051721  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x180051724  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x180051728  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18005172c  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x180051730  test    rbx, rbx
0x180051733  jnz     loc_180051829
0x180051739  test    esi, 0FFFFFFFEh
0x18005173f  jnz     loc_18005183C
0x180051745  test    rbx, rbx
0x180051748  jz      loc_180051845
0x18005174e  test    sil, 1
0x180051752  jz      loc_18005185D
0x180051758  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18005175d  jz      loc_180051881
0x180051763  xor     ecx, ecx; dwErrCode
0x180051765  call    cs:__imp_SetLastError
0x18005176c  nop     dword ptr [rax+rax+00h]
0x180051771  mov     rcx, [rdi+10h]; hFile
0x180051775  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x180051779  call    cs:__imp_GetFileInformationByHandle
0x180051780  nop     dword ptr [rax+rax+00h]
0x180051785  test    eax, eax
0x180051787  jz      loc_180051890
0x18005178d  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x180051790  mov     [rbx+10h], eax
0x180051793  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x180051796  mov     [rbx+14h], eax
0x180051799  mov     rax, qword ptr [rbp+57h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18005179d  mov     [rbx+18h], rax
0x1800517a1  mov     rax, qword ptr [rbp+57h+FileInformation.ftCreationTime.dwLowDateTime]
0x1800517a5  mov     [rbx+20h], rax
0x1800517a9  mov     rax, qword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x1800517ad  mov     [rbx+28h], rax
0x1800517b1  mov     qword ptr [rbx], 0
0x1800517b8  mov     dword ptr [rbx+8], 2
0x1800517bf  mov     eax, [rdi+18h]
0x1800517c2  mov     [rbx+30h], eax
0x1800517c5  mov     dword ptr [rbx+34h], 1
0x1800517cc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800517d3  mov     qword ptr [rbx+48h], 0
0x1800517db  mov     [rbp+57h+var_90], 0
0x1800517e2  movdqu  xmmword ptr [rbx+38h], xmm0
0x1800517e7  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800517ee  mov     ebx, [rbp+57h+var_90]
0x1800517f1  jnz     loc_1800518AA
0x1800517f7  lea     rcx, [rbp+57h+Frame]; Frame
0x1800517fb  call    cs:__imp_RtlPopFrame
0x180051802  nop     dword ptr [rax+rax+00h]
0x180051807  mov     eax, ebx
0x180051809  mov     rcx, [rbp+57h+var_20]
0x18005180d  xor     rcx, rsp; StackCookie
0x180051810  call    __security_check_cookie
0x180051815  mov     rbx, [rsp+0B0h+arg_10]
0x18005181d  add     rsp, 0A0h
0x180051824  pop     rdi
0x180051825  pop     rsi
0x180051826  pop     rbp
0x180051827  retn
0x180051829  xor     edx, edx; Val
0x18005182b  mov     rcx, rbx; void *
0x18005182e  lea     r8d, [rdx+50h]; Size
0x180051832  call    memset_0
0x180051837  jmp     loc_180051739
0x18005183c  mov     [rbp+57h+var_68], 1E1h
0x180051843  jmp     short loc_18005184C
0x180051845  mov     [rbp+57h+var_68], 1E2h
0x18005184c  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180051851  mov     rax, [rbp+57h+var_60]
0x180051855  mov     dword ptr [rax], 80070057h
0x18005185b  jmp     short loc_1800517E7
0x18005185d  lea     r8, aCfilestreambas_4; "CFileStreamBase::Stat"
0x180051864  mov     ecx, 0C0000000h; unsigned int
0x180051869  lea     rdx, aSxsDllSDoesNot; "SXS.DLL: %s() does not handle STATFLAG_"...
0x180051870  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180051875  mov     [rbp+57h+var_90], 80004001h
0x18005187c  jmp     loc_1800517E7
0x180051881  mov     rax, [rbp+57h+var_60]
0x180051885  mov     dword ptr [rax], 8007054Fh
0x18005188b  jmp     loc_1800517E7
0x180051890  lea     rcx, [rbp+57h+Frame]; this
0x180051894  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180051899  lea     rcx, off_180078220; struct _CALL_SITE_INFO *
0x1800518a0  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800518a5  jmp     loc_1800517E7
0x1800518aa  call    cs:__imp_GetLastError
0x1800518b1  nop     dword ptr [rax+rax+00h]
0x1800518b6  mov     rcx, [rbp+57h+var_60]
0x1800518ba  xor     edx, edx; char *
0x1800518bc  mov     edi, eax
0x1800518be  mov     ecx, [rcx]; int
0x1800518c0  test    ecx, ecx
0x1800518c2  js      short loc_1800518CB
0x1800518c4  call    ?FusionpTraceCallCOMSuccessfulExit@@YAXJPEBDZZ; FusionpTraceCallCOMSuccessfulExit(long,char const *,...)
0x1800518c9  jmp     short loc_1800518D0
0x1800518cb  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x1800518d0  mov     ecx, edi; dwErrCode
0x1800518d2  call    cs:__imp_SetLastError
0x1800518d9  nop     dword ptr [rax+rax+00h]
0x1800518de  jmp     loc_1800517F7
```
