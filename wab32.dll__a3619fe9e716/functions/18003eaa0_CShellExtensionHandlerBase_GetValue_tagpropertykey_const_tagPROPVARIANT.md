# CShellExtensionHandlerBase::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18003eaa0`
- end: `0x18003ed1b`
- name: `?GetValue@CShellExtensionHandlerBase@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `635`
- prototype: `int(CShellExtensionHandlerBase *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ed30`

## callees

- `0x180002818`
- `0x180005d08`
- `0x18000d8b4`
- `0x180033410`
- `0x18003df28`
- `0x18003eaa0`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18003eb71`
- `KERNEL32!LocalAlloc` at `0x18003eb71`
- `KERNEL32!FileTimeToSystemTime` at `0x18003ec0f`
- `KERNEL32!FileTimeToSystemTime` at `0x18003ec0f`
- `ole32!PropVariantCopy` at `0x18003ecc2`
- `ole32!PropVariantCopy` at `0x18003ecc2`
- `ole32!PropVariantClear` at `0x18003eb0d`
- `ole32!PropVariantClear` at `0x18003ece2`
- `ole32!PropVariantClear` at `0x18003eb0d`
- `ole32!PropVariantClear` at `0x18003ece2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003eca8`
- `OLEAUT32!__imp_SysAllocString` at `0x18003eca8`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18003ec2d`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x18003ec2d`
- `OLEAUT32!__imp_VarDateFromUdate` at `0x18003ec69`
- `OLEAUT32!__imp_VarDateFromUdate` at `0x18003ec69`
- `OLEAUT32!__imp_VarUdateFromDate` at `0x18003ec51`
- `OLEAUT32!__imp_VarUdateFromDate` at `0x18003ec51`

## pseudocode

```c
__int64 __fastcall CShellExtensionHandlerBase::GetValue(
        CShellExtensionHandlerBase *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  int v6; // ebx
  unsigned int v7; // r8d
  unsigned int i; // edi
  struct _SPropValue *v9; // rbx
  int SPropFromIContactProperties; // eax
  int ulPropTag; // eax
  HRESULT LastError; // eax
  CURRENCY cur; // rcx
  __int64 v14; // rax
  DATE pdateOut; // [rsp+20h] [rbp-60h] BYREF
  struct IContactProperties *v17; // [rsp+28h] [rbp-58h] BYREF
  DOUBLE pvtime[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h]
  struct _SPropValue *v20; // [rsp+48h] [rbp-38h] BYREF
  UDATE pudateOut; // [rsp+50h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-18h] BYREF

  v17 = 0;
  v20 = 0;
  *(_OWORD *)pvtime = 0;
  v19 = 0;
  if ( !*((_QWORD *)this + 5) )
  {
    v6 = -2147418113;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_35;
  }
  PropVariantClear(a3);
  v6 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IContactProperties **))this + 5))(
         *((_QWORD *)this + 5),
         &GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f,
         &v17);
  if ( v6 < 0 )
    goto LABEL_35;
  v7 = *((_DWORD *)this + 28);
  for ( i = 0; i < v7; ++i )
  {
    if ( (unsigned int)operator==(*((_QWORD *)this + 13) + 32LL * i, a2) )
      break;
  }
  if ( v7 == i )
    goto LABEL_34;
  v20 = (struct _SPropValue *)LocalAlloc(0x40u, 0x18u);
  v9 = v20;
  if ( !v20 )
  {
LABEL_11:
    v6 = -2147024882;
    goto LABEL_35;
  }
  v20->ulPropTag = *(_DWORD *)(32LL * i + *((_QWORD *)this + 13) + 20);
  SPropFromIContactProperties = CContactStorage::GetSPropFromIContactProperties(v17, v9);
  if ( SPropFromIContactProperties >= 0 )
  {
    ulPropTag = (unsigned __int16)v9->ulPropTag;
    if ( ulPropTag != 10 )
    {
      if ( ulPropTag == 31 )
      {
        cur = v9->Value.cur;
        if ( cur.int64 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)(cur.int64 + 2 * v14) );
          if ( v14 )
          {
            LOWORD(pvtime[0]) = 8;
            *(_QWORD *)&pvtime[1] = SysAllocString(v9->Value.lpszW);
            if ( !*(_QWORD *)&pvtime[1] )
              goto LABEL_11;
          }
        }
        goto LABEL_33;
      }
      if ( ulPropTag == 64 )
      {
        memset(&pudateOut, 0, sizeof(pudateOut));
        pdateOut = 0.0;
        SystemTime = 0;
        if ( v9->Value.l )
        {
          LOWORD(pvtime[0]) = 7;
          if ( !FileTimeToSystemTime((const FILETIME *)&v9->Value, &SystemTime) )
          {
            LastError = HrGetLastError();
LABEL_22:
            v6 = LastError;
            goto LABEL_35;
          }
          if ( !SystemTimeToVariantTime(&SystemTime, &pvtime[1]) )
          {
            v6 = -2147467259;
            goto LABEL_35;
          }
          pdateOut = pvtime[1];
          if ( VarUdateFromDate(pvtime[1], 0, &pudateOut) >= 0 )
          {
            *(_QWORD *)&pudateOut.st.wHour = 0;
            if ( VarDateFromUdate(&pudateOut, 0, &pdateOut) >= 0 )
              pvtime[1] = pdateOut;
          }
LABEL_33:
          LastError = PropVariantCopy(a3, (const PROPVARIANT *)pvtime);
          goto LABEL_22;
        }
      }
    }
LABEL_34:
    v6 = 0;
    goto LABEL_35;
  }
  v6 = 0;
  if ( SPropFromIContactProperties != -2147024893 )
    v6 = SPropFromIContactProperties;
LABEL_35:
  LocalFreePropArray(1u, &v20);
  PropVariantClear((PROPVARIANT *)pvtime);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003eaa0  mov     [rsp-28h+arg_8], rbx
0x18003eaa5  mov     [rsp-28h+arg_18], rsi
0x18003eaaa  push    rbp
0x18003eaab  push    rdi
0x18003eaac  push    r12
0x18003eaae  push    r14
0x18003eab0  push    r15
0x18003eab2  mov     rbp, rsp
0x18003eab5  sub     rsp, 80h
0x18003eabc  mov     rax, cs:__security_cookie
0x18003eac3  xor     rax, rsp
0x18003eac6  mov     [rbp+var_8], rax
0x18003eaca  xor     r12d, r12d
0x18003eacd  xor     eax, eax
0x18003eacf  xorps   xmm0, xmm0
0x18003ead2  mov     r14, r8
0x18003ead5  mov     r15, rdx
0x18003ead8  mov     rsi, rcx
0x18003eadb  mov     [rbp+var_58], r12
0x18003eadf  mov     [rbp+var_38], r12
0x18003eae3  movups  xmmword ptr [rbp+pvtime], xmm0
0x18003eae7  mov     [rbp+var_40], rax
0x18003eaeb  cmp     [rcx+28h], r12
0x18003eaef  jnz     short loc_18003EAFB
0x18003eaf1  mov     ebx, 8000FFFFh
0x18003eaf6  jmp     loc_18003ECD0
0x18003eafb  test    r14, r14
0x18003eafe  jnz     short loc_18003EB0A
0x18003eb00  mov     ebx, 80070057h
0x18003eb05  jmp     loc_18003ECD0
0x18003eb0a  mov     rcx, r14; pvar
0x18003eb0d  call    cs:__imp_PropVariantClear
0x18003eb13  mov     rcx, [rsi+28h]
0x18003eb17  lea     r8, [rbp+var_58]
0x18003eb1b  lea     rdx, _GUID_70dd27dd_5cbd_46e8_bef0_23b6b346288f
0x18003eb22  mov     rax, [rcx]
0x18003eb25  mov     rax, [rax]
0x18003eb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eb2d  mov     ebx, eax
0x18003eb2f  test    eax, eax
0x18003eb31  js      loc_18003ECD0
0x18003eb37  mov     r8d, [rsi+70h]
0x18003eb3b  mov     edi, r12d
0x18003eb3e  test    r8d, r8d
0x18003eb41  jz      short loc_18003EB60
0x18003eb43  mov     ecx, edi
0x18003eb45  mov     rdx, r15
0x18003eb48  shl     rcx, 5
0x18003eb4c  add     rcx, [rsi+68h]
0x18003eb50  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18003eb55  test    eax, eax
0x18003eb57  jnz     short loc_18003EB60
0x18003eb59  inc     edi
0x18003eb5b  cmp     edi, r8d
0x18003eb5e  jb      short loc_18003EB43
0x18003eb60  cmp     r8d, edi
0x18003eb63  jz      loc_18003ECCD
0x18003eb69  mov     edx, 18h; uBytes
0x18003eb6e  lea     ecx, [rdx+28h]; uFlags
0x18003eb71  call    cs:__imp_LocalAlloc
0x18003eb77  mov     [rbp+var_38], rax
0x18003eb7b  mov     rbx, rax
0x18003eb7e  test    rax, rax
0x18003eb81  jnz     short loc_18003EB8D
0x18003eb83  mov     ebx, 8007000Eh
0x18003eb88  jmp     loc_18003ECD0
0x18003eb8d  mov     rax, [rsi+68h]
0x18003eb91  mov     rdx, rbx; struct _SPropValue *
0x18003eb94  mov     ecx, edi
0x18003eb96  shl     rcx, 5
0x18003eb9a  mov     ecx, [rcx+rax+14h]
0x18003eb9e  mov     [rbx], ecx
0x18003eba0  mov     rcx, [rbp+var_58]; struct IContactProperties *
0x18003eba4  call    ?GetSPropFromIContactProperties@CContactStorage@@SAJPEAUIContactProperties@@PEAU_SPropValue@@@Z; CContactStorage::GetSPropFromIContactProperties(IContactProperties *,_SPropValue *)
0x18003eba9  test    eax, eax
0x18003ebab  jns     short loc_18003EBBD
0x18003ebad  cmp     eax, 80070003h
0x18003ebb2  mov     ebx, r12d
0x18003ebb5  cmovnz  ebx, eax
0x18003ebb8  jmp     loc_18003ECD0
0x18003ebbd  mov     eax, [rbx]
0x18003ebbf  movzx   eax, ax
0x18003ebc2  cmp     eax, 0Ah
0x18003ebc5  jz      loc_18003ECCD
0x18003ebcb  cmp     eax, 1Fh
0x18003ebce  jz      loc_18003EC7F
0x18003ebd4  cmp     eax, 40h ; '@'
0x18003ebd7  jnz     loc_18003ECCD
0x18003ebdd  xorps   xmm0, xmm0
0x18003ebe0  mov     [rbp+pudateOut.st.wYear], r12w
0x18003ebe5  xorps   xmm1, xmm1
0x18003ebe8  lea     rcx, [rbx+8]; lpFileTime
0x18003ebec  movsd   [rbp+pdateOut], xmm1
0x18003ebf1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18003ebf5  movups  xmmword ptr [rbp+pudateOut.st.wMonth], xmm0
0x18003ebf9  cmp     [rcx], r12d
0x18003ebfc  jz      loc_18003ECCD
0x18003ec02  mov     eax, 7
0x18003ec07  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18003ec0b  mov     word ptr [rbp+pvtime], ax
0x18003ec0f  call    cs:__imp_FileTimeToSystemTime
0x18003ec15  test    eax, eax
0x18003ec17  jnz     short loc_18003EC25
0x18003ec19  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18003ec1e  mov     ebx, eax
0x18003ec20  jmp     loc_18003ECD0
0x18003ec25  lea     rdx, [rbp+pvtime+8]; pvtime
0x18003ec29  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003ec2d  call    cs:__imp_SystemTimeToVariantTime
0x18003ec33  test    eax, eax
0x18003ec35  jnz     short loc_18003EC41
0x18003ec37  mov     ebx, 80004005h
0x18003ec3c  jmp     loc_18003ECD0
0x18003ec41  movsd   xmm0, [rbp+pvtime+8]; dateIn
0x18003ec46  lea     r8, [rbp+pudateOut]; pudateOut
0x18003ec4a  xor     edx, edx; dwFlags
0x18003ec4c  movsd   [rbp+pdateOut], xmm0
0x18003ec51  call    cs:__imp_VarUdateFromDate
0x18003ec57  test    eax, eax
0x18003ec59  js      short loc_18003ECBB
0x18003ec5b  lea     r8, [rbp+pdateOut]; pdateOut
0x18003ec5f  mov     qword ptr [rbp+pudateOut.st.wHour], r12
0x18003ec63  xor     edx, edx; dwFlags
0x18003ec65  lea     rcx, [rbp+pudateOut]; pudateIn
0x18003ec69  call    cs:__imp_VarDateFromUdate
0x18003ec6f  test    eax, eax
0x18003ec71  js      short loc_18003ECBB
0x18003ec73  movsd   xmm0, [rbp+pdateOut]
0x18003ec78  movsd   [rbp+pvtime+8], xmm0
0x18003ec7d  jmp     short loc_18003ECBB
0x18003ec7f  mov     rcx, [rbx+8]
0x18003ec83  test    rcx, rcx
0x18003ec86  jz      short loc_18003ECBB
0x18003ec88  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ec8c  inc     rax
0x18003ec8f  cmp     [rcx+rax*2], r12w
0x18003ec94  jnz     short loc_18003EC8C
0x18003ec96  test    rax, rax
0x18003ec99  jz      short loc_18003ECBB
0x18003ec9b  mov     eax, 8
0x18003eca0  mov     word ptr [rbp+pvtime], ax
0x18003eca4  mov     rcx, [rbx+8]; psz
0x18003eca8  call    cs:__imp_SysAllocString
0x18003ecae  mov     [rbp+pvtime+8], rax
0x18003ecb2  test    rax, rax
0x18003ecb5  jz      loc_18003EB83
0x18003ecbb  lea     rdx, [rbp+pvtime]; pvarSrc
0x18003ecbf  mov     rcx, r14; pvarDest
0x18003ecc2  call    cs:__imp_PropVariantCopy
0x18003ecc8  jmp     loc_18003EC1E
0x18003eccd  mov     ebx, r12d
0x18003ecd0  lea     rdx, [rbp+var_38]; struct _SPropValue **
0x18003ecd4  mov     ecx, 1; unsigned int
0x18003ecd9  call    ?LocalFreePropArray@@YAXKPEAPEAU_SPropValue@@@Z; LocalFreePropArray(ulong,_SPropValue * *)
0x18003ecde  lea     rcx, [rbp+pvtime]; pvar
0x18003ece2  call    cs:__imp_PropVariantClear
0x18003ece8  lea     rcx, [rbp+var_58]
0x18003ecec  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003ecf1  mov     eax, ebx
0x18003ecf3  mov     rcx, [rbp+var_8]
0x18003ecf7  xor     rcx, rsp; StackCookie
0x18003ecfa  call    __security_check_cookie
0x18003ecff  lea     r11, [rsp+80h+var_s0]
0x18003ed07  mov     rbx, [r11+38h]
0x18003ed0b  mov     rsi, [r11+48h]
0x18003ed0f  mov     rsp, r11
0x18003ed12  pop     r15
0x18003ed14  pop     r14
0x18003ed16  pop     r12
0x18003ed18  pop     rdi
0x18003ed19  pop     rbp
0x18003ed1a  retn
```
