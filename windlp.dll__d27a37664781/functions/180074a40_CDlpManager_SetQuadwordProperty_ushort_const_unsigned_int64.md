# CDlpManager::SetQuadwordProperty(ushort const *,unsigned __int64)

- ea: `0x180074a40`
- end: `0x180074cc7`
- name: `?SetQuadwordProperty@CDlpManager@@UEAAJPEBG_K@Z`
- size: `647`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180047c30`
- `0x180047db4`
- `0x180074a40`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180074b40`
- `OLEAUT32!__imp_SysAllocString` at `0x180074b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180074c96`
- `OLEAUT32!__imp_SysFreeString` at `0x180074c96`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180074b2c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180074b2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074a8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074a8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ca7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ca7`

## pseudocode

```c
__int64 __fastcall CDlpManager::SetQuadwordProperty(CDlpManager *this, const unsigned __int16 *a2, __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // esi
  int v11; // ebx
  __int64 v12; // r12
  OLECHAR *v13; // rax
  int v14; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-38h]
  __int64 cchCount2; // [rsp+28h] [rbp-30h]
  char *v18; // [rsp+38h] [rbp-20h]
  BSTR bstrString; // [rsp+A0h] [rbp+48h] BYREF

  v18 = (char *)this + 408;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 416);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 416));
  bstrString = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
      goto LABEL_24;
    v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    v9 = 0;
    if ( !v8 )
      goto LABEL_23;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 2060;
    goto LABEL_21;
  }
  v10 = *((_DWORD *)this + 151);
  v11 = 0;
  if ( !v10 )
  {
LABEL_8:
    v13 = SysAllocString(a2);
    if ( v13 )
    {
      bstrString = v13;
      v7 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 600, &bstrString);
      if ( v7 >= 0 )
      {
        v7 = CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 616, a3);
        if ( v7 >= 0 || !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          goto LABEL_24;
        v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v9 = 0;
        if ( !v8 )
        {
LABEL_23:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
          goto LABEL_24;
        }
        LODWORD(cchCount2) = v7;
        LODWORD(lpString2) = 2086;
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
          goto LABEL_24;
        v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
        v9 = 0;
        if ( !v8 )
          goto LABEL_23;
        LODWORD(cchCount2) = v7;
        LODWORD(lpString2) = 2085;
      }
    }
    else
    {
      bstrString = 0;
      v7 = -2147024882;
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72) )
        goto LABEL_24;
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
      v9 = 0;
      if ( !v8 )
        goto LABEL_23;
      LODWORD(cchCount2) = -2147024882;
      LODWORD(lpString2) = 2081;
    }
LABEL_21:
    v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v8,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetQuadwordProperty",
            lpString2,
            cchCount2,
            &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
            v18);
    v9 = (unsigned int)v14;
    if ( v14 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    goto LABEL_23;
  }
  while ( 1 )
  {
    v12 = v11;
    if ( CompareStringW(0x409u, 1u, a2, -1, *(PCNZWCH *)(*((_QWORD *)this + 76) + 8LL * v11), -1) == 2 )
      break;
    if ( ++v11 >= v10 )
      goto LABEL_8;
  }
  v7 = 0;
  *(_QWORD *)(*((_QWORD *)this + 78) + 8 * v12) = a3;
LABEL_24:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( bstrString )
    SysFreeString(bstrString);
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180074a40  push    rbp
0x180074a42  push    rbx
0x180074a43  push    rsi
0x180074a44  push    rdi
0x180074a45  push    r12
0x180074a47  push    r13
0x180074a49  push    r14
0x180074a4b  push    r15
0x180074a4d  mov     rbp, rsp
0x180074a50  sub     rsp, 58h
0x180074a54  mov     r15, r8
0x180074a57  mov     r14, rdx
0x180074a5a  mov     rdi, rcx
0x180074a5d  mov     [rbp+var_10], 0
0x180074a65  xorps   xmm0, xmm0
0x180074a68  xor     eax, eax
0x180074a6a  movups  [rbp+var_28], xmm0
0x180074a6e  mov     [rbp+var_18], rax
0x180074a72  lea     rax, [rcx+198h]
0x180074a79  mov     qword ptr [rbp+var_28+8], rax
0x180074a7d  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180074a84  mov     qword ptr [rbp+var_28], rcx
0x180074a88  lea     r13, [rax+8]
0x180074a8c  mov     rcx, r13; lpCriticalSection
0x180074a8f  call    cs:__imp_EnterCriticalSection
0x180074a95  mov     dword ptr [rbp+var_18], 1
0x180074a9c  mov     [rbp+bstrString], 0
0x180074aa4  test    r14, r14
0x180074aa7  jnz     short loc_180074AF5
0x180074aa9  mov     ebx, 80070057h
0x180074aae  mov     rax, [rdi+48h]
0x180074ab2  lea     rcx, [rdi+48h]
0x180074ab6  mov     rax, [rax+10h]
0x180074aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074abf  test    rax, rax
0x180074ac2  jz      loc_180074C85
0x180074ac8  mov     rax, [rdi+48h]
0x180074acc  lea     rcx, [rdi+48h]
0x180074ad0  mov     rax, [rax+10h]
0x180074ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ad9  xor     ecx, ecx
0x180074adb  test    rax, rax
0x180074ade  jz      loc_180074C80
0x180074ae4  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180074ae8  mov     dword ptr [rsp+58h+lpString2], 80Ch
0x180074af0  jmp     loc_180074C5A
0x180074af5  mov     esi, [rdi+25Ch]
0x180074afb  xor     ebx, ebx
0x180074afd  test    esi, esi
0x180074aff  jz      short loc_180074B3D
0x180074b01  mov     rax, [rdi+260h]
0x180074b08  movsxd  r12, ebx
0x180074b0b  mov     rax, [rax+r12*8]
0x180074b0f  mov     dword ptr [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180074b17  mov     [rsp+58h+lpString2], rax; lpString2
0x180074b1c  or      r9d, 0FFFFFFFFh; cchCount1
0x180074b20  mov     r8, r14; lpString1
0x180074b23  lea     edx, [r9+2]; dwCmpFlags
0x180074b27  mov     ecx, 409h; Locale
0x180074b2c  call    cs:__imp_CompareStringW
0x180074b32  cmp     eax, 2
0x180074b35  jz      short loc_180074B9B
0x180074b37  inc     ebx
0x180074b39  cmp     ebx, esi
0x180074b3b  jb      short loc_180074B01
0x180074b3d  mov     rcx, r14; psz
0x180074b40  call    cs:__imp_SysAllocString
0x180074b46  test    rax, rax
0x180074b49  jnz     short loc_180074BAD
0x180074b4b  mov     [rbp+bstrString], rax
0x180074b4f  mov     ebx, 8007000Eh
0x180074b54  mov     rax, [rdi+48h]
0x180074b58  lea     rcx, [rdi+48h]
0x180074b5c  mov     rax, [rax+10h]
0x180074b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b65  test    rax, rax
0x180074b68  jz      loc_180074C85
0x180074b6e  mov     rax, [rdi+48h]
0x180074b72  lea     rcx, [rdi+48h]
0x180074b76  mov     rax, [rax+10h]
0x180074b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b7f  xor     ecx, ecx
0x180074b81  test    rax, rax
0x180074b84  jz      loc_180074C80
0x180074b8a  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180074b8e  mov     dword ptr [rsp+58h+lpString2], 821h
0x180074b96  jmp     loc_180074C5A
0x180074b9b  xor     ebx, ebx
0x180074b9d  mov     rax, [rdi+270h]
0x180074ba4  mov     [rax+r12*8], r15
0x180074ba8  jmp     loc_180074C85
0x180074bad  mov     [rbp+bstrString], rax
0x180074bb1  lea     rcx, [rdi+258h]
0x180074bb8  lea     rdx, [rbp+bstrString]
0x180074bbc  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x180074bc1  mov     ebx, eax
0x180074bc3  test    eax, eax
0x180074bc5  jns     short loc_180074C0B
0x180074bc7  mov     rdx, [rdi+48h]
0x180074bcb  lea     rcx, [rdi+48h]
0x180074bcf  mov     rax, [rdx+10h]
0x180074bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074bd8  test    rax, rax
0x180074bdb  jz      loc_180074C85
0x180074be1  mov     rax, [rdi+48h]
0x180074be5  lea     rcx, [rdi+48h]
0x180074be9  mov     rax, [rax+10h]
0x180074bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074bf2  xor     ecx, ecx
0x180074bf4  test    rax, rax
0x180074bf7  jz      loc_180074C80
0x180074bfd  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180074c01  mov     dword ptr [rsp+58h+lpString2], 825h
0x180074c09  jmp     short loc_180074C5A
0x180074c0b  lea     rcx, [rdi+268h]
0x180074c12  mov     rdx, r15
0x180074c15  call    ?Append@?$CArray@_K_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJ_K@Z; CArray<unsigned __int64,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::Append(unsigned __int64)
0x180074c1a  mov     ebx, eax
0x180074c1c  test    eax, eax
0x180074c1e  jns     short loc_180074C85
0x180074c20  mov     rax, [rdi+48h]
0x180074c24  lea     rcx, [rdi+48h]
0x180074c28  mov     rax, [rax+10h]
0x180074c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c31  test    rax, rax
0x180074c34  jz      short loc_180074C85
0x180074c36  mov     rax, [rdi+48h]
0x180074c3a  lea     rcx, [rdi+48h]
0x180074c3e  mov     rax, [rax+10h]
0x180074c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c47  xor     ecx, ecx
0x180074c49  test    rax, rax
0x180074c4c  jz      short loc_180074C80
0x180074c4e  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180074c52  mov     dword ptr [rsp+58h+lpString2], 826h
0x180074c5a  lea     r9, aCdlpmanagerSet; "CDlpManager::SetQuadwordProperty"
0x180074c61  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180074c68  mov     edx, 4
0x180074c6d  mov     rcx, rax
0x180074c70  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180074c75  test    eax, eax
0x180074c77  mov     ecx, eax
0x180074c79  jns     short loc_180074C80
0x180074c7b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180074c80  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180074c85  mov     ecx, ebx
0x180074c87  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180074c8c  nop
0x180074c8d  mov     rcx, [rbp+bstrString]; bstrString
0x180074c91  test    rcx, rcx
0x180074c94  jz      short loc_180074C9D
0x180074c96  call    cs:__imp_SysFreeString
0x180074c9c  nop
0x180074c9d  mov     eax, dword ptr [rbp+var_18]
0x180074ca0  test    eax, eax
0x180074ca2  jz      short loc_180074CB4
0x180074ca4  mov     rcx, r13; lpCriticalSection
0x180074ca7  call    cs:__imp_LeaveCriticalSection
0x180074cad  mov     dword ptr [rbp+var_18], 0
0x180074cb4  mov     eax, ebx
0x180074cb6  add     rsp, 58h
0x180074cba  pop     r15
0x180074cbc  pop     r14
0x180074cbe  pop     r13
0x180074cc0  pop     r12
0x180074cc2  pop     rdi
0x180074cc3  pop     rsi
0x180074cc4  pop     rbx
0x180074cc5  pop     rbp
0x180074cc6  retn
```
