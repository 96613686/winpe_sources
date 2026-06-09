# GetUserServiceNameIfAvailable(IUnknown *,ushort const *,CToken *,unsigned __int64,ushort * *,bool *)

- ea: `0x18001f340`
- end: `0x18001f8e4`
- name: `?GetUserServiceNameIfAvailable@@YAJPEAUIUnknown@@PEBGPEAVCToken@@_KPEAPEAGPEA_N@Z`
- size: `1444`
- prototype: `int(struct IUnknown *, const unsigned __int16 *, struct CToken *, unsigned __int64, unsigned __int16 **, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f8f0`
- `0x18009280c`

## callees

- `0x18000ce5c`
- `0x18000fb8c`
- `0x18001ecf0`
- `0x18001f340`
- `0x1800210f8`
- `0x180025950`
- `0x18002aa10`
- `0x18002faa8`
- `0x18005edcc`
- `0x1800b8428`
- `0x1800b9b90`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f459`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f5ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f612`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f76d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f7d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f8bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f459`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f5ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f612`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f76d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f7d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f8bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f3ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f3ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f583`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f583`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18001f5b5`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18001f63c`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18001f5b5`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18001f63c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f522`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f688`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f849`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f885`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f522`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f688`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f849`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001f885`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001f6d5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18001f6d5`

## string_xrefs

- `0x18001f439`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f54b`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f669`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f713`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f738`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f7a0`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f7fc`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f82d`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18001f866`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

## pseudocode

```c
__int64 __fastcall GetUserServiceNameIfAvailable(
        struct IUnknown *a1,
        const unsigned __int16 *a2,
        struct CToken *a3,
        __int64 a4,
        unsigned __int16 **a5,
        bool *a6)
{
  unsigned __int16 **v6; // r15
  bool *v8; // r12
  __int64 v11; // rax
  SIZE_T v12; // rsi
  _WORD *v13; // rax
  _WORD *v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rdx
  _WORD *v18; // r9
  _WORD *v19; // rcx
  unsigned int LastError; // esi
  __int64 result; // rax
  int v22; // eax
  LPWSTR v23; // rcx
  __int64 v24; // rdx
  const char *v25; // r9
  unsigned int SessionId; // eax
  unsigned int UserServiceName; // eax
  void **unique; // rax
  HANDLE v29; // rcx
  _WORD *v30; // rsi
  void *v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // eax
  int v34; // eax
  unsigned int v35; // edi
  unsigned int TokenFromHandle; // edi
  unsigned int v37; // ebx
  unsigned int v38; // [rsp+20h] [rbp-38h]
  const char *v39; // [rsp+28h] [rbp-30h]
  __int64 v40; // [rsp+30h] [rbp-28h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-18h] BYREF
  LPVOID lpMem[2]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v6 = a5;
  v8 = a6;
  v11 = -1;
  *a5 = 0;
  *v8 = 0;
  do
    ++v11;
  while ( a2[v11] );
  LODWORD(a5) = v11 + 1;
  v12 = 2LL * (unsigned int)(v11 + 1);
  if ( !is_mul_ok((unsigned int)(v11 + 1), 2u) )
    v12 = -1;
  v13 = HeapAlloc(g_hHeap, 0, v12);
  v14 = v13;
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CB,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)0x8007000ELL,
      v38);
    return 2147942414LL;
  }
  memset_0(v13, 0, v12);
  v15 = (unsigned int)a5;
  if ( !(_DWORD)a5 )
  {
    LastError = -2147024809;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)LastError,
      v38);
LABEL_18:
    HeapFree(g_hHeap, 0, v14);
    return LastError;
  }
  if ( (unsigned int)a5 > 0x7FFFFFFFuLL )
  {
    LastError = -2147024809;
    *v14 = 0;
    goto LABEL_17;
  }
  v16 = 2147483646;
  v17 = a2;
  v18 = v14;
  do
  {
    if ( !v16 )
      break;
    if ( !*v17 )
      break;
    *v18++ = *v17++;
    --v16;
    --v15;
  }
  while ( v15 );
  v19 = v18 - 1;
  LastError = -2147024774;
  if ( v15 )
    v19 = v18;
  result = 0;
  if ( v15 )
    LastError = 0;
  *v19 = 0;
  if ( !v15 )
    goto LABEL_17;
  if ( !a3 )
  {
    *v6 = v14;
    return result;
  }
  v40 = 0;
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
          a1,
          &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
          &v40);
  LastError = v22;
  if ( v22 == -2147467262 )
  {
    *v6 = v14;
    goto LABEL_25;
  }
  if ( v22 < 0 )
  {
    v24 = 733;
    goto LABEL_37;
  }
  LODWORD(a6) = 0;
  LastError = (*(__int64 (__fastcall **)(__int64, bool **))(*(_QWORD *)v40 + 248LL))(v40, &a6);
  if ( (LastError & 0x80000000) != 0 )
  {
    v24 = 735;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)LastError,
      v38);
    goto LABEL_38;
  }
  if ( !(_DWORD)a6 )
  {
    *v6 = v14;
LABEL_25:
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    return 0;
  }
  if ( !a4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
    goto LABEL_30;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)0x80070005LL,
      (int)"User Context specified on a SKU that does not support it",
      v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    HeapFree(g_hHeap, 0, v14);
    return 2147942405LL;
  }
  hObject = 0;
  v34 = UMgrQueryUserToken(a4, &hObject);
  v35 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v34,
      v38);
LABEL_59:
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    HeapFree(g_hHeap, 0, v14);
    return v35;
  }
  lpMem[0] = 0;
  TokenFromHandle = LookupOrCreateTokenFromHandle(hObject, (struct CToken **)lpMem);
  if ( TokenFromHandle )
  {
    CloseHandle(hObject);
    v35 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2F5,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)TokenFromHandle,
            v38);
    if ( lpMem[0] )
      CToken::Release((CToken *)lpMem[0]);
    goto LABEL_59;
  }
  a3 = (struct CToken *)lpMem[0];
LABEL_30:
  v23 = 0;
  StringSid = 0;
  if ( !a3 )
  {
LABEL_31:
    *v6 = v14;
    if ( v23 )
      LocalFree(v23);
    if ( a3 )
      CToken::Release(a3);
    goto LABEL_25;
  }
  if ( !ConvertSidToStringSidW((char *)a3 + 156, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x305,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                  v25);
    if ( StringSid )
      LocalFree(StringSid);
LABEL_50:
    CToken::Release(a3);
LABEL_38:
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_18;
  }
  SessionId = CToken::GetSessionId(a3);
  UserServiceName = QueryUserServiceName(a2, StringSid, SessionId, v14);
  if ( UserServiceName != 122 )
  {
    if ( !UserServiceName )
      goto LABEL_46;
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x30F,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                  (const char *)UserServiceName,
                  (unsigned int)&a5);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_50;
  }
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(lpMem, (unsigned int)a5);
  v29 = g_hHeap;
  v30 = *unique;
  *unique = 0;
  HeapFree(v29, 0, v14);
  v31 = lpMem[0];
  lpMem[0] = 0;
  if ( v31 )
    HeapFree(g_hHeap, 0, v31);
  v32 = CToken::GetSessionId(a3);
  v33 = QueryUserServiceName(a2, StringSid, v32, v30);
  if ( !v33 )
  {
    v14 = v30;
LABEL_46:
    v23 = StringSid;
    *v8 = 1;
    goto LABEL_31;
  }
  v37 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x30B,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
          (const char *)v33,
          (unsigned int)&a5);
  if ( StringSid )
    LocalFree(StringSid);
  CToken::Release(a3);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v30 )
    HeapFree(g_hHeap, 0, v30);
  return v37;
}

```

## disassembly

```asm
0x18001f340  mov     [rsp-40h+arg_18], r9
0x18001f345  push    rbp
0x18001f346  push    rbx
0x18001f347  push    rsi
0x18001f348  push    rdi
0x18001f349  push    r12
0x18001f34b  push    r13
0x18001f34d  push    r14
0x18001f34f  push    r15
0x18001f351  mov     rbp, rsp
0x18001f354  sub     rsp, 58h
0x18001f358  mov     r15, [rbp+arg_20]
0x18001f35c  mov     rdi, r8
0x18001f35f  mov     r12, [rbp+arg_28]
0x18001f363  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001f36a  mov     r14, rdx
0x18001f36d  mov     r13, rcx
0x18001f370  mov     rax, r8
0x18001f373  mov     qword ptr [r15], 0
0x18001f37a  mov     byte ptr [r12], 0
0x18001f37f  nop
0x18001f380  inc     rax
0x18001f383  cmp     word ptr [rdx+rax*2], 0
0x18001f388  jnz     short loc_18001F380
0x18001f38a  inc     eax
0x18001f38c  mov     ecx, eax
0x18001f38e  mov     dword ptr [rbp+arg_20], eax
0x18001f391  mov     eax, 2
0x18001f396  mul     rcx
0x18001f399  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f3a0  mov     rsi, rax
0x18001f3a3  cmovb   rsi, r8
0x18001f3a7  xor     edx, edx; dwFlags
0x18001f3a9  mov     r8, rsi; dwBytes
0x18001f3ac  call    cs:__imp_HeapAlloc
0x18001f3b3  nop     dword ptr [rax+rax+00h]
0x18001f3b8  mov     rbx, rax
0x18001f3bb  test    rax, rax
0x18001f3be  jz      loc_18001F70F
0x18001f3c4  mov     r8, rsi; Size
0x18001f3c7  xor     edx, edx; Val
0x18001f3c9  mov     rcx, rax; void *
0x18001f3cc  call    memset_0
0x18001f3d1  mov     r8d, dword ptr [rbp+arg_20]
0x18001f3d5  test    r8, r8
0x18001f3d8  jz      loc_18001F6A1
0x18001f3de  cmp     r8, 7FFFFFFFh
0x18001f3e5  ja      loc_18001F8D2
0x18001f3eb  mov     ecx, 7FFFFFFEh
0x18001f3f0  mov     rdx, r14
0x18001f3f3  mov     r9, rbx
0x18001f3f6  test    rcx, rcx
0x18001f3f9  jz      short loc_18001F418
0x18001f3fb  movzx   eax, word ptr [rdx]
0x18001f3fe  test    ax, ax
0x18001f401  jz      short loc_18001F418
0x18001f403  mov     [r9], ax
0x18001f407  add     rdx, 2
0x18001f40b  add     r9, 2
0x18001f40f  dec     rcx
0x18001f412  sub     r8, 1
0x18001f416  jnz     short loc_18001F3F6
0x18001f418  test    r8, r8
0x18001f41b  lea     rcx, [r9-2]
0x18001f41f  mov     esi, 8007007Ah
0x18001f424  cmovnz  rcx, r9
0x18001f428  xor     eax, eax
0x18001f42a  test    r8, r8
0x18001f42d  cmovnz  esi, eax
0x18001f430  mov     [rcx], ax
0x18001f433  jnz     short loc_18001F479
0x18001f435  mov     rcx, [rbp+40h]; this
0x18001f439  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f440  mov     r9d, esi; char *
0x18001f443  mov     edx, 2CCh; void *
0x18001f448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f44d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f454  mov     r8, rbx; lpMem
0x18001f457  xor     edx, edx; dwFlags
0x18001f459  call    cs:__imp_HeapFree
0x18001f460  nop     dword ptr [rax+rax+00h]
0x18001f465  mov     eax, esi
0x18001f467  add     rsp, 58h
0x18001f46b  pop     r15
0x18001f46d  pop     r14
0x18001f46f  pop     r13
0x18001f471  pop     r12
0x18001f473  pop     rdi
0x18001f474  pop     rsi
0x18001f475  pop     rbx
0x18001f476  pop     rbp
0x18001f477  retn
0x18001f479  test    rdi, rdi
0x18001f47c  jz      loc_18001F8DC
0x18001f482  mov     [rbp+var_28], rax
0x18001f486  lea     r8, [rbp+var_28]
0x18001f48a  mov     rax, [r13+0]
0x18001f48e  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x18001f495  mov     rcx, r13
0x18001f498  mov     rax, [rax]
0x18001f49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a0  mov     esi, eax
0x18001f4a2  cmp     eax, 80004002h
0x18001f4a7  jz      loc_18001F53D
0x18001f4ad  test    eax, eax
0x18001f4af  js      loc_18001F780
0x18001f4b5  mov     rcx, [rbp+var_28]
0x18001f4b9  lea     rdx, [rbp+arg_28]
0x18001f4bd  mov     dword ptr [rbp+arg_28], 0
0x18001f4c4  mov     rax, [rcx]
0x18001f4c7  mov     rax, [rax+0F8h]
0x18001f4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4d3  mov     esi, eax
0x18001f4d5  test    eax, eax
0x18001f4d7  js      short loc_18001F542
0x18001f4d9  cmp     dword ptr [rbp+arg_28], 0
0x18001f4dd  jnz     short loc_18001F4FE
0x18001f4df  mov     [r15], rbx
0x18001f4e2  mov     rcx, [rbp+var_28]
0x18001f4e6  test    rcx, rcx
0x18001f4e9  jz      short loc_18001F4F7
0x18001f4eb  mov     rax, [rcx]
0x18001f4ee  mov     rax, [rax+10h]
0x18001f4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f7  xor     eax, eax
0x18001f4f9  jmp     loc_18001F467
0x18001f4fe  mov     rsi, [rbp+arg_18]
0x18001f502  test    rsi, rsi
0x18001f505  jnz     loc_18001F6B9
0x18001f50b  lock inc dword ptr [rdi+8]
0x18001f50f  xor     ecx, ecx; hMem
0x18001f511  mov     [rbp+StringSid], rcx
0x18001f515  test    rdi, rdi
0x18001f518  jnz     short loc_18001F578
0x18001f51a  mov     [r15], rbx
0x18001f51d  test    rcx, rcx
0x18001f520  jz      short loc_18001F52E
0x18001f522  call    cs:__imp_LocalFree
0x18001f529  nop     dword ptr [rax+rax+00h]
0x18001f52e  test    rdi, rdi
0x18001f531  jz      short loc_18001F4E2
0x18001f533  mov     rcx, rdi; this
0x18001f536  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18001f53b  jmp     short loc_18001F4E2
0x18001f53d  mov     [r15], rbx
0x18001f540  jmp     short loc_18001F4E2
0x18001f542  mov     edx, 2DFh; void *
0x18001f547  mov     rcx, [rbp+40h]; this
0x18001f54b  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f552  mov     r9d, esi; char *
0x18001f555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f55a  mov     rcx, [rbp+var_28]
0x18001f55e  test    rcx, rcx
0x18001f561  jz      loc_18001F44D
0x18001f567  mov     rax, [rcx]
0x18001f56a  mov     rax, [rax+10h]
0x18001f56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f573  jmp     loc_18001F44D
0x18001f578  lea     rcx, [rdi+9Ch]; Sid
0x18001f57f  lea     rdx, [rbp+StringSid]; StringSid
0x18001f583  call    cs:__imp_ConvertSidToStringSidW
0x18001f58a  nop     dword ptr [rax+rax+00h]
0x18001f58f  test    eax, eax
0x18001f591  jz      loc_18001F829
0x18001f597  mov     rcx, rdi; this
0x18001f59a  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18001f59f  mov     rdx, [rbp+StringSid]
0x18001f5a3  lea     rcx, [rbp+arg_20]
0x18001f5a7  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x18001f5ac  mov     r9, rbx
0x18001f5af  mov     rcx, r14
0x18001f5b2  mov     r8d, eax
0x18001f5b5  call    cs:__imp_QueryUserServiceName
0x18001f5bc  nop     dword ptr [rax+rax+00h]
0x18001f5c1  cmp     eax, 7Ah ; 'z'
0x18001f5c4  jnz     loc_18001F661
0x18001f5ca  mov     edx, dword ptr [rbp+arg_20]
0x18001f5cd  lea     rcx, [rbp+lpMem]
0x18001f5d1  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18001f5d6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f5dd  mov     r8, rbx; lpMem
0x18001f5e0  xor     edx, edx; dwFlags
0x18001f5e2  mov     rsi, [rax]
0x18001f5e5  mov     qword ptr [rax], 0
0x18001f5ec  call    cs:__imp_HeapFree
0x18001f5f3  nop     dword ptr [rax+rax+00h]
0x18001f5f8  mov     r8, [rbp+lpMem]; lpMem
0x18001f5fc  mov     [rbp+lpMem], 0
0x18001f604  test    r8, r8
0x18001f607  jz      short loc_18001F61E
0x18001f609  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f610  xor     edx, edx; dwFlags
0x18001f612  call    cs:__imp_HeapFree
0x18001f619  nop     dword ptr [rax+rax+00h]
0x18001f61e  mov     rcx, rdi; this
0x18001f621  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18001f626  mov     rdx, [rbp+StringSid]
0x18001f62a  lea     rcx, [rbp+arg_20]
0x18001f62e  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x18001f633  mov     r9, rsi
0x18001f636  mov     rcx, r14
0x18001f639  mov     r8d, eax
0x18001f63c  call    cs:__imp_QueryUserServiceName
0x18001f643  nop     dword ptr [rax+rax+00h]
0x18001f648  test    eax, eax
0x18001f64a  jnz     loc_18001F862
0x18001f650  mov     rbx, rsi
0x18001f653  mov     rcx, [rbp+StringSid]
0x18001f657  mov     byte ptr [r12], 1
0x18001f65c  jmp     loc_18001F51A
0x18001f661  test    eax, eax
0x18001f663  jz      short loc_18001F653
0x18001f665  mov     rcx, [rbp+40h]; this
0x18001f669  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f670  mov     r9d, eax; char *
0x18001f673  mov     edx, 30Fh; void *
0x18001f678  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f67d  mov     rcx, [rbp+StringSid]; hMem
0x18001f681  mov     esi, eax
0x18001f683  test    rcx, rcx
0x18001f686  jz      short loc_18001F694
0x18001f688  call    cs:__imp_LocalFree
0x18001f68f  nop     dword ptr [rax+rax+00h]
0x18001f694  mov     rcx, rdi; this
0x18001f697  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18001f69c  jmp     loc_18001F55A
0x18001f6a1  mov     esi, 80070057h
0x18001f6a6  test    r8, r8
0x18001f6a9  jz      loc_18001F435
0x18001f6af  xor     ecx, ecx
0x18001f6b1  mov     [rbx], cx
0x18001f6b4  jmp     loc_18001F435
0x18001f6b9  call    IsUMgrQueryUserContextPresent
0x18001f6be  test    al, al
0x18001f6c0  jz      loc_18001F78A
0x18001f6c6  lea     rdx, [rbp+hObject]
0x18001f6ca  mov     [rbp+hObject], 0
0x18001f6d2  mov     rcx, rsi
0x18001f6d5  call    cs:__imp_UMgrQueryUserToken
0x18001f6dc  nop     dword ptr [rax+rax+00h]
0x18001f6e1  mov     edi, eax
0x18001f6e3  test    eax, eax
0x18001f6e5  js      short loc_18001F734
0x18001f6e7  mov     rcx, [rbp+hObject]; void *
0x18001f6eb  lea     rdx, [rbp+lpMem]; struct CToken **
0x18001f6ef  mov     [rbp+lpMem], 0
0x18001f6f7  call    ?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z; LookupOrCreateTokenFromHandle(void *,CToken * *)
0x18001f6fc  mov     edi, eax
0x18001f6fe  test    eax, eax
0x18001f700  jnz     loc_18001F7E8
0x18001f706  mov     rdi, [rbp+lpMem]
0x18001f70a  jmp     loc_18001F50F
0x18001f70f  mov     rcx, [rbp+40h]; this
0x18001f713  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f71a  mov     r9d, 8007000Eh; char *
0x18001f720  mov     edx, 2CBh; void *
0x18001f725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f72a  mov     eax, 8007000Eh
0x18001f72f  jmp     loc_18001F467
0x18001f734  mov     rcx, [rbp+40h]; this
0x18001f738  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f73f  mov     r9d, edi; char *
0x18001f742  mov     edx, 2F0h; void *
0x18001f747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f74c  mov     rcx, [rbp+var_28]
0x18001f750  test    rcx, rcx
0x18001f753  jz      short loc_18001F761
0x18001f755  mov     rax, [rcx]
0x18001f758  mov     rax, [rax+10h]
0x18001f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f761  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f768  mov     r8, rbx; lpMem
0x18001f76b  xor     edx, edx; dwFlags
0x18001f76d  call    cs:__imp_HeapFree
0x18001f774  nop     dword ptr [rax+rax+00h]
0x18001f779  mov     eax, edi
0x18001f77b  jmp     loc_18001F467
0x18001f780  mov     edx, 2DDh
0x18001f785  jmp     loc_18001F547
0x18001f78a  mov     rcx, [rbp+40h]; this
0x18001f78e  lea     rax, aUserContextSpe_0; "User Context specified on a SKU that do"...
0x18001f795  mov     r9d, 80070005h; char *
0x18001f79b  mov     qword ptr [rsp+58h+var_38], rax; int
0x18001f7a0  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18001f7a7  mov     edx, 2FAh; void *
0x18001f7ac  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001f7b1  mov     rcx, [rbp+var_28]
0x18001f7b5  test    rcx, rcx
0x18001f7b8  jz      short loc_18001F7C6
0x18001f7ba  mov     rax, [rcx]
0x18001f7bd  mov     rax, [rax+10h]
0x18001f7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7c6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001f7cd  mov     r8, rbx; lpMem
0x18001f7d0  xor     edx, edx; dwFlags
0x18001f7d2  call    cs:__imp_HeapFree
0x18001f7d9  nop     dword ptr [rax+rax+00h]
0x18001f7de  mov     eax, 80070005h
0x18001f7e3  jmp     loc_18001F467
0x18001f7e8  mov     rcx, [rbp+hObject]; hObject
  ... truncated ...
```
