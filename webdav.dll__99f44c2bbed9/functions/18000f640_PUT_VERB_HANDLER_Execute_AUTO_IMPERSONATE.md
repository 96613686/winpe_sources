# PUT_VERB_HANDLER::Execute(AUTO_IMPERSONATE *)

- ea: `0x18000f640`
- end: `0x18000f9f3`
- name: `?Execute@PUT_VERB_HANDLER@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVAUTO_IMPERSONATE@@@Z`
- size: `947`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x1800036a4`
- `0x180003860`
- `0x180005a5c`
- `0x180006d98`
- `0x18000f3ec`
- `0x18000f4e0`
- `0x18000f640`
- `0x1800119c4`
- `0x18001dea0`
- `0x180020614`
- `0x1800206ec`
- `0x180021248`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f915`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f915`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f69d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000f69d`

## pseudocode

```c
__int64 __fastcall PUT_VERB_HANDLER::Execute(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rax
  unsigned __int16 v5; // dx
  const char *v6; // r8
  unsigned __int16 v7; // r9
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rdi
  __int64 v12; // rax
  int v13; // ecx
  unsigned int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rax
  unsigned __int16 v18; // dx
  const char *v19; // r8
  DAV_BASE_HANDLER *v20; // rcx
  int v21; // edi
  __int64 v22; // r8
  unsigned int v23; // eax
  unsigned int v24; // ebx
  int v25; // edx
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v29[5008]; // [rsp+60h] [rbp-A0h] BYREF

  v28 = 0;
  v26 = 0;
  LOCK_SET::LOCK_SET((LOCK_SET *)v29);
  if ( (g_dwDebugFlags & 0x40000000) != 0 )
    DebugBreak();
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
  if ( (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 17) )
  {
    v5 = 501;
    v6 = "Not Implemented";
LABEL_5:
    v7 = 0;
LABEL_6:
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, v5, v6, v7, 0);
LABEL_7:
    LOCK_SET::~LOCK_SET((LOCK_SET *)v29);
    return 2;
  }
  if ( (int)ValidateContentLengthHeader(*(struct IHttpContext **)(a1 + 8), &v28, &v26) < 0 )
  {
    v5 = 400;
    v6 = "Bad Request";
    v7 = 7;
    goto LABEL_6;
  }
  v9 = *(_DWORD *)(a1 + 208);
  if ( v9 != -1 && (v9 & 0x10) != 0 )
  {
    v5 = 409;
    v6 = "Conflict";
    goto LABEL_5;
  }
  if ( !(unsigned int)DAV_BASE_HANDLER::ValidateHttpIfHeaders(
                        (DAV_BASE_HANDLER *)a1,
                        *(struct IHttpFileInfo **)(a1 + 32)) )
    goto LABEL_43;
  v10 = HandleDavIfAndLocks(
          *(struct IHttpContext **)(a1 + 8),
          *(struct DAV_LOCK_STORE **)(*(_QWORD *)(a1 + 24) + 3328LL),
          *(const unsigned __int16 **)(a1 + 72),
          (struct LOCK_SET *)v29,
          *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
          0,
          0,
          0,
          3u);
  if ( v10 < 0 )
  {
LABEL_17:
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v10);
    goto LABEL_7;
  }
  if ( !(unsigned int)LOCK_SET::TestLocks((LOCK_SET *)v29) )
  {
    v10 = DAV_BASE_HANDLER::SendLockTokenSubmittedResponse((DAV_BASE_HANDLER *)a1, (struct LOCK_SET *)v29);
    if ( v10 < 0 )
      goto LABEL_17;
    goto LABEL_43;
  }
  v11 = (_QWORD *)(a1 + 408);
  v10 = NeedsValidation(
          *(struct IHttpContext **)(a1 + 8),
          *(struct IBaseFileSystem **)(a1 + 240),
          (struct IIS_VDIR_CONFIG *)(*(_QWORD *)(a1 + 24) + 64LL),
          *(const unsigned __int16 **)(a1 + 72),
          *(const unsigned __int16 **)(a1 + 184),
          (struct IValidator **)(a1 + 408));
  if ( v10 < 0 )
    goto LABEL_17;
  if ( *v11 )
    v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 24LL))(*v11);
  else
    v12 = *(_QWORD *)(a1 + 184);
  *(_QWORD *)(a1 + 416) = v12;
  if ( (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 240) + 8LL))(*(_QWORD *)(a1 + 240), -1) < 0 )
  {
    v5 = 500;
    v6 = "Internal Server Error";
    goto LABEL_5;
  }
  v13 = *(_DWORD *)(a1 + 208);
  v14 = 0;
  v27 = 0;
  if ( v13 != -1 )
    v14 = v13 & 6;
  *(_DWORD *)(a1 + 400) = v13 != -1;
  v15 = *(_QWORD *)(a1 + 32);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *(_QWORD *)(a1 + 32) = 0;
  }
  if ( *(_DWORD *)(a1 + 400)
    || (v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8)),
        (v17 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 16LL))(v16, 29)) == 0)
    || *v17 != 42
    || v17[1] )
  {
    v21 = PUT_VERB_HANDLER::DoCreateFile(
            (PUT_VERB_HANDLER *)a1,
            &v27,
            v14,
            (unsigned __int64 *)((unsigned __int64)&v28 & -(__int64)(v26 != 0)));
    if ( *a2 )
    {
      *a2 = 0;
      RevertToSelf();
    }
    if ( v21 >= 0 )
    {
      v22 = a1 + 296;
      if ( v27 )
      {
        v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(a1 + 296);
      }
      else
      {
        v25 = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 36LL);
        *(_QWORD *)(a1 + 304) = *(_QWORD *)(a1 + 8);
        *(_QWORD *)(a1 + 312) = a1 + 360;
        *(_QWORD *)(a1 + 320) = 0;
        *(_QWORD *)(a1 + 328) = v22;
        *(_DWORD *)(a1 + 336) = 32;
        *(_DWORD *)(a1 + 340) = 32 * v25;
        *(_QWORD *)(a1 + 344) = 0;
        *(_DWORD *)(a1 + 352) = 0;
        v23 = CAsyncReader::StartRead();
      }
      v24 = v23;
      goto LABEL_44;
    }
    PUT_VERB_HANDLER::Cleanup((PUT_VERB_HANDLER *)a1, 0);
    v20 = (DAV_BASE_HANDLER *)a1;
    if ( v21 != -2147024893 )
    {
      DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v21);
      goto LABEL_43;
    }
    v18 = 409;
    v19 = "Conflict";
  }
  else
  {
    v18 = 412;
    v19 = "Precondition Failed";
    v20 = (DAV_BASE_HANDLER *)a1;
  }
  DAV_BASE_HANDLER::FinishRequest(v20, v18, v19, 0, 0);
LABEL_43:
  v24 = 2;
LABEL_44:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v29);
  return v24;
}

```

## disassembly

```asm
0x18000f640  mov     [rsp-8+arg_10], rbx
0x18000f645  mov     [rsp-8+arg_18], rsi
0x18000f64a  push    rbp
0x18000f64b  push    rdi
0x18000f64c  push    r14
0x18000f64e  lea     rbp, [rsp-1300h]
0x18000f656  mov     eax, 1400h
0x18000f65b  call    _alloca_probe
0x18000f660  sub     rsp, rax
0x18000f663  mov     rax, cs:__security_cookie
0x18000f66a  xor     rax, rsp
0x18000f66d  mov     [rbp+1310h+var_20], rax
0x18000f674  mov     rbx, rcx
0x18000f677  xor     r14d, r14d
0x18000f67a  lea     rcx, [rsp+1410h+var_13B0]; this
0x18000f67f  mov     [rsp+1410h+var_13B8], r14
0x18000f684  mov     [rsp+1410h+var_13C0], r14d
0x18000f689  mov     rsi, rdx
0x18000f68c  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x18000f691  test    cs:g_dwDebugFlags, 40000000h
0x18000f69b  jz      short loc_18000F6A3
0x18000f69d  call    cs:__imp_DebugBreak
0x18000f6a3  mov     rcx, [rbx+8]
0x18000f6a7  mov     rax, [rcx]
0x18000f6aa  mov     rax, [rax+18h]
0x18000f6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6b3  mov     r9, rax
0x18000f6b6  xor     r8d, r8d
0x18000f6b9  mov     rcx, [rax]
0x18000f6bc  lea     edx, [r8+11h]
0x18000f6c0  mov     rax, [rcx+10h]
0x18000f6c4  mov     rcx, r9
0x18000f6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6cc  test    rax, rax
0x18000f6cf  jz      short loc_18000F701
0x18000f6d1  mov     edx, 1F5h; unsigned __int16
0x18000f6d6  lea     r8, aNotImplemented; "Not Implemented"
0x18000f6dd  xor     r9d, r9d; unsigned __int16
0x18000f6e0  mov     rcx, rbx; this
0x18000f6e3  mov     dword ptr [rsp+1410h+var_13F0], r14d; int
0x18000f6e8  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000f6ed  lea     rcx, [rsp+1410h+var_13B0]; this
0x18000f6f2  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000f6f7  mov     eax, 2
0x18000f6fc  jmp     loc_18000F9C3
0x18000f701  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000f705  lea     r8, [rsp+1410h+var_13C0]; int *
0x18000f70a  lea     rdx, [rsp+1410h+var_13B8]; unsigned __int64 *
0x18000f70f  call    ?ValidateContentLengthHeader@@YAJPEAVIHttpContext@@PEA_KPEAH@Z; ValidateContentLengthHeader(IHttpContext *,unsigned __int64 *,int *)
0x18000f714  test    eax, eax
0x18000f716  jns     short loc_18000F72C
0x18000f718  mov     edx, 190h
0x18000f71d  lea     r8, aBadRequest; "Bad Request"
0x18000f724  mov     r9d, 7
0x18000f72a  jmp     short loc_18000F6E0
0x18000f72c  mov     eax, [rbx+0D0h]
0x18000f732  cmp     eax, 0FFFFFFFFh
0x18000f735  jz      short loc_18000F749
0x18000f737  test    al, 10h
0x18000f739  jz      short loc_18000F749
0x18000f73b  mov     edx, 199h
0x18000f740  lea     r8, aConflict; "Conflict"
0x18000f747  jmp     short loc_18000F6DD
0x18000f749  mov     rdx, [rbx+20h]; struct IHttpFileInfo *
0x18000f74d  mov     rcx, rbx; this
0x18000f750  call    ?ValidateHttpIfHeaders@DAV_BASE_HANDLER@@QEAAHPEAVIHttpFileInfo@@@Z; DAV_BASE_HANDLER::ValidateHttpIfHeaders(IHttpFileInfo *)
0x18000f755  test    eax, eax
0x18000f757  jz      loc_18000F9B2
0x18000f75d  mov     rdx, [rbx+18h]
0x18000f761  lea     r9, [rsp+1410h+var_13B0]; struct LOCK_SET *
0x18000f766  mov     r8, [rbx+48h]; unsigned __int16 *
0x18000f76a  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000f76e  mov     [rsp+1410h+var_13D0], 3; unsigned int
0x18000f776  mov     eax, [rdx+38h]
0x18000f779  mov     rdx, [rdx+0D00h]; struct DAV_LOCK_STORE *
0x18000f780  mov     [rsp+1410h+var_13D8], r14d; int
0x18000f785  mov     [rsp+1410h+var_13E0], r14; struct LOCK_SET *
0x18000f78a  mov     [rsp+1410h+var_13E8], r14; unsigned __int16 *
0x18000f78f  mov     dword ptr [rsp+1410h+var_13F0], eax; int
0x18000f793  call    ?HandleDavIfAndLocks@@YAJPEAVIHttpContext@@PEAVDAV_LOCK_STORE@@PEBGPEAVLOCK_SET@@H23HK@Z; HandleDavIfAndLocks(IHttpContext *,DAV_LOCK_STORE *,ushort const *,LOCK_SET *,int,ushort const *,LOCK_SET *,int,ulong)
0x18000f798  test    eax, eax
0x18000f79a  js      short loc_18000F7BF
0x18000f79c  lea     rcx, [rsp+1410h+var_13B0]; this
0x18000f7a1  call    ?TestLocks@LOCK_SET@@QEAAHXZ; LOCK_SET::TestLocks(void)
0x18000f7a6  test    eax, eax
0x18000f7a8  jnz     short loc_18000F7CE
0x18000f7aa  lea     rdx, [rsp+1410h+var_13B0]; struct LOCK_SET *
0x18000f7af  mov     rcx, rbx; this
0x18000f7b2  call    ?SendLockTokenSubmittedResponse@DAV_BASE_HANDLER@@IEAAJPEAVLOCK_SET@@@Z; DAV_BASE_HANDLER::SendLockTokenSubmittedResponse(LOCK_SET *)
0x18000f7b7  test    eax, eax
0x18000f7b9  jns     loc_18000F9B2
0x18000f7bf  mov     edx, eax; int
0x18000f7c1  mov     rcx, rbx; this
0x18000f7c4  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000f7c9  jmp     loc_18000F6ED
0x18000f7ce  mov     r8, [rbx+18h]
0x18000f7d2  lea     rdi, [rbx+198h]
0x18000f7d9  mov     rax, [rbx+0B8h]
0x18000f7e0  add     r8, 40h ; '@'; struct IIS_VDIR_CONFIG *
0x18000f7e4  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f7e8  mov     rdx, [rbx+0F0h]; struct IBaseFileSystem *
0x18000f7ef  mov     rcx, [rbx+8]; struct IHttpContext *
0x18000f7f3  mov     [rsp+1410h+var_13E8], rdi; struct IValidator **
0x18000f7f8  mov     [rsp+1410h+var_13F0], rax; unsigned __int16 *
0x18000f7fd  call    ?NeedsValidation@@YAJPEAVIHttpContext@@PEAVIBaseFileSystem@@PEAVIIS_VDIR_CONFIG@@PEBG3PEAPEAVIValidator@@@Z; NeedsValidation(IHttpContext *,IBaseFileSystem *,IIS_VDIR_CONFIG *,ushort const *,ushort const *,IValidator * *)
0x18000f802  test    eax, eax
0x18000f804  js      short loc_18000F7BF
0x18000f806  mov     rcx, [rdi]
0x18000f809  test    rcx, rcx
0x18000f80c  jnz     short loc_18000F817
0x18000f80e  mov     rax, [rbx+0B8h]
0x18000f815  jmp     short loc_18000F823
0x18000f817  mov     rax, [rcx]
0x18000f81a  mov     rax, [rax+18h]
0x18000f81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f823  mov     [rbx+1A0h], rax
0x18000f82a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f82e  mov     rcx, [rbx+0F0h]
0x18000f835  mov     rax, [rcx]
0x18000f838  mov     rax, [rax+8]
0x18000f83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f841  test    eax, eax
0x18000f843  jns     short loc_18000F856
0x18000f845  mov     edx, 1F4h
0x18000f84a  lea     r8, aInternalServer; "Internal Server Error"
0x18000f851  jmp     loc_18000F6DD
0x18000f856  mov     ecx, [rbx+0D0h]
0x18000f85c  mov     edi, r14d
0x18000f85f  mov     eax, ecx
0x18000f861  mov     [rsp+1410h+var_13BC], r14d
0x18000f866  and     eax, 6
0x18000f869  cmp     ecx, 0FFFFFFFFh
0x18000f86c  cmovnz  edi, eax
0x18000f86f  mov     eax, r14d
0x18000f872  setnz   al
0x18000f875  mov     [rbx+190h], eax
0x18000f87b  mov     rcx, [rbx+20h]
0x18000f87f  test    rcx, rcx
0x18000f882  jz      short loc_18000F894
0x18000f884  mov     rax, [rcx]
0x18000f887  mov     rax, [rax+10h]
0x18000f88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f890  mov     [rbx+20h], r14
0x18000f894  cmp     [rbx+190h], r14d
0x18000f89b  jnz     short loc_18000F8EA
0x18000f89d  mov     rcx, [rbx+8]
0x18000f8a1  mov     rax, [rcx]
0x18000f8a4  mov     rax, [rax+18h]
0x18000f8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ad  mov     r9, rax
0x18000f8b0  xor     r8d, r8d
0x18000f8b3  mov     rcx, [rax]
0x18000f8b6  lea     edx, [r8+1Dh]
0x18000f8ba  mov     rax, [rcx+10h]
0x18000f8be  mov     rcx, r9
0x18000f8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8c6  test    rax, rax
0x18000f8c9  jz      short loc_18000F8EA
0x18000f8cb  cmp     byte ptr [rax], 2Ah ; '*'
0x18000f8ce  jnz     short loc_18000F8EA
0x18000f8d0  cmp     [rax+1], r14b
0x18000f8d4  jnz     short loc_18000F8EA
0x18000f8d6  mov     edx, 19Ch
0x18000f8db  lea     r8, aPreconditionFa; "Precondition Failed"
0x18000f8e2  mov     rcx, rbx
0x18000f8e5  jmp     loc_18000F9A5
0x18000f8ea  mov     eax, [rsp+1410h+var_13C0]
0x18000f8ee  lea     rdx, [rsp+1410h+var_13BC]; int *
0x18000f8f3  neg     eax
0x18000f8f5  mov     r8d, edi; unsigned int
0x18000f8f8  lea     rax, [rsp+1410h+var_13B8]
0x18000f8fd  mov     rcx, rbx; this
0x18000f900  sbb     r9, r9
0x18000f903  and     r9, rax; unsigned __int64 *
0x18000f906  call    ?DoCreateFile@PUT_VERB_HANDLER@@AEAAJPEAHKPEA_K@Z; PUT_VERB_HANDLER::DoCreateFile(int *,ulong,unsigned __int64 *)
0x18000f90b  mov     edi, eax
0x18000f90d  cmp     [rsi], r14d
0x18000f910  jz      short loc_18000F91B
0x18000f912  mov     [rsi], r14d
0x18000f915  call    cs:__imp_RevertToSelf
0x18000f91b  test    edi, edi
0x18000f91d  js      short loc_18000F984
0x18000f91f  lea     r8, [rbx+128h]
0x18000f926  cmp     [rsp+1410h+var_13BC], r14d
0x18000f92b  jz      short loc_18000F940
0x18000f92d  mov     rax, [r8]
0x18000f930  mov     rcx, r8
0x18000f933  mov     rax, [rax+10h]
0x18000f937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93c  mov     ebx, eax
0x18000f93e  jmp     short loc_18000F9B7
0x18000f940  mov     rax, [rbx+18h]
0x18000f944  lea     rcx, [rbx+130h]
0x18000f94b  mov     edx, [rax+24h]
0x18000f94e  mov     rax, [rbx+8]
0x18000f952  mov     [rcx], rax
0x18000f955  lea     rax, [rbx+168h]
0x18000f95c  shl     edx, 5
0x18000f95f  mov     [rcx+8], rax
0x18000f963  mov     [rcx+10h], r14
0x18000f967  mov     [rcx+18h], r8
0x18000f96b  mov     dword ptr [rcx+20h], 20h ; ' '
0x18000f972  mov     [rcx+24h], edx
0x18000f975  mov     [rcx+28h], r14
0x18000f979  mov     [rcx+30h], r14d
0x18000f97d  call    ?StartRead@CAsyncReader@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ; CAsyncReader::StartRead(void)
0x18000f982  jmp     short loc_18000F93C
0x18000f984  xor     edx, edx; int
0x18000f986  mov     rcx, rbx; this
0x18000f989  call    ?Cleanup@PUT_VERB_HANDLER@@AEAAJH@Z; PUT_VERB_HANDLER::Cleanup(int)
0x18000f98e  mov     rcx, rbx; this
0x18000f991  cmp     edi, 80070003h
0x18000f997  jnz     short loc_18000F9EA
0x18000f999  mov     edx, 199h; unsigned __int16
0x18000f99e  lea     r8, aConflict; "Conflict"
0x18000f9a5  xor     r9d, r9d; unsigned __int16
0x18000f9a8  mov     dword ptr [rsp+1410h+var_13F0], r14d; int
0x18000f9ad  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000f9b2  mov     ebx, 2
0x18000f9b7  lea     rcx, [rsp+1410h+var_13B0]; this
0x18000f9bc  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x18000f9c1  mov     eax, ebx
0x18000f9c3  mov     rcx, [rbp+1310h+var_20]
0x18000f9ca  xor     rcx, rsp; StackCookie
0x18000f9cd  call    __security_check_cookie
0x18000f9d2  lea     r11, [rsp+1410h+var_10]
0x18000f9da  mov     rbx, [r11+30h]
0x18000f9de  mov     rsi, [r11+38h]
0x18000f9e2  mov     rsp, r11
0x18000f9e5  pop     r14
0x18000f9e7  pop     rdi
0x18000f9e8  pop     rbp
0x18000f9e9  retn
0x18000f9ea  mov     edx, edi; int
0x18000f9ec  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000f9f1  jmp     short loc_18000F9B2
```
