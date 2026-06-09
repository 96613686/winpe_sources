# UNLOCK_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x180010f50`
- end: `0x18001113e`
- name: `?Execute@UNLOCK_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x180003860`
- `0x180005a5c`
- `0x180007294`
- `0x180010f50`
- `0x18001a0cc`
- `0x180020614`
- `0x1800206ec`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180010f9e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180010f9e`
- `iisutil!PuDbgPrint` at `0x1800110da`
- `iisutil!PuDbgPrint` at `0x1800110da`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010f83`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010f83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011118`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011118`

## string_xrefs

- `0x1800110ce`: `Lock token %ws released\n`

## pseudocode

```c
__int64 __fastcall UNLOCK_VERB_HANDLER::Execute(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  int v4; // eax
  __int64 v5; // rbx
  const unsigned __int16 *EffectiveUser; // rax
  unsigned __int16 v7; // dx
  const char *v8; // r8
  _BYTE v10[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+70h] [rbp-90h]
  _BYTE v12[5008]; // [rsp+90h] [rbp-70h] BYREF

  STRU::STRU((STRU *)v10);
  LOCK_SET::LOCK_SET((LOCK_SET *)v12);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v2 = *(_QWORD *)(a1 + 24);
  if ( !*(_DWORD *)(v2 + 52) || (v3 = *(_QWORD *)(v2 + 3328), !*(_DWORD *)(v3 + 28)) )
  {
    v7 = 501;
    v8 = "Not Implemented";
    goto LABEL_15;
  }
  if ( (int)ValidateLockTokenHeader(*(struct IHttpContext **)(a1 + 8), (struct STRU *)v10) >= 0 )
  {
    if ( !(unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                          (DAV_BASE_HANDLER *)a1,
                          *(struct IHttpFileInfo **)(a1 + 32)) )
      goto LABEL_16;
    v4 = HandleDavIfAndLocks(
           *(struct IHttpContext **)(a1 + 8),
           *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
           *(const unsigned __int16 **)(a1 + 72),
           (struct LOCK_SET *)v12,
           0,
           0,
           0,
           0,
           3u);
    if ( v4 < 0
      || (v5 = v11,
          EffectiveUser = GetEffectiveUser(*(struct IHttpContext **)(a1 + 8)),
          v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, __int64))(**(_QWORD **)(v3 + 16)
                                                                                             + 56LL))(
                 *(_QWORD *)(v3 + 16),
                 a1 + 248,
                 EffectiveUser,
                 v5),
          v4 < 0) )
    {
      DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v4);
      goto LABEL_16;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\iis70\\webdav\\module\\src\\unlock_verb_handler.cxx",
        111,
        "UNLOCK_VERB_HANDLER::Execute",
        "Lock token %ws released\n",
        v11);
    v7 = 204;
    v8 = "No Content";
LABEL_15:
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, v7, v8, 0, 0);
    goto LABEL_16;
  }
  DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0x190u, "Bad Request", 9u, 0);
LABEL_16:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v12);
  STRU::~STRU((STRU *)v10);
  return 2;
}

```

## disassembly

```asm
0x180010f50  push    rbp
0x180010f52  push    rbx
0x180010f53  push    rsi
0x180010f54  push    rdi
0x180010f55  lea     rbp, [rsp-1338h]
0x180010f5d  mov     eax, 1438h
0x180010f62  call    _alloca_probe
0x180010f67  sub     rsp, rax
0x180010f6a  mov     rax, cs:__security_cookie
0x180010f71  xor     rax, rsp
0x180010f74  mov     [rbp+1350h+var_30], rax
0x180010f7b  mov     rdi, rcx
0x180010f7e  lea     rcx, [rsp+1450h+var_1400]
0x180010f83  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010f89  lea     rcx, [rbp+1350h+var_13C0]; this
0x180010f8d  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x180010f92  test    cs:g_dwDebugFlags, 40000000h
0x180010f9c  jz      short loc_180010FA4
0x180010f9e  call    cs:__imp_DebugBreak
0x180010fa4  mov     rax, [rdi+18h]
0x180010fa8  cmp     dword ptr [rax+34h], 0
0x180010fac  jz      loc_1800110EE
0x180010fb2  mov     rsi, [rax+0D00h]
0x180010fb9  cmp     dword ptr [rsi+1Ch], 0
0x180010fbd  jz      loc_1800110EE
0x180010fc3  mov     rcx, [rdi+8]; struct IHttpContext *
0x180010fc7  lea     rdx, [rsp+1450h+var_1400]; struct STRU *
0x180010fcc  call    ?ValidateLockTokenHeader@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z; ValidateLockTokenHeader(IHttpContext *,STRU *)
0x180010fd1  mov     rcx, rdi; this
0x180010fd4  test    eax, eax
0x180010fd6  jns     short loc_180010FF7
0x180010fd8  mov     edx, 190h
0x180010fdd  mov     [rsp+1450h+var_1430], 0
0x180010fe5  mov     r9d, 9
0x180010feb  lea     r8, aBadRequest; "Bad Request"
0x180010ff2  jmp     loc_180011105
0x180010ff7  mov     rdx, [rdi+20h]; struct IHttpFileInfo *
0x180010ffb  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x180011000  test    eax, eax
0x180011002  jz      loc_18001110A
0x180011008  mov     rdx, [rdi+18h]
0x18001100c  lea     r9, [rbp+1350h+var_13C0]; struct LOCK_SET *
0x180011010  mov     r8, [rdi+48h]; unsigned __int16 *
0x180011014  mov     rcx, [rdi+8]; struct IHttpContext *
0x180011018  mov     [rsp+1450h+var_1410], 3; unsigned int
0x180011020  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x180011027  mov     [rsp+1450h+var_1418], 0; int
0x18001102f  mov     [rsp+1450h+var_1420], 0; struct LOCK_SET *
0x180011038  mov     [rsp+1450h+var_1428], 0; unsigned __int16 *
0x180011041  mov     [rsp+1450h+var_1430], 0; int
0x180011049  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18001104e  test    eax, eax
0x180011050  jns     short loc_180011061
0x180011052  mov     edx, eax; int
0x180011054  mov     rcx, rdi; this
0x180011057  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18001105c  jmp     loc_18001110A
0x180011061  mov     rcx, [rdi+8]; struct IHttpContext *
0x180011065  mov     rbx, [rsp+1450h+var_13E0]
0x18001106a  call    ?GetEffectiveUser@@YAPEBGPEAVIHttpContext@@@Z; GetEffectiveUser(IHttpContext *)
0x18001106f  mov     rcx, [rsi+10h]
0x180011073  lea     rdx, [rdi+0F8h]
0x18001107a  mov     r10, rax
0x18001107d  mov     r9, rbx
0x180011080  mov     r8, [rcx]
0x180011083  mov     rax, [r8+38h]
0x180011087  mov     r8, r10
0x18001108a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001108f  test    eax, eax
0x180011091  js      short loc_180011052
0x180011093  mov     eax, cs:g_dwDebugFlags
0x180011099  test    al, 3
0x18001109b  setnz   cl
0x18001109e  bt      eax, 15h
0x1800110a2  setb    al
0x1800110a5  test    al, cl
0x1800110a7  jz      short loc_1800110E0
0x1800110a9  mov     rax, [rsp+1450h+var_13E0]
0x1800110ae  lea     r9, aUnlockVerbHand; "UNLOCK_VERB_HANDLER::Execute"
0x1800110b5  mov     rcx, cs:g_pDebug
0x1800110bc  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\iis70\\webdav\\"...
0x1800110c3  mov     [rsp+1450h+var_1428], rax
0x1800110c8  mov     r8d, 6Fh ; 'o'
0x1800110ce  lea     rax, aLockTokenWsRel; "Lock token %ws released\n"
0x1800110d5  mov     qword ptr [rsp+1450h+var_1430], rax
0x1800110da  call    cs:__imp_PuDbgPrint
0x1800110e0  mov     edx, 0CCh
0x1800110e5  lea     r8, aNoContent; "No Content"
0x1800110ec  jmp     short loc_1800110FA
0x1800110ee  mov     edx, 1F5h; unsigned __int16
0x1800110f3  lea     r8, aNotImplemented; "Not Implemented"
0x1800110fa  xor     r9d, r9d; unsigned __int16
0x1800110fd  mov     rcx, rdi; this
0x180011100  mov     [rsp+1450h+var_1430], r9d; int
0x180011105  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18001110a  lea     rcx, [rbp+1350h+var_13C0]; this
0x18001110e  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x180011113  lea     rcx, [rsp+1450h+var_1400]
0x180011118  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001111e  mov     eax, 2
0x180011123  mov     rcx, [rbp+1350h+var_30]
0x18001112a  xor     rcx, rsp; StackCookie
0x18001112d  call    __security_check_cookie
0x180011132  add     rsp, 1438h
0x180011139  pop     rdi
0x18001113a  pop     rsi
0x18001113b  pop     rbx
0x18001113c  pop     rbp
0x18001113d  retn
```
