# CFileStreamBase::OpenForRead(ushort const *,ulong,ulong,ulong,ulong &,unsigned __int64,...)

- ea: `0x18003ecc8`
- end: `0x18003eefa`
- name: `?OpenForRead@CFileStreamBase@@QEAAHPEBGKKKAEAK_KZZ`
- size: `562`
- prototype: `__int64(CFileStreamBase *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int *, unsigned __int64, ...)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180015a80`
- `0x18003e424`
- `0x18005ae60`
- `0x180062568`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18003ecc8`
- `0x18005d2b0`
- `0x18005d38c`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18003edf3`
- `ntdll!RtlPopFrame` at `0x18003edf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eda4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eda4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eee0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003edc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ed64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003edc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ee5f`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18003ed94`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18003ed94`

## string_xrefs

- `0x18003ee9c`: `CFileStreamBase::OpenForRead`
- `0x18003eea8`: `SXS.DLL: %s(%ls) gave error %ld\n`

## pseudocode

```c
__int64 CFileStreamBase::OpenForRead(
        CFileStreamBase *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int64 a7,
        ...)
{
  const char *v11; // rcx
  DWORD LastError; // eax
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  DWORD v16; // ecx
  va_list v17; // rcx
  unsigned __int64 i; // rax
  bool v19; // zf
  DWORD v20; // eax
  int v21; // [rsp+38h] [rbp-59h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+40h] [rbp-51h] BYREF
  __int64 v23; // [rsp+58h] [rbp-39h]
  int v24; // [rsp+60h] [rbp-31h]
  unsigned int *v25; // [rsp+68h] [rbp-29h]
  _OWORD v26[2]; // [rsp+70h] [rbp-21h] BYREF
  va_list va; // [rsp+118h] [rbp+87h] BYREF

  va_start(va, a7);
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180070D50;
  v21 = 0;
  v25 = (unsigned int *)&v21;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v23 = 544438355;
  v24 = 108;
  CFrame::BaseEnter((CFrame *)&Frame);
  *a6 = 0;
  memset(v26, 0, sizeof(v26));
  if ( !a2 )
  {
    v24 = 114;
    FusionpTraceParameterCheck(v11);
    v16 = 87;
    goto LABEL_8;
  }
  if ( *((_QWORD *)this + 2) != -1 )
  {
    v16 = 1359;
LABEL_8:
    SetLastError(v16);
    *v25 = 0;
    goto LABEL_5;
  }
  SetLastError(0);
  DWORD2(v26[0]) = a5;
  LODWORD(v26[0]) = 32;
  *((_QWORD *)this + 2) = CreateFile2(a2, 0x80000000LL, a3, a4, v26);
  LastError = GetLastError();
  v19 = *((_QWORD *)this + 2) == -1;
  v13 = LastError;
  *((_DWORD *)this + 6) = 0;
  if ( !v19 )
    goto LABEL_4;
  if ( !LastError )
  {
    v13 = 2;
    SetLastError(2u);
  }
  va_copy(v17, va);
  for ( i = 0; ; ++i )
  {
    v19 = i == a7;
    if ( i >= a7 )
      break;
    v17 += 8;
    if ( v13 == *((_DWORD *)v17 - 2) )
    {
      v19 = i == a7;
      *a6 = v13;
      break;
    }
  }
  if ( v19 )
  {
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: %s(%ls) gave error %ld\n", "CFileStreamBase::OpenForRead", a2, v13);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&Frame, v13);
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078300);
  }
  else
  {
LABEL_4:
    SetLastError(0);
    *v25 = 1;
  }
LABEL_5:
  v14 = *v25;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v14 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v20 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v20, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v14;
}

```

## disassembly

```asm
0x18003ecc8  push    rbp
0x18003ecca  push    rbx
0x18003eccb  push    rsi
0x18003eccc  push    rdi
0x18003eccd  push    r14
0x18003eccf  push    r15
0x18003ecd1  lea     rbp, [rsp-17h]
0x18003ecd6  sub     rsp, 0A8h
0x18003ecdd  mov     rax, cs:__security_cookie
0x18003ece4  xor     rax, rsp
0x18003ece7  mov     [rbp+3Fh+var_40], rax
0x18003eceb  mov     r14, [rbp+3Fh+arg_28]
0x18003ecef  lea     rax, qword_180070D50
0x18003ecf6  mov     [rbp+3Fh+Frame.Context], rax
0x18003ecfa  mov     rdi, rcx
0x18003ecfd  lea     rax, [rbp+3Fh+var_98]
0x18003ed01  mov     [rbp+3Fh+var_98], 0
0x18003ed08  lea     rcx, [rbp+3Fh+Frame]; this
0x18003ed0c  mov     [rbp+3Fh+var_68], rax
0x18003ed10  mov     r15d, r9d
0x18003ed13  mov     [rbp+3Fh+Frame.Flags], 1
0x18003ed1a  mov     ebx, r8d
0x18003ed1d  mov     [rbp+3Fh+Frame.Previous], 0
0x18003ed25  mov     rsi, rdx
0x18003ed28  mov     [rbp+3Fh+var_78], 20737853h
0x18003ed30  mov     [rbp+3Fh+var_70], 6Ch ; 'l'
0x18003ed37  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18003ed3c  mov     dword ptr [r14], 0
0x18003ed43  xorps   xmm0, xmm0
0x18003ed46  movups  [rbp+3Fh+var_60], xmm0
0x18003ed4a  movups  [rbp+3Fh+var_50], xmm0
0x18003ed4e  test    rsi, rsi
0x18003ed51  jz      loc_18003EE3B
0x18003ed57  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18003ed5c  jnz     loc_18003EE1E
0x18003ed62  xor     ecx, ecx; dwErrCode
0x18003ed64  call    cs:__imp_SetLastError
0x18003ed6b  nop     dword ptr [rax+rax+00h]
0x18003ed70  mov     eax, [rbp+3Fh+arg_20]
0x18003ed73  mov     r9d, r15d
0x18003ed76  mov     dword ptr [rbp+3Fh+var_60+8], eax
0x18003ed79  mov     r8d, ebx
0x18003ed7c  lea     rax, [rbp+3Fh+var_60]
0x18003ed80  mov     dword ptr [rbp+3Fh+var_60], 20h ; ' '
0x18003ed87  mov     edx, 80000000h
0x18003ed8c  mov     [rsp+0D0h+var_B0], rax
0x18003ed91  mov     rcx, rsi
0x18003ed94  call    cs:__imp_CreateFile2
0x18003ed9b  nop     dword ptr [rax+rax+00h]
0x18003eda0  mov     [rdi+10h], rax
0x18003eda4  call    cs:__imp_GetLastError
0x18003edab  nop     dword ptr [rax+rax+00h]
0x18003edb0  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18003edb5  mov     ebx, eax
0x18003edb7  mov     dword ptr [rdi+18h], 0
0x18003edbe  jz      loc_18003EE4E
0x18003edc4  xor     ecx, ecx; dwErrCode
0x18003edc6  call    cs:__imp_SetLastError
0x18003edcd  nop     dword ptr [rax+rax+00h]
0x18003edd2  mov     rax, [rbp+3Fh+var_68]
0x18003edd6  mov     dword ptr [rax], 1
0x18003eddc  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18003ede3  mov     rax, [rbp+3Fh+var_68]
0x18003ede7  mov     ebx, [rax]
0x18003ede9  jnz     loc_18003EED0
0x18003edef  lea     rcx, [rbp+3Fh+Frame]; Frame
0x18003edf3  call    cs:__imp_RtlPopFrame
0x18003edfa  nop     dword ptr [rax+rax+00h]
0x18003edff  mov     eax, ebx
0x18003ee01  mov     rcx, [rbp+3Fh+var_40]
0x18003ee05  xor     rcx, rsp; StackCookie
0x18003ee08  call    __security_check_cookie
0x18003ee0d  add     rsp, 0A8h
0x18003ee14  pop     r15
0x18003ee16  pop     r14
0x18003ee18  pop     rdi
0x18003ee19  pop     rsi
0x18003ee1a  pop     rbx
0x18003ee1b  pop     rbp
0x18003ee1c  retn
0x18003ee1e  mov     ecx, 54Fh; dwErrCode
0x18003ee23  call    cs:__imp_SetLastError
0x18003ee2a  nop     dword ptr [rax+rax+00h]
0x18003ee2f  mov     rax, [rbp+3Fh+var_68]
0x18003ee33  mov     dword ptr [rax], 0
0x18003ee39  jmp     short loc_18003EDDC
0x18003ee3b  mov     [rbp+3Fh+var_70], 72h ; 'r'
0x18003ee42  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18003ee47  mov     ecx, 57h ; 'W'
0x18003ee4c  jmp     short loc_18003EE23
0x18003ee4e  mov     [rbp+3Fh+var_A0], 0
0x18003ee56  test    eax, eax
0x18003ee58  jnz     short loc_18003EE6B
0x18003ee5a  lea     ebx, [rax+2]
0x18003ee5d  mov     ecx, ebx; dwErrCode
0x18003ee5f  call    cs:__imp_SetLastError
0x18003ee66  nop     dword ptr [rax+rax+00h]
0x18003ee6b  lea     rcx, [rbp+3Fh+arg_38]
0x18003ee72  xor     eax, eax
0x18003ee74  cmp     rax, [rbp+3Fh+arg_30]
0x18003ee78  jnb     short loc_18003EE8F
0x18003ee7a  add     rcx, 8
0x18003ee7e  cmp     ebx, [rcx-8]
0x18003ee81  jz      short loc_18003EE88
0x18003ee83  inc     rax
0x18003ee86  jmp     short loc_18003EE74
0x18003ee88  cmp     rax, [rbp+3Fh+arg_30]
0x18003ee8c  mov     [r14], ebx
0x18003ee8f  jnz     loc_18003EDC4
0x18003ee95  mov     r9, rsi
0x18003ee98  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18003ee9c  lea     r8, aCfilestreambas_6; "CFileStreamBase::OpenForRead"
0x18003eea3  mov     ecx, 0C0000000h; unsigned int
0x18003eea8  lea     rdx, aSxsDllSLsGaveE; "SXS.DLL: %s(%ls) gave error %ld\n"
0x18003eeaf  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18003eeb4  mov     edx, ebx; unsigned int
0x18003eeb6  lea     rcx, [rbp+3Fh+Frame]; this
0x18003eeba  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18003eebf  lea     rcx, off_180078300; struct _CALL_SITE_INFO *
0x18003eec6  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18003eecb  jmp     loc_18003EDDC
0x18003eed0  test    ebx, ebx
0x18003eed2  jz      short loc_18003EEE0
0x18003eed4  xor     ecx, ecx; char *
0x18003eed6  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18003eedb  jmp     loc_18003EDEF
0x18003eee0  call    cs:__imp_GetLastError
0x18003eee7  nop     dword ptr [rax+rax+00h]
0x18003eeec  mov     ecx, eax; unsigned int
0x18003eeee  xor     edx, edx; Format
0x18003eef0  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18003eef5  jmp     loc_18003EDEF
```
