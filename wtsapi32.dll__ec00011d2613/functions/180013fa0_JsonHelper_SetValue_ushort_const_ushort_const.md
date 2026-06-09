# JsonHelper::SetValue(ushort const *,ushort const *)

- ea: `0x180013fa0`
- end: `0x1800140e7`
- name: `?SetValue@JsonHelper@@UEAAJPEBG0@Z`
- size: `327`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x180013880`
- `0x180013fa0`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x18001409c`: `spJsonObj->SetNamedValue`
- `0x180014033`: `spJsonValueStatics->CreateStringValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetValue(JsonHelper *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rbx
  __int64 v6; // rax
  int v7; // ebx
  int ActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64); // rdi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v18; // [rsp+38h] [rbp-50h] BYREF
  const unsigned __int16 *v19; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v20[32]; // [rsp+48h] [rbp-40h] BYREF

  v19 = a2;
  v18 = a3;
  v4 = *((_QWORD *)this + 9);
  v17 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 80LL);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v18);
  v7 = v5(v4, *(_QWORD *)(v6 + 24), &v17);
  if ( v7 >= 0 )
  {
    v11 = *((_QWORD *)this + 7);
    v12 = v17;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v11 + 56LL);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v19);
    v7 = v13(v11, *(_QWORD *)(v14 + 24), v12);
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v15, &WPP_GLOBAL_Control);
      v9 = 41;
      v10 = "spJsonObj->SetNamedValue";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    v9 = 40;
    v10 = "spJsonValueStatics->CreateStringValue";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v10,
      v7);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013fa0  mov     r11, rsp
0x180013fa3  push    rbx
0x180013fa4  push    rsi
0x180013fa5  push    rdi
0x180013fa6  sub     rsp, 70h
0x180013faa  mov     rax, cs:__security_cookie
0x180013fb1  xor     rax, rsp
0x180013fb4  mov     [rsp+88h+var_20], rax
0x180013fb9  mov     [r11-48h], rdx
0x180013fbd  mov     rsi, rcx
0x180013fc0  mov     [r11-50h], r8
0x180013fc4  lea     rdx, [r11-50h]
0x180013fc8  mov     rdi, [rcx+48h]
0x180013fcc  lea     rcx, [r11-40h]
0x180013fd0  mov     qword ptr [r11-58h], 0
0x180013fd8  mov     rax, [rdi]
0x180013fdb  mov     rbx, [rax+50h]
0x180013fdf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013fe4  lea     r8, [rsp+88h+var_58]
0x180013fe9  mov     rcx, rdi
0x180013fec  mov     rdx, [rax+18h]
0x180013ff0  mov     rax, rbx
0x180013ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ff8  mov     ebx, eax
0x180013ffa  test    eax, eax
0x180013ffc  jns     short loc_18001403C
0x180013ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014005  lea     rdx, WPP_GLOBAL_Control
0x18001400c  cmp     rcx, rdx
0x18001400f  jz      loc_1800140C6
0x180014015  test    byte ptr [rcx+1Ch], 8
0x180014019  jz      loc_1800140C6
0x18001401f  cmp     byte ptr [rcx+19h], 2
0x180014023  jb      loc_1800140C6
0x180014029  call    RdpX_GetActivityIdPrefix
0x18001402e  mov     edx, 28h ; '('
0x180014033  lea     rcx, aSpjsonvaluesta; "spJsonValueStatics->CreateStringValue"
0x18001403a  jmp     short loc_1800140A3
0x18001403c  mov     rsi, [rsi+38h]
0x180014040  lea     rdx, [rsp+88h+var_48]
0x180014045  mov     rbx, [rsp+88h+var_58]
0x18001404a  lea     rcx, [rsp+88h+var_40]
0x18001404f  mov     rax, [rsi]
0x180014052  mov     rdi, [rax+38h]
0x180014056  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001405b  mov     r8, rbx
0x18001405e  mov     rcx, rsi
0x180014061  mov     rdx, [rax+18h]
0x180014065  mov     rax, rdi
0x180014068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001406d  mov     ebx, eax
0x18001406f  test    eax, eax
0x180014071  jns     short loc_1800140C6
0x180014073  mov     rax, cs:WPP_GLOBAL_Control
0x18001407a  lea     rdx, WPP_GLOBAL_Control
0x180014081  cmp     rax, rdx
0x180014084  jz      short loc_1800140C6
0x180014086  test    byte ptr [rax+1Ch], 8
0x18001408a  jz      short loc_1800140C6
0x18001408c  cmp     byte ptr [rax+19h], 2
0x180014090  jb      short loc_1800140C6
0x180014092  call    RdpX_GetActivityIdPrefix
0x180014097  mov     edx, 29h ; ')'
0x18001409c  lea     rcx, aSpjsonobjSetna; "spJsonObj->SetNamedValue"
0x1800140a3  mov     [rsp+88h+var_60], ebx
0x1800140a7  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800140ae  mov     [rsp+88h+var_68], rcx
0x1800140b3  mov     r9d, eax
0x1800140b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140bd  mov     rcx, [rcx+10h]
0x1800140c1  call    WPP_SF_DsD
0x1800140c6  lea     rcx, [rsp+88h+var_58]
0x1800140cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800140d0  mov     eax, ebx
0x1800140d2  mov     rcx, [rsp+88h+var_20]
0x1800140d7  xor     rcx, rsp; StackCookie
0x1800140da  call    __security_check_cookie
0x1800140df  add     rsp, 70h
0x1800140e3  pop     rdi
0x1800140e4  pop     rsi
0x1800140e5  pop     rbx
0x1800140e6  retn
```
