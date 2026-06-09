# CPreflistFolder::CompareProfiles(CProfile const &,CProfile const &,_tagpropertykey const &)

- ea: `0x18000d830`
- end: `0x18000d986`
- name: `?CompareProfiles@CPreflistFolder@@IEAAHAEBVCProfile@@0AEBU_tagpropertykey@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, const struct CProfile *, const struct CProfile *, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d6b0`

## callees

- `0x1800036ac`
- `0x18000d830`
- `0x18000f390`
- `0x18000fc60`
- `0x180027ad4`
- `0x180027db0`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPreflistFolder::CompareProfiles(
        CPreflistFolder *this,
        const struct CProfile *a2,
        const struct CProfile *a3,
        const struct _tagpropertykey *a4)
{
  CProfile *v8; // rcx
  unsigned __int16 *v9; // rax
  signed __int64 v10; // rdx
  unsigned __int16 v11; // cx
  int v12; // ebx
  WTL::CString *v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  unsigned __int16 *v16; // rax
  signed __int64 v17; // rdx
  unsigned __int16 v18; // cx
  char *v20; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v21; // [rsp+28h] [rbp-8h] BYREF

  if ( CProfile::HasProperty(this, a4) && CProfile::HasProperty(v8, a4) )
  {
    CProfile::GetProperty(a2, &v21, a4);
    CProfile::GetProperty(a3, &v20, a4);
    v9 = v21;
    v10 = v20 - (char *)v21;
    while ( 1 )
    {
      v11 = *v9;
      if ( *v9 != *(unsigned __int16 *)((char *)v9 + v10) )
        break;
      ++v9;
      if ( !v11 )
      {
        v12 = 0;
        goto LABEL_8;
      }
    }
    v12 = v11 < *(unsigned __int16 *)((char *)v9 + v10) ? -1 : 1;
LABEL_8:
    WTL::CString::~CString((WTL::CString *)&v20);
    v13 = (WTL::CString *)&v21;
LABEL_24:
    WTL::CString::~CString(v13);
    return (unsigned int)v12;
  }
  if ( a4->pid != 3 )
    goto LABEL_18;
  v14 = *(_QWORD *)&a4->fmtid.Data1 - 0x488D949C9B34BBB9LL;
  if ( *(_QWORD *)&a4->fmtid.Data1 == 0x488D949C9B34BBB9LL )
    v14 = *(_QWORD *)a4->fmtid.Data4 - 0x2F7A847CB4EE6D9ALL;
  if ( v14 )
  {
LABEL_18:
    CProfile::GetName(a2, &v20);
    CProfile::GetName(a3, &v21);
    v16 = (unsigned __int16 *)v20;
    v17 = (char *)v21 - v20;
    while ( 1 )
    {
      v18 = *v16;
      if ( *v16 != *(unsigned __int16 *)((char *)v16 + v17) )
        break;
      ++v16;
      if ( !v18 )
      {
        v12 = 0;
        goto LABEL_23;
      }
    }
    v12 = v18 < *(unsigned __int16 *)((char *)v16 + v17) ? -1 : 1;
LABEL_23:
    WTL::CString::~CString((WTL::CString *)&v21);
    v13 = (WTL::CString *)&v20;
    goto LABEL_24;
  }
  CPreflistFolder::InitializeDataSource(this);
  v15 = (*(__int64 (__fastcall **)(__int64, const struct CProfile *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                    + 64LL))(
          CSingletonPtr<CWlanProfileStore>::s_pInstance,
          a2);
  v12 = v15
      - (*(__int64 (__fastcall **)(__int64, const struct CProfile *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                    + 64LL))(
          CSingletonPtr<CWlanProfileStore>::s_pInstance,
          a3);
  if ( v12 >= 0 )
  {
    if ( v12 > 0 )
      return 1;
  }
  else
  {
    return (unsigned int)-1;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d830  push    rbp
0x18000d832  push    rbx
0x18000d833  push    rsi
0x18000d834  push    rdi
0x18000d835  push    r14
0x18000d837  mov     rbp, rsp
0x18000d83a  sub     rsp, 30h
0x18000d83e  mov     rbx, r9
0x18000d841  mov     rdi, r8
0x18000d844  mov     rsi, rdx
0x18000d847  mov     r14, rcx
0x18000d84a  mov     rdx, r9; struct _tagpropertykey *
0x18000d84d  call    ?HasProperty@CProfile@@QEBA_NAEBU_tagpropertykey@@@Z; CProfile::HasProperty(_tagpropertykey const &)
0x18000d852  test    al, al
0x18000d854  jz      short loc_18000D8BA
0x18000d856  mov     rdx, rbx; struct _tagpropertykey *
0x18000d859  call    ?HasProperty@CProfile@@QEBA_NAEBU_tagpropertykey@@@Z; CProfile::HasProperty(_tagpropertykey const &)
0x18000d85e  test    al, al
0x18000d860  jz      short loc_18000D8BA
0x18000d862  mov     r8, rbx
0x18000d865  lea     rdx, [rbp+var_8]
0x18000d869  mov     rcx, rsi
0x18000d86c  call    ?GetProperty@CProfile@@QEBA?AVCString@WTL@@AEBU_tagpropertykey@@@Z; CProfile::GetProperty(_tagpropertykey const &)
0x18000d871  nop
0x18000d872  mov     r8, rbx
0x18000d875  lea     rdx, [rbp+var_10]
0x18000d879  mov     rcx, rdi
0x18000d87c  call    ?GetProperty@CProfile@@QEBA?AVCString@WTL@@AEBU_tagpropertykey@@@Z; CProfile::GetProperty(_tagpropertykey const &)
0x18000d881  mov     rax, [rbp+var_8]
0x18000d885  mov     rdx, [rbp+var_10]
0x18000d889  sub     rdx, rax
0x18000d88c  movzx   ecx, word ptr [rax]
0x18000d88f  cmp     cx, [rax+rdx]
0x18000d893  jnz     short loc_18000D8A2
0x18000d895  add     rax, 2
0x18000d899  test    cx, cx
0x18000d89c  jnz     short loc_18000D88C
0x18000d89e  xor     ebx, ebx
0x18000d8a0  jmp     short loc_18000D8A7
0x18000d8a2  sbb     ebx, ebx
0x18000d8a4  or      ebx, 1
0x18000d8a7  lea     rcx, [rbp+var_10]; this
0x18000d8ab  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000d8b0  nop
0x18000d8b1  lea     rcx, [rbp+var_8]
0x18000d8b5  jmp     loc_18000D974
0x18000d8ba  cmp     dword ptr [rbx+10h], 3
0x18000d8be  jnz     short loc_18000D927
0x18000d8c0  mov     rax, [rbx]
0x18000d8c3  sub     rax, qword ptr cs:stru_1800354C0.fmtid.Data1
0x18000d8ca  jnz     short loc_18000D8D7
0x18000d8cc  mov     rax, [rbx+8]
0x18000d8d0  sub     rax, qword ptr cs:stru_1800354C0.fmtid.Data4
0x18000d8d7  test    rax, rax
0x18000d8da  jnz     short loc_18000D927
0x18000d8dc  mov     rcx, r14; this
0x18000d8df  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000d8e4  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000d8eb  mov     rax, [rcx]
0x18000d8ee  mov     rdx, rsi
0x18000d8f1  mov     rax, [rax+40h]
0x18000d8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8fa  mov     ebx, eax
0x18000d8fc  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000d903  mov     rax, [rcx]
0x18000d906  mov     rdx, rdi
0x18000d909  mov     rax, [rax+40h]
0x18000d90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d912  sub     ebx, eax
0x18000d914  jns     short loc_18000D91B
0x18000d916  or      ebx, 0FFFFFFFFh
0x18000d919  jmp     short loc_18000D979
0x18000d91b  mov     ecx, 1
0x18000d920  test    ebx, ebx
0x18000d922  cmovg   ebx, ecx
0x18000d925  jmp     short loc_18000D979
0x18000d927  lea     rdx, [rbp+var_10]
0x18000d92b  mov     rcx, rsi
0x18000d92e  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18000d933  nop
0x18000d934  lea     rdx, [rbp+var_8]
0x18000d938  mov     rcx, rdi
0x18000d93b  call    ?GetName@CProfile@@QEBA?AVCString@WTL@@XZ; CProfile::GetName(void)
0x18000d940  mov     rax, [rbp+var_10]
0x18000d944  mov     rdx, [rbp+var_8]
0x18000d948  sub     rdx, rax
0x18000d94b  movzx   ecx, word ptr [rax]
0x18000d94e  cmp     cx, [rax+rdx]
0x18000d952  jnz     short loc_18000D961
0x18000d954  add     rax, 2
0x18000d958  test    cx, cx
0x18000d95b  jnz     short loc_18000D94B
0x18000d95d  xor     ebx, ebx
0x18000d95f  jmp     short loc_18000D966
0x18000d961  sbb     ebx, ebx
0x18000d963  or      ebx, 1
0x18000d966  lea     rcx, [rbp+var_8]; this
0x18000d96a  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000d96f  nop
0x18000d970  lea     rcx, [rbp+var_10]; this
0x18000d974  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000d979  mov     eax, ebx
0x18000d97b  add     rsp, 30h
0x18000d97f  pop     r14
0x18000d981  pop     rdi
0x18000d982  pop     rsi
0x18000d983  pop     rbx
0x18000d984  pop     rbp
0x18000d985  retn
```
