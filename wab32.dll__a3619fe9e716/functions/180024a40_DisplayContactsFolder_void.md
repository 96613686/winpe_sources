# DisplayContactsFolder(void)

- ea: `0x180024a40`
- end: `0x180024b64`
- name: `?DisplayContactsFolder@@YAJXZ`
- size: `292`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800094b4`
- `0x1800464e4`

## callees

- `0x180001010`
- `0x1800010a0`
- `0x180001150`
- `0x1800011fc`
- `0x180024a40`
- `0x18006b400`
- `0x18006b620`
- `0x180091eaa`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x180024ad1`
- `SHELL32!ShellExecuteExW` at `0x180024ad1`
- `SHELL32!SHGetKnownFolderIDList` at `0x180024a8c`
- `SHELL32!SHGetKnownFolderIDList` at `0x180024a8c`
- `KERNEL32!GetLastError` at `0x180024b22`
- `KERNEL32!GetLastError` at `0x180024b22`
- `ole32!CoTaskMemFree` at `0x180024b42`
- `ole32!CoTaskMemFree` at `0x180024b42`

## string_xrefs

- `0x180024af2`: `Opened Contacts folder in File Explorer`

## pseudocode

```c
__int64 DisplayContactsFolder(void)
{
  int v0; // ebx
  BOOL v1; // ebx
  int v2; // ecx
  int v3; // r8d
  int v4; // r9d
  signed int LastError; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v8[272]; // [rsp+A0h] [rbp-60h] BYREF
  LPITEMIDLIST ppidl; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v10; // [rsp+1C8h] [rbp+C8h] BYREF

  ppidl = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  CComProtector::CComProtector((CComProtector *)v8);
  v0 = SHGetKnownFolderIDList(&FOLDERID_Contacts, 0, 0, &ppidl);
  if ( v0 >= 0 )
  {
    pExecInfo.cbSize = 112;
    pExecInfo.lpVerb = L"open";
    pExecInfo.lpIDList = ppidl;
    pExecInfo.nShow = 10;
    pExecInfo.fMask = 100663556;
    v1 = ShellExecuteExW(&pExecInfo);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
    if ( (unsigned int)dword_1800A9A40 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v10 = "Opened Contacts folder in File Explorer";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v2,
        (unsigned int)byte_18009FF79,
        v3,
        v4,
        (__int64)&v10);
    }
    TraceLoggingUnregister_EventUnregister();
    if ( v1 )
    {
      v0 = 0;
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  CoTaskMemFree(ppidl);
  CComProtector::~CComProtector((CComProtector *)v8);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180024a40  mov     [rsp-8+arg_10], rbx
0x180024a45  push    rbp
0x180024a46  lea     rbp, [rsp-0B0h]
0x180024a4e  sub     rsp, 1B0h
0x180024a55  xor     edx, edx; Val
0x180024a57  mov     [rbp+0B0h+ppidl], 0
0x180024a62  lea     rcx, [rsp+1B0h+pExecInfo]; void *
0x180024a67  lea     r8d, [rdx+70h]; Size
0x180024a6b  call    memset_0
0x180024a70  lea     rcx, [rbp+0B0h+var_110]; this
0x180024a74  call    ??0CComProtector@@QEAA@XZ; CComProtector::CComProtector(void)
0x180024a79  lea     r9, [rbp+0B0h+ppidl]; ppidl
0x180024a80  xor     r8d, r8d; hToken
0x180024a83  xor     edx, edx; dwFlags
0x180024a85  lea     rcx, FOLDERID_Contacts; rfid
0x180024a8c  call    cs:__imp_SHGetKnownFolderIDList
0x180024a92  mov     ebx, eax
0x180024a94  test    eax, eax
0x180024a96  js      loc_180024B3B
0x180024a9c  lea     rax, aOpen_0; "open"
0x180024aa3  mov     [rsp+1B0h+pExecInfo.cbSize], 70h ; 'p'
0x180024aab  mov     [rsp+1B0h+pExecInfo.lpVerb], rax
0x180024ab0  lea     rcx, [rsp+1B0h+pExecInfo]; pExecInfo
0x180024ab5  mov     rax, [rbp+0B0h+ppidl]
0x180024abc  mov     [rsp+1B0h+pExecInfo.lpIDList], rax
0x180024ac1  mov     [rsp+1B0h+pExecInfo.nShow], 0Ah
0x180024ac9  mov     [rsp+1B0h+pExecInfo.fMask], 6000104h
0x180024ad1  call    cs:__imp_ShellExecuteExW
0x180024ad7  mov     ebx, eax
0x180024ad9  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180024ade  mov     ecx, cs:dword_1800A9A40
0x180024ae4  cmp     ecx, 5
0x180024ae7  jbe     short loc_180024B18
0x180024ae9  call    _tlgKeywordOn
0x180024aee  test    al, al
0x180024af0  jz      short loc_180024B18
0x180024af2  lea     rax, aOpenedContacts; "Opened Contacts folder in File Explorer"
0x180024af9  mov     [rbp+0B0h+arg_8], rax
0x180024b00  lea     rdx, byte_18009FF79
0x180024b07  lea     rax, [rbp+0B0h+arg_8]
0x180024b0e  mov     [rsp+1B0h+var_190], rax
0x180024b13  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180024b18  call    TraceLoggingUnregister_EventUnregister
0x180024b1d  cmp     ebx, 1
0x180024b20  jz      short loc_180024B39
0x180024b22  call    cs:__imp_GetLastError
0x180024b28  mov     ebx, eax
0x180024b2a  test    eax, eax
0x180024b2c  jle     short loc_180024B3B
0x180024b2e  movzx   ebx, ax
0x180024b31  or      ebx, 80070000h
0x180024b37  jmp     short loc_180024B3B
0x180024b39  xor     ebx, ebx
0x180024b3b  mov     rcx, [rbp+0B0h+ppidl]; pv
0x180024b42  call    cs:__imp_CoTaskMemFree
0x180024b48  lea     rcx, [rbp+0B0h+var_110]; this
0x180024b4c  call    ??1CComProtector@@QEAA@XZ; CComProtector::~CComProtector(void)
0x180024b51  mov     eax, ebx
0x180024b53  mov     rbx, [rsp+1B0h+arg_10]
0x180024b5b  add     rsp, 1B0h
0x180024b62  pop     rbp
0x180024b63  retn
```
