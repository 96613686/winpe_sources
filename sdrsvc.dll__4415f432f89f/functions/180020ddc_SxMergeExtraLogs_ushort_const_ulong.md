# SxMergeExtraLogs(ushort const *,ulong)

- ea: `0x180020ddc`
- end: `0x180021061`
- name: `?SxMergeExtraLogs@@YAJPEBGK@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180021068`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001f8ec`
- `0x180020488`
- `0x180020b18`
- `0x180020ddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020f2c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020f2c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180020fcb`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180020fcb`

## pseudocode

```c
__int64 __fastcall SxMergeExtraLogs(const unsigned __int16 *a1, unsigned int a2)
{
  __int16 v3; // ax
  unsigned int v4; // edi
  signed int v5; // esi
  int v6; // ebx
  wchar_t *v7; // rdx
  signed int LastError; // eax
  __int16 v9; // ax
  __int64 v10; // r9
  signed int v11; // eax
  unsigned int v12; // ebx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-29h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-9h] BYREF
  __int16 v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+56h] [rbp-3h]
  unsigned int v19; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v20; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v21; // [rsp+D0h] [rbp+77h] BYREF

  v20 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxMergeExtraLogs", 345, 1);
  v21 = 0;
  lpFileName[0] = (LPCWSTR)qword_180028260;
  lpNewFileName[0] = (LPCWSTR)qword_180028260;
  v20 = 0;
  v19 = 0;
  lpFileName[1] = 0;
  lpNewFileName[1] = 0;
  if ( !a1 )
  {
    v16 = -2147024809;
    v3 = 356;
    goto LABEL_34;
  }
  v16 = 0;
  v17 = 357;
  v16 = SxGet0XLogFileCount(a1, &v21, &v20, &v19);
  v3 = 364;
  if ( v16 < 0 )
    goto LABEL_34;
  v17 = 364;
  if ( !v20 )
  {
    v16 = 0;
    v17 = 369;
    goto LABEL_35;
  }
  v4 = 4;
  v5 = -v19;
  v6 = 4;
  if ( (signed int)-v19 > 4 )
    goto LABEL_35;
  while ( 1 )
  {
    v7 = (wchar_t *)L"%s.%d.%s";
    if ( v6 >= (int)(5 - v20) )
    {
      v16 = CBsString::Format((CBsString *)lpFileName, (wchar_t *)L"%s.%d.%s", a1, (unsigned int)v6, L"etl");
      v3 = 384;
      if ( v16 < 0 )
        goto LABEL_34;
      v17 = 384;
      if ( DeleteFileW(lpFileName[0]) )
        goto LABEL_25;
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError;
        v3 = 388;
        goto LABEL_34;
      }
      v9 = 388;
      goto LABEL_14;
    }
    v10 = (unsigned int)-v6;
    if ( v6 > 0 )
      v10 = (unsigned int)v6;
    if ( v6 < 0 )
      v7 = (wchar_t *)L"%s.0.%d.%s";
    v16 = CBsString::Format((CBsString *)lpFileName, v7, a1, v10, L"etl");
    v3 = 400;
    if ( v16 < 0 )
      goto LABEL_34;
    v17 = 400;
    v16 = CBsString::Format((CBsString *)lpNewFileName, (wchar_t *)L"%s.%d.%s", a1, v4, L"etl");
    v3 = 405;
    if ( v16 < 0 )
      goto LABEL_34;
    v17 = 405;
    if ( MoveFileExW(lpFileName[0], lpNewFileName[0], 1u) )
    {
      --v4;
      goto LABEL_25;
    }
    v11 = GetLastError();
    if ( v11 != 2 )
      break;
    v9 = 410;
LABEL_14:
    v16 = 0;
    v17 = v9;
LABEL_25:
    if ( --v6 < v5 )
      goto LABEL_35;
  }
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  v16 = v11;
  v3 = 410;
LABEL_34:
  v18 = v3;
LABEL_35:
  v12 = v16;
  CBsString::_Release((LPVOID *)lpNewFileName);
  CBsString::_Release((LPVOID *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v12;
}

```

## disassembly

```asm
0x180020ddc  mov     [rsp-8+arg_8], edx
0x180020de0  push    rbp
0x180020de1  push    rbx
0x180020de2  push    rsi
0x180020de3  push    rdi
0x180020de4  push    r14
0x180020de6  lea     rbp, [rsp-37h]
0x180020deb  sub     rsp, 90h
0x180020df2  mov     r14, rcx
0x180020df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dfc  lea     rax, WPP_GLOBAL_Control
0x180020e03  cmp     rcx, rax
0x180020e06  jz      short loc_180020E26
0x180020e08  test    dword ptr [rcx+1Ch], 20000000h
0x180020e0f  jz      short loc_180020E26
0x180020e11  mov     rcx, [rcx+10h]
0x180020e15  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x180020e1c  mov     edx, 13h
0x180020e21  call    WPP_SF_
0x180020e26  mov     r9d, 1; unsigned __int16
0x180020e2c  lea     rdx, aSxmergeextralo; "SxMergeExtraLogs"
0x180020e33  mov     r8d, 159h; unsigned __int16
0x180020e39  lea     rcx, [rbp+57h+var_60]; this
0x180020e3d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180020e42  mov     [rbp+57h+arg_10], 0
0x180020e49  lea     rax, qword_180028260
0x180020e50  mov     [rbp+57h+lpFileName], rax
0x180020e54  mov     [rbp+57h+lpNewFileName], rax
0x180020e58  mov     [rbp+57h+arg_8], 0
0x180020e5f  mov     [rbp+57h+arg_0], 0
0x180020e66  mov     [rbp+57h+var_78], 0
0x180020e6e  mov     [rbp+57h+var_68], 0
0x180020e76  test    r14, r14
0x180020e79  jz      loc_180021023
0x180020e7f  mov     eax, 165h
0x180020e84  mov     [rbp+57h+var_60], 0
0x180020e8b  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x180020e8f  mov     [rbp+57h+var_5C], ax
0x180020e93  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x180020e97  mov     rcx, r14; unsigned __int16 *
0x180020e9a  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x180020e9e  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x180020ea3  mov     [rbp+57h+var_60], eax
0x180020ea6  test    eax, eax
0x180020ea8  mov     eax, 16Ch
0x180020ead  js      loc_18002102F
0x180020eb3  cmp     [rbp+57h+arg_8], 0
0x180020eb7  mov     [rbp+57h+var_5C], ax
0x180020ebb  jnz     short loc_180020ED2
0x180020ebd  mov     eax, 171h
0x180020ec2  mov     [rbp+57h+var_60], 0
0x180020ec9  mov     [rbp+57h+var_5C], ax
0x180020ecd  jmp     loc_180021033
0x180020ed2  mov     esi, [rbp+57h+arg_0]
0x180020ed5  mov     edi, 4
0x180020eda  neg     esi
0x180020edc  mov     ebx, edi
0x180020ede  cmp     esi, edi
0x180020ee0  jg      loc_180021033
0x180020ee6  lea     rcx, aEtl; "etl"
0x180020eed  mov     eax, 5
0x180020ef2  sub     eax, [rbp+57h+arg_8]
0x180020ef5  lea     rdx, aSDS; "%s.%d.%s"
0x180020efc  mov     [rsp+0B0h+var_90], rcx
0x180020f01  mov     r9d, ebx
0x180020f04  lea     rcx, [rbp+57h+lpFileName]; this
0x180020f08  mov     r8, r14
0x180020f0b  cmp     ebx, eax
0x180020f0d  jl      short loc_180020F5E
0x180020f0f  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180020f14  mov     [rbp+57h+var_60], eax
0x180020f17  test    eax, eax
0x180020f19  mov     eax, 180h
0x180020f1e  js      loc_18002102F
0x180020f24  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180020f28  mov     [rbp+57h+var_5C], ax
0x180020f2c  call    cs:__imp_DeleteFileW
0x180020f32  test    eax, eax
0x180020f34  jnz     loc_180020FEC
0x180020f3a  call    cs:__imp_GetLastError
0x180020f40  cmp     eax, 2
0x180020f43  jnz     loc_180020FF7
0x180020f49  mov     eax, 184h
0x180020f4e  mov     [rbp+57h+var_60], 0
0x180020f55  mov     [rbp+57h+var_5C], ax
0x180020f59  jmp     loc_180020FEC
0x180020f5e  neg     r9d
0x180020f61  lea     rax, aS0DS; "%s.0.%d.%s"
0x180020f68  cmovs   r9d, ebx
0x180020f6c  test    ebx, ebx
0x180020f6e  cmovs   rdx, rax; unsigned __int16 *
0x180020f72  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180020f77  mov     [rbp+57h+var_60], eax
0x180020f7a  test    eax, eax
0x180020f7c  mov     eax, 190h
0x180020f81  js      loc_18002102F
0x180020f87  mov     [rbp+57h+var_5C], ax
0x180020f8b  lea     rdx, aSDS; "%s.%d.%s"
0x180020f92  lea     rax, aEtl; "etl"
0x180020f99  mov     r9d, edi
0x180020f9c  mov     r8, r14
0x180020f9f  mov     [rsp+0B0h+var_90], rax
0x180020fa4  lea     rcx, [rbp+57h+lpNewFileName]; this
0x180020fa8  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180020fad  mov     [rbp+57h+var_60], eax
0x180020fb0  test    eax, eax
0x180020fb2  mov     eax, 195h
0x180020fb7  js      short loc_18002102F
0x180020fb9  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180020fbd  mov     r8d, 1; dwFlags
0x180020fc3  mov     rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x180020fc7  mov     [rbp+57h+var_5C], ax
0x180020fcb  call    cs:__imp_MoveFileExW
0x180020fd1  test    eax, eax
0x180020fd3  jnz     short loc_180020FEA
0x180020fd5  call    cs:__imp_GetLastError
0x180020fdb  cmp     eax, 2
0x180020fde  jnz     short loc_18002100D
0x180020fe0  mov     eax, 19Ah
0x180020fe5  jmp     loc_180020F4E
0x180020fea  dec     edi
0x180020fec  dec     ebx
0x180020fee  cmp     ebx, esi
0x180020ff0  jl      short loc_180021033
0x180020ff2  jmp     loc_180020EE6
0x180020ff7  test    eax, eax
0x180020ff9  jle     short loc_180021003
0x180020ffb  movzx   eax, ax
0x180020ffe  or      eax, 80070000h
0x180021003  mov     [rbp+57h+var_60], eax
0x180021006  mov     eax, 184h
0x18002100b  jmp     short loc_18002102F
0x18002100d  test    eax, eax
0x18002100f  jle     short loc_180021019
0x180021011  movzx   eax, ax
0x180021014  or      eax, 80070000h
0x180021019  mov     [rbp+57h+var_60], eax
0x18002101c  mov     eax, 19Ah
0x180021021  jmp     short loc_18002102F
0x180021023  mov     [rbp+57h+var_60], 80070057h
0x18002102a  mov     eax, 164h
0x18002102f  mov     [rbp+57h+var_5A], ax
0x180021033  mov     ebx, [rbp+57h+var_60]
0x180021036  lea     rcx, [rbp+57h+lpNewFileName]; this
0x18002103a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002103f  lea     rcx, [rbp+57h+lpFileName]; this
0x180021043  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180021048  lea     rcx, [rbp+57h+var_60]; this
0x18002104c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180021051  mov     eax, ebx
0x180021053  add     rsp, 90h
0x18002105a  pop     r14
0x18002105c  pop     rdi
0x18002105d  pop     rsi
0x18002105e  pop     rbx
0x18002105f  pop     rbp
0x180021060  retn
```
