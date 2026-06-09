# SxRotateLogs(ushort const *,ulong)

- ea: `0x180021068`
- end: `0x1800212de`
- name: `?SxRotateLogs@@YAJPEBGK@Z`
- size: `630`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001698c`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001f624`
- `0x18001f8ec`
- `0x180020488`
- `0x180020808`
- `0x180020ddc`
- `0x180021068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021215`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800211b7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800211b7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021149`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021149`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002120b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002120b`

## pseudocode

```c
__int64 __fastcall SxRotateLogs(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  int v3; // ebx
  __int16 v4; // ax
  int v5; // r14d
  const WCHAR *v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h]
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v13; // [rsp+50h] [rbp-19h] BYREF
  __int16 v14; // [rsp+54h] [rbp-15h]
  __int16 v15; // [rsp+56h] [rbp-13h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxRotateLogs", 442, 1);
  lpExistingFileName[1] = 0;
  lpExistingFileName[0] = (LPCWSTR)qword_180028260;
  lpFileName = (LPCWSTR)qword_180028260;
  v11 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 450;
LABEL_26:
    v13 = v3;
    goto LABEL_27;
  }
  v13 = 0;
  v14 = 451;
  SxMergeExtraLogs(a1, v2);
  v3 = CBsString::Format((CBsString *)&lpFileName, (wchar_t *)L"%s.%d.%s", a1, 0, L"etl");
  v13 = v3;
  v4 = 458;
  if ( v3 < 0 )
  {
LABEL_27:
    v15 = v4;
    goto LABEL_28;
  }
  v14 = 458;
  if ( GetFileAttributesW(lpFileName) != -1 || GetLastError() - 2 > 1 )
  {
    v5 = 4;
    v3 = CBsString::Format((CBsString *)&lpFileName, (wchar_t *)L"%s.%d.%s", a1, 4, L"etl");
    v13 = v3;
    v4 = 471;
    if ( v3 >= 0 )
    {
      v6 = lpFileName;
      v14 = 471;
      DeleteFileW(lpFileName);
      while ( 1 )
      {
        v3 = CBsString::Format((CBsString *)lpExistingFileName, (wchar_t *)L"%s.%d.%s", a1, (unsigned int)--v5, L"etl");
        v13 = v3;
        v4 = 478;
        if ( v3 < 0 )
          break;
        v14 = 478;
        if ( !MoveFileExW(lpExistingFileName[0], v6, 1u) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0x20 || (v8 = 0x100000024LL, !_bittest64(&v8, LastError)) )
          {
            if ( (int)LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
            v4 = 491;
            goto LABEL_26;
          }
          v13 = 0;
          v14 = 491;
        }
        SxCompressLogFile(v6);
        if ( (_DWORD)v11 )
        {
          LODWORD(v11) = 0;
          *v6 = 0;
        }
        v13 = CBsString::Append((CBsString *)&lpFileName, (unsigned __int16 *)lpExistingFileName[0]);
        v3 = v13;
        if ( v13 < 0 )
        {
          v15 = 498;
          goto LABEL_28;
        }
        v14 = 498;
        if ( !v5 )
          goto LABEL_28;
        v6 = lpFileName;
      }
    }
    goto LABEL_27;
  }
  v13 = 0;
  v14 = 466;
  v3 = 0;
LABEL_28:
  CBsString::_Release((LPVOID *)&lpFileName);
  CBsString::_Release((LPVOID *)lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021068  push    rbp
0x18002106a  push    rbx
0x18002106b  push    rsi
0x18002106c  push    rdi
0x18002106d  push    r13
0x18002106f  push    r14
0x180021071  lea     rbp, [rsp-2Fh]
0x180021076  sub     rsp, 98h
0x18002107d  mov     rsi, rcx
0x180021080  mov     rcx, cs:WPP_GLOBAL_Control
0x180021087  lea     rax, WPP_GLOBAL_Control
0x18002108e  cmp     rcx, rax
0x180021091  jz      short loc_1800210B1
0x180021093  test    dword ptr [rcx+1Ch], 20000000h
0x18002109a  jz      short loc_1800210B1
0x18002109c  mov     rcx, [rcx+10h]
0x1800210a0  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800210a7  mov     edx, 14h
0x1800210ac  call    WPP_SF_
0x1800210b1  mov     r9d, 1; unsigned __int16
0x1800210b7  lea     rdx, aSxrotatelogs; "SxRotateLogs"
0x1800210be  mov     r8d, 1BAh; unsigned __int16
0x1800210c4  lea     rcx, [rbp+57h+var_70]; this
0x1800210c8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800210cd  mov     [rbp+57h+var_78], 0
0x1800210d5  lea     rax, qword_180028260
0x1800210dc  mov     [rbp+57h+lpExistingFileName], rax
0x1800210e0  mov     [rbp+57h+lpFileName], rax
0x1800210e4  mov     [rbp+57h+var_88], 0
0x1800210ec  test    rsi, rsi
0x1800210ef  jz      loc_1800212A0
0x1800210f5  mov     eax, 1C3h
0x1800210fa  mov     [rbp+57h+var_70], 0
0x180021101  mov     rcx, rsi; unsigned __int16 *
0x180021104  mov     [rbp+57h+var_6C], ax
0x180021108  call    ?SxMergeExtraLogs@@YAJPEBGK@Z; SxMergeExtraLogs(ushort const *,ulong)
0x18002110d  lea     rdi, aEtl; "etl"
0x180021114  xor     r9d, r9d
0x180021117  mov     r8, rsi
0x18002111a  mov     [rsp+0C0h+var_A0], rdi
0x18002111f  lea     rdx, aSDS; "%s.%d.%s"
0x180021126  lea     rcx, [rbp+57h+lpFileName]; this
0x18002112a  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18002112f  mov     ebx, eax
0x180021131  mov     [rbp+57h+var_70], eax
0x180021134  test    eax, eax
0x180021136  mov     eax, 1CAh
0x18002113b  js      loc_1800212AD
0x180021141  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180021145  mov     [rbp+57h+var_6C], ax
0x180021149  call    cs:__imp_GetFileAttributesW
0x18002114f  cmp     eax, 0FFFFFFFFh
0x180021152  jnz     short loc_180021179
0x180021154  call    cs:__imp_GetLastError
0x18002115a  add     eax, 0FFFFFFFEh
0x18002115d  cmp     eax, 1
0x180021160  ja      short loc_180021179
0x180021162  mov     eax, 1D2h
0x180021167  mov     [rbp+57h+var_70], 0
0x18002116e  mov     [rbp+57h+var_6C], ax
0x180021172  xor     ebx, ebx
0x180021174  jmp     loc_1800212B1
0x180021179  mov     r14d, 4
0x18002117f  mov     [rsp+0C0h+var_A0], rdi
0x180021184  mov     r9d, r14d
0x180021187  lea     rdx, aSDS; "%s.%d.%s"
0x18002118e  mov     r8, rsi
0x180021191  lea     rcx, [rbp+57h+lpFileName]; this
0x180021195  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18002119a  mov     ebx, eax
0x18002119c  mov     [rbp+57h+var_70], eax
0x18002119f  test    eax, eax
0x1800211a1  mov     eax, 1D7h
0x1800211a6  js      loc_1800212AD
0x1800211ac  mov     rdi, [rbp+57h+lpFileName]
0x1800211b0  mov     rcx, rdi; lpFileName
0x1800211b3  mov     [rbp+57h+var_6C], ax
0x1800211b7  call    cs:__imp_DeleteFileW
0x1800211bd  mov     r13d, 1F2h
0x1800211c3  lea     rax, aEtl; "etl"
0x1800211ca  dec     r14d
0x1800211cd  mov     r9d, r14d
0x1800211d0  mov     [rsp+0C0h+var_A0], rax
0x1800211d5  mov     r8, rsi
0x1800211d8  lea     rdx, aSDS; "%s.%d.%s"
0x1800211df  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800211e3  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800211e8  mov     ebx, eax
0x1800211ea  mov     [rbp+57h+var_70], eax
0x1800211ed  test    eax, eax
0x1800211ef  mov     eax, 1DEh
0x1800211f4  js      loc_1800212AD
0x1800211fa  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x1800211fe  mov     r8d, 1; dwFlags
0x180021204  mov     rdx, rdi; lpNewFileName
0x180021207  mov     [rbp+57h+var_6C], ax
0x18002120b  call    cs:__imp_MoveFileExW
0x180021211  test    eax, eax
0x180021213  jnz     short loc_180021242
0x180021215  call    cs:__imp_GetLastError
0x18002121b  mov     ebx, eax
0x18002121d  cmp     eax, 20h ; ' '
0x180021220  ja      short loc_180021285
0x180021222  mov     rcx, 100000024h
0x18002122c  bt      rcx, rbx
0x180021230  jnb     short loc_180021285
0x180021232  mov     eax, 1EBh
0x180021237  mov     [rbp+57h+var_70], 0
0x18002123e  mov     [rbp+57h+var_6C], ax
0x180021242  mov     rcx, rdi; lpFileName
0x180021245  call    ?SxCompressLogFile@@YAJPEBG@Z; SxCompressLogFile(ushort const *)
0x18002124a  cmp     dword ptr [rbp+57h+var_88], 0
0x18002124e  jz      short loc_18002125C
0x180021250  xor     eax, eax
0x180021252  mov     dword ptr [rbp+57h+var_88], 0
0x180021259  mov     [rdi], ax
0x18002125c  mov     rdx, [rbp+57h+lpExistingFileName]; unsigned __int16 *
0x180021260  lea     rcx, [rbp+57h+lpFileName]; this
0x180021264  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180021269  mov     [rbp+57h+var_70], eax
0x18002126c  mov     ebx, eax
0x18002126e  test    eax, eax
0x180021270  js      short loc_180021299
0x180021272  mov     [rbp+57h+var_6C], r13w
0x180021277  test    r14d, r14d
0x18002127a  jz      short loc_1800212B1
0x18002127c  mov     rdi, [rbp+57h+lpFileName]
0x180021280  jmp     loc_1800211C3
0x180021285  test    ebx, ebx
0x180021287  jle     short loc_180021292
0x180021289  movzx   ebx, bx
0x18002128c  or      ebx, 80070000h
0x180021292  mov     eax, 1EBh
0x180021297  jmp     short loc_1800212AA
0x180021299  mov     [rbp+57h+var_6A], r13w
0x18002129e  jmp     short loc_1800212B1
0x1800212a0  mov     ebx, 80070057h
0x1800212a5  mov     eax, 1C2h
0x1800212aa  mov     [rbp+57h+var_70], ebx
0x1800212ad  mov     [rbp+57h+var_6A], ax
0x1800212b1  lea     rcx, [rbp+57h+lpFileName]; this
0x1800212b5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800212ba  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x1800212be  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800212c3  lea     rcx, [rbp+57h+var_70]; this
0x1800212c7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800212cc  mov     eax, ebx
0x1800212ce  add     rsp, 98h
0x1800212d5  pop     r14
0x1800212d7  pop     r13
0x1800212d9  pop     rdi
0x1800212da  pop     rsi
0x1800212db  pop     rbx
0x1800212dc  pop     rbp
0x1800212dd  retn
```
