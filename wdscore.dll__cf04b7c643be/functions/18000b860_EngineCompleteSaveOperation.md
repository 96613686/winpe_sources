# EngineCompleteSaveOperation

- ea: `0x18000b860`
- end: `0x18000bb65`
- name: `EngineCompleteSaveOperation`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006d64`

## callees

- `0x180002250`
- `0x180002d14`
- `0x180004bc4`
- `0x180008f30`
- `0x180009030`
- `0x18000a624`
- `0x18000af7c`
- `0x18000b484`
- `0x18000b860`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bab4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284ea`

## string_xrefs

- `0x18000b919`: `EngineCompleteSaveOperation`
- `0x18000b9b0`: `EngineCompleteSaveOperation`
- `0x18000ba33`: `EngineCompleteSaveOperation`
- `0x18000baee`: `EngineCompleteSaveOperation`
- `0x18000b8f5`: `EngineCompleteSaveOperation couldn't obtain new file version!`
- `0x18000b98c`: `EngineCompleteSaveOperation couldn't create %s`
- `0x18000ba0f`: `EngineCompleteSaveOperation couldn't save %s`
- `0x18000baca`: `EngineCompleteSaveOperation couldn't save contents file`

## pseudocode

```c
__int64 EngineCompleteSaveOperation()
{
  struct CONTENTS_FILE *v0; // rcx
  unsigned int v1; // esi
  unsigned int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rdi
  struct FILE_VERSION_LIST_ITEM *updated; // rax
  DWORD LastError; // ebx
  int v7; // eax
  const char *v8; // r14
  DWORD v9; // ebx
  int v10; // eax
  DWORD v11; // ebx
  int v12; // eax
  DWORD v13; // ebx
  int v14; // eax
  _BYTE v16[544]; // [rsp+70h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+2C8h] [rbp+0h]

  memset_0(v16, 0, 0x218u);
  v1 = 0;
  if ( g_pContentsFile )
  {
    v2 = 0;
    v3 = qword_18003AF70;
    while ( v2 < dword_18003AF78 )
    {
      v4 = 32LL * v2;
      if ( *(_QWORD *)(v4 + v3 + 24) )
      {
        updated = pUpdateContentsFile(v0, *(const unsigned __int16 **)(v4 + v3));
        if ( !updated )
        {
          LastError = GetLastError();
          v7 = (unsigned int)ConstructPartialMsgW(
                               0x3000016u,
                               "EngineCompleteSaveOperation couldn't obtain new file version!");
          WdsSetupLogMessageW(
            v7,
            589824,
            (int)L"D",
            0,
            1021,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            (__int64)L"EngineCompleteSaveOperation",
            lpModuleName,
            LastError,
            0,
            0);
          goto LABEL_17;
        }
        v8 = (char *)updated + 40;
        if ( !(unsigned int)OF_Open((LPCWSTR)updated + 20, 100, 1, (__int64)v16) )
        {
          v9 = GetLastError();
          v10 = (unsigned int)ConstructPartialMsgW(0x3000017u, "EngineCompleteSaveOperation couldn't create %s", v8);
          WdsSetupLogMessageW(
            v10,
            589824,
            (int)L"D",
            0,
            1027,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            (__int64)L"EngineCompleteSaveOperation",
            lpModuleName,
            v9,
            0,
            0);
          goto LABEL_17;
        }
        if ( !(unsigned int)SeqSerializeToFile(*(_QWORD *)(v4 + qword_18003AF70 + 24), v16, 0) )
        {
          v11 = GetLastError();
          v12 = (unsigned int)ConstructPartialMsgW(0x3000018u, "EngineCompleteSaveOperation couldn't save %s", v8);
          WdsSetupLogMessageW(
            v12,
            589824,
            (int)L"D",
            0,
            1033,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            (__int64)L"EngineCompleteSaveOperation",
            lpModuleName,
            v11,
            0,
            0);
          OF_Close(v16);
          goto LABEL_17;
        }
        OF_Close(v16);
        SeqDestruct(*(LPVOID *)(v4 + qword_18003AF70 + 24));
        v3 = qword_18003AF70;
        *(_QWORD *)(v4 + qword_18003AF70 + 24) = 0;
      }
      ++v2;
    }
    if ( (unsigned int)pSaveNewContentsFile(v0) )
    {
      v1 = 1;
    }
    else
    {
      v13 = GetLastError();
      v14 = (unsigned int)ConstructPartialMsgW(0x3000019u, "EngineCompleteSaveOperation couldn't save contents file");
      WdsSetupLogMessageW(
        v14,
        589824,
        (int)L"D",
        0,
        1050,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        (__int64)L"EngineCompleteSaveOperation",
        lpModuleName,
        v13,
        0,
        0);
    }
  }
LABEL_17:
  if ( g_pContentsFile )
  {
    pDestructContentsFile(g_pContentsFile);
    g_pContentsFile = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v1;
}

```

## disassembly

```asm
0x18000b860  push    rbx
0x18000b862  push    rsi
0x18000b863  push    rdi
0x18000b864  push    r14
0x18000b866  push    r15
0x18000b868  sub     rsp, 2A0h
0x18000b86f  mov     rax, cs:__security_cookie
0x18000b876  xor     rax, rsp
0x18000b879  mov     [rsp+2C8h+var_38], rax
0x18000b881  xor     edx, edx; Val
0x18000b883  mov     r8d, 218h; Size
0x18000b889  lea     rcx, [rsp+2C8h+var_258]; void *
0x18000b88e  call    memset_0
0x18000b893  xor     r15d, r15d
0x18000b896  mov     esi, r15d
0x18000b899  cmp     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, r15; CONTENTS_FILE * g_pContentsFile
0x18000b8a0  jz      loc_18000BB18
0x18000b8a6  mov     ebx, r15d
0x18000b8a9  mov     [rsp+2C8h+var_268], ebx
0x18000b8ad  mov     rax, cs:qword_18003AF70
0x18000b8b4  cmp     ebx, cs:dword_18003AF78
0x18000b8ba  jnb     loc_18000BAAB
0x18000b8c0  mov     edi, ebx
0x18000b8c2  shl     rdi, 5
0x18000b8c6  cmp     [rdi+rax+18h], r15
0x18000b8cb  jz      loc_18000BAA0
0x18000b8d1  mov     rdx, [rdi+rax]; unsigned __int16 *
0x18000b8d5  call    ?pUpdateContentsFile@@YAPEAUFILE_VERSION_LIST_ITEM@@PEAUCONTENTS_FILE@@PEBG@Z; pUpdateContentsFile(CONTENTS_FILE *,ushort const *)
0x18000b8da  test    rax, rax
0x18000b8dd  jnz     short loc_18000B955
0x18000b8df  call    cs:__imp_GetLastError
0x18000b8e6  nop     dword ptr [rax+rax+00h]
0x18000b8eb  mov     ebx, eax
0x18000b8ed  mov     rdi, [rsp+2C8h]
0x18000b8f5  lea     rdx, aEnginecomplete_1; "EngineCompleteSaveOperation couldn't ob"...
0x18000b8fc  mov     ecx, 3000016h; unsigned int
0x18000b901  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b906  mov     [rsp+2C8h+var_278], r15d; int
0x18000b90b  mov     [rsp+2C8h+var_280], r15; __int64
0x18000b910  mov     [rsp+2C8h+var_288], ebx; int
0x18000b914  mov     [rsp+2C8h+lpModuleName], rdi; lpModuleName
0x18000b919  lea     rcx, aEnginecomplete_3; "EngineCompleteSaveOperation"
0x18000b920  mov     [rsp+2C8h+var_298], rcx; __int64
0x18000b925  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b92c  mov     [rsp+2C8h+var_2A0], rcx; unsigned __int16 *
0x18000b931  mov     [rsp+2C8h+var_2A8], 3FDh; int
0x18000b939  xor     r9d, r9d; int
0x18000b93c  lea     r8, aD_1; "D"
0x18000b943  mov     edx, 90000h; int
0x18000b948  mov     rcx, rax; int
0x18000b94b  call    WdsSetupLogMessageW
0x18000b950  jmp     loc_18000BB18
0x18000b955  lea     r14, [rax+28h]
0x18000b959  lea     r9, [rsp+2C8h+var_258]
0x18000b95e  mov     edx, 64h ; 'd'
0x18000b963  lea     r8d, [rdx-63h]
0x18000b967  mov     rcx, r14; lpFileName
0x18000b96a  call    OF_Open
0x18000b96f  test    eax, eax
0x18000b971  jnz     short loc_18000B9D5
0x18000b973  call    cs:__imp_GetLastError
0x18000b97a  nop     dword ptr [rax+rax+00h]
0x18000b97f  mov     ebx, eax
0x18000b981  mov     rdi, [rsp+2C8h]
0x18000b989  mov     r8, r14
0x18000b98c  lea     rdx, aEnginecomplete_0; "EngineCompleteSaveOperation couldn't cr"...
0x18000b993  mov     ecx, 3000017h; unsigned int
0x18000b998  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b99d  mov     [rsp+2C8h+var_278], r15d
0x18000b9a2  mov     [rsp+2C8h+var_280], r15
0x18000b9a7  mov     [rsp+2C8h+var_288], ebx
0x18000b9ab  mov     [rsp+2C8h+lpModuleName], rdi
0x18000b9b0  lea     rcx, aEnginecomplete_3; "EngineCompleteSaveOperation"
0x18000b9b7  mov     [rsp+2C8h+var_298], rcx
0x18000b9bc  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b9c3  mov     [rsp+2C8h+var_2A0], rcx
0x18000b9c8  mov     [rsp+2C8h+var_2A8], 403h
0x18000b9d0  jmp     loc_18000B939
0x18000b9d5  xor     r8d, r8d
0x18000b9d8  lea     rdx, [rsp+2C8h+var_258]
0x18000b9dd  mov     rcx, cs:qword_18003AF70
0x18000b9e4  mov     rcx, [rdi+rcx+18h]
0x18000b9e9  call    SeqSerializeToFile
0x18000b9ee  test    eax, eax
0x18000b9f0  jnz     loc_18000BA79
0x18000b9f6  call    cs:__imp_GetLastError
0x18000b9fd  nop     dword ptr [rax+rax+00h]
0x18000ba02  mov     ebx, eax
0x18000ba04  mov     rdi, [rsp+2C8h]
0x18000ba0c  mov     r8, r14
0x18000ba0f  lea     rdx, aEnginecomplete_2; "EngineCompleteSaveOperation couldn't sa"...
0x18000ba16  mov     ecx, 3000018h; unsigned int
0x18000ba1b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ba20  mov     [rsp+2C8h+var_278], r15d; int
0x18000ba25  mov     [rsp+2C8h+var_280], r15; __int64
0x18000ba2a  mov     [rsp+2C8h+var_288], ebx; int
0x18000ba2e  mov     [rsp+2C8h+lpModuleName], rdi; lpModuleName
0x18000ba33  lea     rcx, aEnginecomplete_3; "EngineCompleteSaveOperation"
0x18000ba3a  mov     [rsp+2C8h+var_298], rcx; __int64
0x18000ba3f  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000ba46  mov     [rsp+2C8h+var_2A0], rcx; unsigned __int16 *
0x18000ba4b  mov     [rsp+2C8h+var_2A8], 409h; int
0x18000ba53  xor     r9d, r9d; int
0x18000ba56  lea     r8, aD_1; "D"
0x18000ba5d  mov     edx, 90000h; int
0x18000ba62  mov     rcx, rax; int
0x18000ba65  call    WdsSetupLogMessageW
0x18000ba6a  lea     rcx, [rsp+2C8h+var_258]
0x18000ba6f  call    OF_Close
0x18000ba74  jmp     loc_18000BB18
0x18000ba79  lea     rcx, [rsp+2C8h+var_258]
0x18000ba7e  call    OF_Close
0x18000ba83  mov     rcx, cs:qword_18003AF70
0x18000ba8a  mov     rcx, [rdi+rcx+18h]; lpMem
0x18000ba8f  call    SeqDestruct
0x18000ba94  mov     rax, cs:qword_18003AF70
0x18000ba9b  mov     [rdi+rax+18h], r15
0x18000baa0  inc     ebx
0x18000baa2  mov     [rsp+2C8h+var_268], ebx
0x18000baa6  jmp     loc_18000B8B4
0x18000baab  call    ?pSaveNewContentsFile@@YAHPEAUCONTENTS_FILE@@@Z; pSaveNewContentsFile(CONTENTS_FILE *)
0x18000bab0  test    eax, eax
0x18000bab2  jnz     short loc_18000BB13
0x18000bab4  call    cs:__imp_GetLastError
0x18000babb  nop     dword ptr [rax+rax+00h]
0x18000bac0  mov     ebx, eax
0x18000bac2  mov     rdi, [rsp+2C8h]
0x18000baca  lea     rdx, aEnginecomplete; "EngineCompleteSaveOperation couldn't sa"...
0x18000bad1  mov     ecx, 3000019h; unsigned int
0x18000bad6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000badb  mov     [rsp+2C8h+var_278], r15d
0x18000bae0  mov     [rsp+2C8h+var_280], r15
0x18000bae5  mov     [rsp+2C8h+var_288], ebx
0x18000bae9  mov     [rsp+2C8h+lpModuleName], rdi
0x18000baee  lea     rcx, aEnginecomplete_3; "EngineCompleteSaveOperation"
0x18000baf5  mov     [rsp+2C8h+var_298], rcx
0x18000bafa  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000bb01  mov     [rsp+2C8h+var_2A0], rcx
0x18000bb06  mov     [rsp+2C8h+var_2A8], 41Ah
0x18000bb0e  jmp     loc_18000B939
0x18000bb13  mov     esi, 1
0x18000bb18  mov     rcx, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; struct CONTENTS_FILE *
0x18000bb1f  test    rcx, rcx
0x18000bb22  jz      short loc_18000BB30
0x18000bb24  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x18000bb29  mov     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, r15; CONTENTS_FILE * g_pContentsFile
0x18000bb30  lea     rcx, CriticalSection; lpCriticalSection
0x18000bb37  call    cs:__imp_LeaveCriticalSection
0x18000bb3e  nop     dword ptr [rax+rax+00h]
0x18000bb43  mov     eax, esi
0x18000bb45  mov     rcx, [rsp+2C8h+var_38]
0x18000bb4d  xor     rcx, rsp; StackCookie
0x18000bb50  call    __security_check_cookie
0x18000bb55  add     rsp, 2A0h
0x18000bb5c  pop     r15
0x18000bb5e  pop     r14
0x18000bb60  pop     rdi
0x18000bb61  pop     rsi
0x18000bb62  pop     rbx
0x18000bb63  retn
0x1800284be  push    rbp
0x1800284c0  sub     rsp, 60h
0x1800284c4  mov     rbp, rdx
0x1800284c7  mov     rcx, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; struct CONTENTS_FILE *
0x1800284ce  test    rcx, rcx
0x1800284d1  jz      short loc_1800284E3
0x1800284d3  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x1800284d8  mov     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, 0; CONTENTS_FILE * g_pContentsFile
0x1800284e3  lea     rcx, CriticalSection; lpCriticalSection
0x1800284ea  call    cs:__imp_LeaveCriticalSection
0x1800284f1  nop     dword ptr [rax+rax+00h]
0x1800284f6  nop
0x1800284f7  add     rsp, 60h
0x1800284fb  pop     rbp
0x1800284fc  retn
```
