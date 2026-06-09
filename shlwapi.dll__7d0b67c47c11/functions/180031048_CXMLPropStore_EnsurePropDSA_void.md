# CXMLPropStore::_EnsurePropDSA(void)

- ea: `0x180031048`
- end: `0x180031398`
- name: `?_EnsurePropDSA@CXMLPropStore@@IEAAJXZ`
- size: `848`
- prototype: `__int64 __fastcall(CXMLPropStore *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e210`
- `0x18002e2e0`

## callees

- `0x180012550`
- `0x18002d55c`
- `0x18002d5c8`
- `0x18002d63c`
- `0x18002d858`
- `0x18002dc2c`
- `0x18002df50`
- `0x18002e0ac`
- `0x18002e61c`
- `0x18002ff10`
- `0x180031048`
- `0x180031490`
- `0x180031598`
- `0x1800360f4`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031107`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031107`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x180031150`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x180031150`
- `SHELL32!__imp_GUIDFromStringW` at `0x1800310d5`
- `SHELL32!__imp_GUIDFromStringW` at `0x180031319`
- `SHELL32!__imp_GUIDFromStringW` at `0x1800310d5`
- `SHELL32!__imp_GUIDFromStringW` at `0x180031319`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18003119d`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18003119d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003133b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003133b`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_EnsurePropDSA(CXMLPropStore *this)
{
  signed int i; // ebx
  HDSA *v2; // r14
  HDSA v4; // rax
  unsigned int v5; // r15d
  HKEY v6; // rcx
  HKEY v7; // rcx
  int appended; // edi
  __int64 v9; // rax
  int v10; // edi
  __int64 v11; // rax
  CXMLPropStore *v12; // rcx
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  int piRet; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 pvData; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMNode *pcbData; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v20; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v21; // [rsp+88h] [rbp-78h] BYREF
  WCHAR pszString[20]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[40]; // [rsp+C0h] [rbp-40h] BYREF

  i = 0;
  v2 = (HDSA *)((char *)this + 88);
  if ( !*((_QWORD *)this + 11) )
  {
    v4 = DSA_Create(20, 10);
    *v2 = v4;
    if ( !v4 )
      return (unsigned int)-2147024882;
    if ( *((_QWORD *)this + 9) )
    {
      v5 = 0;
      do
      {
        v6 = (HKEY)*((_QWORD *)this + 9);
        v20 = 39;
        i = HrRegEnumKeyEx(v6, v5, SubKey, &v20);
        if ( !i )
        {
          v21 = 0;
          if ( !(unsigned int)GUIDFromStringW(SubKey, &v21)
            || (v7 = (HKEY)*((_QWORD *)this + 9), hkey = 0, RegOpenKeyExW(v7, SubKey, 0, 0x20019u, &hkey)) )
          {
            i = -2147467259;
          }
          else
          {
            do
            {
              LODWORD(bstrString) = 15;
              appended = HrRegEnumKeyEx(hkey, i, pszString, (unsigned int *)&bstrString);
              if ( !appended )
              {
                piRet = 0;
                appended = -2147467259;
                if ( StrToIntExW(pszString, 0, &piRet) )
                {
                  LODWORD(pvData) = 0;
                  LODWORD(pcbData) = 4;
                  if ( !SHRegGetValueW(hkey, pszString, L"VT", 16, 0, &pvData, (DWORD *)&pcbData) )
                  {
                    *((_DWORD *)&pvarg.decVal + 4) = piRet;
                    *(struct _GUID *)&pvarg.vt = v21;
                    appended = CDSA_Base<_tagpropertykey>::AppendItem(v2, &pvarg);
                  }
                }
              }
              ++i;
            }
            while ( !appended );
            RegCloseKey(hkey);
            i = 0;
            if ( appended != 1 )
              i = appended;
          }
        }
        ++v5;
      }
      while ( !i );
      if ( i == 1 )
      {
        i = 0;
      }
      else if ( i < 0 )
      {
        return (unsigned int)i;
      }
    }
    ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&pcbData);
    if ( (int)CXMLPropStore::_GetGenericPropsNode(this, &pcbData) >= 0 )
    {
      ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&pvData);
      v9 = ATL::CComPtrBase<IXMLDOMNodeList>::operator->(&pcbData);
      i = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 96LL))(v9, &pvData);
      if ( i >= 0 )
      {
        piRet = 0;
        v10 = 0;
        for ( i = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)pvData + 64LL))(pvData, &piRet); i >= 0; ++v10 )
        {
          if ( v10 >= piRet )
            break;
          ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(&hkey);
          v11 = ATL::CComPtrBase<IXMLDOMNodeList>::operator->(&pvData);
          i = (*(__int64 (__fastcall **)(__int64, _QWORD, HKEY *))(*(_QWORD *)v11 + 56LL))(
                v11,
                (unsigned int)v10,
                &hkey);
          if ( i >= 0 )
          {
            v21 = GUID_NULL;
            ATL::CComVariant::CComVariant((ATL::CComVariant *)&pvarg);
            ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"FMTID");
            i = CXMLPropStore::_GetAttributeFromNode(v12, (struct IXMLDOMNode *)hkey, bstrString, 8u, &pvarg);
            if ( i || (unsigned int)GUIDFromStringW(pvarg.llVal, &v21) )
              i = CXMLPropStore::_AddPropKeysToDSA(this, (struct IXMLDOMNode *)hkey, &v21);
            SysFreeString(bstrString);
            ATL::CComVariant::Clear(&pvarg);
          }
          ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&hkey);
        }
      }
      ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&pvData);
    }
    ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(&pcbData);
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180031048  push    rbp
0x18003104a  push    rbx
0x18003104b  push    rsi
0x18003104c  push    rdi
0x18003104d  push    r14
0x18003104f  push    r15
0x180031051  lea     rbp, [rsp-28h]
0x180031056  sub     rsp, 128h
0x18003105d  mov     rax, cs:__security_cookie
0x180031064  xor     rax, rsp
0x180031067  mov     [rbp+50h+var_40], rax
0x18003106b  xor     ebx, ebx
0x18003106d  lea     r14, [rcx+58h]
0x180031071  mov     rsi, rcx
0x180031074  cmp     [r14], rbx
0x180031077  jnz     loc_18003137A
0x18003107d  lea     edx, [rbx+0Ah]; cItemGrow
0x180031080  lea     ecx, [rbx+14h]; cbItem
0x180031083  call    DSA_Create
0x180031088  mov     [r14], rax
0x18003108b  test    rax, rax
0x18003108e  jz      loc_180031375
0x180031094  cmp     [rsi+48h], rbx
0x180031098  jz      loc_180031208
0x18003109e  xor     r15d, r15d
0x1800310a1  mov     rcx, [rsi+48h]; HKEY
0x1800310a5  lea     r9, [rbp+50h+var_D0]; unsigned int *
0x1800310a9  lea     r8, [rbp+50h+SubKey]; unsigned __int16 *
0x1800310ad  mov     [rbp+50h+var_D0], 27h ; '''
0x1800310b4  mov     edx, r15d; unsigned int
0x1800310b7  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x1800310bc  mov     ebx, eax
0x1800310be  test    eax, eax
0x1800310c0  jnz     loc_1800311EC
0x1800310c6  xorps   xmm0, xmm0
0x1800310c9  lea     rdx, [rbp+50h+var_C8]
0x1800310cd  lea     rcx, [rbp+50h+SubKey]
0x1800310d1  movups  xmmword ptr [rbp+50h+var_C8.Data1], xmm0
0x1800310d5  call    cs:__imp_GUIDFromStringW
0x1800310db  test    eax, eax
0x1800310dd  jz      loc_1800311E7
0x1800310e3  mov     rcx, [rsi+48h]; hKey
0x1800310e7  lea     rax, [rsp+150h+hkey]
0x1800310ec  mov     r9d, 20019h; samDesired
0x1800310f2  mov     [rsp+150h+phkResult], rax; phkResult
0x1800310f7  xor     r8d, r8d; ulOptions
0x1800310fa  mov     [rsp+150h+hkey], 0
0x180031103  lea     rdx, [rbp+50h+SubKey]; lpSubKey
0x180031107  call    cs:__imp_RegOpenKeyExW
0x18003110d  test    eax, eax
0x18003110f  jnz     loc_1800311E7
0x180031115  mov     rcx, [rsp+150h+hkey]; HKEY
0x18003111a  lea     r9, [rsp+150h+bstrString]; unsigned int *
0x18003111f  lea     r8, [rbp+50h+pszString]; unsigned __int16 *
0x180031123  mov     dword ptr [rsp+150h+bstrString], 0Fh
0x18003112b  mov     edx, ebx; unsigned int
0x18003112d  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *)
0x180031132  mov     edi, eax
0x180031134  test    eax, eax
0x180031136  jnz     loc_1800311C8
0x18003113c  lea     r8, [rsp+150h+piRet]; piRet
0x180031141  mov     [rsp+150h+piRet], eax
0x180031145  xor     edx, edx; dwFlags
0x180031147  lea     rcx, [rbp+50h+pszString]; pszString
0x18003114b  mov     edi, 80004005h
0x180031150  call    cs:__imp_StrToIntExW
0x180031156  test    eax, eax
0x180031158  jz      short loc_1800311C8
0x18003115a  mov     rcx, [rsp+150h+hkey]; hkey
0x18003115f  lea     rax, [rsp+150h+var_E0]
0x180031164  mov     [rsp+150h+pcbData], rax; pcbData
0x180031169  lea     r8, ValueName; "VT"
0x180031170  lea     rax, [rsp+150h+var_E8]
0x180031175  mov     dword ptr [rsp+150h+var_E8], 0
0x18003117d  mov     [rsp+150h+pvData], rax; pvData
0x180031182  lea     rdx, [rbp+50h+pszString]; pszSubKey
0x180031186  mov     r9d, 10h; srrfFlags
0x18003118c  mov     [rsp+150h+phkResult], 0; pdwType
0x180031195  mov     dword ptr [rsp+150h+var_E0], 4
0x18003119d  call    cs:__imp_SHRegGetValueW
0x1800311a3  test    eax, eax
0x1800311a5  jnz     short loc_1800311C8
0x1800311a7  movups  xmm0, xmmword ptr [rbp+50h+var_C8.Data1]
0x1800311ab  mov     eax, [rsp+150h+piRet]
0x1800311af  lea     rdx, [rsp+150h+pvarg]
0x1800311b4  mov     rcx, r14
0x1800311b7  mov     dword ptr [rsp+150h+pvarg+10h], eax
0x1800311bb  movdqu  xmmword ptr [rsp+150h+pvarg], xmm0
0x1800311c1  call    ?AppendItem@?$CDSA_Base@U_tagpropertykey@@@@QEAAJPEBU_tagpropertykey@@PEAH@Z; CDSA_Base<_tagpropertykey>::AppendItem(_tagpropertykey const *,int *)
0x1800311c6  mov     edi, eax
0x1800311c8  inc     ebx
0x1800311ca  test    edi, edi
0x1800311cc  jz      loc_180031115
0x1800311d2  mov     rcx, [rsp+150h+hkey]; hKey
0x1800311d7  call    cs:__imp_RegCloseKey
0x1800311dd  xor     ebx, ebx
0x1800311df  cmp     edi, 1
0x1800311e2  cmovnz  ebx, edi
0x1800311e5  jmp     short loc_1800311EC
0x1800311e7  mov     ebx, 80004005h
0x1800311ec  inc     r15d
0x1800311ef  test    ebx, ebx
0x1800311f1  jz      loc_1800310A1
0x1800311f7  cmp     ebx, 1
0x1800311fa  jnz     short loc_180031200
0x1800311fc  xor     ebx, ebx
0x1800311fe  jmp     short loc_180031208
0x180031200  test    ebx, ebx
0x180031202  js      loc_18003137A
0x180031208  lea     rcx, [rsp+150h+var_E0]
0x18003120d  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180031212  lea     rdx, [rsp+150h+var_E0]; struct IXMLDOMNode **
0x180031217  mov     rcx, rsi; this
0x18003121a  call    ?_GetGenericPropsNode@CXMLPropStore@@IEAAJPEAPEAUIXMLDOMNode@@@Z; CXMLPropStore::_GetGenericPropsNode(IXMLDOMNode * *)
0x18003121f  test    eax, eax
0x180031221  js      loc_180031369
0x180031227  lea     rcx, [rsp+150h+var_E8]
0x18003122c  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180031231  lea     rcx, [rsp+150h+var_E0]
0x180031236  call    ??C?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIXMLDOMNodeList@@@1@XZ; ATL::CComPtrBase<IXMLDOMNodeList>::operator->(void)
0x18003123b  mov     rcx, rax
0x18003123e  lea     rdx, [rsp+150h+var_E8]
0x180031243  mov     rax, [rax]
0x180031246  mov     rax, [rax+60h]
0x18003124a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003124f  mov     ebx, eax
0x180031251  test    eax, eax
0x180031253  js      loc_18003135F
0x180031259  mov     rcx, [rsp+150h+var_E8]
0x18003125e  lea     rdx, [rsp+150h+piRet]
0x180031263  mov     [rsp+150h+piRet], 0
0x18003126b  mov     rax, [rcx]
0x18003126e  mov     rax, [rax+40h]
0x180031272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031277  xor     edi, edi
0x180031279  mov     ebx, eax
0x18003127b  test    eax, eax
0x18003127d  js      loc_18003135F
0x180031283  cmp     edi, [rsp+150h+piRet]
0x180031287  jge     loc_18003135F
0x18003128d  lea     rcx, [rsp+150h+hkey]
0x180031292  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x180031297  lea     rcx, [rsp+150h+var_E8]
0x18003129c  call    ??C?$CComPtrBase@UIXMLDOMNodeList@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIXMLDOMNodeList@@@1@XZ; ATL::CComPtrBase<IXMLDOMNodeList>::operator->(void)
0x1800312a1  mov     r9, rax
0x1800312a4  lea     r8, [rsp+150h+hkey]
0x1800312a9  mov     edx, edi
0x1800312ab  mov     rcx, [rax]
0x1800312ae  mov     rax, [rcx+38h]
0x1800312b2  mov     rcx, r9
0x1800312b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312ba  mov     ebx, eax
0x1800312bc  test    eax, eax
0x1800312be  js      loc_18003134B
0x1800312c4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800312cb  lea     rcx, [rsp+150h+pvarg]; this
0x1800312d0  movdqu  xmmword ptr [rbp+50h+var_C8.Data1], xmm0
0x1800312d5  call    ??0CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::CComVariant(void)
0x1800312da  lea     rdx, aFmtid; "FMTID"
0x1800312e1  lea     rcx, [rsp+150h+bstrString]; this
0x1800312e6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800312eb  mov     r8, [rsp+150h+bstrString]; unsigned __int16 *
0x1800312f0  lea     rax, [rsp+150h+pvarg]
0x1800312f5  mov     rdx, [rsp+150h+hkey]; struct IXMLDOMNode *
0x1800312fa  mov     r9d, 8; unsigned __int16
0x180031300  mov     [rsp+150h+phkResult], rax; pvargDest
0x180031305  call    ?_GetAttributeFromNode@CXMLPropStore@@IEAAJPEAUIXMLDOMNode@@PEAGGPEAUtagVARIANT@@@Z; CXMLPropStore::_GetAttributeFromNode(IXMLDOMNode *,ushort *,ushort,tagVARIANT *)
0x18003130a  mov     ebx, eax
0x18003130c  test    eax, eax
0x18003130e  jnz     short loc_180031323
0x180031310  mov     rcx, qword ptr [rsp+150h+pvarg+8]
0x180031315  lea     rdx, [rbp+50h+var_C8]
0x180031319  call    cs:__imp_GUIDFromStringW
0x18003131f  test    eax, eax
0x180031321  jz      short loc_180031336
0x180031323  mov     rdx, [rsp+150h+hkey]; struct IXMLDOMNode *
0x180031328  lea     r8, [rbp+50h+var_C8]; struct _GUID *
0x18003132c  mov     rcx, rsi; this
0x18003132f  call    ?_AddPropKeysToDSA@CXMLPropStore@@IEAAJPEAUIXMLDOMNode@@AEBU_GUID@@@Z; CXMLPropStore::_AddPropKeysToDSA(IXMLDOMNode *,_GUID const &)
0x180031334  mov     ebx, eax
0x180031336  mov     rcx, [rsp+150h+bstrString]; bstrString
0x18003133b  call    cs:__imp_SysFreeString
0x180031341  lea     rcx, [rsp+150h+pvarg]; pvarg
0x180031346  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18003134b  lea     rcx, [rsp+150h+hkey]
0x180031350  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180031355  inc     edi
0x180031357  test    ebx, ebx
0x180031359  jns     loc_180031283
0x18003135f  lea     rcx, [rsp+150h+var_E8]
0x180031364  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180031369  lea     rcx, [rsp+150h+var_E0]
0x18003136e  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x180031373  jmp     short loc_18003137A
0x180031375  mov     ebx, 8007000Eh
0x18003137a  mov     eax, ebx
0x18003137c  mov     rcx, [rbp+50h+var_40]
0x180031380  xor     rcx, rsp; StackCookie
0x180031383  call    __security_check_cookie
0x180031388  add     rsp, 128h
0x18003138f  pop     r15
0x180031391  pop     r14
0x180031393  pop     rdi
0x180031394  pop     rsi
0x180031395  pop     rbx
0x180031396  pop     rbp
0x180031397  retn
```
