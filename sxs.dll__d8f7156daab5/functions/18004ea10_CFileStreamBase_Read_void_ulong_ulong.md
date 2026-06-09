# CFileStreamBase::Read(void *,ulong,ulong *)

- ea: `0x18004ea10`
- end: `0x18004eb70`
- name: `?Read@CFileStreamBase@@UEAAJPEAXKPEAK@Z`
- size: `352`
- prototype: `int(CFileStreamBase *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18002e98c`
- `0x18004ea10`
- `0x18005cc58`
- `0x180067170`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18004eaea`
- `ntdll!RtlPopFrame` at `0x18004eaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eb36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eb5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ea91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004eb5f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004eab1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004eab1`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  DWORD v8; // ecx
  unsigned int v9; // ebx
  DWORD LastError; // edi
  int v12; // ecx
  BOOL v13; // [rsp+30h] [rbp-68h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-64h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+38h] [rbp-60h] BYREF
  __int64 v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  BOOL *v18; // [rsp+60h] [rbp-38h]

  Frame.Flags = 1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071EB0;
  Frame.Previous = 0;
  v16 = 544438355;
  v17 = 260;
  v18 = &v13;
  v13 = 0;
  CFrame::BaseEnter((CFrame *)&Frame);
  NumberOfBytesRead = 0;
  if ( a4 )
    *a4 = 0;
  if ( this[2] == (HANDLE)-1LL )
  {
    *v18 = -2147023537;
  }
  else
  {
    SetLastError(0);
    if ( ReadFile(this[2], a2, a3, &NumberOfBytesRead, 0) )
    {
      v8 = NumberOfBytesRead;
      if ( a4 )
        *a4 = NumberOfBytesRead;
      v13 = v8 == 0;
    }
    else
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&Frame);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_1800782A0);
    }
  }
  v9 = v13;
  if ( g_FusionEnterExitTracingEnabled )
  {
    LastError = GetLastError();
    v12 = *v18;
    if ( *v18 < 0 )
      FusionpTraceCOMFailure(v12, 0);
    else
      FusionpTraceCallCOMSuccessfulExit(v12, 0);
    SetLastError(LastError);
  }
  RtlPopFrame(&Frame);
  return v9;
}

```

## disassembly

```asm
0x18004ea10  mov     r11, rsp
0x18004ea13  push    rbx
0x18004ea14  push    rbp
0x18004ea15  push    rsi
0x18004ea16  push    rdi
0x18004ea17  push    r14
0x18004ea19  sub     rsp, 70h
0x18004ea1d  mov     rax, cs:__security_cookie
0x18004ea24  xor     rax, rsp
0x18004ea27  mov     [rsp+98h+var_30], rax
0x18004ea2c  mov     [rsp+98h+Frame.Flags], 1
0x18004ea34  lea     rax, qword_180071EB0
0x18004ea3b  mov     [r11-50h], rax
0x18004ea3f  xor     r14d, r14d
0x18004ea42  lea     rax, [r11-68h]
0x18004ea46  mov     [r11-58h], r14
0x18004ea4a  mov     rdi, rcx
0x18004ea4d  mov     qword ptr [r11-48h], 20737853h
0x18004ea55  mov     [rsp+98h+var_40], 104h
0x18004ea5d  lea     rcx, [r11-60h]; this
0x18004ea61  mov     [r11-38h], rax
0x18004ea65  mov     rbx, r9
0x18004ea68  mov     ebp, r8d
0x18004ea6b  mov     [r11-68h], r14d
0x18004ea6f  mov     rsi, rdx
0x18004ea72  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004ea77  mov     [rsp+98h+NumberOfBytesRead], r14d
0x18004ea7c  test    rbx, rbx
0x18004ea7f  jz      short loc_18004EA84
0x18004ea81  mov     [rbx], r14d
0x18004ea84  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18004ea89  jz      loc_18004EB11
0x18004ea8f  xor     ecx, ecx; dwErrCode
0x18004ea91  call    cs:__imp_SetLastError
0x18004ea98  nop     dword ptr [rax+rax+00h]
0x18004ea9d  mov     rcx, [rdi+10h]; hFile
0x18004eaa1  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004eaa6  mov     r8d, ebp; nNumberOfBytesToRead
0x18004eaa9  mov     [rsp+98h+lpOverlapped], r14; lpOverlapped
0x18004eaae  mov     rdx, rsi; lpBuffer
0x18004eab1  call    cs:__imp_ReadFile
0x18004eab8  nop     dword ptr [rax+rax+00h]
0x18004eabd  test    eax, eax
0x18004eabf  jz      short loc_18004EB1E
0x18004eac1  mov     ecx, [rsp+98h+NumberOfBytesRead]
0x18004eac5  test    rbx, rbx
0x18004eac8  jz      short loc_18004EACC
0x18004eaca  mov     [rbx], ecx
0x18004eacc  mov     eax, r14d
0x18004eacf  test    ecx, ecx
0x18004ead1  setz    al
0x18004ead4  mov     [rsp+98h+var_68], eax
0x18004ead8  cmp     cs:g_FusionEnterExitTracingEnabled, r14b
0x18004eadf  mov     ebx, [rsp+98h+var_68]
0x18004eae3  jnz     short loc_18004EB36
0x18004eae5  lea     rcx, [rsp+98h+Frame]; Frame
0x18004eaea  call    cs:__imp_RtlPopFrame
0x18004eaf1  nop     dword ptr [rax+rax+00h]
0x18004eaf6  mov     eax, ebx
0x18004eaf8  mov     rcx, [rsp+98h+var_30]
0x18004eafd  xor     rcx, rsp; StackCookie
0x18004eb00  call    __security_check_cookie
0x18004eb05  add     rsp, 70h
0x18004eb09  pop     r14
0x18004eb0b  pop     rdi
0x18004eb0c  pop     rsi
0x18004eb0d  pop     rbp
0x18004eb0e  pop     rbx
0x18004eb0f  retn
0x18004eb11  mov     rax, [rsp+98h+var_38]
0x18004eb16  mov     dword ptr [rax], 8007054Fh
0x18004eb1c  jmp     short loc_18004EAD8
0x18004eb1e  lea     rcx, [rsp+98h+Frame]; this
0x18004eb23  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x18004eb28  lea     rcx, off_1800782A0; struct _CALL_SITE_INFO *
0x18004eb2f  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18004eb34  jmp     short loc_18004EAD8
0x18004eb36  call    cs:__imp_GetLastError
0x18004eb3d  nop     dword ptr [rax+rax+00h]
0x18004eb42  mov     rcx, [rsp+98h+var_38]
0x18004eb47  xor     edx, edx; char *
0x18004eb49  mov     edi, eax
0x18004eb4b  mov     ecx, [rcx]; int
0x18004eb4d  test    ecx, ecx
0x18004eb4f  js      short loc_18004EB58
0x18004eb51  call    ?FusionpTraceCallCOMSuccessfulExit@@YAXJPEBDZZ; FusionpTraceCallCOMSuccessfulExit(long,char const *,...)
0x18004eb56  jmp     short loc_18004EB5D
0x18004eb58  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18004eb5d  mov     ecx, edi; dwErrCode
0x18004eb5f  call    cs:__imp_SetLastError
0x18004eb66  nop     dword ptr [rax+rax+00h]
0x18004eb6b  jmp     loc_18004EAE5
```
