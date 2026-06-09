# CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x18000d888`
- end: `0x18000dbc0`
- name: `?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005e00`
- `0x18000c4d8`
- `0x18000cad8`
- `0x18002beb4`
- `0x18002cd9c`

## callees

- `0x180001df8`
- `0x18000aba4`
- `0x18000d888`
- `0x18001fd60`
- `0x18002da50`
- `0x18007ed40`

## import_xrefs

- `msvcrt!wcschr` at `0x18000d9ca`
- `msvcrt!wcschr` at `0x18000d9ca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000db0f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000db0f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000daf7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000db20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000daf7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000db20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMiscHelpersT<CEmptyType>::CreateFolderPath(wchar_t *a1)
{
  wchar_t *v1; // rax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 v5; // rax
  wchar_t *p_Str; // r8
  __int64 v7; // rdx
  wchar_t *v8; // rcx
  unsigned __int64 v9; // rdi
  wchar_t *v10; // rdi
  int v11; // r14d
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  __int64 v14; // rax
  unsigned __int16 *v15; // r8
  wchar_t *v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  wchar_t *v22; // r9
  __int64 v23; // r8
  unsigned __int16 *v24; // rcx
  int v25; // eax
  DWORD FileAttributesW; // eax
  unsigned __int64 v27; // rdx
  int v28; // ecx
  signed int LastError; // eax
  wchar_t Str; // [rsp+20h] [rbp-E0h] BYREF
  char v32; // [rsp+22h] [rbp-DEh] BYREF
  WCHAR FileName[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v34[264]; // [rsp+440h] [rbp+340h] BYREF

  if ( a1 )
  {
    v1 = a1;
    v2 = 260;
    do
    {
      if ( !*v1 )
        break;
      ++v1;
      --v2;
    }
    while ( v2 );
    v3 = v2 == 0 ? 0x80070057 : 0;
    v4 = (260 - v2) & -(__int64)(v2 != 0);
    if ( v2 )
    {
      v5 = 2147483646;
      p_Str = &Str;
      v7 = 261;
      do
      {
        if ( !v5 )
          break;
        if ( !*a1 )
          break;
        *p_Str++ = *a1++;
        --v5;
        --v7;
      }
      while ( v7 );
      v8 = p_Str - 1;
      v3 = v7 == 0 ? 0x8007007A : 0;
      if ( v7 )
        v8 = p_Str;
      *v8 = 0;
      if ( v7 )
      {
        if ( v4 )
        {
          --v4;
          v3 = 0;
        }
        else
        {
          v3 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
        if ( (v3 & 0x80000000) == 0 )
        {
          v9 = 2 * v4;
          if ( *(wchar_t *)((char *)&Str + v9) == 92 )
          {
            if ( v9 >= 0x20A )
LABEL_63:
              _report_rangecheckfailure();
            *(wchar_t *)((char *)&Str + v9) = 0;
          }
          v10 = (wchar_t *)&v32;
          FileName[0] = 0;
          if ( Str != 92 )
            v10 = &Str;
          v11 = 0;
          while ( 1 )
          {
            v12 = wcschr(v10, 0x5Cu);
            v13 = v12;
            if ( v12 )
            {
              v19 = v12 - v10;
              if ( v19 > 0x7FFFFFFE )
                goto LABEL_59;
              v20 = v12 - v10;
              v21 = v34;
              v22 = v10;
              v23 = 261;
              do
              {
                if ( !v20 )
                  break;
                if ( !*v22 )
                  break;
                *v21++ = *v22++;
                --v20;
                --v23;
              }
              while ( v23 );
              v24 = v21 - 1;
              if ( v23 )
                v24 = v21;
              *v24 = 0;
              v3 = v23 == 0 ? 0x8007007A : 0;
              if ( !v23 )
                goto LABEL_60;
              if ( v13 < v10 )
              {
                v3 = -2147024362;
                goto LABEL_60;
              }
              v17 = 2 * v19;
              if ( v17 >= 0x20A )
                goto LABEL_63;
              *(unsigned __int16 *)((char *)v34 + v17) = 0;
            }
            else
            {
              v14 = 2147483646;
              v15 = v34;
              v16 = v10;
              v17 = 261;
              do
              {
                if ( !v14 )
                  break;
                if ( !*v16 )
                  break;
                *v15++ = *v16++;
                --v14;
                --v17;
              }
              while ( v17 );
              v18 = v15 - 1;
              v3 = v17 == 0 ? 0x8007007A : 0;
              if ( v17 )
                v18 = v15;
              *v18 = 0;
              if ( !v17 )
                goto LABEL_60;
              v11 = 1;
            }
            v25 = StringCchCatW(FileName, v17, v34);
            v3 = v25;
            if ( v25 < 0 )
              goto LABEL_53;
            FileAttributesW = GetFileAttributesW(FileName);
            if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0)
              && (!CreateDirectoryW(FileName, 0) || GetFileAttributesW(FileName) == -1) )
            {
              break;
            }
            if ( v13 )
            {
              v25 = StringCchCatW(FileName, v27, L"\\");
              v3 = v25;
              if ( v25 < 0 )
              {
LABEL_53:
                v28 = v25;
                goto LABEL_61;
              }
              v10 = v13 + 1;
            }
            if ( v11 )
              goto LABEL_62;
          }
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v3 = -2147467259;
          }
        }
      }
    }
  }
  else
  {
LABEL_59:
    v3 = -2147024809;
  }
LABEL_60:
  v28 = v3;
LABEL_61:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v28);
LABEL_62:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x18000d888  push    rbp
0x18000d88a  push    rbx
0x18000d88b  push    rsi
0x18000d88c  push    rdi
0x18000d88d  push    r14
0x18000d88f  push    r15
0x18000d891  lea     rbp, [rsp-568h]
0x18000d899  sub     rsp, 668h
0x18000d8a0  mov     rax, cs:__security_cookie
0x18000d8a7  xor     rax, rsp
0x18000d8aa  mov     [rbp+590h+var_40], rax
0x18000d8b1  xor     r15d, r15d
0x18000d8b4  test    rcx, rcx
0x18000d8b7  jz      loc_18000DB86
0x18000d8bd  mov     r8d, 104h
0x18000d8c3  mov     rax, rcx
0x18000d8c6  mov     edx, r8d
0x18000d8c9  cmp     [rax], r15w
0x18000d8cd  jz      short loc_18000D8D9
0x18000d8cf  add     rax, 2
0x18000d8d3  sub     rdx, 1
0x18000d8d7  jnz     short loc_18000D8C9
0x18000d8d9  mov     rax, rdx
0x18000d8dc  neg     rax
0x18000d8df  mov     rax, rdx
0x18000d8e2  sbb     ebx, ebx
0x18000d8e4  sub     r8, rdx
0x18000d8e7  not     ebx
0x18000d8e9  and     ebx, 80070057h
0x18000d8ef  neg     rax
0x18000d8f2  sbb     rdi, rdi
0x18000d8f5  and     rdi, r8
0x18000d8f8  test    rdx, rdx
0x18000d8fb  jz      loc_18000DB8B
0x18000d901  mov     eax, 7FFFFFFEh
0x18000d906  lea     r8, [rsp+690h+Str]
0x18000d90b  mov     edx, 105h
0x18000d910  test    rax, rax
0x18000d913  jz      short loc_18000D934
0x18000d915  movzx   r9d, word ptr [rcx]
0x18000d919  test    r9w, r9w
0x18000d91d  jz      short loc_18000D934
0x18000d91f  mov     [r8], r9w
0x18000d923  add     rcx, 2
0x18000d927  add     r8, 2
0x18000d92b  dec     rax
0x18000d92e  sub     rdx, 1
0x18000d932  jnz     short loc_18000D910
0x18000d934  mov     rax, rdx
0x18000d937  lea     rcx, [r8-2]
0x18000d93b  neg     rax
0x18000d93e  sbb     ebx, ebx
0x18000d940  not     ebx
0x18000d942  and     ebx, 8007007Ah
0x18000d948  test    rdx, rdx
0x18000d94b  cmovnz  rcx, r8
0x18000d94f  mov     [rcx], r15w
0x18000d953  jz      loc_18000DB8B
0x18000d959  lea     rax, [rdi-1]
0x18000d95d  cmp     rax, rdi
0x18000d960  ja      short loc_18000D96A
0x18000d962  mov     rdi, rax
0x18000d965  mov     ebx, r15d
0x18000d968  jmp     short loc_18000D976
0x18000d96a  mov     ebx, 80070216h
0x18000d96f  mov     ecx, ebx
0x18000d971  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000d976  mov     ecx, ebx
0x18000d978  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000d97d  test    ebx, ebx
0x18000d97f  js      loc_18000DB8B
0x18000d985  add     rdi, rdi
0x18000d988  mov     ecx, 5Ch ; '\'
0x18000d98d  cmp     [rsp+rdi+690h+Str], cx
0x18000d992  jnz     short loc_18000D9A7
0x18000d994  cmp     rdi, 20Ah
0x18000d99b  jnb     loc_18000DBBA
0x18000d9a1  mov     [rsp+rdi+690h+Str], r15w
0x18000d9a7  cmp     [rsp+690h+Str], cx
0x18000d9ac  lea     rdi, [rsp+690h+var_66E]
0x18000d9b1  lea     rax, [rsp+690h+Str]
0x18000d9b6  mov     [rbp+590h+FileName], r15w
0x18000d9be  cmovnz  rdi, rax
0x18000d9c2  mov     r14d, r15d
0x18000d9c5  mov     edx, ecx; Ch
0x18000d9c7  mov     rcx, rdi; Str
0x18000d9ca  call    cs:__imp_wcschr
0x18000d9d0  mov     rsi, rax
0x18000d9d3  test    rax, rax
0x18000d9d6  jnz     short loc_18000DA40
0x18000d9d8  mov     eax, 7FFFFFFEh
0x18000d9dd  lea     r8, [rbp+590h+var_250]
0x18000d9e4  mov     rcx, rdi
0x18000d9e7  mov     edx, 105h
0x18000d9ec  test    rax, rax
0x18000d9ef  jz      short loc_18000DA10
0x18000d9f1  movzx   r9d, word ptr [rcx]
0x18000d9f5  test    r9w, r9w
0x18000d9f9  jz      short loc_18000DA10
0x18000d9fb  mov     [r8], r9w
0x18000d9ff  add     rcx, 2
0x18000da03  add     r8, 2
0x18000da07  dec     rax
0x18000da0a  sub     rdx, 1
0x18000da0e  jnz     short loc_18000D9EC
0x18000da10  mov     rax, rdx
0x18000da13  lea     rcx, [r8-2]
0x18000da17  neg     rax
0x18000da1a  sbb     ebx, ebx
0x18000da1c  not     ebx
0x18000da1e  and     ebx, 8007007Ah
0x18000da24  test    rdx, rdx
0x18000da27  cmovnz  rcx, r8
0x18000da2b  mov     [rcx], r15w
0x18000da2f  jz      loc_18000DB8B
0x18000da35  mov     r14d, 1
0x18000da3b  jmp     loc_18000DAD7
0x18000da40  mov     rdx, rsi
0x18000da43  sub     rdx, rdi
0x18000da46  sar     rdx, 1
0x18000da49  cmp     rdx, 7FFFFFFEh
0x18000da50  ja      loc_18000DB86
0x18000da56  mov     rcx, rdx
0x18000da59  lea     rax, [rbp+590h+var_250]
0x18000da60  mov     r9, rdi
0x18000da63  mov     r8d, 105h
0x18000da69  test    rcx, rcx
0x18000da6c  jz      short loc_18000DA8D
0x18000da6e  movzx   r10d, word ptr [r9]
0x18000da72  test    r10w, r10w
0x18000da76  jz      short loc_18000DA8D
0x18000da78  mov     [rax], r10w
0x18000da7c  add     r9, 2
0x18000da80  add     rax, 2
0x18000da84  dec     rcx
0x18000da87  sub     r8, 1
0x18000da8b  jnz     short loc_18000DA69
0x18000da8d  test    r8, r8
0x18000da90  lea     rcx, [rax-2]
0x18000da94  cmovnz  rcx, rax
0x18000da98  mov     rax, r8
0x18000da9b  neg     rax
0x18000da9e  sbb     ebx, ebx
0x18000daa0  not     ebx
0x18000daa2  mov     [rcx], r15w
0x18000daa6  and     ebx, 8007007Ah
0x18000daac  test    r8, r8
0x18000daaf  jz      loc_18000DB8B
0x18000dab5  cmp     rsi, rdi
0x18000dab8  jb      loc_18000DB7F
0x18000dabe  add     rdx, rdx; unsigned __int64
0x18000dac1  cmp     rdx, 20Ah
0x18000dac8  jnb     loc_18000DBBA
0x18000dace  mov     [rbp+rdx+590h+var_250], r15w
0x18000dad7  lea     r8, [rbp+590h+var_250]; unsigned __int16 *
0x18000dade  lea     rcx, [rbp+590h+FileName]; unsigned __int16 *
0x18000dae5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000daea  mov     ebx, eax
0x18000daec  test    eax, eax
0x18000daee  js      short loc_18000DB5B
0x18000daf0  lea     rcx, [rbp+590h+FileName]; lpFileName
0x18000daf7  call    cs:__imp_GetFileAttributesW
0x18000dafd  cmp     eax, 0FFFFFFFFh
0x18000db00  jz      short loc_18000DB06
0x18000db02  test    al, 10h
0x18000db04  jnz     short loc_18000DB2B
0x18000db06  xor     edx, edx; lpSecurityAttributes
0x18000db08  lea     rcx, [rbp+590h+FileName]; lpPathName
0x18000db0f  call    cs:__imp_CreateDirectoryW
0x18000db15  test    eax, eax
0x18000db17  jz      short loc_18000DB5F
0x18000db19  lea     rcx, [rbp+590h+FileName]; lpFileName
0x18000db20  call    cs:__imp_GetFileAttributesW
0x18000db26  cmp     eax, 0FFFFFFFFh
0x18000db29  jz      short loc_18000DB5F
0x18000db2b  test    rsi, rsi
0x18000db2e  jz      short loc_18000DB4D
0x18000db30  lea     r8, asc_180084C70; "\\"
0x18000db37  lea     rcx, [rbp+590h+FileName]; unsigned __int16 *
0x18000db3e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000db43  mov     ebx, eax
0x18000db45  test    eax, eax
0x18000db47  js      short loc_18000DB5B
0x18000db49  lea     rdi, [rsi+2]
0x18000db4d  test    r14d, r14d
0x18000db50  jnz     short loc_18000DB92
0x18000db52  lea     ecx, [r14+5Ch]
0x18000db56  jmp     loc_18000D9C5
0x18000db5b  mov     ecx, eax
0x18000db5d  jmp     short loc_18000DB8D
0x18000db5f  call    cs:__imp_GetLastError
0x18000db65  mov     ebx, eax
0x18000db67  test    eax, eax
0x18000db69  jnz     short loc_18000DB72
0x18000db6b  mov     ebx, 80004005h
0x18000db70  jmp     short loc_18000DB8B
0x18000db72  jle     short loc_18000DB8B
0x18000db74  movzx   ebx, ax
0x18000db77  or      ebx, 80070000h
0x18000db7d  jmp     short loc_18000DB8B
0x18000db7f  mov     ebx, 80070216h
0x18000db84  jmp     short loc_18000DB8B
0x18000db86  mov     ebx, 80070057h
0x18000db8b  mov     ecx, ebx
0x18000db8d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000db92  mov     ecx, ebx
0x18000db94  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000db99  mov     eax, ebx
0x18000db9b  mov     rcx, [rbp+590h+var_40]
0x18000dba2  xor     rcx, rsp; StackCookie
0x18000dba5  call    __security_check_cookie
0x18000dbaa  add     rsp, 668h
0x18000dbb1  pop     r15
0x18000dbb3  pop     r14
0x18000dbb5  pop     rdi
0x18000dbb6  pop     rsi
0x18000dbb7  pop     rbx
0x18000dbb8  pop     rbp
0x18000dbb9  retn
0x18000dbba  call    __report_rangecheckfailure
```
