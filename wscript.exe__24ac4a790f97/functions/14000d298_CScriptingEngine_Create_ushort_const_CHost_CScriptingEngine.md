# CScriptingEngine::Create(ushort const *,CHost *,CScriptingEngine * *)

- ea: `0x14000d298`
- end: `0x14000d5b6`
- name: `?Create@CScriptingEngine@@SAJPEBGPEAVCHost@@PEAPEAV1@@Z`
- size: `798`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, struct CHost *, struct CScriptingEngine **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007930`

## callees

- `0x140001008`
- `0x14000d298`
- `0x1400148c4`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x14000d3dd`
- `ole32!CLSIDFromString` at `0x14000d3dd`
- `ole32!CoCreateInstance` at `0x14000d409`
- `ole32!CoCreateInstance` at `0x14000d409`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::Create(LPCOLESTR lpsz, struct CHost *a2, struct CScriptingEngine **a3)
{
  int v4; // r15d
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  HRESULT v9; // edi
  _QWORD *v10; // rsi
  char v11; // al
  unsigned int v12; // eax
  LPVOID ppv; // [rsp+30h] [rbp-58h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-50h] BYREF

  pclsid = 0;
  v4 = 0;
  ppv = 0;
  v7 = operator new(0xB8u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
    goto LABEL_16;
  }
  v7[4] = &IActiveScriptSiteWldp::`vftable';
  v7[5] = &CUnknown::`vftable';
  v7[8] = &CUnknown::InnerUnknown::`vftable';
  *((_DWORD *)v7 + 18) = 1;
  v7[6] = v7 + 8;
  v7[7] = v7;
  _InterlockedIncrement(&Global::g_cObjects);
  v7[12] = 0;
  *v7 = &CScriptingEngine::`vftable'{for `IActiveScriptSite'};
  v7[15] = 0;
  v7[1] = &CScriptingEngine::`vftable'{for `IActiveScriptSiteDebug64'};
  v7[16] = 0;
  v7[2] = &CScriptingEngine::`vftable'{for `IActiveScriptSiteWindow'};
  v7[3] = &CScriptingEngine::`vftable'{for `IPrivateScriptSite'};
  v7[4] = &CScriptingEngine::`vftable'{for `IActiveScriptSiteWldp'};
  v7[5] = &CScriptingEngine::`vftable'{for `CUnknown'};
  v7[10] = &CScriptingEngine::`vftable'{for `IOleCommandTarget'};
  *((_DWORD *)v7 + 34) = 0;
  v7[13] = 0;
  v7[14] = 0;
  v7[18] = 0;
  v7[19] = 0;
  v7[20] = 0;
  v7[21] = 0;
  *((_WORD *)v7 + 88) = 0;
  *((_DWORD *)v7 + 22) = 0;
  v9 = CCharSink::Init((CCharSink *)(v7 + 15), 0x1000u);
  if ( v9 >= 0 )
  {
    v8[14] = a2;
    v9 = CLSIDFromString(lpsz, &pclsid);
    if ( v9 >= 0 )
    {
      v9 = CoCreateInstance(&pclsid, 0, 0x17u, &IID_IUnknown, &ppv);
      if ( v9 >= 0 )
      {
        v10 = v8 + 12;
        v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(ppv, &IID_IActiveScript, (__int64)(v8 + 12));
        if ( v9 >= 0 )
        {
          v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))ppv)(
                 ppv,
                 &IID_IActiveScriptParse64,
                 (__int64)(v8 + 13));
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v10 + 24LL))(*v10, v8);
            if ( v9 >= 0 )
            {
              v4 = 1;
              v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v8[13] + 24LL))(v8[13]);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)*v10 + 64LL))(
                       *v10,
                       L"WScript",
                       2);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)*v10 + 64LL))(
                         *v10,
                         L"WSH",
                         2);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v10 + 40LL))(*v10, 5);
                    if ( v9 >= 0 )
                    {
                      v11 = *((_BYTE *)a2 + 71);
                      *((_BYTE *)v8 + 176) = v11;
                      if ( !v11
                        || (v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*v10)(
                                   *v10,
                                   &IID_IActiveScriptDebug64,
                                   (__int64)(v8 + 21)),
                            v9 >= 0) )
                      {
                        v9 = 0;
                        v12 = CScriptingEngine::m_contextCount + 1;
                        *((_DWORD *)v8 + 22) = CScriptingEngine::m_contextCount + 1;
                        *a3 = (struct CScriptingEngine *)v8;
                        CScriptingEngine::m_contextCount = v12;
LABEL_16:
                        v8 = 0;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
  {
    if ( v4 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8[12] + 56LL))(v8[12]);
    (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000d298  mov     [rsp+arg_8], rbx
0x14000d29d  push    rbp
0x14000d29e  push    rsi
0x14000d29f  push    rdi
0x14000d2a0  push    r12
0x14000d2a2  push    r13
0x14000d2a4  push    r14
0x14000d2a6  push    r15
0x14000d2a8  sub     rsp, 50h
0x14000d2ac  mov     rax, cs:__security_cookie
0x14000d2b3  xor     rax, rsp
0x14000d2b6  mov     [rsp+88h+var_40], rax
0x14000d2bb  mov     rsi, rcx
0x14000d2be  xorps   xmm0, xmm0
0x14000d2c1  xor     r13d, r13d
0x14000d2c4  mov     ecx, 0B8h; Size
0x14000d2c9  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x14000d2ce  mov     r15d, r13d
0x14000d2d1  mov     [rsp+88h+var_58], r13
0x14000d2d6  mov     r12, r8
0x14000d2d9  mov     rbp, rdx
0x14000d2dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000d2e1  mov     rbx, rax
0x14000d2e4  test    rax, rax
0x14000d2e7  jz      loc_14000D548
0x14000d2ed  lea     rax, ??_7IActiveScriptSiteWldp@@6B@; const IActiveScriptSiteWldp::`vftable'
0x14000d2f4  mov     [rbx+20h], rax
0x14000d2f8  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x14000d2ff  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x14000d306  mov     [rbx+28h], rax
0x14000d30a  lea     rax, [rbx+40h]
0x14000d30e  mov     [rax], rcx
0x14000d311  mov     dword ptr [rax+8], 1
0x14000d318  mov     [rbx+30h], rax
0x14000d31c  mov     [rbx+38h], rbx
0x14000d320  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x14000d327  lea     rax, ??_7CScriptingEngine@@6BIActiveScriptSite@@@; const CScriptingEngine::`vftable'{for `IActiveScriptSite'}
0x14000d32e  mov     [rbx+60h], r13
0x14000d332  mov     [rbx], rax
0x14000d335  lea     rcx, [rbx+78h]; this
0x14000d339  lea     rax, ??_7CScriptingEngine@@6BIActiveScriptSiteDebug64@@@; const CScriptingEngine::`vftable'{for `IActiveScriptSiteDebug64'}
0x14000d340  mov     [rbx+78h], r13
0x14000d344  mov     [rbx+8], rax
0x14000d348  mov     edx, 1000h; unsigned int
0x14000d34d  lea     rax, ??_7CScriptingEngine@@6BIActiveScriptSiteWindow@@@; const CScriptingEngine::`vftable'{for `IActiveScriptSiteWindow'}
0x14000d354  mov     [rbx+80h], r13
0x14000d35b  mov     [rbx+10h], rax
0x14000d35f  lea     rax, ??_7CScriptingEngine@@6BIPrivateScriptSite@@@; const CScriptingEngine::`vftable'{for `IPrivateScriptSite'}
0x14000d366  mov     [rbx+18h], rax
0x14000d36a  lea     rax, ??_7CScriptingEngine@@6BIActiveScriptSiteWldp@@@; const CScriptingEngine::`vftable'{for `IActiveScriptSiteWldp'}
0x14000d371  mov     [rbx+20h], rax
0x14000d375  lea     rax, ??_7CScriptingEngine@@6BCUnknown@@@; const CScriptingEngine::`vftable'{for `CUnknown'}
0x14000d37c  mov     [rbx+28h], rax
0x14000d380  lea     rax, ??_7CScriptingEngine@@6BIOleCommandTarget@@@; const CScriptingEngine::`vftable'{for `IOleCommandTarget'}
0x14000d387  mov     [rbx+50h], rax
0x14000d38b  mov     [rbx+88h], r13d
0x14000d392  mov     [rbx+68h], r13
0x14000d396  mov     [rbx+70h], r13
0x14000d39a  mov     [rbx+90h], r13
0x14000d3a1  mov     [rbx+98h], r13
0x14000d3a8  mov     [rbx+0A0h], r13
0x14000d3af  mov     [rbx+0A8h], r13
0x14000d3b6  mov     [rbx+0B0h], r13w
0x14000d3be  mov     [rbx+58h], r13d
0x14000d3c2  call    ?Init@CCharSink@@QEAAJK@Z; CCharSink::Init(ulong)
0x14000d3c7  mov     edi, eax
0x14000d3c9  test    eax, eax
0x14000d3cb  js      loc_14000D550
0x14000d3d1  lea     rdx, [rsp+88h+pclsid]; pclsid
0x14000d3d6  mov     [rbx+70h], rbp
0x14000d3da  mov     rcx, rsi; lpsz
0x14000d3dd  call    cs:__imp_CLSIDFromString
0x14000d3e3  mov     edi, eax
0x14000d3e5  test    eax, eax
0x14000d3e7  js      loc_14000D550
0x14000d3ed  lea     rax, [rsp+88h+var_58]
0x14000d3f2  xor     edx, edx; pUnkOuter
0x14000d3f4  lea     r9, IID_IUnknown; riid
0x14000d3fb  mov     [rsp+88h+ppv], rax; ppv
0x14000d400  lea     r8d, [r13+17h]; dwClsContext
0x14000d404  lea     rcx, [rsp+88h+pclsid]; rclsid
0x14000d409  call    cs:__imp_CoCreateInstance
0x14000d40f  mov     edi, eax
0x14000d411  test    eax, eax
0x14000d413  js      loc_14000D550
0x14000d419  mov     rcx, [rsp+88h+var_58]
0x14000d41e  lea     rsi, [rbx+60h]
0x14000d422  mov     r8, rsi
0x14000d425  lea     rdx, IID_IActiveScript
0x14000d42c  mov     rax, [rcx]
0x14000d42f  mov     rax, [rax]
0x14000d432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d437  mov     edi, eax
0x14000d439  test    eax, eax
0x14000d43b  js      loc_14000D550
0x14000d441  mov     rcx, [rsp+88h+var_58]
0x14000d446  lea     r8, [rbx+68h]
0x14000d44a  lea     rdx, IID_IActiveScriptParse64
0x14000d451  mov     rax, [rcx]
0x14000d454  mov     rax, [rax]
0x14000d457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d45c  mov     edi, eax
0x14000d45e  test    eax, eax
0x14000d460  js      loc_14000D550
0x14000d466  mov     rcx, [rsi]
0x14000d469  mov     rdx, rbx
0x14000d46c  mov     rax, [rcx]
0x14000d46f  mov     rax, [rax+18h]
0x14000d473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d478  mov     edi, eax
0x14000d47a  test    eax, eax
0x14000d47c  js      loc_14000D550
0x14000d482  mov     rcx, [rbx+68h]
0x14000d486  lea     r15d, [r13+1]
0x14000d48a  mov     rax, [rcx]
0x14000d48d  mov     rax, [rax+18h]
0x14000d491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d496  mov     edi, eax
0x14000d498  test    eax, eax
0x14000d49a  js      loc_14000D550
0x14000d4a0  mov     rcx, [rsi]
0x14000d4a3  lea     r14d, [r13+2]
0x14000d4a7  mov     r8d, r14d
0x14000d4aa  lea     rdx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x14000d4b1  mov     rax, [rcx]
0x14000d4b4  mov     rax, [rax+40h]
0x14000d4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4bd  mov     edi, eax
0x14000d4bf  test    eax, eax
0x14000d4c1  js      loc_14000D550
0x14000d4c7  mov     rcx, [rsi]
0x14000d4ca  lea     rdx, ?GWSZ_WSH@@3QBGB; "WSH"
0x14000d4d1  mov     r8d, r14d
0x14000d4d4  mov     rax, [rcx]
0x14000d4d7  mov     rax, [rax+40h]
0x14000d4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4e0  mov     edi, eax
0x14000d4e2  test    eax, eax
0x14000d4e4  js      short loc_14000D550
0x14000d4e6  mov     rcx, [rsi]
0x14000d4e9  lea     edx, [r13+5]
0x14000d4ed  mov     rax, [rcx]
0x14000d4f0  mov     rax, [rax+28h]
0x14000d4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4f9  mov     edi, eax
0x14000d4fb  test    eax, eax
0x14000d4fd  js      short loc_14000D550
0x14000d4ff  mov     al, [rbp+47h]
0x14000d502  mov     [rbx+0B0h], al
0x14000d508  test    al, al
0x14000d50a  jz      short loc_14000D52E
0x14000d50c  mov     rcx, [rsi]
0x14000d50f  lea     r8, [rbx+0A8h]
0x14000d516  lea     rdx, IID_IActiveScriptDebug64
0x14000d51d  mov     rax, [rcx]
0x14000d520  mov     rax, [rax]
0x14000d523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d528  mov     edi, eax
0x14000d52a  test    eax, eax
0x14000d52c  js      short loc_14000D550
0x14000d52e  mov     eax, cs:?m_contextCount@CScriptingEngine@@0KA; ulong CScriptingEngine::m_contextCount
0x14000d534  mov     edi, r13d
0x14000d537  inc     eax
0x14000d539  mov     [rbx+58h], eax
0x14000d53c  mov     [r12], rbx
0x14000d540  mov     cs:?m_contextCount@CScriptingEngine@@0KA, eax; ulong CScriptingEngine::m_contextCount
0x14000d546  jmp     short loc_14000D54D
0x14000d548  mov     edi, 8007000Eh
0x14000d54d  mov     rbx, r13
0x14000d550  mov     rcx, [rsp+88h+var_58]
0x14000d555  test    rcx, rcx
0x14000d558  jz      short loc_14000D566
0x14000d55a  mov     rax, [rcx]
0x14000d55d  mov     rax, [rax+10h]
0x14000d561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d566  test    rbx, rbx
0x14000d569  jz      short loc_14000D58F
0x14000d56b  test    r15d, r15d
0x14000d56e  jz      short loc_14000D580
0x14000d570  mov     rcx, [rbx+60h]
0x14000d574  mov     rax, [rcx]
0x14000d577  mov     rax, [rax+38h]
0x14000d57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d580  mov     rax, [rbx]
0x14000d583  mov     rcx, rbx
0x14000d586  mov     rax, [rax+10h]
0x14000d58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d58f  mov     eax, edi
0x14000d591  mov     rcx, [rsp+88h+var_40]
0x14000d596  xor     rcx, rsp; StackCookie
0x14000d599  call    __security_check_cookie
0x14000d59e  mov     rbx, [rsp+88h+arg_8]
0x14000d5a6  add     rsp, 50h
0x14000d5aa  pop     r15
0x14000d5ac  pop     r14
0x14000d5ae  pop     r13
0x14000d5b0  pop     r12
0x14000d5b2  pop     rdi
0x14000d5b3  pop     rsi
0x14000d5b4  pop     rbp
0x14000d5b5  retn
```
