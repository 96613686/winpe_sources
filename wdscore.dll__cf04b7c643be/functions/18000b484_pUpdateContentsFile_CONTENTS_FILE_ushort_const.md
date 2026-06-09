# pUpdateContentsFile(CONTENTS_FILE *,ushort const *)

- ea: `0x18000b484`
- end: `0x18000b608`
- name: `?pUpdateContentsFile@@YAPEAUFILE_VERSION_LIST_ITEM@@PEAUCONTENTS_FILE@@PEBG@Z`
- size: `388`
- prototype: `struct FILE_VERSION_LIST_ITEM *(struct CONTENTS_FILE *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000b6c4`
- `0x18000b860`

## callees

- `0x180001ee8`
- `0x180002250`
- `0x180005e18`
- `0x180009e30`
- `0x18000a194`
- `0x18000a658`
- `0x18000b484`
- `0x18001dc70`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b54f`

## string_xrefs

- `0x18000b590`: `pUpdateContentsFile`
- `0x18000b565`: `pUpdateContentsFile StringCchPrintf failed`

## pseudocode

```c
struct FILE_VERSION_LIST_ITEM *__fastcall pUpdateContentsFile(struct CONTENTS_FILE *a1, const unsigned __int16 *a2)
{
  struct CONTENTS_FILE *v3; // rdi
  __int64 v4; // rsi
  struct FILE_VERSION_LIST_ITEM *EntryInContentsFile; // rax
  struct FILE_VERSION_LIST_ITEM *v6; // rbx
  char *v7; // r10
  struct FILE_VERSION_LIST_ITEM *v8; // rax
  int v9; // edi
  DWORD LastError; // ebx
  int *v11; // rax
  unsigned __int16 v13[264]; // [rsp+60h] [rbp-248h] BYREF
  LPCWSTR lpModuleName; // [rsp+2A8h] [rbp+0h]

  v3 = g_pContentsFile;
  v4 = 0;
  memset_0(v13, 0, 0x208u);
  EntryInContentsFile = pFindEntryInContentsFile(v3, a2);
  v6 = EntryInContentsFile;
  v7 = (char *)v3 + 8;
  if ( EntryInContentsFile )
  {
    v9 = *((_DWORD *)EntryInContentsFile + 272) + 1;
    if ( (int)StringCchPrintfW(
                v13,
                0x104u,
                L"%s\\%s%d.%s",
                v7,
                (char *)EntryInContentsFile + 568,
                v9,
                *((_QWORD *)EntryInContentsFile + 70)) >= 0 )
    {
      if ( StringCchCopyW((unsigned __int16 *)v6 + 20, 0x104u, v13) >= 0 )
      {
        *((_DWORD *)v6 + 272) = v9;
        return v6;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = (int *)ConstructPartialMsgW(0x300000Du, "pUpdateContentsFile StringCchPrintf failed");
      WdsSetupLogMessageW(
        v11,
        589824,
        (__int64)L"D",
        0,
        0x269u,
        L"onecore\\base\\ntsetup\\panther\\engine\\engine.cpp",
        L"pUpdateContentsFile",
        lpModuleName,
        LastError,
        0,
        0);
    }
  }
  else
  {
    v8 = pConstructFileVersion((const unsigned __int16 *)v3 + 4, a2, 0, L"que");
    v6 = v8;
    if ( v8 )
    {
      AddToTail(*(_QWORD *)v3, v8);
      return v6;
    }
  }
  return (struct FILE_VERSION_LIST_ITEM *)v4;
}

```

## disassembly

```asm
0x18000b484  push    rbx
0x18000b486  push    rsi
0x18000b487  push    rdi
0x18000b488  push    r14
0x18000b48a  sub     rsp, 288h
0x18000b491  mov     rax, cs:__security_cookie
0x18000b498  xor     rax, rsp
0x18000b49b  mov     [rsp+2A8h+var_38], rax
0x18000b4a3  mov     r14, rdx
0x18000b4a6  mov     rdi, cs:?g_pContentsFile@@3PEAUCONTENTS_FILE@@EA; CONTENTS_FILE * g_pContentsFile
0x18000b4ad  xor     esi, esi
0x18000b4af  xor     edx, edx; Val
0x18000b4b1  mov     r8d, 208h; Size
0x18000b4b7  lea     rcx, [rsp+2A8h+var_248]; void *
0x18000b4bc  call    memset_0
0x18000b4c1  nop
0x18000b4c2  mov     rdx, r14; unsigned __int16 *
0x18000b4c5  mov     rcx, rdi; struct CONTENTS_FILE *
0x18000b4c8  call    ?pFindEntryInContentsFile@@YAPEAUFILE_VERSION_LIST_ITEM@@PEAUCONTENTS_FILE@@PEBG@Z; pFindEntryInContentsFile(CONTENTS_FILE *,ushort const *)
0x18000b4cd  mov     rbx, rax
0x18000b4d0  lea     r10, [rdi+8]
0x18000b4d4  test    rax, rax
0x18000b4d7  jnz     short loc_18000B50A
0x18000b4d9  lea     r9, aQue; "que"
0x18000b4e0  xor     r8d, r8d; unsigned int
0x18000b4e3  mov     rdx, r14; unsigned __int16 *
0x18000b4e6  mov     rcx, r10; unsigned __int16 *
0x18000b4e9  call    ?pConstructFileVersion@@YAPEAUFILE_VERSION_LIST_ITEM@@PEBG0I0@Z; pConstructFileVersion(ushort const *,ushort const *,uint,ushort const *)
0x18000b4ee  mov     rbx, rax
0x18000b4f1  test    rax, rax
0x18000b4f4  jz      loc_18000B5E7
0x18000b4fa  mov     rdx, rax
0x18000b4fd  mov     rcx, [rdi]
0x18000b500  call    AddToTail
0x18000b505  jmp     loc_18000B5E4
0x18000b50a  mov     edi, [rax+440h]
0x18000b510  inc     edi
0x18000b512  lea     rcx, [rax+238h]
0x18000b519  mov     rax, [rax+230h]
0x18000b520  mov     [rsp+2A8h+var_278], rax
0x18000b525  mov     dword ptr [rsp+2A8h+var_280], edi
0x18000b529  mov     qword ptr [rsp+2A8h+var_288], rcx
0x18000b52e  mov     r9, r10
0x18000b531  lea     r8, aSSDS; "%s\\%s%d.%s"
0x18000b538  mov     r14d, 104h
0x18000b53e  mov     edx, r14d; unsigned __int64
0x18000b541  lea     rcx, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000b546  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b54b  test    eax, eax
0x18000b54d  jns     short loc_18000B5C9
0x18000b54f  call    cs:__imp_GetLastError
0x18000b556  nop     dword ptr [rax+rax+00h]
0x18000b55b  mov     ebx, eax
0x18000b55d  mov     rdi, [rsp+2A8h]
0x18000b565  lea     rdx, aPupdatecontent_0; "pUpdateContentsFile StringCchPrintf fai"...
0x18000b56c  mov     ecx, 300000Dh; unsigned int
0x18000b571  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000b576  mov     [rsp+2A8h+var_258], 0; int
0x18000b57e  mov     [rsp+2A8h+var_260], 0; __int64
0x18000b587  mov     [rsp+2A8h+var_268], ebx; int
0x18000b58b  mov     [rsp+2A8h+lpModuleName], rdi; lpModuleName
0x18000b590  lea     rcx, aPupdatecontent; "pUpdateContentsFile"
0x18000b597  mov     [rsp+2A8h+var_278], rcx; __int64
0x18000b59c  lea     rcx, aOnecoreBaseNts_1; "onecore\\base\\ntsetup\\panther\\engine"...
0x18000b5a3  mov     [rsp+2A8h+var_280], rcx; unsigned __int16 *
0x18000b5a8  mov     [rsp+2A8h+var_288], 269h; int
0x18000b5b0  xor     r9d, r9d; int
0x18000b5b3  lea     r8, aD_1; "D"
0x18000b5ba  mov     edx, 90000h; int
0x18000b5bf  mov     rcx, rax; int
0x18000b5c2  call    WdsSetupLogMessageW
0x18000b5c7  jmp     short loc_18000B5E7
0x18000b5c9  lea     rcx, [rbx+28h]; unsigned __int16 *
0x18000b5cd  lea     r8, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000b5d2  mov     rdx, r14; unsigned __int64
0x18000b5d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b5da  test    eax, eax
0x18000b5dc  js      short loc_18000B5E7
0x18000b5de  mov     [rbx+440h], edi
0x18000b5e4  mov     rsi, rbx
0x18000b5e7  mov     rax, rsi
0x18000b5ea  mov     rcx, [rsp+2A8h+var_38]
0x18000b5f2  xor     rcx, rsp; StackCookie
0x18000b5f5  call    __security_check_cookie
0x18000b5fa  add     rsp, 288h
0x18000b601  pop     r14
0x18000b603  pop     rdi
0x18000b604  pop     rsi
0x18000b605  pop     rbx
0x18000b606  retn
0x180027ab6  push    rbp
0x180027ab8  sub     rsp, 60h
0x180027abc  mov     rbp, rdx
0x180027abf  add     rsp, 60h
0x180027ac3  pop     rbp
0x180027ac4  retn
```
