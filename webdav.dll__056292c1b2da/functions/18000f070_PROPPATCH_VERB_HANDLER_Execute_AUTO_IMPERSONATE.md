# PROPPATCH_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x18000f070`
- end: `0x18000f1f6`
- name: `?Execute@PROPPATCH_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180002e60`
- `0x180003634`
- `0x1800036a4`
- `0x180003860`
- `0x180005a5c`
- `0x18000f070`
- `0x18001dea0`
- `0x180020614`
- `0x1800206ec`
- `0x180021248`
- `0x180022520`
- `0x1800225b0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f0aa`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f0aa`

## pseudocode

```c
__int64 __fastcall PROPPATCH_VERB_HANDLER::Execute(__int64 a1)
{
  int v2; // eax
  __int64 v4; // rax
  unsigned int v5; // ebx
  _BYTE v6[5008]; // [rsp+50h] [rbp-13A8h] BYREF

  LOCK_SET::LOCK_SET((LOCK_SET *)v6);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  XML_RESPONDER::Initialize(
    (XML_RESPONDER *)(a1 + 448),
    *(struct IHttpContext **)(a1 + 8),
    (*(_DWORD *)(*(_QWORD *)(a1 + 24) + 8LL) >> 2) & 1);
  if ( !(unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                        (DAV_BASE_HANDLER *)a1,
                        *(struct IHttpFileInfo **)(a1 + 32)) )
    goto LABEL_7;
  v2 = HandleDavIfAndLocks(
         *(struct IHttpContext **)(a1 + 8),
         *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
         *(const unsigned __int16 **)(a1 + 72),
         (struct LOCK_SET *)v6,
         *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
         0,
         0,
         0,
         1u);
  if ( v2 < 0 )
    goto LABEL_9;
  if ( !(unsigned int)LOCK_SET::TestLocks((LOCK_SET *)v6) )
  {
    v2 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, (struct LOCK_SET *)v6);
    if ( v2 >= 0 )
    {
LABEL_7:
      LOCK_SET::~LOCK_SET((LOCK_SET *)v6);
      return 2;
    }
LABEL_9:
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v2);
    v5 = 2;
    goto LABEL_10;
  }
  v4 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)(a1 + 440) = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 12LL);
  *(_QWORD *)(a1 + 304) = v4;
  *(_QWORD *)(a1 + 312) = a1 + 432;
  *(_QWORD *)(a1 + 328) = a1 + 296;
  *(_DWORD *)(a1 + 336) = -1;
  *(_DWORD *)(a1 + 340) = -1;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_DWORD *)(a1 + 352) = 0;
  v5 = CAsyncReader::StartRead(a1 + 304);
LABEL_10:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v6);
  return v5;
}

```

## disassembly

```asm
0x18000f070  push    rbx
0x18000f072  mov     eax, 13F0h
0x18000f077  call    _alloca_probe
0x18000f07c  sub     rsp, rax
0x18000f07f  mov     rax, cs:__security_cookie
0x18000f086  xor     rax, rsp
0x18000f089  mov     [rsp+13F8h+var_18], rax
0x18000f091  mov     rbx, rcx
0x18000f094  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000f099  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000f09e  test    cs:g_dwDebugFlags, 40000000h
0x18000f0a8  jz      short loc_18000F0B0
0x18000f0aa  call    cs:__imp_DebugBreak
0x18000f0b0  mov     rax, [rbx+18h]
0x18000f0b4  lea     rcx, [rbx+1C0h]; this
0x18000f0bb  mov     rdx, [rbx+8]; struct IHttpContext *
0x18000f0bf  mov     r8d, [rax+8]
0x18000f0c3  shr     r8d, 2
0x18000f0c7  and     r8d, 1; int
0x18000f0cb  call    ?Initialize@XML_RESPONDER@@QEAAXPEAVIHttpContext@@H@Z; XML_RESPONDER::Initialize(IHttpContext *,int)
0x18000f0d0  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x18000f0d4  mov     rcx, rbx; this
0x18000f0d7  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x18000f0dc  test    eax, eax
0x18000f0de  jz      short loc_18000F151
0x18000f0e0  mov     rdx, [rbx+18h]
0x18000f0e4  lea     r9, [rsp+13F8h+var_13A8]; struct LOCK_SET *
0x18000f0e9  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000f0ed  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000f0f1  mov     [rsp+13F8h+var_13B8], 1; unsigned int
0x18000f0f9  mov     eax, [rdx+38h]
0x18000f0fc  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x18000f103  mov     [rsp+13F8h+var_13C0], 0; int
0x18000f10b  mov     [rsp+13F8h+var_13C8], 0; struct LOCK_SET *
0x18000f114  mov     [rsp+13F8h+var_13D0], 0; unsigned __int16 *
0x18000f11d  mov     [rsp+13F8h+var_13D8], eax; int
0x18000f121  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18000f126  test    eax, eax
0x18000f128  js      loc_18000F1D6
0x18000f12e  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000f133  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x18000f138  test    eax, eax
0x18000f13a  jnz     short loc_18000F179
0x18000f13c  lea     rdx, [rsp+13F8h+var_13A8]; struct LOCK_SET *
0x18000f141  mov     rcx, rbx; this
0x18000f144  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x18000f149  test    eax, eax
0x18000f14b  js      loc_18000F1D6
0x18000f151  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000f156  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000f15b  mov     eax, 2
0x18000f160  mov     rcx, [rsp+13F8h+var_18]
0x18000f168  xor     rcx, rsp; StackCookie
0x18000f16b  call    __security_check_cookie
0x18000f170  add     rsp, 13F0h
0x18000f177  pop     rbx
0x18000f178  retn
0x18000f179  mov     rax, [rbx+18h]
0x18000f17d  lea     rdx, [rbx+130h]
0x18000f184  mov     ecx, [rax+0Ch]
0x18000f187  mov     rax, [rbx+8]
0x18000f18b  mov     [rbx+1B8h], ecx
0x18000f191  lea     rcx, [rbx+128h]
0x18000f198  mov     [rdx], rax
0x18000f19b  lea     rax, [rbx+1B0h]
0x18000f1a2  mov     [rdx+8], rax
0x18000f1a6  or      eax, 0FFFFFFFFh
0x18000f1a9  mov     [rdx+18h], rcx
0x18000f1ad  mov     rcx, rdx
0x18000f1b0  mov     [rdx+20h], eax
0x18000f1b3  mov     [rdx+24h], eax
0x18000f1b6  mov     qword ptr [rdx+10h], 0
0x18000f1be  mov     qword ptr [rdx+28h], 0
0x18000f1c6  mov     dword ptr [rdx+30h], 0
0x18000f1cd  call    ?StartRead@CAsyncReader@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; CAsyncReader::StartRead(void)
0x18000f1d2  mov     ebx, eax
0x18000f1d4  jmp     short loc_18000F1E5
0x18000f1d6  mov     edx, eax; int
0x18000f1d8  mov     rcx, rbx; this
0x18000f1db  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000f1e0  mov     ebx, 2
0x18000f1e5  lea     rcx, [rsp+13F8h+var_13A8]; this
0x18000f1ea  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000f1ef  mov     eax, ebx
0x18000f1f1  jmp     loc_18000F160
```
