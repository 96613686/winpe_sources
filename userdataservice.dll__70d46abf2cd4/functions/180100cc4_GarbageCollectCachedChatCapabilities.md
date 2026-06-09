# _GarbageCollectCachedChatCapabilities

- ea: `0x180100cc4`
- end: `0x1801010e2`
- name: `_GarbageCollectCachedChatCapabilities`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101714`

## callees

- `0x1800049f0`
- `0x18000e1f8`
- `0x180012988`
- `0x180017a9c`
- `0x180046614`
- `0x180062674`
- `0x1800909cc`
- `0x1801006e4`
- `0x180100854`
- `0x180100cc4`
- `0x180101144`
- `0x1801018ac`
- `0x1801018dc`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PhoneUtil!GetTelUriFromDialString` at `0x180100f25`
- `PhoneUtil!GetTelUriFromDialString` at `0x180100fab`
- `PhoneUtil!GetTelUriFromDialString` at `0x180100f25`
- `PhoneUtil!GetTelUriFromDialString` at `0x180100fab`
- `PhoneUtil!GetDialStringFromTelUri` at `0x180100f40`
- `PhoneUtil!GetDialStringFromTelUri` at `0x180100fc9`
- `PhoneUtil!GetDialStringFromTelUri` at `0x180100f40`
- `PhoneUtil!GetDialStringFromTelUri` at `0x180100fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180100d10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180100d10`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180100e6c`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180100e6c`
- `PhoneOm!PhoneAPIInitialize` at `0x180100dd1`
- `PhoneOm!PhoneAPIInitialize` at `0x180100dd1`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180100e32`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180100e32`

## pseudocode

```c
__int64 __fastcall GarbageCollectCachedChatCapabilities(__int64 *a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v7)(__int64 *, __int64 *, __int64); // rdi
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  int DefaultOutgoingLine; // eax
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 i; // rbx
  __int64 v19; // r10
  __int64 v20; // r11
  int DialStringFromTelUri; // edi
  __int64 v22; // r15
  unsigned int j; // esi
  int TelUriFromDialString; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rcx
  _BYTE v33[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v34[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 **v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[8]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v39; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[128]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v41[96]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v42[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v43[64]; // [rsp+260h] [rbp+160h] BYREF

  v3 = *a1;
  v36 = 0;
  v35 = 0;
  v7 = *(__int64 (__fastcall **)(__int64 *, __int64 *, __int64))(v3 + 32);
  GetProcessHeap();
  tlx::replace<UdmPropertyValue,&void _MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>((void **)&v36);
  v8 = v7(a1, qword_180141BF0, 1);
  LODWORD(v9) = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_45(
      (unsigned int)v8,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
      111);
    goto LABEL_42;
  }
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v34);
  if ( !(unsigned __int8)utl::vector<int,utl::allocator<int>>::_Resize<,0>(
                           v34,
                           0x6DB6DB6DB6DB6DB7LL * ((__int64)(a2[1] - *a2) >> 3)) )
  {
    LODWORD(v9) = -2147024882;
    v10 = 114;
    v11 = 2147942414LL;
    v12 = 0;
LABEL_5:
    Log_HREvent_45(
      v11,
      v12,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
      v10);
LABEL_6:
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v34);
    goto LABEL_42;
  }
  v13 = PhoneAPIInitialize();
  LODWORD(v9) = v13;
  if ( v13 < 0 )
  {
    v10 = 116;
    v12 = 1;
    v11 = (unsigned int)v13;
    goto LABEL_5;
  }
  v33[1] = 1;
  v39 = 0;
  memset_0(v40, 0, 0x13Cu);
  memset_0(v42, 0, sizeof(v42));
  memset_0(v43, 0, sizeof(v43));
  DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v39);
  LODWORD(v9) = DefaultOutgoingLine;
  if ( DefaultOutgoingLine < 0 )
  {
    v15 = 125;
LABEL_11:
    Log_HREvent_45(
      (unsigned int)DefaultOutgoingLine,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
      v15);
    tlx::_UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___::__UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___(
      v33,
      v16);
    goto LABEL_6;
  }
  DefaultOutgoingLine = PhoneGetProviderLineServiceInfo(&v39, v40);
  LODWORD(v9) = DefaultOutgoingLine;
  if ( DefaultOutgoingLine < 0 )
  {
    v15 = 126;
    goto LABEL_11;
  }
  for ( i = 0; (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
  {
    if ( (HIWORD(v36[3 * i]) & 0x300) == 0 )
    {
      if ( *((_DWORD *)qword_180141BF0 + i) == 1090519105 )
      {
        utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v37);
        DialStringFromTelUri = ContactPropsFromBlob<ContactPhoneData>(
                                 *(_DWORD *)(v20 + 8 * v19 + 8),
                                 *(unsigned __int16 **)(v20 + 8 * v19 + 16),
                                 v37);
        if ( DialStringFromTelUri >= 0 )
        {
          v22 = v37[0];
          for ( j = 0; ; ++j )
          {
            if ( j >= (unsigned __int64)(0x2E8BA2E8BA2E8BA3LL * ((v37[1] - v22) >> 3)) )
            {
              utl::vector<ContactPhoneData,utl::allocator<ContactPhoneData>>::_Uninit(v37);
              goto LABEL_31;
            }
            TelUriFromDialString = GetTelUriFromDialString(
                                     *(const unsigned __int16 **)(88LL * j + v22 + 16),
                                     v41,
                                     v42,
                                     0x40u);
            if ( TelUriFromDialString < 0 )
            {
              Log_HREvent_45(
                (unsigned int)TelUriFromDialString,
                0,
                "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
                152);
            }
            else
            {
              DialStringFromTelUri = GetDialStringFromTelUri(v42, v43, 0x40u);
              if ( DialStringFromTelUri < 0 )
              {
                v27 = 147;
                goto LABEL_34;
              }
              MarkAsSeen(v43, a2, v34);
            }
          }
        }
        v27 = 136;
LABEL_34:
        Log_HREvent_45(
          (unsigned int)DialStringFromTelUri,
          1,
          "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
          v27);
        utl::vector<ContactPhoneData,utl::allocator<ContactPhoneData>>::_Uninit(v37);
        goto LABEL_35;
      }
      v25 = GetTelUriFromDialString(v36[3 * i + 1], v41, v42, 0x40u);
      if ( v25 < 0 )
      {
        Log_HREvent_45(
          (unsigned int)v25,
          0,
          "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
          169);
      }
      else
      {
        v26 = GetDialStringFromTelUri(v42, v43, 0x40u);
        DialStringFromTelUri = v26;
        if ( v26 < 0 )
        {
          Log_HREvent_45(
            (unsigned int)v26,
            1,
            "onecoreuap\\base\\appmodel\\messagingom\\utils\\contactrcscapabilities\\lib\\contactrcscapabilities.cpp",
            164);
LABEL_35:
          tlx::_UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___::__UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___(
            v33,
            v28);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v34);
          LODWORD(v9) = DialStringFromTelUri;
          goto LABEL_42;
        }
        MarkAsSeen(v43, a2, v34);
      }
    }
LABEL_31:
    ;
  }
  v29 = v34[0];
  v9 = (__int64)(v34[1] - v34[0]) >> 2;
  while ( (_DWORD)v9 )
  {
    v9 = (unsigned int)(v9 - 1);
    v17 = (unsigned int)v9;
    if ( !*(_DWORD *)(v29 + 4 * v9) )
    {
      v30 = utl::vector<ContactRcsCapabilityData,utl::allocator<ContactRcsCapabilityData>>::at(a2, (unsigned int)v9);
      utl::vector<ContactRcsCapabilityData,utl::allocator<ContactRcsCapabilityData>>::erase(v31, v38, v30);
      ++*a3;
    }
  }
  tlx::_UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___::__UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___(
    v33,
    v17);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v34);
LABEL_42:
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v36);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180100cc4  push    rbp
0x180100cc6  push    rbx
0x180100cc7  push    rsi
0x180100cc8  push    rdi
0x180100cc9  push    r12
0x180100ccb  push    r14
0x180100ccd  push    r15
0x180100ccf  lea     rbp, [rsp-1F0h]
0x180100cd7  sub     rsp, 2F0h
0x180100cde  mov     rax, cs:__security_cookie
0x180100ce5  xor     rax, rsp
0x180100ce8  mov     [rbp+220h+var_40], rax
0x180100cef  mov     rax, [rcx]
0x180100cf2  mov     r12, r8
0x180100cf5  mov     r14, rdx
0x180100cf8  mov     [rsp+320h+var_2B8], 0
0x180100d01  mov     rsi, rcx
0x180100d04  mov     [rsp+320h+var_2C0], 0
0x180100d0c  mov     rdi, [rax+20h]
0x180100d10  call    cs:__imp_GetProcessHeap
0x180100d16  lea     rcx, [rsp+320h+var_2B8]
0x180100d1b  mov     rbx, rax
0x180100d1e  call    ??$replace@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAUUdmPropertyValue@@AEAV?$auto_ptr@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(tlx::auto_ptr<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)> &)
0x180100d23  mov     r9d, 0Dh
0x180100d29  mov     [rsp+320h+var_2F0], rbx
0x180100d2e  lea     rcx, [rsp+320h+var_2C0]
0x180100d33  mov     [rsp+320h+var_2F8], rcx
0x180100d38  lea     rdx, qword_180141BF0
0x180100d3f  mov     [rsp+320h+var_300], rax
0x180100d44  mov     rcx, rsi
0x180100d47  lea     r15d, [r9-0Ch]
0x180100d4b  mov     rax, rdi
0x180100d4e  mov     r8d, r15d
0x180100d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100d56  mov     ebx, eax
0x180100d58  test    eax, eax
0x180100d5a  jns     short loc_180100D76
0x180100d5c  lea     r9d, [r15+6Eh]
0x180100d60  mov     edx, r15d
0x180100d63  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180100d6a  mov     ecx, eax
0x180100d6c  call    Log_HREvent_45
0x180100d71  jmp     loc_1801010B5
0x180100d76  lea     rcx, [rsp+320h+var_2D8]
0x180100d7b  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180100d80  mov     rdx, [r14+8]
0x180100d84  lea     rcx, [rsp+320h+var_2D8]
0x180100d89  sub     rdx, [r14]
0x180100d8c  mov     rax, 6DB6DB6DB6DB6DB7h
0x180100d96  sar     rdx, 3
0x180100d9a  imul    rdx, rax
0x180100d9e  call    ??$_Resize@$$V$0A@@?$vector@HV?$allocator@H@utl@@@utl@@AEAA_N_K@Z; utl::vector<int,utl::allocator<int>>::_Resize<,0>(unsigned __int64)
0x180100da3  test    al, al
0x180100da5  jnz     short loc_180100DD1
0x180100da7  mov     ebx, 8007000Eh
0x180100dac  mov     r9d, 72h ; 'r'
0x180100db2  mov     ecx, ebx
0x180100db4  xor     edx, edx
0x180100db6  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180100dbd  call    Log_HREvent_45
0x180100dc2  lea     rcx, [rsp+320h+var_2D8]
0x180100dc7  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x180100dcc  jmp     loc_1801010B5
0x180100dd1  call    cs:__imp_PhoneAPIInitialize
0x180100dd7  mov     ebx, eax
0x180100dd9  test    eax, eax
0x180100ddb  jns     short loc_180100DEA
0x180100ddd  mov     r9d, 74h ; 't'
0x180100de3  mov     edx, r15d
0x180100de6  mov     ecx, eax
0x180100de8  jmp     short loc_180100DB6
0x180100dea  xorps   xmm0, xmm0
0x180100ded  mov     [rsp+320h+var_2DF], r15b
0x180100df2  xor     edx, edx; Val
0x180100df4  lea     rcx, [rbp+220h+var_280]; void *
0x180100df8  mov     r8d, 13Ch; Size
0x180100dfe  movups  [rbp+220h+var_290], xmm0
0x180100e02  call    memset_0
0x180100e07  mov     ebx, 80h
0x180100e0c  lea     rcx, [rbp+220h+var_140]; void *
0x180100e13  mov     r8d, ebx; Size
0x180100e16  xor     edx, edx; Val
0x180100e18  call    memset_0
0x180100e1d  mov     r8d, ebx; Size
0x180100e20  lea     rcx, [rbp+220h+var_C0]; void *
0x180100e27  xor     edx, edx; Val
0x180100e29  call    memset_0
0x180100e2e  lea     rcx, [rbp+220h+var_290]
0x180100e32  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x180100e38  mov     ebx, eax
0x180100e3a  test    eax, eax
0x180100e3c  jns     short loc_180100E64
0x180100e3e  mov     r9d, 7Dh ; '}'
0x180100e44  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180100e4b  mov     edx, r15d
0x180100e4e  mov     ecx, eax
0x180100e50  call    Log_HREvent_45
0x180100e55  lea     rcx, [rsp+320h+var_2E0]
0x180100e5a  call    tlx___UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55_______UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___
0x180100e5f  jmp     loc_180100DC2
0x180100e64  lea     rdx, [rbp+220h+var_280]
0x180100e68  lea     rcx, [rbp+220h+var_290]
0x180100e6c  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x180100e72  mov     ebx, eax
0x180100e74  test    eax, eax
0x180100e76  jns     short loc_180100E80
0x180100e78  mov     r9d, 7Eh ; '~'
0x180100e7e  jmp     short loc_180100E44
0x180100e80  xor     ebx, ebx
0x180100e82  cmp     ebx, 0Dh
0x180100e85  jnb     loc_180101068
0x180100e8b  mov     r11, [rsp+320h+var_2B8]
0x180100e90  lea     r10, [rbx+rbx*2]
0x180100e94  mov     ecx, 300h
0x180100e99  test    [r11+r10*8+6], cx
0x180100e9f  jnz     loc_180101001
0x180100ea5  lea     rcx, qword_180141BF0
0x180100eac  cmp     dword ptr [rcx+rbx*4], 41000041h
0x180100eb3  jnz     loc_180100F95
0x180100eb9  lea     rcx, [rsp+320h+var_2B0]
0x180100ebe  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180100ec3  mov     rdx, [r11+r10*8+10h]
0x180100ec8  lea     r8, [rsp+320h+var_2B0]
0x180100ecd  mov     ecx, [r11+r10*8+8]
0x180100ed2  call    ??$ContactPropsFromBlob@VContactPhoneData@@@@YAJKPEAEPEAV?$vector@VContactPhoneData@@V?$allocator@VContactPhoneData@@@utl@@@utl@@@Z; ContactPropsFromBlob<ContactPhoneData>(ulong,uchar *,utl::vector<ContactPhoneData,utl::allocator<ContactPhoneData>> *)
0x180100ed7  mov     edi, eax
0x180100ed9  test    eax, eax
0x180100edb  js      loc_180101016
0x180100ee1  mov     r15, [rsp+320h+var_2B0]
0x180100ee6  xor     esi, esi
0x180100ee8  mov     rax, [rsp+320h+var_2A8]
0x180100eed  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180100ef7  sub     rax, r15
0x180100efa  mov     ecx, esi
0x180100efc  sar     rax, 3
0x180100f00  imul    rax, rdx
0x180100f04  cmp     rcx, rax
0x180100f07  jnb     short loc_180100F83
0x180100f09  imul    rcx, 58h ; 'X'
0x180100f0d  mov     edi, 40h ; '@'
0x180100f12  lea     r8, [rbp+220h+var_140]
0x180100f19  mov     r9d, edi
0x180100f1c  lea     rdx, [rbp+220h+var_200]
0x180100f20  mov     rcx, [rcx+r15+10h]
0x180100f25  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x180100f2b  test    eax, eax
0x180100f2d  js      short loc_180100F66
0x180100f2f  mov     r8d, edi
0x180100f32  lea     rdx, [rbp+220h+var_C0]
0x180100f39  lea     rcx, [rbp+220h+var_140]
0x180100f40  call    cs:__imp_?GetDialStringFromTelUri@@YAJPEBGPEAGI@Z; GetDialStringFromTelUri(ushort const *,ushort *,uint)
0x180100f46  mov     edi, eax
0x180100f48  test    eax, eax
0x180100f4a  js      loc_180101009
0x180100f50  lea     r8, [rsp+320h+var_2D8]
0x180100f55  mov     rdx, r14
0x180100f58  lea     rcx, [rbp+220h+var_C0]
0x180100f5f  call    _MarkAsSeen
0x180100f64  jmp     short loc_180100F7C
0x180100f66  mov     r9d, 98h
0x180100f6c  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180100f73  xor     edx, edx
0x180100f75  mov     ecx, eax
0x180100f77  call    Log_HREvent_45
0x180100f7c  inc     esi
0x180100f7e  jmp     loc_180100EE8
0x180100f83  lea     rcx, [rsp+320h+var_2B0]
0x180100f88  call    ?_Uninit@?$vector@VContactPhoneData@@V?$allocator@VContactPhoneData@@@utl@@@utl@@AEAAXXZ; utl::vector<ContactPhoneData,utl::allocator<ContactPhoneData>>::_Uninit(void)
0x180100f8d  mov     r15d, 1
0x180100f93  jmp     short loc_180101001
0x180100f95  mov     rcx, [r11+r10*8+8]
0x180100f9a  lea     r8, [rbp+220h+var_140]
0x180100fa1  mov     r9d, 40h ; '@'
0x180100fa7  lea     rdx, [rbp+220h+var_200]
0x180100fab  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x180100fb1  test    eax, eax
0x180100fb3  js      short loc_180100FEB
0x180100fb5  mov     r8d, 40h ; '@'
0x180100fbb  lea     rdx, [rbp+220h+var_C0]
0x180100fc2  lea     rcx, [rbp+220h+var_140]
0x180100fc9  call    cs:__imp_?GetDialStringFromTelUri@@YAJPEBGPEAGI@Z; GetDialStringFromTelUri(ushort const *,ushort *,uint)
0x180100fcf  mov     edi, eax
0x180100fd1  test    eax, eax
0x180100fd3  js      short loc_18010104F
0x180100fd5  lea     r8, [rsp+320h+var_2D8]
0x180100fda  mov     rdx, r14
0x180100fdd  lea     rcx, [rbp+220h+var_C0]
0x180100fe4  call    _MarkAsSeen
0x180100fe9  jmp     short loc_180101001
0x180100feb  mov     r9d, 0A9h
0x180100ff1  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180100ff8  xor     edx, edx
0x180100ffa  mov     ecx, eax
0x180100ffc  call    Log_HREvent_45
0x180101001  add     ebx, r15d
0x180101004  jmp     loc_180100E82
0x180101009  mov     r9d, 93h
0x18010100f  mov     edx, 1
0x180101014  jmp     short loc_18010101F
0x180101016  mov     r9d, 88h
0x18010101c  mov     edx, r15d
0x18010101f  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x180101026  mov     ecx, edi
0x180101028  call    Log_HREvent_45
0x18010102d  lea     rcx, [rsp+320h+var_2B0]
0x180101032  call    ?_Uninit@?$vector@VContactPhoneData@@V?$allocator@VContactPhoneData@@@utl@@@utl@@AEAAXXZ; utl::vector<ContactPhoneData,utl::allocator<ContactPhoneData>>::_Uninit(void)
0x180101037  lea     rcx, [rsp+320h+var_2E0]
0x18010103c  call    tlx___UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55_______UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___
0x180101041  lea     rcx, [rsp+320h+var_2D8]
0x180101046  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x18010104b  mov     ebx, edi
0x18010104d  jmp     short loc_1801010B5
0x18010104f  mov     r9d, 0A4h
0x180101055  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\messagingom"...
0x18010105c  mov     edx, r15d
0x18010105f  mov     ecx, edi
0x180101061  call    Log_HREvent_45
0x180101066  jmp     short loc_180101037
0x180101068  mov     rbx, [rsp+320h+var_2D0]
0x18010106d  mov     rdi, [rsp+320h+var_2D8]
0x180101072  sub     rbx, rdi
0x180101075  sar     rbx, 2
0x180101079  jmp     short loc_18010109D
0x18010107b  dec     ebx
0x18010107d  mov     edx, ebx
0x18010107f  cmp     dword ptr [rdi+rbx*4], 0
0x180101083  jnz     short loc_18010109D
0x180101085  mov     rcx, r14
0x180101088  call    ?at@?$vector@VContactRcsCapabilityData@@V?$allocator@VContactRcsCapabilityData@@@utl@@@utl@@QEAAAEAVContactRcsCapabilityData@@_K@Z; utl::vector<ContactRcsCapabilityData,utl::allocator<ContactRcsCapabilityData>>::at(unsigned __int64)
0x18010108d  mov     r8, rax
0x180101090  lea     rdx, [rbp+220h+var_298]
0x180101094  call    ?erase@?$vector@VContactRcsCapabilityData@@V?$allocator@VContactRcsCapabilityData@@@utl@@@utl@@QEAA?AV?$_ArrayIt@VContactRcsCapabilityData@@@2@V?$_ArrayConstIt@VContactRcsCapabilityData@@@2@@Z; utl::vector<ContactRcsCapabilityData,utl::allocator<ContactRcsCapabilityData>>::erase(utl::_ArrayConstIt<ContactRcsCapabilityData>)
0x180101099  add     [r12], r15d
0x18010109d  test    ebx, ebx
0x18010109f  jnz     short loc_18010107B
0x1801010a1  lea     rcx, [rsp+320h+var_2E0]
0x1801010a6  call    tlx___UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55_______UndoSolo__lambda_1a1406cdb4b1be29c4c14917f743cc55___
0x1801010ab  lea     rcx, [rsp+320h+var_2D8]
0x1801010b0  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1801010b5  lea     rcx, [rsp+320h+var_2B8]
0x1801010ba  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1801010bf  mov     eax, ebx
0x1801010c1  mov     rcx, [rbp+220h+var_40]
0x1801010c8  xor     rcx, rsp; StackCookie
0x1801010cb  call    __security_check_cookie
0x1801010d0  add     rsp, 2F0h
0x1801010d7  pop     r15
0x1801010d9  pop     r14
0x1801010db  pop     r12
0x1801010dd  pop     rdi
0x1801010de  pop     rsi
0x1801010df  pop     rbx
0x1801010e0  pop     rbp
0x1801010e1  retn
```
