# JsonHelper::SetValue(ushort const *,double)

- ea: `0x1800140f0`
- end: `0x18001421f`
- name: `?SetValue@JsonHelper@@UEAAJPEBGN@Z`
- size: `303`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, double)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x180013880`
- `0x1800140f0`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x1800141d4`: `m_spJsonObj->SetNamedValue`
- `0x18001416b`: `m_spJsonValueStatics->CreateNumberValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::SetValue(JsonHelper *this, const unsigned __int16 *a2, double a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  int ActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64); // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v15; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v16; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-48h] BYREF

  v15 = 0;
  v4 = *((_QWORD *)this + 9);
  v16 = a2;
  v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v4 + 72LL))(v4, a2, &v15);
  if ( v5 >= 0 )
  {
    v9 = *((_QWORD *)this + 7);
    v10 = v15;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v9 + 56LL);
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v17, &v16);
    v5 = v11(v9, *(_QWORD *)(v12 + 24), v10);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v13, &WPP_GLOBAL_Control);
      v7 = 45;
      v8 = "m_spJsonObj->SetNamedValue";
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    v7 = 44;
    v8 = "m_spJsonValueStatics->CreateNumberValue";
LABEL_11:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v8,
      v5);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800140f0  push    rbx
0x1800140f2  push    rsi
0x1800140f3  push    rdi
0x1800140f4  sub     rsp, 70h
0x1800140f8  mov     rax, cs:__security_cookie
0x1800140ff  xor     rax, rsp
0x180014102  mov     [rsp+88h+var_28], rax
0x180014107  mov     rsi, rcx
0x18001410a  mov     [rsp+88h+var_58], 0
0x180014113  mov     rcx, [rcx+48h]
0x180014117  lea     r8, [rsp+88h+var_58]
0x18001411c  movaps  xmm1, xmm2
0x18001411f  mov     [rsp+88h+var_50], rdx
0x180014124  mov     rax, [rcx]
0x180014127  mov     rax, [rax+48h]
0x18001412b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014130  mov     ebx, eax
0x180014132  test    eax, eax
0x180014134  jns     short loc_180014174
0x180014136  mov     rcx, cs:WPP_GLOBAL_Control
0x18001413d  lea     rdx, WPP_GLOBAL_Control
0x180014144  cmp     rcx, rdx
0x180014147  jz      loc_1800141FE
0x18001414d  test    byte ptr [rcx+1Ch], 8
0x180014151  jz      loc_1800141FE
0x180014157  cmp     byte ptr [rcx+19h], 2
0x18001415b  jb      loc_1800141FE
0x180014161  call    RdpX_GetActivityIdPrefix
0x180014166  mov     edx, 2Ch ; ','
0x18001416b  lea     rcx, aMSpjsonvaluest; "m_spJsonValueStatics->CreateNumberValue"
0x180014172  jmp     short loc_1800141DB
0x180014174  mov     rsi, [rsi+38h]
0x180014178  lea     rdx, [rsp+88h+var_50]
0x18001417d  mov     rbx, [rsp+88h+var_58]
0x180014182  lea     rcx, [rsp+88h+var_48]
0x180014187  mov     rax, [rsi]
0x18001418a  mov     rdi, [rax+38h]
0x18001418e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014193  mov     r8, rbx
0x180014196  mov     rcx, rsi
0x180014199  mov     rdx, [rax+18h]
0x18001419d  mov     rax, rdi
0x1800141a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a5  mov     ebx, eax
0x1800141a7  test    eax, eax
0x1800141a9  jns     short loc_1800141FE
0x1800141ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800141b2  lea     rdx, WPP_GLOBAL_Control
0x1800141b9  cmp     rax, rdx
0x1800141bc  jz      short loc_1800141FE
0x1800141be  test    byte ptr [rax+1Ch], 8
0x1800141c2  jz      short loc_1800141FE
0x1800141c4  cmp     byte ptr [rax+19h], 2
0x1800141c8  jb      short loc_1800141FE
0x1800141ca  call    RdpX_GetActivityIdPrefix
0x1800141cf  mov     edx, 2Dh ; '-'
0x1800141d4  lea     rcx, aMSpjsonobjSetn; "m_spJsonObj->SetNamedValue"
0x1800141db  mov     [rsp+88h+var_60], ebx
0x1800141df  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800141e6  mov     [rsp+88h+var_68], rcx
0x1800141eb  mov     r9d, eax
0x1800141ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141f5  mov     rcx, [rcx+10h]
0x1800141f9  call    WPP_SF_DsD
0x1800141fe  lea     rcx, [rsp+88h+var_58]
0x180014203  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x180014208  mov     eax, ebx
0x18001420a  mov     rcx, [rsp+88h+var_28]
0x18001420f  xor     rcx, rsp; StackCookie
0x180014212  call    __security_check_cookie
0x180014217  add     rsp, 70h
0x18001421b  pop     rdi
0x18001421c  pop     rsi
0x18001421d  pop     rbx
0x18001421e  retn
```
