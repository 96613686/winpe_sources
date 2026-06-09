# EnumIdentitiesWithCachedCredentials

- ea: `0x18002abc0`
- end: `0x18002ada8`
- name: `EnumIdentitiesWithCachedCredentials`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18000a870`
- `0x18000ba8c`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x18000ecc4`
- `0x1800114f8`
- `0x180020ce0`
- `0x180024d50`
- `0x180029788`
- `0x18002abc0`
- `0x180048ecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ac6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ac88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002aca3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ac6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ac88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002aca3`

## string_xrefs

- `0x18002abe5`: `wszCachedCredType='%ls'`
- `0x18002abf1`: `IDCRL::EnumIdentitiesWithCachedCredentials`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnumIdentitiesWithCachedCredentials(__int64 a1, struct IDCRL::_tagPEIH **a2)
{
  __int64 v4; // rbx
  const unsigned __int16 *v5; // rsi
  const unsigned __int16 *v6; // r8
  unsigned int v7; // edi
  unsigned __int16 **v8; // rbx
  unsigned int v9; // ebx
  __int64 v11; // [rsp+40h] [rbp-78h] BYREF
  unsigned __int16 **v12; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v13; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int16 **v14; // [rsp+58h] [rbp-60h]
  int v15; // [rsp+60h] [rbp-58h] BYREF
  CPassportException *v16; // [rsp+68h] [rbp-50h] BYREF
  ATL::CAtlException *v17; // [rsp+70h] [rbp-48h] BYREF
  const wil::ResultException *v18; // [rsp+78h] [rbp-40h] BYREF
  char *v19[7]; // [rsp+80h] [rbp-38h] BYREF
  int NewExternalIterationHandle; // [rsp+D0h] [rbp+18h] BYREF
  unsigned int v21; // [rsp+D8h] [rbp+20h] BYREF

  NewExternalIterationHandle = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v19,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0x971u,
    (char *)&NewExternalIterationHandle,
    "IDCRL::EnumIdentitiesWithCachedCredentials",
    L"wszCachedCredType='%ls'",
    a1);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v11,
    a1);
  v4 = 0;
  v5 = 0;
  v12 = 0;
  v21 = 0;
  v13 = 0;
  v14 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v11);
  NewExternalIterationHandle = VerifyInitialized();
  if ( NewExternalIterationHandle >= 0 )
  {
    if ( (unsigned int)_o__wcsicmp(v11, L"ps:active") )
    {
      if ( (unsigned int)_o__wcsicmp(v11, L"ps:password") )
      {
        if ( (unsigned int)_o__wcsicmp(v11, L"ps:membernameonly") )
        {
          if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                               &v11,
                               L"ps:virtualapp=") )
          {
            if ( !*(_DWORD *)(v11 - 16) )
              v4 = 16777233;
          }
          else
          {
            v4 = 256;
            v5 = (const unsigned __int16 *)a1;
          }
        }
        else
        {
          v4 = 16;
        }
      }
      else
      {
        v4 = 1;
      }
    }
    else
    {
      v4 = 0x1000000;
    }
    NewExternalIterationHandle = WLIDCEnumIdentities(v4, v5, v6, &v21, &v12);
    if ( NewExternalIterationHandle >= 0 )
    {
      v7 = v21;
      v8 = v12;
      CMIDLPtrArray<unsigned short *>::Clear(&v13);
      try
      {
        v14 = v8;
        v13 = v7;
        NewExternalIterationHandle = CIdentityIteratorStore::GetNewExternalIterationHandleEx(
                                       (CIdentityIteratorStore *)(g_pPPCRL + 114),
                                       v21,
                                       v12,
                                       a2);
      }
      catch ( CPassportException *v16 )
      {
        NewExternalIterationHandle = *((_DWORD *)v16 + 2);
        if ( NewExternalIterationHandle >= 0 )
          NewExternalIterationHandle = -2147418113;
      }
      catch ( ATL::CAtlException *v17 )
      {
        NewExternalIterationHandle = *(_DWORD *)v17;
        if ( NewExternalIterationHandle >= 0 )
          NewExternalIterationHandle = -2147418113;
      }
      catch ( std::bad_alloc )
      {
        NewExternalIterationHandle = -2147024882;
      }
      catch ( long v15 )
      {
        NewExternalIterationHandle = v15;
        if ( v15 >= 0 )
          NewExternalIterationHandle = -2147418113;
      }
      catch ( const wil::ResultException *v18 )
      {
        NewExternalIterationHandle = *((_DWORD *)v18 + 8);
        if ( NewExternalIterationHandle >= 0 )
          NewExternalIterationHandle = -2147418113;
      }
    }
  }
  v9 = NewExternalIterationHandle;
  CMIDLPtrArray<unsigned short *>::Clear(&v13);
  ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v19);
  return v9;
}

```

## disassembly

```asm
0x18002abc0  mov     r11, rsp
0x18002abc3  mov     [r11+8], rbx
0x18002abc7  push    rsi
0x18002abc8  push    rdi
0x18002abc9  push    r14
0x18002abcb  sub     rsp, 0A0h
0x18002abd2  mov     r14, rdx
0x18002abd5  mov     rdi, rcx
0x18002abd8  mov     dword ptr [r11+18h], 0
0x18002abe0  mov     [rsp+0B8h+var_88], rcx
0x18002abe5  lea     rax, aWszcachedcredt; "wszCachedCredType='%ls'"
0x18002abec  mov     [rsp+0B8h+var_90], rax
0x18002abf1  lea     rax, aIdcrlEnumident; "IDCRL::EnumIdentitiesWithCachedCredenti"...
0x18002abf8  mov     [rsp+0B8h+var_98], rax
0x18002abfd  lea     r9, [r11+18h]
0x18002ac01  mov     r8d, 971h
0x18002ac07  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002ac0e  lea     rcx, [r11-38h]
0x18002ac12  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x18002ac17  nop
0x18002ac18  mov     rdx, rdi
0x18002ac1b  lea     rcx, [rsp+0B8h+var_78]
0x18002ac20  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002ac25  nop
0x18002ac26  xor     ebx, ebx
0x18002ac28  xor     esi, esi
0x18002ac2a  mov     [rsp+0B8h+var_70], rbx
0x18002ac2f  mov     [rsp+0B8h+arg_18], ebx
0x18002ac36  mov     [rsp+0B8h+var_68], ebx
0x18002ac3a  mov     [rsp+0B8h+var_60], rbx
0x18002ac3f  lea     rcx, [rsp+0B8h+var_78]
0x18002ac44  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x18002ac49  nop
0x18002ac4a  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x18002ac4f  mov     [rsp+0B8h+arg_10], eax
0x18002ac56  test    eax, eax
0x18002ac58  jns     short loc_18002AC5F
0x18002ac5a  jmp     loc_18002AD5B
0x18002ac5f  lea     rdx, aPsActive; "ps:active"
0x18002ac66  mov     rcx, [rsp+0B8h+var_78]
0x18002ac6b  call    cs:__imp__o__wcsicmp
0x18002ac71  test    eax, eax
0x18002ac73  jnz     short loc_18002AC7C
0x18002ac75  mov     ebx, 1000000h
0x18002ac7a  jmp     short loc_18002ACE3
0x18002ac7c  lea     rdx, aPsPassword; "ps:password"
0x18002ac83  mov     rcx, [rsp+0B8h+var_78]
0x18002ac88  call    cs:__imp__o__wcsicmp
0x18002ac8e  test    eax, eax
0x18002ac90  jnz     short loc_18002AC97
0x18002ac92  lea     ebx, [rax+1]
0x18002ac95  jmp     short loc_18002ACE3
0x18002ac97  lea     rdx, aPsMembernameon; "ps:membernameonly"
0x18002ac9e  mov     rcx, [rsp+0B8h+var_78]
0x18002aca3  call    cs:__imp__o__wcsicmp
0x18002aca9  test    eax, eax
0x18002acab  jnz     short loc_18002ACB2
0x18002acad  lea     ebx, [rax+10h]
0x18002acb0  jmp     short loc_18002ACE3
0x18002acb2  lea     rdx, aPsVirtualapp; "ps:virtualapp="
0x18002acb9  lea     rcx, [rsp+0B8h+var_78]
0x18002acbe  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x18002acc3  test    eax, eax
0x18002acc5  jnz     short loc_18002ACD1
0x18002acc7  mov     ebx, 100h
0x18002accc  mov     rsi, rdi
0x18002accf  jmp     short loc_18002ACE3
0x18002acd1  mov     ecx, 1000011h
0x18002acd6  mov     rax, [rsp+0B8h+var_78]
0x18002acdb  cmp     dword ptr [rax-10h], 0
0x18002acdf  cmovz   rbx, rcx
0x18002ace3  lea     rax, [rsp+0B8h+var_70]
0x18002ace8  mov     [rsp+0B8h+var_98], rax; unsigned __int16 ***
0x18002aced  lea     r9, [rsp+0B8h+arg_18]; unsigned int *
0x18002acf5  mov     rdx, rsi; unsigned __int16 *
0x18002acf8  mov     rcx, rbx; unsigned __int64
0x18002acfb  call    ?WLIDCEnumIdentities@@YAJ_KPEBG1PEAKPEAPEAPEAG@Z; WLIDCEnumIdentities(unsigned __int64,ushort const *,ushort const *,ulong *,ushort * * *)
0x18002ad00  mov     [rsp+0B8h+arg_10], eax
0x18002ad07  test    eax, eax
0x18002ad09  jns     short loc_18002AD0D
0x18002ad0b  jmp     short loc_18002AD5B
0x18002ad0d  mov     edi, [rsp+0B8h+arg_18]
0x18002ad14  mov     rbx, [rsp+0B8h+var_70]
0x18002ad19  lea     rcx, [rsp+0B8h+var_68]
0x18002ad1e  call    ?Clear@?$CMIDLPtrArray@PEAG@@QEAAXXZ; CMIDLPtrArray<ushort *>::Clear(void)
0x18002ad23  mov     [rsp+0B8h+var_60], rbx
0x18002ad28  mov     [rsp+0B8h+var_68], edi
0x18002ad2c  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18002ad33  add     rcx, 1C8h; this
0x18002ad3a  mov     r9, r14; struct IDCRL::_tagPEIH **
0x18002ad3d  mov     r8, [rsp+0B8h+var_70]; unsigned __int16 **
0x18002ad42  mov     edx, [rsp+0B8h+arg_18]; unsigned int
0x18002ad49  call    ?GetNewExternalIterationHandleEx@CIdentityIteratorStore@@QEAAJKPEBQEAGPEAPEAU_tagPEIH@IDCRL@@@Z; CIdentityIteratorStore::GetNewExternalIterationHandleEx(ulong,ushort * const *,IDCRL::_tagPEIH * *)
0x18002ad4e  mov     [rsp+0B8h+arg_10], eax
0x18002ad55  test    eax, eax
0x18002ad57  jns     short loc_18002AD5B
0x18002ad59  jmp     short $+2
0x18002ad5b  mov     ebx, [rsp+0B8h+arg_10]
0x18002ad62  lea     rcx, [rsp+0B8h+var_68]
0x18002ad67  call    ?Clear@?$CMIDLPtrArray@PEAG@@QEAAXXZ; CMIDLPtrArray<ushort *>::Clear(void)
0x18002ad6c  nop
0x18002ad6d  mov     rcx, [rsp+0B8h+var_78]
0x18002ad72  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002ad76  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002ad7b  nop
0x18002ad7c  lea     rcx, [rsp+0B8h+var_38]
0x18002ad84  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002ad89  mov     eax, ebx
0x18002ad8b  mov     rbx, [rsp+0B8h+arg_0]
0x18002ad93  add     rsp, 0A0h
0x18002ad9a  pop     r14
0x18002ad9c  pop     rdi
0x18002ad9d  pop     rsi
0x18002ad9e  retn
0x18002ad9f  jmp     short loc_18002AD5B
0x18002ada1  jmp     short loc_18002AD5B
0x18002ada3  jmp     short loc_18002AD5B
0x18002ada5  jmp     short loc_18002AD5B
```
