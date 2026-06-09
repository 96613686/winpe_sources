# FusionpTraceCOMFailureVaBig(long,char const *,char *)

- ea: `0x180066f2c`
- end: `0x180067167`
- name: `?FusionpTraceCOMFailureVaBig@@YAXJPEBDPEAD@Z`
- size: `571`
- prototype: `void __fastcall(DWORD dwMessageId, const char *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005c140`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x180011864`
- `0x180059760`
- `0x180066f2c`
- `0x18006a110`

## import_xrefs

- `ntdll!_vsnprintf_s` at `0x18006701d`
- `ntdll!_vsnprintf_s` at `0x18006701d`
- `ntdll!_snprintf_s` at `0x180066fec`
- `ntdll!_snprintf_s` at `0x1800670a8`
- `ntdll!_snprintf_s` at `0x180066fec`
- `ntdll!_snprintf_s` at `0x1800670a8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006710f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006710f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180066fc1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180066fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066f60`

## string_xrefs

- `0x180067029`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n`
- `0x180067039`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n`

## pseudocode

```c
void __fastcall FusionpTraceCOMFailureVaBig(DWORD dwMessageId, const char *Format, va_list ArgList)
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
  char v17[256]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR Buffer[256]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v19[512]; // [rsp+2A0h] [rbp+1A0h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v14 = 0;
  v13 = 0;
  FusionpGetProcessImageFileName(&SearchString);
  v17[0] = 0;
  Buffer[0] = 0;
  v19[0] = 0;
  if ( !FormatMessageA(0x10FFu, 0, dwMessageId, 0, Buffer, 0x100u, 0) )
  {
    _snprintf_s(Buffer, 0x100u, 0xFFu, "<Untranslatable(non-existed or too long) HRESULT: 0x%08lx>", dwMessageId);
    Buffer[255] = 0;
  }
  v17[0] = 0;
  if ( Format )
  {
    _vsnprintf_s(v17, 0x100u, 0xFFu, Format, ArgList);
    v7 = "%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n";
    v17[255] = 0;
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
    0x200u,
    0x1FFu,
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
  v19[511] = 0;
  FusionpDbgPrintEx(0x80000010, "%s", v19);
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
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007C820);
      hFile = v9;
    }
  }
}

```

## disassembly

```asm
0x180066f2c  mov     [rsp-8+arg_18], rbx
0x180066f31  push    rbp
0x180066f32  push    rsi
0x180066f33  push    rdi
0x180066f34  push    r14
0x180066f36  push    r15
0x180066f38  lea     rbp, [rsp-3B0h]
0x180066f40  sub     rsp, 4B0h
0x180066f47  mov     rax, cs:__security_cookie
0x180066f4e  xor     rax, rsp
0x180066f51  mov     [rbp+3D0h+var_30], rax
0x180066f58  mov     rsi, r8
0x180066f5b  mov     rbx, rdx
0x180066f5e  mov     edi, ecx
0x180066f60  call    cs:__imp_GetCurrentThreadId
0x180066f67  nop     dword ptr [rax+rax+00h]
0x180066f6c  xorps   xmm0, xmm0
0x180066f6f  lea     rcx, [rbp+3D0h+SearchString]; SearchString
0x180066f73  mov     r14d, eax
0x180066f76  xor     eax, eax
0x180066f78  mov     [rbp+3D0h+var_450], rax
0x180066f7c  movups  [rsp+4D0h+var_460], xmm0
0x180066f81  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x180066f86  xor     r15d, r15d
0x180066f89  lea     rax, [rbp+3D0h+Buffer]
0x180066f90  mov     [rsp+4D0h+Arguments], r15; Arguments
0x180066f95  xor     r9d, r9d; dwLanguageId
0x180066f98  mov     dword ptr [rsp+4D0h+nSize], 100h; nSize
0x180066fa0  mov     r8d, edi; dwMessageId
0x180066fa3  xor     edx, edx; lpSource
0x180066fa5  mov     [rsp+4D0h+lpBuffer], rax; lpBuffer
0x180066faa  mov     ecx, 10FFh; dwFlags
0x180066faf  mov     [rbp+3D0h+var_430], r15b
0x180066fb3  mov     [rbp+3D0h+Buffer], r15b
0x180066fba  mov     [rbp+3D0h+var_230], r15b
0x180066fc1  call    cs:__imp_FormatMessageA
0x180066fc8  nop     dword ptr [rax+rax+00h]
0x180066fcd  test    eax, eax
0x180066fcf  jnz     short loc_180066FFF
0x180066fd1  mov     edx, 100h; BufferCount
0x180066fd6  mov     dword ptr [rsp+4D0h+lpBuffer], edi
0x180066fda  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x180066fe1  lea     rcx, [rbp+3D0h+Buffer]; Buffer
0x180066fe8  lea     r8d, [rdx-1]; MaxCount
0x180066fec  call    cs:__imp__snprintf_s
0x180066ff3  nop     dword ptr [rax+rax+00h]
0x180066ff8  mov     [rbp+3D0h+var_231], r15b
0x180066fff  mov     [rbp+3D0h+var_430], r15b
0x180067003  test    rbx, rbx
0x180067006  jz      short loc_180067039
0x180067008  mov     edx, 100h; BufferCount
0x18006700d  mov     [rsp+4D0h+lpBuffer], rsi; ArgList
0x180067012  mov     r9, rbx; Format
0x180067015  lea     rcx, [rbp+3D0h+var_430]; Buffer
0x180067019  lea     r8d, [rdx-1]; MaxCount
0x18006701d  call    cs:__imp__vsnprintf_s
0x180067024  nop     dword ptr [rax+rax+00h]
0x180067029  lea     rbx, aSDFunctionSIub; "%s(%d): [function %s %Iubit process %wZ"...
0x180067030  mov     [rbp+3D0h+var_331], r15b
0x180067037  jmp     short loc_180067040
0x180067039  lea     rbx, aSDFunctionSIub_1; "%s(%d): [function %s %Iubit process %wZ"...
0x180067040  lea     rcx, [rsp+4D0h+var_460]; struct _FRAME_INFO *
0x180067045  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x18006704a  lea     rax, [rbp+3D0h+var_430]
0x18006704e  mov     edx, 200h; BufferCount
0x180067053  mov     [rsp+4D0h+var_470], rax
0x180067058  lea     rcx, [rbp+3D0h+var_230]; Buffer
0x18006705f  lea     rax, [rbp+3D0h+Buffer]
0x180067066  mov     r9, rbx; Format
0x180067069  mov     [rsp+4D0h+var_478], rax
0x18006706e  lea     rax, [rbp+3D0h+SearchString]
0x180067072  mov     [rsp+4D0h+var_480], edi
0x180067076  lea     r8d, [rdx-1]; MaxCount
0x18006707a  mov     [rsp+4D0h+var_488], r14d
0x18006707f  mov     [rsp+4D0h+var_490], rax
0x180067084  mov     rax, qword ptr [rsp+4D0h+var_460+8]
0x180067089  mov     [rsp+4D0h+var_498], 40h ; '@'
0x180067092  mov     [rsp+4D0h+Arguments], rax
0x180067097  mov     eax, dword ptr [rbp+3D0h+var_450]
0x18006709a  mov     dword ptr [rsp+4D0h+nSize], eax
0x18006709e  mov     rax, qword ptr [rsp+4D0h+var_460]
0x1800670a3  mov     [rsp+4D0h+lpBuffer], rax
0x1800670a8  call    cs:__imp__snprintf_s
0x1800670af  nop     dword ptr [rax+rax+00h]
0x1800670b4  lea     r8, [rbp+3D0h+var_230]
0x1800670bb  mov     [rbp+3D0h+var_31], r15b
0x1800670c2  lea     rdx, aS; "%s"
0x1800670c9  mov     ecx, 80000010h; unsigned int
0x1800670ce  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800670d3  mov     rcx, cs:hFile; hFile
0x1800670da  lea     rax, [rcx-1]
0x1800670de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800670e2  ja      short loc_180067140
0x1800670e4  mov     [rbp+3D0h+NumberOfBytesWritten], r15d
0x1800670e8  lea     rax, [rbp+3D0h+var_230]
0x1800670ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800670f3  inc     r8
0x1800670f6  cmp     [rax+r8], r15b
0x1800670fa  jnz     short loc_1800670F3
0x1800670fc  inc     r8d; nNumberOfBytesToWrite
0x1800670ff  mov     [rsp+4D0h+lpBuffer], r15; lpOverlapped
0x180067104  lea     r9, [rbp+3D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180067108  lea     rdx, [rbp+3D0h+var_230]; lpBuffer
0x18006710f  call    cs:__imp_WriteFile
0x180067116  nop     dword ptr [rax+rax+00h]
0x18006711b  test    eax, eax
0x18006711d  jnz     short loc_180067140
0x18006711f  mov     rbx, cs:hFile
0x180067126  lea     rcx, off_18007C820; struct _CALL_SITE_INFO *
0x18006712d  mov     cs:hFile, r15
0x180067134  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180067139  mov     cs:hFile, rbx
0x180067140  mov     rcx, [rbp+3D0h+var_30]
0x180067147  xor     rcx, rsp; StackCookie
0x18006714a  call    __security_check_cookie
0x18006714f  mov     rbx, [rsp+4D0h+arg_18]
0x180067157  add     rsp, 4B0h
0x18006715e  pop     r15
0x180067160  pop     r14
0x180067162  pop     rdi
0x180067163  pop     rsi
0x180067164  pop     rbp
0x180067165  retn
```
