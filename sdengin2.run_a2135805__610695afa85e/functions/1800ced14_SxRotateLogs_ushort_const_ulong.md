# SxRotateLogs(ushort const *,ulong)

- ea: `0x1800ced14`
- end: `0x1800cef9a`
- name: `?SxRotateLogs@@YAJPEBGK@Z`
- size: `646`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180091a44`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x18009e3c4`
- `0x18009e904`
- `0x18009f560`
- `0x1800ce328`
- `0x1800ce968`
- `0x1800ced14`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800cee6b`
- `KERNEL32!DeleteFileW` at `0x1800cee6b`
- `KERNEL32!MoveFileExW` at `0x1800ceed1`
- `KERNEL32!MoveFileExW` at `0x1800ceed1`
- `KERNEL32!GetLastError` at `0x1800cee06`
- `KERNEL32!GetLastError` at `0x1800ceee1`
- `KERNEL32!GetLastError` at `0x1800cee06`
- `KERNEL32!GetLastError` at `0x1800ceee1`
- `KERNEL32!GetFileAttributesW` at `0x1800cedf5`
- `KERNEL32!GetFileAttributesW` at `0x1800cedf5`

## pseudocode

```c
__int64 __fastcall SxRotateLogs(const unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edx
  signed int v6; // ebx
  __int16 v7; // ax
  int v8; // r14d
  const WCHAR *v9; // rsi
  DWORD LastError; // eax
  __int64 v11; // rcx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v15; // [rsp+50h] [rbp-19h] BYREF
  __int16 v16; // [rsp+54h] [rbp-15h]
  __int16 v17; // [rsp+56h] [rbp-13h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "SxRotateLogs", 0x1BAu, 1u);
  lpExistingFileName[1] = 0;
  lpExistingFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v7 = 450;
LABEL_24:
    v15 = v6;
    goto LABEL_25;
  }
  v15 = 0;
  v16 = 451;
  SxMergeExtraLogs(a1, v5);
  v6 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 0, L"etl");
  v15 = v6;
  v7 = 458;
  if ( v6 < 0 )
    goto LABEL_25;
  v16 = 458;
  if ( GetFileAttributesW(lpFileName[0]) == -1 && GetLastError() - 2 <= 1 )
  {
    v6 = 0;
    v15 = 0;
    v16 = 466;
    goto LABEL_26;
  }
  v8 = 4;
  v6 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 4, L"etl");
  v15 = v6;
  v7 = 471;
  if ( v6 < 0 )
  {
LABEL_25:
    v17 = v7;
    goto LABEL_26;
  }
  v9 = lpFileName[0];
  v16 = 471;
  DeleteFileW(lpFileName[0]);
  v6 = v15;
  while ( v8 )
  {
    v6 = CBsString::Format((CBsString *)lpExistingFileName, L"%s.%d.%s", a1, (unsigned int)--v8, L"etl");
    v15 = v6;
    v7 = 478;
    if ( v6 < 0 )
      goto LABEL_25;
    v16 = 478;
    if ( !MoveFileExW(lpExistingFileName[0], v9, 1u) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0x20 || (v11 = 0x100000024LL, !_bittest64(&v11, LastError)) )
      {
        if ( (int)LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v7 = 491;
        goto LABEL_24;
      }
      v15 = 0;
      v16 = 491;
    }
    SxCompressLogFile(v9);
    v15 = CBsString::Set((CBsString *)lpFileName, lpExistingFileName[0]);
    v6 = v15;
    if ( v15 < 0 )
    {
      v17 = 498;
      break;
    }
    v9 = lpFileName[0];
    v16 = 498;
  }
LABEL_26:
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ced14  push    rbp
0x1800ced16  push    rbx
0x1800ced17  push    rsi
0x1800ced18  push    rdi
0x1800ced19  push    r13
0x1800ced1b  push    r14
0x1800ced1d  lea     rbp, [rsp-2Fh]
0x1800ced22  sub     rsp, 98h
0x1800ced29  mov     rdi, rcx
0x1800ced2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ced33  lea     rax, WPP_GLOBAL_Control
0x1800ced3a  cmp     rcx, rax
0x1800ced3d  jz      short loc_1800CED5D
0x1800ced3f  test    dword ptr [rcx+1Ch], 20000000h
0x1800ced46  jz      short loc_1800CED5D
0x1800ced48  mov     rcx, [rcx+10h]
0x1800ced4c  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800ced53  mov     edx, 14h
0x1800ced58  call    WPP_SF_
0x1800ced5d  mov     r9d, 1; unsigned __int16
0x1800ced63  lea     rdx, aSxrotatelogs; "SxRotateLogs"
0x1800ced6a  mov     r8d, 1BAh; unsigned __int16
0x1800ced70  lea     rcx, [rbp+57h+var_70]; this
0x1800ced74  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800ced79  mov     [rbp+57h+var_78], 0
0x1800ced81  lea     rax, qword_1800EE510
0x1800ced88  mov     [rbp+57h+lpExistingFileName], rax
0x1800ced8c  mov     [rbp+57h+lpFileName], rax
0x1800ced90  mov     [rbp+57h+var_88], 0
0x1800ced98  test    rdi, rdi
0x1800ced9b  jz      loc_1800CEF5B
0x1800ceda1  mov     eax, 1C3h
0x1800ceda6  mov     [rbp+57h+var_70], 0
0x1800cedad  mov     rcx, rdi; unsigned __int16 *
0x1800cedb0  mov     [rbp+57h+var_6C], ax
0x1800cedb4  call    ?SxMergeExtraLogs@@YAJPEBGK@Z; SxMergeExtraLogs(ushort const *,ulong)
0x1800cedb9  lea     rsi, aEtl_0; "etl"
0x1800cedc0  xor     r9d, r9d
0x1800cedc3  mov     r8, rdi
0x1800cedc6  mov     [rsp+0C0h+var_A0], rsi
0x1800cedcb  lea     rdx, aSDS; "%s.%d.%s"
0x1800cedd2  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cedd6  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800ceddb  mov     ebx, eax
0x1800ceddd  mov     [rbp+57h+var_70], eax
0x1800cede0  test    eax, eax
0x1800cede2  mov     eax, 1CAh
0x1800cede7  js      loc_1800CEF68
0x1800ceded  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800cedf1  mov     [rbp+57h+var_6C], ax
0x1800cedf5  call    cs:__imp_GetFileAttributesW
0x1800cedfc  nop     dword ptr [rax+rax+00h]
0x1800cee01  cmp     eax, 0FFFFFFFFh
0x1800cee04  jnz     short loc_1800CEE2D
0x1800cee06  call    cs:__imp_GetLastError
0x1800cee0d  nop     dword ptr [rax+rax+00h]
0x1800cee12  add     eax, 0FFFFFFFEh
0x1800cee15  cmp     eax, 1
0x1800cee18  ja      short loc_1800CEE2D
0x1800cee1a  xor     ebx, ebx
0x1800cee1c  mov     eax, 1D2h
0x1800cee21  mov     [rbp+57h+var_70], ebx
0x1800cee24  mov     [rbp+57h+var_6C], ax
0x1800cee28  jmp     loc_1800CEF6C
0x1800cee2d  mov     r14d, 4
0x1800cee33  mov     [rsp+0C0h+var_A0], rsi
0x1800cee38  mov     r9d, r14d
0x1800cee3b  lea     rdx, aSDS; "%s.%d.%s"
0x1800cee42  mov     r8, rdi
0x1800cee45  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cee49  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800cee4e  mov     ebx, eax
0x1800cee50  mov     [rbp+57h+var_70], eax
0x1800cee53  test    eax, eax
0x1800cee55  mov     eax, 1D7h
0x1800cee5a  js      loc_1800CEF68
0x1800cee60  mov     rsi, [rbp+57h+lpFileName]
0x1800cee64  mov     rcx, rsi; lpFileName
0x1800cee67  mov     [rbp+57h+var_6C], ax
0x1800cee6b  call    cs:__imp_DeleteFileW
0x1800cee72  nop     dword ptr [rax+rax+00h]
0x1800cee77  mov     ebx, [rbp+57h+var_70]
0x1800cee7a  mov     r13d, 1F2h
0x1800cee80  test    r14d, r14d
0x1800cee83  jz      loc_1800CEF6C
0x1800cee89  lea     rax, aEtl_0; "etl"
0x1800cee90  dec     r14d
0x1800cee93  mov     r9d, r14d
0x1800cee96  mov     [rsp+0C0h+var_A0], rax
0x1800cee9b  mov     r8, rdi
0x1800cee9e  lea     rdx, aSDS; "%s.%d.%s"
0x1800ceea5  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800ceea9  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800ceeae  mov     ebx, eax
0x1800ceeb0  mov     [rbp+57h+var_70], eax
0x1800ceeb3  test    eax, eax
0x1800ceeb5  mov     eax, 1DEh
0x1800ceeba  js      loc_1800CEF68
0x1800ceec0  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800ceec4  mov     r8d, 1; dwFlags
0x1800ceeca  mov     rdx, rsi; lpNewFileName
0x1800ceecd  mov     [rbp+57h+var_6C], ax
0x1800ceed1  call    cs:__imp_MoveFileExW
0x1800ceed8  nop     dword ptr [rax+rax+00h]
0x1800ceedd  test    eax, eax
0x1800ceedf  jnz     short loc_1800CEF14
0x1800ceee1  call    cs:__imp_GetLastError
0x1800ceee8  nop     dword ptr [rax+rax+00h]
0x1800ceeed  mov     ebx, eax
0x1800ceeef  cmp     eax, 20h ; ' '
0x1800ceef2  ja      short loc_1800CEF40
0x1800ceef4  mov     rcx, 100000024h
0x1800ceefe  bt      rcx, rbx
0x1800cef02  jnb     short loc_1800CEF40
0x1800cef04  mov     eax, 1EBh
0x1800cef09  mov     [rbp+57h+var_70], 0
0x1800cef10  mov     [rbp+57h+var_6C], ax
0x1800cef14  mov     rcx, rsi; lpFileName
0x1800cef17  call    ?SxCompressLogFile@@YAJPEBG@Z; SxCompressLogFile(ushort const *)
0x1800cef1c  mov     rdx, [rbp+57h+lpExistingFileName]; unsigned __int16 *
0x1800cef20  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cef24  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800cef29  mov     [rbp+57h+var_70], eax
0x1800cef2c  mov     ebx, eax
0x1800cef2e  test    eax, eax
0x1800cef30  js      short loc_1800CEF54
0x1800cef32  mov     rsi, [rbp+57h+lpFileName]
0x1800cef36  mov     [rbp+57h+var_6C], r13w
0x1800cef3b  jmp     loc_1800CEE80
0x1800cef40  test    ebx, ebx
0x1800cef42  jle     short loc_1800CEF4D
0x1800cef44  movzx   ebx, bx
0x1800cef47  or      ebx, 80070000h
0x1800cef4d  mov     eax, 1EBh
0x1800cef52  jmp     short loc_1800CEF65
0x1800cef54  mov     [rbp+57h+var_6A], r13w
0x1800cef59  jmp     short loc_1800CEF6C
0x1800cef5b  mov     ebx, 80070057h
0x1800cef60  mov     eax, 1C2h
0x1800cef65  mov     [rbp+57h+var_70], ebx
0x1800cef68  mov     [rbp+57h+var_6A], ax
0x1800cef6c  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cef70  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800cef75  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800cef79  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800cef7e  lea     rcx, [rbp+57h+var_70]; this
0x1800cef82  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800cef87  mov     eax, ebx
0x1800cef89  add     rsp, 98h
0x1800cef90  pop     r14
0x1800cef92  pop     r13
0x1800cef94  pop     rdi
0x1800cef95  pop     rsi
0x1800cef96  pop     rbx
0x1800cef97  pop     rbp
0x1800cef98  retn
```
