# GetUserServiceNameIfAvailable(IUnknown *,ushort const *,CToken *,unsigned __int64,ushort * *,bool *)

- ea: `0x180029db0`
- end: `0x18002a307`
- name: `?GetUserServiceNameIfAvailable@@YAJPEAUIUnknown@@PEBGPEAVCToken@@_KPEAPEAGPEA_N@Z`
- size: `1367`
- prototype: `int(struct IUnknown *, const unsigned __int16 *, struct CToken *, unsigned __int64, unsigned __int16 **, bool *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002a310`
- `0x180091620`

## callees

- `0x18000b428`
- `0x18001ec28`
- `0x180025730`
- `0x1800297e0`
- `0x180029db0`
- `0x18002ba28`
- `0x18002f8cc`
- `0x180031ae0`
- `0x1800594f4`
- `0x1800b3128`
- `0x1800b4890`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a227`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ec3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029fd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a04d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a06d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a1b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a213`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a2e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029ec3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180029fd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a04d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a06d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a1b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a213`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a2e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029e1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180029e1c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029ff0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029ff0`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18002a01c`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18002a091`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18002a01c`
- `api-ms-win-service-private-l1-1-2!QueryUserServiceName` at `0x18002a091`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180029f85`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a0db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a27e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a2b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180029f85`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a0db`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a27e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002a2b4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002a122`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002a122`

## string_xrefs

- `0x180029ea3`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x180029fa8`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a0b8`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a15a`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a17f`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a1e1`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a231`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a262`: `onecore\com\combase\rpcss\olescm\clsid.cxx`
- `0x18002a295`: `onecore\com\combase\rpcss\olescm\clsid.cxx`

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
  unsigned int v20; // esi
  __int64 result; // rax
  int v22; // eax
  int LastError; // esi
  LPWSTR v24; // rcx
  __int64 v25; // rdx
  const char *v26; // r9
  unsigned int SessionId; // eax
  unsigned int UserServiceName; // eax
  void **unique; // rax
  HANDLE v30; // rcx
  _WORD *v31; // rsi
  void *v32; // r8
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax
  unsigned int v36; // edi
  unsigned int TokenFromHandle; // edi
  unsigned int v38; // ebx
  unsigned int v39; // [rsp+20h] [rbp-38h]
  const char *v40; // [rsp+28h] [rbp-30h]
  __int64 v41; // [rsp+30h] [rbp-28h] BYREF
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
      v39);
    return 2147942414LL;
  }
  memset_0(v13, 0, v12);
  v15 = (unsigned int)a5;
  if ( !(_DWORD)a5 )
  {
    v20 = -2147024809;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)v20,
      v39);
    HeapFree(g_hHeap, 0, v14);
    return v20;
  }
  if ( (unsigned int)a5 > 0x7FFFFFFFuLL )
  {
    v20 = -2147024809;
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
  v20 = -2147024774;
  if ( v15 )
    v19 = v18;
  result = 0;
  if ( v15 )
    v20 = 0;
  *v19 = 0;
  if ( !v15 )
    goto LABEL_17;
  if ( !a3 )
  {
    *v6 = v14;
    return result;
  }
  v41 = 0;
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
          a1,
          &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680,
          &v41);
  LastError = v22;
  if ( v22 == -2147467262 )
  {
    *v6 = v14;
    goto LABEL_24;
  }
  if ( v22 < 0 )
  {
    v25 = 733;
    goto LABEL_36;
  }
  LODWORD(a6) = 0;
  LastError = (*(__int64 (__fastcall **)(__int64, bool **))(*(_QWORD *)v41 + 248LL))(v41, &a6);
  if ( LastError < 0 )
  {
    v25 = 735;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)LastError,
      v39);
LABEL_37:
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    HeapFree(g_hHeap, 0, v14);
    return (unsigned int)LastError;
  }
  if ( !(_DWORD)a6 )
  {
    *v6 = v14;
LABEL_24:
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    return 0;
  }
  if ( !a4 )
  {
    _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
    goto LABEL_29;
  }
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2FA,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)0x80070005LL,
      (int)"User Context specified on a SKU that does not support it",
      v40);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    HeapFree(g_hHeap, 0, v14);
    return 2147942405LL;
  }
  hObject = 0;
  v35 = UMgrQueryUserToken(a4, &hObject);
  v36 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
      (const char *)(unsigned int)v35,
      v39);
LABEL_58:
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    HeapFree(g_hHeap, 0, v14);
    return v36;
  }
  lpMem[0] = 0;
  TokenFromHandle = LookupOrCreateTokenFromHandle(hObject, (struct CToken **)lpMem);
  if ( TokenFromHandle )
  {
    CloseHandle(hObject);
    v36 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2F5,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
            (const char *)TokenFromHandle,
            v39);
    if ( lpMem[0] )
      CToken::Release((CToken *)lpMem[0]);
    goto LABEL_58;
  }
  a3 = (struct CToken *)lpMem[0];
LABEL_29:
  v24 = 0;
  StringSid = 0;
  if ( !a3 )
  {
LABEL_30:
    *v6 = v14;
    if ( v24 )
      LocalFree(v24);
    if ( a3 )
      CToken::Release(a3);
    goto LABEL_24;
  }
  if ( !ConvertSidToStringSidW((char *)a3 + 156, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x305,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
                  v26);
    if ( StringSid )
      LocalFree(StringSid);
    goto LABEL_69;
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
    {
      LocalFree(StringSid);
      CToken::Release(a3);
      goto LABEL_37;
    }
LABEL_69:
    CToken::Release(a3);
    goto LABEL_37;
  }
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(lpMem, (unsigned int)a5);
  v30 = g_hHeap;
  v31 = *unique;
  *unique = 0;
  HeapFree(v30, 0, v14);
  v32 = lpMem[0];
  lpMem[0] = 0;
  if ( v32 )
    HeapFree(g_hHeap, 0, v32);
  v33 = CToken::GetSessionId(a3);
  v34 = QueryUserServiceName(a2, StringSid, v33, v31);
  if ( !v34 )
  {
    v14 = v31;
LABEL_46:
    v24 = StringSid;
    *v8 = 1;
    goto LABEL_30;
  }
  v38 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x30B,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.cxx",
          (const char *)v34,
          (unsigned int)&a5);
  if ( StringSid )
    LocalFree(StringSid);
  CToken::Release(a3);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v31 )
    HeapFree(g_hHeap, 0, v31);
  return v38;
}

```

## disassembly

```asm
0x180029db0  mov     [rsp-40h+arg_18], r9
0x180029db5  push    rbp
0x180029db6  push    rbx
0x180029db7  push    rsi
0x180029db8  push    rdi
0x180029db9  push    r12
0x180029dbb  push    r13
0x180029dbd  push    r14
0x180029dbf  push    r15
0x180029dc1  mov     rbp, rsp
0x180029dc4  sub     rsp, 58h
0x180029dc8  mov     r15, [rbp+arg_20]
0x180029dcc  mov     rdi, r8
0x180029dcf  mov     r12, [rbp+arg_28]
0x180029dd3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180029dda  mov     r14, rdx
0x180029ddd  mov     r13, rcx
0x180029de0  mov     rax, r8
0x180029de3  mov     qword ptr [r15], 0
0x180029dea  mov     byte ptr [r12], 0
0x180029def  nop
0x180029df0  inc     rax
0x180029df3  cmp     word ptr [rdx+rax*2], 0
0x180029df8  jnz     short loc_180029DF0
0x180029dfa  inc     eax
0x180029dfc  mov     ecx, eax
0x180029dfe  mov     dword ptr [rbp+arg_20], eax
0x180029e01  mov     eax, 2
0x180029e06  mul     rcx
0x180029e09  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180029e10  mov     rsi, rax
0x180029e13  cmovb   rsi, r8
0x180029e17  xor     edx, edx; dwFlags
0x180029e19  mov     r8, rsi; dwBytes
0x180029e1c  call    cs:__imp_HeapAlloc
0x180029e22  mov     rbx, rax
0x180029e25  test    rax, rax
0x180029e28  jz      loc_18002A156
0x180029e2e  mov     r8, rsi; Size
0x180029e31  xor     edx, edx; Val
0x180029e33  mov     rcx, rax; void *
0x180029e36  call    memset_0
0x180029e3b  mov     r8d, dword ptr [rbp+arg_20]
0x180029e3f  test    r8, r8
0x180029e42  jz      loc_18002A0EE
0x180029e48  cmp     r8, 7FFFFFFFh
0x180029e4f  ja      loc_18002A2F5
0x180029e55  mov     ecx, 7FFFFFFEh
0x180029e5a  mov     rdx, r14
0x180029e5d  mov     r9, rbx
0x180029e60  test    rcx, rcx
0x180029e63  jz      short loc_180029E82
0x180029e65  movzx   eax, word ptr [rdx]
0x180029e68  test    ax, ax
0x180029e6b  jz      short loc_180029E82
0x180029e6d  mov     [r9], ax
0x180029e71  add     rdx, 2
0x180029e75  add     r9, 2
0x180029e79  dec     rcx
0x180029e7c  sub     r8, 1
0x180029e80  jnz     short loc_180029E60
0x180029e82  test    r8, r8
0x180029e85  lea     rcx, [r9-2]
0x180029e89  mov     esi, 8007007Ah
0x180029e8e  cmovnz  rcx, r9
0x180029e92  xor     eax, eax
0x180029e94  test    r8, r8
0x180029e97  cmovnz  esi, eax
0x180029e9a  mov     [rcx], ax
0x180029e9d  jnz     short loc_180029EDC
0x180029e9f  mov     rcx, [rbp+40h]; this
0x180029ea3  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180029eaa  mov     r9d, esi; char *
0x180029ead  mov     edx, 2CCh; void *
0x180029eb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029eb7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180029ebe  mov     r8, rbx; lpMem
0x180029ec1  xor     edx, edx; dwFlags
0x180029ec3  call    cs:__imp_HeapFree
0x180029ec9  mov     eax, esi
0x180029ecb  add     rsp, 58h
0x180029ecf  pop     r15
0x180029ed1  pop     r14
0x180029ed3  pop     r13
0x180029ed5  pop     r12
0x180029ed7  pop     rdi
0x180029ed8  pop     rsi
0x180029ed9  pop     rbx
0x180029eda  pop     rbp
0x180029edb  retn
0x180029edc  test    rdi, rdi
0x180029edf  jz      loc_18002A2FF
0x180029ee5  mov     [rbp+var_28], rax
0x180029ee9  lea     r8, [rbp+var_28]
0x180029eed  mov     rax, [r13+0]
0x180029ef1  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x180029ef8  mov     rcx, r13
0x180029efb  mov     rax, [rax]
0x180029efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f03  mov     esi, eax
0x180029f05  cmp     eax, 80004002h
0x180029f0a  jz      loc_180029F9A
0x180029f10  test    eax, eax
0x180029f12  js      loc_18002A1C1
0x180029f18  mov     rcx, [rbp+var_28]
0x180029f1c  lea     rdx, [rbp+arg_28]
0x180029f20  mov     dword ptr [rbp+arg_28], 0
0x180029f27  mov     rax, [rcx]
0x180029f2a  mov     rax, [rax+0F8h]
0x180029f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f36  mov     esi, eax
0x180029f38  test    eax, eax
0x180029f3a  js      short loc_180029F9F
0x180029f3c  cmp     dword ptr [rbp+arg_28], 0
0x180029f40  jnz     short loc_180029F61
0x180029f42  mov     [r15], rbx
0x180029f45  mov     rcx, [rbp+var_28]
0x180029f49  test    rcx, rcx
0x180029f4c  jz      short loc_180029F5A
0x180029f4e  mov     rax, [rcx]
0x180029f51  mov     rax, [rax+10h]
0x180029f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f5a  xor     eax, eax
0x180029f5c  jmp     loc_180029ECB
0x180029f61  mov     rsi, [rbp+arg_18]
0x180029f65  test    rsi, rsi
0x180029f68  jnz     loc_18002A106
0x180029f6e  lock inc dword ptr [rdi+8]
0x180029f72  xor     ecx, ecx; hMem
0x180029f74  mov     [rbp+StringSid], rcx
0x180029f78  test    rdi, rdi
0x180029f7b  jnz     short loc_180029FE5
0x180029f7d  mov     [r15], rbx
0x180029f80  test    rcx, rcx
0x180029f83  jz      short loc_180029F8B
0x180029f85  call    cs:__imp_LocalFree
0x180029f8b  test    rdi, rdi
0x180029f8e  jz      short loc_180029F45
0x180029f90  mov     rcx, rdi; this
0x180029f93  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x180029f98  jmp     short loc_180029F45
0x180029f9a  mov     [r15], rbx
0x180029f9d  jmp     short loc_180029F45
0x180029f9f  mov     edx, 2DFh; void *
0x180029fa4  mov     rcx, [rbp+40h]; this
0x180029fa8  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180029faf  mov     r9d, esi; char *
0x180029fb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fb7  mov     rcx, [rbp+var_28]
0x180029fbb  test    rcx, rcx
0x180029fbe  jz      short loc_180029FCC
0x180029fc0  mov     rax, [rcx]
0x180029fc3  mov     rax, [rax+10h]
0x180029fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fcc  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180029fd3  mov     r8, rbx; lpMem
0x180029fd6  xor     edx, edx; dwFlags
0x180029fd8  call    cs:__imp_HeapFree
0x180029fde  mov     eax, esi
0x180029fe0  jmp     loc_180029ECB
0x180029fe5  lea     rcx, [rdi+9Ch]; Sid
0x180029fec  lea     rdx, [rbp+StringSid]; StringSid
0x180029ff0  call    cs:__imp_ConvertSidToStringSidW
0x180029ff6  test    eax, eax
0x180029ff8  jz      loc_18002A25E
0x180029ffe  mov     rcx, rdi; this
0x18002a001  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18002a006  mov     rdx, [rbp+StringSid]
0x18002a00a  lea     rcx, [rbp+arg_20]
0x18002a00e  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x18002a013  mov     r9, rbx
0x18002a016  mov     rcx, r14
0x18002a019  mov     r8d, eax
0x18002a01c  call    cs:__imp_QueryUserServiceName
0x18002a022  cmp     eax, 7Ah ; 'z'
0x18002a025  jnz     loc_18002A0B0
0x18002a02b  mov     edx, dword ptr [rbp+arg_20]
0x18002a02e  lea     rcx, [rbp+lpMem]
0x18002a032  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18002a037  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002a03e  mov     r8, rbx; lpMem
0x18002a041  xor     edx, edx; dwFlags
0x18002a043  mov     rsi, [rax]
0x18002a046  mov     qword ptr [rax], 0
0x18002a04d  call    cs:__imp_HeapFree
0x18002a053  mov     r8, [rbp+lpMem]; lpMem
0x18002a057  mov     [rbp+lpMem], 0
0x18002a05f  test    r8, r8
0x18002a062  jz      short loc_18002A073
0x18002a064  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002a06b  xor     edx, edx; dwFlags
0x18002a06d  call    cs:__imp_HeapFree
0x18002a073  mov     rcx, rdi; this
0x18002a076  call    ?GetSessionId@CToken@@QEAAKXZ; CToken::GetSessionId(void)
0x18002a07b  mov     rdx, [rbp+StringSid]
0x18002a07f  lea     rcx, [rbp+arg_20]
0x18002a083  mov     qword ptr [rsp+58h+var_38], rcx; unsigned int
0x18002a088  mov     r9, rsi
0x18002a08b  mov     rcx, r14
0x18002a08e  mov     r8d, eax
0x18002a091  call    cs:__imp_QueryUserServiceName
0x18002a097  test    eax, eax
0x18002a099  jnz     loc_18002A291
0x18002a09f  mov     rbx, rsi
0x18002a0a2  mov     rcx, [rbp+StringSid]
0x18002a0a6  mov     byte ptr [r12], 1
0x18002a0ab  jmp     loc_180029F7D
0x18002a0b0  test    eax, eax
0x18002a0b2  jz      short loc_18002A0A2
0x18002a0b4  mov     rcx, [rbp+40h]; this
0x18002a0b8  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a0bf  mov     r9d, eax; char *
0x18002a0c2  mov     edx, 30Fh; void *
0x18002a0c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a0cc  mov     rcx, [rbp+StringSid]; hMem
0x18002a0d0  mov     esi, eax
0x18002a0d2  test    rcx, rcx
0x18002a0d5  jz      loc_18002A284
0x18002a0db  call    cs:__imp_LocalFree
0x18002a0e1  mov     rcx, rdi; this
0x18002a0e4  call    ?Release@CToken@@UEAAKXZ; CToken::Release(void)
0x18002a0e9  jmp     loc_180029FB7
0x18002a0ee  mov     esi, 80070057h
0x18002a0f3  test    r8, r8
0x18002a0f6  jz      loc_180029E9F
0x18002a0fc  xor     ecx, ecx
0x18002a0fe  mov     [rbx], cx
0x18002a101  jmp     loc_180029E9F
0x18002a106  call    IsUMgrQueryUserContextPresent
0x18002a10b  test    al, al
0x18002a10d  jz      loc_18002A1CB
0x18002a113  lea     rdx, [rbp+hObject]
0x18002a117  mov     [rbp+hObject], 0
0x18002a11f  mov     rcx, rsi
0x18002a122  call    cs:__imp_UMgrQueryUserToken
0x18002a128  mov     edi, eax
0x18002a12a  test    eax, eax
0x18002a12c  js      short loc_18002A17B
0x18002a12e  mov     rcx, [rbp+hObject]; void *
0x18002a132  lea     rdx, [rbp+lpMem]; struct CToken **
0x18002a136  mov     [rbp+lpMem], 0
0x18002a13e  call    ?LookupOrCreateTokenFromHandle@@YAJPEAXPEAPEAVCToken@@@Z; LookupOrCreateTokenFromHandle(void *,CToken * *)
0x18002a143  mov     edi, eax
0x18002a145  test    eax, eax
0x18002a147  jnz     loc_18002A223
0x18002a14d  mov     rdi, [rbp+lpMem]
0x18002a151  jmp     loc_180029F72
0x18002a156  mov     rcx, [rbp+40h]; this
0x18002a15a  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a161  mov     r9d, 8007000Eh; char *
0x18002a167  mov     edx, 2CBh; void *
0x18002a16c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a171  mov     eax, 8007000Eh
0x18002a176  jmp     loc_180029ECB
0x18002a17b  mov     rcx, [rbp+40h]; this
0x18002a17f  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a186  mov     r9d, edi; char *
0x18002a189  mov     edx, 2F0h; void *
0x18002a18e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a193  mov     rcx, [rbp+var_28]
0x18002a197  test    rcx, rcx
0x18002a19a  jz      short loc_18002A1A8
0x18002a19c  mov     rax, [rcx]
0x18002a19f  mov     rax, [rax+10h]
0x18002a1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1a8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002a1af  mov     r8, rbx; lpMem
0x18002a1b2  xor     edx, edx; dwFlags
0x18002a1b4  call    cs:__imp_HeapFree
0x18002a1ba  mov     eax, edi
0x18002a1bc  jmp     loc_180029ECB
0x18002a1c1  mov     edx, 2DDh
0x18002a1c6  jmp     loc_180029FA4
0x18002a1cb  mov     rcx, [rbp+40h]; this
0x18002a1cf  lea     rax, aUserContextSpe_0; "User Context specified on a SKU that do"...
0x18002a1d6  mov     r9d, 80070005h; char *
0x18002a1dc  mov     qword ptr [rsp+58h+var_38], rax; int
0x18002a1e1  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a1e8  mov     edx, 2FAh; void *
0x18002a1ed  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002a1f2  mov     rcx, [rbp+var_28]
0x18002a1f6  test    rcx, rcx
0x18002a1f9  jz      short loc_18002A207
0x18002a1fb  mov     rax, [rcx]
0x18002a1fe  mov     rax, [rax+10h]
0x18002a202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a207  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002a20e  mov     r8, rbx; lpMem
0x18002a211  xor     edx, edx; dwFlags
0x18002a213  call    cs:__imp_HeapFree
0x18002a219  mov     eax, 80070005h
0x18002a21e  jmp     loc_180029ECB
0x18002a223  mov     rcx, [rbp+hObject]; hObject
0x18002a227  call    cs:__imp_CloseHandle
0x18002a22d  mov     rcx, [rbp+40h]; this
0x18002a231  lea     r8, aOnecoreComComb_27; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18002a238  mov     r9d, edi; char *
0x18002a23b  mov     edx, 2F5h; void *
0x18002a240  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002a245  mov     rcx, [rbp+lpMem]; this
  ... truncated ...
```
