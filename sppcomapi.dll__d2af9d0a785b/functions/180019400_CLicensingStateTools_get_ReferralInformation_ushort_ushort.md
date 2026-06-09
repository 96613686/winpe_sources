# CLicensingStateTools::get_ReferralInformation(ushort *,ushort * *)

- ea: `0x180019400`
- end: `0x180019526`
- name: `?get_ReferralInformation@CLicensingStateTools@@UEAAJPEAGPEAPEAG@Z`
- size: `294`
- prototype: `int(CLicensingStateTools *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003520`
- `0x180004288`
- `0x180004d98`
- `0x180019400`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800194a1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800194a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019507`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019507`
- `SLC!SLOpen` at `0x180019441`
- `SLC!SLOpen` at `0x180019441`
- `SLC!SLClose` at `0x1800194e8`
- `SLC!SLClose` at `0x1800194e8`
- `sppcext!SLGetReferralInformation` at `0x180019475`
- `sppcext!SLGetReferralInformation` at `0x180019475`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_ReferralInformation(
        CLicensingStateTools *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  HRESULT BSTR; // eax
  unsigned __int16 *v8; // rax
  HSLC phSLC; // [rsp+48h] [rbp+10h] BYREF
  PWSTR ppwszValue; // [rsp+58h] [rbp+20h] BYREF

  ppwszValue = 0;
  phSLC = 0;
  if ( !a2 || !a3 )
  {
    v5 = 2147942487LL;
    v6 = -2147024809;
LABEL_14:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_15;
  }
  BSTR = SLOpen(&phSLC);
  v6 = BSTR;
  if ( BSTR < 0 )
  {
LABEL_5:
    v5 = (unsigned int)BSTR;
    goto LABEL_14;
  }
  if ( SLGetReferralInformation(phSLC, SL_REFERRALTYPE_APPID, &WINDOWS_SLID, a2, &ppwszValue) >= 0 )
  {
    BSTR = CreateBSTR(ppwszValue, a3);
    v6 = BSTR;
    if ( BSTR >= 0 )
      goto LABEL_15;
    goto LABEL_5;
  }
  v8 = SysAllocString(&word_18003FCD0);
  if ( v8 )
  {
    v6 = 0;
    *a3 = v8;
  }
  else
  {
    v6 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) != 0 )
  {
    v5 = v6;
    goto LABEL_14;
  }
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( phSLC )
  {
    SLClose(phSLC);
    phSLC = 0;
  }
  if ( ppwszValue )
    LocalFree(ppwszValue);
  return v6;
}

```

## disassembly

```asm
0x180019400  mov     rax, rsp
0x180019403  mov     [rax+8], rbx
0x180019407  mov     [rax+18h], rsi
0x18001940b  push    rdi
0x18001940c  sub     rsp, 30h
0x180019410  mov     qword ptr [rax+20h], 0
0x180019418  mov     rdi, r8
0x18001941b  mov     qword ptr [rax+10h], 0
0x180019423  mov     rsi, rdx
0x180019426  test    rdx, rdx
0x180019429  jnz     short loc_180019437
0x18001942b  mov     ecx, 80070057h
0x180019430  mov     ebx, ecx
0x180019432  jmp     loc_1800194D2
0x180019437  test    rdi, rdi
0x18001943a  jz      short loc_18001942B
0x18001943c  lea     rcx, [rsp+38h+phSLC]; phSLC
0x180019441  call    cs:__imp_SLOpen
0x180019448  nop     dword ptr [rax+rax+00h]
0x18001944d  mov     ebx, eax
0x18001944f  test    eax, eax
0x180019451  jns     short loc_180019457
0x180019453  mov     ecx, eax
0x180019455  jmp     short loc_1800194D2
0x180019457  mov     rcx, [rsp+38h+phSLC]; hSLC
0x18001945c  lea     rax, [rsp+38h+arg_18]
0x180019461  mov     r9, rsi; pwszValueName
0x180019464  mov     [rsp+38h+ppwszValue], rax; ppwszValue
0x180019469  lea     r8, WINDOWS_SLID; pSkuOrAppId
0x180019470  mov     edx, 1; eReferralType
0x180019475  call    cs:__imp_SLGetReferralInformation
0x18001947c  nop     dword ptr [rax+rax+00h]
0x180019481  test    eax, eax
0x180019483  js      short loc_18001949A
0x180019485  mov     rcx, [rsp+38h+arg_18]; unsigned __int16 *
0x18001948a  mov     rdx, rdi; unsigned __int16 **
0x18001948d  call    ?CreateBSTR@@YAJPEBGPEAPEAG@Z; CreateBSTR(ushort const *,ushort * *)
0x180019492  mov     ebx, eax
0x180019494  test    eax, eax
0x180019496  jns     short loc_1800194D7
0x180019498  jmp     short loc_180019453
0x18001949a  lea     rcx, word_18003FCD0; psz
0x1800194a1  call    cs:__imp_SysAllocString
0x1800194a8  nop     dword ptr [rax+rax+00h]
0x1800194ad  test    rax, rax
0x1800194b0  jnz     short loc_1800194C0
0x1800194b2  mov     ebx, 8007000Eh
0x1800194b7  mov     ecx, ebx
0x1800194b9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800194be  jmp     short loc_1800194C5
0x1800194c0  xor     ebx, ebx
0x1800194c2  mov     [rdi], rax
0x1800194c5  mov     ecx, ebx
0x1800194c7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800194cc  test    ebx, ebx
0x1800194ce  jns     short loc_1800194D7
0x1800194d0  mov     ecx, ebx
0x1800194d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800194d7  mov     ecx, ebx
0x1800194d9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800194de  mov     rcx, [rsp+38h+phSLC]; hSLC
0x1800194e3  test    rcx, rcx
0x1800194e6  jz      short loc_1800194FD
0x1800194e8  call    cs:__imp_SLClose
0x1800194ef  nop     dword ptr [rax+rax+00h]
0x1800194f4  mov     [rsp+38h+phSLC], 0
0x1800194fd  mov     rcx, [rsp+38h+arg_18]; hMem
0x180019502  test    rcx, rcx
0x180019505  jz      short loc_180019513
0x180019507  call    cs:__imp_LocalFree
0x18001950e  nop     dword ptr [rax+rax+00h]
0x180019513  mov     rsi, [rsp+38h+arg_10]
0x180019518  mov     eax, ebx
0x18001951a  mov     rbx, [rsp+38h+arg_0]
0x18001951f  add     rsp, 30h
0x180019523  pop     rdi
0x180019524  retn
```
