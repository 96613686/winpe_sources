# CPreflistFolder::GetCommandState(CUICommand *,IShellItemArray *,int,int *)

- ea: `0x18000e700`
- end: `0x18000e98d`
- name: `?GetCommandState@CPreflistFolder@@UEAAJPEAVCUICommand@@PEAUIShellItemArray@@HPEAH@Z`
- size: `653`
- prototype: `__int64 __fastcall(CPreflistFolder *__hidden this, struct CUICommand *, struct IShellItemArray *, int, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000cfd4`
- `0x18000e700`
- `0x18000f080`
- `0x18000f264`
- `0x18000f448`
- `0x18000fc60`
- `0x180011124`
- `0x18002749c`
- `0x180027594`
- `0x18002d7f6`
- `0x18002d840`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPreflistFolder::GetCommandState(
        CPreflistFolder *this,
        struct CUICommand *a2,
        struct IShellItemArray *a3,
        __int64 a4,
        int *a5)
{
  int v7; // edx
  __int64 Head; // rax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int128 Buf1; // [rsp+20h] [rbp-51h] BYREF
  __int128 v14; // [rsp+30h] [rbp-41h] BYREF
  __int64 v15; // [rsp+40h] [rbp-31h]
  __int128 v16; // [rsp+48h] [rbp-29h]
  int v17; // [rsp+58h] [rbp-19h]

  Buf1 = 0;
  (*(void (__fastcall **)(struct CUICommand *, __int128 *))(*(_QWORD *)a2 + 48LL))(a2, &Buf1);
  if ( !memcmp_0(&Buf1, &xmmword_1800353B8, 0x10u) )
  {
    CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 64));
    v14 = 0u;
    v15 = 0;
    LODWORD(v16) = 0;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      &v14);
    v11 = 2;
    if ( *((_QWORD *)&v14 + 1) > 1u )
      v11 = 0;
    *a5 = v11;
    goto LABEL_24;
  }
  if ( !memcmp_0(&Buf1, &xmmword_1800353A8, 0x10u) )
  {
    CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 64));
    v14 = 0u;
    v15 = 0;
    LODWORD(v16) = 0;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
      CSingletonPtr<CWlanProfileStore>::s_pInstance,
      &v14);
    v10 = 2;
    if ( *((_QWORD *)&v14 + 1) )
      v10 = 0;
    *a5 = v10;
LABEL_24:
    ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v14);
    return 0;
  }
  if ( memcmp_0(&Buf1, &xmmword_1800353E8, 0x10u) )
  {
    if ( !memcmp_0(&Buf1, &xmmword_1800353D8, 0x10u) )
    {
      CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 64));
      CProfile::CProfile((CProfile *)&v14);
      if ( CPreflistFolder::GetFirstProfile(a3, (struct CProfile *)&v14) < 0 )
        v7 = 2;
      else
        v7 = (*(unsigned __int8 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                    + 144LL))(
               CSingletonPtr<CWlanProfileStore>::s_pInstance,
               &v14) == 0
           ? 2
           : 0;
    }
    else
    {
      if ( memcmp_0(&Buf1, &xmmword_1800353C8, 0x10u) )
      {
        *a5 = 0;
        return 0;
      }
      CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 64));
      CProfile::CProfile((CProfile *)&v14);
      if ( CPreflistFolder::GetFirstProfile(a3, (struct CProfile *)&v14) < 0 )
        v7 = 2;
      else
        v7 = (*(unsigned __int8 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                                    + 152LL))(
               CSingletonPtr<CWlanProfileStore>::s_pInstance,
               &v14) == 0
           ? 2
           : 0;
    }
    *a5 = v7;
    CProfile::~CProfile((CProfile *)&v14);
    return 0;
  }
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 10;
  CPreflistFolder::GetProfileList((__int64)a3, (__int64)&v14);
  if ( v15 != 1
    || (Head = ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::GetHead(&v14), v9 = 0, *(_BYTE *)(Head + 81)) )
  {
    v9 = 2;
  }
  *a5 = v9;
  ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(&v14);
  return 0;
}

```

## disassembly

```asm
0x18000e700  mov     [rsp-8+arg_18], rbx
0x18000e705  push    rbp
0x18000e706  push    rsi
0x18000e707  push    rdi
0x18000e708  push    r14
0x18000e70a  push    r15
0x18000e70c  lea     rbp, [rsp-2Fh]
0x18000e711  sub     rsp, 0A0h
0x18000e718  mov     rax, cs:__security_cookie
0x18000e71f  xor     rax, rsp
0x18000e722  mov     [rbp+4Fh+var_30], rax
0x18000e726  mov     rsi, r8
0x18000e729  mov     r8, rdx
0x18000e72c  mov     rdi, rcx
0x18000e72f  mov     rbx, [rbp+4Fh+arg_20]
0x18000e733  xorps   xmm0, xmm0
0x18000e736  movups  [rbp+4Fh+Buf1], xmm0
0x18000e73a  mov     rax, [rdx]
0x18000e73d  lea     rdx, [rbp+4Fh+Buf1]
0x18000e741  mov     rcx, r8
0x18000e744  mov     rax, [rax+30h]
0x18000e748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e74d  mov     r15d, 10h
0x18000e753  mov     r8d, r15d; Size
0x18000e756  lea     rdx, xmmword_1800353B8; Buf2
0x18000e75d  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000e761  call    memcmp_0
0x18000e766  xor     r14d, r14d
0x18000e769  test    eax, eax
0x18000e76b  jz      loc_18000E91F
0x18000e771  mov     r8d, r15d; Size
0x18000e774  lea     rdx, xmmword_1800353A8; Buf2
0x18000e77b  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000e77f  call    memcmp_0
0x18000e784  test    eax, eax
0x18000e786  jz      loc_18000E8DE
0x18000e78c  mov     r8d, r15d; Size
0x18000e78f  lea     rdx, xmmword_1800353E8; Buf2
0x18000e796  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000e79a  call    memcmp_0
0x18000e79f  test    eax, eax
0x18000e7a1  jz      loc_18000E889
0x18000e7a7  mov     r8d, r15d; Size
0x18000e7aa  lea     rdx, xmmword_1800353D8; Buf2
0x18000e7b1  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000e7b5  call    memcmp_0
0x18000e7ba  test    eax, eax
0x18000e7bc  jz      short loc_18000E83A
0x18000e7be  mov     r8d, r15d; Size
0x18000e7c1  lea     rdx, xmmword_1800353C8; Buf2
0x18000e7c8  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000e7cc  call    memcmp_0
0x18000e7d1  test    eax, eax
0x18000e7d3  jz      short loc_18000E7DD
0x18000e7d5  mov     [rbx], r14d
0x18000e7d8  jmp     loc_18000E968
0x18000e7dd  lea     rcx, [rdi-40h]; this
0x18000e7e1  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000e7e6  lea     rcx, [rbp+4Fh+var_90]; this
0x18000e7ea  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x18000e7ef  nop
0x18000e7f0  lea     rdx, [rbp+4Fh+var_90]; struct CProfile *
0x18000e7f4  mov     rcx, rsi; struct IShellItemArray *
0x18000e7f7  call    ?GetFirstProfile@CPreflistFolder@@CAJPEAUIShellItemArray@@AEAVCProfile@@@Z; CPreflistFolder::GetFirstProfile(IShellItemArray *,CProfile &)
0x18000e7fc  test    eax, eax
0x18000e7fe  js      short loc_18000E825
0x18000e800  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000e807  mov     rax, [rcx]
0x18000e80a  lea     rdx, [rbp+4Fh+var_90]
0x18000e80e  mov     rax, [rax+98h]
0x18000e815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81a  neg     al
0x18000e81c  sbb     edx, edx
0x18000e81e  not     edx
0x18000e820  and     edx, 2
0x18000e823  jmp     short loc_18000E82A
0x18000e825  mov     edx, 2
0x18000e82a  mov     [rbx], edx
0x18000e82c  lea     rcx, [rbp+4Fh+var_90]; this
0x18000e830  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x18000e835  jmp     loc_18000E968
0x18000e83a  lea     rcx, [rdi-40h]; this
0x18000e83e  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000e843  lea     rcx, [rbp+4Fh+var_90]; this
0x18000e847  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x18000e84c  nop
0x18000e84d  lea     rdx, [rbp+4Fh+var_90]; struct CProfile *
0x18000e851  mov     rcx, rsi; struct IShellItemArray *
0x18000e854  call    ?GetFirstProfile@CPreflistFolder@@CAJPEAUIShellItemArray@@AEAVCProfile@@@Z; CPreflistFolder::GetFirstProfile(IShellItemArray *,CProfile &)
0x18000e859  test    eax, eax
0x18000e85b  js      short loc_18000E882
0x18000e85d  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000e864  mov     rax, [rcx]
0x18000e867  lea     rdx, [rbp+4Fh+var_90]
0x18000e86b  mov     rax, [rax+90h]
0x18000e872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e877  neg     al
0x18000e879  sbb     edx, edx
0x18000e87b  not     edx
0x18000e87d  and     edx, 2
0x18000e880  jmp     short loc_18000E887
0x18000e882  mov     edx, 2
0x18000e887  jmp     short loc_18000E82A
0x18000e889  xorps   xmm0, xmm0
0x18000e88c  movdqu  [rbp+4Fh+var_90], xmm0
0x18000e891  mov     [rbp+4Fh+var_80], r14
0x18000e895  xorps   xmm1, xmm1
0x18000e898  movdqu  [rbp+4Fh+var_78], xmm1
0x18000e89d  mov     [rbp+4Fh+var_68], 0Ah
0x18000e8a4  lea     rdx, [rbp+4Fh+var_90]
0x18000e8a8  mov     rcx, rsi
0x18000e8ab  call    ?GetProfileList@CPreflistFolder@@CAJPEAUIShellItemArray@@AEAV?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@@Z; CPreflistFolder::GetProfileList(IShellItemArray *,ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>> &)
0x18000e8b0  cmp     [rbp+4Fh+var_80], 1
0x18000e8b5  jnz     short loc_18000E8C9
0x18000e8b7  lea     rcx, [rbp+4Fh+var_90]
0x18000e8bb  call    ?GetHead@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAAEAVCProfile@@XZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::GetHead(void)
0x18000e8c0  cmp     [rax+51h], r14b
0x18000e8c4  mov     ecx, r14d
0x18000e8c7  jz      short loc_18000E8CE
0x18000e8c9  mov     ecx, 2
0x18000e8ce  mov     [rbx], ecx
0x18000e8d0  lea     rcx, [rbp+4Fh+var_90]
0x18000e8d4  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x18000e8d9  jmp     loc_18000E968
0x18000e8de  lea     rcx, [rdi-40h]; this
0x18000e8e2  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000e8e7  mov     qword ptr [rbp+4Fh+var_90], r14
0x18000e8eb  mov     qword ptr [rbp+4Fh+var_90+8], r14
0x18000e8ef  mov     [rbp+4Fh+var_80], r14
0x18000e8f3  mov     dword ptr [rbp+4Fh+var_78], r14d
0x18000e8f7  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000e8fe  mov     rax, [rcx]
0x18000e901  lea     rdx, [rbp+4Fh+var_90]
0x18000e905  mov     rax, [rax+48h]
0x18000e909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90e  mov     ecx, 2
0x18000e913  cmp     qword ptr [rbp+4Fh+var_90+8], r14
0x18000e917  cmova   ecx, r14d
0x18000e91b  mov     [rbx], ecx
0x18000e91d  jmp     short loc_18000E95F
0x18000e91f  lea     rcx, [rdi-40h]; this
0x18000e923  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x18000e928  mov     qword ptr [rbp+4Fh+var_90], r14
0x18000e92c  mov     qword ptr [rbp+4Fh+var_90+8], r14
0x18000e930  mov     [rbp+4Fh+var_80], r14
0x18000e934  mov     dword ptr [rbp+4Fh+var_78], r14d
0x18000e938  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x18000e93f  mov     rax, [rcx]
0x18000e942  lea     rdx, [rbp+4Fh+var_90]
0x18000e946  mov     rax, [rax+48h]
0x18000e94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94f  mov     ecx, 2
0x18000e954  cmp     qword ptr [rbp+4Fh+var_90+8], 1
0x18000e959  cmova   ecx, r14d
0x18000e95d  mov     [rbx], ecx
0x18000e95f  lea     rcx, [rbp+4Fh+var_90]
0x18000e963  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x18000e968  xor     eax, eax
0x18000e96a  mov     rcx, [rbp+4Fh+var_30]
0x18000e96e  xor     rcx, rsp; StackCookie
0x18000e971  call    __security_check_cookie
0x18000e976  mov     rbx, [rsp+0C0h+arg_18]
0x18000e97e  add     rsp, 0A0h
0x18000e985  pop     r15
0x18000e987  pop     r14
0x18000e989  pop     rdi
0x18000e98a  pop     rsi
0x18000e98b  pop     rbp
0x18000e98c  retn
```
