# I_SetReferenceData(VCHANNEL_DATA *,_CARD_ROLE,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x18000a81c`
- end: `0x18000acab`
- name: `?I_SetReferenceData@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `1167`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a1b8`
- `0x18000b85c`
- `0x180016954`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x18000653c`
- `0x180006708`
- `0x1800068dc`
- `0x18000720c`
- `0x180007628`
- `0x180007988`
- `0x180007a10`
- `0x18000a81c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c010`
- `0x18000c124`
- `0x18000c198`
- `0x1800123c4`
- `0x180012580`
- `0x18001280c`
- `0x1800128c4`
- `0x180013814`
- `0x18001f784`
- `0x1800201f0`
- `0x180028250`
- `0x18002bb98`
- `0x1800348a0`

## string_xrefs

- `0x18000ab71`: `Unable to update user record`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_SetReferenceData(__int64 *a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // r9d
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int KspKey; // eax
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  const char *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int Guid; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26[2]; // [rsp+60h] [rbp-A0h] BYREF
  int *v27; // [rsp+68h] [rbp-98h] BYREF
  __int16 v28; // [rsp+70h] [rbp-90h]
  _QWORD v29[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v30; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v31[3]; // [rsp+98h] [rbp-68h] BYREF
  __int16 v32; // [rsp+B0h] [rbp-50h]
  _QWORD v33[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v34[4]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszKeyName[40]; // [rsp+F0h] [rbp-10h] BYREF
  int v36; // [rsp+140h] [rbp+40h]
  int v37; // [rsp+144h] [rbp+44h]
  int InitialRetryCount; // [rsp+148h] [rbp+48h]
  unsigned __int16 v39[48]; // [rsp+150h] [rbp+50h] BYREF
  char v40[24]; // [rsp+1B0h] [rbp+B0h] BYREF

  v24 = a1;
  v23 = a2;
  Guid = 0;
  v25 = 0;
  strcpy(v40, "I_SetReferenceData");
  v33[0] = v40;
  v33[1] = &v25;
  v33[2] = &Guid;
  lambda_83d1b05148d8ce538ce5599ab87dbed6_::operator()(v33);
  v25 = 1;
  v30 = v33;
  if ( !v24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( v23 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( v24[16] == v24[17] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v24, v4);
  if ( v24[16] == v24[17] )
  {
    WppTraceIndent(v24, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          v6,
          39);
    }
    __fastfail(0x80100027);
  }
  memset_0(v39, 0, 0x5Cu);
  I_PinMapGetRecord(*v24, v23, v39);
  memset_0(pszKeyName, 0, 0x5Cu);
  v36 = 1;
  v37 = *(_DWORD *)(a3 + 8) - *(_DWORD *)a3;
  InitialRetryCount = I_PinMapGetInitialRetryCount(v23);
  memset_0(pszKeyName, 0, sizeof(pszKeyName));
  *(_QWORD *)v26 = 0;
  v8 = 0;
  KspKey = Guid;
  while ( v8 < 0xA )
  {
    Guid = I_GenerateGuid(pszKeyName);
    if ( Guid )
    {
      WppTraceIndent(v10, 2);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 91;
        v13 = "Generating GUID failed";
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      v26,
      0);
    KspKey = I_CreateKspKey(*v24, 0x47u, 4, (NCRYPT_KEY_HANDLE *)v26, pszKeyName, (_QWORD *)a3, 0);
    Guid = KspKey;
    if ( KspKey != -2146893809 )
      break;
    ++v8;
  }
  if ( KspKey )
  {
    WppTraceIndent(v7, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 92;
      v13 = "Unable to generate new smart card key";
LABEL_27:
      WPP_SF_sDs(
        v11[2],
        v12,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Guid,
        (__int64)v13);
    }
LABEL_28:
    v14 = Guid;
    goto LABEL_51;
  }
  v27 = v26;
  v28 = 258;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v29);
  Guid = I_UnprotectMemory(v24 + 16, v29);
  if ( Guid )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_35;
    }
    v17 = 93;
    v18 = "Unable to recover auth key";
    goto LABEL_34;
  }
  Guid = I_PinMapSetRecord(*v24, v23, pszKeyName);
  if ( !Guid )
  {
    v31[0] = &v24;
    v31[1] = &v23;
    v31[2] = v39;
    v32 = 256;
    v34[0] = &v24;
    v34[1] = &v23;
    v34[2] = v26;
    v34[3] = v29;
    Guid = lambda_d37e129344ab85845669e1723f984cec_::operator()(v34);
    if ( Guid )
    {
      WppTraceIndent(v20, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          Guid,
          (__int64)"Updating PIN map file failed");
      }
    }
    else
    {
      HIBYTE(v28) = 0;
      HIBYTE(v32) = 0;
      if ( I_PinMapIsActive((const struct PIN_MAP_RECORD *)v39)
        && !I_PinMapIsBlocked((const struct PIN_MAP_RECORD *)v39) )
      {
        I_DeleteKspKey((const struct VCARD_DATA *)*v24, v39);
      }
    }
    v14 = Guid;
    wil::details::ScopeExitFnGuard__lambda_9255b61ebf9cdc00d424ac667efbfeba___::operator()(v31);
    goto LABEL_50;
  }
  WppTraceIndent(v19, 2);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = 94;
    v18 = "Unable to update user record";
LABEL_34:
    WPP_SF_sDs(
      v16[2],
      v17,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      Guid,
      (__int64)v18);
  }
LABEL_35:
  v14 = Guid;
LABEL_50:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v29);
  wil::details::ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f___::operator()(&v27);
LABEL_51:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>((NCRYPT_HANDLE *)v26);
  WppTraceUnwinder__lambda_83d1b05148d8ce538ce5599ab87dbed6____::_WppTraceUnwinder__lambda_83d1b05148d8ce538ce5599ab87dbed6____(&v30);
  return v14;
}

```

## disassembly

```asm
0x18000a81c  push    rbp
0x18000a81e  push    rbx
0x18000a81f  push    rsi
0x18000a820  push    rdi
0x18000a821  push    r12
0x18000a823  push    r13
0x18000a825  push    r15
0x18000a827  lea     rbp, [rsp-0D0h]
0x18000a82f  sub     rsp, 1D0h
0x18000a836  mov     rax, cs:__security_cookie
0x18000a83d  xor     rax, rsp
0x18000a840  mov     [rbp+100h+var_38], rax
0x18000a847  mov     rdi, r8
0x18000a84a  mov     [rsp+200h+var_1B0], rcx
0x18000a84f  mov     [rsp+200h+var_1B8], edx
0x18000a853  mov     [rsp+200h+var_1C0], 0
0x18000a85b  mov     [rsp+200h+var_1A8], 0
0x18000a863  movups  xmm0, xmmword ptr cs:aISetreferenced; "I_SetReferenceData"
0x18000a86a  movups  xmmword ptr [rbp+100h+var_50], xmm0
0x18000a871  mov     eax, dword ptr cs:aISetreferenced+0Fh; "ata"
0x18000a877  mov     dword ptr [rbp+100h+var_50+0Fh], eax
0x18000a87d  lea     rax, [rbp+100h+var_50]
0x18000a884  mov     [rbp+100h+var_148], rax
0x18000a888  lea     rax, [rsp+200h+var_1A8]
0x18000a88d  mov     [rbp+100h+var_140], rax
0x18000a891  lea     rax, [rsp+200h+var_1C0]
0x18000a896  mov     [rbp+100h+var_138], rax
0x18000a89a  lea     rcx, [rbp+100h+var_148]
0x18000a89e  call    _lambda_83d1b05148d8ce538ce5599ab87dbed6___operator__
0x18000a8a3  mov     r15d, 1
0x18000a8a9  mov     [rsp+200h+var_1A8], r15d
0x18000a8ae  lea     rax, [rbp+100h+var_148]
0x18000a8b2  mov     [rbp+100h+var_170], rax
0x18000a8b6  cmp     [rsp+200h+var_1B0], 0
0x18000a8bc  jnz     short loc_18000A8C3
0x18000a8be  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a8c3  mov     eax, [rsp+200h+var_1B8]
0x18000a8c7  dec     eax
0x18000a8c9  cmp     eax, r15d
0x18000a8cc  jbe     short loc_18000A8D3
0x18000a8ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a8d3  mov     rcx, [rsp+200h+var_1B0]
0x18000a8d8  mov     rax, [rcx+88h]
0x18000a8df  cmp     [rcx+80h], rax
0x18000a8e6  jnz     short loc_18000A8ED
0x18000a8e8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a8ed  mov     rcx, [rsp+200h+var_1B0]
0x18000a8f2  mov     rax, [rcx+88h]
0x18000a8f9  mov     esi, 2
0x18000a8fe  lea     r12, WPP_GLOBAL_Control
0x18000a905  lea     r13, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000a90c  cmp     [rcx+80h], rax
0x18000a913  jnz     short loc_18000A951
0x18000a915  mov     edx, esi
0x18000a917  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000a91c  mov     ebx, 80100027h
0x18000a921  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a928  cmp     rcx, r12
0x18000a92b  jz      short loc_18000A94C
0x18000a92d  test    [rcx+1Ch], r15b
0x18000a931  jz      short loc_18000A94C
0x18000a933  cmp     [rcx+19h], r15b
0x18000a937  jb      short loc_18000A94C
0x18000a939  lea     edx, [rsi+58h]
0x18000a93c  mov     dword ptr [rsp+200h+pszKeyName], ebx
0x18000a940  mov     r8, r13
0x18000a943  mov     rcx, [rcx+10h]
0x18000a947  call    WPP_SF_sD
0x18000a94c  mov     rcx, rbx
0x18000a94f  int     29h; Win8: RtlFailFast(ecx)
0x18000a951  mov     ebx, 5Ch ; '\'
0x18000a956  mov     r8d, ebx; Size
0x18000a959  xor     edx, edx; Val
0x18000a95b  lea     rcx, [rbp+100h+var_B0]; void *
0x18000a95f  call    memset_0
0x18000a964  lea     r8, [rbp+100h+var_B0]
0x18000a968  mov     edx, [rsp+200h+var_1B8]
0x18000a96c  mov     rcx, [rsp+200h+var_1B0]
0x18000a971  mov     rcx, [rcx]
0x18000a974  call    ?I_PinMapGetRecord@@YAXPEBUVCARD_DATA@@W4_CARD_ROLE@@PEAUPIN_MAP_RECORD@@@Z; I_PinMapGetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD *)
0x18000a979  mov     r8d, ebx; Size
0x18000a97c  xor     edx, edx; Val
0x18000a97e  lea     rcx, [rbp+100h+var_110]; void *
0x18000a982  call    memset_0
0x18000a987  mov     [rbp+100h+var_C0], r15d
0x18000a98b  mov     eax, [rdi+8]
0x18000a98e  sub     eax, [rdi]
0x18000a990  mov     [rbp+100h+var_BC], eax
0x18000a993  mov     ecx, [rsp+200h+var_1B8]
0x18000a997  call    ?I_PinMapGetInitialRetryCount@@YAJW4_CARD_ROLE@@@Z; I_PinMapGetInitialRetryCount(_CARD_ROLE)
0x18000a99c  mov     [rbp+100h+var_B8], eax
0x18000a99f  xor     edx, edx; Val
0x18000a9a1  lea     r8d, [rbx-0Ch]; Size
0x18000a9a5  lea     rcx, [rbp+100h+var_110]; void *
0x18000a9a9  call    memset_0
0x18000a9ae  mov     qword ptr [rsp+200h+var_1A0], 0
0x18000a9b7  xor     ebx, ebx
0x18000a9b9  mov     eax, [rsp+200h+var_1C0]
0x18000a9bd  cmp     ebx, 0Ah
0x18000a9c0  jnb     loc_18000AA4D
0x18000a9c6  lea     rcx, [rbp+100h+var_110]; unsigned __int16 *
0x18000a9ca  call    ?I_GenerateGuid@@YAKPEAGK@Z; I_GenerateGuid(ushort *,ulong)
0x18000a9cf  mov     [rsp+200h+var_1C0], eax
0x18000a9d3  test    eax, eax
0x18000a9d5  jnz     short loc_18000AA20
0x18000a9d7  xor     edx, edx
0x18000a9d9  lea     rcx, [rsp+200h+var_1A0]
0x18000a9de  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18000a9e3  mov     [rsp+200h+var_1D0], 0; int
0x18000a9eb  mov     [rsp+200h+var_1D8], rdi; __int64
0x18000a9f0  lea     rax, [rbp+100h+var_110]
0x18000a9f4  mov     [rsp+200h+pszKeyName], rax; pszKeyName
0x18000a9f9  lea     r9, [rsp+200h+var_1A0]; int
0x18000a9fe  mov     r8b, 4; int
0x18000aa01  mov     dl, 47h ; 'G'; int
0x18000aa03  mov     rcx, [rsp+200h+var_1B0]
0x18000aa08  mov     rcx, [rcx]; int
0x18000aa0b  call    ?I_CreateKspKey@@YAKPEBUVCARD_DATA@@EEPEA_KPEBGAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@H@Z; I_CreateKspKey(VCARD_DATA const *,uchar,uchar,unsigned __int64 *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &,int)
0x18000aa10  mov     [rsp+200h+var_1C0], eax
0x18000aa14  cmp     eax, 8009000Fh
0x18000aa19  jnz     short loc_18000AA4D
0x18000aa1b  add     ebx, r15d
0x18000aa1e  jmp     short loc_18000A9BD
0x18000aa20  mov     edx, esi
0x18000aa22  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000aa27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa2e  cmp     rcx, r12
0x18000aa31  jz      short loc_18000AA9C
0x18000aa33  test    [rcx+1Ch], r15b
0x18000aa37  jz      short loc_18000AA9C
0x18000aa39  cmp     [rcx+19h], sil
0x18000aa3d  jb      short loc_18000AA9C
0x18000aa3f  mov     edx, 5Bh ; '['
0x18000aa44  lea     rax, aGeneratingGuid; "Generating GUID failed"
0x18000aa4b  jmp     short loc_18000AA7C
0x18000aa4d  test    eax, eax
0x18000aa4f  jz      short loc_18000AAA5
0x18000aa51  mov     edx, esi
0x18000aa53  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000aa58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa5f  cmp     rcx, r12
0x18000aa62  jz      short loc_18000AA9C
0x18000aa64  test    [rcx+1Ch], r15b
0x18000aa68  jz      short loc_18000AA9C
0x18000aa6a  cmp     [rcx+19h], sil
0x18000aa6e  jb      short loc_18000AA9C
0x18000aa70  mov     edx, 5Ch ; '\'
0x18000aa75  lea     rax, aUnableToGenera_3; "Unable to generate new smart card key"
0x18000aa7c  mov     [rsp+200h+var_1D8], rax
0x18000aa81  mov     eax, [rsp+200h+var_1C0]
0x18000aa85  mov     dword ptr [rsp+200h+pszKeyName], eax
0x18000aa89  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000aa90  mov     r8, r13
0x18000aa93  mov     rcx, [rcx+10h]
0x18000aa97  call    WPP_SF_sDs
0x18000aa9c  mov     ebx, [rsp+200h+var_1C0]
0x18000aaa0  jmp     loc_18000AC74
0x18000aaa5  lea     rax, [rsp+200h+var_1A0]
0x18000aaaa  mov     [rsp+200h+var_198], rax
0x18000aaaf  mov     [rsp+200h+var_190], 102h
0x18000aab6  lea     rcx, [rsp+200h+var_188]
0x18000aabb  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000aac0  nop
0x18000aac1  mov     rcx, [rsp+200h+var_1B0]
0x18000aac6  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000aaca  lea     rdx, [rsp+200h+var_188]
0x18000aacf  call    ?I_UnprotectMemory@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_UnprotectMemory(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18000aad4  mov     [rsp+200h+var_1C0], eax
0x18000aad8  test    eax, eax
0x18000aada  jz      short loc_18000AB30
0x18000aadc  mov     edx, esi
0x18000aade  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000aae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaea  cmp     rcx, r12
0x18000aaed  jz      short loc_18000AB27
0x18000aaef  test    [rcx+1Ch], r15b
0x18000aaf3  jz      short loc_18000AB27
0x18000aaf5  cmp     [rcx+19h], sil
0x18000aaf9  jb      short loc_18000AB27
0x18000aafb  mov     edx, 5Dh ; ']'
0x18000ab00  lea     rax, aUnableToRecove; "Unable to recover auth key"
0x18000ab07  mov     [rsp+200h+var_1D8], rax
0x18000ab0c  mov     eax, [rsp+200h+var_1C0]
0x18000ab10  mov     dword ptr [rsp+200h+pszKeyName], eax
0x18000ab14  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000ab1b  mov     r8, r13
0x18000ab1e  mov     rcx, [rcx+10h]
0x18000ab22  call    WPP_SF_sDs
0x18000ab27  mov     ebx, [rsp+200h+var_1C0]
0x18000ab2b  jmp     loc_18000AC5E
0x18000ab30  lea     r8, [rbp+100h+var_110]
0x18000ab34  mov     edx, [rsp+200h+var_1B8]
0x18000ab38  mov     rcx, [rsp+200h+var_1B0]
0x18000ab3d  mov     rcx, [rcx]
0x18000ab40  call    ?I_PinMapSetRecord@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@PEBUPIN_MAP_RECORD@@@Z; I_PinMapSetRecord(VCARD_DATA const *,_CARD_ROLE,PIN_MAP_RECORD const *)
0x18000ab45  mov     [rsp+200h+var_1C0], eax
0x18000ab49  test    eax, eax
0x18000ab4b  jz      short loc_18000AB7A
0x18000ab4d  mov     edx, esi
0x18000ab4f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ab54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab5b  cmp     rcx, r12
0x18000ab5e  jz      short loc_18000AB27
0x18000ab60  test    [rcx+1Ch], r15b
0x18000ab64  jz      short loc_18000AB27
0x18000ab66  cmp     [rcx+19h], sil
0x18000ab6a  jb      short loc_18000AB27
0x18000ab6c  mov     edx, 5Eh ; '^'
0x18000ab71  lea     rax, aUnableToUpdate_1; "Unable to update user record"
0x18000ab78  jmp     short loc_18000AB07
0x18000ab7a  lea     rax, [rsp+200h+var_1B0]
0x18000ab7f  mov     [rbp+100h+var_168], rax
0x18000ab83  lea     rax, [rsp+200h+var_1B8]
0x18000ab88  mov     [rbp+100h+var_160], rax
0x18000ab8c  lea     rax, [rbp+100h+var_B0]
0x18000ab90  mov     [rbp+100h+var_158], rax
0x18000ab94  mov     [rbp+100h+var_150], 100h
0x18000ab9a  lea     rax, [rsp+200h+var_1B0]
0x18000ab9f  mov     [rbp+100h+var_130], rax
0x18000aba3  lea     rax, [rsp+200h+var_1B8]
0x18000aba8  mov     [rbp+100h+var_128], rax
0x18000abac  lea     rax, [rsp+200h+var_1A0]
0x18000abb1  mov     [rbp+100h+var_120], rax
0x18000abb5  lea     rax, [rsp+200h+var_188]
0x18000abba  mov     [rbp+100h+var_118], rax
0x18000abbe  lea     rcx, [rbp+100h+var_130]
0x18000abc2  call    _lambda_d37e129344ab85845669e1723f984cec___operator__
0x18000abc7  mov     [rsp+200h+var_1C0], eax
0x18000abcb  test    eax, eax
0x18000abcd  jz      short loc_18000AC1C
0x18000abcf  mov     edx, esi
0x18000abd1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000abd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abdd  cmp     rcx, r12
0x18000abe0  jz      short loc_18000AC50
0x18000abe2  test    [rcx+1Ch], r15b
0x18000abe6  jz      short loc_18000AC50
0x18000abe8  cmp     [rcx+19h], sil
0x18000abec  jb      short loc_18000AC50
0x18000abee  mov     edx, 62h ; 'b'
0x18000abf3  lea     rax, aUpdatingPinMap_0; "Updating PIN map file failed"
0x18000abfa  mov     [rsp+200h+var_1D8], rax
0x18000abff  mov     eax, [rsp+200h+var_1C0]
0x18000ac03  mov     dword ptr [rsp+200h+pszKeyName], eax
0x18000ac07  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000ac0e  mov     r8, r13
0x18000ac11  mov     rcx, [rcx+10h]
0x18000ac15  call    WPP_SF_sDs
0x18000ac1a  jmp     short loc_18000AC50
0x18000ac1c  mov     byte ptr [rsp+200h+var_190+1], 0
0x18000ac21  mov     byte ptr [rbp+100h+var_150+1], 0
0x18000ac25  lea     rcx, [rbp+100h+var_B0]; struct PIN_MAP_RECORD *
0x18000ac29  call    ?I_PinMapIsActive@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsActive(PIN_MAP_RECORD const *)
0x18000ac2e  test    eax, eax
0x18000ac30  jz      short loc_18000AC50
0x18000ac32  lea     rcx, [rbp+100h+var_B0]; struct PIN_MAP_RECORD *
0x18000ac36  call    ?I_PinMapIsBlocked@@YAHPEBUPIN_MAP_RECORD@@@Z; I_PinMapIsBlocked(PIN_MAP_RECORD const *)
0x18000ac3b  test    eax, eax
0x18000ac3d  jnz     short loc_18000AC50
0x18000ac3f  lea     rdx, [rbp+100h+var_B0]; unsigned __int16 *
0x18000ac43  mov     rcx, [rsp+200h+var_1B0]
0x18000ac48  mov     rcx, [rcx]; struct VCARD_DATA *
0x18000ac4b  call    ?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z; I_DeleteKspKey(VCARD_DATA const *,ushort const *)
0x18000ac50  mov     ebx, [rsp+200h+var_1C0]
0x18000ac54  lea     rcx, [rbp+100h+var_168]
0x18000ac58  call    wil__details__ScopeExitFnGuard__lambda_9255b61ebf9cdc00d424ac667efbfeba_____operator__
0x18000ac5d  nop
0x18000ac5e  lea     rcx, [rsp+200h+var_188]
0x18000ac63  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18000ac68  nop
0x18000ac69  lea     rcx, [rsp+200h+var_198]
0x18000ac6e  call    wil__details__ScopeExitFnGuard__lambda_f25b18b8ec239be5ec6b26588f446d9f_____operator__
0x18000ac73  nop
0x18000ac74  lea     rcx, [rsp+200h+var_1A0]
0x18000ac79  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18000ac7e  nop
0x18000ac7f  lea     rcx, [rbp+100h+var_170]
0x18000ac83  call    WppTraceUnwinder__lambda_83d1b05148d8ce538ce5599ab87dbed6_______WppTraceUnwinder__lambda_83d1b05148d8ce538ce5599ab87dbed6____
0x18000ac88  mov     eax, ebx
0x18000ac8a  mov     rcx, [rbp+100h+var_38]
0x18000ac91  xor     rcx, rsp; StackCookie
0x18000ac94  call    __security_check_cookie
0x18000ac99  add     rsp, 1D0h
0x18000aca0  pop     r15
0x18000aca2  pop     r13
0x18000aca4  pop     r12
0x18000aca6  pop     rdi
0x18000aca7  pop     rsi
0x18000aca8  pop     rbx
0x18000aca9  pop     rbp
0x18000acaa  retn
```
