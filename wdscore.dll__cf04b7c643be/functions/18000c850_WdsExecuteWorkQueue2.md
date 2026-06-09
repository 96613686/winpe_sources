# WdsExecuteWorkQueue2

- ea: `0x18000c850`
- end: `0x18000cfaa`
- name: `WdsExecuteWorkQueue2`
- size: `1882`
- prototype: `__int64 __fastcall(int, int, int, int, struct WDS_QUEUE_INFO *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x180002250`
- `0x180002774`
- `0x180002878`
- `0x180003108`
- `0x180003958`
- `0x180004830`
- `0x180005d54`
- `0x180005e18`
- `0x18000a8f0`
- `0x18000ad30`
- `0x18000b3fc`
- `0x18000c850`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002856f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000caa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002854d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000caa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002854d`

## string_xrefs

- `0x18000c9b3`: `Could not locate saved '%s' in working directory`
- `0x18000cb4a`: `Could not locate saved '%s' in working directory`

## pseudocode

```c
__int64 __fastcall WdsExecuteWorkQueue2(
        const char **a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        struct WDS_QUEUE_INFO *a5,
        unsigned int a6)
{
  unsigned int v10; // r12d
  int v11; // esi
  int v12; // ebx
  unsigned int v13; // r8d
  DWORD LastError; // ebx
  int *v15; // rax
  DWORD v16; // ebx
  int *v17; // rax
  unsigned int i; // ebx
  DWORD v19; // ebx
  int *v20; // rax
  DWORD v21; // ebx
  int *v22; // rax
  unsigned int v23; // r8d
  DWORD v24; // ebx
  int *v25; // rax
  DWORD v26; // ebx
  int *v27; // rax
  unsigned int j; // ebx
  DWORD v29; // ebx
  int *v30; // rax
  DWORD v31; // ebx
  int *v32; // rax
  unsigned int k; // ebx
  DWORD v34; // ebx
  int *v35; // rax
  unsigned int m; // ebx
  DWORD v37; // ebx
  int *v38; // rax
  DWORD v39; // ebx
  int *v40; // rax
  DWORD v41; // ebx
  int *v42; // rax
  DWORD v43; // ebx
  unsigned __int16 v45[264]; // [rsp+70h] [rbp-468h] BYREF
  unsigned __int16 v46[264]; // [rsp+280h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+4D8h] [rbp+0h]

  v10 = 0;
  v11 = 0;
  if ( !(unsigned int)pInitializeWorkQueue((struct WDS_QUEUE_INFO *)a1, a5, a6) )
    goto LABEL_46;
  v11 = 1;
  if ( a2 )
  {
    v12 = a2 - 1;
    if ( v12 )
    {
      if ( v12 == 1 )
      {
        memset_0(v45, 0, 0x208u);
        memset_0(v46, 0, 0x208u);
        if ( (int)StringCchPrintfW(v46, 0x104u, L"%s%s", *a1, L"Online") < 0 )
        {
          LastError = GetLastError();
          v15 = (int *)ConstructPartialMsgW(0x2000030u, "stringcchprintf failed for '%s'", *a1);
          WdsSetupLogMessageW(
            v15,
            589824,
            (__int64)L"D",
            0,
            0x6BFu,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue2",
            lpModuleName,
            LastError,
            0,
            0);
          goto LABEL_46;
        }
        if ( !(unsigned int)pLookupContentsFileEntry(v46, v45, v13) )
        {
          v16 = GetLastError();
          v17 = (int *)ConstructPartialMsgW(
                         0x4000031u,
                         "Could not locate saved '%s' in working directory",
                         (const char *)v46);
          WdsSetupLogMessageW(
            v17,
            589824,
            (__int64)L"D",
            0,
            0x6C7u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue2",
            lpModuleName,
            v16,
            0,
            0);
          goto LABEL_46;
        }
        for ( i = 0; i < a4; ++i )
        {
          if ( !(unsigned int)SeqAddLoadedModule(
                                lpMem,
                                *(_QWORD *)(a3 + 24LL * i),
                                *(_QWORD *)(a3 + 24LL * i + 8),
                                *(_QWORD *)(a3 + 24LL * i + 16)) )
          {
            v19 = GetLastError();
            v20 = (int *)ConstructPartialMsgW(0x2000032u, "Failed to add all setup modules");
            WdsSetupLogMessageW(
              v20,
              589824,
              (__int64)L"D",
              0,
              0x6D8u,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"WdsExecuteWorkQueue2",
              lpModuleName,
              v19,
              0,
              0);
            goto LABEL_46;
          }
        }
        if ( !(unsigned int)SeqSerializeFromFile(lpMem, v45) )
        {
          v21 = GetLastError();
          v22 = (int *)ConstructPartialMsgW(
                         0x4000033u,
                         "Could not load SEQ state from '%s'",
                         (const char *)&g_WorkingDir);
          WdsSetupLogMessageW(
            v22,
            589824,
            (__int64)L"D",
            0,
            0x6DFu,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"WdsExecuteWorkQueue2",
            lpModuleName,
            v21,
            0,
            0);
          goto LABEL_46;
        }
      }
      goto LABEL_43;
    }
    memset_0(v45, 0, 0x208u);
    if ( !(unsigned int)pLookupContentsFileEntry((const unsigned __int16 *)*a1, v45, v23) )
    {
      v24 = GetLastError();
      v25 = (int *)ConstructPartialMsgW(0x400002Cu, "Could not locate saved '%s' in working directory", *a1);
      WdsSetupLogMessageW(
        v25,
        589824,
        (__int64)L"D",
        0,
        0x681u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue2",
        lpModuleName,
        v24,
        0,
        0);
      goto LABEL_46;
    }
    if ( !(unsigned int)SeqSerializeFromFile(lpMem, v45) )
    {
      v26 = GetLastError();
      v27 = (int *)ConstructPartialMsgW(0x400002Du, "Could not load SEQ state from '%s'", (const char *)&g_WorkingDir);
      WdsSetupLogMessageW(
        v27,
        589824,
        (__int64)L"D",
        0,
        0x687u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue2",
        lpModuleName,
        v26,
        0,
        0);
      goto LABEL_46;
    }
    for ( j = 0; j < a4; ++j )
    {
      if ( !(unsigned int)SeqAddLoadedModule(
                            lpMem,
                            *(_QWORD *)(a3 + 24LL * j),
                            *(_QWORD *)(a3 + 24LL * j + 8),
                            *(_QWORD *)(a3 + 24LL * j + 16)) )
      {
        v29 = GetLastError();
        v30 = (int *)ConstructPartialMsgW(0x200002Eu, "Failed to add all setup modules");
        WdsSetupLogMessageW(
          v30,
          589824,
          (__int64)L"D",
          0,
          0x696u,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"WdsExecuteWorkQueue2",
          lpModuleName,
          v29,
          0,
          0);
        goto LABEL_46;
      }
    }
    if ( !(unsigned int)SeqInitModules(lpMem, 1, a4) )
    {
      v31 = GetLastError();
      v32 = (int *)ConstructPartialMsgW(0x200002Fu, "Failed to initialize setup modules");
      WdsSetupLogMessageW(
        v32,
        589824,
        (__int64)L"D",
        0,
        0x6A2u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue2",
        lpModuleName,
        v31,
        0,
        0);
      goto LABEL_46;
    }
  }
  else
  {
    if ( !a4 || !a3 || !*((_DWORD *)a1 + 4) )
    {
      v41 = GetLastError();
      v42 = (int *)ConstructPartialMsgW(
                     0x2000034u,
                     "WdsExecuteWorkQueue2 with WDS_START_EMPTY_QUEUE given 0 modules or 0 groups");
      WdsSetupLogMessageW(
        v42,
        589824,
        (__int64)L"D",
        0,
        0x6EBu,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue2",
        lpModuleName,
        v41,
        0,
        0);
      goto LABEL_46;
    }
    for ( k = 0; k < *((_DWORD *)a1 + 4); ++k )
    {
      if ( !(unsigned int)SeqAddPriorityGroup(lpMem, *(_QWORD *)&a1[1][8 * k]) )
      {
        v34 = GetLastError();
        v35 = (int *)ConstructPartialMsgW(0x2000035u, "Failed to initialize setup groups");
        WdsSetupLogMessageW(
          v35,
          589824,
          (__int64)L"D",
          0,
          0x6FBu,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"WdsExecuteWorkQueue2",
          lpModuleName,
          v34,
          0,
          0);
        goto LABEL_46;
      }
    }
    for ( m = 0; m < a4; ++m )
    {
      if ( !(unsigned int)SeqAddLoadedModule(
                            lpMem,
                            *(_QWORD *)(a3 + 24LL * m),
                            *(_QWORD *)(a3 + 24LL * m + 8),
                            *(_QWORD *)(a3 + 24LL * m + 16)) )
      {
        v37 = GetLastError();
        v38 = (int *)ConstructPartialMsgW(0x2000036u, "Failed to add all setup modules");
        WdsSetupLogMessageW(
          v38,
          589824,
          (__int64)L"D",
          0,
          0x70Bu,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"WdsExecuteWorkQueue2",
          lpModuleName,
          v37,
          0,
          0);
        goto LABEL_46;
      }
    }
    if ( !(unsigned int)SeqInitModules(lpMem, 1, a4) )
    {
      v39 = GetLastError();
      v40 = (int *)ConstructPartialMsgW(0x2000037u, "Failed to initialize setup modules");
      WdsSetupLogMessageW(
        v40,
        589824,
        (__int64)L"D",
        0,
        0x717u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"WdsExecuteWorkQueue2",
        lpModuleName,
        v39,
        0,
        0);
      goto LABEL_46;
    }
  }
  SeqValidateModules(lpMem);
LABEL_43:
  if ( (unsigned int)SeqExecute((char *)lpMem) != 3 )
    v10 = 1;
LABEL_46:
  v43 = GetLastError();
  if ( v11 )
    pTerminateWorkQueue();
  SetLastError(v43);
  return v10;
}

```

## disassembly

```asm
0x18000c850  push    rbx
0x18000c852  push    rsi
0x18000c853  push    rdi
0x18000c854  push    r12
0x18000c856  push    r13
0x18000c858  push    r14
0x18000c85a  push    r15
0x18000c85c  sub     rsp, 4A0h
0x18000c863  mov     rax, cs:__security_cookie
0x18000c86a  xor     rax, rsp
0x18000c86d  mov     [rsp+4D8h+var_48], rax
0x18000c875  mov     r15d, r9d
0x18000c878  mov     rdi, r8
0x18000c87b  mov     ebx, edx
0x18000c87d  mov     r14, rcx
0x18000c880  mov     rdx, [rsp+4D8h+arg_20]; struct WDS_QUEUE_INFO *
0x18000c888  xor     r13d, r13d
0x18000c88b  mov     r12d, r13d
0x18000c88e  mov     esi, r13d
0x18000c891  mov     [rsp+4D8h+var_474], r13d
0x18000c896  mov     r8d, [rsp+4D8h+arg_28]; unsigned int
0x18000c89e  call    ?pInitializeWorkQueue@@YAHPEAUWDS_QUEUE_INFO@@0I@Z; pInitializeWorkQueue(WDS_QUEUE_INFO *,WDS_QUEUE_INFO *,uint)
0x18000c8a3  test    eax, eax
0x18000c8a5  jz      loc_18000CF5E
0x18000c8ab  lea     esi, [r13+1]
0x18000c8af  mov     [rsp+4D8h+var_474], esi
0x18000c8b3  test    ebx, ebx
0x18000c8b5  jz      loc_18000CD19
0x18000c8bb  sub     ebx, esi
0x18000c8bd  jz      loc_18000CB0E
0x18000c8c3  cmp     ebx, esi
0x18000c8c5  jnz     loc_18000CED6
0x18000c8cb  mov     ebx, 208h
0x18000c8d0  mov     r8d, ebx; Size
0x18000c8d3  xor     edx, edx; Val
0x18000c8d5  lea     rcx, [rsp+4D8h+var_468]; void *
0x18000c8da  call    memset_0
0x18000c8df  mov     r8d, ebx; Size
0x18000c8e2  xor     edx, edx; Val
0x18000c8e4  lea     rcx, [rsp+4D8h+var_258]; void *
0x18000c8ec  call    memset_0
0x18000c8f1  lea     rax, aOnline; "Online"
0x18000c8f8  mov     qword ptr [rsp+4D8h+var_4B8], rax
0x18000c8fd  mov     r9, [r14]
0x18000c900  lea     r8, aSS; "%s%s"
0x18000c907  mov     edx, 104h; unsigned __int64
0x18000c90c  lea     rcx, [rsp+4D8h+var_258]; unsigned __int16 *
0x18000c914  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c919  test    eax, eax
0x18000c91b  jns     short loc_18000C97F
0x18000c91d  call    cs:__imp_GetLastError
0x18000c924  nop     dword ptr [rax+rax+00h]
0x18000c929  mov     ebx, eax
0x18000c92b  mov     rdi, [rsp+4D8h]
0x18000c933  mov     r8, [r14]
0x18000c936  lea     rdx, aStringcchprint; "stringcchprintf failed for '%s'"
0x18000c93d  mov     ecx, 2000030h; unsigned int
0x18000c942  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c947  mov     [rsp+4D8h+var_488], r13d
0x18000c94c  mov     [rsp+4D8h+var_490], r13
0x18000c951  mov     [rsp+4D8h+var_498], ebx
0x18000c955  mov     [rsp+4D8h+lpModuleName], rdi
0x18000c95a  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000c961  mov     [rsp+4D8h+var_4A8], rcx
0x18000c966  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c96d  mov     [rsp+4D8h+var_4B0], rcx
0x18000c972  mov     [rsp+4D8h+var_4B8], 6BFh
0x18000c97a  jmp     loc_18000CF46
0x18000c97f  lea     rdx, [rsp+4D8h+var_468]; unsigned __int16 *
0x18000c984  lea     rcx, [rsp+4D8h+var_258]; unsigned __int16 *
0x18000c98c  call    ?pLookupContentsFileEntry@@YAHPEBGPEAGI@Z; pLookupContentsFileEntry(ushort const *,ushort *,uint)
0x18000c991  test    eax, eax
0x18000c993  jnz     short loc_18000C9FC
0x18000c995  call    cs:__imp_GetLastError
0x18000c99c  nop     dword ptr [rax+rax+00h]
0x18000c9a1  mov     ebx, eax
0x18000c9a3  mov     rdi, [rsp+4D8h]
0x18000c9ab  lea     r8, [rsp+4D8h+var_258]
0x18000c9b3  lea     rdx, aCouldNotLocate; "Could not locate saved '%s' in working "...
0x18000c9ba  mov     ecx, 4000031h; unsigned int
0x18000c9bf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000c9c4  mov     [rsp+4D8h+var_488], r13d
0x18000c9c9  mov     [rsp+4D8h+var_490], r13
0x18000c9ce  mov     [rsp+4D8h+var_498], ebx
0x18000c9d2  mov     [rsp+4D8h+lpModuleName], rdi
0x18000c9d7  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000c9de  mov     [rsp+4D8h+var_4A8], rcx
0x18000c9e3  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000c9ea  mov     [rsp+4D8h+var_4B0], rcx
0x18000c9ef  mov     [rsp+4D8h+var_4B8], 6C7h
0x18000c9f7  jmp     loc_18000CF46
0x18000c9fc  mov     ebx, r13d
0x18000c9ff  mov     [rsp+4D8h+var_478], ebx
0x18000ca03  mov     rcx, cs:lpMem
0x18000ca0a  cmp     ebx, r15d
0x18000ca0d  jnb     loc_18000CA96
0x18000ca13  mov     eax, ebx
0x18000ca15  lea     rdx, [rax+rax*2]
0x18000ca19  mov     r9, [rdi+rdx*8+10h]
0x18000ca1e  mov     r8, [rdi+rdx*8+8]
0x18000ca23  mov     rdx, [rdi+rdx*8]
0x18000ca27  call    SeqAddLoadedModule
0x18000ca2c  test    eax, eax
0x18000ca2e  jnz     short loc_18000CA8F
0x18000ca30  call    cs:__imp_GetLastError
0x18000ca37  nop     dword ptr [rax+rax+00h]
0x18000ca3c  mov     ebx, eax
0x18000ca3e  mov     rdi, [rsp+4D8h]
0x18000ca46  lea     rdx, aFailedToAddAll; "Failed to add all setup modules"
0x18000ca4d  mov     ecx, 2000032h; unsigned int
0x18000ca52  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ca57  mov     [rsp+4D8h+var_488], r13d
0x18000ca5c  mov     [rsp+4D8h+var_490], r13
0x18000ca61  mov     [rsp+4D8h+var_498], ebx
0x18000ca65  mov     [rsp+4D8h+lpModuleName], rdi
0x18000ca6a  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000ca71  mov     [rsp+4D8h+var_4A8], rcx
0x18000ca76  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000ca7d  mov     [rsp+4D8h+var_4B0], rcx
0x18000ca82  mov     [rsp+4D8h+var_4B8], 6D8h
0x18000ca8a  jmp     loc_18000CF46
0x18000ca8f  add     ebx, esi
0x18000ca91  jmp     loc_18000C9FF
0x18000ca96  lea     rdx, [rsp+4D8h+var_468]
0x18000ca9b  call    SeqSerializeFromFile
0x18000caa0  test    eax, eax
0x18000caa2  jnz     loc_18000CED6
0x18000caa8  call    cs:__imp_GetLastError
0x18000caaf  nop     dword ptr [rax+rax+00h]
0x18000cab4  mov     ebx, eax
0x18000cab6  mov     rdi, [rsp+4D8h]
0x18000cabe  lea     r8, ?g_WorkingDir@@3PAGA; ushort near * g_WorkingDir
0x18000cac5  lea     rdx, aCouldNotLoadSe; "Could not load SEQ state from '%s'"
0x18000cacc  mov     ecx, 4000033h; unsigned int
0x18000cad1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cad6  mov     [rsp+4D8h+var_488], r13d
0x18000cadb  mov     [rsp+4D8h+var_490], r13
0x18000cae0  mov     [rsp+4D8h+var_498], ebx
0x18000cae4  mov     [rsp+4D8h+lpModuleName], rdi
0x18000cae9  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000caf0  mov     [rsp+4D8h+var_4A8], rcx
0x18000caf5  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cafc  mov     [rsp+4D8h+var_4B0], rcx
0x18000cb01  mov     [rsp+4D8h+var_4B8], 6DFh
0x18000cb09  jmp     loc_18000CF46
0x18000cb0e  xor     edx, edx; Val
0x18000cb10  mov     r8d, 208h; Size
0x18000cb16  lea     rcx, [rsp+4D8h+var_468]; void *
0x18000cb1b  call    memset_0
0x18000cb20  lea     rdx, [rsp+4D8h+var_468]; unsigned __int16 *
0x18000cb25  mov     rcx, [r14]; unsigned __int16 *
0x18000cb28  call    ?pLookupContentsFileEntry@@YAHPEBGPEAGI@Z; pLookupContentsFileEntry(ushort const *,ushort *,uint)
0x18000cb2d  test    eax, eax
0x18000cb2f  jnz     short loc_18000CB93
0x18000cb31  call    cs:__imp_GetLastError
0x18000cb38  nop     dword ptr [rax+rax+00h]
0x18000cb3d  mov     ebx, eax
0x18000cb3f  mov     rdi, [rsp+4D8h]
0x18000cb47  mov     r8, [r14]
0x18000cb4a  lea     rdx, aCouldNotLocate; "Could not locate saved '%s' in working "...
0x18000cb51  mov     ecx, 400002Ch; unsigned int
0x18000cb56  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cb5b  mov     [rsp+4D8h+var_488], r13d
0x18000cb60  mov     [rsp+4D8h+var_490], r13
0x18000cb65  mov     [rsp+4D8h+var_498], ebx
0x18000cb69  mov     [rsp+4D8h+lpModuleName], rdi
0x18000cb6e  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000cb75  mov     [rsp+4D8h+var_4A8], rcx
0x18000cb7a  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cb81  mov     [rsp+4D8h+var_4B0], rcx
0x18000cb86  mov     [rsp+4D8h+var_4B8], 681h
0x18000cb8e  jmp     loc_18000CF46
0x18000cb93  lea     rdx, [rsp+4D8h+var_468]
0x18000cb98  mov     rcx, cs:lpMem
0x18000cb9f  call    SeqSerializeFromFile
0x18000cba4  test    eax, eax
0x18000cba6  jnz     short loc_18000CC0E
0x18000cba8  call    cs:__imp_GetLastError
0x18000cbaf  nop     dword ptr [rax+rax+00h]
0x18000cbb4  mov     ebx, eax
0x18000cbb6  mov     rdi, [rsp+4D8h]
0x18000cbbe  lea     r8, ?g_WorkingDir@@3PAGA; ushort near * g_WorkingDir
0x18000cbc5  lea     rdx, aCouldNotLoadSe; "Could not load SEQ state from '%s'"
0x18000cbcc  mov     ecx, 400002Dh; unsigned int
0x18000cbd1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cbd6  mov     [rsp+4D8h+var_488], r13d
0x18000cbdb  mov     [rsp+4D8h+var_490], r13
0x18000cbe0  mov     [rsp+4D8h+var_498], ebx
0x18000cbe4  mov     [rsp+4D8h+lpModuleName], rdi
0x18000cbe9  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000cbf0  mov     [rsp+4D8h+var_4A8], rcx
0x18000cbf5  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cbfc  mov     [rsp+4D8h+var_4B0], rcx
0x18000cc01  mov     [rsp+4D8h+var_4B8], 687h
0x18000cc09  jmp     loc_18000CF46
0x18000cc0e  mov     ebx, r13d
0x18000cc11  mov     [rsp+4D8h+var_478], ebx
0x18000cc15  mov     rcx, cs:lpMem
0x18000cc1c  cmp     ebx, r15d
0x18000cc1f  jnb     loc_18000CCA8
0x18000cc25  mov     eax, ebx
0x18000cc27  lea     rdx, [rax+rax*2]
0x18000cc2b  mov     r9, [rdi+rdx*8+10h]
0x18000cc30  mov     r8, [rdi+rdx*8+8]
0x18000cc35  mov     rdx, [rdi+rdx*8]
0x18000cc39  call    SeqAddLoadedModule
0x18000cc3e  test    eax, eax
0x18000cc40  jnz     short loc_18000CCA1
0x18000cc42  call    cs:__imp_GetLastError
0x18000cc49  nop     dword ptr [rax+rax+00h]
0x18000cc4e  mov     ebx, eax
0x18000cc50  mov     rdi, [rsp+4D8h]
0x18000cc58  lea     rdx, aFailedToAddAll; "Failed to add all setup modules"
0x18000cc5f  mov     ecx, 200002Eh; unsigned int
0x18000cc64  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cc69  mov     [rsp+4D8h+var_488], r13d
0x18000cc6e  mov     [rsp+4D8h+var_490], r13
0x18000cc73  mov     [rsp+4D8h+var_498], ebx
0x18000cc77  mov     [rsp+4D8h+lpModuleName], rdi
0x18000cc7c  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000cc83  mov     [rsp+4D8h+var_4A8], rcx
0x18000cc88  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cc8f  mov     [rsp+4D8h+var_4B0], rcx
0x18000cc94  mov     [rsp+4D8h+var_4B8], 696h
0x18000cc9c  jmp     loc_18000CF46
0x18000cca1  add     ebx, esi
0x18000cca3  jmp     loc_18000CC11
0x18000cca8  mov     r8d, r15d
0x18000ccab  mov     edx, esi
0x18000ccad  call    SeqInitModules
0x18000ccb2  test    eax, eax
0x18000ccb4  jnz     loc_18000CECA
0x18000ccba  call    cs:__imp_GetLastError
0x18000ccc1  nop     dword ptr [rax+rax+00h]
0x18000ccc6  mov     ebx, eax
0x18000ccc8  mov     rdi, [rsp+4D8h]
0x18000ccd0  lea     rdx, aFailedToInitia_0; "Failed to initialize setup modules"
0x18000ccd7  mov     ecx, 200002Fh; unsigned int
0x18000ccdc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cce1  mov     [rsp+4D8h+var_488], r13d
0x18000cce6  mov     [rsp+4D8h+var_490], r13
0x18000cceb  mov     [rsp+4D8h+var_498], ebx
0x18000ccef  mov     [rsp+4D8h+lpModuleName], rdi
0x18000ccf4  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000ccfb  mov     [rsp+4D8h+var_4A8], rcx
0x18000cd00  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cd07  mov     [rsp+4D8h+var_4B0], rcx
0x18000cd0c  mov     [rsp+4D8h+var_4B8], 6A2h
0x18000cd14  jmp     loc_18000CF46
0x18000cd19  test    r15d, r15d
0x18000cd1c  jz      loc_18000CEEC
0x18000cd22  test    rdi, rdi
0x18000cd25  jz      loc_18000CEEC
0x18000cd2b  cmp     [r14+10h], r13d
0x18000cd2f  jz      loc_18000CEEC
0x18000cd35  mov     ebx, r13d
0x18000cd38  mov     [rsp+4D8h+var_478], ebx
0x18000cd3c  cmp     ebx, [r14+10h]
0x18000cd40  jnb     loc_18000CDC6
0x18000cd46  mov     eax, ebx
0x18000cd48  mov     rdx, [r14+8]
0x18000cd4c  mov     rdx, [rdx+rax*8]
0x18000cd50  mov     rcx, cs:lpMem
0x18000cd57  call    SeqAddPriorityGroup
0x18000cd5c  test    eax, eax
0x18000cd5e  jnz     short loc_18000CDBF
0x18000cd60  call    cs:__imp_GetLastError
0x18000cd67  nop     dword ptr [rax+rax+00h]
0x18000cd6c  mov     ebx, eax
0x18000cd6e  mov     rdi, [rsp+4D8h]
0x18000cd76  lea     rdx, aFailedToInitia_1; "Failed to initialize setup groups"
0x18000cd7d  mov     ecx, 2000035h; unsigned int
0x18000cd82  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cd87  mov     [rsp+4D8h+var_488], r13d
0x18000cd8c  mov     [rsp+4D8h+var_490], r13
0x18000cd91  mov     [rsp+4D8h+var_498], ebx
0x18000cd95  mov     [rsp+4D8h+lpModuleName], rdi
0x18000cd9a  lea     rcx, aWdsexecutework_5; "WdsExecuteWorkQueue2"
0x18000cda1  mov     [rsp+4D8h+var_4A8], rcx
0x18000cda6  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000cdad  mov     [rsp+4D8h+var_4B0], rcx
0x18000cdb2  mov     [rsp+4D8h+var_4B8], 6FBh
0x18000cdba  jmp     loc_18000CF46
0x18000cdbf  add     ebx, esi
0x18000cdc1  jmp     loc_18000CD38
0x18000cdc6  mov     ebx, r13d
0x18000cdc9  mov     [rsp+4D8h+var_478], ebx
0x18000cdcd  mov     rcx, cs:lpMem
0x18000cdd4  cmp     ebx, r15d
0x18000cdd7  jnb     loc_18000CE60
0x18000cddd  mov     eax, ebx
0x18000cddf  lea     rdx, [rax+rax*2]
0x18000cde3  mov     r9, [rdi+rdx*8+10h]
0x18000cde8  mov     r8, [rdi+rdx*8+8]
0x18000cded  mov     rdx, [rdi+rdx*8]
0x18000cdf1  call    SeqAddLoadedModule
0x18000cdf6  test    eax, eax
0x18000cdf8  jnz     short loc_18000CE59
0x18000cdfa  call    cs:__imp_GetLastError
0x18000ce01  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
