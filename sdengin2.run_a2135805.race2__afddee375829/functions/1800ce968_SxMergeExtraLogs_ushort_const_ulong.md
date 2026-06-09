# SxMergeExtraLogs(ushort const *,ulong)

- ea: `0x1800ce968`
- end: `0x1800cec10`
- name: `?SxMergeExtraLogs@@YAJPEBGK@Z`
- size: `680`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800ced14`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x18009e3c4`
- `0x18009f560`
- `0x1800ce658`
- `0x1800ce968`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1800ceabe`
- `KERNEL32!DeleteFileW` at `0x1800ceabe`
- `KERNEL32!MoveFileExW` at `0x1800ceb69`
- `KERNEL32!MoveFileExW` at `0x1800ceb69`
- `KERNEL32!GetLastError` at `0x1800cead2`
- `KERNEL32!GetLastError` at `0x1800ceb79`
- `KERNEL32!GetLastError` at `0x1800cead2`
- `KERNEL32!GetLastError` at `0x1800ceb79`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxMergeExtraLogs", 0x159u, 1u);
  v19 = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpNewFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x1800ce968  mov     [rsp-8+arg_8], edx
0x1800ce96c  push    rbp
0x1800ce96d  push    rbx
0x1800ce96e  push    rsi
0x1800ce96f  push    rdi
0x1800ce970  push    r13
0x1800ce972  lea     rbp, [rsp-37h]
0x1800ce977  sub     rsp, 90h
0x1800ce97e  mov     rdi, rcx
0x1800ce981  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce988  lea     rax, WPP_GLOBAL_Control
0x1800ce98f  cmp     rcx, rax
0x1800ce992  jz      short loc_1800CE9B2
0x1800ce994  test    dword ptr [rcx+1Ch], 20000000h
0x1800ce99b  jz      short loc_1800CE9B2
0x1800ce99d  mov     rcx, [rcx+10h]
0x1800ce9a1  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800ce9a8  mov     edx, 13h
0x1800ce9ad  call    WPP_SF_
0x1800ce9b2  mov     r9d, 1; unsigned __int16
0x1800ce9b8  lea     rdx, aSxmergeextralo; "SxMergeExtraLogs"
0x1800ce9bf  mov     r8d, 159h; unsigned __int16
0x1800ce9c5  lea     rcx, [rbp+57h+var_60]; this
0x1800ce9c9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800ce9ce  mov     [rbp+57h+arg_10], 0
0x1800ce9d5  lea     rax, qword_1800EE510
0x1800ce9dc  mov     [rbp+57h+lpFileName], rax
0x1800ce9e0  mov     [rbp+57h+lpNewFileName], rax
0x1800ce9e4  mov     [rbp+57h+arg_8], 0
0x1800ce9eb  mov     [rbp+57h+arg_0], 0
0x1800ce9f2  mov     [rbp+57h+var_78], 0
0x1800ce9fa  mov     [rbp+57h+var_68], 0
0x1800cea02  test    rdi, rdi
0x1800cea05  jz      loc_1800CEBD1
0x1800cea0b  mov     eax, 165h
0x1800cea10  mov     [rbp+57h+var_60], 0
0x1800cea17  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x1800cea1b  mov     [rbp+57h+var_5C], ax
0x1800cea1f  lea     r8, [rbp+57h+arg_8]; unsigned int *
0x1800cea23  mov     rcx, rdi; unsigned __int16 *
0x1800cea26  lea     rdx, [rbp+57h+arg_10]; unsigned int *
0x1800cea2a  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x1800cea2f  mov     [rbp+57h+var_60], eax
0x1800cea32  test    eax, eax
0x1800cea34  mov     eax, 16Ch
0x1800cea39  js      loc_1800CEBDD
0x1800cea3f  cmp     [rbp+57h+arg_8], 0
0x1800cea43  mov     [rbp+57h+var_5C], ax
0x1800cea47  jnz     short loc_1800CEA5E
0x1800cea49  mov     eax, 171h
0x1800cea4e  mov     [rbp+57h+var_60], 0
0x1800cea55  mov     [rbp+57h+var_5C], ax
0x1800cea59  jmp     loc_1800CEBE1
0x1800cea5e  mov     esi, 4
0x1800cea63  mov     r13d, 184h
0x1800cea69  mov     ebx, esi
0x1800cea6b  mov     eax, [rbp+57h+arg_0]
0x1800cea6e  lea     rcx, aEtl_0; "etl"
0x1800cea75  neg     eax
0x1800cea77  cmp     ebx, eax
0x1800cea79  jl      loc_1800CEBE1
0x1800cea7f  mov     eax, 5
0x1800cea84  mov     [rsp+0B0h+var_90], rcx
0x1800cea89  sub     eax, [rbp+57h+arg_8]
0x1800cea8c  lea     rdx, aSDS; "%s.%d.%s"
0x1800cea93  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cea97  mov     r9d, ebx
0x1800cea9a  mov     r8, rdi
0x1800cea9d  cmp     ebx, eax
0x1800cea9f  jl      short loc_1800CEAF8
0x1800ceaa1  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800ceaa6  mov     [rbp+57h+var_60], eax
0x1800ceaa9  test    eax, eax
0x1800ceaab  mov     eax, 180h
0x1800ceab0  js      loc_1800CEBDD
0x1800ceab6  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800ceaba  mov     [rbp+57h+var_5C], ax
0x1800ceabe  call    cs:__imp_DeleteFileW
0x1800ceac5  nop     dword ptr [rax+rax+00h]
0x1800ceaca  test    eax, eax
0x1800ceacc  jnz     loc_1800CEB9E
0x1800cead2  call    cs:__imp_GetLastError
0x1800cead9  nop     dword ptr [rax+rax+00h]
0x1800ceade  cmp     eax, 2
0x1800ceae1  jnz     loc_1800CEBA5
0x1800ceae7  mov     [rbp+57h+var_60], 0
0x1800ceaee  mov     [rbp+57h+var_5C], r13w
0x1800ceaf3  jmp     loc_1800CEB9E
0x1800ceaf8  neg     r9d
0x1800ceafb  lea     rax, aS0DS; "%s.0.%d.%s"
0x1800ceb02  cmovs   r9d, ebx
0x1800ceb06  test    ebx, ebx
0x1800ceb08  cmovs   rdx, rax; unsigned __int16 *
0x1800ceb0c  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800ceb11  mov     [rbp+57h+var_60], eax
0x1800ceb14  test    eax, eax
0x1800ceb16  mov     eax, 190h
0x1800ceb1b  js      loc_1800CEBDD
0x1800ceb21  mov     [rbp+57h+var_5C], ax
0x1800ceb25  lea     rdx, aSDS; "%s.%d.%s"
0x1800ceb2c  lea     rax, aEtl_0; "etl"
0x1800ceb33  mov     r9d, esi
0x1800ceb36  mov     r8, rdi
0x1800ceb39  mov     [rsp+0B0h+var_90], rax
0x1800ceb3e  lea     rcx, [rbp+57h+lpNewFileName]; this
0x1800ceb42  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800ceb47  mov     [rbp+57h+var_60], eax
0x1800ceb4a  test    eax, eax
0x1800ceb4c  mov     eax, 195h
0x1800ceb51  js      loc_1800CEBDD
0x1800ceb57  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x1800ceb5b  mov     r8d, 1; dwFlags
0x1800ceb61  mov     rcx, [rbp+57h+lpFileName]; lpExistingFileName
0x1800ceb65  mov     [rbp+57h+var_5C], ax
0x1800ceb69  call    cs:__imp_MoveFileExW
0x1800ceb70  nop     dword ptr [rax+rax+00h]
0x1800ceb75  test    eax, eax
0x1800ceb77  jnz     short loc_1800CEB9C
0x1800ceb79  call    cs:__imp_GetLastError
0x1800ceb80  nop     dword ptr [rax+rax+00h]
0x1800ceb85  cmp     eax, 2
0x1800ceb88  jnz     short loc_1800CEBBB
0x1800ceb8a  mov     eax, 19Ah
0x1800ceb8f  mov     [rbp+57h+var_60], 0
0x1800ceb96  mov     [rbp+57h+var_5C], ax
0x1800ceb9a  jmp     short loc_1800CEB9E
0x1800ceb9c  dec     esi
0x1800ceb9e  dec     ebx
0x1800ceba0  jmp     loc_1800CEA6B
0x1800ceba5  test    eax, eax
0x1800ceba7  jle     short loc_1800CEBB1
0x1800ceba9  movzx   eax, ax
0x1800cebac  or      eax, 80070000h
0x1800cebb1  mov     [rbp+57h+var_60], eax
0x1800cebb4  mov     [rbp+57h+var_5A], r13w
0x1800cebb9  jmp     short loc_1800CEBE1
0x1800cebbb  test    eax, eax
0x1800cebbd  jle     short loc_1800CEBC7
0x1800cebbf  movzx   eax, ax
0x1800cebc2  or      eax, 80070000h
0x1800cebc7  mov     [rbp+57h+var_60], eax
0x1800cebca  mov     eax, 19Ah
0x1800cebcf  jmp     short loc_1800CEBDD
0x1800cebd1  mov     [rbp+57h+var_60], 80070057h
0x1800cebd8  mov     eax, 164h
0x1800cebdd  mov     [rbp+57h+var_5A], ax
0x1800cebe1  mov     ebx, [rbp+57h+var_60]
0x1800cebe4  lea     rcx, [rbp+57h+lpNewFileName]; this
0x1800cebe8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800cebed  lea     rcx, [rbp+57h+lpFileName]; this
0x1800cebf1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800cebf6  lea     rcx, [rbp+57h+var_60]; this
0x1800cebfa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800cebff  mov     eax, ebx
0x1800cec01  add     rsp, 90h
0x1800cec08  pop     r13
0x1800cec0a  pop     rdi
0x1800cec0b  pop     rsi
0x1800cec0c  pop     rbx
0x1800cec0d  pop     rbp
0x1800cec0e  retn
```
