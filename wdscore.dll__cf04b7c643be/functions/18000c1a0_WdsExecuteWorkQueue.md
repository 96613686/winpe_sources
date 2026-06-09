# WdsExecuteWorkQueue

- ea: `0x18000c1a0`
- end: `0x18000c848`
- name: `WdsExecuteWorkQueue`
- size: `1704`
- prototype: `__int64 __fastcall(int, int, int, int, struct WDS_QUEUE_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18000cfb0`

## callees

- `0x180002250`
- `0x1800027dc`
- `0x180002878`
- `0x180003108`
- `0x180004830`
- `0x180005e18`
- `0x18000a288`
- `0x18000a8f0`
- `0x18000ad30`
- `0x18000b3fc`
- `0x18000c1a0`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c80b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c80b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180028530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002850e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002850e`

## string_xrefs

- `0x18000c23a`: `Couldn't create clean panther temp dir`
- `0x18000c3a8`: `Could not locate saved '%s' in working directory`
- `0x18000c4ac`: `Could not locate saved '%s' in working directory`

## pseudocode

```c
__int64 __fastcall WdsExecuteWorkQueue(
        const char **a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        struct WDS_QUEUE_INFO *a5,
        unsigned int a6)
{
  unsigned int v6; // edi
  unsigned int v10; // r13d
  int v11; // r15d
  DWORD LastError; // ebx
  int *v13; // rax
  int v14; // esi
  unsigned int v15; // r8d
  DWORD v16; // ebx
  int *v17; // rax
  DWORD v18; // ebx
  int *v19; // rax
  DWORD v20; // ebx
  int *v21; // rax
  unsigned int v22; // r8d
  DWORD v23; // ebx
  int *v24; // rax
  DWORD v25; // ebx
  int *v26; // rax
  unsigned int i; // ebx
  DWORD v28; // ebx
  int *v29; // rax
  unsigned int j; // ebx
  DWORD v31; // ebx
  int *v32; // rax
  unsigned int k; // ebx
  DWORD v34; // ebx
  int *v35; // rax
  DWORD v36; // ebx
  int *v37; // rax
  DWORD v38; // ebx
  unsigned __int16 v41[264]; // [rsp+70h] [rbp-458h] BYREF
  unsigned __int16 v42[264]; // [rsp+280h] [rbp-248h] BYREF
  LPCWSTR lpModuleName; // [rsp+4C8h] [rbp+0h]

  v6 = a4;
  v10 = 0;
  v11 = 0;
  if ( a1 && (unsigned int)pInitializeWorkQueue((struct WDS_QUEUE_INFO *)a1, a5, a6) )
  {
    v11 = 1;
    if ( !(unsigned int)pCreateCleanTempDir() )
    {
      LastError = GetLastError();
      v13 = (int *)ConstructPartialMsgW(0x3000022u, "Couldn't create clean panther temp dir");
      WdsSetupLogMessageW(
        v13,
        589824,
        (__int64)L"D",
        0,
        0x5B6u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue",
        lpModuleName,
        LastError,
        0,
        0);
      v6 = a4;
    }
    if ( a2 )
    {
      v14 = a2 - 1;
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          memset_0(v41, 0, 0x208u);
          memset_0(v42, 0, 0x208u);
          if ( (int)StringCchPrintfW(v42, 0x104u, L"%s%s", *a1, L"Online") < 0 )
          {
            v16 = GetLastError();
            v17 = (int *)ConstructPartialMsgW(0x2000029u, "stringcchprintf failed for '%s'", *a1);
            WdsSetupLogMessageW(
              v17,
              589824,
              (__int64)L"D",
              0,
              0x623u,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"WdsExecuteWorkQueue",
              lpModuleName,
              v16,
              0,
              0);
LABEL_39:
            v10 = 0;
            goto LABEL_40;
          }
          if ( !(unsigned int)pLookupContentsFileEntry(v42, v41, v15) )
          {
            v18 = GetLastError();
            v19 = (int *)ConstructPartialMsgW(
                           0x400002Au,
                           "Could not locate saved '%s' in working directory",
                           (const char *)v42);
            WdsSetupLogMessageW(
              v19,
              589824,
              (__int64)L"D",
              0,
              0x62Bu,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"WdsExecuteWorkQueue",
              lpModuleName,
              v18,
              0,
              0);
            goto LABEL_39;
          }
          if ( !(unsigned int)SeqSerializeFromFile(lpMem, v41) )
          {
            v20 = GetLastError();
            v21 = (int *)ConstructPartialMsgW(
                           0x400002Bu,
                           "Could not load SEQ state from '%s'",
                           (const char *)&g_WorkingDir);
            WdsSetupLogMessageW(
              v21,
              589824,
              (__int64)L"D",
              0,
              0x631u,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"WdsExecuteWorkQueue",
              lpModuleName,
              v20,
              0,
              0);
            goto LABEL_39;
          }
        }
      }
      else
      {
        memset_0(v41, 0, 0x208u);
        if ( !(unsigned int)pLookupContentsFileEntry((const unsigned __int16 *)*a1, v41, v22) )
        {
          v23 = GetLastError();
          v24 = (int *)ConstructPartialMsgW(0x4000026u, "Could not locate saved '%s' in working directory", *a1);
          WdsSetupLogMessageW(
            v24,
            589824,
            (__int64)L"D",
            0,
            0x5F6u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue",
            lpModuleName,
            v23,
            0,
            0);
          goto LABEL_39;
        }
        if ( !(unsigned int)SeqSerializeFromFile(lpMem, v41) )
        {
          v25 = GetLastError();
          v26 = (int *)ConstructPartialMsgW(
                         0x4000027u,
                         "Could not load SEQ state from '%s'",
                         (const char *)&g_WorkingDir);
          WdsSetupLogMessageW(
            v26,
            589824,
            (__int64)L"D",
            0,
            0x5FCu,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue",
            lpModuleName,
            v25,
            0,
            0);
          goto LABEL_39;
        }
        for ( i = 0; i < v6; ++i )
        {
          if ( (int)SeqAddModule(
                      lpMem,
                      *(_QWORD *)(32LL * i + a3),
                      *(_QWORD *)(32LL * i + a3 + 8),
                      *(_QWORD *)(32LL * i + a3 + 16),
                      *(_QWORD *)(32LL * i + a3 + 24)) >= 3 )
          {
            v28 = GetLastError();
            v29 = (int *)ConstructPartialMsgW(0x2000028u, "Failed to initialize setup modules");
            WdsSetupLogMessageW(
              v29,
              589824,
              (__int64)L"D",
              0,
              0x60Cu,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"WdsExecuteWorkQueue",
              lpModuleName,
              v28,
              0,
              0);
            goto LABEL_39;
          }
        }
      }
    }
    else
    {
      if ( !v6 || !a3 || !*((_DWORD *)a1 + 4) )
      {
        v36 = GetLastError();
        v37 = (int *)ConstructPartialMsgW(
                       0x2000023u,
                       "WdsExecuteWorkQueue with WDS_START_EMPTY_QUEUE given 0 modules or 0 groups");
        WdsSetupLogMessageW(
          v37,
          589824,
          (__int64)L"D",
          0,
          0x5C1u,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"WdsExecuteWorkQueue",
          lpModuleName,
          v36,
          0,
          0);
        goto LABEL_39;
      }
      for ( j = 0; j < *((_DWORD *)a1 + 4); ++j )
      {
        if ( !(unsigned int)SeqAddPriorityGroup(lpMem, *(_QWORD *)&a1[1][8 * j]) )
        {
          v31 = GetLastError();
          v32 = (int *)ConstructPartialMsgW(0x2000024u, "Failed to initialize setup groups");
          WdsSetupLogMessageW(
            v32,
            589824,
            (__int64)L"D",
            0,
            0x5D1u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue",
            lpModuleName,
            v31,
            0,
            0);
          goto LABEL_39;
        }
      }
      for ( k = 0; k < a4; ++k )
      {
        if ( (int)SeqAddModule(
                    lpMem,
                    *(_QWORD *)(32LL * k + a3),
                    *(_QWORD *)(32LL * k + a3 + 8),
                    *(_QWORD *)(32LL * k + a3 + 16),
                    *(_QWORD *)(32LL * k + a3 + 24)) >= 3 )
        {
          v34 = GetLastError();
          v35 = (int *)ConstructPartialMsgW(0x2000025u, "Failed to initialize setup modules");
          WdsSetupLogMessageW(
            v35,
            589824,
            (__int64)L"D",
            0,
            0x5E3u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue",
            lpModuleName,
            v34,
            0,
            0);
          goto LABEL_39;
        }
      }
    }
    if ( (unsigned int)SeqExecute((char *)lpMem) != 3 )
    {
      v10 = 1;
      goto LABEL_40;
    }
    goto LABEL_39;
  }
LABEL_40:
  v38 = GetLastError();
  if ( v11 )
    pTerminateWorkQueue();
  SetLastError(v38);
  return v10;
}

```

## disassembly

```asm
0x18000c1a0  mov     [rsp+arg_8], rbx
0x18000c1a5  mov     [rsp+arg_18], rsi
0x18000c1aa  push    rdi
0x18000c1ab  push    r12
0x18000c1ad  push    r13
0x18000c1af  push    r14
0x18000c1b1  push    r15
0x18000c1b3  sub     rsp, 4A0h
0x18000c1ba  mov     rax, cs:__security_cookie
0x18000c1c1  xor     rax, rsp
0x18000c1c4  mov     [rsp+4C8h+var_38], rax
0x18000c1cc  mov     edi, r9d
0x18000c1cf  mov     [rsp+4C8h+var_460], r9d
0x18000c1d4  mov     r12, r8
0x18000c1d7  mov     esi, edx
0x18000c1d9  mov     r14, rcx
0x18000c1dc  mov     rdx, [rsp+4C8h+arg_20]; struct WDS_QUEUE_INFO *
0x18000c1e4  xor     r13d, r13d
0x18000c1e7  mov     [rsp+4C8h+var_468], r13d
0x18000c1ec  xor     r15d, r15d
0x18000c1ef  mov     [rsp+4C8h+var_45C], r15d
0x18000c1f4  test    rcx, rcx
0x18000c1f7  jz      loc_18000C7F1
0x18000c1fd  mov     r8d, [rsp+4C8h+arg_28]; unsigned int
0x18000c205  call    ?pInitializeWorkQueue@@YAHPEAUWDS_QUEUE_INFO@@0I@Z; pInitializeWorkQueue(WDS_QUEUE_INFO *,WDS_QUEUE_INFO *,uint)
0x18000c20a  test    eax, eax
0x18000c20c  jz      loc_18000C7F1
0x18000c212  lea     r15d, [r13+1]
0x18000c216  mov     [rsp+4C8h+var_45C], r15d
0x18000c21b  call    ?pCreateCleanTempDir@@YAHXZ; pCreateCleanTempDir(void)
0x18000c220  test    eax, eax
0x18000c222  jnz     short loc_18000C29E
0x18000c224  call    cs:__imp_GetLastError
0x18000c22b  nop     dword ptr [rax+rax+00h]
0x18000c230  mov     ebx, eax
0x18000c232  mov     rdi, [rsp+4C8h]
0x18000c23a  lea     rdx, aCouldnTCreateC; "Couldn't create clean panther temp dir"
0x18000c241  mov     ecx, 3000022h; unsigned int
0x18000c246  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c24b  mov     [rsp+4C8h+var_478], r13d; int
0x18000c250  mov     [rsp+4C8h+var_480], r13; __int64
0x18000c255  mov     [rsp+4C8h+var_488], ebx; int
0x18000c259  mov     [rsp+4C8h+lpModuleName], rdi; lpModuleName
0x18000c25e  lea     rbx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c265  mov     [rsp+4C8h+var_498], rbx; __int64
0x18000c26a  lea     rbx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c271  mov     [rsp+4C8h+var_4A0], rbx; unsigned __int16 *
0x18000c276  mov     [rsp+4C8h+var_4A8], 5B6h; int
0x18000c27e  xor     r9d, r9d; int
0x18000c281  lea     r13, aD_1; "D"
0x18000c288  mov     r8, r13; int
0x18000c28b  mov     edx, 90000h; int
0x18000c290  mov     rcx, rax; int
0x18000c293  call    WdsSetupLogMessageW
0x18000c298  mov     edi, [rsp+4C8h+var_460]
0x18000c29c  jmp     short loc_18000C2A5
0x18000c29e  lea     r13, aD_1; "D"
0x18000c2a5  test    esi, esi
0x18000c2a7  jz      loc_18000C611
0x18000c2ad  sub     esi, r15d
0x18000c2b0  jz      loc_18000C46E
0x18000c2b6  cmp     esi, r15d
0x18000c2b9  jnz     loc_18000C778
0x18000c2bf  mov     ebx, 208h
0x18000c2c4  mov     r8d, ebx; Size
0x18000c2c7  xor     edx, edx; Val
0x18000c2c9  lea     rcx, [rsp+4C8h+var_458]; void *
0x18000c2ce  call    memset_0
0x18000c2d3  mov     r8d, ebx; Size
0x18000c2d6  xor     edx, edx; Val
0x18000c2d8  lea     rcx, [rsp+4C8h+var_248]; void *
0x18000c2e0  call    memset_0
0x18000c2e5  lea     rax, aOnline; "Online"
0x18000c2ec  mov     qword ptr [rsp+4C8h+var_4A8], rax
0x18000c2f1  mov     r9, [r14]
0x18000c2f4  lea     r8, aSS; "%s%s"
0x18000c2fb  mov     edx, 104h; unsigned __int64
0x18000c300  lea     rcx, [rsp+4C8h+var_248]; unsigned __int16 *
0x18000c308  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c30d  xor     esi, esi
0x18000c30f  test    eax, eax
0x18000c311  jns     short loc_18000C374
0x18000c313  call    cs:__imp_GetLastError
0x18000c31a  nop     dword ptr [rax+rax+00h]
0x18000c31f  mov     ebx, eax
0x18000c321  mov     rdi, [rsp+4C8h]
0x18000c329  mov     r8, [r14]
0x18000c32c  lea     rdx, aStringcchprint; "stringcchprintf failed for '%s'"
0x18000c333  mov     ecx, 2000029h; unsigned int
0x18000c338  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c33d  mov     [rsp+4C8h+var_478], esi
0x18000c341  mov     [rsp+4C8h+var_480], rsi
0x18000c346  mov     [rsp+4C8h+var_488], ebx
0x18000c34a  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c34f  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c356  mov     [rsp+4C8h+var_498], rcx
0x18000c35b  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c362  mov     [rsp+4C8h+var_4A0], rcx
0x18000c367  mov     [rsp+4C8h+var_4A8], 623h
0x18000c36f  jmp     loc_18000C6B1
0x18000c374  lea     rdx, [rsp+4C8h+var_458]; unsigned __int16 *
0x18000c379  lea     rcx, [rsp+4C8h+var_248]; unsigned __int16 *
0x18000c381  call    ?pLookupContentsFileEntry@@YAHPEBGPEAGI@Z; pLookupContentsFileEntry(ushort const *,ushort *,uint)
0x18000c386  test    eax, eax
0x18000c388  jnz     short loc_18000C3F0
0x18000c38a  call    cs:__imp_GetLastError
0x18000c391  nop     dword ptr [rax+rax+00h]
0x18000c396  mov     ebx, eax
0x18000c398  mov     rdi, [rsp+4C8h]
0x18000c3a0  lea     r8, [rsp+4C8h+var_248]
0x18000c3a8  lea     rdx, aCouldNotLocate; "Could not locate saved '%s' in working "...
0x18000c3af  mov     ecx, 400002Ah; unsigned int
0x18000c3b4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c3b9  mov     [rsp+4C8h+var_478], esi
0x18000c3bd  mov     [rsp+4C8h+var_480], rsi
0x18000c3c2  mov     [rsp+4C8h+var_488], ebx
0x18000c3c6  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c3cb  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c3d2  mov     [rsp+4C8h+var_498], rcx
0x18000c3d7  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c3de  mov     [rsp+4C8h+var_4A0], rcx
0x18000c3e3  mov     [rsp+4C8h+var_4A8], 62Bh
0x18000c3eb  jmp     loc_18000C6B1
0x18000c3f0  lea     rdx, [rsp+4C8h+var_458]
0x18000c3f5  mov     rcx, cs:lpMem
0x18000c3fc  call    SeqSerializeFromFile
0x18000c401  test    eax, eax
0x18000c403  jnz     loc_18000C778
0x18000c409  call    cs:__imp_GetLastError
0x18000c410  nop     dword ptr [rax+rax+00h]
0x18000c415  mov     ebx, eax
0x18000c417  mov     rdi, [rsp+4C8h]
0x18000c41f  lea     r8, ?g_WorkingDir@@3PAGA; ushort near * g_WorkingDir
0x18000c426  lea     rdx, aCouldNotLoadSe; "Could not load SEQ state from '%s'"
0x18000c42d  mov     ecx, 400002Bh; unsigned int
0x18000c432  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c437  mov     [rsp+4C8h+var_478], esi
0x18000c43b  mov     [rsp+4C8h+var_480], rsi
0x18000c440  mov     [rsp+4C8h+var_488], ebx
0x18000c444  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c449  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c450  mov     [rsp+4C8h+var_498], rcx
0x18000c455  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c45c  mov     [rsp+4C8h+var_4A0], rcx
0x18000c461  mov     [rsp+4C8h+var_4A8], 631h
0x18000c469  jmp     loc_18000C6B1
0x18000c46e  xor     edx, edx; Val
0x18000c470  mov     r8d, 208h; Size
0x18000c476  lea     rcx, [rsp+4C8h+var_458]; void *
0x18000c47b  call    memset_0
0x18000c480  lea     rdx, [rsp+4C8h+var_458]; unsigned __int16 *
0x18000c485  mov     rcx, [r14]; unsigned __int16 *
0x18000c488  call    ?pLookupContentsFileEntry@@YAHPEBGPEAGI@Z; pLookupContentsFileEntry(ushort const *,ushort *,uint)
0x18000c48d  xor     esi, esi
0x18000c48f  test    eax, eax
0x18000c491  jnz     short loc_18000C4F4
0x18000c493  call    cs:__imp_GetLastError
0x18000c49a  nop     dword ptr [rax+rax+00h]
0x18000c49f  mov     ebx, eax
0x18000c4a1  mov     rdi, [rsp+4C8h]
0x18000c4a9  mov     r8, [r14]
0x18000c4ac  lea     rdx, aCouldNotLocate; "Could not locate saved '%s' in working "...
0x18000c4b3  mov     ecx, 4000026h; unsigned int
0x18000c4b8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c4bd  mov     [rsp+4C8h+var_478], esi
0x18000c4c1  mov     [rsp+4C8h+var_480], rsi
0x18000c4c6  mov     [rsp+4C8h+var_488], ebx
0x18000c4ca  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c4cf  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c4d6  mov     [rsp+4C8h+var_498], rcx
0x18000c4db  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c4e2  mov     [rsp+4C8h+var_4A0], rcx
0x18000c4e7  mov     [rsp+4C8h+var_4A8], 5F6h
0x18000c4ef  jmp     loc_18000C6B1
0x18000c4f4  lea     rdx, [rsp+4C8h+var_458]
0x18000c4f9  mov     rcx, cs:lpMem
0x18000c500  call    SeqSerializeFromFile
0x18000c505  test    eax, eax
0x18000c507  jnz     short loc_18000C56E
0x18000c509  call    cs:__imp_GetLastError
0x18000c510  nop     dword ptr [rax+rax+00h]
0x18000c515  mov     ebx, eax
0x18000c517  mov     rdi, [rsp+4C8h]
0x18000c51f  lea     r8, ?g_WorkingDir@@3PAGA; ushort near * g_WorkingDir
0x18000c526  lea     rdx, aCouldNotLoadSe; "Could not load SEQ state from '%s'"
0x18000c52d  mov     ecx, 4000027h; unsigned int
0x18000c532  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c537  mov     [rsp+4C8h+var_478], esi
0x18000c53b  mov     [rsp+4C8h+var_480], rsi
0x18000c540  mov     [rsp+4C8h+var_488], ebx
0x18000c544  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c549  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c550  mov     [rsp+4C8h+var_498], rcx
0x18000c555  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c55c  mov     [rsp+4C8h+var_4A0], rcx
0x18000c561  mov     [rsp+4C8h+var_4A8], 5FCh
0x18000c569  jmp     loc_18000C6B1
0x18000c56e  mov     ebx, esi
0x18000c570  mov     [rsp+4C8h+var_464], ebx
0x18000c574  cmp     ebx, edi
0x18000c576  jnb     loc_18000C778
0x18000c57c  mov     edx, ebx
0x18000c57e  shl     rdx, 5
0x18000c582  mov     rax, [rdx+r12+18h]
0x18000c587  mov     qword ptr [rsp+4C8h+var_4A8], rax
0x18000c58c  mov     r9, [rdx+r12+10h]
0x18000c591  mov     r8, [rdx+r12+8]
0x18000c596  mov     rdx, [rdx+r12]
0x18000c59a  mov     rcx, cs:lpMem
0x18000c5a1  call    SeqAddModule
0x18000c5a6  cmp     eax, 3
0x18000c5a9  jl      short loc_18000C609
0x18000c5ab  call    cs:__imp_GetLastError
0x18000c5b2  nop     dword ptr [rax+rax+00h]
0x18000c5b7  mov     ebx, eax
0x18000c5b9  mov     rdi, [rsp+4C8h]
0x18000c5c1  lea     rdx, aFailedToInitia_0; "Failed to initialize setup modules"
0x18000c5c8  mov     ecx, 2000028h; unsigned int
0x18000c5cd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c5d2  mov     [rsp+4C8h+var_478], esi
0x18000c5d6  mov     [rsp+4C8h+var_480], rsi
0x18000c5db  mov     [rsp+4C8h+var_488], ebx
0x18000c5df  mov     [rsp+4C8h+lpModuleName], rdi
0x18000c5e4  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c5eb  mov     [rsp+4C8h+var_498], rcx
0x18000c5f0  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c5f7  mov     [rsp+4C8h+var_4A0], rcx
0x18000c5fc  mov     [rsp+4C8h+var_4A8], 60Ch
0x18000c604  jmp     loc_18000C6B1
0x18000c609  add     ebx, r15d
0x18000c60c  jmp     loc_18000C570
0x18000c611  xor     esi, esi
0x18000c613  test    edi, edi
0x18000c615  jz      loc_18000C78E
0x18000c61b  test    r12, r12
0x18000c61e  jz      loc_18000C78E
0x18000c624  cmp     [r14+10h], esi
0x18000c628  jz      loc_18000C78E
0x18000c62e  mov     ebx, esi
0x18000c630  mov     [rsp+4C8h+var_464], ebx
0x18000c634  cmp     ebx, [r14+10h]
0x18000c638  jnb     loc_18000C6D1
0x18000c63e  mov     eax, ebx
0x18000c640  mov     rdx, [r14+8]
0x18000c644  mov     rdx, [rdx+rax*8]
0x18000c648  mov     rcx, cs:lpMem
0x18000c64f  call    SeqAddPriorityGroup
0x18000c654  test    eax, eax
0x18000c656  jnz     short loc_18000C6C9
0x18000c658  call    cs:__imp_GetLastError
0x18000c65f  nop     dword ptr [rax+rax+00h]
0x18000c664  mov     ebx, eax
0x18000c666  mov     rdi, [rsp+4C8h]
0x18000c66e  lea     rdx, aFailedToInitia_1; "Failed to initialize setup groups"
0x18000c675  mov     ecx, 2000024h; unsigned int
0x18000c67a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c67f  mov     [rsp+4C8h+var_478], esi; int
0x18000c683  mov     [rsp+4C8h+var_480], rsi; __int64
0x18000c688  mov     [rsp+4C8h+var_488], ebx; int
0x18000c68c  mov     [rsp+4C8h+lpModuleName], rdi; lpModuleName
0x18000c691  lea     rcx, aWdsexecutework_2; "WdsExecuteWorkQueue"
0x18000c698  mov     [rsp+4C8h+var_498], rcx; __int64
0x18000c69d  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c6a4  mov     [rsp+4C8h+var_4A0], rcx; unsigned __int16 *
0x18000c6a9  mov     [rsp+4C8h+var_4A8], 5D1h; int
0x18000c6b1  xor     r9d, r9d; int
0x18000c6b4  mov     r8, r13; int
0x18000c6b7  mov     edx, 90000h; int
0x18000c6bc  mov     rcx, rax; int
0x18000c6bf  call    WdsSetupLogMessageW
0x18000c6c4  jmp     loc_18000C7EC
0x18000c6c9  add     ebx, r15d
0x18000c6cc  jmp     loc_18000C630
0x18000c6d1  mov     ebx, esi
0x18000c6d3  mov     edi, [rsp+4C8h+var_460]
0x18000c6d7  mov     [rsp+4C8h+var_464], ebx
0x18000c6db  cmp     ebx, edi
0x18000c6dd  jnb     loc_18000C778
0x18000c6e3  mov     edx, ebx
0x18000c6e5  shl     rdx, 5
0x18000c6e9  mov     rax, [rdx+r12+18h]
0x18000c6ee  mov     qword ptr [rsp+4C8h+var_4A8], rax
0x18000c6f3  mov     r9, [rdx+r12+10h]
0x18000c6f8  mov     r8, [rdx+r12+8]
0x18000c6fd  mov     rdx, [rdx+r12]
0x18000c701  mov     rcx, cs:lpMem
0x18000c708  call    SeqAddModule
0x18000c70d  cmp     eax, 3
0x18000c710  jl      short loc_18000C770
0x18000c712  call    cs:__imp_GetLastError
0x18000c719  nop     dword ptr [rax+rax+00h]
0x18000c71e  mov     ebx, eax
0x18000c720  mov     rdi, [rsp+4C8h]
0x18000c728  lea     rdx, aFailedToInitia_0; "Failed to initialize setup modules"
0x18000c72f  mov     ecx, 2000025h; unsigned int
0x18000c734  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c739  mov     [rsp+4C8h+var_478], esi
0x18000c73d  mov     [rsp+4C8h+var_480], rsi
0x18000c742  mov     [rsp+4C8h+var_488], ebx
0x18000c746  mov     [rsp+4C8h+lpModuleName], rdi
  ... truncated ...
```
