# pConstructContentsFile(ushort const *)

- ea: `0x180009f2c`
- end: `0x18000a18c`
- name: `?pConstructContentsFile@@YAPEAUCONTENTS_FILE@@PEBG@Z`
- size: `608`
- prototype: `struct CONTENTS_FILE *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000ad30`
- `0x18000b6c4`

## callees

- `0x1800021c4`
- `0x180002250`
- `0x180008bc8`
- `0x180008d8c`
- `0x180008f30`
- `0x180009030`
- `0x180009e30`
- `0x180009f2c`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f98`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a155`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800282ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a155`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800282ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800282d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800282d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0cc`

## string_xrefs

- `0x18000a051`: `Failed to open contents file '%s'`
- `0x18000a0e2`: `Failed to read in ContentsFile->FileVersions`

## pseudocode

```c
struct CONTENTS_FILE *__fastcall pConstructContentsFile(const unsigned __int16 *a1)
{
  unsigned __int16 *v1; // r14
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rsi
  __int64 v4; // rax
  DWORD LastError; // ebx
  int *v6; // rax
  DWORD v7; // ebx
  int *v8; // rax
  HANDLE v9; // rax
  int v11; // [rsp+20h] [rbp-4B8h]
  _BYTE v12[544]; // [rsp+70h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp-248h] BYREF
  LPCWSTR lpModuleName; // [rsp+4D8h] [rbp+0h]

  memset_0(FileName, 0, 0x208u);
  v1 = 0;
  memset_0(v12, 0, 0x218u);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x210u);
  if ( v3 )
  {
    v4 = ConstructList(WdsSeqFree, &pSerializeFileVersion);
    *(_QWORD *)v3 = v4;
    if ( v4 )
    {
      if ( StringCchCopyW(v3 + 4, 0x104u, &g_WorkingDir) >= 0 )
      {
        if ( (unsigned int)GetNumberedFileName(&g_WorkingDir, v11, 1) )
        {
          if ( !(unsigned int)OF_Open(FileName, 1, 0, (__int64)v12) )
          {
            LastError = GetLastError();
            v6 = (int *)ConstructPartialMsgW(0x300000Bu, "Failed to open contents file '%s'", (const char *)FileName);
            WdsSetupLogMessageW(
              v6,
              589824,
              (__int64)L"D",
              0,
              0x20Au,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"pConstructContentsFile",
              lpModuleName,
              LastError,
              0,
              0);
            goto LABEL_11;
          }
          if ( !(unsigned int)SerializeList(*(_QWORD *)v3, 0, 0, (unsigned int)v12, (__int64)(v3 + 4)) )
          {
            v7 = GetLastError();
            v8 = (int *)ConstructPartialMsgW(0x300000Cu, "Failed to read in ContentsFile->FileVersions");
            WdsSetupLogMessageW(
              v8,
              589824,
              (__int64)L"D",
              0,
              0x210u,
              L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
              L"pConstructContentsFile",
              lpModuleName,
              v7,
              0,
              0);
            goto LABEL_11;
          }
        }
        v1 = v3;
        v3 = 0;
      }
    }
  }
LABEL_11:
  if ( v3 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v3);
  }
  OF_Close(v12);
  return (struct CONTENTS_FILE *)v1;
}

```

## disassembly

```asm
0x180009f2c  push    rbx
0x180009f2e  push    rsi
0x180009f2f  push    rdi
0x180009f30  push    r14
0x180009f32  sub     rsp, 4B8h
0x180009f39  mov     rax, cs:__security_cookie
0x180009f40  xor     rax, rsp
0x180009f43  mov     [rsp+4D8h+var_38], rax
0x180009f4b  xor     edx, edx; Val
0x180009f4d  mov     r8d, 208h; Size
0x180009f53  lea     rcx, [rsp+4D8h+FileName]; void *
0x180009f5b  call    memset_0
0x180009f60  mov     [rsp+4D8h+var_478], 0
0x180009f69  xor     r14d, r14d
0x180009f6c  xor     edx, edx; Val
0x180009f6e  mov     r8d, 218h; Size
0x180009f74  lea     rcx, [rsp+4D8h+var_468]; void *
0x180009f79  call    memset_0
0x180009f7e  nop
0x180009f7f  call    cs:__imp_GetProcessHeap
0x180009f86  nop     dword ptr [rax+rax+00h]
0x180009f8b  mov     rcx, rax; hHeap
0x180009f8e  lea     edx, [r14+8]; dwFlags
0x180009f92  mov     r8d, 210h; dwBytes
0x180009f98  call    cs:__imp_HeapAlloc
0x180009f9f  nop     dword ptr [rax+rax+00h]
0x180009fa4  mov     rsi, rax
0x180009fa7  mov     [rsp+4D8h+var_478], rax
0x180009fac  test    rax, rax
0x180009faf  jz      loc_18000A13C
0x180009fb5  lea     rdx, ?pSerializeFileVersion@@YAHPEAPEAUTAG_LISTITEM@@W4OF_DIRECTION@@PEAUTAG_OBJECT_FILE@@PEAX@Z; pSerializeFileVersion(TAG_LISTITEM * *,OF_DIRECTION,TAG_OBJECT_FILE *,void *)
0x180009fbc  lea     rcx, WdsSeqFree
0x180009fc3  call    ConstructList
0x180009fc8  mov     [rsi], rax
0x180009fcb  test    rax, rax
0x180009fce  jz      loc_18000A13C
0x180009fd4  lea     rbx, [rsi+8]
0x180009fd8  lea     r8, ?g_WorkingDir@@3PAGA; unsigned __int16 *
0x180009fdf  mov     edx, 104h; unsigned __int64
0x180009fe4  mov     rcx, rbx; unsigned __int16 *
0x180009fe7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009fec  test    eax, eax
0x180009fee  js      loc_18000A13C
0x180009ff4  lea     edi, [r14+1]
0x180009ff8  mov     dword ptr [rsp+4D8h+var_4B0], edi; int
0x180009ffc  lea     r9, [rsp+4D8h+FileName]
0x18000a004  lea     rcx, ?g_WorkingDir@@3PAGA; pszSrc
0x18000a00b  call    GetNumberedFileName
0x18000a010  test    eax, eax
0x18000a012  jz      loc_18000A132
0x18000a018  lea     r9, [rsp+4D8h+var_468]
0x18000a01d  xor     r8d, r8d
0x18000a020  mov     edx, edi
0x18000a022  lea     rcx, [rsp+4D8h+FileName]; lpFileName
0x18000a02a  call    OF_Open
0x18000a02f  test    eax, eax
0x18000a031  jnz     short loc_18000A0B1
0x18000a033  call    cs:__imp_GetLastError
0x18000a03a  nop     dword ptr [rax+rax+00h]
0x18000a03f  mov     ebx, eax
0x18000a041  mov     rdi, [rsp+4D8h]
0x18000a049  lea     r8, [rsp+4D8h+FileName]
0x18000a051  lea     rdx, aFailedToOpenCo_0; "Failed to open contents file '%s'"
0x18000a058  mov     ecx, 300000Bh; unsigned int
0x18000a05d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a062  mov     [rsp+4D8h+var_488], r14d; int
0x18000a067  mov     [rsp+4D8h+var_490], r14; __int64
0x18000a06c  mov     [rsp+4D8h+var_498], ebx; int
0x18000a070  mov     [rsp+4D8h+lpModuleName], rdi; lpModuleName
0x18000a075  lea     rcx, aPconstructcont; "pConstructContentsFile"
0x18000a07c  mov     [rsp+4D8h+var_4A8], rcx; __int64
0x18000a081  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a088  mov     [rsp+4D8h+var_4B0], rcx; unsigned __int16 *
0x18000a08d  mov     [rsp+4D8h+var_4B8], 20Ah; int
0x18000a095  xor     r9d, r9d; int
0x18000a098  lea     r8, aD_1; "D"
0x18000a09f  mov     edx, 90000h; int
0x18000a0a4  mov     rcx, rax; int
0x18000a0a7  call    WdsSetupLogMessageW
0x18000a0ac  jmp     loc_18000A13C
0x18000a0b1  mov     qword ptr [rsp+4D8h+var_4B8], rbx
0x18000a0b6  lea     r9, [rsp+4D8h+var_468]
0x18000a0bb  xor     r8d, r8d
0x18000a0be  xor     edx, edx
0x18000a0c0  mov     rcx, [rsi]
0x18000a0c3  call    SerializeList
0x18000a0c8  test    eax, eax
0x18000a0ca  jnz     short loc_18000A132
0x18000a0cc  call    cs:__imp_GetLastError
0x18000a0d3  nop     dword ptr [rax+rax+00h]
0x18000a0d8  mov     ebx, eax
0x18000a0da  mov     rdi, [rsp+4D8h]
0x18000a0e2  lea     rdx, aFailedToReadIn; "Failed to read in ContentsFile->FileVer"...
0x18000a0e9  mov     ecx, 300000Ch; unsigned int
0x18000a0ee  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000a0f3  mov     [rsp+4D8h+var_488], 0
0x18000a0fb  mov     [rsp+4D8h+var_490], 0
0x18000a104  mov     [rsp+4D8h+var_498], ebx
0x18000a108  mov     [rsp+4D8h+lpModuleName], rdi
0x18000a10d  lea     rcx, aPconstructcont; "pConstructContentsFile"
0x18000a114  mov     [rsp+4D8h+var_4A8], rcx
0x18000a119  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000a120  mov     [rsp+4D8h+var_4B0], rcx
0x18000a125  mov     [rsp+4D8h+var_4B8], 210h
0x18000a12d  jmp     loc_18000A095
0x18000a132  mov     r14, rsi
0x18000a135  xor     esi, esi
0x18000a137  mov     [rsp+4D8h+var_478], rsi
0x18000a13c  test    rsi, rsi
0x18000a13f  jz      short loc_18000A161
0x18000a141  call    cs:__imp_GetProcessHeap
0x18000a148  nop     dword ptr [rax+rax+00h]
0x18000a14d  mov     rcx, rax; hHeap
0x18000a150  mov     r8, rsi; lpMem
0x18000a153  xor     edx, edx; dwFlags
0x18000a155  call    cs:__imp_HeapFree
0x18000a15c  nop     dword ptr [rax+rax+00h]
0x18000a161  lea     rcx, [rsp+4D8h+var_468]
0x18000a166  call    OF_Close
0x18000a16b  mov     rax, r14
0x18000a16e  mov     rcx, [rsp+4D8h+var_38]
0x18000a176  xor     rcx, rsp; StackCookie
0x18000a179  call    __security_check_cookie
0x18000a17e  add     rsp, 4B8h
0x18000a185  pop     r14
0x18000a187  pop     rdi
0x18000a188  pop     rsi
0x18000a189  pop     rbx
0x18000a18a  retn
0x1800282c5  push    rbx
0x1800282c7  push    rbp
0x1800282c8  sub     rsp, 68h
0x1800282cc  mov     rbp, rdx
0x1800282cf  mov     rbx, [rbp+60h]
0x1800282d3  test    rbx, rbx
0x1800282d6  jz      short loc_1800282F9
0x1800282d8  call    cs:__imp_GetProcessHeap
0x1800282df  nop     dword ptr [rax+rax+00h]
0x1800282e4  mov     rcx, rax; hHeap
0x1800282e7  mov     r8, rbx; lpMem
0x1800282ea  xor     edx, edx; dwFlags
0x1800282ec  call    cs:__imp_HeapFree
0x1800282f3  nop     dword ptr [rax+rax+00h]
0x1800282f8  nop
0x1800282f9  lea     rcx, [rbp+70h]
0x1800282fd  call    OF_Close
0x180028302  nop
0x180028303  add     rsp, 68h
0x180028307  pop     rbp
0x180028308  pop     rbx
0x180028309  retn
```
