# PRobustlyCreateableFile::RobustlyCreateFile(ushort const *,ushort)

- ea: `0x18000c158`
- end: `0x18000c294`
- name: `?RobustlyCreateFile@PRobustlyCreateableFile@@IEAAXPEBGG@Z`
- size: `316`
- prototype: `void __fastcall(PRobustlyCreateableFile *this, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000b97c`

## callees

- `0x18000b3f0`
- `0x18000b4a0`
- `0x18000c158`
- `0x18000cebc`
- `0x18000cef8`
- `0x18000d038`
- `0x18000ebec`
- `0x180011000`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c24f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c233`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c26a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c26a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c219`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c219`

## pseudocode

```c
void __fastcall PRobustlyCreateableFile::RobustlyCreateFile(
        PRobustlyCreateableFile *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3)
{
  int v6; // eax
  PRobustlyCreateableFile *v7; // rcx
  CStringize *v8; // rax
  DWORD LastError; // eax
  DWORD v10; // eax
  WCHAR ExistingFileName[528]; // [rsp+20h] [rbp-448h] BYREF

  v6 = (**(__int64 (__fastcall ***)(PRobustlyCreateableFile *))this)(this);
  if ( !v6 )
  {
    PRobustlyCreateableFile::RobustlyDeleteFile(v7, a2);
    v8 = CStringize::CStringize((CStringize *)ExistingFileName, a3);
    TrkReportEvent(0xC00030D7, 1u, v8, 0);
    v6 = 1;
  }
  if ( v6 == 1 )
  {
    if ( (int)StringCchCopyW(ExistingFileName, 0x105u, a2) < 0
      || (int)StringCchCatW(ExistingFileName, 0x105u, L".tmp") < 0 )
    {
      RaiseException(0x80000005, 0, 0, 0);
      __debugbreak();
    }
    (*(void (__fastcall **)(PRobustlyCreateableFile *, WCHAR *))(*(_QWORD *)this + 8LL))(this, ExistingFileName);
    if ( !MoveFileExW(ExistingFileName, a2, 2u) )
    {
      LastError = GetLastError();
      TrkRaiseWin32Error(LastError);
    }
    SetLastError(0);
    v6 = (**(__int64 (__fastcall ***)(PRobustlyCreateableFile *, const unsigned __int16 *))this)(this, a2);
  }
  if ( v6 != 2 )
  {
    v10 = GetLastError();
    TrkRaiseWin32Error(v10);
  }
}

```

## disassembly

```asm
0x18000c158  mov     [rsp+arg_18], rbx
0x18000c15d  push    rbp
0x18000c15e  push    rsi
0x18000c15f  push    rdi
0x18000c160  sub     rsp, 450h
0x18000c167  mov     rax, cs:__security_cookie
0x18000c16e  xor     rax, rsp
0x18000c171  mov     [rsp+468h+var_28], rax
0x18000c179  mov     rax, [rcx]
0x18000c17c  movzx   esi, r8w
0x18000c180  mov     rbx, rdx
0x18000c183  mov     rdi, rcx
0x18000c186  mov     rax, [rax]
0x18000c189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c18e  mov     ebp, 1
0x18000c193  test    eax, eax
0x18000c195  jnz     short loc_18000C1C0
0x18000c197  mov     rdx, rbx; unsigned __int16 *
0x18000c19a  call    ?RobustlyDeleteFile@PRobustlyCreateableFile@@IEAAXPEBG@Z; PRobustlyCreateableFile::RobustlyDeleteFile(ushort const *)
0x18000c19f  movzx   edx, si; unsigned __int16
0x18000c1a2  lea     rcx, [rsp+468h+ExistingFileName]; this
0x18000c1a7  call    ??0CStringize@@QEAA@G@Z; CStringize::CStringize(ushort)
0x18000c1ac  xor     r9d, r9d
0x18000c1af  mov     r8, rax
0x18000c1b2  mov     edx, ebp; unsigned __int16
0x18000c1b4  mov     ecx, 0C00030D7h; unsigned int
0x18000c1b9  call    ?TrkReportEvent@@YAJKGZZ; TrkReportEvent(ulong,ushort,...)
0x18000c1be  mov     eax, ebp
0x18000c1c0  cmp     eax, ebp
0x18000c1c2  jnz     loc_18000C24A
0x18000c1c8  mov     esi, 105h
0x18000c1cd  lea     rcx, [rsp+468h+ExistingFileName]; unsigned __int16 *
0x18000c1d2  mov     edx, esi; unsigned __int64
0x18000c1d4  mov     r8, rbx; unsigned __int16 *
0x18000c1d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c1dc  test    eax, eax
0x18000c1de  js      short loc_18000C25D
0x18000c1e0  lea     r8, aTmp; ".tmp"
0x18000c1e7  mov     edx, esi; unsigned __int64
0x18000c1e9  lea     rcx, [rsp+468h+ExistingFileName]; unsigned __int16 *
0x18000c1ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c1f3  test    eax, eax
0x18000c1f5  js      short loc_18000C25D
0x18000c1f7  mov     rax, [rdi]
0x18000c1fa  lea     rdx, [rsp+468h+ExistingFileName]
0x18000c1ff  mov     rcx, rdi
0x18000c202  mov     rax, [rax+8]
0x18000c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20b  mov     r8d, 2; dwFlags
0x18000c211  lea     rcx, [rsp+468h+ExistingFileName]; lpExistingFileName
0x18000c216  mov     rdx, rbx; lpNewFileName
0x18000c219  call    cs:__imp_MoveFileExW
0x18000c21f  test    eax, eax
0x18000c221  jnz     short loc_18000C231
0x18000c223  call    cs:__imp_GetLastError
0x18000c229  mov     ecx, eax; int
0x18000c22b  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000c231  xor     ecx, ecx; dwErrCode
0x18000c233  call    cs:__imp_SetLastError
0x18000c239  mov     rax, [rdi]
0x18000c23c  mov     rdx, rbx
0x18000c23f  mov     rcx, rdi
0x18000c242  mov     rax, [rax]
0x18000c245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24a  cmp     eax, 2
0x18000c24d  jz      short loc_18000C271
0x18000c24f  call    cs:__imp_GetLastError
0x18000c255  mov     ecx, eax; int
0x18000c257  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000c25d  xor     r9d, r9d; lpArguments
0x18000c260  xor     r8d, r8d; nNumberOfArguments
0x18000c263  xor     edx, edx; dwExceptionFlags
0x18000c265  mov     ecx, 80000005h; dwExceptionCode
0x18000c26a  call    cs:__imp_RaiseException
0x18000c270  int     3; Trap to Debugger
0x18000c271  mov     rcx, [rsp+468h+var_28]
0x18000c279  xor     rcx, rsp; StackCookie
0x18000c27c  call    __security_check_cookie
0x18000c281  mov     rbx, [rsp+468h+arg_18]
0x18000c289  add     rsp, 450h
0x18000c290  pop     rdi
0x18000c291  pop     rsi
0x18000c292  pop     rbp
0x18000c293  retn
```
