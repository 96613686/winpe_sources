# CFSFolder::Load(IPropertyBag *,IErrorLog *)

- ea: `0x180183850`
- end: `0x180183b3b`
- name: `?Load@CFSFolder@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `747`
- prototype: `int(CFSFolder *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009fc0`
- `0x18005ef04`
- `0x180183850`
- `0x180183ff0`
- `0x180184380`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180183afa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180183afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180183ada`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180183aec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180183aec`
- `OLEAUT32!__imp_SysFreeString` at `0x180183aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x180183aa4`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1801838ff`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x1801838ff`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18018389f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801838c2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18018392d`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18018389f`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801838c2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18018392d`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180183968`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x180183968`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180183a5f`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x180183a5f`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1801838df`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180183a87`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1801838df`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180183a87`

## string_xrefs

- `0x180183a7d`: `TargetFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::Load(CFSFolder *this, struct IPropertyBag *a2, struct IErrorLog *a3)
{
  int v5; // ecx
  HRESULT GUID; // esi
  HRESULT (__stdcall *QueryInterface)(IPropertyBag *, const IID *const, void **); // rdi
  __int64 v8; // r14
  void (__fastcall *v9)(__int64, __int64, _QWORD *); // r15
  _QWORD *v10; // rdi
  HKEY v11; // rbp
  __int64 v12; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  DWORD LastError; // ebx
  INT v18[2]; // [rsp+20h] [rbp-48h] BYREF
  BOOL value; // [rsp+28h] [rbp-40h] BYREF
  DWORD v20; // [rsp+2Ch] [rbp-3Ch] BYREF

  CFSFolder::_ResetForInitialize((CFSFolder *)((char *)this - 136));
  *((_DWORD *)this + 100) |= 0x10u;
  PSPropertyBag_ReadDWORD(a2, L"Attributes", (DWORD *)this + 89);
  *((_DWORD *)this + 96) = 0;
  PSPropertyBag_ReadDWORD(a2, L"DescriptionID", (DWORD *)this + 96);
  PSPropertyBag_ReadBSTR(a2, L"HelpTopic", (BSTR *)this + 49);
  value = 0;
  PSPropertyBag_ReadBOOL(a2, L"AllowChildAliasRegistration", &value);
  *((_BYTE *)this + 405) = value;
  v20 = 0;
  PSPropertyBag_ReadDWORD(a2, L"RecursiveSearch", &v20);
  v5 = v20 != 0 ? 0x200 : 0;
  *((_DWORD *)this + 100) &= ~0x200u;
  *((_DWORD *)this + 100) |= v5;
  GUID = PSPropertyBag_ReadGUID(a2, L"TargetKnownFolder", (GUID *)((char *)this + 360));
  if ( GUID < 0 )
  {
    v18[0] = 0;
    if ( PSPropertyBag_ReadInt(a2, L"TargetSpecialFolder", v18) < 0
      || (GUID = SHKnownFolderFromCSIDL((unsigned int)v18[0], (char *)this + 360), GUID < 0) )
    {
      *(_QWORD *)v18 = 0;
      GUID = PSPropertyBag_ReadBSTR(a2, L"TargetFolderPath", (BSTR *)v18);
      if ( GUID >= 0 )
      {
        SysFreeString(*((BSTR *)this + 39));
        v15 = *(_QWORD *)v18;
        *((_QWORD *)this + 39) = *(_QWORD *)v18;
        v16 = *((unsigned int *)this + 89);
        if ( (_DWORD)v16 == -1 )
        {
          *((_DWORD *)this + 89) = 16;
          v16 = 16;
        }
        GUID = SHSimpleIDListFromAttributesAndFlags(v15, v16, v14, (char *)this + 304);
      }
    }
  }
  *((_DWORD *)this + 100) &= ~0x100u;
  *((_DWORD *)this + 100) |= (GUID >= 0) << 8;
  if ( GUID >= 0 )
  {
    *(_QWORD *)v18 = 0;
    QueryInterface = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v18);
    if ( ((int (__fastcall *)(struct IPropertyBag *, GUID *, INT *))QueryInterface)(
           a2,
           &GUID_d960050c_f4e1_4294_ac4b_598913605923,
           v18) >= 0 )
    {
      v8 = *(_QWORD *)v18;
      v9 = *(void (__fastcall **)(__int64, __int64, _QWORD *))(**(_QWORD **)v18 + 32LL);
      v10 = (_QWORD *)((char *)this + 800);
      v11 = (HKEY)*((_QWORD *)this + 100);
      if ( v11 )
      {
        LastError = GetLastError();
        RegCloseKey(v11);
        SetLastError(LastError);
      }
      *v10 = 0;
      v9(v8, 16, v10);
    }
    v12 = *(_QWORD *)v18;
    if ( *(_QWORD *)v18 )
    {
      *(_QWORD *)v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return (unsigned int)GUID;
}

```

## disassembly

```asm
0x180183850  mov     [rsp+arg_10], rbx
0x180183855  mov     [rsp+arg_18], rbp
0x18018385a  push    rsi
0x18018385b  push    rdi
0x18018385c  push    r12
0x18018385e  push    r14
0x180183860  push    r15
0x180183862  sub     rsp, 40h
0x180183866  mov     rax, cs:__security_cookie
0x18018386d  xor     rax, rsp
0x180183870  mov     [rsp+68h+var_38], rax
0x180183875  mov     r14, rdx
0x180183878  mov     rbx, rcx
0x18018387b  add     rcx, 0FFFFFFFFFFFFFF78h; this
0x180183882  call    ?_ResetForInitialize@CFSFolder@@IEAAJXZ; CFSFolder::_ResetForInitialize(void)
0x180183887  or      dword ptr [rbx+190h], 10h
0x18018388e  lea     r8, [rbx+164h]; value
0x180183895  lea     rdx, aAttributes; "Attributes"
0x18018389c  mov     rcx, r14; propBag
0x18018389f  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801838a6  nop     dword ptr [rax+rax+00h]
0x1801838ab  lea     r8, [rbx+180h]; value
0x1801838b2  xor     r12d, r12d
0x1801838b5  mov     [r8], r12d
0x1801838b8  lea     rdx, aDescriptionid; "DescriptionID"
0x1801838bf  mov     rcx, r14; propBag
0x1801838c2  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801838c9  nop     dword ptr [rax+rax+00h]
0x1801838ce  lea     r8, [rbx+188h]; value
0x1801838d5  lea     rdx, aHelptopic; "HelpTopic"
0x1801838dc  mov     rcx, r14; propBag
0x1801838df  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1801838e6  nop     dword ptr [rax+rax+00h]
0x1801838eb  mov     [rsp+68h+value], r12d
0x1801838f0  lea     r8, [rsp+68h+value]; value
0x1801838f5  lea     rdx, aAllowchildalia; "AllowChildAliasRegistration"
0x1801838fc  mov     rcx, r14; propBag
0x1801838ff  call    cs:__imp_PSPropertyBag_ReadBOOL
0x180183906  nop     dword ptr [rax+rax+00h]
0x18018390b  cmp     [rsp+68h+value], r12d
0x180183910  setnz   al
0x180183913  mov     [rbx+195h], al
0x180183919  mov     [rsp+68h+var_3C], r12d
0x18018391e  lea     r8, [rsp+68h+var_3C]; value
0x180183923  lea     rdx, aRecursivesearc; "RecursiveSearch"
0x18018392a  mov     rcx, r14; propBag
0x18018392d  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180183934  nop     dword ptr [rax+rax+00h]
0x180183939  mov     eax, [rsp+68h+var_3C]
0x18018393d  neg     eax
0x18018393f  sbb     ecx, ecx
0x180183941  and     ecx, 200h
0x180183947  and     dword ptr [rbx+190h], 0FFFFFDFFh
0x180183951  or      [rbx+190h], ecx
0x180183957  lea     r8, [rbx+168h]; value
0x18018395e  lea     rdx, aTargetknownfol; "TargetKnownFolder"
0x180183965  mov     rcx, r14; propBag
0x180183968  call    cs:__imp_PSPropertyBag_ReadGUID
0x18018396f  nop     dword ptr [rax+rax+00h]
0x180183974  mov     esi, eax
0x180183976  test    eax, eax
0x180183978  js      loc_180183A4B
0x18018397e  and     dword ptr [rbx+190h], 0FFFFFEFFh
0x180183988  mov     eax, esi
0x18018398a  not     eax
0x18018398c  shr     eax, 1Fh
0x18018398f  shl     eax, 8
0x180183992  or      [rbx+190h], eax
0x180183998  test    esi, esi
0x18018399a  js      loc_180183A22
0x1801839a0  mov     qword ptr [rsp+68h+var_48], r12
0x1801839a5  mov     rax, [r14]
0x1801839a8  mov     rdi, [rax]
0x1801839ab  lea     rcx, [rsp+68h+var_48]
0x1801839b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801839b5  lea     r8, [rsp+68h+var_48]
0x1801839ba  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x1801839c1  mov     rcx, r14
0x1801839c4  mov     rax, rdi
0x1801839c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801839cc  test    eax, eax
0x1801839ce  js      short loc_180183A06
0x1801839d0  mov     r14, qword ptr [rsp+68h+var_48]
0x1801839d5  mov     rax, [r14]
0x1801839d8  mov     r15, [rax+20h]
0x1801839dc  lea     rdi, [rbx+320h]
0x1801839e3  mov     rbp, [rdi]
0x1801839e6  test    rbp, rbp
0x1801839e9  jnz     loc_180183ADA
0x1801839ef  mov     [rdi], r12
0x1801839f2  mov     r8, rdi
0x1801839f5  mov     edx, 10h
0x1801839fa  mov     rcx, r14
0x1801839fd  mov     rax, r15
0x180183a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183a05  nop
0x180183a06  mov     rcx, qword ptr [rsp+68h+var_48]
0x180183a0b  test    rcx, rcx
0x180183a0e  jz      short loc_180183A22
0x180183a10  mov     qword ptr [rsp+68h+var_48], r12
0x180183a15  mov     rax, [rcx]
0x180183a18  mov     rax, [rax+10h]
0x180183a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183a21  nop
0x180183a22  mov     eax, esi
0x180183a24  mov     rcx, [rsp+68h+var_38]
0x180183a29  xor     rcx, rsp; StackCookie
0x180183a2c  call    __security_check_cookie
0x180183a31  lea     r11, [rsp+68h+var_28]
0x180183a36  mov     rbx, [r11+40h]
0x180183a3a  mov     rbp, [r11+48h]
0x180183a3e  mov     rsp, r11
0x180183a41  pop     r15
0x180183a43  pop     r14
0x180183a45  pop     r12
0x180183a47  pop     rdi
0x180183a48  pop     rsi
0x180183a49  retn
0x180183a4b  mov     [rsp+68h+var_48], r12d
0x180183a50  lea     r8, [rsp+68h+var_48]; value
0x180183a55  lea     rdx, aTargetspecialf; "TargetSpecialFolder"
0x180183a5c  mov     rcx, r14; propBag
0x180183a5f  call    cs:__imp_PSPropertyBag_ReadInt
0x180183a66  nop     dword ptr [rax+rax+00h]
0x180183a6b  test    eax, eax
0x180183a6d  jns     loc_180183B0B
0x180183a73  mov     qword ptr [rsp+68h+var_48], r12
0x180183a78  lea     r8, [rsp+68h+var_48]; value
0x180183a7d  lea     rdx, aTargetfolderpa; "TargetFolderPath"
0x180183a84  mov     rcx, r14; propBag
0x180183a87  call    cs:__imp_PSPropertyBag_ReadBSTR
0x180183a8e  nop     dword ptr [rax+rax+00h]
0x180183a93  mov     esi, eax
0x180183a95  test    eax, eax
0x180183a97  js      loc_18018397E
0x180183a9d  mov     rcx, [rbx+138h]; bstrString
0x180183aa4  call    cs:__imp_SysFreeString
0x180183aab  nop     dword ptr [rax+rax+00h]
0x180183ab0  mov     rcx, qword ptr [rsp+68h+var_48]
0x180183ab5  mov     [rbx+138h], rcx
0x180183abc  mov     edx, [rbx+164h]
0x180183ac2  cmp     edx, 0FFFFFFFFh
0x180183ac5  jz      short loc_180183B2A
0x180183ac7  lea     r9, [rbx+130h]
0x180183ace  call    ?SHSimpleIDListFromAttributesAndFlags@@YAJPEBGKW4SIMPLE_IDLIST_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; SHSimpleIDListFromAttributesAndFlags(ushort const *,ulong,SIMPLE_IDLIST_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x180183ad3  mov     esi, eax
0x180183ad5  jmp     loc_18018397E
0x180183ada  call    cs:__imp_GetLastError
0x180183ae1  nop     dword ptr [rax+rax+00h]
0x180183ae6  nop
0x180183ae7  mov     ebx, eax
0x180183ae9  mov     rcx, rbp; hKey
0x180183aec  call    cs:__imp_RegCloseKey
0x180183af3  nop     dword ptr [rax+rax+00h]
0x180183af8  mov     ecx, ebx; dwErrCode
0x180183afa  call    cs:__imp_SetLastError
0x180183b01  nop     dword ptr [rax+rax+00h]
0x180183b06  jmp     loc_1801839EF
0x180183b0b  lea     rdx, [rbx+168h]
0x180183b12  mov     ecx, [rsp+68h+var_48]
0x180183b16  call    SHKnownFolderFromCSIDL
0x180183b1b  mov     esi, eax
0x180183b1d  test    eax, eax
0x180183b1f  jns     loc_18018397E
0x180183b25  jmp     loc_180183A73
0x180183b2a  mov     dword ptr [rbx+164h], 10h
0x180183b34  mov     edx, 10h
0x180183b39  jmp     short loc_180183AC7
```
