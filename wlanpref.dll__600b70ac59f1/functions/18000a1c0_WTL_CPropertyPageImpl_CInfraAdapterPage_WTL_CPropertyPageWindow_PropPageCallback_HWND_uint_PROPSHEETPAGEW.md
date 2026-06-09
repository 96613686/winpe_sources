# WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>::PropPageCallback(HWND__ *,uint,_PROPSHEETPAGEW *)

- ea: `0x18000a1c0`
- end: `0x18000a25d`
- name: `?PropPageCallback@?$CPropertyPageImpl@VCInfraAdapterPage@@VCPropertyPageWindow@WTL@@@WTL@@SAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003014`
- `0x180008560`
- `0x18000a1c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a256`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a256`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1f8`

## pseudocode

```c
__int64 __fastcall WTL::CPropertyPageImpl<CInfraAdapterPage,WTL::CPropertyPageWindow>::PropPageCallback(
        __int64 a1,
        int a2,
        __int64 a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rbx
  __int64 *v6; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+28h] [rbp-10h]

  result = 0;
  if ( a2 == 2 )
  {
    v4 = (*(_QWORD *)(a3 + 48) + 96LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(a3 + 48) >> 64);
    v5 = (_QWORD *)(v4 + 16);
    if ( v4 == -16 || !v4 )
    {
      RaiseException(0xC0000005, 1u, 0, 0);
      JUMPOUT(0x18000A25CLL);
    }
    *v5 = v4;
    v7 = 0;
    *(_DWORD *)(v4 + 24) = GetCurrentThreadId();
    v6 = qword_18003FA18;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      v5[2] = qword_18003FA40;
      qword_18003FA40 = (__int64)v5;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v6);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000a1c0  push    rbx
0x18000a1c2  sub     rsp, 30h
0x18000a1c6  xor     eax, eax
0x18000a1c8  test    edx, edx
0x18000a1ca  jz      short loc_18000A241
0x18000a1cc  sub     edx, 1
0x18000a1cf  jz      short loc_18000A241
0x18000a1d1  cmp     edx, 1
0x18000a1d4  jnz     short loc_18000A241
0x18000a1d6  mov     rax, [r8+30h]
0x18000a1da  lea     rcx, [rax+60h]
0x18000a1de  neg     rax
0x18000a1e1  sbb     rdx, rdx
0x18000a1e4  and     rdx, rcx
0x18000a1e7  lea     rbx, [rdx+10h]
0x18000a1eb  test    rbx, rbx
0x18000a1ee  jz      short loc_18000A247
0x18000a1f0  test    rdx, rdx
0x18000a1f3  jz      short loc_18000A247
0x18000a1f5  mov     [rbx], rdx
0x18000a1f8  call    cs:__imp_GetCurrentThreadId
0x18000a1fe  lea     rcx, [rsp+38h+var_18]
0x18000a203  mov     [rsp+38h+var_10], 0
0x18000a208  mov     [rbx+8], eax
0x18000a20b  lea     rax, qword_18003FA18
0x18000a212  mov     [rsp+38h+var_18], rax
0x18000a217  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000a21c  test    eax, eax
0x18000a21e  js      short loc_18000A232
0x18000a220  mov     rax, cs:qword_18003FA40
0x18000a227  mov     [rbx+10h], rax
0x18000a22b  mov     cs:qword_18003FA40, rbx
0x18000a232  lea     rcx, [rsp+38h+var_18]
0x18000a237  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000a23c  mov     eax, 1
0x18000a241  add     rsp, 30h
0x18000a245  pop     rbx
0x18000a246  retn
0x18000a247  xor     r9d, r9d; lpArguments
0x18000a24a  xor     r8d, r8d; nNumberOfArguments
0x18000a24d  mov     ecx, 0C0000005h; dwExceptionCode
0x18000a252  lea     edx, [r9+1]; dwExceptionFlags
0x18000a256  call    cs:__imp_RaiseException
```
