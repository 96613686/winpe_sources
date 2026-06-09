# JsonHelper::SetValue(ushort const *,IJsonHelper *)

- ea: `0x180014230`
- end: `0x180014387`
- name: `?SetValue@JsonHelper@@UEAAJPEBGPEAVIJsonHelper@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, struct IJsonHelper *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x180012330`
- `0x180013880`
- `0x180014230`
- `0x180014bb0`
- `0x180015488`
- `0x180015565`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x1800142d3`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x18001433c`: `m_spJsonObj->SetNamedValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetValue(JsonHelper *this, const unsigned __int16 *a2, struct IJsonHelper *a3)
{
  __int64 v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  int ActivityIdPrefix; // eax
  int v8; // edx
  const char *v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64); // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v16; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-48h] BYREF

  v17 = a2;
  v4 = _RTDynamicCast_0(a3, 0, &IJsonHelper `RTTI Type Descriptor', &JsonHelper `RTTI Type Descriptor', 0);
  v16 = 0;
  if ( !v4 )
  {
    v5 = -2147024809;
    goto LABEL_14;
  }
  v5 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(v4 + 56, &v16);
  if ( v5 >= 0 )
  {
    v10 = *((_QWORD *)this + 7);
    v11 = v16;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 56LL);
    v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, &v17);
    v5 = v12(v10, *(_QWORD *)(v13 + 24), v11);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v14);
      v8 = 47;
      v9 = "m_spJsonObj->SetNamedValue";
      goto LABEL_13;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v6);
    v8 = 46;
    v9 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_13:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v9,
      v5);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014230  push    rbx
0x180014232  push    rsi
0x180014233  push    rdi
0x180014234  sub     rsp, 70h
0x180014238  mov     rax, cs:__security_cookie
0x18001423f  xor     rax, rsp
0x180014242  mov     [rsp+88h+var_28], rax
0x180014247  mov     rax, r8
0x18001424a  mov     [rsp+88h+var_50], rdx
0x18001424f  mov     rsi, rcx
0x180014252  mov     dword ptr [rsp+88h+var_68], 0
0x18001425a  mov     rcx, rax
0x18001425d  lea     r9, ??_R0?AVJsonHelper@@@8; JsonHelper `RTTI Type Descriptor'
0x180014264  lea     r8, ??_R0?AVIJsonHelper@@@8; IJsonHelper `RTTI Type Descriptor'
0x18001426b  xor     edx, edx
0x18001426d  call    __RTDynamicCast_0
0x180014272  mov     [rsp+88h+var_58], 0
0x18001427b  test    rax, rax
0x18001427e  jnz     short loc_18001428A
0x180014280  mov     ebx, 80070057h
0x180014285  jmp     loc_180014366
0x18001428a  lea     rcx, [rax+38h]
0x18001428e  lea     rdx, [rsp+88h+var_58]
0x180014293  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x180014298  mov     ebx, eax
0x18001429a  test    eax, eax
0x18001429c  jns     short loc_1800142DC
0x18001429e  mov     rax, cs:WPP_GLOBAL_Control
0x1800142a5  lea     rcx, WPP_GLOBAL_Control
0x1800142ac  cmp     rax, rcx
0x1800142af  jz      loc_180014366
0x1800142b5  test    byte ptr [rax+1Ch], 8
0x1800142b9  jz      loc_180014366
0x1800142bf  cmp     byte ptr [rax+19h], 2
0x1800142c3  jb      loc_180014366
0x1800142c9  call    RdpX_GetActivityIdPrefix
0x1800142ce  mov     edx, 2Eh ; '.'
0x1800142d3  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x1800142da  jmp     short loc_180014343
0x1800142dc  mov     rsi, [rsi+38h]
0x1800142e0  lea     rdx, [rsp+88h+var_50]
0x1800142e5  mov     rbx, [rsp+88h+var_58]
0x1800142ea  lea     rcx, [rsp+88h+var_48]
0x1800142ef  mov     rax, [rsi]
0x1800142f2  mov     rdi, [rax+38h]
0x1800142f6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800142fb  mov     r8, rbx
0x1800142fe  mov     rcx, rsi
0x180014301  mov     rdx, [rax+18h]
0x180014305  mov     rax, rdi
0x180014308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001430d  mov     ebx, eax
0x18001430f  test    eax, eax
0x180014311  jns     short loc_180014366
0x180014313  mov     rax, cs:WPP_GLOBAL_Control
0x18001431a  lea     rcx, WPP_GLOBAL_Control
0x180014321  cmp     rax, rcx
0x180014324  jz      short loc_180014366
0x180014326  test    byte ptr [rax+1Ch], 8
0x18001432a  jz      short loc_180014366
0x18001432c  cmp     byte ptr [rax+19h], 2
0x180014330  jb      short loc_180014366
0x180014332  call    RdpX_GetActivityIdPrefix
0x180014337  mov     edx, 2Fh ; '/'
0x18001433c  lea     rcx, aMSpjsonobjSetn; "m_spJsonObj->SetNamedValue"
0x180014343  mov     [rsp+88h+var_60], ebx
0x180014347  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18001434e  mov     [rsp+88h+var_68], rcx
0x180014353  mov     r9d, eax
0x180014356  mov     rcx, cs:WPP_GLOBAL_Control
0x18001435d  mov     rcx, [rcx+10h]
0x180014361  call    WPP_SF_DsD
0x180014366  lea     rcx, [rsp+88h+var_58]
0x18001436b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180014370  mov     eax, ebx
0x180014372  mov     rcx, [rsp+88h+var_28]
0x180014377  xor     rcx, rsp; StackCookie
0x18001437a  call    __security_check_cookie
0x18001437f  add     rsp, 70h
0x180014383  pop     rdi
0x180014384  pop     rsi
0x180014385  pop     rbx
0x180014386  retn
```
