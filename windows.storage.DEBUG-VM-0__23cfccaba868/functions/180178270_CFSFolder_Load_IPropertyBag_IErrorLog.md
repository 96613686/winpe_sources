# CFSFolder::Load(IPropertyBag *,IErrorLog *)

- ea: `0x180178270`
- end: `0x18017850e`
- name: `?Load@CFSFolder@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `670`
- prototype: `int(CFSFolder *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x180055254`
- `0x180178270`
- `0x1801789a0`
- `0x180178cf0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801784d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801784d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801784bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801784bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801784cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801784cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18017848f`
- `OLEAUT32!__imp_SysFreeString` at `0x18017848f`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18017830d`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18017830d`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801782bf`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801782dc`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180178335`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801782bf`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1801782dc`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180178335`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18017836a`
- `PROPSYS!PSPropertyBag_ReadGUID` at `0x18017836a`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017845a`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017845a`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1801782f3`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180178478`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x1801782f3`
- `PROPSYS!PSPropertyBag_ReadBSTR` at `0x180178478`

## string_xrefs

- `0x18017846e`: `TargetFolderPath`

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
0x180178270  mov     [rsp+arg_10], rbx
0x180178275  mov     [rsp+arg_18], rbp
0x18017827a  push    rsi
0x18017827b  push    rdi
0x18017827c  push    r12
0x18017827e  push    r14
0x180178280  push    r15
0x180178282  sub     rsp, 40h
0x180178286  mov     rax, cs:__security_cookie
0x18017828d  xor     rax, rsp
0x180178290  mov     [rsp+68h+var_38], rax
0x180178295  mov     r14, rdx
0x180178298  mov     rbx, rcx
0x18017829b  add     rcx, 0FFFFFFFFFFFFFF78h; this
0x1801782a2  call    ?_ResetForInitialize@CFSFolder@@IEAAJXZ; CFSFolder::_ResetForInitialize(void)
0x1801782a7  or      dword ptr [rbx+190h], 10h
0x1801782ae  lea     r8, [rbx+164h]; value
0x1801782b5  lea     rdx, aAttributes; "Attributes"
0x1801782bc  mov     rcx, r14; propBag
0x1801782bf  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801782c5  lea     r8, [rbx+180h]; value
0x1801782cc  xor     r12d, r12d
0x1801782cf  mov     [r8], r12d
0x1801782d2  lea     rdx, aDescriptionid; "DescriptionID"
0x1801782d9  mov     rcx, r14; propBag
0x1801782dc  call    cs:__imp_PSPropertyBag_ReadDWORD
0x1801782e2  lea     r8, [rbx+188h]; value
0x1801782e9  lea     rdx, aHelptopic; "HelpTopic"
0x1801782f0  mov     rcx, r14; propBag
0x1801782f3  call    cs:__imp_PSPropertyBag_ReadBSTR
0x1801782f9  mov     [rsp+68h+value], r12d
0x1801782fe  lea     r8, [rsp+68h+value]; value
0x180178303  lea     rdx, aAllowchildalia; "AllowChildAliasRegistration"
0x18017830a  mov     rcx, r14; propBag
0x18017830d  call    cs:__imp_PSPropertyBag_ReadBOOL
0x180178313  cmp     [rsp+68h+value], r12d
0x180178318  setnz   al
0x18017831b  mov     [rbx+195h], al
0x180178321  mov     [rsp+68h+var_3C], r12d
0x180178326  lea     r8, [rsp+68h+var_3C]; value
0x18017832b  lea     rdx, aRecursivesearc; "RecursiveSearch"
0x180178332  mov     rcx, r14; propBag
0x180178335  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18017833b  mov     eax, [rsp+68h+var_3C]
0x18017833f  neg     eax
0x180178341  sbb     ecx, ecx
0x180178343  and     ecx, 200h
0x180178349  and     dword ptr [rbx+190h], 0FFFFFDFFh
0x180178353  or      [rbx+190h], ecx
0x180178359  lea     r8, [rbx+168h]; value
0x180178360  lea     rdx, aTargetknownfol; "TargetKnownFolder"
0x180178367  mov     rcx, r14; propBag
0x18017836a  call    cs:__imp_PSPropertyBag_ReadGUID
0x180178370  mov     esi, eax
0x180178372  test    eax, eax
0x180178374  js      loc_180178446
0x18017837a  and     dword ptr [rbx+190h], 0FFFFFEFFh
0x180178384  mov     eax, esi
0x180178386  not     eax
0x180178388  shr     eax, 1Fh
0x18017838b  shl     eax, 8
0x18017838e  or      [rbx+190h], eax
0x180178394  test    esi, esi
0x180178396  js      loc_18017841E
0x18017839c  mov     qword ptr [rsp+68h+var_48], r12
0x1801783a1  mov     rax, [r14]
0x1801783a4  mov     rdi, [rax]
0x1801783a7  lea     rcx, [rsp+68h+var_48]
0x1801783ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801783b1  lea     r8, [rsp+68h+var_48]
0x1801783b6  lea     rdx, _GUID_d960050c_f4e1_4294_ac4b_598913605923
0x1801783bd  mov     rcx, r14
0x1801783c0  mov     rax, rdi
0x1801783c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801783c8  test    eax, eax
0x1801783ca  js      short loc_180178402
0x1801783cc  mov     r14, qword ptr [rsp+68h+var_48]
0x1801783d1  mov     rax, [r14]
0x1801783d4  mov     r15, [rax+20h]
0x1801783d8  lea     rdi, [rbx+320h]
0x1801783df  mov     rbp, [rdi]
0x1801783e2  test    rbp, rbp
0x1801783e5  jnz     loc_1801784BF
0x1801783eb  mov     [rdi], r12
0x1801783ee  mov     r8, rdi
0x1801783f1  mov     edx, 10h
0x1801783f6  mov     rcx, r14
0x1801783f9  mov     rax, r15
0x1801783fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178401  nop
0x180178402  mov     rcx, qword ptr [rsp+68h+var_48]
0x180178407  test    rcx, rcx
0x18017840a  jz      short loc_18017841E
0x18017840c  mov     qword ptr [rsp+68h+var_48], r12
0x180178411  mov     rax, [rcx]
0x180178414  mov     rax, [rax+10h]
0x180178418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017841d  nop
0x18017841e  mov     eax, esi
0x180178420  mov     rcx, [rsp+68h+var_38]
0x180178425  xor     rcx, rsp; StackCookie
0x180178428  call    __security_check_cookie
0x18017842d  lea     r11, [rsp+68h+var_28]
0x180178432  mov     rbx, [r11+40h]
0x180178436  mov     rbp, [r11+48h]
0x18017843a  mov     rsp, r11
0x18017843d  pop     r15
0x18017843f  pop     r14
0x180178441  pop     r12
0x180178443  pop     rdi
0x180178444  pop     rsi
0x180178445  retn
0x180178446  mov     [rsp+68h+var_48], r12d
0x18017844b  lea     r8, [rsp+68h+var_48]; value
0x180178450  lea     rdx, aTargetspecialf; "TargetSpecialFolder"
0x180178457  mov     rcx, r14; propBag
0x18017845a  call    cs:__imp_PSPropertyBag_ReadInt
0x180178460  test    eax, eax
0x180178462  jns     short loc_1801784DE
0x180178464  mov     qword ptr [rsp+68h+var_48], r12
0x180178469  lea     r8, [rsp+68h+var_48]; value
0x18017846e  lea     rdx, aTargetfolderpa; "TargetFolderPath"
0x180178475  mov     rcx, r14; propBag
0x180178478  call    cs:__imp_PSPropertyBag_ReadBSTR
0x18017847e  mov     esi, eax
0x180178480  test    eax, eax
0x180178482  js      loc_18017837A
0x180178488  mov     rcx, [rbx+138h]; bstrString
0x18017848f  call    cs:__imp_SysFreeString
0x180178495  mov     rcx, qword ptr [rsp+68h+var_48]
0x18017849a  mov     [rbx+138h], rcx
0x1801784a1  mov     edx, [rbx+164h]
0x1801784a7  cmp     edx, 0FFFFFFFFh
0x1801784aa  jz      short loc_1801784FD
0x1801784ac  lea     r9, [rbx+130h]
0x1801784b3  call    ?SHSimpleIDListFromAttributesAndFlags@@YAJPEBGKW4SIMPLE_IDLIST_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; SHSimpleIDListFromAttributesAndFlags(ushort const *,ulong,SIMPLE_IDLIST_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x1801784b8  mov     esi, eax
0x1801784ba  jmp     loc_18017837A
0x1801784bf  call    cs:__imp_GetLastError
0x1801784c5  nop
0x1801784c6  mov     ebx, eax
0x1801784c8  mov     rcx, rbp; hKey
0x1801784cb  call    cs:__imp_RegCloseKey
0x1801784d1  mov     ecx, ebx; dwErrCode
0x1801784d3  call    cs:__imp_SetLastError
0x1801784d9  jmp     loc_1801783EB
0x1801784de  lea     rdx, [rbx+168h]
0x1801784e5  mov     ecx, [rsp+68h+var_48]
0x1801784e9  call    SHKnownFolderFromCSIDL
0x1801784ee  mov     esi, eax
0x1801784f0  test    eax, eax
0x1801784f2  jns     loc_18017837A
0x1801784f8  jmp     loc_180178464
0x1801784fd  mov     dword ptr [rbx+164h], 10h
0x180178507  mov     edx, 10h
0x18017850c  jmp     short loc_1801784AC
```
