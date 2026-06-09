# CWwanManager::SendToastNotification(_GUID const &,ushort const *,CWwanManager::WWAN_TOAST_TYPE)

- ea: `0x18007a430`
- end: `0x18007a91b`
- name: `?SendToastNotification@CWwanManager@@QEAAXAEBU_GUID@@PEBGW4WWAN_TOAST_TYPE@1@@Z`
- size: `1259`
- prototype: `void __high(const struct _GUID *, const unsigned __int16 *, enum CWwanManager::WWAN_TOAST_TYPE)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180068eac`
- `0x18006efb4`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180019f48`
- `0x18007a430`
- `0x1800996e4`
- `0x180099b20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a562`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a581`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a59c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a5ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a628`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a647`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a664`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a680`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a6d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a731`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a750`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a76d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a789`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a7db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a811`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a830`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a84d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a89f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a562`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a581`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a59c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a5ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a628`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a647`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a664`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a680`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a6d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a731`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a750`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a76d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a789`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a7db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a811`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a830`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a84d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007a89f`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18007a51b`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18007a51b`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a5b9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a69d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a7a6`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a86a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a5b9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a69d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a7a6`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18007a86a`

## string_xrefs

- `0x18007a863`: `@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/SIMLockToast.png}`
- `0x18007a5c6`: `SHLoadIndirectString failed to resolve icon path [%d].`
- `0x18007a6aa`: `SHLoadIndirectString failed to resolve icon path [%d].`
- `0x18007a7b3`: `SHLoadIndirectString failed to resolve icon path [%d].`
- `0x18007a877`: `SHLoadIndirectString failed to resolve icon path [%d].`
- `0x18007a8af`: `OPEN_SETTING`
- `0x18007a5b2`: `@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}`
- `0x18007a696`: `@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}`
- `0x18007a79f`: `@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}`
- `0x18007a7f2`: `SIM_REMOVE_SS`

## pseudocode

```c
void __fastcall CWwanManager::SendToastNotification(
        __int64 a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v7; // r8d
  __int64 v8; // rax
  int v9; // ebx
  int v10; // ebx
  HRESULT v11; // eax
  CWwanNotificationScheduler *Instance; // rax
  HRESULT v13; // eax
  CWwanNotificationScheduler *v14; // rax
  const unsigned __int16 *v15; // rcx
  HRESULT v16; // eax
  HRESULT v17; // eax
  const unsigned __int16 *v18; // [rsp+40h] [rbp-C0h]
  int v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v20[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v21[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR v22[64]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v24[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR v25[256]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+430h] [rbp+330h] BYREF

  v19[0] = 1;
  memset_0(v24, 0, 0x4Au);
  v8 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&a2->Data1 )
    v8 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)a2->Data4;
  if ( v8 )
    GuidToString(a2, v24, v7);
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v25, 0, sizeof(v25));
  memset_0(v20, 0, sizeof(v20));
  memset_0(v21, 0, sizeof(v21));
  memset_0(pszOutBuf, 0, 0x208u);
  memset_0(v22, 0, sizeof(v22));
  OOBEComplete(v19);
  if ( !a4 )
  {
    LoadStringW(g_hInstance, 0x300u, Buffer, 64);
    LoadStringW(g_hInstance, 0x301u, v25, 256);
    LoadStringW(g_hInstance, 0x306u, v20, 32);
    v17 = SHLoadIndirectString(
            L"@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/SIMLockToast.png}",
            pszOutBuf,
            0x104u,
            0);
    if ( v17 < 0 )
      WwanLog::Error(
        "CWwanManager::SendToastNotification",
        0,
        L"SHLoadIndirectString failed to resolve icon path [%d].",
        (unsigned int)v17);
    LoadStringW(g_hInstance, 0x30Bu, v22, 64);
    Instance = CWwanNotificationScheduler::GetInstance();
    v18 = a3;
    goto LABEL_25;
  }
  v9 = a4 - 1;
  if ( !v9 )
  {
    if ( !v19[0] )
      return;
    LoadStringW(g_hInstance, 0x302u, Buffer, 64);
    LoadStringW(g_hInstance, 0x30Au, v25, 256);
    LoadStringW(g_hInstance, 0x307u, v20, 32);
    LoadStringW(g_hInstance, 0x308u, v21, 32);
    v16 = SHLoadIndirectString(
            L"@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}",
            pszOutBuf,
            0x104u,
            0);
    if ( v16 < 0 )
      WwanLog::Error(
        "CWwanManager::SendToastNotification",
        0,
        L"SHLoadIndirectString failed to resolve icon path [%d].",
        (unsigned int)v16);
    LoadStringW(g_hInstance, 0x30Bu, v22, 64);
    v14 = CWwanNotificationScheduler::GetInstance();
    v15 = L"SIM_REMOVE_SS";
LABEL_17:
    CWwanNotificationScheduler::SendScheduledWwansvcToast(v14, Buffer, v25, v20, v21, pszOutBuf, v22, v15, v24);
    return;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( !v19[0] )
      return;
    LoadStringW(g_hInstance, 0x309u, Buffer, 64);
    LoadStringW(g_hInstance, 0x30Au, v25, 256);
    LoadStringW(g_hInstance, 0x307u, v20, 32);
    LoadStringW(g_hInstance, 0x308u, v21, 32);
    v13 = SHLoadIndirectString(
            L"@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}",
            pszOutBuf,
            0x104u,
            0);
    if ( v13 < 0 )
      WwanLog::Error(
        "CWwanManager::SendToastNotification",
        0,
        L"SHLoadIndirectString failed to resolve icon path [%d].",
        (unsigned int)v13);
    LoadStringW(g_hInstance, 0x30Bu, v22, 64);
    v14 = CWwanNotificationScheduler::GetInstance();
    v15 = L"SIM_INSERT_SS";
    goto LABEL_17;
  }
  if ( v10 == 1 && v19[0] )
  {
    LoadStringW(g_hInstance, 0x304u, Buffer, 64);
    LoadStringW(g_hInstance, 0x305u, v25, 256);
    LoadStringW(g_hInstance, 0x306u, v20, 32);
    v11 = SHLoadIndirectString(
            L"@{Windows?ms-resource://Windows.UI.ShellCommon/Files/Images/CellularToast.png}",
            pszOutBuf,
            0x104u,
            0);
    if ( v11 < 0 )
      WwanLog::Error(
        "CWwanManager::SendToastNotification",
        0,
        L"SHLoadIndirectString failed to resolve icon path [%d].",
        (unsigned int)v11);
    LoadStringW(g_hInstance, 0x30Bu, v22, 64);
    Instance = CWwanNotificationScheduler::GetInstance();
    v18 = v24;
LABEL_25:
    CWwanNotificationScheduler::SendScheduledWwansvcToast(
      Instance,
      Buffer,
      v25,
      v20,
      &String1,
      pszOutBuf,
      v22,
      L"OPEN_SETTING",
      v18);
  }
}

```

## disassembly

```asm
0x18007a430  mov     [rsp-8+arg_0], rbx
0x18007a435  mov     [rsp-8+arg_18], rsi
0x18007a43a  push    rbp
0x18007a43b  push    rdi
0x18007a43c  push    r15
0x18007a43e  lea     rbp, [rsp-550h]
0x18007a446  sub     rsp, 650h
0x18007a44d  mov     rax, cs:__security_cookie
0x18007a454  xor     rax, rsp
0x18007a457  mov     [rbp+560h+var_20], rax
0x18007a45e  mov     rdi, rdx
0x18007a461  mov     [rsp+660h+var_610], 1
0x18007a469  xor     edx, edx; Val
0x18007a46b  lea     rcx, [rbp+560h+var_480]; void *
0x18007a472  mov     rsi, r8
0x18007a475  mov     ebx, r9d
0x18007a478  lea     r8d, [rdx+4Ah]; Size
0x18007a47c  call    memset_0
0x18007a481  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18007a488  sub     rax, [rdi]
0x18007a48b  jnz     short loc_18007A498
0x18007a48d  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18007a494  sub     rax, [rdi+8]
0x18007a498  test    rax, rax
0x18007a49b  jz      short loc_18007A4AC
0x18007a49d  lea     rdx, [rbp+560h+var_480]; unsigned __int16 *
0x18007a4a4  mov     rcx, rdi; struct _GUID *
0x18007a4a7  call    ?GuidToString@@YAHPEBU_GUID@@PEAGH@Z; GuidToString(_GUID const *,ushort *,int)
0x18007a4ac  mov     edi, 80h
0x18007a4b1  lea     rcx, [rbp+560h+Buffer]; void *
0x18007a4b5  mov     r8d, edi; Size
0x18007a4b8  xor     edx, edx; Val
0x18007a4ba  call    memset_0
0x18007a4bf  xor     edx, edx; Val
0x18007a4c1  lea     rcx, [rbp+560h+var_430]; void *
0x18007a4c8  mov     r8d, 200h; Size
0x18007a4ce  call    memset_0
0x18007a4d3  lea     r15d, [rdi-40h]
0x18007a4d7  xor     edx, edx; Val
0x18007a4d9  mov     r8d, r15d; Size
0x18007a4dc  lea     rcx, [rsp+660h+var_600]; void *
0x18007a4e1  call    memset_0
0x18007a4e6  mov     r8d, r15d; Size
0x18007a4e9  lea     rcx, [rbp+560h+var_5C0]; void *
0x18007a4ed  xor     edx, edx; Val
0x18007a4ef  call    memset_0
0x18007a4f4  xor     edx, edx; Val
0x18007a4f6  lea     rcx, [rbp+560h+pszOutBuf]; void *
0x18007a4fd  mov     r8d, 208h; Size
0x18007a503  call    memset_0
0x18007a508  mov     r8d, edi; Size
0x18007a50b  lea     rcx, [rbp+560h+var_580]; void *
0x18007a50f  xor     edx, edx; Val
0x18007a511  call    memset_0
0x18007a516  lea     rcx, [rsp+660h+var_610]
0x18007a51b  call    cs:__imp_OOBEComplete
0x18007a521  test    ebx, ebx
0x18007a523  jz      loc_18007A7FE
0x18007a529  sub     ebx, 1
0x18007a52c  jz      loc_18007A713
0x18007a532  sub     ebx, 1
0x18007a535  jz      loc_18007A60A
0x18007a53b  cmp     ebx, 1
0x18007a53e  jnz     loc_18007A8F4
0x18007a544  cmp     [rsp+660h+var_610], 0
0x18007a549  jz      loc_18007A8F4
0x18007a54f  mov     rcx, cs:g_hInstance; hInstance
0x18007a556  lea     r8, [rbp+560h+Buffer]; lpBuffer
0x18007a55a  mov     r9d, r15d; cchBufferMax
0x18007a55d  mov     edx, 304h; uID
0x18007a562  call    cs:__imp_LoadStringW
0x18007a568  mov     rcx, cs:g_hInstance; hInstance
0x18007a56f  lea     r8, [rbp+560h+var_430]; lpBuffer
0x18007a576  mov     r9d, 100h; cchBufferMax
0x18007a57c  mov     edx, 305h; uID
0x18007a581  call    cs:__imp_LoadStringW
0x18007a587  mov     rcx, cs:g_hInstance; hInstance
0x18007a58e  lea     r9d, [rdi-60h]; cchBufferMax
0x18007a592  lea     r8, [rsp+660h+var_600]; lpBuffer
0x18007a597  mov     edx, 306h; uID
0x18007a59c  call    cs:__imp_LoadStringW
0x18007a5a2  xor     r9d, r9d; ppvReserved
0x18007a5a5  lea     rdx, [rbp+560h+pszOutBuf]; pszOutBuf
0x18007a5ac  mov     r8d, 104h; cchOutBuf
0x18007a5b2  lea     rcx, pszSource; "@{Windows?ms-resource://Windows.UI.Shel"...
0x18007a5b9  call    cs:__imp_SHLoadIndirectString
0x18007a5bf  test    eax, eax
0x18007a5c1  jns     short loc_18007A5DB
0x18007a5c3  mov     r9d, eax
0x18007a5c6  lea     r8, aShloadindirect; "SHLoadIndirectString failed to resolve "...
0x18007a5cd  xor     edx, edx; struct _GUID *
0x18007a5cf  lea     rcx, aCwwanmanagerSe_0; "CWwanManager::SendToastNotification"
0x18007a5d6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007a5db  mov     rcx, cs:g_hInstance; hInstance
0x18007a5e2  lea     r8, [rbp+560h+var_580]; lpBuffer
0x18007a5e6  mov     r9d, r15d; cchBufferMax
0x18007a5e9  mov     edx, 30Bh; uID
0x18007a5ee  call    cs:__imp_LoadStringW
0x18007a5f4  call    ?GetInstance@CWwanNotificationScheduler@@SAPEAV1@XZ; CWwanNotificationScheduler::GetInstance(void)
0x18007a5f9  lea     rcx, [rbp+560h+var_480]
0x18007a600  mov     [rsp+660h+var_620], rcx
0x18007a605  jmp     loc_18007A8AF
0x18007a60a  cmp     [rsp+660h+var_610], 0
0x18007a60f  jz      loc_18007A8F4
0x18007a615  mov     rcx, cs:g_hInstance; hInstance
0x18007a61c  lea     r8, [rbp+560h+Buffer]; lpBuffer
0x18007a620  mov     r9d, r15d; cchBufferMax
0x18007a623  mov     edx, 309h; uID
0x18007a628  call    cs:__imp_LoadStringW
0x18007a62e  mov     rcx, cs:g_hInstance; hInstance
0x18007a635  lea     r8, [rbp+560h+var_430]; lpBuffer
0x18007a63c  mov     r9d, 100h; cchBufferMax
0x18007a642  mov     edx, 30Ah; uID
0x18007a647  call    cs:__imp_LoadStringW
0x18007a64d  mov     rcx, cs:g_hInstance; hInstance
0x18007a654  lea     r8, [rsp+660h+var_600]; lpBuffer
0x18007a659  mov     r9d, 20h ; ' '; cchBufferMax
0x18007a65f  mov     edx, 307h; uID
0x18007a664  call    cs:__imp_LoadStringW
0x18007a66a  mov     rcx, cs:g_hInstance; hInstance
0x18007a671  lea     r8, [rbp+560h+var_5C0]; lpBuffer
0x18007a675  mov     r9d, 20h ; ' '; cchBufferMax
0x18007a67b  mov     edx, 308h; uID
0x18007a680  call    cs:__imp_LoadStringW
0x18007a686  xor     r9d, r9d; ppvReserved
0x18007a689  lea     rdx, [rbp+560h+pszOutBuf]; pszOutBuf
0x18007a690  mov     r8d, 104h; cchOutBuf
0x18007a696  lea     rcx, pszSource; "@{Windows?ms-resource://Windows.UI.Shel"...
0x18007a69d  call    cs:__imp_SHLoadIndirectString
0x18007a6a3  test    eax, eax
0x18007a6a5  jns     short loc_18007A6BF
0x18007a6a7  mov     r9d, eax
0x18007a6aa  lea     r8, aShloadindirect; "SHLoadIndirectString failed to resolve "...
0x18007a6b1  xor     edx, edx; struct _GUID *
0x18007a6b3  lea     rcx, aCwwanmanagerSe_0; "CWwanManager::SendToastNotification"
0x18007a6ba  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007a6bf  mov     rcx, cs:g_hInstance; hInstance
0x18007a6c6  lea     r8, [rbp+560h+var_580]; lpBuffer
0x18007a6ca  mov     r9d, r15d; cchBufferMax
0x18007a6cd  mov     edx, 30Bh; uID
0x18007a6d2  call    cs:__imp_LoadStringW
0x18007a6d8  call    ?GetInstance@CWwanNotificationScheduler@@SAPEAV1@XZ; CWwanNotificationScheduler::GetInstance(void)
0x18007a6dd  lea     rcx, [rbp+560h+var_480]
0x18007a6e4  mov     [rsp+660h+var_620], rcx
0x18007a6e9  lea     rcx, aSimInsertSs; "SIM_INSERT_SS"
0x18007a6f0  mov     [rsp+660h+var_628], rcx
0x18007a6f5  lea     rcx, [rbp+560h+var_580]
0x18007a6f9  mov     [rsp+660h+var_630], rcx
0x18007a6fe  lea     rcx, [rbp+560h+pszOutBuf]
0x18007a705  mov     [rsp+660h+var_638], rcx
0x18007a70a  lea     rcx, [rbp+560h+var_5C0]
0x18007a70e  jmp     loc_18007A8D7
0x18007a713  cmp     [rsp+660h+var_610], 0
0x18007a718  jz      loc_18007A8F4
0x18007a71e  mov     rcx, cs:g_hInstance; hInstance
0x18007a725  lea     r8, [rbp+560h+Buffer]; lpBuffer
0x18007a729  mov     r9d, r15d; cchBufferMax
0x18007a72c  mov     edx, 302h; uID
0x18007a731  call    cs:__imp_LoadStringW
0x18007a737  mov     rcx, cs:g_hInstance; hInstance
0x18007a73e  lea     r8, [rbp+560h+var_430]; lpBuffer
0x18007a745  mov     r9d, 100h; cchBufferMax
0x18007a74b  mov     edx, 30Ah; uID
0x18007a750  call    cs:__imp_LoadStringW
0x18007a756  mov     rcx, cs:g_hInstance; hInstance
0x18007a75d  lea     r8, [rsp+660h+var_600]; lpBuffer
0x18007a762  mov     r9d, 20h ; ' '; cchBufferMax
0x18007a768  mov     edx, 307h; uID
0x18007a76d  call    cs:__imp_LoadStringW
0x18007a773  mov     rcx, cs:g_hInstance; hInstance
0x18007a77a  lea     r8, [rbp+560h+var_5C0]; lpBuffer
0x18007a77e  mov     r9d, 20h ; ' '; cchBufferMax
0x18007a784  mov     edx, 308h; uID
0x18007a789  call    cs:__imp_LoadStringW
0x18007a78f  xor     r9d, r9d; ppvReserved
0x18007a792  lea     rdx, [rbp+560h+pszOutBuf]; pszOutBuf
0x18007a799  mov     r8d, 104h; cchOutBuf
0x18007a79f  lea     rcx, pszSource; "@{Windows?ms-resource://Windows.UI.Shel"...
0x18007a7a6  call    cs:__imp_SHLoadIndirectString
0x18007a7ac  test    eax, eax
0x18007a7ae  jns     short loc_18007A7C8
0x18007a7b0  mov     r9d, eax
0x18007a7b3  lea     r8, aShloadindirect; "SHLoadIndirectString failed to resolve "...
0x18007a7ba  xor     edx, edx; struct _GUID *
0x18007a7bc  lea     rcx, aCwwanmanagerSe_0; "CWwanManager::SendToastNotification"
0x18007a7c3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007a7c8  mov     rcx, cs:g_hInstance; hInstance
0x18007a7cf  lea     r8, [rbp+560h+var_580]; lpBuffer
0x18007a7d3  mov     r9d, r15d; cchBufferMax
0x18007a7d6  mov     edx, 30Bh; uID
0x18007a7db  call    cs:__imp_LoadStringW
0x18007a7e1  call    ?GetInstance@CWwanNotificationScheduler@@SAPEAV1@XZ; CWwanNotificationScheduler::GetInstance(void)
0x18007a7e6  lea     rcx, [rbp+560h+var_480]
0x18007a7ed  mov     [rsp+660h+var_620], rcx
0x18007a7f2  lea     rcx, aSimRemoveSs; "SIM_REMOVE_SS"
0x18007a7f9  jmp     loc_18007A6F0
0x18007a7fe  mov     rcx, cs:g_hInstance; hInstance
0x18007a805  lea     r8, [rbp+560h+Buffer]; lpBuffer
0x18007a809  mov     r9d, r15d; cchBufferMax
0x18007a80c  mov     edx, 300h; uID
0x18007a811  call    cs:__imp_LoadStringW
0x18007a817  mov     rcx, cs:g_hInstance; hInstance
0x18007a81e  lea     r8, [rbp+560h+var_430]; lpBuffer
0x18007a825  mov     r9d, 100h; cchBufferMax
0x18007a82b  mov     edx, 301h; uID
0x18007a830  call    cs:__imp_LoadStringW
0x18007a836  mov     rcx, cs:g_hInstance; hInstance
0x18007a83d  lea     r8, [rsp+660h+var_600]; lpBuffer
0x18007a842  mov     r9d, 20h ; ' '; cchBufferMax
0x18007a848  mov     edx, 306h; uID
0x18007a84d  call    cs:__imp_LoadStringW
0x18007a853  xor     r9d, r9d; ppvReserved
0x18007a856  lea     rdx, [rbp+560h+pszOutBuf]; pszOutBuf
0x18007a85d  mov     r8d, 104h; cchOutBuf
0x18007a863  lea     rcx, aWindowsMsResou; "@{Windows?ms-resource://Windows.UI.Shel"...
0x18007a86a  call    cs:__imp_SHLoadIndirectString
0x18007a870  test    eax, eax
0x18007a872  jns     short loc_18007A88C
0x18007a874  mov     r9d, eax
0x18007a877  lea     r8, aShloadindirect; "SHLoadIndirectString failed to resolve "...
0x18007a87e  xor     edx, edx; struct _GUID *
0x18007a880  lea     rcx, aCwwanmanagerSe_0; "CWwanManager::SendToastNotification"
0x18007a887  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007a88c  mov     rcx, cs:g_hInstance; hInstance
0x18007a893  lea     r8, [rbp+560h+var_580]; lpBuffer
0x18007a897  mov     r9d, r15d; cchBufferMax
0x18007a89a  mov     edx, 30Bh; uID
0x18007a89f  call    cs:__imp_LoadStringW
0x18007a8a5  call    ?GetInstance@CWwanNotificationScheduler@@SAPEAV1@XZ; CWwanNotificationScheduler::GetInstance(void)
0x18007a8aa  mov     [rsp+660h+var_620], rsi; unsigned __int16 *
0x18007a8af  lea     rcx, aOpenSetting; "OPEN_SETTING"
0x18007a8b6  mov     [rsp+660h+var_628], rcx; unsigned __int16 *
0x18007a8bb  lea     rcx, [rbp+560h+var_580]
0x18007a8bf  mov     [rsp+660h+var_630], rcx; unsigned __int16 *
0x18007a8c4  lea     rcx, [rbp+560h+pszOutBuf]
0x18007a8cb  mov     [rsp+660h+var_638], rcx; unsigned __int16 *
0x18007a8d0  lea     rcx, String1
0x18007a8d7  mov     [rsp+660h+var_640], rcx; unsigned __int16 *
0x18007a8dc  lea     r9, [rsp+660h+var_600]; unsigned __int16 *
0x18007a8e1  mov     rcx, rax; this
0x18007a8e4  lea     r8, [rbp+560h+var_430]; unsigned __int16 *
0x18007a8eb  lea     rdx, [rbp+560h+Buffer]; unsigned __int16 *
0x18007a8ef  call    ?SendScheduledWwansvcToast@CWwanNotificationScheduler@@QEAAXPEBG0000000@Z; CWwanNotificationScheduler::SendScheduledWwansvcToast(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18007a8f4  mov     rcx, [rbp+560h+var_20]
0x18007a8fb  xor     rcx, rsp; StackCookie
0x18007a8fe  call    __security_check_cookie
0x18007a903  lea     r11, [rsp+660h+var_10]
0x18007a90b  mov     rbx, [r11+20h]
0x18007a90f  mov     rsi, [r11+38h]
0x18007a913  mov     rsp, r11
0x18007a916  pop     r15
0x18007a918  pop     rdi
0x18007a919  pop     rbp
0x18007a91a  retn
```
