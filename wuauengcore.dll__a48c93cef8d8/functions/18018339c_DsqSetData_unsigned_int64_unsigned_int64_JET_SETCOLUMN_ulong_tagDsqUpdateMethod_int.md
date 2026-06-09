# DsqSetData(unsigned __int64,unsigned __int64,JET_SETCOLUMN *,ulong,tagDsqUpdateMethod,int)

- ea: `0x18018339c`
- end: `0x18018363b`
- name: `?DsqSetData@@YAJ_K0PEAUJET_SETCOLUMN@@KW4tagDsqUpdateMethod@@H@Z`
- size: `671`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `37`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180177c4c`
- `0x1801783ec`
- `0x18018045c`
- `0x180180f98`
- `0x180181bb4`
- `0x180182258`
- `0x1801859b4`
- `0x180187728`
- `0x1801893ec`
- `0x18018b7d0`
- `0x18018bd0c`
- `0x18018ca18`
- `0x1801912b0`
- `0x180191cac`
- `0x1801922ac`
- `0x180193060`
- `0x180193b8c`
- `0x180196be8`
- `0x18019d53c`
- `0x18019d5fc`
- `0x18019dd8c`
- `0x18019e090`
- `0x18019eba8`
- `0x1801a0820`
- `0x1801a1c0c`
- `0x1801a1f1c`
- `0x1801a2688`
- `0x1801a2e30`
- `0x1801a3480`
- `0x1801a393c`
- `0x1801a3d6c`
- `0x1801a3f50`
- `0x1801a5774`
- `0x1801a6cc0`
- `0x1801a8058`
- `0x1801a8a70`
- `0x1801a94c0`

## callees

- `0x18012b618`
- `0x18018339c`
- `0x1801853f0`
- `0x180238960`

## import_xrefs

- `ESENT!JetUpdate` at `0x1801834df`
- `ESENT!JetUpdate` at `0x1801834df`
- `ESENT!JetSetColumns` at `0x1801834a5`
- `ESENT!JetSetColumns` at `0x1801834a5`
- `ESENT!JetPrepareUpdate` at `0x180183452`
- `ESENT!JetPrepareUpdate` at `0x180183478`
- `ESENT!JetPrepareUpdate` at `0x180183557`
- `ESENT!JetPrepareUpdate` at `0x180183452`
- `ESENT!JetPrepareUpdate` at `0x180183478`
- `ESENT!JetPrepareUpdate` at `0x180183557`
- `ESENT!JetGotoBookmark` at `0x18018357d`
- `ESENT!JetGotoBookmark` at `0x1801835c5`
- `ESENT!JetGotoBookmark` at `0x18018357d`
- `ESENT!JetGotoBookmark` at `0x1801835c5`
- `ESENT!JetDelete` at `0x18018358d`
- `ESENT!JetDelete` at `0x18018358d`
- `ESENT!JetGetBookmark` at `0x180183417`
- `ESENT!JetGetBookmark` at `0x180183417`

## string_xrefs

- `0x180183512`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`
- `0x1801835e4`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`
- `0x18018348b`: `JetPrepareUpdate`
- `0x1801835a0`: `JetDelete`
- `0x180183506`: `JetUpdate`

## pseudocode

```c
__int64 __fastcall DsqSetData(JET_SESID a1, JET_TABLEID a2, JET_SETCOLUMN *a3, unsigned int a4, int a5, int a6)
{
  JET_TABLEID v8; // rsi
  unsigned int v9; // ebp
  int v10; // r12d
  JET_ERR v11; // ecx
  JET_ERR Bookmark; // eax
  unsigned int v13; // r8d
  const char *v14; // rax
  JET_ERR v15; // eax
  unsigned int v16; // eax
  const char *v17; // rdx
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  unsigned int cbBookmark; // [rsp+54h] [rbp-264h] BYREF
  unsigned int pcbActual; // [rsp+58h] [rbp-260h] BYREF
  _BYTE pvBookmark[256]; // [rsp+60h] [rbp-258h] BYREF
  _BYTE v26[256]; // [rsp+160h] [rbp-158h] BYREF

  pcbActual = 0;
  v8 = a2;
  cbBookmark = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1603;
  if ( (unsigned int)(a5 - 1) <= 1 )
  {
    v13 = 2;
  }
  else
  {
    if ( a5 != 3 )
      goto LABEL_9;
    Bookmark = JetGetBookmark(a1, a2, pvBookmark, 0x100u, &cbBookmark);
    if ( Bookmark )
    {
      if ( Bookmark != -1603 )
      {
        v9 = JETErrToHRESULTAndAttemptRecovery(Bookmark);
        v14 = "JetGetBookmark";
LABEL_30:
        WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix", v9, v14, a1, v8);
        return v9;
      }
      goto LABEL_11;
    }
    v10 = 1;
    v13 = 5;
    a2 = v8;
  }
  v11 = JetPrepareUpdate(a1, a2, v13);
  if ( v11 != -1603 )
    goto LABEL_12;
LABEL_9:
  if ( (a5 & 0xFFFFFFFC) == 0 && a5 != 1 )
LABEL_11:
    v11 = JetPrepareUpdate(a1, v8, 0);
LABEL_12:
  if ( v11 )
  {
    v9 = JETErrToHRESULTAndAttemptRecovery(v11);
    v14 = "JetPrepareUpdate";
    goto LABEL_30;
  }
  v15 = JetSetColumns(a1, v8, a3, a4);
  if ( v15 )
  {
    v16 = JETErrToHRESULTAndAttemptRecovery(v15);
    v9 = v16;
    v17 = "JetSetColumns";
LABEL_21:
    WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix", v16, v17, a1, v8);
    JetPrepareUpdate(a1, v8, 3u);
    return v9;
  }
  v18 = JetUpdate(a1, v8, v26, 0x100u, &pcbActual);
  if ( v18 )
  {
    if ( (unsigned int)(v18 + 1605) <= 1 )
      v9 = -2145091570;
    else
      v9 = JETErrToHRESULTAndAttemptRecovery(v18);
    v16 = v9;
    v17 = "JetUpdate";
    goto LABEL_21;
  }
  if ( a5 == 3 && v10 )
  {
    v19 = JetGotoBookmark(a1, v8, pvBookmark, cbBookmark);
    if ( v19 )
    {
LABEL_29:
      v9 = JETErrToHRESULTAndAttemptRecovery(v19);
      v14 = "JetGotoBookmark";
      goto LABEL_30;
    }
    v20 = JetDelete(a1, v8);
    if ( v20 )
    {
      v9 = JETErrToHRESULTAndAttemptRecovery(v20);
      v14 = "JetDelete";
      goto LABEL_30;
    }
  }
  if ( a6 )
  {
    v19 = JetGotoBookmark(a1, v8, v26, pcbActual);
    if ( v19 )
      goto LABEL_29;
  }
  return v9;
}

```

## disassembly

```asm
0x18018339c  push    rbx
0x18018339e  push    rbp
0x18018339f  push    rsi
0x1801833a0  push    rdi
0x1801833a1  push    r12
0x1801833a3  push    r13
0x1801833a5  push    r14
0x1801833a7  push    r15
0x1801833a9  sub     rsp, 278h
0x1801833b0  mov     rax, cs:__security_cookie
0x1801833b7  xor     rax, rsp
0x1801833ba  mov     [rsp+2B8h+var_58], rax
0x1801833c2  mov     r15d, [rsp+2B8h+arg_20]
0x1801833ca  xor     ebx, ebx
0x1801833cc  mov     rdi, rcx
0x1801833cf  mov     [rsp+2B8h+csetcolumn], r9d
0x1801833d4  mov     r13, r8
0x1801833d7  mov     [rsp+2B8h+var_260], ebx
0x1801833db  mov     rsi, rdx
0x1801833de  mov     [rsp+2B8h+cbBookmark], ebx
0x1801833e2  lea     eax, [r15-1]
0x1801833e6  mov     ebp, ebx
0x1801833e8  lea     r14d, [rbx+1]
0x1801833ec  mov     r12d, ebx
0x1801833ef  mov     ecx, 0FFFFF9BDh
0x1801833f4  cmp     eax, r14d
0x1801833f7  jbe     short loc_180183449
0x1801833f9  cmp     r15d, 3
0x1801833fd  jnz     short loc_180183461
0x1801833ff  lea     rax, [rsp+2B8h+cbBookmark]
0x180183404  mov     r9d, 100h; cbMax
0x18018340a  lea     r8, [rsp+2B8h+pvBookmark]; pvBookmark
0x18018340f  mov     [rsp+2B8h+pcbActual], rax; pcbActual
0x180183414  mov     rcx, rdi; sesid
0x180183417  call    cs:__imp_JetGetBookmark
0x18018341d  test    eax, eax
0x18018341f  jnz     short loc_18018342D
0x180183421  mov     r12d, r14d
0x180183424  lea     r8d, [rbx+5]
0x180183428  mov     rdx, rsi
0x18018342b  jmp     short loc_18018344F
0x18018342d  cmp     eax, 0FFFFF9BDh
0x180183432  jz      short loc_18018346F
0x180183434  mov     ecx, eax; int
0x180183436  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18018343b  mov     ebp, eax
0x18018343d  lea     rax, aJetgetbookmark_0; "JetGetBookmark"
0x180183444  jmp     loc_1801835DF
0x180183449  mov     r8d, 2; prep
0x18018344f  mov     rcx, rdi; sesid
0x180183452  call    cs:__imp_JetPrepareUpdate
0x180183458  mov     ecx, eax
0x18018345a  cmp     eax, 0FFFFF9BDh
0x18018345f  jnz     short loc_180183480
0x180183461  test    r15d, 0FFFFFFFCh
0x180183468  jnz     short loc_180183480
0x18018346a  cmp     r15d, r14d
0x18018346d  jz      short loc_180183480
0x18018346f  xor     r8d, r8d; prep
0x180183472  mov     rdx, rsi; tableid
0x180183475  mov     rcx, rdi; sesid
0x180183478  call    cs:__imp_JetPrepareUpdate
0x18018347e  mov     ecx, eax; int
0x180183480  test    ecx, ecx
0x180183482  jz      short loc_180183497
0x180183484  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x180183489  mov     ebp, eax
0x18018348b  lea     rax, aJetprepareupda_0; "JetPrepareUpdate"
0x180183492  jmp     loc_1801835DF
0x180183497  mov     r9d, [rsp+2B8h+csetcolumn]; csetcolumn
0x18018349c  mov     r8, r13; psetcolumn
0x18018349f  mov     rdx, rsi; tableid
0x1801834a2  mov     rcx, rdi; sesid
0x1801834a5  call    cs:__imp_JetSetColumns
0x1801834ab  test    eax, eax
0x1801834ad  jz      short loc_1801834C1
0x1801834af  mov     ecx, eax; int
0x1801834b1  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x1801834b6  mov     ebp, eax
0x1801834b8  lea     rdx, aJetsetcolumns_0; "JetSetColumns"
0x1801834bf  jmp     short loc_18018350D
0x1801834c1  lea     rax, [rsp+2B8h+var_260]
0x1801834c6  mov     r9d, 100h; cbBookmark
0x1801834cc  lea     r8, [rsp+2B8h+var_158]; pvBookmark
0x1801834d4  mov     [rsp+2B8h+pcbActual], rax; pcbActual
0x1801834d9  mov     rdx, rsi; tableid
0x1801834dc  mov     rcx, rdi; sesid
0x1801834df  call    cs:__imp_JetUpdate
0x1801834e5  test    eax, eax
0x1801834e7  jz      short loc_180183562
0x1801834e9  lea     ecx, [rax+645h]
0x1801834ef  cmp     ecx, r14d
0x1801834f2  jbe     short loc_1801834FF
0x1801834f4  mov     ecx, eax; int
0x1801834f6  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x1801834fb  mov     ebp, eax
0x1801834fd  jmp     short loc_180183504
0x1801834ff  mov     ebp, 8024800Eh
0x180183504  mov     eax, ebp
0x180183506  lea     rdx, aJetupdate_0; "JetUpdate"
0x18018350d  mov     [rsp+2B8h+var_270], rsi
0x180183512  lea     rcx, aDs0x08xHsFaile_0; "DS: 0x%08x: %hs failed. sesid: %Ix. tab"...
0x180183519  mov     [rsp+2B8h+var_278], rdi
0x18018351e  mov     r9, rdi
0x180183521  mov     [rsp+2B8h+var_280], rdx
0x180183526  mov     r10, rsi
0x180183529  mov     [rsp+2B8h+var_288], eax
0x18018352d  mov     r8d, 2000h
0x180183533  mov     [rsp+2B8h+var_290], rcx
0x180183538  mov     r9d, r14d
0x18018353b  mov     rcx, rbx
0x18018353e  mov     [rsp+2B8h+pcbActual], rbx
0x180183543  mov     rdx, rbx
0x180183546  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18018354b  mov     r8d, 3; prep
0x180183551  mov     rdx, rsi; tableid
0x180183554  mov     rcx, rdi; sesid
0x180183557  call    cs:__imp_JetPrepareUpdate
0x18018355d  jmp     loc_180183615
0x180183562  cmp     r15d, 3
0x180183566  jnz     short loc_1801835A9
0x180183568  test    r12d, r12d
0x18018356b  jz      short loc_1801835A9
0x18018356d  mov     r9d, [rsp+2B8h+cbBookmark]; cbBookmark
0x180183572  lea     r8, [rsp+2B8h+pvBookmark]; pvBookmark
0x180183577  mov     rdx, rsi; tableid
0x18018357a  mov     rcx, rdi; sesid
0x18018357d  call    cs:__imp_JetGotoBookmark
0x180183583  test    eax, eax
0x180183585  jnz     short loc_1801835CF
0x180183587  mov     rdx, rsi; tableid
0x18018358a  mov     rcx, rdi; sesid
0x18018358d  call    cs:__imp_JetDelete
0x180183593  test    eax, eax
0x180183595  jz      short loc_1801835A9
0x180183597  mov     ecx, eax; int
0x180183599  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18018359e  mov     ebp, eax
0x1801835a0  lea     rax, aJetdelete_0; "JetDelete"
0x1801835a7  jmp     short loc_1801835DF
0x1801835a9  cmp     [rsp+2B8h+arg_28], ebx
0x1801835b0  jz      short loc_180183615
0x1801835b2  mov     r9d, [rsp+2B8h+var_260]; cbBookmark
0x1801835b7  lea     r8, [rsp+2B8h+var_158]; pvBookmark
0x1801835bf  mov     rdx, rsi; tableid
0x1801835c2  mov     rcx, rdi; sesid
0x1801835c5  call    cs:__imp_JetGotoBookmark
0x1801835cb  test    eax, eax
0x1801835cd  jz      short loc_180183615
0x1801835cf  mov     ecx, eax; int
0x1801835d1  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x1801835d6  mov     ebp, eax
0x1801835d8  lea     rax, aJetgotobookmar_0; "JetGotoBookmark"
0x1801835df  mov     [rsp+2B8h+var_270], rsi
0x1801835e4  lea     rcx, aDs0x08xHsFaile_0; "DS: 0x%08x: %hs failed. sesid: %Ix. tab"...
0x1801835eb  mov     [rsp+2B8h+var_278], rdi
0x1801835f0  mov     r9d, r14d
0x1801835f3  mov     [rsp+2B8h+var_280], rax
0x1801835f8  mov     r8d, 2000h
0x1801835fe  mov     [rsp+2B8h+var_288], ebp
0x180183602  xor     edx, edx
0x180183604  mov     [rsp+2B8h+var_290], rcx
0x180183609  xor     ecx, ecx
0x18018360b  mov     [rsp+2B8h+pcbActual], rbx
0x180183610  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180183615  mov     eax, ebp
0x180183617  mov     rcx, [rsp+2B8h+var_58]
0x18018361f  xor     rcx, rsp; StackCookie
0x180183622  call    __security_check_cookie
0x180183627  add     rsp, 278h
0x18018362e  pop     r15
0x180183630  pop     r14
0x180183632  pop     r13
0x180183634  pop     r12
0x180183636  pop     rdi
0x180183637  pop     rsi
0x180183638  pop     rbp
0x180183639  pop     rbx
0x18018363a  retn
```
