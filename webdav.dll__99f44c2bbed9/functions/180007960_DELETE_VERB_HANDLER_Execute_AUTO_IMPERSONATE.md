# DELETE_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x180007960`
- end: `0x180007ba9`
- name: `?Execute@DELETE_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180002e60`
- `0x1800033d4`
- `0x180003634`
- `0x1800036a4`
- `0x180003860`
- `0x1800056ac`
- `0x180005a5c`
- `0x180007710`
- `0x180007960`
- `0x180015204`
- `0x180020614`
- `0x1800206ec`
- `0x180021248`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000799d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000799d`

## pseudocode

```c
__int64 __fastcall DELETE_VERB_HANDLER::Execute(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  unsigned int ConstrainedDepth; // esi
  unsigned int v5; // edi
  int v7; // eax
  __int64 v8; // rcx
  struct IHttpServer *v9; // rdi
  int v10; // eax
  unsigned __int16 v11; // dx
  const char *v12; // r8
  DAV_BASE_HANDLER *v13; // rcx
  _BYTE v14[5008]; // [rsp+50h] [rbp-13C8h] BYREF

  LOCK_SET::LOCK_SET((LOCK_SET *)v14);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v2 = 1;
  XML_RESPONDER::Initialize(
    (XML_RESPONDER *)(a1 + 296),
    *(struct IHttpContext **)(a1 + 8),
    (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL) >> 2) & 1);
  v3 = *(_DWORD *)(a1 + 208);
  if ( v3 == -1 || (v3 & 0x10) == 0 )
    v2 = 0;
  ConstrainedDepth = GetConstrainedDepth(*(_QWORD *)(a1 + 8), v2);
  if ( ConstrainedDepth == -1 )
  {
    v5 = 2;
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0x190u, "Bad Request", 2u, 0);
LABEL_8:
    LOCK_SET::~LOCK_SET((LOCK_SET *)v14);
    return v5;
  }
  if ( !(unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                        (DAV_BASE_HANDLER *)a1,
                        *(struct IHttpFileInfo **)(a1 + 32)) )
    goto LABEL_14;
  v7 = HandleDavIfAndLocks(
         *(struct IHttpContext **)(a1 + 8),
         *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
         *(const unsigned __int16 **)(a1 + 72),
         (struct LOCK_SET *)v14,
         *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
         0,
         0,
         0,
         3u);
  if ( v7 < 0 )
  {
LABEL_13:
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v7);
    goto LABEL_14;
  }
  if ( (unsigned int)LOCK_SET::TestLocks((LOCK_SET *)v14) )
  {
    v8 = *(_QWORD *)(a1 + 32);
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      *(_QWORD *)(a1 + 32) = 0;
    }
    v9 = g_pGlobalInfo;
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
    v10 = DELETE_VERB_HANDLER::DoDelete(a1, ConstrainedDepth);
    if ( v10 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 392) )
      {
        if ( (int)XML_RESPONDER::FinishXmlMultistatusResponse((XML_RESPONDER *)(a1 + 296)) < 0 )
        {
          v11 = 500;
          v12 = "Internal Server Error";
          v13 = (DAV_BASE_HANDLER *)a1;
          goto LABEL_25;
        }
      }
      else
      {
        DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0xC8u, "OK", 0, 0);
      }
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v9 + 32LL))(v9);
      v5 = 0;
      goto LABEL_8;
    }
    v13 = (DAV_BASE_HANDLER *)a1;
    if ( v10 != -2147024893 )
    {
      DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v10);
      goto LABEL_27;
    }
    v11 = 409;
    v12 = "Conflict";
LABEL_25:
    DAV_BASE_HANDLER::FinishRequest(v13, v11, v12, 0, 0);
LABEL_27:
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)v9 + 32LL))(v9);
    v5 = 2;
    goto LABEL_8;
  }
  v7 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, (struct LOCK_SET *)v14);
  if ( v7 < 0 )
    goto LABEL_13;
LABEL_14:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v14);
  return 2;
}

```

## disassembly

```asm
0x180007960  push    rbx
0x180007962  push    rbp
0x180007963  push    rsi
0x180007964  push    rdi
0x180007965  mov     eax, 13F8h
0x18000796a  call    _alloca_probe
0x18000796f  sub     rsp, rax
0x180007972  mov     rax, cs:__security_cookie
0x180007979  xor     rax, rsp
0x18000797c  mov     [rsp+1418h+var_38], rax
0x180007984  mov     rbx, rcx
0x180007987  lea     rcx, [rsp+1418h+var_13C8]; this
0x18000798c  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x180007991  test    cs:g_dwDebugFlags, 40000000h
0x18000799b  jz      short loc_1800079A3
0x18000799d  call    cs:__imp_DebugBreak
0x1800079a3  mov     rax, [rbx+18h]
0x1800079a7  lea     rbp, [rbx+128h]
0x1800079ae  mov     rdx, [rbx+8]; struct IHttpContext *
0x1800079b2  mov     edi, 1
0x1800079b7  mov     rcx, rbp; this
0x1800079ba  mov     r8d, [rax+8]
0x1800079be  shr     r8d, 2
0x1800079c2  and     r8d, edi; int
0x1800079c5  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x1800079ca  mov     eax, [rbx+0D0h]
0x1800079d0  cmp     eax, 0FFFFFFFFh
0x1800079d3  jz      short loc_1800079D9
0x1800079d5  test    al, 10h
0x1800079d7  jnz     short loc_1800079DB
0x1800079d9  xor     edi, edi
0x1800079db  mov     rcx, [rbx+8]
0x1800079df  mov     edx, edi
0x1800079e1  call    ?GetConstrainedDepth@@YA?AW4DAV_DEPTH@@PEAVIHttpContext@@H@Z; GetConstrainedDepth(IHttpContext *,int)
0x1800079e6  mov     esi, eax
0x1800079e8  mov     rcx, rbx; this
0x1800079eb  cmp     eax, 0FFFFFFFFh
0x1800079ee  jnz     short loc_180007A20
0x1800079f0  lea     edi, [rax+3]
0x1800079f3  mov     [rsp+1418h+var_13F8], 0; int
0x1800079fb  mov     r9d, edi; unsigned __int16
0x1800079fe  lea     r8, aBadRequest; "Bad Request"
0x180007a05  mov     edx, 190h; unsigned __int16
0x180007a0a  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x180007a0f  lea     rcx, [rsp+1418h+var_13C8]; this
0x180007a14  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x180007a19  mov     eax, edi
0x180007a1b  jmp     loc_180007AAF
0x180007a20  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x180007a24  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x180007a29  test    eax, eax
0x180007a2b  jz      short loc_180007AA0
0x180007a2d  mov     rdx, [rbx+18h]
0x180007a31  lea     r9, [rsp+1418h+var_13C8]; struct LOCK_SET *
0x180007a36  mov     r8, [rbx+48h]; unsigned __int16 *
0x180007a3a  mov     rcx, [rbx+8]; struct IHttpContext *
0x180007a3e  mov     [rsp+1418h+var_13D8], 3; unsigned int
0x180007a46  mov     eax, [rdx+38h]
0x180007a49  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x180007a50  mov     [rsp+1418h+var_13E0], 0; int
0x180007a58  mov     [rsp+1418h+var_13E8], 0; struct LOCK_SET *
0x180007a61  mov     [rsp+1418h+var_13F0], 0; unsigned __int16 *
0x180007a6a  mov     [rsp+1418h+var_13F8], eax; int
0x180007a6e  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x180007a73  test    eax, eax
0x180007a75  js      short loc_180007A96
0x180007a77  lea     rcx, [rsp+1418h+var_13C8]; this
0x180007a7c  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x180007a81  test    eax, eax
0x180007a83  jnz     short loc_180007ACB
0x180007a85  lea     rdx, [rsp+1418h+var_13C8]; struct LOCK_SET *
0x180007a8a  mov     rcx, rbx; this
0x180007a8d  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x180007a92  test    eax, eax
0x180007a94  jns     short loc_180007AA0
0x180007a96  mov     edx, eax; int
0x180007a98  mov     rcx, rbx; this
0x180007a9b  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x180007aa0  lea     rcx, [rsp+1418h+var_13C8]; this
0x180007aa5  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x180007aaa  mov     eax, 2
0x180007aaf  mov     rcx, [rsp+1418h+var_38]
0x180007ab7  xor     rcx, rsp; StackCookie
0x180007aba  call    __security_check_cookie
0x180007abf  add     rsp, 13F8h
0x180007ac6  pop     rdi
0x180007ac7  pop     rsi
0x180007ac8  pop     rbp
0x180007ac9  pop     rbx
0x180007aca  retn
0x180007acb  mov     rcx, [rbx+20h]
0x180007acf  test    rcx, rcx
0x180007ad2  jz      short loc_180007AE8
0x180007ad4  mov     rax, [rcx]
0x180007ad7  mov     rax, [rax+10h]
0x180007adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae0  mov     qword ptr [rbx+20h], 0
0x180007ae8  mov     rdi, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180007aef  mov     rcx, rdi
0x180007af2  mov     rax, [rdi]
0x180007af5  mov     rax, [rax+18h]
0x180007af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afe  mov     edx, esi
0x180007b00  mov     rcx, rbx
0x180007b03  call    ?DoDelete@DELETE_VERB_HANDLER@@AEAAJW4DAV_DEPTH@@@Z; DELETE_VERB_HANDLER::DoDelete(DAV_DEPTH)
0x180007b08  test    eax, eax
0x180007b0a  js      short loc_180007B64
0x180007b0c  cmp     dword ptr [rbx+188h], 0
0x180007b13  jz      short loc_180007B32
0x180007b15  mov     rcx, rbp; this
0x180007b18  call    ?FinishXmlMultistatusResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlMultistatusResponse(void)
0x180007b1d  test    eax, eax
0x180007b1f  jns     short loc_180007B4E
0x180007b21  mov     edx, 1F4h
0x180007b26  lea     r8, aInternalServer; "Internal Server Error"
0x180007b2d  mov     rcx, rbx
0x180007b30  jmp     short loc_180007B7A
0x180007b32  xor     r9d, r9d; unsigned __int16
0x180007b35  lea     r8, aOk; "OK"
0x180007b3c  mov     edx, 0C8h; unsigned __int16
0x180007b41  mov     [rsp+1418h+var_13F8], r9d; int
0x180007b46  mov     rcx, rbx; this
0x180007b49  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x180007b4e  mov     rax, [rdi]
0x180007b51  mov     rcx, rdi
0x180007b54  mov     rax, [rax+20h]
0x180007b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b5d  xor     edi, edi
0x180007b5f  jmp     loc_180007A0F
0x180007b64  mov     rcx, rbx; this
0x180007b67  cmp     eax, 80070003h
0x180007b6c  jnz     short loc_180007B89
0x180007b6e  mov     edx, 199h; unsigned __int16
0x180007b73  lea     r8, aConflict; "Conflict"
0x180007b7a  xor     r9d, r9d; unsigned __int16
0x180007b7d  mov     [rsp+1418h+var_13F8], r9d; int
0x180007b82  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x180007b87  jmp     short loc_180007B90
0x180007b89  mov     edx, eax; int
0x180007b8b  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x180007b90  mov     rax, [rdi]
0x180007b93  mov     rcx, rdi
0x180007b96  mov     rax, [rax+20h]
0x180007b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9f  mov     edi, 2
0x180007ba4  jmp     loc_180007A0F
```
