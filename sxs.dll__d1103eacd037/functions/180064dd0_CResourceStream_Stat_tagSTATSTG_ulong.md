# CResourceStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180064dd0`
- end: `0x180064f96`
- name: `?Stat@CResourceStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `454`
- prototype: `int(CResourceStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18002ff90`
- `0x18005cc58`
- `0x18005d2b0`
- `0x180064dd0`
- `0x18006a0f5`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064ebc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180064ed2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180064ed2`

## string_xrefs

- `0x180064ea2`: `SXS.DLL: %s() does not handle STATFLAG_NONE; returning E_NOTIMPL.\n`

## pseudocode

```c
__int64 __fastcall CResourceStream::Stat(CResourceStream *this, struct tagSTATSTG *a2, int a3)
{
  const char *v6; // rcx
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-29h] BYREF
  int v10; // [rsp+28h] [rbp-21h] BYREF
  __int64 v11; // [rsp+30h] [rbp-19h]
  __int64 *v12; // [rsp+38h] [rbp-11h]
  __int64 v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+48h] [rbp-1h]
  int *v15; // [rsp+50h] [rbp+7h]
  _OWORD FileInformation[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v17; // [rsp+78h] [rbp+2Fh]

  v9 = -2147418113;
  v12 = &qword_1800783A8;
  v10 = 1;
  v15 = &v9;
  v11 = 0;
  v13 = 544438355;
  v14 = 140;
  CFrame::BaseEnter((CFrame *)&v10);
  v17 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( a2 )
    memset_0(a2, 0, 0x50u);
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v14 = 146;
LABEL_5:
    FusionpTraceParameterCheck(v6);
    *v15 = -2147024809;
    goto LABEL_15;
  }
  if ( !a2 )
  {
    v14 = 147;
    goto LABEL_5;
  }
  if ( (a3 & 1) != 0 )
  {
    SetLastError(0);
    if ( GetFileAttributesExW(*((LPCWSTR *)this + 8), GetFileExInfoStandard, FileInformation) )
    {
      *(_QWORD *)a2 = 0;
      *((_DWORD *)a2 + 2) = 2;
      if ( *((_QWORD *)this + 4) >= *((_QWORD *)this + 3) )
      {
        *((_DWORD *)a2 + 4) = *((_DWORD *)this + 8) - *((_DWORD *)this + 6);
        *((_QWORD *)a2 + 3) = *(_QWORD *)((char *)&FileInformation[1] + 4);
        *((_OWORD *)a2 + 2) = *(_OWORD *)((char *)FileInformation + 4);
        *((_DWORD *)a2 + 5) = 0;
        *((_QWORD *)a2 + 6) = 32;
        *((_QWORD *)a2 + 9) = 0;
        v9 = 0;
        *(GUID *)((char *)a2 + 56) = GUID_NULL;
      }
      else
      {
        *v15 = -2147023537;
      }
    }
    else
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v10);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180078388);
    }
  }
  else
  {
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: %s() does not handle STATFLAG_NONE; returning E_NOTIMPL.\n",
      "CResourceStream::Stat");
    v9 = -2147467263;
  }
LABEL_15:
  v7 = v9;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v10);
  return v7;
}

```

## disassembly

```asm
0x180064dd0  mov     [rsp-8+arg_10], rbx
0x180064dd5  push    rbp
0x180064dd6  push    rsi
0x180064dd7  push    rdi
0x180064dd8  lea     rbp, [rsp-47h]
0x180064ddd  sub     rsp, 90h
0x180064de4  mov     rax, cs:__security_cookie
0x180064deb  xor     rax, rsp
0x180064dee  mov     [rbp+57h+var_20], rax
0x180064df2  lea     rax, qword_1800783A8
0x180064df9  mov     [rbp+57h+var_80], 8000FFFFh
0x180064e00  mov     [rbp+57h+var_68], rax
0x180064e04  mov     rdi, rcx
0x180064e07  lea     rax, [rbp+57h+var_80]
0x180064e0b  mov     [rbp+57h+var_78], 1
0x180064e12  lea     rcx, [rbp+57h+var_78]; this
0x180064e16  mov     [rbp+57h+var_50], rax
0x180064e1a  mov     esi, r8d
0x180064e1d  mov     [rbp+57h+var_70], 0
0x180064e25  mov     rbx, rdx
0x180064e28  mov     [rbp+57h+var_60], 20737853h
0x180064e30  mov     [rbp+57h+var_58], 8Ch
0x180064e37  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180064e3c  xor     eax, eax
0x180064e3e  xorps   xmm0, xmm0
0x180064e41  mov     [rbp+57h+var_28], eax
0x180064e44  movups  [rbp+57h+FileInformation], xmm0
0x180064e48  movups  [rbp+57h+var_38], xmm0
0x180064e4c  test    rbx, rbx
0x180064e4f  jz      short loc_180064E5F
0x180064e51  xor     edx, edx; Val
0x180064e53  lea     r8d, [rax+50h]; Size
0x180064e57  mov     rcx, rbx; void *
0x180064e5a  call    memset_0
0x180064e5f  test    esi, 0FFFFFFFEh
0x180064e65  jz      short loc_180064E82
0x180064e67  mov     [rbp+57h+var_58], 92h
0x180064e6e  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180064e73  mov     rax, [rbp+57h+var_50]
0x180064e77  mov     dword ptr [rax], 80070057h
0x180064e7d  jmp     loc_180064F68
0x180064e82  test    rbx, rbx
0x180064e85  jnz     short loc_180064E90
0x180064e87  mov     [rbp+57h+var_58], 93h
0x180064e8e  jmp     short loc_180064E6E
0x180064e90  test    sil, 1
0x180064e94  jnz     short loc_180064EBA
0x180064e96  lea     r8, aCresourcestrea; "CResourceStream::Stat"
0x180064e9d  mov     ecx, 0C0000000h; unsigned int
0x180064ea2  lea     rdx, aSxsDllSDoesNot; "SXS.DLL: %s() does not handle STATFLAG_"...
0x180064ea9  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180064eae  mov     [rbp+57h+var_80], 80004001h
0x180064eb5  jmp     loc_180064F68
0x180064eba  xor     ecx, ecx; dwErrCode
0x180064ebc  call    cs:__imp_SetLastError
0x180064ec3  nop     dword ptr [rax+rax+00h]
0x180064ec8  mov     rcx, [rdi+40h]; lpFileName
0x180064ecc  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180064ed0  xor     edx, edx; fInfoLevelId
0x180064ed2  call    cs:__imp_GetFileAttributesExW
0x180064ed9  nop     dword ptr [rax+rax+00h]
0x180064ede  test    eax, eax
0x180064ee0  jnz     short loc_180064EF9
0x180064ee2  lea     rcx, [rbp+57h+var_78]; this
0x180064ee6  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064eeb  lea     rcx, off_180078388; struct _CALL_SITE_INFO *
0x180064ef2  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180064ef7  jmp     short loc_180064F68
0x180064ef9  mov     qword ptr [rbx], 0
0x180064f00  mov     dword ptr [rbx+8], 2
0x180064f07  mov     rax, [rdi+18h]
0x180064f0b  cmp     [rdi+20h], rax
0x180064f0f  jnb     short loc_180064F1D
0x180064f11  mov     rax, [rbp+57h+var_50]
0x180064f15  mov     dword ptr [rax], 8007054Fh
0x180064f1b  jmp     short loc_180064F68
0x180064f1d  mov     eax, [rdi+20h]
0x180064f20  sub     eax, [rdi+18h]
0x180064f23  mov     [rbx+10h], eax
0x180064f26  mov     rax, qword ptr [rbp+57h+var_38+4]
0x180064f2a  mov     [rbx+18h], rax
0x180064f2e  mov     rax, qword ptr [rbp+57h+FileInformation+4]
0x180064f32  mov     [rbx+20h], rax
0x180064f36  mov     rax, qword ptr [rbp+57h+FileInformation+0Ch]
0x180064f3a  mov     [rbx+28h], rax
0x180064f3e  mov     dword ptr [rbx+14h], 0
0x180064f45  mov     qword ptr [rbx+30h], 20h ; ' '
0x180064f4d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180064f54  mov     qword ptr [rbx+48h], 0
0x180064f5c  mov     [rbp+57h+var_80], 0
0x180064f63  movdqu  xmmword ptr [rbx+38h], xmm0
0x180064f68  mov     ebx, [rbp+57h+var_80]
0x180064f6b  lea     rcx, [rbp+57h+var_78]; this
0x180064f6f  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180064f74  mov     eax, ebx
0x180064f76  mov     rcx, [rbp+57h+var_20]
0x180064f7a  xor     rcx, rsp; StackCookie
0x180064f7d  call    __security_check_cookie
0x180064f82  mov     rbx, [rsp+0A0h+arg_10]
0x180064f8a  add     rsp, 90h
0x180064f91  pop     rdi
0x180064f92  pop     rsi
0x180064f93  pop     rbp
0x180064f94  retn
```
