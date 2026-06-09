# CVssSidCollection::AddWellKnownSid(WELL_KNOWN_SID_TYPE,VSS_ACCESS_CONTROL)

- ea: `0x18003c4ac`
- end: `0x18003c75c`
- name: `?AddWellKnownSid@CVssSidCollection@@AEAAXW4WELL_KNOWN_SID_TYPE@@W4VSS_ACCESS_CONTROL@@@Z`
- size: `688`
- prototype: `void __fastcall(__int64, WELL_KNOWN_SID_TYPE, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ced0`

## callees

- `0x18000212c`
- `0x1800036e8`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800377c4`
- `0x18003bc08`
- `0x18003c4ac`
- `0x18003c764`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c5c2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c564`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c644`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c564`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c644`

## string_xrefs

- `0x18003c4d2`: `base\stor\vss\modules\sec\security.cxx`
- `0x18003c4de`: `CVssSidCollection::AddWellKnownSid`
- `0x18003c5ac`: `CreateWellKnownSid(type, NULL, NULL, &dwSid)`
- `0x18003c60b`: `CreateWellKnownSid(type, NULL, NULL, &dwSid)`
- `0x18003c69a`: `CreateWellKnownSid(type, NULL, pSid, [%ld])`
- `0x18003c70a`: `Set m_pSidAdmin`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CVssSidCollection::AddWellKnownSid(__int64 a1, WELL_KNOWN_SID_TYPE a2, int a3)
{
  PSID v6; // rbx
  void **v7; // [rsp+28h] [rbp-D8h] BYREF
  PSID pSid; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v9; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+54h] [rbp-ACh]
  int v14; // [rsp+58h] [rbp-A8h]
  _BYTE v15[120]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+D8h] [rbp-28h]
  LPVOID v17[14]; // [rsp+E0h] [rbp-20h] BYREF
  DWORD cbSid; // [rsp+198h] [rbp+98h] BYREF

  v9 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v10 = L"CVssSidCollection::AddWellKnownSid";
  v11 = L"SECSECRC";
  v12 = 1348;
  v13 = 11;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v17, (__int64)&v9, 0);
  pSid = 0;
  v7 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  cbSid = 0;
  if ( CreateWellKnownSid(a2, 0, 0, &cbSid) )
  {
    v9 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v10 = L"CVssSidCollection::AddWellKnownSid";
    v11 = L"SECSECRC";
    v12 = 1358;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateWin32Error(v17, &v9, L"CreateWellKnownSid(type, NULL, NULL, &dwSid)");
  }
  if ( GetLastError() != 122 )
  {
    v9 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v10 = L"CVssSidCollection::AddWellKnownSid";
    v11 = L"SECSECRC";
    v12 = 1361;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateWin32Error(v17, &v9, L"CreateWellKnownSid(type, NULL, NULL, &dwSid)");
  }
  CVssAllocatingPtr_Storage<void *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>::AllocateBytes(
    &v7,
    cbSid);
  v6 = pSid;
  if ( !CreateWellKnownSid(a2, 0, pSid, &cbSid) )
  {
    v9 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v10 = L"CVssSidCollection::AddWellKnownSid";
    v11 = L"SECSECRC";
    v12 = 1370;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateWin32Error(v17, &v9, L"CreateWellKnownSid(type, NULL, pSid, [%ld])", cbSid);
  }
  CVssSidCollection::AddSid(a1, v6, a3);
  if ( !*(_QWORD *)(a1 + 104) )
  {
    v9 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v10 = L"CVssSidCollection::AddWellKnownSid";
    v11 = L"SECSECRC";
    v12 = 1376;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::Trace(v17, &v9, L"Set m_pSidAdmin");
    pSid = 0;
    *(_QWORD *)(a1 + 104) = v6;
  }
  CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&void * LocalFree(void *),void * (*)(unsigned __int64),&void * LocalAllocate(unsigned __int64)>>(&v7);
  CVssFunctionTracer::~CVssFunctionTracer(v17);
}

```

## disassembly

```asm
0x18003c4ac  mov     [rsp-8+arg_0], rbx
0x18003c4b1  mov     [rsp-8+arg_8], rsi
0x18003c4b6  push    rbp
0x18003c4b7  push    rdi
0x18003c4b8  push    r12
0x18003c4ba  push    r13
0x18003c4bc  push    r14
0x18003c4be  lea     rbp, [rsp-50h]
0x18003c4c3  sub     rsp, 150h
0x18003c4ca  mov     r14d, r8d
0x18003c4cd  mov     esi, edx
0x18003c4cf  mov     rdi, rcx
0x18003c4d2  lea     r12, aBaseStorVssMod_8; "base\\stor\\vss\\modules\\sec\\security"...
0x18003c4d9  mov     [rsp+170h+var_138], r12
0x18003c4de  lea     r13, aCvsssidcollect; "CVssSidCollection::AddWellKnownSid"
0x18003c4e5  mov     [rsp+170h+var_130], r13
0x18003c4ea  lea     rbx, aSecsecrc; "SECSECRC"
0x18003c4f1  mov     [rsp+170h+var_128], rbx
0x18003c4f6  mov     [rsp+170h+var_120], 544h
0x18003c4fe  mov     [rsp+170h+var_11C], 0Bh
0x18003c506  mov     [rsp+170h+var_118], 0FFh
0x18003c50e  mov     [rbp+70h+var_98], 1000000h
0x18003c515  xor     edx, edx; Val
0x18003c517  lea     r8d, [rdx+78h]; Size
0x18003c51b  lea     rcx, [rsp+170h+var_110]; void *
0x18003c520  call    memset_0
0x18003c525  xor     r8d, r8d
0x18003c528  lea     rdx, [rsp+170h+var_138]
0x18003c52d  lea     rcx, [rbp+70h+var_90]
0x18003c531  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003c536  nop
0x18003c537  mov     [rsp+170h+pSid], 0
0x18003c540  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x18003c547  mov     [rsp+170h+var_148], rax
0x18003c54c  mov     [rbp+70h+cbSid], 0
0x18003c556  lea     r9, [rbp+70h+cbSid]; cbSid
0x18003c55d  xor     r8d, r8d; pSid
0x18003c560  xor     edx, edx; DomainSid
0x18003c562  mov     ecx, esi; WellKnownSidType
0x18003c564  call    cs:__imp_CreateWellKnownSid
0x18003c56a  test    eax, eax
0x18003c56c  jz      short loc_18003C5C2
0x18003c56e  mov     [rsp+170h+var_138], r12
0x18003c573  mov     [rsp+170h+var_130], r13
0x18003c578  mov     [rsp+170h+var_128], rbx
0x18003c57d  mov     [rsp+170h+var_120], 54Eh
0x18003c585  mov     [rsp+170h+var_11C], 0Bh
0x18003c58d  mov     [rsp+170h+var_118], 0FFh
0x18003c595  mov     [rbp+70h+var_98], 1000000h
0x18003c59c  xor     edx, edx; Val
0x18003c59e  lea     r8d, [rdx+78h]; Size
0x18003c5a2  lea     rcx, [rsp+170h+var_110]; void *
0x18003c5a7  call    memset_0
0x18003c5ac  lea     r8, aCreatewellknow_1; "CreateWellKnownSid(type, NULL, NULL, &d"...
0x18003c5b3  lea     rdx, [rsp+170h+var_138]
0x18003c5b8  lea     rcx, [rbp+70h+var_90]
0x18003c5bc  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18003c5c2  call    cs:__imp_GetLastError
0x18003c5c8  cmp     eax, 7Ah ; 'z'
0x18003c5cb  jz      short loc_18003C621
0x18003c5cd  mov     [rsp+170h+var_138], r12
0x18003c5d2  mov     [rsp+170h+var_130], r13
0x18003c5d7  mov     [rsp+170h+var_128], rbx
0x18003c5dc  mov     [rsp+170h+var_120], 551h
0x18003c5e4  mov     [rsp+170h+var_11C], 0Bh
0x18003c5ec  mov     [rsp+170h+var_118], 0FFh
0x18003c5f4  mov     [rbp+70h+var_98], 1000000h
0x18003c5fb  xor     edx, edx; Val
0x18003c5fd  lea     r8d, [rdx+78h]; Size
0x18003c601  lea     rcx, [rsp+170h+var_110]; void *
0x18003c606  call    memset_0
0x18003c60b  lea     r8, aCreatewellknow_1; "CreateWellKnownSid(type, NULL, NULL, &d"...
0x18003c612  lea     rdx, [rsp+170h+var_138]
0x18003c617  lea     rcx, [rbp+70h+var_90]
0x18003c61b  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18003c621  mov     edx, [rbp+70h+cbSid]
0x18003c627  lea     rcx, [rsp+170h+var_148]
0x18003c62c  call    ?AllocateBytes@?$CVssAllocatingPtr_Storage@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@QEAAX_K@Z; CVssAllocatingPtr_Storage<void *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>::AllocateBytes(unsigned __int64)
0x18003c631  mov     rbx, [rsp+170h+pSid]
0x18003c636  lea     r9, [rbp+70h+cbSid]; cbSid
0x18003c63d  mov     r8, rbx; pSid
0x18003c640  xor     edx, edx; DomainSid
0x18003c642  mov     ecx, esi; WellKnownSidType
0x18003c644  call    cs:__imp_CreateWellKnownSid
0x18003c64a  test    eax, eax
0x18003c64c  jnz     short loc_18003C6B0
0x18003c64e  mov     [rsp+170h+var_138], r12
0x18003c653  mov     [rsp+170h+var_130], r13
0x18003c658  lea     rax, aSecsecrc; "SECSECRC"
0x18003c65f  mov     [rsp+170h+var_128], rax
0x18003c664  mov     [rsp+170h+var_120], 55Ah
0x18003c66c  mov     [rsp+170h+var_11C], 0Bh
0x18003c674  mov     [rsp+170h+var_118], 0FFh
0x18003c67c  mov     [rbp+70h+var_98], 1000000h
0x18003c683  xor     edx, edx; Val
0x18003c685  lea     r8d, [rdx+78h]; Size
0x18003c689  lea     rcx, [rsp+170h+var_110]; void *
0x18003c68e  call    memset_0
0x18003c693  mov     r9d, [rbp+70h+cbSid]
0x18003c69a  lea     r8, aCreatewellknow; "CreateWellKnownSid(type, NULL, pSid, [%"...
0x18003c6a1  lea     rdx, [rsp+170h+var_138]
0x18003c6a6  lea     rcx, [rbp+70h+var_90]
0x18003c6aa  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18003c6b0  mov     r8d, r14d
0x18003c6b3  mov     rdx, rbx
0x18003c6b6  mov     rcx, rdi
0x18003c6b9  call    ?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z; CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)
0x18003c6be  cmp     qword ptr [rdi+68h], 0
0x18003c6c3  jnz     short loc_18003C72C
0x18003c6c5  mov     [rsp+170h+var_138], r12
0x18003c6ca  mov     [rsp+170h+var_130], r13
0x18003c6cf  lea     rax, aSecsecrc; "SECSECRC"
0x18003c6d6  mov     [rsp+170h+var_128], rax
0x18003c6db  mov     [rsp+170h+var_120], 560h
0x18003c6e3  mov     [rsp+170h+var_11C], 0Bh
0x18003c6eb  mov     [rsp+170h+var_118], 0FFh
0x18003c6f3  mov     [rbp+70h+var_98], 1000000h
0x18003c6fa  xor     edx, edx; Val
0x18003c6fc  lea     r8d, [rdx+78h]; Size
0x18003c700  lea     rcx, [rsp+170h+var_110]; void *
0x18003c705  call    memset_0
0x18003c70a  lea     r8, aSetMPsidadmin; "Set m_pSidAdmin"
0x18003c711  lea     rdx, [rsp+170h+var_138]
0x18003c716  lea     rcx, [rbp+70h+var_90]
0x18003c71a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18003c71f  mov     [rsp+170h+pSid], 0
0x18003c728  mov     [rdi+68h], rbx
0x18003c72c  lea     rcx, [rsp+170h+var_148]
0x18003c731  call    ??1?$CVssAuto@PEAU_SID@@V?$CVssAllocatingPtr_Storage@PEAU_SID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZP6APEAX_K@Z$1?LocalAllocate@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>::~CVssAuto<_SID *,CVssAllocatingPtr_Storage<_SID *,void * (*)(void *),&LocalFree(void *),void * (*)(unsigned __int64),&LocalAllocate(unsigned __int64)>>(void)
0x18003c736  nop
0x18003c737  lea     rcx, [rbp+70h+var_90]; this
0x18003c73b  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003c740  lea     r11, [rsp+170h+var_20]
0x18003c748  mov     rbx, [r11+30h]
0x18003c74c  mov     rsi, [r11+38h]
0x18003c750  mov     rsp, r11
0x18003c753  pop     r14
0x18003c755  pop     r13
0x18003c757  pop     r12
0x18003c759  pop     rdi
0x18003c75a  pop     rbp
0x18003c75b  retn
```
