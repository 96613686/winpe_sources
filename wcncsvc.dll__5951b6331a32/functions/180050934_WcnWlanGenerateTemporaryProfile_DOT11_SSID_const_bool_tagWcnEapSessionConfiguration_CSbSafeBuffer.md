# WcnWlanGenerateTemporaryProfile(_DOT11_SSID const *,bool,tagWcnEapSessionConfiguration *,CSbSafeBuffer *)

- ea: `0x180050934`
- end: `0x180050b2f`
- name: `?WcnWlanGenerateTemporaryProfile@@YAJPEBU_DOT11_SSID@@_NPEAUtagWcnEapSessionConfiguration@@PEAVCSbSafeBuffer@@@Z`
- size: `507`
- prototype: `int(const struct _DOT11_SSID *, bool, struct tagWcnEapSessionConfiguration *, struct CSbSafeBuffer *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180046e54`
- `0x18004c224`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000a6d4`
- `0x18004ff48`
- `0x180050934`
- `0x180053004`
- `0x18005630c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180050adf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180050adf`

## string_xrefs

- `0x180050a6c`: `<?xml version="1.0"?><WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> <name>WCN Temporary Profile</name> <SSIDConfig>  <SSID>   <hex>%s</hex>  </SSID>  <nonBroadcast>true</nonBroadcast> </SSIDConfig> <connectionType>ESS</connectionType> <connectionMode>manual</connectionMode> <MSM>  <security>   <authEncryption>    <authentication>open</authentication>    <encryption>WEP</encryption>    <useOneX>true</useOneX>   </authEncryption>   <OneX xmlns="http://www.microsoft.com/n`
- `0x180050a80`: `<?xml version="1.0"?><WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> <name>WCN Temporary Profile</name> <SSIDConfig>  <SSID>   <hex>%s</hex>  </SSID>  <nonBroadcast>true</nonBroadcast> </SSIDConfig> <connectionType>ESS</connectionType> <connectionMode>manual</connectionMode> <MSM>  <security>   <authEncryption>    <authentication>open</authentication>    <encryption>none</encryption>    <useOneX>true</useOneX>   </authEncryption>   <OneX xmlns="http://www.microsoft.com/`

## pseudocode

```c
__int64 __fastcall WcnWlanGenerateTemporaryProfile(
        const struct _DOT11_SSID *a1,
        char a2,
        struct tagWcnEapSessionConfiguration *a3,
        struct CSbSafeBuffer *a4)
{
  const char *Indent; // rax
  __int64 v9; // r10
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // ebx
  _BYTE *v13; // r10
  int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  const wchar_t *v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 33, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, Indent);
  }
  v10 = (unsigned __int16 *)operator new(0xAAEu, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    v14 = WcnStringBlobToHex(a1->uSSIDLength, a1->ucSSID, 0x42u, v10);
    v12 = v14;
    if ( v14 >= 0 )
    {
      v14 = WcnStringBlobToHex(0x14u, (const unsigned __int8 *)a3, 0x2Au, v11 + 66);
      v12 = v14;
      if ( v14 >= 0 )
      {
        v17 = L"<?xml version=\"1.0\"?><WLANProfile xmlns=\"http://www.microsoft.com/networking/WLAN/profile/v1\"> <name>W"
               "CN Temporary Profile</name> <SSIDConfig>  <SSID>   <hex>%s</hex>  </SSID>  <nonBroadcast>true</nonBroadca"
               "st> </SSIDConfig> <connectionType>ESS</connectionType> <connectionMode>manual</connectionMode> <MSM>  <se"
               "curity>   <authEncryption>    <authentication>open</authentication>    <encryption>none</encryption>    <"
               "useOneX>true</useOneX>   </authEncryption>   <OneX xmlns=\"http://www.microsoft.com/networking/OneX/v1\">"
               "    <maxAuthFailures>1</maxAuthFailures>    <EAPConfig>     <EapHostConfig xmlns=\"http://www.microsoft.c"
               "om/provisioning/EapHostConfig\">      <EapMethod>       <Type xmlns=\"http://www.microsoft.com/provisioni"
               "ng/EapCommon\">254</Type>       <VendorId xmlns=\"http://www.microsoft.com/provisioning/EapCommon\">14122"
               "</VendorId>       <VendorType xmlns=\"http://www.microsoft.com/provisioning/EapCommon\">1</VendorType>   "
               "    <AuthorId xmlns=\"http://www.microsoft.com/provisioning/EapCommon\">311</AuthorId>      </EapMethod> "
               "     <ConfigBlob>%s</ConfigBlob>     </EapHostConfig>    </EAPConfig>   </OneX>  </security> </MSM></WLANProfile>";
        if ( !a2 )
          v17 = L"<?xml version=\"1.0\"?><WLANProfile xmlns=\"http://www.microsoft.com/networking/WLAN/profile/v1\"> <name"
                 ">WCN Temporary Profile</name> <SSIDConfig>  <SSID>   <hex>%s</hex>  </SSID>  <nonBroadcast>true</nonBro"
                 "adcast> </SSIDConfig> <connectionType>ESS</connectionType> <connectionMode>manual</connectionMode> <MSM"
                 ">  <security>   <authEncryption>    <authentication>open</authentication>    <encryption>WEP</encryptio"
                 "n>    <useOneX>true</useOneX>   </authEncryption>   <OneX xmlns=\"http://www.microsoft.com/networking/O"
                 "neX/v1\">    <maxAuthFailures>1</maxAuthFailures>    <EAPConfig>     <EapHostConfig xmlns=\"http://www."
                 "microsoft.com/provisioning/EapHostConfig\">      <EapMethod>       <Type xmlns=\"http://www.microsoft.c"
                 "om/provisioning/EapCommon\">254</Type>       <VendorId xmlns=\"http://www.microsoft.com/provisioning/Ea"
                 "pCommon\">14122</VendorId>       <VendorType xmlns=\"http://www.microsoft.com/provisioning/EapCommon\">"
                 "1</VendorType>       <AuthorId xmlns=\"http://www.microsoft.com/provisioning/EapCommon\">311</AuthorId>"
                 "      </EapMethod>      <ConfigBlob>%s</ConfigBlob>     </EapHostConfig>    </EAPConfig>   </OneX>  </s"
                 "ecurity> </MSM></WLANProfile>";
        v18 = swprintf_s<1259>(v11 + 108, v17, v11, v11 + 66);
        if ( v18 > 0x4EA )
        {
          v12 = -2147022885;
          goto LABEL_25;
        }
        v14 = CSbSafeBuffer::CopyFromBuffer(a4, (const unsigned __int8 *)v11 + 216, 2LL * (int)(v18 + 1));
        v12 = v14;
        if ( v14 >= 0 )
          goto LABEL_25;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_25;
        v16 = 37;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_25;
        v16 = 36;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_25;
      v16 = 35;
    }
    WPP_SF_d(v15[2], v16, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, (unsigned int)v14);
LABEL_25:
    operator delete(v11);
    goto LABEL_26;
  }
  v12 = -2147024882;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v12;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, "pData");
LABEL_26:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != (_BYTE *)&WPP_GLOBAL_Control && (v12 < 0 || v13[25] >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 38, (unsigned int)WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, v19, v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180050934  push    rbx
0x180050936  push    rbp
0x180050937  push    rsi
0x180050938  push    rdi
0x180050939  push    r12
0x18005093b  push    r13
0x18005093d  push    r14
0x18005093f  push    r15
0x180050941  sub     rsp, 38h
0x180050945  mov     r15, r9
0x180050948  mov     rbp, r8
0x18005094b  mov     r14b, dl
0x18005094e  mov     rbx, rcx
0x180050951  mov     r10, cs:WPP_GLOBAL_Control
0x180050958  lea     r12, WPP_GLOBAL_Control
0x18005095f  lea     r13, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x180050966  cmp     r10, r12
0x180050969  jz      short loc_180050990
0x18005096b  cmp     byte ptr [r10+19h], 6
0x180050970  jb      short loc_180050990
0x180050972  mov     ecx, 1; int
0x180050977  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18005097c  mov     rcx, [r10+10h]
0x180050980  mov     edx, 21h ; '!'
0x180050985  mov     r9, rax
0x180050988  mov     r8, r13
0x18005098b  call    WPP_SF_s
0x180050990  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180050997  mov     ecx, 0AAEh; unsigned __int64
0x18005099c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800509a1  mov     rdi, rax
0x1800509a4  test    rax, rax
0x1800509a7  jnz     short loc_1800509E4
0x1800509a9  mov     ebx, 8007000Eh
0x1800509ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800509b5  cmp     r10, r12
0x1800509b8  jz      loc_180050B1C
0x1800509be  cmp     byte ptr [r10+19h], 2
0x1800509c3  jb      loc_180050AEC
0x1800509c9  mov     rcx, [r10+10h]
0x1800509cd  lea     edx, [rax+22h]
0x1800509d0  lea     r9, aPdata; "pData"
0x1800509d7  mov     r8, r13
0x1800509da  call    WPP_SF_s
0x1800509df  jmp     loc_180050AE5
0x1800509e4  mov     ecx, [rbx]; unsigned int
0x1800509e6  lea     rdx, [rbx+4]; unsigned __int8 *
0x1800509ea  mov     r9, rdi; unsigned __int16 *
0x1800509ed  mov     r8d, 42h ; 'B'; unsigned int
0x1800509f3  call    ?WcnStringBlobToHex@@YAJKPEBEKPEAG@Z; WcnStringBlobToHex(ulong,uchar const *,ulong,ushort *)
0x1800509f8  mov     ebx, eax
0x1800509fa  test    eax, eax
0x1800509fc  jns     short loc_180050A31
0x1800509fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a05  cmp     rcx, r12
0x180050a08  jz      loc_180050ADC
0x180050a0e  cmp     byte ptr [rcx+19h], 2
0x180050a12  jb      loc_180050ADC
0x180050a18  mov     edx, 23h ; '#'
0x180050a1d  mov     rcx, [rcx+10h]
0x180050a21  mov     r9d, eax
0x180050a24  mov     r8, r13
0x180050a27  call    WPP_SF_d
0x180050a2c  jmp     loc_180050ADC
0x180050a31  mov     r8d, 2Ah ; '*'; unsigned int
0x180050a37  lea     rsi, [rdi+84h]
0x180050a3e  mov     r9, rsi; unsigned __int16 *
0x180050a41  mov     rdx, rbp; unsigned __int8 *
0x180050a44  lea     ecx, [r8-16h]; unsigned int
0x180050a48  call    ?WcnStringBlobToHex@@YAJKPEBEKPEAG@Z; WcnStringBlobToHex(ulong,uchar const *,ulong,ushort *)
0x180050a4d  mov     ebx, eax
0x180050a4f  test    eax, eax
0x180050a51  jns     short loc_180050A6C
0x180050a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a5a  cmp     rcx, r12
0x180050a5d  jz      short loc_180050ADC
0x180050a5f  cmp     byte ptr [rcx+19h], 2
0x180050a63  jb      short loc_180050ADC
0x180050a65  mov     edx, 24h ; '$'
0x180050a6a  jmp     short loc_180050A1D
0x180050a6c  lea     rax, aXmlVersion10Wl; "<?xml version=\"1.0\"?><WLANProfile xml"...
0x180050a73  test    r14b, r14b
0x180050a76  lea     rbx, [rdi+0D8h]
0x180050a7d  mov     r9, rsi
0x180050a80  lea     rdx, aXmlVersion10Wl_0; "<?xml version=\"1.0\"?><WLANProfile xml"...
0x180050a87  mov     r8, rdi
0x180050a8a  cmovz   rdx, rax
0x180050a8e  mov     rcx, rbx
0x180050a91  call    ??$swprintf_s@$0EOL@@@YAHAEAY0EOL@GPEBGZZ; swprintf_s<1259>(ushort (&)[1259],ushort const *,...)
0x180050a96  cmp     eax, 0FFFFFFFFh
0x180050a99  jz      short loc_180050AD7
0x180050a9b  cmp     eax, 4EBh
0x180050aa0  jnb     short loc_180050AD7
0x180050aa2  inc     eax
0x180050aa4  mov     rdx, rbx; unsigned __int8 *
0x180050aa7  movsxd  r8, eax
0x180050aaa  mov     rcx, r15; this
0x180050aad  add     r8, r8; unsigned __int64
0x180050ab0  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x180050ab5  mov     ebx, eax
0x180050ab7  test    eax, eax
0x180050ab9  jns     short loc_180050ADC
0x180050abb  mov     rcx, cs:WPP_GLOBAL_Control
0x180050ac2  cmp     rcx, r12
0x180050ac5  jz      short loc_180050ADC
0x180050ac7  cmp     byte ptr [rcx+19h], 2
0x180050acb  jb      short loc_180050ADC
0x180050acd  mov     edx, 25h ; '%'
0x180050ad2  jmp     loc_180050A1D
0x180050ad7  mov     ebx, 800707DBh
0x180050adc  mov     rcx, rdi
0x180050adf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180050ae5  mov     r10, cs:WPP_GLOBAL_Control
0x180050aec  cmp     r10, r12
0x180050aef  jz      short loc_180050B1C
0x180050af1  test    ebx, ebx
0x180050af3  js      short loc_180050AFC
0x180050af5  cmp     byte ptr [r10+19h], 6
0x180050afa  jb      short loc_180050B1C
0x180050afc  or      ecx, 0FFFFFFFFh; int
0x180050aff  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180050b04  mov     rcx, [r10+10h]
0x180050b08  mov     edx, 26h ; '&'
0x180050b0d  mov     r9, rax
0x180050b10  mov     [rsp+78h+var_58], ebx
0x180050b14  mov     r8, r13
0x180050b17  call    WPP_SF_sd
0x180050b1c  mov     eax, ebx
0x180050b1e  add     rsp, 38h
0x180050b22  pop     r15
0x180050b24  pop     r14
0x180050b26  pop     r13
0x180050b28  pop     r12
0x180050b2a  pop     rdi
0x180050b2b  pop     rsi
0x180050b2c  pop     rbp
0x180050b2d  pop     rbx
0x180050b2e  retn
```
