# CFileStreamBase::OpenForWrite(ushort const *,ulong,ulong,ulong)

- ea: `0x180064848`
- end: `0x18006499a`
- name: `?OpenForWrite@CFileStreamBase@@QEAAHPEBGKKK@Z`
- size: `338`
- prototype: `int(CFileStreamBase *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180063d20`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18001c270`
- `0x18005d2b0`
- `0x180064848`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800648be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800648f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064951`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800648be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800648f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064951`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064924`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180064924`

## pseudocode

```c
__int64 __fastcall CFileStreamBase::OpenForWrite(CFileStreamBase *this, const unsigned __int16 *a2)
{
  const char *v4; // rcx
  DWORD v5; // ecx
  HANDLE FileW; // rax
  unsigned int v7; // ebx
  int v9; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+48h] [rbp-38h] BYREF
  __int64 v11; // [rsp+50h] [rbp-30h]
  __int64 *v12; // [rsp+58h] [rbp-28h]
  __int64 v13; // [rsp+60h] [rbp-20h]
  int v14; // [rsp+68h] [rbp-18h]
  unsigned int *v15; // [rsp+70h] [rbp-10h]

  v9 = 0;
  v12 = &qword_180078340;
  v10 = 1;
  v15 = (unsigned int *)&v9;
  v11 = 0;
  v13 = 544438355;
  v14 = 56;
  CFrame::BaseEnter((CFrame *)&v10);
  if ( *((_QWORD *)this + 2) != -1 )
  {
    v5 = 1359;
LABEL_3:
    SetLastError(v5);
    *v15 = 0;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v14 = 60;
    FusionpTraceParameterCheck(v4);
    v5 = 87;
    goto LABEL_3;
  }
  SetLastError(0);
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 1u, 0x8000000u, 0);
  *((_QWORD *)this + 2) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078320);
  }
  else
  {
    *((_DWORD *)this + 6) = 4097;
    SetLastError(0);
    *v15 = 1;
  }
LABEL_9:
  v7 = *v15;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v10);
  return v7;
}

```

## disassembly

```asm
0x180064848  mov     [rsp-8+arg_10], rbx
0x18006484d  mov     [rsp-8+arg_18], rdi
0x180064852  push    rbp
0x180064853  mov     rbp, rsp
0x180064856  sub     rsp, 80h
0x18006485d  mov     rax, cs:__security_cookie
0x180064864  xor     rax, rsp
0x180064867  mov     [rbp+var_8], rax
0x18006486b  lea     rax, qword_180078340
0x180064872  mov     [rbp+var_40], 0
0x180064879  mov     [rbp+var_28], rax
0x18006487d  mov     rbx, rcx
0x180064880  lea     rax, [rbp+var_40]
0x180064884  mov     [rbp+var_38], 1
0x18006488b  lea     rcx, [rbp+var_38]; this
0x18006488f  mov     [rbp+var_10], rax
0x180064893  mov     rdi, rdx
0x180064896  mov     [rbp+var_30], 0
0x18006489e  mov     [rbp+var_20], 20737853h
0x1800648a6  mov     [rbp+var_18], 38h ; '8'
0x1800648ad  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800648b2  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800648b7  jz      short loc_1800648D9
0x1800648b9  mov     ecx, 54Fh; dwErrCode
0x1800648be  call    cs:__imp_SetLastError
0x1800648c5  nop     dword ptr [rax+rax+00h]
0x1800648ca  mov     rax, [rbp+var_10]
0x1800648ce  mov     dword ptr [rax], 0
0x1800648d4  jmp     loc_180064967
0x1800648d9  test    rdi, rdi
0x1800648dc  jnz     short loc_1800648EF
0x1800648de  mov     [rbp+var_18], 3Ch ; '<'
0x1800648e5  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800648ea  lea     ecx, [rdi+57h]
0x1800648ed  jmp     short loc_1800648BE
0x1800648ef  xor     ecx, ecx; dwErrCode
0x1800648f1  call    cs:__imp_SetLastError
0x1800648f8  nop     dword ptr [rax+rax+00h]
0x1800648fd  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180064906  xor     r9d, r9d; lpSecurityAttributes
0x180064909  mov     [rsp+80h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180064911  xor     r8d, r8d; dwShareMode
0x180064914  mov     edx, 40000000h; dwDesiredAccess
0x180064919  mov     [rsp+80h+dwCreationDisposition], 1; dwCreationDisposition
0x180064921  mov     rcx, rdi; lpFileName
0x180064924  call    cs:__imp_CreateFileW
0x18006492b  nop     dword ptr [rax+rax+00h]
0x180064930  mov     [rbx+10h], rax
0x180064934  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064938  jnz     short loc_180064948
0x18006493a  lea     rcx, off_180078320; struct _CALL_SITE_INFO *
0x180064941  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180064946  jmp     short loc_180064967
0x180064948  xor     ecx, ecx; dwErrCode
0x18006494a  mov     dword ptr [rbx+18h], 1001h
0x180064951  call    cs:__imp_SetLastError
0x180064958  nop     dword ptr [rax+rax+00h]
0x18006495d  mov     rax, [rbp+var_10]
0x180064961  mov     dword ptr [rax], 1
0x180064967  mov     rax, [rbp+var_10]
0x18006496b  lea     rcx, [rbp+var_38]; this
0x18006496f  mov     ebx, [rax]
0x180064971  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180064976  mov     eax, ebx
0x180064978  mov     rcx, [rbp+var_8]
0x18006497c  xor     rcx, rsp; StackCookie
0x18006497f  call    __security_check_cookie
0x180064984  lea     r11, [rsp+80h+var_s0]
0x18006498c  mov     rbx, [r11+20h]
0x180064990  mov     rdi, [r11+28h]
0x180064994  mov     rsp, r11
0x180064997  pop     rbp
0x180064998  retn
```
