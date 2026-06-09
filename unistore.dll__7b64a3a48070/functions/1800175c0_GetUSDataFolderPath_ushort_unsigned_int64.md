# GetUSDataFolderPath(ushort *,unsigned __int64)

- ea: `0x1800175c0`
- end: `0x1800177af`
- name: `?GetUSDataFolderPath@@YAJPEAG_K@Z`
- size: `495`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800185b8`
- `0x180032170`
- `0x18007df9c`
- `0x18007e6fc`

## callees

- `0x1800175c0`
- `0x18001784c`
- `0x180071e60`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017648`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017648`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001774a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001774a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017764`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800176b6`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800176b6`

## string_xrefs

- `0x1800176ca`: `Comms`

## pseudocode

```c
__int64 __fastcall GetUSDataFolderPath(unsigned __int16 *a1, unsigned __int64 a2, __int64 a3)
{
  KNOWNFOLDERID v5; // xmm0
  __int64 v6; // r9
  HRESULT v7; // ebx
  __int64 v8; // rdx
  __int64 v10; // r8
  HRESULT v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r9
  unsigned __int64 i; // rdi
  int pvData; // [rsp+40h] [rbp-19h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-11h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-9h] BYREF
  PCWSTR pszMore[3]; // [rsp+58h] [rbp-1h]
  KNOWNFOLDERID rfid; // [rsp+70h] [rbp+17h] BYREF

  if ( !a1 )
  {
    v6 = 69;
LABEL_7:
    v7 = -2147024809;
    v8 = 0;
    goto LABEL_8;
  }
  if ( !a2 )
  {
    v6 = 70;
    goto LABEL_7;
  }
  if ( g_unistorePathReplace )
  {
    v7 = StringCchCopyW(a1, a2, &g_unistorePathReplace);
    if ( v7 >= 0 )
      return 0;
    v8 = 1;
    v6 = 74;
LABEL_8:
    Log_UnistoreHREvent_16((unsigned int)v7, v8, a3, v6);
    return (unsigned int)v7;
  }
  pvData = 0;
  pcbData = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\Unified Store",
    L"UseLegacyDBLocation",
    0x20000018u,
    0,
    &pvData,
    &pcbData);
  if ( pvData )
    v5 = (KNOWNFOLDERID)xmmword_1800DB238;
  else
    v5 = (KNOWNFOLDERID)xmmword_18010B730;
  rfid = v5;
  ppszPath = 0;
  v7 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, &ppszPath);
  if ( v7 < 0 )
  {
    v14 = 87;
LABEL_15:
    Log_UnistoreHREvent_16((unsigned int)v7, 1, v10, v14);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return (unsigned int)v7;
  }
  pszMore[1] = L"Comms";
  pszMore[0] = ppszPath;
  pszMore[2] = L"Unistore";
  v11 = StringCchCopyW(a1, a2, ppszPath);
  v7 = v11;
  if ( v11 < 0 )
  {
    v13 = 33;
LABEL_14:
    Log_UnistoreHREvent_16((unsigned int)v11, 1, v12, v13);
    v14 = 96;
    goto LABEL_15;
  }
  for ( i = 1; i < 3; ++i )
  {
    v11 = PathCchCombine(a1, a2, a1, pszMore[i]);
    v7 = v11;
    if ( v11 < 0 )
    {
      v13 = 37;
      goto LABEL_14;
    }
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 0;
}

```

## disassembly

```asm
0x1800175c0  mov     [rsp-8+arg_10], rbx
0x1800175c5  push    rbp
0x1800175c6  push    rsi
0x1800175c7  push    rdi
0x1800175c8  push    r14
0x1800175ca  push    r15
0x1800175cc  lea     rbp, [rsp-37h]
0x1800175d1  sub     rsp, 90h
0x1800175d8  mov     rax, cs:__security_cookie
0x1800175df  xor     rax, rsp
0x1800175e2  mov     [rbp+57h+var_30], rax
0x1800175e6  xor     r15d, r15d
0x1800175e9  mov     rsi, rdx
0x1800175ec  mov     r14, rcx
0x1800175ef  test    rcx, rcx
0x1800175f2  jz      short loc_18001765D
0x1800175f4  test    rdx, rdx
0x1800175f7  jz      loc_180017779
0x1800175fd  cmp     cs:?g_unistorePathReplace@@3PAGA, r15w; ushort near * g_unistorePathReplace
0x180017605  jnz     loc_180017784
0x18001760b  lea     rax, [rbp+57h+var_60]
0x18001760f  mov     [rbp+57h+var_70], r15d
0x180017613  mov     [rsp+0B0h+pcbData], rax; pcbData
0x180017618  lea     r8, ?c_wszUnistoreUseLegacy@@3QBGB; "UseLegacyDBLocation"
0x18001761f  lea     rax, [rbp+57h+var_70]
0x180017623  mov     [rbp+57h+var_60], 4
0x18001762a  mov     [rsp+0B0h+pvData], rax; pvData
0x18001762f  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x180017636  mov     r9d, 20000018h; dwFlags
0x18001763c  mov     [rsp+0B0h+pdwType], r15; pdwType
0x180017641  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180017648  call    cs:__imp_RegGetValueW
0x18001764e  cmp     [rbp+57h+var_70], r15d
0x180017652  jnz     short loc_180017696
0x180017654  movups  xmm0, cs:xmmword_18010B730
0x18001765b  jmp     short loc_18001769D
0x18001765d  mov     r9d, 45h ; 'E'
0x180017663  mov     ebx, 80070057h
0x180017668  xor     edx, edx
0x18001766a  mov     ecx, ebx
0x18001766c  call    Log_UnistoreHREvent_16
0x180017671  mov     eax, ebx
0x180017673  mov     rcx, [rbp+57h+var_30]
0x180017677  xor     rcx, rsp; StackCookie
0x18001767a  call    __security_check_cookie
0x18001767f  mov     rbx, [rsp+0B0h+arg_10]
0x180017687  add     rsp, 90h
0x18001768e  pop     r15
0x180017690  pop     r14
0x180017692  pop     rdi
0x180017693  pop     rsi
0x180017694  pop     rbp
0x180017695  retn
0x180017696  movups  xmm0, cs:xmmword_1800DB238
0x18001769d  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x1800176a1  movdqa  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x1800176a6  xor     r8d, r8d; hToken
0x1800176a9  mov     [rbp+57h+ppszPath], r15
0x1800176ad  mov     edx, 4000h; dwFlags
0x1800176b2  lea     rcx, [rbp+57h+rfid]; rfid
0x1800176b6  call    cs:__imp_SHGetKnownFolderPath
0x1800176bc  mov     ebx, eax
0x1800176be  test    eax, eax
0x1800176c0  js      loc_180017771
0x1800176c6  mov     r8, [rbp+57h+ppszPath]; unsigned __int16 *
0x1800176ca  lea     rax, ?gc_szCommsFolderName@@3QBGB; "Comms"
0x1800176d1  mov     [rbp+57h+var_50], rax
0x1800176d5  mov     rdx, rsi; unsigned __int64
0x1800176d8  lea     rax, ?gc_szUSStoresFolderName@@3QBGB; "Unistore"
0x1800176df  mov     [rbp+57h+pszMore], r8
0x1800176e3  mov     rcx, r14; unsigned __int16 *
0x1800176e6  mov     [rbp+57h+var_48], rax
0x1800176ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800176ef  mov     ebx, eax
0x1800176f1  test    eax, eax
0x1800176f3  jns     short loc_180017731
0x1800176f5  mov     r9d, 21h ; '!'
0x1800176fb  mov     edx, 1
0x180017700  mov     ecx, eax
0x180017702  call    Log_UnistoreHREvent_16
0x180017707  mov     r9d, 60h ; '`'
0x18001770d  mov     edx, 1
0x180017712  mov     ecx, ebx
0x180017714  call    Log_UnistoreHREvent_16
0x180017719  mov     rcx, [rbp+57h+ppszPath]; pv
0x18001771d  test    rcx, rcx
0x180017720  jz      loc_180017671
0x180017726  call    cs:__imp_CoTaskMemFree
0x18001772c  jmp     loc_180017671
0x180017731  mov     edi, 1
0x180017736  cmp     rdi, 3
0x18001773a  jnb     short loc_18001775B
0x18001773c  mov     r9, [rbp+rdi*8+57h+pszMore]; pszMore
0x180017741  mov     r8, r14; pszPathIn
0x180017744  mov     rdx, rsi; cchPathOut
0x180017747  mov     rcx, r14; pszPathOut
0x18001774a  call    cs:__imp_PathCchCombine
0x180017750  mov     ebx, eax
0x180017752  test    eax, eax
0x180017754  js      short loc_1800177A4
0x180017756  inc     rdi
0x180017759  jmp     short loc_180017736
0x18001775b  mov     rcx, [rbp+57h+ppszPath]; pv
0x18001775f  test    rcx, rcx
0x180017762  jz      short loc_18001776A
0x180017764  call    cs:__imp_CoTaskMemFree
0x18001776a  xor     eax, eax
0x18001776c  jmp     loc_180017673
0x180017771  mov     r9d, 57h ; 'W'
0x180017777  jmp     short loc_18001770D
0x180017779  mov     r9d, 46h ; 'F'
0x18001777f  jmp     loc_180017663
0x180017784  lea     r8, ?g_unistorePathReplace@@3PAGA; unsigned __int16 *
0x18001778b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017790  mov     ebx, eax
0x180017792  test    eax, eax
0x180017794  jns     short loc_18001776A
0x180017796  mov     edx, 1
0x18001779b  lea     r9d, [rdx+49h]
0x18001779f  jmp     loc_18001766A
0x1800177a4  mov     r9d, 25h ; '%'
0x1800177aa  jmp     loc_1800176FB
```
