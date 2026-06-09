# CIDLDataObj::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18001f0a0`
- end: `0x18001f5b0`
- name: `?GetData@CIDLDataObj@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `1296`
- prototype: `__int64 __fastcall(CIDLDataObj *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x18001f0a0`
- `0x180022c04`
- `0x1800237ac`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x1800548ac`
- `0x1800548fc`
- `0x18005494c`
- `0x180054a2c`
- `0x1800608fc`
- `0x1800616e8`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001f288`
- `KERNEL32!GetLastError` at `0x18001f3ad`
- `KERNEL32!GetLastError` at `0x18001f288`
- `KERNEL32!GetLastError` at `0x18001f3ad`
- `KERNEL32!DeactivateActCtx` at `0x18001f2ab`
- `KERNEL32!DeactivateActCtx` at `0x18001f3c8`
- `KERNEL32!DeactivateActCtx` at `0x18001f2ab`
- `KERNEL32!DeactivateActCtx` at `0x18001f3c8`
- `KERNEL32!SetLastError` at `0x18001f2bc`
- `KERNEL32!SetLastError` at `0x18001f3d7`
- `KERNEL32!SetLastError` at `0x18001f2bc`
- `KERNEL32!SetLastError` at `0x18001f3d7`
- `KERNEL32!GlobalAlloc` at `0x18001f1be`
- `KERNEL32!GlobalAlloc` at `0x18001f1be`
- `ole32!CreateStreamOnHGlobal` at `0x18001f470`
- `ole32!CreateStreamOnHGlobal` at `0x18001f470`
- `ole32!ReleaseStgMedium` at `0x18001f17a`
- `ole32!ReleaseStgMedium` at `0x18001f17a`

## string_xrefs

- `0x18001f263`: `DSA_GetItemPtr`
- `0x18001f38c`: `DSA_GetItemPtr`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIDLDataObj::GetData(CIDLDataObj *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // rbx
  unsigned int i; // r14d
  _DWORD *v8; // rcx
  int v9; // eax
  _WORD *ItemPtr; // rax
  STGMEDIUM *v11; // rax
  STGMEDIUM *v12; // rbx
  _DWORD *v13; // rax
  HRESULT StreamOnHGlobal; // ebx
  unsigned int j; // r12d
  _DWORD *v16; // r13
  int v17; // eax
  __int64 (__fastcall *v18)(_DWORD *, _QWORD); // r14
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r13
  __int64 (__fastcall *v23)(__int64, _QWORD); // r14
  __int64 v24; // rax
  int v25; // r13d
  __int64 v26; // rax
  __int64 v27; // r14
  IUnknown *v28; // rcx
  __int64 v29; // rcx
  DWORD dwErrCode; // [rsp+30h] [rbp-D0h]
  DWORD dwErrCodea; // [rsp+30h] [rbp-D0h]
  int v33; // [rsp+38h] [rbp-C8h]
  __int64 v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+40h] [rbp-C0h]
  ULONG_PTR ulCookie; // [rsp+48h] [rbp-B8h] BYREF
  ULONG_PTR Cookie[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h]
  _BYTE v40[560]; // [rsp+B0h] [rbp-50h] BYREF

  p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a3->hBitmap;
  a3->hBitmap = 0;
  a3->pUnkForRelease = 0;
  if ( !*((_DWORD *)this + 12) && a2->cfFormat == g_cfFileDescriptor )
  {
    CCreateFileGroupDescriptor::CCreateFileGroupDescriptor((CCreateFileGroupDescriptor *)v40);
    if ( (int)CCreateFileGroupDescriptor::BuildFileDescriptor(
                (CCreateFileGroupDescriptor *)v40,
                (struct IDataObject *)this,
                1) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v8 = (_DWORD *)*((_QWORD *)this + 7);
        v9 = v8 ? *v8 : 0;
        if ( (int)i >= v9 )
          break;
        ItemPtr = (_WORD *)IsolationAwareDSA_GetItemPtr(v8, i);
        if ( ItemPtr )
        {
          if ( *ItemPtr == g_cfFileContents )
          {
            v11 = (STGMEDIUM *)IsolationAwareDSA_GetItemPtr(*((_QWORD *)this + 8), i);
            v12 = v11;
            if ( v11 )
            {
              if ( v11->hBitmap )
              {
                ReleaseStgMedium(v11);
                v12->hBitmap = 0;
                v12->pUnkForRelease = 0;
              }
            }
          }
        }
      }
      CCreateFileGroupDescriptor::AddFileDescriptorToDataObj(
        (CCreateFileGroupDescriptor *)v40,
        (struct IDataObject *)this);
      *((_DWORD *)this + 12) = 1;
      p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a3->hBitmap;
    }
    CCreateFileGroupDescriptor::~CCreateFileGroupDescriptor((CCreateFileGroupDescriptor *)v40);
  }
  if ( a2->cfFormat == g_cfNotRecyclable )
  {
    v13 = GlobalAlloc(0, 4u);
    p_hBitmap->hBitmap = (HBITMAP)v13;
    if ( !v13 )
    {
LABEL_21:
      StreamOnHGlobal = -2147024882;
      goto LABEL_79;
    }
    a3->tymed = 1;
    *v13 = 1;
    return 0;
  }
  StreamOnHGlobal = -2147221404;
  if ( a2->cfFormat == g_cfEnterpriseId && (unsigned int)CIDLDataObj::_IsAddingEnterpriseIdRequired(this) )
    CIDLDataObj::_AddEnterpriseId(this);
  v35 = 0;
  for ( j = 0; ; ++j )
  {
    v16 = (_DWORD *)*((_QWORD *)this + 7);
    v17 = v16 ? *v16 : 0;
    if ( (int)j >= v17 )
      break;
    v18 = (__int64 (__fastcall *)(_DWORD *, _QWORD))`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn;
    if ( !`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn )
    {
      ulCookie = 0;
      if ( !IsolationAwarePrivateT_SAbnPgpgk
        && IsolationAwarePrivateT_SqbjaYRiRY == (_DWORD)`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn
        && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
      {
        continue;
      }
      v19 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DSA_GetItemPtr");
      v18 = (__int64 (__fastcall *)(_DWORD *, _QWORD))v19;
      if ( !IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( v19 )
        {
          v33 = 0;
          dwErrCode = 0;
        }
        else
        {
          v33 = 1;
          dwErrCode = GetLastError();
        }
        DeactivateActCtx(0, ulCookie);
        if ( v33 )
          SetLastError(dwErrCode);
      }
      if ( !v18 )
        continue;
      `IsolationAwareDSA_GetItemPtr'::`2'::s_pfn = (__int64)v18;
    }
    v20 = v18(v16, j);
    if ( !v20
      || *(_WORD *)v20 != a2->cfFormat
      || (a2->tymed & *(_DWORD *)(v20 + 24)) == 0
      || *(_DWORD *)(v20 + 16) != a2->dwAspect )
    {
      continue;
    }
    if ( g_cfFileContents == a2->cfFormat )
    {
      v21 = IsolationAwareDSA_GetItemPtr(*((_QWORD *)this + 8), j);
      if ( !v21 || !*(_QWORD *)(v21 + 8) )
        continue;
      if ( v35 != a2->lindex )
      {
        ++v35;
        continue;
      }
    }
    v22 = *((_QWORD *)this + 8);
    v34 = v22;
    v23 = (__int64 (__fastcall *)(__int64, _QWORD))`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn;
    if ( !`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn )
    {
      Cookie[0] = 0;
      if ( !IsolationAwarePrivateT_SAbnPgpgk
        && IsolationAwarePrivateT_SqbjaYRiRY == (_DWORD)`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn
        && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(Cookie) )
      {
        continue;
      }
      v24 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DSA_GetItemPtr");
      v23 = (__int64 (__fastcall *)(__int64, _QWORD))v24;
      if ( !IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( v24 )
        {
          v25 = 0;
          dwErrCodea = 0;
        }
        else
        {
          v25 = 1;
          dwErrCodea = GetLastError();
        }
        DeactivateActCtx(0, Cookie[0]);
        if ( v25 )
          SetLastError(dwErrCodea);
        v22 = v34;
      }
      if ( !v23 )
        continue;
      `IsolationAwareDSA_GetItemPtr'::`2'::s_pfn = (__int64)v23;
    }
    v26 = v23(v22, j);
    v27 = v26;
    if ( v26 )
    {
      *(_OWORD *)&a3->tymed = *(_OWORD *)v26;
      a3->pUnkForRelease = *(IUnknown **)(v26 + 16);
      if ( a3->hBitmap )
      {
        if ( a3->tymed == 1 )
        {
          _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
          a3->pUnkForRelease = (IUnknown *)this;
          return 0;
        }
        if ( a3->tymed == 4 )
        {
          StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, HBITMAP *))(**(_QWORD **)(v26 + 8) + 104LL))(
                              *(_QWORD *)(v26 + 8),
                              &a3->hBitmap);
          if ( StreamOnHGlobal < 0 )
          {
            StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &a3->pstm);
            if ( StreamOnHGlobal >= 0 )
            {
              memset_0(v38, 0, 0x50u);
              if ( (*(int (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(v27 + 8) + 96LL))(
                     *(_QWORD *)(v27 + 8),
                     v38,
                     1) < 0 )
                goto LABEL_21;
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v27 + 8) + 40LL))(
                *(_QWORD *)(v27 + 8),
                0,
                0,
                0);
              StreamOnHGlobal = (*(__int64 (__fastcall **)(_QWORD, HBITMAP, __int64, _QWORD, _QWORD))(**(_QWORD **)(v27 + 8) + 56LL))(
                                  *(_QWORD *)(v27 + 8),
                                  a3->hBitmap,
                                  v39,
                                  0,
                                  0);
              (*(void (__fastcall **)(HBITMAP, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3->hBitmap + 40LL))(
                a3->hBitmap,
                0,
                0,
                0);
              v28 = *(IUnknown **)(v27 + 16);
              a3->pUnkForRelease = v28;
              if ( v28 )
                ((void (__fastcall *)(IUnknown *))v28->lpVtbl->AddRef)(v28);
            }
          }
          if ( StreamOnHGlobal != -2147221404 )
            goto LABEL_78;
        }
      }
      break;
    }
  }
  v29 = *((_QWORD *)this + 3);
  if ( !v29 )
    goto LABEL_79;
  StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, struct tagFORMATETC *, struct tagSTGMEDIUM *))(*(_QWORD *)v29 + 24LL))(
                      v29,
                      a2,
                      a3);
LABEL_78:
  if ( StreamOnHGlobal < 0 )
  {
LABEL_79:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
        (unsigned int)StreamOnHGlobal);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18001f0a0  mov     [rsp-8+arg_18], rbx
0x18001f0a5  push    rbp
0x18001f0a6  push    rsi
0x18001f0a7  push    rdi
0x18001f0a8  push    r12
0x18001f0aa  push    r13
0x18001f0ac  push    r14
0x18001f0ae  push    r15
0x18001f0b0  lea     rbp, [rsp-1F0h]
0x18001f0b8  sub     rsp, 2F0h
0x18001f0bf  mov     rax, cs:__security_cookie
0x18001f0c6  xor     rax, rsp
0x18001f0c9  mov     [rbp+220h+var_40], rax
0x18001f0d0  mov     rsi, r8
0x18001f0d3  mov     r15, rdx
0x18001f0d6  mov     rdi, rcx
0x18001f0d9  lea     rbx, [r8+8]
0x18001f0dd  mov     qword ptr [rbx], 0
0x18001f0e4  mov     qword ptr [r8+10h], 0
0x18001f0ec  mov     r13d, 1
0x18001f0f2  cmp     dword ptr [rcx+30h], 0
0x18001f0f6  jnz     loc_18001F1AA
0x18001f0fc  movzx   eax, cs:?g_cfFileDescriptor@@3GA; ushort g_cfFileDescriptor
0x18001f103  cmp     [rdx], ax
0x18001f106  jnz     loc_18001F1AA
0x18001f10c  lea     rcx, [rbp+220h+var_270]; this
0x18001f110  call    ??0CCreateFileGroupDescriptor@@QEAA@XZ; CCreateFileGroupDescriptor::CCreateFileGroupDescriptor(void)
0x18001f115  nop
0x18001f116  mov     r8d, r13d; int
0x18001f119  mov     rdx, rdi; struct IDataObject *
0x18001f11c  lea     rcx, [rbp+220h+var_270]; this
0x18001f120  call    ?BuildFileDescriptor@CCreateFileGroupDescriptor@@QEAAJPEAUIDataObject@@H@Z; CCreateFileGroupDescriptor::BuildFileDescriptor(IDataObject *,int)
0x18001f125  test    eax, eax
0x18001f127  js      short loc_18001F1A1
0x18001f129  xor     r14d, r14d
0x18001f12c  xor     r12d, r12d
0x18001f12f  mov     rcx, [rdi+38h]
0x18001f133  test    rcx, rcx
0x18001f136  jz      short loc_18001F13C
0x18001f138  mov     eax, [rcx]
0x18001f13a  jmp     short loc_18001F13F
0x18001f13c  mov     eax, r12d
0x18001f13f  cmp     r14d, eax
0x18001f142  jge     short loc_18001F18D
0x18001f144  mov     edx, r14d
0x18001f147  call    IsolationAwareDSA_GetItemPtr
0x18001f14c  test    rax, rax
0x18001f14f  jz      short loc_18001F188
0x18001f151  movzx   ecx, cs:?g_cfFileContents@@3GA; ushort g_cfFileContents
0x18001f158  cmp     [rax], cx
0x18001f15b  jnz     short loc_18001F188
0x18001f15d  mov     edx, r14d
0x18001f160  mov     rcx, [rdi+40h]
0x18001f164  call    IsolationAwareDSA_GetItemPtr
0x18001f169  mov     rbx, rax
0x18001f16c  test    rax, rax
0x18001f16f  jz      short loc_18001F188
0x18001f171  cmp     [rax+8], r12
0x18001f175  jz      short loc_18001F188
0x18001f177  mov     rcx, rax; LPSTGMEDIUM
0x18001f17a  call    cs:__imp_ReleaseStgMedium
0x18001f180  mov     [rbx+8], r12
0x18001f184  mov     [rbx+10h], r12
0x18001f188  add     r14d, r13d
0x18001f18b  jmp     short loc_18001F12F
0x18001f18d  mov     rdx, rdi; struct IDataObject *
0x18001f190  lea     rcx, [rbp+220h+var_270]; this
0x18001f194  call    ?AddFileDescriptorToDataObj@CCreateFileGroupDescriptor@@QEAAJPEAUIDataObject@@@Z; CCreateFileGroupDescriptor::AddFileDescriptorToDataObj(IDataObject *)
0x18001f199  mov     [rdi+30h], r13d
0x18001f19d  lea     rbx, [rsi+8]
0x18001f1a1  lea     rcx, [rbp+220h+var_270]; this
0x18001f1a5  call    ??1CCreateFileGroupDescriptor@@QEAA@XZ; CCreateFileGroupDescriptor::~CCreateFileGroupDescriptor(void)
0x18001f1aa  movzx   eax, word ptr [r15]
0x18001f1ae  cmp     ax, cs:?g_cfNotRecyclable@@3GA; ushort g_cfNotRecyclable
0x18001f1b5  jnz     short loc_18001F1E3
0x18001f1b7  mov     edx, 4; dwBytes
0x18001f1bc  xor     ecx, ecx; uFlags
0x18001f1be  call    cs:__imp_GlobalAlloc
0x18001f1c4  mov     [rbx], rax
0x18001f1c7  test    rax, rax
0x18001f1ca  jz      short loc_18001F1D9
0x18001f1cc  mov     [rsi], r13d
0x18001f1cf  mov     [rax], r13d
0x18001f1d2  xor     ebx, ebx
0x18001f1d4  jmp     loc_18001F584
0x18001f1d9  mov     ebx, 8007000Eh
0x18001f1de  jmp     loc_18001F553
0x18001f1e3  mov     ebx, 80040064h
0x18001f1e8  cmp     ax, cs:?g_cfEnterpriseId@@3GA; ushort g_cfEnterpriseId
0x18001f1ef  jnz     short loc_18001F205
0x18001f1f1  mov     rcx, rdi; this
0x18001f1f4  call    ?_IsAddingEnterpriseIdRequired@CIDLDataObj@@AEAAHXZ; CIDLDataObj::_IsAddingEnterpriseIdRequired(void)
0x18001f1f9  test    eax, eax
0x18001f1fb  jz      short loc_18001F205
0x18001f1fd  mov     rcx, rdi; this
0x18001f200  call    ?_AddEnterpriseId@CIDLDataObj@@AEAAXXZ; CIDLDataObj::_AddEnterpriseId(void)
0x18001f205  mov     [rsp+320h+var_2E0], 0
0x18001f20d  xor     r12d, r12d
0x18001f210  mov     r13, [rdi+38h]
0x18001f214  test    r13, r13
0x18001f217  jz      short loc_18001F21F
0x18001f219  mov     eax, [r13+0]
0x18001f21d  jmp     short loc_18001F221
0x18001f21f  xor     eax, eax
0x18001f221  cmp     r12d, eax
0x18001f224  jge     loc_18001F532
0x18001f22a  mov     r14, cs:?s_pfn@?1??IsolationAwareDSA_GetItemPtr@@9@4P6APEAXPEAU_DSA@@H@ZEA; void * (*`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn)(_DSA *,int)
0x18001f231  test    r14, r14
0x18001f234  jnz     loc_18001F2D2
0x18001f23a  mov     [rsp+320h+ulCookie], r14
0x18001f23f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001f246  jnz     short loc_18001F263
0x18001f248  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001f24f  jnz     short loc_18001F263
0x18001f251  lea     rcx, [rsp+320h+ulCookie]; lpCookie
0x18001f256  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001f25b  test    eax, eax
0x18001f25d  jz      loc_18001F404
0x18001f263  lea     rcx, aDsaGetitemptr; "DSA_GetItemPtr"
0x18001f26a  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001f26f  mov     r14, rax
0x18001f272  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001f279  jnz     short loc_18001F2C2
0x18001f27b  test    rax, rax
0x18001f27e  jnz     short loc_18001F294
0x18001f280  mov     dword ptr [rsp+320h+var_2E8], 1
0x18001f288  call    cs:__imp_GetLastError
0x18001f28e  mov     [rsp+320h+dwErrCode], eax
0x18001f292  jmp     short loc_18001F2A4
0x18001f294  mov     dword ptr [rsp+320h+var_2E8], 0
0x18001f29c  mov     [rsp+320h+dwErrCode], 0
0x18001f2a4  mov     rdx, [rsp+320h+ulCookie]; ulCookie
0x18001f2a9  xor     ecx, ecx; dwFlags
0x18001f2ab  call    cs:__imp_DeactivateActCtx
0x18001f2b1  cmp     dword ptr [rsp+320h+var_2E8], 0
0x18001f2b6  jz      short loc_18001F2C2
0x18001f2b8  mov     ecx, [rsp+320h+dwErrCode]; dwErrCode
0x18001f2bc  call    cs:__imp_SetLastError
0x18001f2c2  test    r14, r14
0x18001f2c5  jz      loc_18001F404
0x18001f2cb  mov     cs:?s_pfn@?1??IsolationAwareDSA_GetItemPtr@@9@4P6APEAXPEAU_DSA@@H@ZEA, r14; void * (*`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn)(_DSA *,int)
0x18001f2d2  mov     edx, r12d
0x18001f2d5  mov     rcx, r13
0x18001f2d8  mov     rax, r14
0x18001f2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2e0  test    rax, rax
0x18001f2e3  jz      loc_18001F404
0x18001f2e9  movzx   edx, word ptr [r15]
0x18001f2ed  cmp     [rax], dx
0x18001f2f0  jnz     loc_18001F404
0x18001f2f6  mov     ecx, [r15+18h]
0x18001f2fa  test    [rax+18h], ecx
0x18001f2fd  jz      loc_18001F404
0x18001f303  mov     ecx, [r15+10h]
0x18001f307  cmp     [rax+10h], ecx
0x18001f30a  jnz     loc_18001F404
0x18001f310  cmp     cs:?g_cfFileContents@@3GA, dx; ushort g_cfFileContents
0x18001f317  jnz     short loc_18001F34E
0x18001f319  mov     edx, r12d
0x18001f31c  mov     rcx, [rdi+40h]
0x18001f320  call    IsolationAwareDSA_GetItemPtr
0x18001f325  test    rax, rax
0x18001f328  jz      loc_18001F404
0x18001f32e  cmp     qword ptr [rax+8], 0
0x18001f333  jz      loc_18001F404
0x18001f339  mov     eax, [rsp+320h+var_2E0]
0x18001f33d  cmp     eax, [r15+14h]
0x18001f341  jz      short loc_18001F34E
0x18001f343  inc     eax
0x18001f345  mov     [rsp+320h+var_2E0], eax
0x18001f349  jmp     loc_18001F404
0x18001f34e  mov     r13, [rdi+40h]
0x18001f352  mov     [rsp+320h+var_2E8], r13
0x18001f357  mov     r14, cs:?s_pfn@?1??IsolationAwareDSA_GetItemPtr@@9@4P6APEAXPEAU_DSA@@H@ZEA; void * (*`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn)(_DSA *,int)
0x18001f35e  test    r14, r14
0x18001f361  jnz     loc_18001F3EE
0x18001f367  mov     [rsp+320h+Cookie], r14
0x18001f36c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001f373  jnz     short loc_18001F38C
0x18001f375  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001f37c  jnz     short loc_18001F38C
0x18001f37e  lea     rcx, [rsp+320h+Cookie]; lpCookie
0x18001f383  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001f388  test    eax, eax
0x18001f38a  jz      short loc_18001F404
0x18001f38c  lea     rcx, aDsaGetitemptr; "DSA_GetItemPtr"
0x18001f393  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001f398  mov     r14, rax
0x18001f39b  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001f3a2  jnz     short loc_18001F3E2
0x18001f3a4  test    rax, rax
0x18001f3a7  jnz     short loc_18001F3B9
0x18001f3a9  lea     r13d, [rax+1]
0x18001f3ad  call    cs:__imp_GetLastError
0x18001f3b3  mov     [rsp+320h+dwErrCode], eax
0x18001f3b7  jmp     short loc_18001F3C1
0x18001f3b9  xor     r13d, r13d
0x18001f3bc  mov     [rsp+320h+dwErrCode], r13d
0x18001f3c1  mov     rdx, [rsp+320h+Cookie]; ulCookie
0x18001f3c6  xor     ecx, ecx; dwFlags
0x18001f3c8  call    cs:__imp_DeactivateActCtx
0x18001f3ce  test    r13d, r13d
0x18001f3d1  jz      short loc_18001F3DD
0x18001f3d3  mov     ecx, [rsp+320h+dwErrCode]; dwErrCode
0x18001f3d7  call    cs:__imp_SetLastError
0x18001f3dd  mov     r13, [rsp+320h+var_2E8]
0x18001f3e2  test    r14, r14
0x18001f3e5  jz      short loc_18001F404
0x18001f3e7  mov     cs:?s_pfn@?1??IsolationAwareDSA_GetItemPtr@@9@4P6APEAXPEAU_DSA@@H@ZEA, r14; void * (*`IsolationAwareDSA_GetItemPtr'::`2'::s_pfn)(_DSA *,int)
0x18001f3ee  mov     edx, r12d
0x18001f3f1  mov     rcx, r13
0x18001f3f4  mov     rax, r14
0x18001f3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3fc  mov     r14, rax
0x18001f3ff  test    rax, rax
0x18001f402  jnz     short loc_18001F40C
0x18001f404  inc     r12d
0x18001f407  jmp     loc_18001F210
0x18001f40c  movups  xmm0, xmmword ptr [rax]
0x18001f40f  movups  xmmword ptr [rsi], xmm0
0x18001f412  movsd   xmm1, qword ptr [rax+10h]
0x18001f417  movsd   qword ptr [rsi+10h], xmm1
0x18001f41c  cmp     qword ptr [rsi+8], 0
0x18001f421  jz      loc_18001F532
0x18001f427  mov     r13d, 1
0x18001f42d  cmp     [rsi], r13d
0x18001f430  jnz     short loc_18001F440
0x18001f432  lock add [rdi+10h], r13d
0x18001f437  mov     [rsi+10h], rdi
0x18001f43b  jmp     loc_18001F1D2
0x18001f440  cmp     dword ptr [rsi], 4
0x18001f443  jnz     loc_18001F532
0x18001f449  mov     rcx, [rax+8]
0x18001f44d  mov     rax, [rcx]
0x18001f450  lea     rdx, [rsi+8]
0x18001f454  mov     rax, [rax+68h]
0x18001f458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f45d  mov     ebx, eax
0x18001f45f  test    eax, eax
0x18001f461  jns     loc_18001F52A
0x18001f467  lea     r8, [rsi+8]; ppstm
0x18001f46b  mov     edx, r13d; fDeleteOnRelease
0x18001f46e  xor     ecx, ecx; hGlobal
0x18001f470  call    cs:__imp_CreateStreamOnHGlobal
0x18001f476  mov     ebx, eax
0x18001f478  test    eax, eax
0x18001f47a  js      loc_18001F52A
0x18001f480  xor     edx, edx; Val
0x18001f482  lea     r8d, [rdx+50h]; Size
0x18001f486  lea     rcx, [rsp+320h+var_2C0]; void *
0x18001f48b  call    memset_0
0x18001f490  mov     rcx, [r14+8]
0x18001f494  mov     rax, [rcx]
0x18001f497  mov     r8d, r13d
0x18001f49a  lea     rdx, [rsp+320h+var_2C0]
0x18001f49f  mov     rax, [rax+60h]
0x18001f4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a8  test    eax, eax
0x18001f4aa  js      loc_18001F1D9
0x18001f4b0  mov     rcx, [r14+8]
0x18001f4b4  mov     rax, [rcx]
0x18001f4b7  xor     r9d, r9d
0x18001f4ba  xor     r8d, r8d
0x18001f4bd  mov     rdx, cs:qword_180082C10
0x18001f4c4  mov     rax, [rax+28h]
0x18001f4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4cd  mov     rcx, [r14+8]
0x18001f4d1  mov     rax, [rcx]
0x18001f4d4  mov     [rsp+320h+var_300], 0
0x18001f4dd  xor     r9d, r9d
0x18001f4e0  mov     r8, [rsp+320h+var_2B0]
0x18001f4e5  mov     rdx, [rsi+8]
0x18001f4e9  mov     rax, [rax+38h]
0x18001f4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f2  mov     ebx, eax
0x18001f4f4  mov     rcx, [rsi+8]
0x18001f4f8  mov     rax, [rcx]
0x18001f4fb  xor     r9d, r9d
0x18001f4fe  xor     r8d, r8d
0x18001f501  mov     rdx, cs:qword_180082C10
0x18001f508  mov     rax, [rax+28h]
0x18001f50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f511  mov     rcx, [r14+10h]
0x18001f515  mov     [rsi+10h], rcx
0x18001f519  test    rcx, rcx
0x18001f51c  jz      short loc_18001F52A
0x18001f51e  mov     rax, [rcx]
0x18001f521  mov     rax, [rax+8]
0x18001f525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f52a  cmp     ebx, 80040064h
0x18001f530  jnz     short loc_18001F54F
0x18001f532  mov     rcx, [rdi+18h]
0x18001f536  test    rcx, rcx
0x18001f539  jz      short loc_18001F553
0x18001f53b  mov     rax, [rcx]
0x18001f53e  mov     r8, rsi
0x18001f541  mov     rdx, r15
0x18001f544  mov     rax, [rax+18h]
0x18001f548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f54d  mov     ebx, eax
  ... truncated ...
```
