# CSrchAdminSSO::_OnSearchRootsNotification(void *,bool,bool &)

- ea: `0x180003900`
- end: `0x1800039ed`
- name: `?_OnSearchRootsNotification@CSrchAdminSSO@@AEAAJPEAX_NAEA_N@Z`
- size: `237`
- prototype: `int(CSrchAdminSSO *__hidden this, void *, bool, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003900`
- `0x180022840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003927`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003927`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800039b0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800039b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000394b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000397a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000394b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000397a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000391e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000391e`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x1800039ce`
- `api-ms-win-winrt-search-folder-l1-1-0!IsMSSearchEnabled` at `0x1800039ce`

## pseudocode

```c
__int64 __fastcall CSrchAdminSSO::_OnSearchRootsNotification(HKEY *this, void *a2, char a3, bool *a4)
{
  HKEY *phkResult; // rdi
  LSTATUS v8; // eax
  bool v9; // sf
  LSTATUS v10; // eax
  signed int v11; // ebx
  BOOL v12; // edx
  LSTATUS v13; // eax

  phkResult = this + 38;
  RegCloseKey(this[38]);
  ResetEvent(a2);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Search\\CrawlScopeManager\\Windows\\SystemIndex\\SearchRoots",
         0,
         0x10u,
         phkResult);
  v9 = v8 < 0;
  if ( v8 > 0 )
    v9 = 1;
  if ( !v9 )
  {
    v12 = 0;
LABEL_9:
    v13 = RegNotifyChangeKeyValue(*phkResult, v12, 1u, a2, 1);
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_11;
  }
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", 0, 0x10u, phkResult);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  v12 = 1;
  if ( v11 >= 0 )
    goto LABEL_9;
LABEL_11:
  if ( a3 || !(unsigned int)IsMSSearchEnabled(0, 0) )
  {
    CPHLocationCreator::OnSearchRootsChanged();
    *a4 = 1;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003900  push    rbx
0x180003902  push    rbp
0x180003903  push    rsi
0x180003904  push    rdi
0x180003905  push    r14
0x180003907  sub     rsp, 30h
0x18000390b  lea     rdi, [rcx+130h]
0x180003912  mov     rsi, r9
0x180003915  mov     rcx, [rdi]; hKey
0x180003918  mov     r14b, r8b
0x18000391b  mov     rbp, rdx
0x18000391e  call    cs:__imp_RegCloseKey
0x180003924  mov     rcx, rbp; hEvent
0x180003927  call    cs:__imp_ResetEvent
0x18000392d  mov     ebx, 10h
0x180003932  mov     [rsp+58h+phkResult], rdi; phkResult
0x180003937  mov     r9d, ebx; samDesired
0x18000393a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows Search\\Cr"...
0x180003941  xor     r8d, r8d; ulOptions
0x180003944  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000394b  call    cs:__imp_RegOpenKeyExW
0x180003951  test    eax, eax
0x180003953  jle     short loc_18000395F
0x180003955  movzx   eax, ax
0x180003958  or      eax, 80070000h
0x18000395d  test    eax, eax
0x18000395f  jns     short loc_18000399A
0x180003961  mov     r9d, ebx; samDesired
0x180003964  mov     [rsp+58h+phkResult], rdi; phkResult
0x180003969  xor     r8d, r8d; ulOptions
0x18000396c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x180003973  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000397a  call    cs:__imp_RegOpenKeyExW
0x180003980  mov     ebx, eax
0x180003982  test    eax, eax
0x180003984  jle     short loc_18000398F
0x180003986  movzx   ebx, ax
0x180003989  or      ebx, 80070000h
0x18000398f  mov     edx, 1
0x180003994  test    ebx, ebx
0x180003996  jns     short loc_18000399C
0x180003998  jmp     short loc_1800039C5
0x18000399a  xor     edx, edx; bWatchSubtree
0x18000399c  mov     rcx, [rdi]; hKey
0x18000399f  mov     r9, rbp; hEvent
0x1800039a2  mov     r8d, 1; dwNotifyFilter
0x1800039a8  mov     dword ptr [rsp+58h+phkResult], 1; fAsynchronous
0x1800039b0  call    cs:__imp_RegNotifyChangeKeyValue
0x1800039b6  mov     ebx, eax
0x1800039b8  test    eax, eax
0x1800039ba  jle     short loc_1800039C5
0x1800039bc  movzx   ebx, ax
0x1800039bf  or      ebx, 80070000h
0x1800039c5  test    r14b, r14b
0x1800039c8  jnz     short loc_1800039D8
0x1800039ca  xor     edx, edx
0x1800039cc  xor     ecx, ecx
0x1800039ce  call    cs:__imp_IsMSSearchEnabled
0x1800039d4  test    eax, eax
0x1800039d6  jnz     short loc_1800039E0
0x1800039d8  call    ?OnSearchRootsChanged@CPHLocationCreator@@SAXXZ; CPHLocationCreator::OnSearchRootsChanged(void)
0x1800039dd  mov     byte ptr [rsi], 1
0x1800039e0  mov     eax, ebx
0x1800039e2  add     rsp, 30h
0x1800039e6  pop     r14
0x1800039e8  pop     rdi
0x1800039e9  pop     rsi
0x1800039ea  pop     rbp
0x1800039eb  pop     rbx
0x1800039ec  retn
```
