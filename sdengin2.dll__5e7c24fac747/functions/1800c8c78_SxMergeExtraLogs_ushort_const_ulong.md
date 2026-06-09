# SxMergeExtraLogs(ushort const *,ulong)

- ea: `0x1800c8c78`
- end: `0x1800c8f03`
- name: `?SxMergeExtraLogs@@YAJPEBGK@Z`
- size: `651`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800c8ffc`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180099d58`
- `0x18009ae34`
- `0x1800c8990`
- `0x1800c8c78`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800c8dce`
- `KERNEL32!DeleteFileW` at `0x1800c8dce`
- `KERNEL32!MoveFileExW` at `0x1800c8e69`
- `KERNEL32!MoveFileExW` at `0x1800c8e69`
- `KERNEL32!GetLastError` at `0x1800c8ddc`
- `KERNEL32!GetLastError` at `0x1800c8e73`
- `KERNEL32!GetLastError` at `0x1800c8ddc`
- `KERNEL32!GetLastError` at `0x1800c8e73`

## pseudocode

```c
__int64 __fastcall SxMergeExtraLogs(const unsigned __int16 *a1, unsigned int a2)
{
  __int16 v3; // ax
  unsigned int v4; // esi
  int i; // ebx
  const unsigned __int16 *v6; // rdx
  signed int v7; // eax
  __int64 v8; // r9
  signed int LastError; // eax
  unsigned int v10; // ebx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-29h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v14; // [rsp+50h] [rbp-9h] BYREF
  __int16 v15; // [rsp+54h] [rbp-5h]
  __int16 v16; // [rsp+56h] [rbp-3h]
  unsigned int v17; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v18; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+D0h] [rbp+77h] BYREF

  v18 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxMergeExtraLogs", 345, 1);
  v19 = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpNewFileName[0] = (LPCWSTR)qword_1800E8530;
  v18 = 0;
  v17 = 0;
  lpFileName[1] = 0;
  lpNewFileName[1] = 0;
  if ( !a1 )
  {
    v14 = -2147024809;
    v3 = 356;
    goto LABEL_33;
  }
  v14 = 0;
  v15 = 357;
  v14 = SxGet0XLogFileCount(a1, &v19, &v18, &v17);
  v3 = 364;
  if ( v14 < 0 )
  {
LABEL_33:
    v16 = v3;
    goto LABEL_34;
  }
  v15 = 364;
  if ( v18 )
  {
    v4 = 4;
    for ( i = 4; i >= (signed int)-v17; --i )
    {
      v6 = L"%s.%d.%s";
      if ( i < (int)(5 - v18) )
      {
        v8 = (unsigned int)-i;
        if ( i > 0 )
          v8 = (unsigned int)i;
        if ( i < 0 )
          v6 = L"%s.0.%d.%s";
        v14 = CBsString::Format((CBsString *)lpFileName, v6, a1, v8, L"etl");
        v3 = 400;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 400;
        v14 = CBsString::Format((CBsString *)lpNewFileName, L"%s.%d.%s", a1, v4, L"etl");
        v3 = 405;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 405;
        if ( MoveFileExW(lpFileName[0], lpNewFileName[0], 1u) )
        {
          --v4;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError != 2 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v14 = LastError;
            v3 = 410;
            goto LABEL_33;
          }
          v14 = 0;
          v15 = 410;
        }
      }
      else
      {
        v14 = CBsString::Format((CBsString *)lpFileName, L"%s.%d.%s", a1, (unsigned int)i, L"etl");
        v3 = 384;
        if ( v14 < 0 )
          goto LABEL_33;
        v15 = 384;
        if ( !DeleteFileW(lpFileName[0]) )
        {
          v7 = GetLastError();
          if ( v7 != 2 )
          {
            if ( v7 > 0 )
              v7 = (unsigned __int16)v7 | 0x80070000;
            v14 = v7;
            v16 = 388;
            break;
          }
          v14 = 0;
          v15 = 388;
        }
      }
    }
  }
  else
  {
    v14 = 0;
    v15 = 369;
  }
LABEL_34:
  v10 = v14;
  CBsString::_Release((CBsString *)lpNewFileName);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v10;
}

```

## disassembly

```asm
0x1800c8c78  mov     [rsp-8+arg_8], edx
0x1800c8c7c  push    rbp
0x1800c8c7d  push    rbx
0x1800c8c7e  push    rsi
0x1800c8c7f  push    rdi
0x1800c8c80  push    r13
0x1800c8c82  lea     rbp, [rsp-37h]
0x1800c8c87  sub     rsp, 90h
0x1800c8c8e  mov     rdi, rcx
0x1800c8c91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8c98  lea     rax, WPP_GLOBAL_Control
0x1800c8c9f  cmp     rcx, rax
0x1800c8ca2  jz      short loc_1800C8CC2
0x1800c8ca4  test    dword ptr [rcx+1Ch], 20000000h
0x1800c8cab  jz      short loc_1800C8CC2
0x1800c8cad  mov     rcx, [rcx+10h]
0x1800c8cb1  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800c8cb8  mov     edx, 13h
0x1800c8cbd  call    WPP_SF_
0x1800c8cc2  mov     r9d, 1; unsigned __int16
0x1800c8cc8  lea     rdx, aSxmergeextralo; "SxMergeExtraLogs"
0x1800c8ccf  mov     r8d, 159h; unsigned __int16
0x1800c8cd5  lea     rcx, [rbp+57h+var_60]; this
0x1800c8cd9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800c8cde  mov     [rbp+57h+arg_10], 0
0x1800c8ce5  lea     rax, qword_1800E8530
0x1800c8cec  mov     [rbp+57h+lpFileName], rax
0x1800c8cf0  mov     [rbp+57h+lpNewFileName], rax
0x1800c8cf4  mov     [rbp+57h+arg_8], 0
0x1800c8cfb  mov     [rbp+57h+arg_0], 0
0x1800c8d02  mov     [rbp+57h+var_78], 0
0x1800c8d0a  mov     [rbp+57h+var_68], 0
0x1800c8d12  test    rdi, rdi
0x1800c8d15  jz      loc_1800C8EC5
0x1800c8d1b  mov     eax, 165h
0x1800c8d20  mov     [rbp+57h+var_60], 0
0x1800c8d27  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800c8d2b  mov     [rbp+57h+var_5C], ax
0x1800c8d2f  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x1800c8d33  mov     rcx, rdi; unsigned __int16 *
0x1800c8d36  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x1800c8d3a  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x1800c8d3f  mov     [rbp+57h+var_60], eax
0x1800c8d42  test    eax, eax
0x1800c8d44  mov     eax, 16Ch
0x1800c8d49  js      loc_1800C8ED1
0x1800c8d4f  cmp     [rbp+57h+arg_8], 0
0x1800c8d53  mov     [rbp+57h+var_5C], ax
0x1800c8d57  jnz     short loc_1800C8D6E
0x1800c8d59  mov     eax, 171h
0x1800c8d5e  mov     [rbp+57h+var_60], 0
0x1800c8d65  mov     [rbp+57h+var_5C], ax
0x1800c8d69  jmp     loc_1800C8ED5
0x1800c8d6e  mov     esi, 4
0x1800c8d73  mov     r13d, 184h
0x1800c8d79  mov     ebx, esi
0x1800c8d7b  mov     eax, [rbp+57h+arg_0]
0x1800c8d7e  lea     rcx, aEtl_0; "etl"
0x1800c8d85  neg     eax
0x1800c8d87  cmp     ebx, eax
0x1800c8d89  jl      loc_1800C8ED5
0x1800c8d8f  mov     eax, 5
0x1800c8d94  mov     [rsp+0B0h+var_90], rcx
0x1800c8d99  sub     eax, [rbp+57h+arg_8]
0x1800c8d9c  lea     rdx, aSDS; "%s.%d.%s"
0x1800c8da3  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c8da7  mov     r9d, ebx
0x1800c8daa  mov     r8, rdi
0x1800c8dad  cmp     ebx, eax
0x1800c8daf  jl      short loc_1800C8DFC
0x1800c8db1  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c8db6  mov     [rbp+57h+var_60], eax
0x1800c8db9  test    eax, eax
0x1800c8dbb  mov     eax, 180h
0x1800c8dc0  js      loc_1800C8ED1
0x1800c8dc6  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800c8dca  mov     [rbp+57h+var_5C], ax
0x1800c8dce  call    cs:__imp_DeleteFileW
0x1800c8dd4  test    eax, eax
0x1800c8dd6  jnz     loc_1800C8E92
0x1800c8ddc  call    cs:__imp_GetLastError
0x1800c8de2  cmp     eax, 2
0x1800c8de5  jnz     loc_1800C8E99
0x1800c8deb  mov     [rbp+57h+var_60], 0
0x1800c8df2  mov     [rbp+57h+var_5C], r13w
0x1800c8df7  jmp     loc_1800C8E92
0x1800c8dfc  neg     r9d
0x1800c8dff  lea     rax, aS0DS; "%s.0.%d.%s"
0x1800c8e06  cmovs   r9d, ebx
0x1800c8e0a  test    ebx, ebx
0x1800c8e0c  cmovs   rdx, rax; unsigned __int16 *
0x1800c8e10  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c8e15  mov     [rbp+57h+var_60], eax
0x1800c8e18  test    eax, eax
0x1800c8e1a  mov     eax, 190h
0x1800c8e1f  js      loc_1800C8ED1
0x1800c8e25  mov     [rbp+57h+var_5C], ax
0x1800c8e29  lea     rdx, aSDS; "%s.%d.%s"
0x1800c8e30  lea     rax, aEtl_0; "etl"
0x1800c8e37  mov     r9d, esi
0x1800c8e3a  mov     r8, rdi
0x1800c8e3d  mov     [rsp+0B0h+var_90], rax
0x1800c8e42  lea     rcx, [rbp+57h+lpNewFileName]; this
0x1800c8e46  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800c8e4b  mov     [rbp+57h+var_60], eax
0x1800c8e4e  test    eax, eax
0x1800c8e50  mov     eax, 195h
0x1800c8e55  js      short loc_1800C8ED1
0x1800c8e57  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x1800c8e5b  mov     r8d, 1; dwFlags
0x1800c8e61  mov     rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x1800c8e65  mov     [rbp+57h+var_5C], ax
0x1800c8e69  call    cs:__imp_MoveFileExW
0x1800c8e6f  test    eax, eax
0x1800c8e71  jnz     short loc_1800C8E90
0x1800c8e73  call    cs:__imp_GetLastError
0x1800c8e79  cmp     eax, 2
0x1800c8e7c  jnz     short loc_1800C8EAF
0x1800c8e7e  mov     eax, 19Ah
0x1800c8e83  mov     [rbp+57h+var_60], 0
0x1800c8e8a  mov     [rbp+57h+var_5C], ax
0x1800c8e8e  jmp     short loc_1800C8E92
0x1800c8e90  dec     esi
0x1800c8e92  dec     ebx
0x1800c8e94  jmp     loc_1800C8D7B
0x1800c8e99  test    eax, eax
0x1800c8e9b  jle     short loc_1800C8EA5
0x1800c8e9d  movzx   eax, ax
0x1800c8ea0  or      eax, 80070000h
0x1800c8ea5  mov     [rbp+57h+var_60], eax
0x1800c8ea8  mov     [rbp+57h+var_5A], r13w
0x1800c8ead  jmp     short loc_1800C8ED5
0x1800c8eaf  test    eax, eax
0x1800c8eb1  jle     short loc_1800C8EBB
0x1800c8eb3  movzx   eax, ax
0x1800c8eb6  or      eax, 80070000h
0x1800c8ebb  mov     [rbp+57h+var_60], eax
0x1800c8ebe  mov     eax, 19Ah
0x1800c8ec3  jmp     short loc_1800C8ED1
0x1800c8ec5  mov     [rbp+57h+var_60], 80070057h
0x1800c8ecc  mov     eax, 164h
0x1800c8ed1  mov     [rbp+57h+var_5A], ax
0x1800c8ed5  mov     ebx, [rbp+57h+var_60]
0x1800c8ed8  lea     rcx, [rbp+57h+lpNewFileName]; this
0x1800c8edc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800c8ee1  lea     rcx, [rbp+57h+lpFileName]; this
0x1800c8ee5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800c8eea  lea     rcx, [rbp+57h+var_60]; this
0x1800c8eee  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800c8ef3  mov     eax, ebx
0x1800c8ef5  add     rsp, 90h
0x1800c8efc  pop     r13
0x1800c8efe  pop     rdi
0x1800c8eff  pop     rsi
0x1800c8f00  pop     rbx
0x1800c8f01  pop     rbp
0x1800c8f02  retn
```
