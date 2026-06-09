# WTL::CPropertyPageImpl<CWcnPageWlanPbcCombo,WTL::CPropertyPageWindow>::PropPageCallback(HWND__ *,uint,_PROPSHEETPAGEW *)

- ea: `0x18000c020`
- end: `0x18000c0c0`
- name: `?PropPageCallback@?$CPropertyPageImpl@VCWcnPageWlanPbcCombo@@VCPropertyPageWindow@WTL@@@WTL@@SAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800034c4`
- `0x18000a494`
- `0x18000c020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c0b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c0b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c05b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c05b`

## pseudocode

```c
__int64 __fastcall WTL::CPropertyPageImpl<CWcnPageWlanPbcCombo,WTL::CPropertyPageWindow>::PropPageCallback(
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
    v4 = (*(_QWORD *)(a3 + 48) + 144LL) & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(a3 + 48) >> 64);
    v5 = (_QWORD *)(v4 + 16);
    if ( v4 == -16 || !v4 )
    {
      RaiseException(0xC0000005, 1u, 0, 0);
      JUMPOUT(0x18000C0BFLL);
    }
    *v5 = v4;
    v7 = 0;
    *(_DWORD *)(v4 + 24) = GetCurrentThreadId();
    v6 = qword_18004D8E8;
    if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v6) >= 0 )
    {
      v5[2] = qword_18004D910;
      qword_18004D910 = (__int64)v5;
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v6);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000c020  push    rbx
0x18000c022  sub     rsp, 30h
0x18000c026  xor     eax, eax
0x18000c028  test    edx, edx
0x18000c02a  jz      short loc_18000C0A4
0x18000c02c  sub     edx, 1
0x18000c02f  jz      short loc_18000C0A4
0x18000c031  cmp     edx, 1
0x18000c034  jnz     short loc_18000C0A4
0x18000c036  mov     rax, [r8+30h]
0x18000c03a  lea     rcx, [rax+90h]
0x18000c041  neg     rax
0x18000c044  sbb     rdx, rdx
0x18000c047  and     rdx, rcx
0x18000c04a  lea     rbx, [rdx+10h]
0x18000c04e  test    rbx, rbx
0x18000c051  jz      short loc_18000C0AA
0x18000c053  test    rdx, rdx
0x18000c056  jz      short loc_18000C0AA
0x18000c058  mov     [rbx], rdx
0x18000c05b  call    cs:__imp_GetCurrentThreadId
0x18000c061  lea     rcx, [rsp+38h+var_18]
0x18000c066  mov     [rsp+38h+var_10], 0
0x18000c06b  mov     [rbx+8], eax
0x18000c06e  lea     rax, qword_18004D8E8
0x18000c075  mov     [rsp+38h+var_18], rax
0x18000c07a  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000c07f  test    eax, eax
0x18000c081  js      short loc_18000C095
0x18000c083  mov     rax, cs:qword_18004D910
0x18000c08a  mov     [rbx+10h], rax
0x18000c08e  mov     cs:qword_18004D910, rbx
0x18000c095  lea     rcx, [rsp+38h+var_18]
0x18000c09a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000c09f  mov     eax, 1
0x18000c0a4  add     rsp, 30h
0x18000c0a8  pop     rbx
0x18000c0a9  retn
0x18000c0aa  xor     r9d, r9d; lpArguments
0x18000c0ad  xor     r8d, r8d; nNumberOfArguments
0x18000c0b0  mov     ecx, 0C0000005h; dwExceptionCode
0x18000c0b5  lea     edx, [r9+1]; dwExceptionFlags
0x18000c0b9  call    cs:__imp_RaiseException
```
