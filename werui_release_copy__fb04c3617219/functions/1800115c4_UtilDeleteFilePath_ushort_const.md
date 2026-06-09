# UtilDeleteFilePath(ushort const *)

- ea: `0x1800115c4`
- end: `0x180011719`
- name: `?UtilDeleteFilePath@@YAJPEBG@Z`
- size: `341`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001275c`

## callees

- `0x180001234`
- `0x180001694`
- `0x180003fe4`
- `0x180005ddc`
- `0x18000983c`
- `0x1800115c4`
- `0x180012d68`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180011601`
- `KERNEL32!CreateFileW` at `0x180011601`
- `KERNEL32!SetFileInformationByHandle` at `0x1800116a9`
- `KERNEL32!SetFileInformationByHandle` at `0x1800116a9`
- `KERNEL32!GetLastError` at `0x180011621`
- `KERNEL32!GetLastError` at `0x1800116b3`
- `KERNEL32!GetLastError` at `0x180011621`
- `KERNEL32!GetLastError` at `0x1800116b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilDeleteFilePath(WCHAR *a1)
{
  HANDLE FileW; // rax
  HANDLE v3; // rbx
  DWORD v4; // eax
  __int64 v5; // rcx
  int v6; // edi
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int16 *v10; // rdx
  DWORD LastError; // eax
  __int64 v12; // rcx
  WCHAR *v14; // [rsp+40h] [rbp-10h] BYREF
  char FileInformation; // [rsp+78h] [rbp+28h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+38h] BYREF

  hFile = 0;
  FileW = CreateFileW(a1, 0x10000u, 3u, 0, 3u, 0x2200080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  v3 = hFile;
  if ( (unsigned __int64)hFile + 1 > 1 )
  {
    v6 = UtilVerifyFilePath(a1, hFile);
    if ( v6 >= 0 )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v3, FileDispositionInfo, &FileInformation, 1u) )
      {
        LastError = GetLastError();
        v6 = ERROR_HR_FROM_WIN32(LastError);
        if ( (unsigned int)dword_180022000 > 2 )
        {
          if ( (unsigned __int8)tlgKeywordOn(v12, 8) )
          {
            v10 = &word_18001C196;
            goto LABEL_13;
          }
        }
      }
    }
    else if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180022000, 8) )
    {
      v10 = (__int16 *)byte_18001C1D9;
      goto LABEL_13;
    }
  }
  else
  {
    v4 = GetLastError();
    v6 = ERROR_HR_FROM_WIN32(v4);
    if ( (unsigned int)dword_180022000 > 2 && (unsigned __int8)tlgKeywordOn(v5, 8) )
    {
      v10 = (__int16 *)&dword_18001C214;
LABEL_13:
      v16 = v6;
      v14 = a1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v7,
        (_DWORD)v10,
        v8,
        v9,
        (__int64)&v14,
        (__int64)&v16);
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800115c4  mov     rax, rsp
0x1800115c7  mov     [rax+8], rbx
0x1800115cb  push    rbp
0x1800115cc  push    rsi
0x1800115cd  push    rdi
0x1800115ce  mov     rbp, rsp
0x1800115d1  sub     rsp, 50h
0x1800115d5  mov     rsi, rcx
0x1800115d8  mov     [rbp+hFile], 0
0x1800115e0  mov     qword ptr [rax-38h], 0
0x1800115e8  mov     dword ptr [rax-40h], 2200080h
0x1800115ef  mov     r8d, 3; dwShareMode
0x1800115f5  mov     [rax-48h], r8d
0x1800115f9  xor     r9d, r9d; lpSecurityAttributes
0x1800115fc  mov     edx, 10000h; dwDesiredAccess
0x180011601  call    cs:__imp_CreateFileW
0x180011607  mov     rdx, rax
0x18001160a  lea     rcx, [rbp+hFile]
0x18001160e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180011613  mov     rbx, [rbp+hFile]
0x180011617  lea     rax, [rbx+1]
0x18001161b  cmp     rax, 1
0x18001161f  ja      short loc_18001165D
0x180011621  call    cs:__imp_GetLastError
0x180011627  mov     ecx, eax; unsigned int
0x180011629  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001162e  mov     edi, eax
0x180011630  mov     eax, cs:dword_180022000
0x180011636  cmp     eax, 2
0x180011639  jbe     loc_180011701
0x18001163f  mov     edx, 8
0x180011644  call    _tlgKeywordOn
0x180011649  test    al, al
0x18001164b  jz      loc_180011701
0x180011651  lea     rdx, dword_18001C214
0x180011658  jmp     loc_1800116E2
0x18001165d  mov     rdx, rbx; void *
0x180011660  mov     rcx, rsi; unsigned __int16 *
0x180011663  call    ?UtilVerifyFilePath@@YAJPEBGPEAX@Z; UtilVerifyFilePath(ushort const *,void *)
0x180011668  mov     edi, eax
0x18001166a  test    eax, eax
0x18001166c  jns     short loc_180011694
0x18001166e  mov     ecx, cs:dword_180022000
0x180011674  cmp     ecx, 2
0x180011677  jbe     loc_180011701
0x18001167d  mov     edx, 8
0x180011682  call    _tlgKeywordOn
0x180011687  test    al, al
0x180011689  jz      short loc_180011701
0x18001168b  lea     rdx, byte_18001C1D9
0x180011692  jmp     short loc_1800116E2
0x180011694  mov     [rbp+FileInformation], 1
0x180011698  mov     r9d, 1; dwBufferSize
0x18001169e  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800116a2  lea     edx, [r9+3]; FileInformationClass
0x1800116a6  mov     rcx, rbx; hFile
0x1800116a9  call    cs:__imp_SetFileInformationByHandle
0x1800116af  test    eax, eax
0x1800116b1  jnz     short loc_180011701
0x1800116b3  call    cs:__imp_GetLastError
0x1800116b9  mov     ecx, eax; unsigned int
0x1800116bb  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800116c0  mov     edi, eax
0x1800116c2  mov     eax, cs:dword_180022000
0x1800116c8  cmp     eax, 2
0x1800116cb  jbe     short loc_180011701
0x1800116cd  mov     edx, 8
0x1800116d2  call    _tlgKeywordOn
0x1800116d7  test    al, al
0x1800116d9  jz      short loc_180011701
0x1800116db  lea     rdx, word_18001C196
0x1800116e2  lea     rax, [rbp+arg_10]
0x1800116e6  mov     [rsp+50h+var_28], rax
0x1800116eb  lea     rax, [rbp+var_10]
0x1800116ef  mov     [rsp+50h+var_30], rax
0x1800116f4  mov     [rbp+arg_10], edi
0x1800116f7  mov     [rbp+var_10], rsi
0x1800116fb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180011700  nop
0x180011701  lea     rcx, [rbp+hFile]
0x180011705  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001170a  mov     eax, edi
0x18001170c  mov     rbx, [rsp+50h+arg_0]
0x180011711  add     rsp, 50h
0x180011715  pop     rdi
0x180011716  pop     rsi
0x180011717  pop     rbp
0x180011718  retn
```
