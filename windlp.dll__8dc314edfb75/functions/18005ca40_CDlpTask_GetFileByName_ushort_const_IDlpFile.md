# CDlpTask::GetFileByName(ushort const *,IDlpFile * *)

- ea: `0x18005ca40`
- end: `0x18005cdac`
- name: `?GetFileByName@CDlpTask@@UEAAJPEBGPEAPEAVIDlpFile@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, PCNZWCH lpString1, struct IDlpFile **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180049d6c`
- `0x18005ca40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005cc69`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cd00`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cc69`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cd00`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cccd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005cccd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ca8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ca8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cd14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cd14`

## string_xrefs

- `0x18005cafa`: `CDlpTask::GetFileByName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpTask::GetFileByName(CDlpTask *this, PCNZWCH lpString1, struct IDlpFile **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // r15d
  int v12; // esi
  OLECHAR *v13; // rax
  __int64 v14; // rcx
  struct IDlpFile *v16; // rcx
  PCNZWCH lpString2; // [rsp+20h] [rbp-38h]
  __int64 cchCount2; // [rsp+28h] [rbp-30h]
  char *v19; // [rsp+38h] [rbp-20h]
  BSTR bstrString; // [rsp+A0h] [rbp+48h] BYREF

  v19 = (char *)this + 480;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  bstrString = 0;
  if ( !lpString1 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_32;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1854;
    goto LABEL_5;
  }
  if ( !*lpString1 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_32;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1855;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_32;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1856;
    goto LABEL_5;
  }
  v7 = CDlpTask::CheckInitialized(this, 0);
  if ( v7 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
      goto LABEL_32;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( !v8 )
      goto LABEL_7;
    LODWORD(cchCount2) = v7;
    LODWORD(lpString2) = 1860;
LABEL_5:
    v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v8,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTask::GetFileByName",
            lpString2,
            cchCount2,
            &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
            v19);
    v9 = (unsigned int)v10;
    if ( v10 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_7;
  }
  v11 = *((_DWORD *)this + 91);
  v12 = 0;
  if ( !v11 )
  {
LABEL_31:
    v7 = -2147023728;
    goto LABEL_32;
  }
  v13 = bstrString;
  while ( 1 )
  {
    if ( v13 )
    {
      SysFreeString(v13);
      bstrString = 0;
    }
    v14 = *(_QWORD *)(*((_QWORD *)this + 46) + 8LL * v12);
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 32LL))(v14, &bstrString);
    if ( v7 == -2147023728 )
    {
      v7 = 0;
      goto LABEL_27;
    }
    if ( v7 < 0 )
      break;
LABEL_27:
    v13 = bstrString;
    if ( bstrString )
    {
      if ( CompareStringW(0x409u, 1u, lpString1, -1, bstrString, -1) == 2 )
      {
        _mm_lfence();
        v16 = *(struct IDlpFile **)(*((_QWORD *)this + 46) + 8LL * v12);
        *a3 = v16;
        (*(void (__fastcall **)(struct IDlpFile *))(*(_QWORD *)v16 + 8LL))(v16);
        goto LABEL_32;
      }
      v13 = bstrString;
    }
    if ( ++v12 >= v11 )
      goto LABEL_31;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176) )
  {
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 16LL))((char *)this + 176);
    v9 = 0;
    if ( v8 )
    {
      LODWORD(cchCount2) = v7;
      LODWORD(lpString2) = 1872;
      goto LABEL_5;
    }
LABEL_7:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  }
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005ca40  push    rbp
0x18005ca42  push    rbx
0x18005ca43  push    rsi
0x18005ca44  push    rdi
0x18005ca45  push    r12
0x18005ca47  push    r13
0x18005ca49  push    r14
0x18005ca4b  push    r15
0x18005ca4d  mov     rbp, rsp
0x18005ca50  sub     rsp, 58h
0x18005ca54  mov     r12, r8
0x18005ca57  mov     r14, rdx
0x18005ca5a  mov     rdi, rcx
0x18005ca5d  xor     r15d, r15d
0x18005ca60  mov     [rbp+var_10], r15
0x18005ca64  xorps   xmm0, xmm0
0x18005ca67  xor     eax, eax
0x18005ca69  movups  [rbp+var_28], xmm0
0x18005ca6d  mov     [rbp+var_18], rax
0x18005ca71  lea     rax, [rcx+1E0h]
0x18005ca78  mov     qword ptr [rbp+var_28+8], rax
0x18005ca7c  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x18005ca83  mov     qword ptr [rbp+var_28], rcx
0x18005ca87  lea     r13, [rax+8]
0x18005ca8b  mov     rcx, r13; lpCriticalSection
0x18005ca8e  call    cs:__imp_EnterCriticalSection
0x18005ca94  mov     dword ptr [rbp+var_18], 1
0x18005ca9b  mov     [rbp+bstrString], r15
0x18005ca9f  test    r14, r14
0x18005caa2  jnz     loc_18005CB2A
0x18005caa8  mov     esi, 80070057h
0x18005caad  mov     ebx, esi
0x18005caaf  mov     rax, [rdi+0B0h]
0x18005cab6  lea     rcx, [rdi+0B0h]
0x18005cabd  mov     rax, [rax+10h]
0x18005cac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cac6  test    rax, rax
0x18005cac9  jz      loc_18005CCEF
0x18005cacf  mov     rax, [rdi+0B0h]
0x18005cad6  lea     rcx, [rdi+0B0h]
0x18005cadd  mov     rax, [rax+10h]
0x18005cae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cae6  mov     ecx, r15d
0x18005cae9  test    rax, rax
0x18005caec  jz      short loc_18005CB20
0x18005caee  mov     dword ptr [rsp+58h+cchCount2], esi
0x18005caf2  mov     dword ptr [rsp+58h+lpString2], 73Eh
0x18005cafa  lea     r9, aCdlptaskGetfil_0; "CDlpTask::GetFileByName"
0x18005cb01  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18005cb08  mov     edx, 4
0x18005cb0d  mov     rcx, rax
0x18005cb10  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18005cb15  test    eax, eax
0x18005cb17  mov     ecx, eax
0x18005cb19  jns     short loc_18005CB20
0x18005cb1b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18005cb20  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005cb25  jmp     loc_18005CCEF
0x18005cb2a  cmp     [r14], r15w
0x18005cb2e  jnz     short loc_18005CB87
0x18005cb30  mov     esi, 80070057h
0x18005cb35  mov     ebx, esi
0x18005cb37  mov     rax, [rdi+0B0h]
0x18005cb3e  lea     rcx, [rdi+0B0h]
0x18005cb45  mov     rax, [rax+10h]
0x18005cb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb4e  test    rax, rax
0x18005cb51  jz      loc_18005CCEF
0x18005cb57  mov     rax, [rdi+0B0h]
0x18005cb5e  lea     rcx, [rdi+0B0h]
0x18005cb65  mov     rax, [rax+10h]
0x18005cb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb6e  mov     ecx, r15d
0x18005cb71  test    rax, rax
0x18005cb74  jz      short loc_18005CB20
0x18005cb76  mov     dword ptr [rsp+58h+cchCount2], esi
0x18005cb7a  mov     dword ptr [rsp+58h+lpString2], 73Fh
0x18005cb82  jmp     loc_18005CAFA
0x18005cb87  test    r12, r12
0x18005cb8a  jnz     short loc_18005CBE7
0x18005cb8c  mov     esi, 80070057h
0x18005cb91  mov     ebx, esi
0x18005cb93  mov     rax, [rdi+0B0h]
0x18005cb9a  lea     rcx, [rdi+0B0h]
0x18005cba1  mov     rax, [rax+10h]
0x18005cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbaa  test    rax, rax
0x18005cbad  jz      loc_18005CCEF
0x18005cbb3  mov     rax, [rdi+0B0h]
0x18005cbba  lea     rcx, [rdi+0B0h]
0x18005cbc1  mov     rax, [rax+10h]
0x18005cbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbca  mov     ecx, r15d
0x18005cbcd  test    rax, rax
0x18005cbd0  jz      loc_18005CB20
0x18005cbd6  mov     dword ptr [rsp+58h+cchCount2], esi
0x18005cbda  mov     dword ptr [rsp+58h+lpString2], 740h
0x18005cbe2  jmp     loc_18005CAFA
0x18005cbe7  xor     edx, edx; enum WINDLP_STATE *
0x18005cbe9  mov     rcx, rdi; this
0x18005cbec  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x18005cbf1  mov     ebx, eax
0x18005cbf3  test    eax, eax
0x18005cbf5  jns     short loc_18005CC4B
0x18005cbf7  mov     rdx, [rdi+0B0h]
0x18005cbfe  lea     rcx, [rdi+0B0h]
0x18005cc05  mov     rax, [rdx+10h]
0x18005cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc0e  test    rax, rax
0x18005cc11  jz      loc_18005CCEF
0x18005cc17  mov     rax, [rdi+0B0h]
0x18005cc1e  lea     rcx, [rdi+0B0h]
0x18005cc25  mov     rax, [rax+10h]
0x18005cc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc2e  mov     ecx, r15d
0x18005cc31  test    rax, rax
0x18005cc34  jz      loc_18005CB20
0x18005cc3a  mov     dword ptr [rsp+58h+cchCount2], ebx
0x18005cc3e  mov     dword ptr [rsp+58h+lpString2], 744h
0x18005cc46  jmp     loc_18005CAFA
0x18005cc4b  mov     r15d, [rdi+16Ch]
0x18005cc52  xor     esi, esi
0x18005cc54  test    r15d, r15d
0x18005cc57  jz      loc_18005CCE7
0x18005cc5d  mov     rax, [rbp+bstrString]
0x18005cc61  test    rax, rax
0x18005cc64  jz      short loc_18005CC77
0x18005cc66  mov     rcx, rax; bstrString
0x18005cc69  call    cs:__imp_SysFreeString
0x18005cc6f  mov     [rbp+bstrString], 0
0x18005cc77  mov     rcx, [rdi+170h]
0x18005cc7e  movsxd  rax, esi
0x18005cc81  mov     rcx, [rcx+rax*8]
0x18005cc85  mov     rax, [rcx]
0x18005cc88  lea     rdx, [rbp+bstrString]
0x18005cc8c  mov     rax, [rax+20h]
0x18005cc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc95  mov     ebx, eax
0x18005cc97  cmp     eax, 80070490h
0x18005cc9c  jnz     short loc_18005CCA2
0x18005cc9e  xor     ebx, ebx
0x18005cca0  jmp     short loc_18005CCAA
0x18005cca2  test    ebx, ebx
0x18005cca4  js      loc_18005CD54
0x18005ccaa  mov     rax, [rbp+bstrString]
0x18005ccae  test    rax, rax
0x18005ccb1  jz      short loc_18005CCDC
0x18005ccb3  or      ecx, 0FFFFFFFFh
0x18005ccb6  mov     dword ptr [rsp+58h+cchCount2], ecx; cchCount2
0x18005ccba  mov     [rsp+58h+lpString2], rax; lpString2
0x18005ccbf  mov     r9d, ecx; cchCount1
0x18005ccc2  mov     r8, r14; lpString1
0x18005ccc5  lea     edx, [rcx+2]; dwCmpFlags
0x18005ccc8  mov     ecx, 409h; Locale
0x18005cccd  call    cs:__imp_CompareStringW
0x18005ccd3  cmp     eax, 2
0x18005ccd6  jz      short loc_18005CD31
0x18005ccd8  mov     rax, [rbp+bstrString]
0x18005ccdc  inc     esi
0x18005ccde  cmp     esi, r15d
0x18005cce1  jb      loc_18005CC61
0x18005cce7  mov     ebx, 80070490h
0x18005ccec  xor     r15d, r15d
0x18005ccef  mov     ecx, ebx
0x18005ccf1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005ccf6  nop
0x18005ccf7  mov     rcx, [rbp+bstrString]; bstrString
0x18005ccfb  test    rcx, rcx
0x18005ccfe  jz      short loc_18005CD0A
0x18005cd00  call    cs:__imp_SysFreeString
0x18005cd06  mov     [rbp+bstrString], r15
0x18005cd0a  mov     eax, dword ptr [rbp+var_18]
0x18005cd0d  test    eax, eax
0x18005cd0f  jz      short loc_18005CD1E
0x18005cd11  mov     rcx, r13; lpCriticalSection
0x18005cd14  call    cs:__imp_LeaveCriticalSection
0x18005cd1a  mov     dword ptr [rbp+var_18], r15d
0x18005cd1e  mov     eax, ebx
0x18005cd20  add     rsp, 58h
0x18005cd24  pop     r15
0x18005cd26  pop     r14
0x18005cd28  pop     r13
0x18005cd2a  pop     r12
0x18005cd2c  pop     rdi
0x18005cd2d  pop     rsi
0x18005cd2e  pop     rbx
0x18005cd2f  pop     rbp
0x18005cd30  retn
0x18005cd31  lfence
0x18005cd34  mov     rcx, [rdi+170h]
0x18005cd3b  movsxd  rax, esi
0x18005cd3e  mov     rcx, [rcx+rax*8]
0x18005cd42  mov     [r12], rcx
0x18005cd46  mov     rax, [rcx]
0x18005cd49  mov     rax, [rax+8]
0x18005cd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd52  jmp     short loc_18005CCEC
0x18005cd54  mov     rax, [rdi+0B0h]
0x18005cd5b  lea     rcx, [rdi+0B0h]
0x18005cd62  mov     rax, [rax+10h]
0x18005cd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd6b  xor     r15d, r15d
0x18005cd6e  test    rax, rax
0x18005cd71  jz      loc_18005CCEF
0x18005cd77  mov     rax, [rdi+0B0h]
0x18005cd7e  lea     rcx, [rdi+0B0h]
0x18005cd85  mov     rax, [rax+10h]
0x18005cd89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd8e  mov     ecx, r15d
0x18005cd91  test    rax, rax
0x18005cd94  jz      loc_18005CB20
0x18005cd9a  mov     dword ptr [rsp+58h+cchCount2], ebx
0x18005cd9e  mov     dword ptr [rsp+58h+lpString2], 750h
0x18005cda6  jmp     loc_18005CAFA
```
