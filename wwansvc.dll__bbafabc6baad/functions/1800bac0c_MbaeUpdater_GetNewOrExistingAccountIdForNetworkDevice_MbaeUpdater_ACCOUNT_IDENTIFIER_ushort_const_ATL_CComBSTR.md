# MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice(MbaeUpdater::ACCOUNT_IDENTIFIER,ushort const *,ATL::CComBSTR *)

- ea: `0x1800bac0c`
- end: `0x1800bada2`
- name: `?_GetNewOrExistingAccountIdForNetworkDevice@MbaeUpdater@@AEAAJW4ACCOUNT_IDENTIFIER@1@PEBGPEAVCComBSTR@ATL@@@Z`
- size: `406`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b9de8`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180013ad0`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x1800b9a58`
- `0x1800ba800`
- `0x1800bac0c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800bac49`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bac49`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bacc0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bad14`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bacc0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800bad14`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800baca1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800baca1`

## string_xrefs

- `0x1800bac35`: `MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice`
- `0x1800bad28`: `MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice`
- `0x1800bad78`: `MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice`

## pseudocode

```c
__int64 __fastcall MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        BSTR *a4)
{
  int AccountIdForNetworkDevice; // eax
  __int64 v9; // r8
  HRESULT v10; // ebx
  GUID *p_pguid; // rax
  __int64 *v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // edx
  GUID pguid; // [rsp+30h] [rbp-D0h] BYREF
  char v17; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR v18[40]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF

  WwanLog::Enter("MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice");
  SysFreeString(*a4);
  *a4 = 0;
  AccountIdForNetworkDevice = MbaeUpdater::_FindAccountIdForNetworkDevice(a1, a2, a3, a4);
  v10 = AccountIdForNetworkDevice;
  if ( AccountIdForNetworkDevice >= 0 )
  {
    if ( (Microsoft_Windows_WWAN_SVC_EVENTSEnableBits & 4) != 0 )
    {
      p_pguid = &pguid;
      v12 = MbaeUpdaterExistingAccount;
LABEL_12:
      McGenEventWrite_EventWriteTransfer(&WWAN_EVT_GUID_Context, v12, v9, 1, p_pguid);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  if ( AccountIdForNetworkDevice == -2147023728 )
  {
    pguid = 0;
    v10 = CoCreateGuid(&pguid);
    if ( v10 >= 0 )
    {
      v10 = StringFromGUID2(&pguid, sz, 40);
      if ( v10 >= 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( sz[v13] );
        v10 = ATL::CComBSTR::Append((ATL::CComBSTR *)a4, sz, v13);
        if ( v10 >= 0 )
        {
          memset_0(v18, 0, 0x4Eu);
          StringFromGUID2(&pguid, v18, 39);
          WwanLog::Verbose(
            "MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice",
            0,
            L" Creating new account id (%S)",
            v18);
          if ( (Microsoft_Windows_WWAN_SVC_EVENTSEnableBits & 4) != 0 )
          {
            p_pguid = (GUID *)&v17;
            v12 = MbaeUpdaterNewAccount;
            goto LABEL_12;
          }
LABEL_13:
          v14 = 0;
          goto LABEL_16;
        }
      }
    }
  }
  v14 = (unsigned __int16)v10;
  if ( (v10 & 0x1FFF0000) != 0x70000 )
    v14 = v10;
LABEL_16:
  WwanLog::ExitWithStatus("MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice", v14);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800bac0c  push    rbp
0x1800bac0e  push    rbx
0x1800bac0f  push    rsi
0x1800bac10  push    rdi
0x1800bac11  push    r14
0x1800bac13  push    r15
0x1800bac15  lea     rbp, [rsp-8]
0x1800bac1a  sub     rsp, 108h
0x1800bac21  mov     rax, cs:__security_cookie
0x1800bac28  xor     rax, rsp
0x1800bac2b  mov     [rbp+30h+var_40], rax
0x1800bac2f  mov     rbx, rcx
0x1800bac32  mov     r14, r9
0x1800bac35  lea     rcx, aMbaeupdaterGet_0; "MbaeUpdater::_GetNewOrExistingAccountId"...
0x1800bac3c  mov     rsi, r8
0x1800bac3f  mov     edi, edx
0x1800bac41  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800bac46  mov     rcx, [r14]; bstrString
0x1800bac49  call    cs:__imp_SysFreeString
0x1800bac4f  xor     r15d, r15d
0x1800bac52  mov     r9, r14
0x1800bac55  mov     r8, rsi
0x1800bac58  mov     [r14], r15
0x1800bac5b  mov     edx, edi
0x1800bac5d  mov     rcx, rbx
0x1800bac60  call    ?_FindAccountIdForNetworkDevice@MbaeUpdater@@AEAAJW4ACCOUNT_IDENTIFIER@1@PEBGPEAVCComBSTR@ATL@@@Z; MbaeUpdater::_FindAccountIdForNetworkDevice(MbaeUpdater::ACCOUNT_IDENTIFIER,ushort const *,ATL::CComBSTR *)
0x1800bac65  mov     ebx, eax
0x1800bac67  test    eax, eax
0x1800bac69  js      short loc_1800BAC89
0x1800bac6b  test    cs:Microsoft_Windows_WWAN_SVC_EVENTSEnableBits, 4
0x1800bac72  jz      loc_1800BAD60
0x1800bac78  lea     rax, [rsp+130h+pguid]
0x1800bac7d  lea     rdx, MbaeUpdaterExistingAccount
0x1800bac84  jmp     loc_1800BAD49
0x1800bac89  cmp     eax, 80070490h
0x1800bac8e  jnz     loc_1800BAD65
0x1800bac94  xorps   xmm0, xmm0
0x1800bac97  lea     rcx, [rsp+130h+pguid]; pguid
0x1800bac9c  movups  xmmword ptr [rsp+130h+pguid.Data1], xmm0
0x1800baca1  call    cs:__imp_CoCreateGuid
0x1800baca7  mov     ebx, eax
0x1800baca9  test    eax, eax
0x1800bacab  js      loc_1800BAD65
0x1800bacb1  mov     r8d, 28h ; '('; cchMax
0x1800bacb7  lea     rdx, [rbp+30h+sz]; lpsz
0x1800bacbb  lea     rcx, [rsp+130h+pguid]; rguid
0x1800bacc0  call    cs:__imp_StringFromGUID2
0x1800bacc6  mov     ebx, eax
0x1800bacc8  test    eax, eax
0x1800bacca  js      loc_1800BAD65
0x1800bacd0  lea     rax, [rbp+30h+sz]
0x1800bacd4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bacd8  inc     r8; int
0x1800bacdb  cmp     [rax+r8*2], r15w
0x1800bace0  jnz     short loc_1800BACD8
0x1800bace2  lea     rdx, [rbp+30h+sz]; unsigned __int16 *
0x1800bace6  mov     rcx, r14; this
0x1800bace9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800bacee  mov     ebx, eax
0x1800bacf0  test    eax, eax
0x1800bacf2  js      short loc_1800BAD65
0x1800bacf4  xor     edx, edx; Val
0x1800bacf6  lea     rcx, [rsp+130h+var_E0]; void *
0x1800bacfb  lea     r8d, [rdx+4Eh]; Size
0x1800bacff  call    memset_0
0x1800bad04  mov     r8d, 27h ; '''; cchMax
0x1800bad0a  lea     rdx, [rsp+130h+var_E0]; lpsz
0x1800bad0f  lea     rcx, [rsp+130h+pguid]; rguid
0x1800bad14  call    cs:__imp_StringFromGUID2
0x1800bad1a  lea     r9, [rsp+130h+var_E0]
0x1800bad1f  xor     edx, edx; struct _GUID *
0x1800bad21  lea     r8, aCreatingNewAcc; " Creating new account id (%S)"
0x1800bad28  lea     rcx, aMbaeupdaterGet_0; "MbaeUpdater::_GetNewOrExistingAccountId"...
0x1800bad2f  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800bad34  test    cs:Microsoft_Windows_WWAN_SVC_EVENTSEnableBits, 4
0x1800bad3b  jz      short loc_1800BAD60
0x1800bad3d  lea     rax, [rsp+130h+var_F0]
0x1800bad42  lea     rdx, MbaeUpdaterNewAccount
0x1800bad49  mov     r9d, 1
0x1800bad4f  mov     [rsp+130h+var_110], rax
0x1800bad54  lea     rcx, WWAN_EVT_GUID_Context
0x1800bad5b  call    McGenEventWrite_EventWriteTransfer
0x1800bad60  mov     edx, r15d
0x1800bad63  jmp     short loc_1800BAD78
0x1800bad65  mov     eax, ebx
0x1800bad67  movzx   edx, bx
0x1800bad6a  and     eax, 1FFF0000h
0x1800bad6f  cmp     eax, 70000h
0x1800bad74  jz      short loc_1800BAD78
0x1800bad76  mov     edx, ebx; unsigned int
0x1800bad78  lea     rcx, aMbaeupdaterGet_0; "MbaeUpdater::_GetNewOrExistingAccountId"...
0x1800bad7f  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800bad84  mov     eax, ebx
0x1800bad86  mov     rcx, [rbp+30h+var_40]
0x1800bad8a  xor     rcx, rsp; StackCookie
0x1800bad8d  call    __security_check_cookie
0x1800bad92  add     rsp, 108h
0x1800bad99  pop     r15
0x1800bad9b  pop     r14
0x1800bad9d  pop     rdi
0x1800bad9e  pop     rsi
0x1800bad9f  pop     rbx
0x1800bada0  pop     rbp
0x1800bada1  retn
```
