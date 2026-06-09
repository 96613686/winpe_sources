# _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x18006818c`
- end: `0x1800682e0`
- name: `?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `340`
- prototype: `__int64 __fastcall(wchar_t *this, LPSECURITY_ATTRIBUTES lpSecurityAttributes, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068090`
- `0x18006818c`

## callees

- `0x18001b044`
- `0x18001c368`
- `0x180031cd0`
- `0x18006818c`
- `0x18006852c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800682a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800682a6`
- `ntdll!wcsrchr` at `0x180068246`
- `ntdll!wcsrchr` at `0x180068246`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800681fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180068283`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800681fb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180068283`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilEnsureDirectoryWorker(
        wchar_t *this,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        struct _SECURITY_ATTRIBUTES *a3)
{
  int v3; // ebx
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  wchar_t *v10; // rax
  unsigned int v11; // r9d
  wchar_t *v12; // r14
  int v13; // eax
  DWORD LastError; // eax
  wchar_t *v16; // [rsp+88h] [rbp+20h] BYREF

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
  if ( (unsigned int)dword_1800DE000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 8) )
  {
    v16 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned int)&dword_1800CD014,
      v8,
      v9,
      (__int64)&v16);
  }
  return v6;
}

```

## disassembly

```asm
0x18006818c  push    rbx
0x18006818e  push    rbp
0x18006818f  push    rsi
0x180068190  push    rdi
0x180068191  push    r12
0x180068193  push    r14
0x180068195  sub     rsp, 38h
0x180068199  mov     ebx, r8d
0x18006819c  mov     rbp, rdx
0x18006819f  mov     rsi, rcx
0x1800681a2  cmp     r8d, 1Eh
0x1800681a6  jbe     short loc_1800681FB
0x1800681a8  mov     eax, cs:dword_1800DE000
0x1800681ae  mov     ebx, 800700A1h
0x1800681b3  cmp     eax, 2
0x1800681b6  jbe     loc_1800682D0
0x1800681bc  mov     edx, 8
0x1800681c1  lea     rcx, dword_1800DE000
0x1800681c8  call    _tlgKeywordOn
0x1800681cd  test    al, al
0x1800681cf  jz      loc_1800682D0
0x1800681d5  lea     rax, [rsp+68h+arg_18]
0x1800681dd  mov     [rsp+68h+arg_18], rsi
0x1800681e5  lea     rdx, dword_1800CD014
0x1800681ec  mov     [rsp+68h+var_48], rax
0x1800681f1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800681f6  jmp     loc_1800682D0
0x1800681fb  call    cs:__imp_CreateDirectoryW
0x180068202  nop     dword ptr [rax+rax+00h]
0x180068207  xor     edi, edi
0x180068209  test    eax, eax
0x18006820b  jnz     loc_1800682CE
0x180068211  call    cs:__imp_GetLastError
0x180068218  nop     dword ptr [rax+rax+00h]
0x18006821d  mov     rcx, rsi; wchar_t *
0x180068220  cmp     eax, 0B7h
0x180068225  jnz     short loc_18006823D
0x180068227  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x18006822c  neg     al
0x18006822e  sbb     ebx, ebx
0x180068230  not     ebx
0x180068232  and     ebx, 80070050h
0x180068238  jmp     loc_1800682D0
0x18006823d  mov     r12d, 5Ch ; '\'
0x180068243  mov     edx, r12d; Ch
0x180068246  call    cs:__imp_wcsrchr
0x18006824d  nop     dword ptr [rax+rax+00h]
0x180068252  mov     r14, rax
0x180068255  test    rax, rax
0x180068258  jnz     short loc_180068261
0x18006825a  mov     ebx, 80070003h
0x18006825f  jmp     short loc_1800682D0
0x180068261  lea     r8d, [rbx+1]; struct _SECURITY_ATTRIBUTES *
0x180068265  mov     [rax], di
0x180068268  mov     rdx, rbp; lpSecurityAttributes
0x18006826b  mov     rcx, rsi; this
0x18006826e  call    ?UtilEnsureDirectoryWorker@_werDetail@@YAJPEA_WPEAU_SECURITY_ATTRIBUTES@@K@Z; _werDetail::UtilEnsureDirectoryWorker(wchar_t *,_SECURITY_ATTRIBUTES *,ulong)
0x180068273  mov     [r14], r12w
0x180068277  mov     ebx, eax
0x180068279  test    eax, eax
0x18006827b  js      short loc_1800682D0
0x18006827d  mov     rdx, rbp; lpSecurityAttributes
0x180068280  mov     rcx, rsi; lpPathName
0x180068283  call    cs:__imp_CreateDirectoryW
0x18006828a  nop     dword ptr [rax+rax+00h]
0x18006828f  test    eax, eax
0x180068291  jnz     short loc_1800682CE
0x180068293  call    cs:__imp_GetLastError
0x18006829a  nop     dword ptr [rax+rax+00h]
0x18006829f  cmp     eax, 0B7h
0x1800682a4  jz      short loc_1800682BD
0x1800682a6  call    cs:__imp_GetLastError
0x1800682ad  nop     dword ptr [rax+rax+00h]
0x1800682b2  mov     ecx, eax; unsigned int
0x1800682b4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800682b9  mov     ebx, eax
0x1800682bb  jmp     short loc_1800682D0
0x1800682bd  mov     rcx, rsi; wchar_t *
0x1800682c0  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x1800682c5  mov     ebx, 80070050h
0x1800682ca  test    al, al
0x1800682cc  jz      short loc_1800682D0
0x1800682ce  mov     ebx, edi
0x1800682d0  mov     eax, ebx
0x1800682d2  add     rsp, 38h
0x1800682d6  pop     r14
0x1800682d8  pop     r12
0x1800682da  pop     rdi
0x1800682db  pop     rsi
0x1800682dc  pop     rbp
0x1800682dd  pop     rbx
0x1800682de  retn
```
