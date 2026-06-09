# EngineBeginSaveOperation

- ea: `0x18000b6c4`
- end: `0x18000b858`
- name: `EngineBeginSaveOperation`
- size: `404`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180006d64`

## callees

- `0x180002250`
- `0x180009030`
- `0x180009f2c`
- `0x18000a624`
- `0x18000b484`
- `0x18000b6c4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b83f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b83f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800284a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b6e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b6e6`

## string_xrefs

- `0x18000b7a6`: `EngineBegineSaveOperation couldn't create contents file`

## pseudocode

```c
_BOOL8 __fastcall EngineBeginSaveOperation(unsigned __int16 *a1, __int64 a2)
{
  BOOL v4; // esi
  const unsigned __int16 *v5; // rcx
  DWORD v6; // ebx
  int *v7; // rax
  struct CONTENTS_FILE *v8; // rcx
  DWORD LastError; // ebx
  int *v10; // rax
  struct FILE_VERSION_LIST_ITEM *updated; // rax
  LPCWSTR lpModuleName; // [rsp+98h] [rbp+0h]

  v4 = 0;
  EnterCriticalSection(&CriticalSection);
  if ( g_WorkingDir )
  {
    if ( !g_pContentsFile )
    {
      g_pContentsFile = pConstructContentsFile(v5);
      if ( g_pContentsFile )
      {
        updated = pUpdateContentsFile(v8, a1);
        if ( updated )
          v4 = OF_Open((LPCWSTR)updated + 20, 100, 1, a2) != 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = (int *)ConstructPartialMsgW(0x2000015u, "EngineBegineSaveOperation couldn't create contents file");
        WdsSetupLogMessageW(
          v10,
          589824,
          (__int64)L"D",
          0,
          0x3A8u,
          L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
          L"EngineBeginSaveOperation",
          lpModuleName,
          LastError,
          0,
          0);
      }
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = (int *)ConstructPartialMsgW(
                  0x3000014u,
                  "No working dir has been given to panther.  Call WdsInitialize(ReInit=TRUE) to specify one");
    WdsSetupLogMessageW(
      v7,
      589824,
      (__int64)L"D",
      0,
      0x39Au,
      L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
      L"EngineBeginSaveOperation",
      lpModuleName,
      v6,
      0,
      0);
  }
  if ( !v4 )
  {
    if ( g_pContentsFile )
    {
      pDestructContentsFile(g_pContentsFile);
      g_pContentsFile = 0;
    }
    LeaveCriticalSection(&CriticalSection);
  }
  return v4;
}

```

## disassembly

```asm
0x18000b6c4  push    rbx
0x18000b6c6  push    rsi
0x18000b6c7  push    rdi
0x18000b6c8  push    r14
0x18000b6ca  sub     rsp, 78h
0x18000b6ce  mov     rdi, rdx
0x18000b6d1  mov     rbx, rcx
0x18000b6d4  xor     r14d, r14d
0x18000b6d7  mov     esi, r14d
0x18000b6da  mov     [rsp+98h+var_38], r14d
0x18000b6df  lea     rcx, CriticalSection; lpCriticalSection
0x18000b6e6  call    cs:__imp_EnterCriticalSection
0x18000b6ed  nop     dword ptr [rax+rax+00h]
0x18000b6f2  cmp     cs:?g_WorkingDir@@3PAGA, r14w; ushort near * g_WorkingDir
0x18000b6fa  jnz     short loc_18000B772
0x18000b6fc  call    cs:__imp_GetLastError
0x18000b703  nop     dword ptr [rax+rax+00h]
0x18000b708  mov     ebx, eax
0x18000b70a  mov     rdi, [rsp+98h]
0x18000b712  lea     rdx, aNoWorkingDirHa_1; "No working dir has been given to panthe"...
0x18000b719  mov     ecx, 3000014h; unsigned int
0x18000b71e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b723  mov     [rsp+98h+var_48], r14d; int
0x18000b728  mov     [rsp+98h+var_50], r14; __int64
0x18000b72d  mov     [rsp+98h+var_58], ebx; int
0x18000b731  mov     [rsp+98h+lpModuleName], rdi; lpModuleName
0x18000b736  lea     rcx, aEnginebeginsav; "EngineBeginSaveOperation"
0x18000b73d  mov     [rsp+98h+var_68], rcx; __int64
0x18000b742  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b749  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x18000b74e  mov     [rsp+98h+var_78], 39Ah; int
0x18000b756  xor     r9d, r9d; int
0x18000b759  lea     r8, aD_1; "D"
0x18000b760  mov     edx, 90000h; int
0x18000b765  mov     rcx, rax; int
0x18000b768  call    WdsSetupLogMessageW
0x18000b76d  jmp     loc_18000B81C
0x18000b772  cmp     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, r14; CONTENTS_FILE * g_pContentsFile
0x18000b779  jnz     loc_18000B81C
0x18000b77f  call    ?pConstructContentsFile@@YAPEAUCONTENTS_FILE@@PEBG@Z; pConstructContentsFile(ushort const *)
0x18000b784  mov     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, rax; CONTENTS_FILE * g_pContentsFile
0x18000b78b  test    rax, rax
0x18000b78e  jnz     short loc_18000B7EF
0x18000b790  call    cs:__imp_GetLastError
0x18000b797  nop     dword ptr [rax+rax+00h]
0x18000b79c  mov     ebx, eax
0x18000b79e  mov     rdi, [rsp+98h]
0x18000b7a6  lea     rdx, aEnginebeginesa; "EngineBegineSaveOperation couldn't crea"...
0x18000b7ad  mov     ecx, 2000015h; unsigned int
0x18000b7b2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b7b7  mov     [rsp+98h+var_48], r14d
0x18000b7bc  mov     [rsp+98h+var_50], r14
0x18000b7c1  mov     [rsp+98h+var_58], ebx
0x18000b7c5  mov     [rsp+98h+lpModuleName], rdi
0x18000b7ca  lea     rcx, aEnginebeginsav; "EngineBeginSaveOperation"
0x18000b7d1  mov     [rsp+98h+var_68], rcx
0x18000b7d6  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b7dd  mov     [rsp+98h+var_70], rcx
0x18000b7e2  mov     [rsp+98h+var_78], 3A8h
0x18000b7ea  jmp     loc_18000B756
0x18000b7ef  mov     rdx, rbx; unsigned __int16 *
0x18000b7f2  call    ?pUpdateContentsFile@@YAPEAUFILE_VERSION_LIST_ITEM@@PEAUCONTENTS_FILE@@PEBG@Z; pUpdateContentsFile(CONTENTS_FILE *,ushort const *)
0x18000b7f7  test    rax, rax
0x18000b7fa  jz      short loc_18000B81C
0x18000b7fc  lea     rcx, [rax+28h]; lpFileName
0x18000b800  mov     r9, rdi
0x18000b803  mov     ebx, 1
0x18000b808  mov     r8d, ebx
0x18000b80b  lea     edx, [rbx+63h]
0x18000b80e  call    OF_Open
0x18000b813  test    eax, eax
0x18000b815  cmovnz  esi, ebx
0x18000b818  mov     [rsp+98h+var_38], esi
0x18000b81c  test    esi, esi
0x18000b81e  jnz     short loc_18000B84B
0x18000b820  mov     rcx, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; struct CONTENTS_FILE *
0x18000b827  test    rcx, rcx
0x18000b82a  jz      short loc_18000B838
0x18000b82c  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x18000b831  mov     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, r14; CONTENTS_FILE * g_pContentsFile
0x18000b838  lea     rcx, CriticalSection; lpCriticalSection
0x18000b83f  call    cs:__imp_LeaveCriticalSection
0x18000b846  nop     dword ptr [rax+rax+00h]
0x18000b84b  mov     eax, esi
0x18000b84d  add     rsp, 78h
0x18000b851  pop     r14
0x18000b853  pop     rdi
0x18000b854  pop     rsi
0x18000b855  pop     rbx
0x18000b856  retn
0x180028472  push    rbp
0x180028474  sub     rsp, 60h
0x180028478  mov     rbp, rdx
0x18002847b  cmp     dword ptr [rbp+60h], 0
0x18002847f  jnz     short loc_1800284B1
0x180028481  mov     rcx, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; struct CONTENTS_FILE *
0x180028488  test    rcx, rcx
0x18002848b  jz      short loc_18002849D
0x18002848d  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x180028492  mov     cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA, 0; CONTENTS_FILE * g_pContentsFile
0x18002849d  lea     rcx, CriticalSection; lpCriticalSection
0x1800284a4  call    cs:__imp_LeaveCriticalSection
0x1800284ab  nop     dword ptr [rax+rax+00h]
0x1800284b0  nop
0x1800284b1  add     rsp, 60h
0x1800284b5  pop     rbp
0x1800284b6  retn
```
