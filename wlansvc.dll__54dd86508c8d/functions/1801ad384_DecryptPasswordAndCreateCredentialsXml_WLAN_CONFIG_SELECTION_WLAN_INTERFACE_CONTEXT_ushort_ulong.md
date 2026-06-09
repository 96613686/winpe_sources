# DecryptPasswordAndCreateCredentialsXml(WLAN_CONFIG_SELECTION *,_WLAN_INTERFACE_CONTEXT *,ushort *,ulong)

- ea: `0x1801ad384`
- end: `0x1801ad706`
- name: `?DecryptPasswordAndCreateCredentialsXml@@YAKPEAUWLAN_CONFIG_SELECTION@@PEAU_WLAN_INTERFACE_CONTEXT@@PEAGK@Z`
- size: `898`
- prototype: `unsigned int(struct WLAN_CONFIG_SELECTION *, struct _WLAN_INTERFACE_CONTEXT *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801ad054`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x180019bd0`
- `0x1800c996c`
- `0x180107318`
- `0x1801ad384`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad664`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801ad546`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801ad546`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801ad65c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801ad65c`
- `CRYPT32!CryptUnprotectData` at `0x1801ad577`
- `CRYPT32!CryptUnprotectData` at `0x1801ad577`

## string_xrefs

- `0x1801ad5b1`: `<?xml version="1.0"?><EapHostUserCredentials xmlns="http://www.microsoft.com/provisioning/EapHostUserCredentials" xmlns:eapCommon="http://www.microsoft.com/provisioning/EapCommon" xmlns:baseEap="http://www.microsoft.com/provisioning/BaseEapMethodUserCredentials">  <EapMethod>    <eapCommon:Type>25</eapCommon:Type>    <eapCommon:AuthorId>0</eapCommon:AuthorId>  </EapMethod>  <Credentials xmlns:eapUser="http://www.microsoft.com/provisioning/EapUserPropertiesV1" xmlns:xsi="http://www.w3.org/2001/XM`

## pseudocode

```c
__int64 __fastcall DecryptPasswordAndCreateCredentialsXml(
        struct WLAN_CONFIG_SELECTION *a1,
        struct _WLAN_INTERFACE_CONTEXT *a2,
        unsigned __int16 *a3)
{
  DWORD ProfileUserData; // eax
  unsigned __int8 *v6; // r14
  DWORD LastError; // edi
  unsigned int v8; // edx
  unsigned __int8 *v9; // r8
  unsigned int v10; // ecx
  unsigned int v11; // edx
  unsigned __int8 *v12; // r9
  unsigned int v13; // ecx
  unsigned int v14; // r8d
  unsigned __int8 *v15; // rdx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned __int8 *v18; // rsi
  void *v19; // rcx
  int v20; // ebx
  CRYPTPROTECT_PROMPTSTRUCT *pPromptStruct; // [rsp+20h] [rbp-50h]
  DATA_BLOB pDataIn; // [rsp+50h] [rbp-20h] BYREF
  DATA_BLOB pDataOut; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 *v25; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+48h] BYREF

  v25 = 0;
  v26 = 0;
  LODWORD(pPromptStruct) = 1;
  ProfileUserData = wlansvc::profile::GetProfileUserData(
                      0,
                      (void *)2,
                      *((_QWORD *)a1 + 86),
                      (char *)a2 + 8,
                      (const struct _GUID *)pPromptStruct,
                      (unsigned __int16 *)a1 + 12,
                      0,
                      (struct _PM_PROFILE *)L"MSMUserData",
                      &v26,
                      &v25);
  v6 = v25;
  LastError = ProfileUserData;
  if ( ProfileUserData )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        10,
        WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids,
        ProfileUserData);
    }
LABEL_47:
    LastError = 2011;
    goto LABEL_48;
  }
  if ( v26 < 0x18 )
    goto LABEL_45;
  v8 = *((_DWORD *)v25 + 5);
  if ( v8 < 0x18 )
    goto LABEL_45;
  if ( v26 < v8 )
    goto LABEL_45;
  v9 = &v25[v8];
  if ( !v9 )
    goto LABEL_45;
  v10 = v26 - v8;
  if ( v26 - v8 < 0x14 )
    goto LABEL_45;
  v11 = *((_DWORD *)v9 + 4);
  if ( v11 < 0x1C
    || v10 < v11
    || (v12 = &v9[v11]) == 0
    || (v13 = v10 - v11, v13 < 0x20)
    || (v14 = *((_DWORD *)v12 + 7), v14 < 0x20)
    || v13 < v14
    || (v15 = &v12[v14]) == 0
    || (v16 = v13 - v14, v16 < 0x3C)
    || *v15 != 25
    || (v17 = v16 - 60, v17 < 0x14)
    || v17 < *((_DWORD *)v15 + 16)
    || *((_DWORD *)v15 + 17) != 26
    || (v18 = v15 + 76, v15 == (unsigned __int8 *)-76LL) )
  {
LABEL_45:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids);
    }
    goto LABEL_47;
  }
  v19 = (void *)*((_QWORD *)a1 + 86);
  pDataIn.pbData = v15 + 864;
  pDataIn.cbData = *((_DWORD *)v15 + 215);
  *(&pDataIn.cbData + 1) = 0;
  pDataOut = 0;
  if ( ImpersonateLoggedOnUser(v19) )
  {
    if ( CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
    {
      memcpy_0(v18 + 269, pDataOut.pbData, pDataOut.cbData);
      v20 = StringCchPrintfW(
              a3,
              0xFA0u,
              L"<?xml version=\"1.0\"?><EapHostUserCredentials xmlns=\"http://www.microsoft.com/provisioning/EapHostUserCr"
               "edentials\" xmlns:eapCommon=\"http://www.microsoft.com/provisioning/EapCommon\" xmlns:baseEap=\"http://ww"
               "w.microsoft.com/provisioning/BaseEapMethodUserCredentials\">  <EapMethod>    <eapCommon:Type>25</eapCommo"
               "n:Type>    <eapCommon:AuthorId>0</eapCommon:AuthorId>  </EapMethod>  <Credentials xmlns:eapUser=\"http://"
               "www.microsoft.com/provisioning/EapUserPropertiesV1\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instanc"
               "e\" xmlns:baseEap=\"http://www.microsoft.com/provisioning/BaseEapUserPropertiesV1\" xmlns:MsPeap=\"http:/"
               "/www.microsoft.com/provisioning/MsPeapUserPropertiesV1\" xmlns:MsChapV2=\"http://www.microsoft.com/provis"
               "ioning/MsChapV2UserPropertiesV1\">    <baseEap:Eap>      <baseEap:Type>25</baseEap:Type>      <MsPeap:Eap"
               "Type>        <baseEap:Eap>          <baseEap:Type>26</baseEap:Type>          <MsChapV2:EapType>          "
               "  <MsChapV2:Username>%S</MsChapV2:Username>            <MsChapV2:Password>%S</MsChapV2:Password>         "
               "   <MsChapV2:LogonDomain>%S</MsChapV2:LogonDomain>          </MsChapV2:EapType>        </baseEap:Eap>    "
               "  </MsPeap:EapType>    </baseEap:Eap>  </Credentials></EapHostUserCredentials>",
              v18 + 12,
              v18 + 269,
              v18 + 526);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            11,
            WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids,
            (unsigned int)v20);
        }
        if ( (v20 & 0x1FFF0000) == 0x70000 )
          LastError = (unsigned __int16)v20;
        else
          LastError = v20;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids, LastError);
      }
    }
    RevertToSelf();
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids, LastError);
    }
  }
LABEL_48:
  if ( v6 )
    FreeWLMem(v6);
  return LastError;
}

```

## disassembly

```asm
0x1801ad384  mov     r11, rsp
0x1801ad387  mov     [r11+10h], rbx
0x1801ad38b  mov     [r11+18h], rsi
0x1801ad38f  mov     [r11+20h], r9d
0x1801ad393  push    rbp
0x1801ad394  push    rdi
0x1801ad395  push    r12
0x1801ad397  push    r14
0x1801ad399  push    r15
0x1801ad39b  mov     rbp, rsp
0x1801ad39e  sub     rsp, 70h
0x1801ad3a2  mov     rbx, rcx
0x1801ad3a5  mov     [rbp+arg_0], 0
0x1801ad3ad  lea     rax, [rcx+18h]
0x1801ad3b1  mov     [rbp+arg_18], 0
0x1801ad3b8  lea     rcx, [rbp+arg_0]
0x1801ad3bc  mov     r12d, 1
0x1801ad3c2  mov     [r11-50h], rcx
0x1801ad3c6  lea     r9, [rdx+8]; void *
0x1801ad3ca  lea     rcx, [rbp+arg_18]
0x1801ad3ce  mov     r15, r8
0x1801ad3d1  mov     r8, [rbx+2B0h]; unsigned int
0x1801ad3d8  mov     [r11-58h], rcx
0x1801ad3dc  lea     edx, [r12+1]; void *
0x1801ad3e1  lea     rcx, aMsmuserdata; "MSMUserData"
0x1801ad3e8  mov     [r11-60h], rcx
0x1801ad3ec  xor     ecx, ecx; this
0x1801ad3ee  mov     qword ptr [r11-68h], 0
0x1801ad3f6  mov     [r11-70h], rax
0x1801ad3fa  mov     [r11-78h], r12d
0x1801ad3fe  call    ?GetProfileUserData@profile@wlansvc@@YAKPEAXK0PEBU_GUID@@KPEBGPEAU_PM_PROFILE@@2PEAKPEAPEAE@Z; wlansvc::profile::GetProfileUserData(void *,ulong,void *,_GUID const *,ulong,ushort const *,_PM_PROFILE *,ushort const *,ulong *,uchar * *)
0x1801ad403  mov     r14, [rbp+arg_0]
0x1801ad407  mov     edi, eax
0x1801ad409  test    eax, eax
0x1801ad40b  jz      short loc_1801AD455
0x1801ad40d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad414  lea     rax, WPP_GLOBAL_Control
0x1801ad41b  cmp     rcx, rax
0x1801ad41e  jz      loc_1801AD6D9
0x1801ad424  cmp     [rcx+69h], r12b
0x1801ad428  jb      loc_1801AD6D9
0x1801ad42e  test    [rcx+6Ch], r12b
0x1801ad432  jz      loc_1801AD6D9
0x1801ad438  mov     rcx, [rcx+60h]
0x1801ad43c  lea     edx, [r12+9]
0x1801ad441  mov     r9d, edi
0x1801ad444  lea     r8, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids
0x1801ad44b  call    WPP_SF_d
0x1801ad450  jmp     loc_1801AD6D9
0x1801ad455  mov     ecx, [rbp+arg_18]
0x1801ad458  cmp     ecx, 18h
0x1801ad45b  jb      loc_1801AD6A5
0x1801ad461  mov     edx, [r14+14h]
0x1801ad465  cmp     edx, 18h
0x1801ad468  jb      loc_1801AD6A5
0x1801ad46e  cmp     ecx, edx
0x1801ad470  jb      loc_1801AD6A5
0x1801ad476  mov     r8d, edx
0x1801ad479  add     r8, r14
0x1801ad47c  jz      loc_1801AD6A5
0x1801ad482  sub     ecx, edx
0x1801ad484  cmp     ecx, 14h
0x1801ad487  jb      loc_1801AD6A5
0x1801ad48d  mov     edx, [r8+10h]
0x1801ad491  cmp     edx, 1Ch
0x1801ad494  jb      loc_1801AD6A5
0x1801ad49a  cmp     ecx, edx
0x1801ad49c  jb      loc_1801AD6A5
0x1801ad4a2  mov     r9d, edx
0x1801ad4a5  add     r9, r8
0x1801ad4a8  jz      loc_1801AD6A5
0x1801ad4ae  sub     ecx, edx
0x1801ad4b0  cmp     ecx, 20h ; ' '
0x1801ad4b3  jb      loc_1801AD6A5
0x1801ad4b9  mov     r8d, [r9+1Ch]
0x1801ad4bd  cmp     r8d, 20h ; ' '
0x1801ad4c1  jb      loc_1801AD6A5
0x1801ad4c7  cmp     ecx, r8d
0x1801ad4ca  jb      loc_1801AD6A5
0x1801ad4d0  mov     edx, r8d
0x1801ad4d3  add     rdx, r9
0x1801ad4d6  jz      loc_1801AD6A5
0x1801ad4dc  sub     ecx, r8d
0x1801ad4df  cmp     ecx, 3Ch ; '<'
0x1801ad4e2  jb      loc_1801AD6A5
0x1801ad4e8  cmp     byte ptr [rdx], 19h
0x1801ad4eb  jnz     loc_1801AD6A5
0x1801ad4f1  add     ecx, 0FFFFFFC4h
0x1801ad4f4  cmp     ecx, 14h
0x1801ad4f7  jb      loc_1801AD6A5
0x1801ad4fd  cmp     ecx, [rdx+40h]
0x1801ad500  jb      loc_1801AD6A5
0x1801ad506  cmp     dword ptr [rdx+44h], 1Ah
0x1801ad50a  jnz     loc_1801AD6A5
0x1801ad510  lea     rsi, [rdx+4Ch]
0x1801ad514  test    rsi, rsi
0x1801ad517  jz      loc_1801AD6A5
0x1801ad51d  mov     rcx, [rbx+2B0h]; hToken
0x1801ad524  lea     rax, [rsi+314h]
0x1801ad52b  mov     [rbp+pDataIn.pbData], rax
0x1801ad52f  xorps   xmm0, xmm0
0x1801ad532  mov     eax, [rsi+310h]
0x1801ad538  mov     [rbp+pDataIn.cbData], eax
0x1801ad53b  mov     dword ptr [rbp+pDataIn+4], 0
0x1801ad542  movups  xmmword ptr [rbp+var_10.cbData], xmm0
0x1801ad546  call    cs:__imp_ImpersonateLoggedOnUser
0x1801ad54c  test    eax, eax
0x1801ad54e  jz      loc_1801AD664
0x1801ad554  lea     rax, [rbp+var_10]
0x1801ad558  xor     r9d, r9d; pvReserved
0x1801ad55b  mov     [rsp+70h+pDataOut], rax; pDataOut
0x1801ad560  lea     rcx, [rbp+pDataIn]; pDataIn
0x1801ad564  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x1801ad569  xor     r8d, r8d; pOptionalEntropy
0x1801ad56c  xor     edx, edx; ppszDataDescr
0x1801ad56e  mov     [rsp+70h+pPromptStruct], 0; pPromptStruct
0x1801ad577  call    cs:__imp_CryptUnprotectData
0x1801ad57d  test    eax, eax
0x1801ad57f  jz      loc_1801AD61D
0x1801ad585  mov     r8d, [rbp+var_10.cbData]; Size
0x1801ad589  lea     rbx, [rsi+10Dh]
0x1801ad590  mov     rdx, [rbp+var_10.pbData]; Src
0x1801ad594  mov     rcx, rbx; void *
0x1801ad597  call    memcpy_0
0x1801ad59c  lea     rax, [rsi+20Eh]
0x1801ad5a3  mov     edx, 0FA0h; unsigned __int64
0x1801ad5a8  mov     qword ptr [rsp+70h+dwFlags], rax
0x1801ad5ad  lea     r9, [rsi+0Ch]
0x1801ad5b1  lea     r8, aXmlVersion10Ea; "<?xml version=\"1.0\"?><EapHostUserCred"...
0x1801ad5b8  mov     [rsp+70h+pPromptStruct], rbx
0x1801ad5bd  mov     rcx, r15; unsigned __int16 *
0x1801ad5c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ad5c5  mov     ebx, eax
0x1801ad5c7  test    eax, eax
0x1801ad5c9  jns     loc_1801AD65C
0x1801ad5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad5d6  lea     rax, WPP_GLOBAL_Control
0x1801ad5dd  cmp     rcx, rax
0x1801ad5e0  jz      short loc_1801AD606
0x1801ad5e2  cmp     [rcx+69h], r12b
0x1801ad5e6  jb      short loc_1801AD606
0x1801ad5e8  test    [rcx+6Ch], r12b
0x1801ad5ec  jz      short loc_1801AD606
0x1801ad5ee  mov     rcx, [rcx+60h]
0x1801ad5f2  lea     r8, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids
0x1801ad5f9  mov     edx, 0Bh
0x1801ad5fe  mov     r9d, ebx
0x1801ad601  call    WPP_SF_d
0x1801ad606  mov     eax, ebx
0x1801ad608  and     eax, 1FFF0000h
0x1801ad60d  cmp     eax, 70000h
0x1801ad612  jnz     short loc_1801AD619
0x1801ad614  movzx   edi, bx
0x1801ad617  jmp     short loc_1801AD65C
0x1801ad619  mov     edi, ebx
0x1801ad61b  jmp     short loc_1801AD65C
0x1801ad61d  call    cs:__imp_GetLastError
0x1801ad623  mov     edi, eax
0x1801ad625  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad62c  lea     rax, WPP_GLOBAL_Control
0x1801ad633  cmp     rcx, rax
0x1801ad636  jz      short loc_1801AD65C
0x1801ad638  cmp     [rcx+69h], r12b
0x1801ad63c  jb      short loc_1801AD65C
0x1801ad63e  test    [rcx+6Ch], r12b
0x1801ad642  jz      short loc_1801AD65C
0x1801ad644  mov     rcx, [rcx+60h]
0x1801ad648  lea     r8, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids
0x1801ad64f  mov     edx, 0Ch
0x1801ad654  mov     r9d, edi
0x1801ad657  call    WPP_SF_d
0x1801ad65c  call    cs:__imp_RevertToSelf
0x1801ad662  jmp     short loc_1801AD6DE
0x1801ad664  call    cs:__imp_GetLastError
0x1801ad66a  mov     edi, eax
0x1801ad66c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad673  lea     rax, WPP_GLOBAL_Control
0x1801ad67a  cmp     rcx, rax
0x1801ad67d  jz      short loc_1801AD6DE
0x1801ad67f  cmp     [rcx+69h], r12b
0x1801ad683  jb      short loc_1801AD6DE
0x1801ad685  test    [rcx+6Ch], r12b
0x1801ad689  jz      short loc_1801AD6DE
0x1801ad68b  mov     rcx, [rcx+60h]
0x1801ad68f  lea     r8, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids
0x1801ad696  mov     edx, 0Dh
0x1801ad69b  mov     r9d, edi
0x1801ad69e  call    WPP_SF_d
0x1801ad6a3  jmp     short loc_1801AD6DE
0x1801ad6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ad6ac  lea     rax, WPP_GLOBAL_Control
0x1801ad6b3  cmp     rcx, rax
0x1801ad6b6  jz      short loc_1801AD6D9
0x1801ad6b8  cmp     [rcx+69h], r12b
0x1801ad6bc  jb      short loc_1801AD6D9
0x1801ad6be  test    [rcx+6Ch], r12b
0x1801ad6c2  jz      short loc_1801AD6D9
0x1801ad6c4  mov     rcx, [rcx+60h]
0x1801ad6c8  lea     r8, WPP_7917bbf5782a35afc127b65b87eb6fc3_Traceguids
0x1801ad6cf  mov     edx, 0Eh
0x1801ad6d4  call    WPP_SF_
0x1801ad6d9  mov     edi, 7DBh
0x1801ad6de  test    r14, r14
0x1801ad6e1  jz      short loc_1801AD6EB
0x1801ad6e3  mov     rcx, r14
0x1801ad6e6  call    FreeWLMem
0x1801ad6eb  lea     r11, [rsp+70h+var_s0]
0x1801ad6f0  mov     eax, edi
0x1801ad6f2  mov     rbx, [r11+38h]
0x1801ad6f6  mov     rsi, [r11+40h]
0x1801ad6fa  mov     rsp, r11
0x1801ad6fd  pop     r15
0x1801ad6ff  pop     r14
0x1801ad701  pop     r12
0x1801ad703  pop     rdi
0x1801ad704  pop     rbp
0x1801ad705  retn
```
