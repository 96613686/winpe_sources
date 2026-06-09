# FusionpTraceCOMFailureOriginationVaBig(long,char const *,char *)

- ea: `0x180066ce8`
- end: `0x180066f23`
- name: `?FusionpTraceCOMFailureOriginationVaBig@@YAXJPEBDPEAD@Z`
- size: `571`
- prototype: `void __fastcall(DWORD dwMessageId, const char *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005cdcc`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x180011864`
- `0x180059760`
- `0x180066ce8`
- `0x18006a110`

## import_xrefs

- `ntdll!_vsnprintf_s` at `0x180066dd9`
- `ntdll!_vsnprintf_s` at `0x180066dd9`
- `ntdll!_snprintf_s` at `0x180066da8`
- `ntdll!_snprintf_s` at `0x180066e64`
- `ntdll!_snprintf_s` at `0x180066da8`
- `ntdll!_snprintf_s` at `0x180066e64`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180066ecb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180066ecb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180066d7d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x180066d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066d1c`

## string_xrefs

- `0x180066de5`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s) %s\n`
- `0x180066df5`: `%s(%d): [function %s %Iubit process %wZ tid 0x%lx] COM Error 0x%08lx (%s)\n`

## pseudocode

```c
void __fastcall FusionpTraceCOMFailureOriginationVaBig(DWORD dwMessageId, const char *Format, va_list ArgList)
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
  FusionpDbgPrintEx(0xC0000000, "%s", v19);
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
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_18007C7E0);
      hFile = v9;
    }
  }
}

```

## disassembly

```asm
0x180066ce8  mov     [rsp-8+arg_18], rbx
0x180066ced  push    rbp
0x180066cee  push    rsi
0x180066cef  push    rdi
0x180066cf0  push    r14
0x180066cf2  push    r15
0x180066cf4  lea     rbp, [rsp-3B0h]
0x180066cfc  sub     rsp, 4B0h
0x180066d03  mov     rax, cs:__security_cookie
0x180066d0a  xor     rax, rsp
0x180066d0d  mov     [rbp+3D0h+var_30], rax
0x180066d14  mov     rsi, r8
0x180066d17  mov     rbx, rdx
0x180066d1a  mov     edi, ecx
0x180066d1c  call    cs:__imp_GetCurrentThreadId
0x180066d23  nop     dword ptr [rax+rax+00h]
0x180066d28  xorps   xmm0, xmm0
0x180066d2b  lea     rcx, [rbp+3D0h+SearchString]; SearchString
0x180066d2f  mov     r14d, eax
0x180066d32  xor     eax, eax
0x180066d34  mov     [rbp+3D0h+var_450], rax
0x180066d38  movups  [rsp+4D0h+var_460], xmm0
0x180066d3d  call    ?FusionpGetProcessImageFileName@@YAXPEAU_UNICODE_STRING@@@Z; FusionpGetProcessImageFileName(_UNICODE_STRING *)
0x180066d42  xor     r15d, r15d
0x180066d45  lea     rax, [rbp+3D0h+Buffer]
0x180066d4c  mov     [rsp+4D0h+Arguments], r15; Arguments
0x180066d51  xor     r9d, r9d; dwLanguageId
0x180066d54  mov     dword ptr [rsp+4D0h+nSize], 100h; nSize
0x180066d5c  mov     r8d, edi; dwMessageId
0x180066d5f  xor     edx, edx; lpSource
0x180066d61  mov     [rsp+4D0h+lpBuffer], rax; lpBuffer
0x180066d66  mov     ecx, 10FFh; dwFlags
0x180066d6b  mov     [rbp+3D0h+var_430], r15b
0x180066d6f  mov     [rbp+3D0h+Buffer], r15b
0x180066d76  mov     [rbp+3D0h+var_230], r15b
0x180066d7d  call    cs:__imp_FormatMessageA
0x180066d84  nop     dword ptr [rax+rax+00h]
0x180066d89  test    eax, eax
0x180066d8b  jnz     short loc_180066DBB
0x180066d8d  mov     edx, 100h; BufferCount
0x180066d92  mov     dword ptr [rsp+4D0h+lpBuffer], edi
0x180066d96  lea     r9, aUntranslatable_0; "<Untranslatable(non-existed or too long"...
0x180066d9d  lea     rcx, [rbp+3D0h+Buffer]; Buffer
0x180066da4  lea     r8d, [rdx-1]; MaxCount
0x180066da8  call    cs:__imp__snprintf_s
0x180066daf  nop     dword ptr [rax+rax+00h]
0x180066db4  mov     [rbp+3D0h+var_231], r15b
0x180066dbb  mov     [rbp+3D0h+var_430], r15b
0x180066dbf  test    rbx, rbx
0x180066dc2  jz      short loc_180066DF5
0x180066dc4  mov     edx, 100h; BufferCount
0x180066dc9  mov     [rsp+4D0h+lpBuffer], rsi; ArgList
0x180066dce  mov     r9, rbx; Format
0x180066dd1  lea     rcx, [rbp+3D0h+var_430]; Buffer
0x180066dd5  lea     r8d, [rdx-1]; MaxCount
0x180066dd9  call    cs:__imp__vsnprintf_s
0x180066de0  nop     dword ptr [rax+rax+00h]
0x180066de5  lea     rbx, aSDFunctionSIub; "%s(%d): [function %s %Iubit process %wZ"...
0x180066dec  mov     [rbp+3D0h+var_331], r15b
0x180066df3  jmp     short loc_180066DFC
0x180066df5  lea     rbx, aSDFunctionSIub_1; "%s(%d): [function %s %Iubit process %wZ"...
0x180066dfc  lea     rcx, [rsp+4D0h+var_460]; struct _FRAME_INFO *
0x180066e01  call    ?FusionpGetActiveFrameInfo@@YA_NAEAU_FRAME_INFO@@@Z; FusionpGetActiveFrameInfo(_FRAME_INFO &)
0x180066e06  lea     rax, [rbp+3D0h+var_430]
0x180066e0a  mov     edx, 200h; BufferCount
0x180066e0f  mov     [rsp+4D0h+var_470], rax
0x180066e14  lea     rcx, [rbp+3D0h+var_230]; Buffer
0x180066e1b  lea     rax, [rbp+3D0h+Buffer]
0x180066e22  mov     r9, rbx; Format
0x180066e25  mov     [rsp+4D0h+var_478], rax
0x180066e2a  lea     rax, [rbp+3D0h+SearchString]
0x180066e2e  mov     [rsp+4D0h+var_480], edi
0x180066e32  lea     r8d, [rdx-1]; MaxCount
0x180066e36  mov     [rsp+4D0h+var_488], r14d
0x180066e3b  mov     [rsp+4D0h+var_490], rax
0x180066e40  mov     rax, qword ptr [rsp+4D0h+var_460+8]
0x180066e45  mov     [rsp+4D0h+var_498], 40h ; '@'
0x180066e4e  mov     [rsp+4D0h+Arguments], rax
0x180066e53  mov     eax, dword ptr [rbp+3D0h+var_450]
0x180066e56  mov     dword ptr [rsp+4D0h+nSize], eax
0x180066e5a  mov     rax, qword ptr [rsp+4D0h+var_460]
0x180066e5f  mov     [rsp+4D0h+lpBuffer], rax
0x180066e64  call    cs:__imp__snprintf_s
0x180066e6b  nop     dword ptr [rax+rax+00h]
0x180066e70  lea     r8, [rbp+3D0h+var_230]
0x180066e77  mov     [rbp+3D0h+var_31], r15b
0x180066e7e  lea     rdx, aS; "%s"
0x180066e85  mov     ecx, 0C0000000h; unsigned int
0x180066e8a  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180066e8f  mov     rcx, cs:hFile; hFile
0x180066e96  lea     rax, [rcx-1]
0x180066e9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180066e9e  ja      short loc_180066EFC
0x180066ea0  mov     [rbp+3D0h+NumberOfBytesWritten], r15d
0x180066ea4  lea     rax, [rbp+3D0h+var_230]
0x180066eab  or      r8, 0FFFFFFFFFFFFFFFFh
0x180066eaf  inc     r8
0x180066eb2  cmp     [rax+r8], r15b
0x180066eb6  jnz     short loc_180066EAF
0x180066eb8  inc     r8d; nNumberOfBytesToWrite
0x180066ebb  mov     [rsp+4D0h+lpBuffer], r15; lpOverlapped
0x180066ec0  lea     r9, [rbp+3D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180066ec4  lea     rdx, [rbp+3D0h+var_230]; lpBuffer
0x180066ecb  call    cs:__imp_WriteFile
0x180066ed2  nop     dword ptr [rax+rax+00h]
0x180066ed7  test    eax, eax
0x180066ed9  jnz     short loc_180066EFC
0x180066edb  mov     rbx, cs:hFile
0x180066ee2  lea     rcx, off_18007C7E0; struct _CALL_SITE_INFO *
0x180066ee9  mov     cs:hFile, r15
0x180066ef0  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180066ef5  mov     cs:hFile, rbx
0x180066efc  mov     rcx, [rbp+3D0h+var_30]
0x180066f03  xor     rcx, rsp; StackCookie
0x180066f06  call    __security_check_cookie
0x180066f0b  mov     rbx, [rsp+4D0h+arg_18]
0x180066f13  add     rsp, 4B0h
0x180066f1a  pop     r15
0x180066f1c  pop     r14
0x180066f1e  pop     rdi
0x180066f1f  pop     rsi
0x180066f20  pop     rbp
0x180066f21  retn
```
