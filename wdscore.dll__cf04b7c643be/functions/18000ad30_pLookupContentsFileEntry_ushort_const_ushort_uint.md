# pLookupContentsFileEntry(ushort const *,ushort *,uint)

- ea: `0x18000ad30`
- end: `0x18000af74`
- name: `?pLookupContentsFileEntry@@YAHPEBGPEAGI@Z`
- size: `580`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000a6b8`
- `0x18000c1a0`
- `0x18000c850`

## callees

- `0x180002250`
- `0x180009e30`
- `0x180009f2c`
- `0x18000a624`
- `0x18000a658`
- `0x18000ad30`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aedd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aedd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000af56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad59`

## string_xrefs

- `0x18000aef3`: `Couldn't copy pFV->FileName in pLookupContentsFileEntry`

## pseudocode

```c
__int64 __fastcall pLookupContentsFileEntry(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  struct CONTENTS_FILE *v4; // rsi
  unsigned int v5; // r14d
  const unsigned __int16 *v6; // rcx
  DWORD v7; // ebx
  int *v8; // rax
  struct CONTENTS_FILE *v9; // rax
  DWORD v10; // ebx
  int *v11; // rax
  struct FILE_VERSION_LIST_ITEM *EntryInContentsFile; // rax
  DWORD v13; // ebx
  int *v14; // rax
  DWORD LastError; // ebx
  int *v16; // rax
  LPCWSTR lpModuleName; // [rsp+A8h] [rbp+0h]

  v4 = 0;
  v5 = 0;
  EnterCriticalSection(&CriticalSection);
  if ( g_WorkingDir )
  {
    v9 = pConstructContentsFile(v6);
    v4 = v9;
    if ( v9 )
    {
      EntryInContentsFile = pFindEntryInContentsFile(v9, a1);
      if ( EntryInContentsFile )
      {
        if ( StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)EntryInContentsFile + 20) >= 0 )
        {
          v5 = 1;
        }
        else
        {
          LastError = GetLastError();
          v16 = (int *)ConstructPartialMsgW(0x400001Du, "Couldn't copy pFV->FileName in pLookupContentsFileEntry");
          WdsSetupLogMessageW(
            v16,
            589824,
            (__int64)L"D",
            0,
            0x460u,
            L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
            L"pLookupContentsFileEntry",
            lpModuleName,
            LastError,
            0,
            0);
        }
      }
      else
      {
        v13 = GetLastError();
        v14 = (int *)ConstructPartialMsgW(0x400001Cu, "Couldn't find queue '%s' in contents file", (const char *)a1);
        WdsSetupLogMessageW(
          v14,
          589824,
          (__int64)L"D",
          0,
          0x45Au,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"pLookupContentsFileEntry",
          lpModuleName,
          v13,
          0,
          0);
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = (int *)ConstructPartialMsgW(0x300001Bu, "Couldn't construct contents file!");
      WdsSetupLogMessageW(
        v11,
        589824,
        (__int64)L"D",
        0,
        0x452u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"pLookupContentsFileEntry",
        lpModuleName,
        v10,
        0,
        0);
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = (int *)ConstructPartialMsgW(
                  0x300001Au,
                  "No working dir has been given to panther.  Call WdsInitialize(Reinit=TRUE) to specify one (2nd msg)");
    WdsSetupLogMessageW(
      v8,
      589824,
      (__int64)L"D",
      0,
      0x44Au,
      L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
      L"pLookupContentsFileEntry",
      lpModuleName,
      v7,
      0,
      0);
  }
  if ( v4 )
    pDestructContentsFile(v4);
  LeaveCriticalSection(&CriticalSection);
  return v5;
}

```

## disassembly

```asm
0x18000ad30  push    rbx
0x18000ad32  push    rsi
0x18000ad33  push    rdi
0x18000ad34  push    r12
0x18000ad36  push    r14
0x18000ad38  push    r15
0x18000ad3a  sub     rsp, 78h
0x18000ad3e  mov     rbx, rdx
0x18000ad41  mov     r15, rcx
0x18000ad44  xor     r12d, r12d
0x18000ad47  mov     esi, r12d
0x18000ad4a  mov     [rsp+0A8h+var_48], r12
0x18000ad4f  mov     r14d, r12d
0x18000ad52  lea     rcx, CriticalSection; lpCriticalSection
0x18000ad59  call    cs:__imp_EnterCriticalSection
0x18000ad60  nop     dword ptr [rax+rax+00h]
0x18000ad65  cmp     cs:?g_WorkingDir@@3PAGA, r12w; ushort near * g_WorkingDir
0x18000ad6d  jnz     short loc_18000ADE5
0x18000ad6f  call    cs:__imp_GetLastError
0x18000ad76  nop     dword ptr [rax+rax+00h]
0x18000ad7b  mov     ebx, eax
0x18000ad7d  mov     rdi, [rsp+0A8h]
0x18000ad85  lea     rdx, aNoWorkingDirHa_0; "No working dir has been given to panthe"...
0x18000ad8c  mov     ecx, 300001Ah; unsigned int
0x18000ad91  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ad96  mov     [rsp+0A8h+var_58], r12d; int
0x18000ad9b  mov     [rsp+0A8h+var_60], r12; __int64
0x18000ada0  mov     [rsp+0A8h+var_68], ebx; int
0x18000ada4  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x18000ada9  lea     rcx, aPlookupcontent; "pLookupContentsFileEntry"
0x18000adb0  mov     [rsp+0A8h+var_78], rcx; __int64
0x18000adb5  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000adbc  mov     [rsp+0A8h+var_80], rcx; unsigned __int16 *
0x18000adc1  mov     [rsp+0A8h+var_88], 44Ah; int
0x18000adc9  xor     r9d, r9d; int
0x18000adcc  lea     r8, aD_1; "D"
0x18000add3  mov     edx, 90000h; int
0x18000add8  mov     rcx, rax; int
0x18000addb  call    WdsSetupLogMessageW
0x18000ade0  jmp     loc_18000AF42
0x18000ade5  call    ?pConstructContentsFile@@YAPEAUCONTENTS_FILE@@PEBG@Z; pConstructContentsFile(ushort const *)
0x18000adea  mov     rsi, rax
0x18000aded  mov     [rsp+0A8h+var_48], rax
0x18000adf2  test    rax, rax
0x18000adf5  jnz     short loc_18000AE56
0x18000adf7  call    cs:__imp_GetLastError
0x18000adfe  nop     dword ptr [rax+rax+00h]
0x18000ae03  mov     ebx, eax
0x18000ae05  mov     rdi, [rsp+0A8h]
0x18000ae0d  lea     rdx, aCouldnTConstru; "Couldn't construct contents file!"
0x18000ae14  mov     ecx, 300001Bh; unsigned int
0x18000ae19  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ae1e  mov     [rsp+0A8h+var_58], r12d
0x18000ae23  mov     [rsp+0A8h+var_60], r12
0x18000ae28  mov     [rsp+0A8h+var_68], ebx
0x18000ae2c  mov     [rsp+0A8h+lpModuleName], rdi
0x18000ae31  lea     rcx, aPlookupcontent; "pLookupContentsFileEntry"
0x18000ae38  mov     [rsp+0A8h+var_78], rcx
0x18000ae3d  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000ae44  mov     [rsp+0A8h+var_80], rcx
0x18000ae49  mov     [rsp+0A8h+var_88], 452h
0x18000ae51  jmp     loc_18000ADC9
0x18000ae56  mov     rdx, r15; unsigned __int16 *
0x18000ae59  mov     rcx, rax; struct CONTENTS_FILE *
0x18000ae5c  call    ?pFindEntryInContentsFile@@YAPEAUFILE_VERSION_LIST_ITEM@@PEAUCONTENTS_FILE@@PEBG@Z; pFindEntryInContentsFile(CONTENTS_FILE *,ushort const *)
0x18000ae61  test    rax, rax
0x18000ae64  jnz     short loc_18000AEC8
0x18000ae66  call    cs:__imp_GetLastError
0x18000ae6d  nop     dword ptr [rax+rax+00h]
0x18000ae72  mov     ebx, eax
0x18000ae74  mov     rdi, [rsp+0A8h]
0x18000ae7c  mov     r8, r15
0x18000ae7f  lea     rdx, aCouldnTFindQue; "Couldn't find queue '%s' in contents fi"...
0x18000ae86  mov     ecx, 400001Ch; unsigned int
0x18000ae8b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ae90  mov     [rsp+0A8h+var_58], r12d
0x18000ae95  mov     [rsp+0A8h+var_60], r12
0x18000ae9a  mov     [rsp+0A8h+var_68], ebx
0x18000ae9e  mov     [rsp+0A8h+lpModuleName], rdi
0x18000aea3  lea     rcx, aPlookupcontent; "pLookupContentsFileEntry"
0x18000aeaa  mov     [rsp+0A8h+var_78], rcx
0x18000aeaf  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000aeb6  mov     [rsp+0A8h+var_80], rcx
0x18000aebb  mov     [rsp+0A8h+var_88], 45Ah
0x18000aec3  jmp     loc_18000ADC9
0x18000aec8  lea     r8, [rax+28h]; unsigned __int16 *
0x18000aecc  mov     edx, 104h; unsigned __int64
0x18000aed1  mov     rcx, rbx; unsigned __int16 *
0x18000aed4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aed9  test    eax, eax
0x18000aedb  jns     short loc_18000AF3C
0x18000aedd  call    cs:__imp_GetLastError
0x18000aee4  nop     dword ptr [rax+rax+00h]
0x18000aee9  mov     ebx, eax
0x18000aeeb  mov     rdi, [rsp+0A8h]
0x18000aef3  lea     rdx, aCouldnTCopyPfv; "Couldn't copy pFV->FileName in pLookupC"...
0x18000aefa  mov     ecx, 400001Dh; unsigned int
0x18000aeff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000af04  mov     [rsp+0A8h+var_58], r12d
0x18000af09  mov     [rsp+0A8h+var_60], r12
0x18000af0e  mov     [rsp+0A8h+var_68], ebx
0x18000af12  mov     [rsp+0A8h+lpModuleName], rdi
0x18000af17  lea     rcx, aPlookupcontent; "pLookupContentsFileEntry"
0x18000af1e  mov     [rsp+0A8h+var_78], rcx
0x18000af23  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000af2a  mov     [rsp+0A8h+var_80], rcx
0x18000af2f  mov     [rsp+0A8h+var_88], 460h
0x18000af37  jmp     loc_18000ADC9
0x18000af3c  mov     r14d, 1
0x18000af42  test    rsi, rsi
0x18000af45  jz      short loc_18000AF4F
0x18000af47  mov     rcx, rsi; struct CONTENTS_FILE *
0x18000af4a  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x18000af4f  lea     rcx, CriticalSection; lpCriticalSection
0x18000af56  call    cs:__imp_LeaveCriticalSection
0x18000af5d  nop     dword ptr [rax+rax+00h]
0x18000af62  mov     eax, r14d
0x18000af65  add     rsp, 78h
0x18000af69  pop     r15
0x18000af6b  pop     r14
0x18000af6d  pop     r12
0x18000af6f  pop     rdi
0x18000af70  pop     rsi
0x18000af71  pop     rbx
0x18000af72  retn
0x1800283af  push    rbp
0x1800283b1  sub     rsp, 60h
0x1800283b5  mov     rbp, rdx
0x1800283b8  mov     rcx, [rbp+60h]; struct CONTENTS_FILE *
0x1800283bc  test    rcx, rcx
0x1800283bf  jz      short loc_1800283C7
0x1800283c1  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x1800283c6  nop
0x1800283c7  lea     rcx, CriticalSection
0x1800283ce  add     rsp, 60h
0x1800283d2  pop     rbp
0x1800283d3  jmp     cs:__imp_LeaveCriticalSection
```
