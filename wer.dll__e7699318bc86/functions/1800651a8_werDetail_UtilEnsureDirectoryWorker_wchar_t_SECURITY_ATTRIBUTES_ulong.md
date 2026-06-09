# _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x1800651a8`
- end: `0x1800652d4`
- name: `?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `300`
- prototype: `__int64 __fastcall(wchar_t *this, LPSECURITY_ATTRIBUTES lpSecurityAttributes, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800650ac`
- `0x1800651a8`

## callees

- `0x18000716c`
- `0x180019808`
- `0x1800303dc`
- `0x1800651a8`
- `0x1800654ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800652a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800652a1`
- `ntdll!wcsrchr` at `0x180065253`
- `ntdll!wcsrchr` at `0x180065253`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180065217`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006528a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180065217`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18006528a`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilEnsureDirectoryWorker(
        wchar_t *this,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        struct _SECURITY_ATTRIBUTES *a3)
{
  int v3; // ebx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rax
  unsigned int v11; // r9d
  wchar_t *v12; // r14
  int v13; // eax
  DWORD LastError; // eax
  const size_t *v16; // [rsp+88h] [rbp+20h] BYREF

  v3 = (int)a3;
  if ( (unsigned int)a3 <= 0x1E )
  {
    if ( !CreateDirectoryW(this, lpSecurityAttributes) )
    {
      if ( GetLastError() == 183 )
        return !UtilPathIsDirectory(this) ? 0x80070050 : 0;
      v10 = wcsrchr(this, 0x5Cu);
      v12 = v10;
      if ( !v10 )
        return (unsigned int)-2147024893;
      *v10 = 0;
      v13 = _werDetail::UtilEnsureDirectoryWorker(
              this,
              lpSecurityAttributes,
              (struct _SECURITY_ATTRIBUTES *)(unsigned int)(v3 + 1),
              v11);
      *v12 = 92;
      v6 = v13;
      if ( v13 < 0 )
        return v6;
      if ( !CreateDirectoryW(this, lpSecurityAttributes) )
      {
        if ( GetLastError() != 183 )
        {
          LastError = GetLastError();
          return (unsigned int)ERROR_HR_FROM_WIN32(LastError);
        }
        v6 = -2147024816;
        if ( !UtilPathIsDirectory(this) )
          return v6;
      }
    }
    return 0;
  }
  v6 = -2147024735;
  if ( (unsigned int)dword_1800D9000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 8) )
  {
    v16 = (const size_t *)this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned __int8 *)&dword_1800C7F64,
      v8,
      v9,
      &v16);
  }
  return v6;
}

```

## disassembly

```asm
0x1800651a8  push    rbx
0x1800651aa  push    rbp
0x1800651ab  push    rsi
0x1800651ac  push    rdi
0x1800651ad  push    r12
0x1800651af  push    r14
0x1800651b1  sub     rsp, 38h
0x1800651b5  mov     ebx, r8d
0x1800651b8  mov     rbp, rdx
0x1800651bb  mov     rsi, rcx
0x1800651be  cmp     r8d, 1Eh
0x1800651c2  jbe     short loc_180065217
0x1800651c4  mov     eax, cs:dword_1800D9000
0x1800651ca  mov     ebx, 800700A1h
0x1800651cf  cmp     eax, 2
0x1800651d2  jbe     loc_1800652C5
0x1800651d8  mov     edx, 8
0x1800651dd  lea     rcx, dword_1800D9000
0x1800651e4  call    _tlgKeywordOn
0x1800651e9  test    al, al
0x1800651eb  jz      loc_1800652C5
0x1800651f1  lea     rax, [rsp+68h+arg_18]
0x1800651f9  mov     [rsp+68h+arg_18], rsi
0x180065201  lea     rdx, dword_1800C7F64
0x180065208  mov     [rsp+68h+var_48], rax
0x18006520d  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180065212  jmp     loc_1800652C5
0x180065217  call    cs:__imp_CreateDirectoryW
0x18006521d  xor     edi, edi
0x18006521f  test    eax, eax
0x180065221  jnz     loc_1800652C3
0x180065227  call    cs:__imp_GetLastError
0x18006522d  mov     rcx, rsi; wchar_t *
0x180065230  cmp     eax, 0B7h
0x180065235  jnz     short loc_18006524A
0x180065237  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18006523c  neg     al
0x18006523e  sbb     ebx, ebx
0x180065240  not     ebx
0x180065242  and     ebx, 80070050h
0x180065248  jmp     short loc_1800652C5
0x18006524a  mov     r12d, 5Ch ; '\'
0x180065250  mov     edx, r12d; Ch
0x180065253  call    cs:__imp_wcsrchr
0x180065259  mov     r14, rax
0x18006525c  test    rax, rax
0x18006525f  jnz     short loc_180065268
0x180065261  mov     ebx, 80070003h
0x180065266  jmp     short loc_1800652C5
0x180065268  lea     r8d, [rbx+1]; struct _SECURITY_ATTRIBUTES *
0x18006526c  mov     [rax], di
0x18006526f  mov     rdx, rbp; lpSecurityAttributes
0x180065272  mov     rcx, rsi; this
0x180065275  call    ?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z; _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)
0x18006527a  mov     [r14], r12w
0x18006527e  mov     ebx, eax
0x180065280  test    eax, eax
0x180065282  js      short loc_1800652C5
0x180065284  mov     rdx, rbp; lpSecurityAttributes
0x180065287  mov     rcx, rsi; lpPathName
0x18006528a  call    cs:__imp_CreateDirectoryW
0x180065290  test    eax, eax
0x180065292  jnz     short loc_1800652C3
0x180065294  call    cs:__imp_GetLastError
0x18006529a  cmp     eax, 0B7h
0x18006529f  jz      short loc_1800652B2
0x1800652a1  call    cs:__imp_GetLastError
0x1800652a7  mov     ecx, eax; unsigned int
0x1800652a9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800652ae  mov     ebx, eax
0x1800652b0  jmp     short loc_1800652C5
0x1800652b2  mov     rcx, rsi; wchar_t *
0x1800652b5  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x1800652ba  mov     ebx, 80070050h
0x1800652bf  test    al, al
0x1800652c1  jz      short loc_1800652C5
0x1800652c3  mov     ebx, edi
0x1800652c5  mov     eax, ebx
0x1800652c7  add     rsp, 38h
0x1800652cb  pop     r14
0x1800652cd  pop     r12
0x1800652cf  pop     rdi
0x1800652d0  pop     rsi
0x1800652d1  pop     rbp
0x1800652d2  pop     rbx
0x1800652d3  retn
```
