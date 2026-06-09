# SxRotateLogs(ushort const *,ulong)

- ea: `0x1800c8ffc`
- end: `0x1800c9263`
- name: `?SxRotateLogs@@YAJPEBGK@Z`
- size: `615`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008db40`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180099d58`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800c8680`
- `0x1800c8c78`
- `0x1800c8ffc`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800c9147`
- `KERNEL32!DeleteFileW` at `0x1800c9147`
- `KERNEL32!MoveFileExW` at `0x1800c91a7`
- `KERNEL32!MoveFileExW` at `0x1800c91a7`
- `KERNEL32!GetLastError` at `0x1800c90e8`
- `KERNEL32!GetLastError` at `0x1800c91b1`
- `KERNEL32!GetLastError` at `0x1800c90e8`
- `KERNEL32!GetLastError` at `0x1800c91b1`
- `KERNEL32!GetFileAttributesW` at `0x1800c90dd`
- `KERNEL32!GetFileAttributesW` at `0x1800c90dd`

## pseudocode

```c
__int64 __fastcall SxRotateLogs(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  signed int v3; // ebx
  __int16 v4; // ax
  int v5; // r14d
  const WCHAR *v6; // rsi
  DWORD LastError; // eax
  __int64 v8; // rcx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-39h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v12; // [rsp+50h] [rbp-19h] BYREF
  __int16 v13; // [rsp+54h] [rbp-15h]
  __int16 v14; // [rsp+56h] [rbp-13h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxRotateLogs", 442, 1);
  lpExistingFileName[1] = 0;
  lpExistingFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 450;
LABEL_24:
    v12 = v3;
    goto LABEL_25;
  }
  v12 = 0;
  v13 = 451;
  SxMergeExtraLogs(a1, v2);
  v3 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 0, L"etl");
  v12 = v3;
  v4 = 458;
  if ( v3 < 0 )
    goto LABEL_25;
  v13 = 458;
  if ( GetFileAttributesW(lpFileName[0]) == -1 && GetLastError() - 2 <= 1 )
  {
    v3 = 0;
    v12 = 0;
    v13 = 466;
    goto LABEL_26;
  }
  v5 = 4;
  v3 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, 4, L"etl");
  v12 = v3;
  v4 = 471;
  if ( v3 < 0 )
  {
LABEL_25:
    v14 = v4;
    goto LABEL_26;
  }
  v6 = lpFileName[0];
  v13 = 471;
  DeleteFileW(lpFileName[0]);
  v3 = v12;
  while ( v5 )
  {
    v3 = CBsString::Format((CBsString *)lpExistingFileName, L"%s.%d.%s", a1, (unsigned int)--v5, L"etl");
    v12 = v3;
    v4 = 478;
    if ( v3 < 0 )
      goto LABEL_25;
    v13 = 478;
    if ( !MoveFileExW(lpExistingFileName[0], v6, 1u) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0x20 || (v8 = 0x100000024LL, !_bittest64(&v8, LastError)) )
      {
        if ( (int)LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        v4 = 491;
        goto LABEL_24;
      }
      v12 = 0;
      v13 = 491;
    }
    SxCompressLogFile(v6);
    v12 = CBsString::Set((CBsString *)lpFileName, lpExistingFileName[0]);
    v3 = v12;
    if ( v12 < 0 )
    {
      v14 = 498;
      break;
    }
    v6 = lpFileName[0];
    v13 = 498;
  }
LABEL_26:
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800c8ffc  push    rbp
0x1800c8ffe  push    rbx
0x1800c8fff  push    rsi
0x1800c9000  push    rdi
0x1800c9001  push    r13
0x1800c9003  push    r14
0x1800c9005  lea     rbp, [rsp-2Fh]
0x1800c900a  sub     rsp, 98h
0x1800c9011  mov     rdi, rcx
0x1800c9014  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c901b  lea     rax, WPP_GLOBAL_Control
0x1800c9022  cmp     rcx, rax
0x1800c9025  jz      short loc_1800C9045
0x1800c9027  test    dword ptr [rcx+1Ch], 20000000h
0x1800c902e  jz      short loc_1800C9045
0x1800c9030  mov     rcx, [rcx+10h]
0x1800c9034  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800c903b  mov     edx, 14h
0x1800c9040  call    WPP_SF_
0x1800c9045  mov     r9d, 1; unsigned __int16
0x1800c904b  lea     rdx, aSxrotatelogs; "SxRotateLogs"
0x1800c9052  mov     r8d, 1BAh; unsigned __int16
0x1800c9058  lea     rcx, [rbp+57h+var_70]; this
0x1800c905c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800c9061  mov     [rbp+57h+var_78], 0
0x1800c9069  lea     rax, qword_1800E8530
0x1800c9070  mov     [rbp+57h+lpExistingFileName], rax
0x1800c9074  mov     [rbp+57h+lpFileName], rax
0x1800c9078  mov     [rbp+57h+var_88], 0
0x1800c9080  test    rdi, rdi
0x1800c9083  jz      loc_1800C9225
0x1800c9089  mov     eax, 1C3h
0x1800c908e  mov     [rbp+57h+var_70], 0
0x1800c9095  mov     rcx, rdi; unsigned __int16 *
0x1800c9098  mov     [rbp+57h+var_6C], ax
0x1800c909c  call    ?SxMergeExtraLogs@@YAJPEBGK@Z; SxMergeExtraLogs(ushort const *,ulong)
0x1800c90a1  lea     rsi, aEtl_0; "etl"
0x1800c90a8  xor     r9d, r9d
0x1800c90ab  mov     r8, rdi
0x1800c90ae  mov     [rsp+0C0h+var_A0], rsi
0x1800c90b3  lea     rdx, aSDS; "%s.%d.%s"
0x1800c90ba  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c90be  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c90c3  mov     ebx, eax
0x1800c90c5  mov     [rbp+57h+var_70], eax
0x1800c90c8  test    eax, eax
0x1800c90ca  mov     eax, 1CAh
0x1800c90cf  js      loc_1800C9232
0x1800c90d5  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800c90d9  mov     [rbp+57h+var_6C], ax
0x1800c90dd  call    cs:__imp_GetFileAttributesW
0x1800c90e3  cmp     eax, 0FFFFFFFFh
0x1800c90e6  jnz     short loc_1800C9109
0x1800c90e8  call    cs:__imp_GetLastError
0x1800c90ee  add     eax, 0FFFFFFFEh
0x1800c90f1  cmp     eax, 1
0x1800c90f4  ja      short loc_1800C9109
0x1800c90f6  xor     ebx, ebx
0x1800c90f8  mov     eax, 1D2h
0x1800c90fd  mov     [rbp+57h+var_70], ebx
0x1800c9100  mov     [rbp+57h+var_6C], ax
0x1800c9104  jmp     loc_1800C9236
0x1800c9109  mov     r14d, 4
0x1800c910f  mov     [rsp+0C0h+var_A0], rsi
0x1800c9114  mov     r9d, r14d
0x1800c9117  lea     rdx, aSDS; "%s.%d.%s"
0x1800c911e  mov     r8, rdi
0x1800c9121  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c9125  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c912a  mov     ebx, eax
0x1800c912c  mov     [rbp+57h+var_70], eax
0x1800c912f  test    eax, eax
0x1800c9131  mov     eax, 1D7h
0x1800c9136  js      loc_1800C9232
0x1800c913c  mov     rsi, [rbp+57h+lpFileName]
0x1800c9140  mov     rcx, rsi; lpFileName
0x1800c9143  mov     [rbp+57h+var_6C], ax
0x1800c9147  call    cs:__imp_DeleteFileW
0x1800c914d  mov     ebx, [rbp+57h+var_70]
0x1800c9150  mov     r13d, 1F2h
0x1800c9156  test    r14d, r14d
0x1800c9159  jz      loc_1800C9236
0x1800c915f  lea     rax, aEtl_0; "etl"
0x1800c9166  dec     r14d
0x1800c9169  mov     r9d, r14d
0x1800c916c  mov     [rsp+0C0h+var_A0], rax
0x1800c9171  mov     r8, rdi
0x1800c9174  lea     rdx, aSDS; "%s.%d.%s"
0x1800c917b  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800c917f  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c9184  mov     ebx, eax
0x1800c9186  mov     [rbp+57h+var_70], eax
0x1800c9189  test    eax, eax
0x1800c918b  mov     eax, 1DEh
0x1800c9190  js      loc_1800C9232
0x1800c9196  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800c919a  mov     r8d, 1; dwFlags
0x1800c91a0  mov     rdx, rsi; lpNewFileName
0x1800c91a3  mov     [rbp+57h+var_6C], ax
0x1800c91a7  call    cs:__imp_MoveFileExW
0x1800c91ad  test    eax, eax
0x1800c91af  jnz     short loc_1800C91DE
0x1800c91b1  call    cs:__imp_GetLastError
0x1800c91b7  mov     ebx, eax
0x1800c91b9  cmp     eax, 20h ; ' '
0x1800c91bc  ja      short loc_1800C920A
0x1800c91be  mov     rcx, 100000024h
0x1800c91c8  bt      rcx, rbx
0x1800c91cc  jnb     short loc_1800C920A
0x1800c91ce  mov     eax, 1EBh
0x1800c91d3  mov     [rbp+57h+var_70], 0
0x1800c91da  mov     [rbp+57h+var_6C], ax
0x1800c91de  mov     rcx, rsi; lpFileName
0x1800c91e1  call    ?SxCompressLogFile@@YAJPEBG@Z; SxCompressLogFile(ushort const *)
0x1800c91e6  mov     rdx, [rbp+57h+lpExistingFileName]; unsigned __int16 *
0x1800c91ea  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c91ee  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800c91f3  mov     [rbp+57h+var_70], eax
0x1800c91f6  mov     ebx, eax
0x1800c91f8  test    eax, eax
0x1800c91fa  js      short loc_1800C921E
0x1800c91fc  mov     rsi, [rbp+57h+lpFileName]
0x1800c9200  mov     [rbp+57h+var_6C], r13w
0x1800c9205  jmp     loc_1800C9156
0x1800c920a  test    ebx, ebx
0x1800c920c  jle     short loc_1800C9217
0x1800c920e  movzx   ebx, bx
0x1800c9211  or      ebx, 80070000h
0x1800c9217  mov     eax, 1EBh
0x1800c921c  jmp     short loc_1800C922F
0x1800c921e  mov     [rbp+57h+var_6A], r13w
0x1800c9223  jmp     short loc_1800C9236
0x1800c9225  mov     ebx, 80070057h
0x1800c922a  mov     eax, 1C2h
0x1800c922f  mov     [rbp+57h+var_70], ebx
0x1800c9232  mov     [rbp+57h+var_6A], ax
0x1800c9236  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c923a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800c923f  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800c9243  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800c9248  lea     rcx, [rbp+57h+var_70]; this
0x1800c924c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800c9251  mov     eax, ebx
0x1800c9253  add     rsp, 98h
0x1800c925a  pop     r14
0x1800c925c  pop     r13
0x1800c925e  pop     rdi
0x1800c925f  pop     rsi
0x1800c9260  pop     rbx
0x1800c9261  pop     rbp
0x1800c9262  retn
```
