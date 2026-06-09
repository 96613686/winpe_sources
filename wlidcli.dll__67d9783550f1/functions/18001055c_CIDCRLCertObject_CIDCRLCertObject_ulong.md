# CIDCRLCertObject::CIDCRLCertObject(ulong)

- ea: `0x18001055c`
- end: `0x18001066f`
- name: `??0CIDCRLCertObject@@IEAA@K@Z`
- size: `275`
- prototype: `CIDCRLCertObject *__fastcall(CIDCRLCertObject *this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180011e50`
- `0x180012998`

## callees

- `0x180002da0`
- `0x18000a914`
- `0x18000b1d8`
- `0x18000c328`
- `0x18001055c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001062f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001062f`
- `RPCRT4!UuidCreate` at `0x1800105e8`
- `RPCRT4!UuidCreate` at `0x1800105e8`
- `RPCRT4!UuidToStringW` at `0x1800105fc`
- `RPCRT4!UuidToStringW` at `0x1800105fc`
- `RPCRT4!RpcStringFreeW` at `0x180010627`
- `RPCRT4!RpcStringFreeW` at `0x180010627`

## pseudocode

```c
CIDCRLCertObject *__fastcall CIDCRLCertObject::CIDCRLCertObject(CIDCRLCertObject *this, int a2)
{
  DWORD CurrentProcessId; // eax
  RPC_WSTR StringUuid[2]; // [rsp+30h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF

  StringUuid[1] = (RPC_WSTR)this;
  CThreadProtected::CThreadProtected(this);
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 6) = &SmartPCCERT_CONTEXT::`vftable';
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 64);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 72);
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = a2;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)this + 96);
  Uuid = 0;
  StringUuid[0] = 0;
  if ( (*((_BYTE *)this + 88) & 1) != 0 )
  {
    if ( !UuidCreate(&Uuid) )
      UuidToStringW(&Uuid, StringUuid);
    if ( StringUuid[0] )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 96,
        L"%ls_%s",
        L"IDENTITYCRL_CERT_CONTAINER");
      RpcStringFreeW(StringUuid);
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 96,
        L"%ls_%08x_%p",
        L"IDENTITYCRL_CERT_CONTAINER",
        CurrentProcessId,
        this);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001055c  mov     [rsp+arg_8], rbx
0x180010561  push    rdi
0x180010562  sub     rsp, 60h
0x180010566  mov     rax, cs:__security_cookie
0x18001056d  xor     rax, rsp
0x180010570  mov     [rsp+68h+var_18], rax
0x180010575  mov     ebx, edx
0x180010577  mov     rdi, rcx
0x18001057a  mov     [rsp+68h+var_30], rcx
0x18001057f  call    ??0CThreadProtected@@QEAA@XZ; CThreadProtected::CThreadProtected(void)
0x180010584  nop
0x180010585  mov     qword ptr [rdi+28h], 0
0x18001058d  mov     qword ptr [rdi+38h], 0
0x180010595  lea     rax, ??_7SmartPCCERT_CONTEXT@@6B@; const SmartPCCERT_CONTEXT::`vftable'
0x18001059c  mov     [rdi+30h], rax
0x1800105a0  lea     rcx, [rdi+40h]
0x1800105a4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800105a9  nop
0x1800105aa  lea     rcx, [rdi+48h]
0x1800105ae  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800105b3  nop
0x1800105b4  mov     qword ptr [rdi+50h], 0
0x1800105bc  mov     [rdi+58h], ebx
0x1800105bf  lea     rbx, [rdi+60h]
0x1800105c3  mov     rcx, rbx
0x1800105c6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800105cb  nop
0x1800105cc  xorps   xmm0, xmm0
0x1800105cf  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x1800105d4  mov     [rsp+68h+StringUuid], 0
0x1800105dd  test    byte ptr [rdi+58h], 1
0x1800105e1  jz      short loc_180010654
0x1800105e3  lea     rcx, [rsp+68h+Uuid]; Uuid
0x1800105e8  call    cs:__imp_UuidCreate
0x1800105ee  test    eax, eax
0x1800105f0  jnz     short loc_180010602
0x1800105f2  lea     rdx, [rsp+68h+StringUuid]; StringUuid
0x1800105f7  lea     rcx, [rsp+68h+Uuid]; Uuid
0x1800105fc  call    cs:__imp_UuidToStringW
0x180010602  mov     r9, [rsp+68h+StringUuid]
0x180010607  test    r9, r9
0x18001060a  jz      short loc_18001062F
0x18001060c  lea     r8, aIdentitycrlCer; "IDENTITYCRL_CERT_CONTAINER"
0x180010613  lea     rdx, aLsS; "%ls_%s"
0x18001061a  mov     rcx, rbx
0x18001061d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180010622  lea     rcx, [rsp+68h+StringUuid]; String
0x180010627  call    cs:__imp_RpcStringFreeW
0x18001062d  jmp     short loc_180010654
0x18001062f  call    cs:__imp_GetCurrentProcessId
0x180010635  mov     r9d, eax
0x180010638  mov     [rsp+68h+var_48], rdi
0x18001063d  lea     r8, aIdentitycrlCer; "IDENTITYCRL_CERT_CONTAINER"
0x180010644  lea     rdx, aLs08xP; "%ls_%08x_%p"
0x18001064b  mov     rcx, rbx
0x18001064e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180010653  nop
0x180010654  mov     rax, rdi
0x180010657  mov     rcx, [rsp+68h+var_18]
0x18001065c  xor     rcx, rsp; StackCookie
0x18001065f  call    __security_check_cookie
0x180010664  mov     rbx, [rsp+68h+arg_8]
0x180010669  add     rsp, 60h
0x18001066d  pop     rdi
0x18001066e  retn
```
