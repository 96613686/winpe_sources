# pSaveNewContentsFile(CONTENTS_FILE *)

- ea: `0x18000af7c`
- end: `0x18000b1db`
- name: `?pSaveNewContentsFile@@YAHPEAUCONTENTS_FILE@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct CONTENTS_FILE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18000b860`

## callees

- `0x180002250`
- `0x180008bc8`
- `0x180008d8c`
- `0x180008f30`
- `0x180009030`
- `0x18000af7c`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b017`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14d`

## string_xrefs

- `0x18000b035`: `Failed to open contents file for output '%s'`
- `0x18000b163`: `Failed to write out ContentsFile->FileVersions`

## pseudocode

```c
__int64 __fastcall pSaveNewContentsFile(struct CONTENTS_FILE *a1)
{
  struct CONTENTS_FILE *v1; // rbx
  unsigned int v2; // r14d
  __int64 v3; // r13
  DWORD v4; // ebx
  int *v5; // rax
  DWORD LastError; // ebx
  int *v7; // rax
  DWORD v8; // ebx
  int *v9; // rax
  int v11; // [rsp+20h] [rbp-4C8h]
  struct CONTENTS_FILE *v12; // [rsp+60h] [rbp-488h]
  _BYTE v13[544]; // [rsp+70h] [rbp-478h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp-258h] BYREF
  LPCWSTR lpModuleName; // [rsp+4E8h] [rbp+0h]

  v1 = g_pContentsFile;
  v12 = g_pContentsFile;
  memset_0(FileName, 0, 0x208u);
  memset_0(v13, 0, 0x218u);
  v2 = 0;
  v3 = (__int64)v1 + 8;
  if ( !(unsigned int)GetNumberedFileName((STRSAFE_LPCWSTR)v1 + 4, v11, 0) )
    goto LABEL_8;
  if ( (unsigned int)OF_Open(FileName, 1, 1, (__int64)v13) )
  {
    if ( g_bEnableDiagnosticMode )
    {
      LastError = GetLastError();
      v7 = (int *)ConstructPartialMsgW(0x70000000u, "Saving Contents File %s", (const char *)FileName);
      WdsSetupLogMessageW(
        v7,
        589824,
        (__int64)L"D",
        0,
        0x2A2u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"pSaveNewContentsFile",
        lpModuleName,
        LastError,
        0,
        0);
      v1 = v12;
    }
    if ( !(unsigned int)SerializeList(*(_QWORD *)v1, 1, 0, (unsigned int)v13, v3) )
    {
      v8 = GetLastError();
      v9 = (int *)ConstructPartialMsgW(0x300000Fu, "Failed to write out ContentsFile->FileVersions");
      WdsSetupLogMessageW(
        v9,
        589824,
        (__int64)L"D",
        0,
        0x2A6u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"pSaveNewContentsFile",
        lpModuleName,
        v8,
        0,
        0);
      goto LABEL_9;
    }
LABEL_8:
    v2 = 1;
    goto LABEL_9;
  }
  v4 = GetLastError();
  v5 = (int *)ConstructPartialMsgW(0x300000Eu, "Failed to open contents file for output '%s'", (const char *)FileName);
  WdsSetupLogMessageW(
    v5,
    589824,
    (__int64)L"D",
    0,
    0x29Eu,
    L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
    L"pSaveNewContentsFile",
    lpModuleName,
    v4,
    0,
    0);
LABEL_9:
  OF_Close(v13);
  return v2;
}

```

## disassembly

```asm
0x18000af7c  push    rbx
0x18000af7e  push    rdi
0x18000af7f  push    r12
0x18000af81  push    r13
0x18000af83  push    r14
0x18000af85  push    r15
0x18000af87  sub     rsp, 4B8h
0x18000af8e  mov     rax, cs:__security_cookie
0x18000af95  xor     rax, rsp
0x18000af98  mov     [rsp+4E8h+var_48], rax
0x18000afa0  mov     rbx, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; CONTENTS_FILE * g_pContentsFile
0x18000afa7  mov     [rsp+4E8h+var_488], rbx
0x18000afac  xor     edx, edx; Val
0x18000afae  mov     r8d, 208h; Size
0x18000afb4  lea     rcx, [rsp+4E8h+FileName]; void *
0x18000afbc  call    memset_0
0x18000afc1  xor     edx, edx; Val
0x18000afc3  mov     r8d, 218h; Size
0x18000afc9  lea     rcx, [rsp+4E8h+var_478]; void *
0x18000afce  call    memset_0
0x18000afd3  xor     r15d, r15d
0x18000afd6  mov     r14d, r15d
0x18000afd9  lea     r13, [rbx+8]
0x18000afdd  mov     dword ptr [rsp+4E8h+var_4C0], r15d; int
0x18000afe2  lea     r9, [rsp+4E8h+FileName]
0x18000afea  mov     rcx, r13; pszSrc
0x18000afed  call    GetNumberedFileName
0x18000aff2  test    eax, eax
0x18000aff4  jz      loc_18000B1A5
0x18000affa  lea     r9, [rsp+4E8h+var_478]
0x18000afff  lea     edx, [r15+1]
0x18000b003  mov     r8d, edx
0x18000b006  lea     rcx, [rsp+4E8h+FileName]; lpFileName
0x18000b00e  call    OF_Open
0x18000b013  test    eax, eax
0x18000b015  jnz     short loc_18000B095
0x18000b017  call    cs:__imp_GetLastError
0x18000b01e  nop     dword ptr [rax+rax+00h]
0x18000b023  mov     ebx, eax
0x18000b025  mov     rdi, [rsp+4E8h]
0x18000b02d  lea     r8, [rsp+4E8h+FileName]
0x18000b035  lea     rdx, aFailedToOpenCo; "Failed to open contents file for output"...
0x18000b03c  mov     ecx, 300000Eh; unsigned int
0x18000b041  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b046  mov     [rsp+4E8h+var_498], r15d; int
0x18000b04b  mov     [rsp+4E8h+var_4A0], r15; __int64
0x18000b050  mov     [rsp+4E8h+var_4A8], ebx; int
0x18000b054  mov     [rsp+4E8h+lpModuleName], rdi; lpModuleName
0x18000b059  lea     r15, aPsavenewconten; "pSaveNewContentsFile"
0x18000b060  mov     [rsp+4E8h+var_4B8], r15; __int64
0x18000b065  lea     r12, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b06c  mov     [rsp+4E8h+var_4C0], r12; unsigned __int16 *
0x18000b071  mov     [rsp+4E8h+var_4C8], 29Eh; int
0x18000b079  xor     r9d, r9d; int
0x18000b07c  lea     r8, aD_1; "D"
0x18000b083  mov     edx, 90000h; int
0x18000b088  mov     rcx, rax; int
0x18000b08b  call    WdsSetupLogMessageW
0x18000b090  jmp     loc_18000B1AB
0x18000b095  cmp     cs:?g_bEnableDiagnosticMode@@3HA, r15d; int g_bEnableDiagnosticMode
0x18000b09c  jz      loc_18000B122
0x18000b0a2  call    cs:__imp_GetLastError
0x18000b0a9  nop     dword ptr [rax+rax+00h]
0x18000b0ae  mov     ebx, eax
0x18000b0b0  mov     rdi, [rsp+4E8h]
0x18000b0b8  lea     r8, [rsp+4E8h+FileName]
0x18000b0c0  lea     rdx, aSavingContents; "Saving Contents File %s"
0x18000b0c7  mov     ecx, 70000000h; unsigned int
0x18000b0cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b0d1  mov     [rsp+4E8h+var_498], r15d; int
0x18000b0d6  mov     [rsp+4E8h+var_4A0], r15; __int64
0x18000b0db  mov     [rsp+4E8h+var_4A8], ebx; int
0x18000b0df  mov     [rsp+4E8h+lpModuleName], rdi; lpModuleName
0x18000b0e4  lea     r15, aPsavenewconten; "pSaveNewContentsFile"
0x18000b0eb  mov     [rsp+4E8h+var_4B8], r15; __int64
0x18000b0f0  lea     r12, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b0f7  mov     [rsp+4E8h+var_4C0], r12; unsigned __int16 *
0x18000b0fc  mov     [rsp+4E8h+var_4C8], 2A2h; int
0x18000b104  xor     r9d, r9d; int
0x18000b107  lea     r8, aD_1; "D"
0x18000b10e  mov     edx, 90000h; int
0x18000b113  mov     rcx, rax; int
0x18000b116  call    WdsSetupLogMessageW
0x18000b11b  mov     rbx, [rsp+4E8h+var_488]
0x18000b120  jmp     short loc_18000B130
0x18000b122  lea     r15, aPsavenewconten; "pSaveNewContentsFile"
0x18000b129  lea     r12, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b130  mov     qword ptr [rsp+4E8h+var_4C8], r13
0x18000b135  lea     r9, [rsp+4E8h+var_478]
0x18000b13a  xor     r8d, r8d
0x18000b13d  lea     edx, [r8+1]
0x18000b141  mov     rcx, [rbx]
0x18000b144  call    SerializeList
0x18000b149  test    eax, eax
0x18000b14b  jnz     short loc_18000B1A5
0x18000b14d  call    cs:__imp_GetLastError
0x18000b154  nop     dword ptr [rax+rax+00h]
0x18000b159  mov     ebx, eax
0x18000b15b  mov     rdi, [rsp+4E8h]
0x18000b163  lea     rdx, aFailedToWriteO; "Failed to write out ContentsFile->FileV"...
0x18000b16a  mov     ecx, 300000Fh; unsigned int
0x18000b16f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b174  mov     [rsp+4E8h+var_498], 0
0x18000b17c  mov     [rsp+4E8h+var_4A0], 0
0x18000b185  mov     [rsp+4E8h+var_4A8], ebx
0x18000b189  mov     [rsp+4E8h+lpModuleName], rdi
0x18000b18e  mov     [rsp+4E8h+var_4B8], r15
0x18000b193  mov     [rsp+4E8h+var_4C0], r12
0x18000b198  mov     [rsp+4E8h+var_4C8], 2A6h
0x18000b1a0  jmp     loc_18000B079
0x18000b1a5  mov     r14d, 1
0x18000b1ab  lea     rcx, [rsp+4E8h+var_478]
0x18000b1b0  call    OF_Close
0x18000b1b5  mov     eax, r14d
0x18000b1b8  mov     rcx, [rsp+4E8h+var_48]
0x18000b1c0  xor     rcx, rsp; StackCookie
0x18000b1c3  call    __security_check_cookie
0x18000b1c8  add     rsp, 4B8h
0x18000b1cf  pop     r15
0x18000b1d1  pop     r14
0x18000b1d3  pop     r13
0x18000b1d5  pop     r12
0x18000b1d7  pop     rdi
0x18000b1d8  pop     rbx
0x18000b1d9  retn
0x1800283e6  push    rbp
0x1800283e8  sub     rsp, 60h
0x1800283ec  mov     rbp, rdx
0x1800283ef  lea     rcx, [rbp+70h]
0x1800283f3  call    OF_Close
0x1800283f8  nop
0x1800283f9  add     rsp, 60h
0x1800283fd  pop     rbp
0x1800283fe  retn
```
