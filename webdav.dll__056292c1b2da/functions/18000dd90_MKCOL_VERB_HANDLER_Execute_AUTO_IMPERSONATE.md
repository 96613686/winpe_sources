# MKCOL_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x18000dd90`
- end: `0x18000df75`
- name: `?Execute@MKCOL_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x1800036a4`
- `0x180003860`
- `0x180005a5c`
- `0x18000dcb8`
- `0x18000dd90`
- `0x180020614`
- `0x1800206ec`
- `0x180021248`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `msvcrt!_strtoui64` at `0x18000de4d`
- `msvcrt!_strtoui64` at `0x18000de4d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ddce`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ddce`

## string_xrefs

- `0x18000def6`: `Created`

## pseudocode

```c
__int64 __fastcall MKCOL_VERB_HANDLER::Execute(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rax
  const char *v5; // rax
  int v6; // eax
  DAV_BASE_HANDLER *v7; // rcx
  unsigned __int16 v8; // dx
  const char *v9; // r8
  char *EndPtr; // [rsp+50h] [rbp-13B8h] BYREF
  _BYTE v12[5008]; // [rsp+60h] [rbp-13A8h] BYREF

  LOCK_SET::LOCK_SET((LOCK_SET *)v12);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v2 = *(_QWORD *)(a1 + 8);
  EndPtr = 0;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 16LL))(v3, 6)
    || (v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2),
        (v5 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 11)) != 0)
    && _strtoui64(v5, &EndPtr, 10) )
  {
    v8 = 415;
    v9 = "Unsupported Media Type";
    v7 = (DAV_BASE_HANDLER *)a1;
    goto LABEL_19;
  }
  if ( !(unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                        (DAV_BASE_HANDLER *)a1,
                        *(struct IHttpFileInfo **)(a1 + 32)) )
    goto LABEL_20;
  v6 = HandleDavIfAndLocks(
         *(struct IHttpContext **)(a1 + 8),
         *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
         *(const unsigned __int16 **)(a1 + 72),
         (struct LOCK_SET *)v12,
         *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
         0,
         0,
         0,
         3u);
  if ( v6 < 0 )
  {
LABEL_10:
    v7 = (DAV_BASE_HANDLER *)a1;
LABEL_11:
    DAV_BASE_HANDLER::MapAndHandleError(v7, v6);
    goto LABEL_20;
  }
  if ( (unsigned int)LOCK_SET::TestLocks((LOCK_SET *)v12) )
  {
    v6 = MKCOL_VERB_HANDLER::DoMkCol((MKCOL_VERB_HANDLER *)a1);
    v7 = (DAV_BASE_HANDLER *)a1;
    if ( v6 < 0 )
    {
      if ( v6 == -2147024893 )
      {
        v8 = 409;
        v9 = "Conflict";
      }
      else
      {
        if ( v6 != -2147024713 )
          goto LABEL_11;
        v8 = 405;
        v9 = "Method Not Allowed";
      }
    }
    else
    {
      v8 = 201;
      v9 = "Created";
    }
LABEL_19:
    DAV_BASE_HANDLER::FinishRequest(v7, v8, v9, 0, 0);
    goto LABEL_20;
  }
  v6 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, (struct LOCK_SET *)v12);
  if ( v6 < 0 )
    goto LABEL_10;
LABEL_20:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v12);
  return 2;
}

```

## disassembly

```asm
0x18000dd90  mov     [rsp+arg_8], rbx
0x18000dd95  push    rdi
0x18000dd96  mov     eax, 1400h
0x18000dd9b  call    _alloca_probe
0x18000dda0  sub     rsp, rax
0x18000dda3  mov     rax, cs:__security_cookie
0x18000ddaa  xor     rax, rsp
0x18000ddad  mov     [rsp+1408h+var_18], rax
0x18000ddb5  mov     rbx, rcx
0x18000ddb8  lea     rcx, [rsp+1408h+var_13A8]; this
0x18000ddbd  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000ddc2  test    cs:g_dwDebugFlags, 40000000h
0x18000ddcc  jz      short loc_18000DDD4
0x18000ddce  call    cs:__imp_DebugBreak
0x18000ddd4  mov     rdi, [rbx+8]
0x18000ddd8  mov     rcx, rdi
0x18000dddb  mov     [rsp+1408h+EndPtr], 0
0x18000dde4  mov     rax, [rdi]
0x18000dde7  mov     rax, [rax+18h]
0x18000ddeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf0  mov     r9, rax
0x18000ddf3  xor     r8d, r8d
0x18000ddf6  mov     rcx, [rax]
0x18000ddf9  lea     edx, [r8+6]
0x18000ddfd  mov     rax, [rcx+10h]
0x18000de01  mov     rcx, r9
0x18000de04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de09  test    rax, rax
0x18000de0c  jnz     loc_18000DF29
0x18000de12  mov     rax, [rdi]
0x18000de15  mov     rcx, rdi
0x18000de18  mov     rax, [rax+18h]
0x18000de1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de21  mov     r9, rax
0x18000de24  xor     r8d, r8d
0x18000de27  mov     rcx, [rax]
0x18000de2a  lea     edx, [r8+0Bh]
0x18000de2e  mov     rax, [rcx+10h]
0x18000de32  mov     rcx, r9
0x18000de35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de3a  test    rax, rax
0x18000de3d  jz      short loc_18000DE5C
0x18000de3f  mov     r8d, 0Ah; Radix
0x18000de45  lea     rdx, [rsp+1408h+EndPtr]; EndPtr
0x18000de4a  mov     rcx, rax; String
0x18000de4d  call    cs:__imp__strtoui64
0x18000de53  test    rax, rax
0x18000de56  jnz     loc_18000DF29
0x18000de5c  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x18000de60  mov     rcx, rbx; this
0x18000de63  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x18000de68  test    eax, eax
0x18000de6a  jz      loc_18000DF45
0x18000de70  mov     rdx, [rbx+18h]
0x18000de74  lea     r9, [rsp+1408h+var_13A8]; struct LOCK_SET *
0x18000de79  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000de7d  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000de81  mov     [rsp+1408h+var_13C8], 3; unsigned int
0x18000de89  mov     eax, [rdx+38h]
0x18000de8c  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x18000de93  mov     [rsp+1408h+var_13D0], 0; int
0x18000de9b  mov     [rsp+1408h+var_13D8], 0; struct LOCK_SET *
0x18000dea4  mov     [rsp+1408h+var_13E0], 0; unsigned __int16 *
0x18000dead  mov     [rsp+1408h+var_13E8], eax; int
0x18000deb1  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18000deb6  test    eax, eax
0x18000deb8  js      short loc_18000DED9
0x18000deba  lea     rcx, [rsp+1408h+var_13A8]; this
0x18000debf  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x18000dec4  mov     rcx, rbx; this
0x18000dec7  test    eax, eax
0x18000dec9  jnz     short loc_18000DEE5
0x18000decb  lea     rdx, [rsp+1408h+var_13A8]; struct LOCK_SET *
0x18000ded0  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x18000ded5  test    eax, eax
0x18000ded7  jns     short loc_18000DF45
0x18000ded9  mov     rcx, rbx; this
0x18000dedc  mov     edx, eax; int
0x18000dede  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000dee3  jmp     short loc_18000DF45
0x18000dee5  call    ?DoMkCol@MKCOL_VERB_HANDLER@@AEAAJXZ; MKCOL_VERB_HANDLER::DoMkCol(void)
0x18000deea  mov     rcx, rbx
0x18000deed  test    eax, eax
0x18000deef  js      short loc_18000DEFF
0x18000def1  mov     edx, 0C9h
0x18000def6  lea     r8, aCreated; "Created"
0x18000defd  jmp     short loc_18000DF38
0x18000deff  cmp     eax, 80070003h
0x18000df04  jnz     short loc_18000DF14
0x18000df06  mov     edx, 199h
0x18000df0b  lea     r8, aConflict; "Conflict"
0x18000df12  jmp     short loc_18000DF38
0x18000df14  cmp     eax, 800700B7h
0x18000df19  jnz     short loc_18000DEDC
0x18000df1b  mov     edx, 195h
0x18000df20  lea     r8, aMethodNotAllow; "Method Not Allowed"
0x18000df27  jmp     short loc_18000DF38
0x18000df29  mov     edx, 19Fh; unsigned __int16
0x18000df2e  lea     r8, aUnsupportedMed; "Unsupported Media Type"
0x18000df35  mov     rcx, rbx; this
0x18000df38  xor     r9d, r9d; unsigned __int16
0x18000df3b  mov     [rsp+1408h+var_13E8], r9d; int
0x18000df40  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000df45  lea     rcx, [rsp+1408h+var_13A8]; this
0x18000df4a  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000df4f  mov     eax, 2
0x18000df54  mov     rcx, [rsp+1408h+var_18]
0x18000df5c  xor     rcx, rsp; StackCookie
0x18000df5f  call    __security_check_cookie
0x18000df64  mov     rbx, [rsp+1408h+arg_8]
0x18000df6c  add     rsp, 1400h
0x18000df73  pop     rdi
0x18000df74  retn
```
