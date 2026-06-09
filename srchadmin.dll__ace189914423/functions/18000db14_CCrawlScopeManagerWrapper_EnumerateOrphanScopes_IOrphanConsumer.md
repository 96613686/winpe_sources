# CCrawlScopeManagerWrapper::EnumerateOrphanScopes(IOrphanConsumer *)

- ea: `0x18000db14`
- end: `0x18000dd3a`
- name: `?EnumerateOrphanScopes@CCrawlScopeManagerWrapper@@QEAAJPEAVIOrphanConsumer@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(CCrawlScopeManagerWrapper *__hidden this, struct IOrphanConsumer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180025fac`

## callees

- `0x1800038ac`
- `0x18000db14`
- `0x18000de7c`
- `0x18001d568`
- `0x180032010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x18000dc1c`
- `SHLWAPI!StrStrW` at `0x18000dc1c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc82`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc82`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000dc43`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000dc43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dce1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCrawlScopeManagerWrapper::EnumerateOrphanScopes(
        CCrawlScopeManagerWrapper *this,
        struct IOrphanConsumer *a2)
{
  __int64 v3; // rcx
  signed int v4; // ebx
  __int64 v5; // rsi
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rdi
  bool v8; // sf
  PWSTR v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // rcx
  int cchCount2; // eax
  unsigned __int16 *v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  int v16; // [rsp+80h] [rbp+40h] BYREF
  __int64 v17; // [rsp+90h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+58h] BYREF

  v3 = *(_QWORD *)this;
  v4 = v3 == 0 ? 0x8000FFFF : 0;
  LODWORD(v5) = 0;
  v6 = 0;
  v7 = 0;
  v14 = 0;
  v15 = 0;
  if ( v3 )
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 80LL))(v3, &v15);
  v17 = 0;
  v8 = v4 < 0;
  if ( !v4 )
  {
    while ( 1 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, 1, &v17);
      if ( v4 )
      {
LABEL_29:
        v8 = v4 < 0;
        goto LABEL_30;
      }
      v16 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 32LL))(v17, &v16);
      if ( v4 < 0 )
      {
        pv = 0;
      }
      else
      {
        if ( !v16 )
          goto LABEL_28;
        pv = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v17 + 24LL))(v17, &pv);
        if ( v4 >= 0 )
        {
          v4 = PathDupNormalize((const unsigned __int16 *)pv, &v14);
          v7 = v14;
        }
      }
      CoTaskMemFree(pv);
      if ( v4 < 0 )
        goto LABEL_28;
      v9 = StrStrW(v7, L"*");
      v10 = v7;
      if ( v9 )
        goto LABEL_27;
      if ( CompareStringOrdinal(v7, 6, L"winrt:", -1, 1) == 2 )
      {
LABEL_26:
        v10 = v7;
LABEL_27:
        CoTaskMemFree(v10);
        goto LABEL_28;
      }
      if ( !v6 )
        break;
      v11 = -1;
      do
        ++v11;
      while ( v7[v11] );
      cchCount2 = v5;
      if ( (int)v5 >= (int)v11 )
        cchCount2 = v11;
      if ( CompareStringW(0x7Fu, 1u, v6, -1, v7, cchCount2) != 2 )
      {
        CoTaskMemFree(v6);
        v6 = v7;
        v7 = 0;
        v14 = 0;
        v5 = -1;
        do
          ++v5;
        while ( v6[v5] );
LABEL_24:
        v4 = (**(__int64 (__fastcall ***)(struct IOrphanConsumer *, void *))a2)(a2, v6);
      }
      if ( v7 )
        goto LABEL_26;
LABEL_28:
      ATL::CComPtrBase<ISearchRoot>::Release(&v17);
      if ( v4 )
        goto LABEL_29;
    }
    v6 = v7;
    v7 = 0;
    v14 = 0;
    v5 = -1;
    do
      ++v5;
    while ( v6[v5] );
    goto LABEL_24;
  }
LABEL_30:
  if ( !v8 )
    v4 = (*(__int64 (__fastcall **)(struct IOrphanConsumer *))(*(_QWORD *)a2 + 16LL))(a2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000db14  mov     [rsp-38h+arg_8], rbx
0x18000db19  push    rbp
0x18000db1a  push    rsi
0x18000db1b  push    rdi
0x18000db1c  push    r12
0x18000db1e  push    r13
0x18000db20  push    r14
0x18000db22  push    r15
0x18000db24  mov     rbp, rsp
0x18000db27  sub     rsp, 40h
0x18000db2b  mov     r15, rdx
0x18000db2e  mov     rcx, [rcx]
0x18000db31  mov     rax, rcx
0x18000db34  neg     rax
0x18000db37  sbb     ebx, ebx
0x18000db39  not     ebx
0x18000db3b  and     ebx, 8000FFFFh
0x18000db41  xor     r12d, r12d
0x18000db44  mov     esi, r12d
0x18000db47  mov     r14d, r12d
0x18000db4a  mov     edi, r12d
0x18000db4d  mov     [rbp+var_10], r12
0x18000db51  mov     [rbp+var_8], r12
0x18000db55  test    rcx, rcx
0x18000db58  jz      short loc_18000DB6C
0x18000db5a  mov     rax, [rcx]
0x18000db5d  lea     rdx, [rbp+var_8]
0x18000db61  mov     rax, [rax+50h]
0x18000db65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db6a  mov     ebx, eax
0x18000db6c  mov     [rbp+arg_10], r12
0x18000db70  test    ebx, ebx
0x18000db72  jnz     loc_18000DCFA
0x18000db78  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000db7c  mov     rcx, [rbp+var_8]
0x18000db80  mov     rax, [rcx]
0x18000db83  xor     r9d, r9d
0x18000db86  lea     r8, [rbp+arg_10]
0x18000db8a  lea     edx, [r9+1]
0x18000db8e  mov     rax, [rax+18h]
0x18000db92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db97  mov     ebx, eax
0x18000db99  test    eax, eax
0x18000db9b  jnz     loc_18000DCF8
0x18000dba1  mov     [rbp+arg_0], r12d
0x18000dba5  mov     rcx, [rbp+arg_10]
0x18000dba9  mov     rax, [rcx]
0x18000dbac  lea     rdx, [rbp+arg_0]
0x18000dbb0  mov     rax, [rax+20h]
0x18000dbb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb9  mov     ebx, eax
0x18000dbbb  test    eax, eax
0x18000dbbd  js      short loc_18000DBFC
0x18000dbbf  cmp     [rbp+arg_0], r12d
0x18000dbc3  jz      loc_18000DCE7
0x18000dbc9  mov     [rbp+pv], r12
0x18000dbcd  mov     rcx, [rbp+arg_10]
0x18000dbd1  mov     rax, [rcx]
0x18000dbd4  lea     rdx, [rbp+pv]
0x18000dbd8  mov     rax, [rax+18h]
0x18000dbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbe1  mov     ebx, eax
0x18000dbe3  test    eax, eax
0x18000dbe5  js      short loc_18000DC00
0x18000dbe7  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000dbeb  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000dbef  call    ?PathDupNormalize@@YAJPEBGPEAPEAG@Z; PathDupNormalize(ushort const *,ushort * *)
0x18000dbf4  mov     ebx, eax
0x18000dbf6  mov     rdi, [rbp+var_10]
0x18000dbfa  jmp     short loc_18000DC00
0x18000dbfc  mov     [rbp+pv], r12
0x18000dc00  mov     rcx, [rbp+pv]; pv
0x18000dc04  call    cs:__imp_CoTaskMemFree
0x18000dc0a  test    ebx, ebx
0x18000dc0c  js      loc_18000DCE7
0x18000dc12  lea     rdx, pszSrch; "*"
0x18000dc19  mov     rcx, rdi; pszFirst
0x18000dc1c  call    cs:__imp_StrStrW
0x18000dc22  mov     rcx, rdi; lpString1
0x18000dc25  test    rax, rax
0x18000dc28  jnz     loc_18000DCE1
0x18000dc2e  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x18000dc36  mov     r9d, r13d; cchCount2
0x18000dc39  lea     r8, String2; "winrt:"
0x18000dc40  lea     edx, [rax+6]; cchCount1
0x18000dc43  call    cs:__imp_CompareStringOrdinal
0x18000dc49  cmp     eax, 2
0x18000dc4c  jz      loc_18000DCDE
0x18000dc52  test    r14, r14
0x18000dc55  jz      short loc_18000DCAF
0x18000dc57  mov     rcx, r13
0x18000dc5a  inc     rcx
0x18000dc5d  cmp     [rdi+rcx*2], r12w
0x18000dc62  jnz     short loc_18000DC5A
0x18000dc64  mov     eax, esi
0x18000dc66  cmp     esi, ecx
0x18000dc68  cmovge  eax, ecx
0x18000dc6b  mov     [rsp+40h+cchCount2], eax; cchCount2
0x18000dc6f  mov     qword ptr [rsp+40h+bIgnoreCase], rdi; lpString2
0x18000dc74  mov     r9d, r13d; cchCount1
0x18000dc77  mov     r8, r14; lpString1
0x18000dc7a  mov     edx, 1; dwCmpFlags
0x18000dc7f  lea     ecx, [rdx+7Eh]; Locale
0x18000dc82  call    cs:__imp_CompareStringW
0x18000dc88  cmp     eax, 2
0x18000dc8b  jz      short loc_18000DCD9
0x18000dc8d  mov     rcx, r14; pv
0x18000dc90  call    cs:__imp_CoTaskMemFree
0x18000dc96  mov     r14, rdi
0x18000dc99  mov     rdi, r12
0x18000dc9c  mov     [rbp+var_10], r12
0x18000dca0  mov     rsi, r13
0x18000dca3  inc     rsi
0x18000dca6  cmp     [r14+rsi*2], r12w
0x18000dcab  jnz     short loc_18000DCA3
0x18000dcad  jmp     short loc_18000DCC6
0x18000dcaf  mov     r14, rdi
0x18000dcb2  mov     rdi, r12
0x18000dcb5  mov     [rbp+var_10], r12
0x18000dcb9  mov     rsi, r13
0x18000dcbc  inc     rsi
0x18000dcbf  cmp     [r14+rsi*2], r12w
0x18000dcc4  jnz     short loc_18000DCBC
0x18000dcc6  mov     rax, [r15]
0x18000dcc9  mov     rdx, r14
0x18000dccc  mov     rcx, r15
0x18000dccf  mov     rax, [rax]
0x18000dcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcd7  mov     ebx, eax
0x18000dcd9  test    rdi, rdi
0x18000dcdc  jz      short loc_18000DCE7
0x18000dcde  mov     rcx, rdi; pv
0x18000dce1  call    cs:__imp_CoTaskMemFree
0x18000dce7  lea     rcx, [rbp+arg_10]
0x18000dceb  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18000dcf0  test    ebx, ebx
0x18000dcf2  jz      loc_18000DB7C
0x18000dcf8  test    ebx, ebx
0x18000dcfa  js      short loc_18000DD0D
0x18000dcfc  mov     rax, [r15]
0x18000dcff  mov     rcx, r15
0x18000dd02  mov     rax, [rax+10h]
0x18000dd06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd0b  mov     ebx, eax
0x18000dd0d  lea     rcx, [rbp+arg_10]
0x18000dd11  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000dd16  nop
0x18000dd17  lea     rcx, [rbp+var_8]
0x18000dd1b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000dd20  mov     eax, ebx
0x18000dd22  mov     rbx, [rsp+40h+arg_8]
0x18000dd2a  add     rsp, 40h
0x18000dd2e  pop     r15
0x18000dd30  pop     r14
0x18000dd32  pop     r13
0x18000dd34  pop     r12
0x18000dd36  pop     rdi
0x18000dd37  pop     rsi
0x18000dd38  pop     rbp
0x18000dd39  retn
```
