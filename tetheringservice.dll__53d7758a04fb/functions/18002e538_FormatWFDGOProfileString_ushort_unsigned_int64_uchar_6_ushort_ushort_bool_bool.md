# FormatWFDGOProfileString(ushort *,unsigned __int64,uchar (*)[6],ushort *,ushort *,bool,bool)

- ea: `0x18002e538`
- end: `0x18002e8d0`
- name: `?FormatWFDGOProfileString@@YAJPEAG_KPEAY05E00_N3@Z`
- size: `920`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int8 (*)[6], unsigned __int16 *, wchar_t *Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800110d4`

## callees

- `0x180003088`
- `0x1800094bc`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002e1ec`
- `0x18002e538`
- `0x18002eb90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e865`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e882`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e865`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e882`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002e653`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002e653`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e612`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002e612`

## string_xrefs

- `0x18002e82c`: `SecurityKey`
- `0x18002e765`: `<?xml version="1.0" encoding="utf-8"?><WFDProfile xmlns="http://www.microsoft.com/networking/WiFiDirect/profile/v1">  <groupName>WindowsPhoneSoftAPGroup</groupName>  <groupID>    <deviceAddress>%02x:%02x:%02x:%02x:%02x:%02x</deviceAddress>    <SSID>%ws</SSID>  </groupID>  <persistent>true</persistent>  <localSettings>    <role>GroupOwner</role>    <deviceAddress>%02x:%02x:%02x:%02x:%02x:%02x</deviceAddress>  </localSettings>  <security>   <authentication>%ws</authentication>   <encryption>AES</e`

## pseudocode

```c
__int64 __fastcall FormatWFDGOProfileString(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int8 (*a3)[6],
        unsigned __int16 *a4,
        wchar_t *Source)
{
  TetheringServiceTelemetry *v8; // rcx
  int v9; // ebx
  void **p_Block; // r13
  const wchar_t *v11; // rsi
  __int64 v12; // rdi
  size_t v13; // rax
  int v14; // edx
  int v15; // r8d
  int v16; // eax
  int v17; // eax
  size_t v18; // rdi
  void *v19; // rax
  unsigned __int16 *v20; // rbp
  int v21; // eax
  unsigned int v22; // ebx
  const wchar_t *v23; // r9
  void *Block; // [rsp+A0h] [rbp-48h] BYREF
  void *v26; // [rsp+A8h] [rbp-40h] BYREF
  int v27[4]; // [rsp+B0h] [rbp-38h]
  int v29; // [rsp+F8h] [rbp+10h]

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  Block = 0;
  v26 = 0;
  if ( !a1 || !a3 || !a4 || !Source )
    goto LABEL_34;
  v9 = 0;
  while ( 1 )
  {
    p_Block = &v26;
    v11 = a4;
    if ( v9 )
      v11 = Source;
    else
      p_Block = &Block;
    v12 = v9 != 0 ? 65LL : 33LL;
    v13 = wcsnlen(v11, v12);
    *(_QWORD *)v27 = v13;
    if ( v13 == v12 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = L"SSID";
        if ( v9 )
          v23 = L"SecurityKey";
        WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, (_DWORD)v23, v12);
        v8 = WPP_GLOBAL_Control;
      }
LABEL_34:
      v22 = -2147024809;
      goto LABEL_35;
    }
    v16 = ATL::EscapeXML(v11, v13, 0, 0);
    if ( !v16 )
      goto LABEL_27;
    v17 = v16 + 1;
    v18 = 2LL * v17;
    v29 = v17;
    v19 = malloc(v18);
    *p_Block = v19;
    v20 = (unsigned __int16 *)v19;
    if ( !v19 )
      break;
    memset_0(v19, 0, v18);
    if ( !(unsigned int)ATL::EscapeXML(v11, v27[0], v20, v29) )
      goto LABEL_27;
    if ( ++v9 >= 2 )
    {
      if ( Block && v26 )
      {
        v21 = StringCchPrintfW(
                a1,
                0x800u,
                L"<?xml version=\"1.0\" encoding=\"utf-8\"?><WFDProfile xmlns=\"http://www.microsoft.com/networking/WiFiDi"
                 "rect/profile/v1\">  <groupName>WindowsPhoneSoftAPGroup</groupName>  <groupID>    <deviceAddress>%02x:%0"
                 "2x:%02x:%02x:%02x:%02x</deviceAddress>    <SSID>%ws</SSID>  </groupID>  <persistent>true</persistent>  "
                 "<localSettings>    <role>GroupOwner</role>    <deviceAddress>%02x:%02x:%02x:%02x:%02x:%02x</deviceAddre"
                 "ss>  </localSettings>  <security>   <authentication>%ws</authentication>   <encryption>AES</encryption>"
                 "   <transitionMode>%ws</transitionMode>    <groupKey>      <keyType>passPhrase</keyType>      <protecte"
                 "d>false</protected>      <keyMaterial>%ws</keyMaterial>    </groupKey>  </security></WFDProfile>");
        v22 = v21;
        if ( v21 < 0 )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              &WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids,
              (unsigned int)v21);
LABEL_23:
            v8 = WPP_GLOBAL_Control;
            goto LABEL_35;
          }
          goto LABEL_35;
        }
      }
      else
      {
LABEL_27:
        v22 = -2147467259;
      }
      v8 = WPP_GLOBAL_Control;
      goto LABEL_35;
    }
  }
  v22 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids);
    goto LABEL_23;
  }
LABEL_35:
  if ( Block )
  {
    free(Block);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v26 )
  {
    free(v26);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v8 + 2), 14, &WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids, v22);
  return v22;
}

```

## disassembly

```asm
0x18002e538  mov     rax, rsp
0x18002e53b  mov     [rax+18h], rbx
0x18002e53f  mov     [rax+20h], rbp
0x18002e543  mov     [rax+10h], rdx
0x18002e547  mov     [rax+8], rcx
0x18002e54b  push    rsi
0x18002e54c  push    rdi
0x18002e54d  push    r12
0x18002e54f  push    r13
0x18002e551  push    r14
0x18002e553  sub     rsp, 0C0h
0x18002e55a  mov     r12, r9
0x18002e55d  mov     r14, r8
0x18002e560  mov     rbx, rcx
0x18002e563  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e56a  lea     rbp, WPP_GLOBAL_Control
0x18002e571  cmp     rcx, rbp
0x18002e574  jz      short loc_18002E598
0x18002e576  test    byte ptr [rcx+1Ch], 8
0x18002e57a  jz      short loc_18002E598
0x18002e57c  mov     rcx, [rcx+10h]
0x18002e580  lea     r8, WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids
0x18002e587  mov     edx, 0Ah
0x18002e58c  call    WPP_SF_
0x18002e591  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e598  mov     [rsp+0E8h+Block], 0
0x18002e5a4  mov     [rsp+0E8h+var_40], 0
0x18002e5b0  test    rbx, rbx
0x18002e5b3  jz      loc_18002E850
0x18002e5b9  test    r14, r14
0x18002e5bc  jz      loc_18002E850
0x18002e5c2  test    r12, r12
0x18002e5c5  jz      loc_18002E850
0x18002e5cb  cmp     [rsp+0E8h+Source], 0
0x18002e5d4  jz      loc_18002E850
0x18002e5da  xor     ebx, ebx
0x18002e5dc  test    ebx, ebx
0x18002e5de  lea     rax, [rsp+0E8h+Block]
0x18002e5e6  lea     r13, [rsp+0E8h+var_40]
0x18002e5ee  mov     rsi, r12
0x18002e5f1  cmovnz  rsi, [rsp+0E8h+Source]
0x18002e5fa  cmovz   r13, rax
0x18002e5fe  mov     eax, ebx
0x18002e600  mov     rcx, rsi; Source
0x18002e603  neg     eax
0x18002e605  sbb     rdi, rdi
0x18002e608  and     edi, 20h
0x18002e60b  add     rdi, 21h ; '!'
0x18002e60f  mov     rdx, rdi; MaxCount
0x18002e612  call    cs:__imp_wcsnlen
0x18002e618  mov     qword ptr [rsp+0E8h+var_38], rax
0x18002e620  cmp     rax, rdi
0x18002e623  jz      loc_18002E80F
0x18002e629  xor     r9d, r9d; int
0x18002e62c  xor     r8d, r8d; unsigned __int16 *
0x18002e62f  mov     edx, eax; int
0x18002e631  mov     rcx, rsi; unsigned __int16 *
0x18002e634  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x18002e639  test    eax, eax
0x18002e63b  jz      loc_18002E7FA
0x18002e641  inc     eax
0x18002e643  movsxd  rdi, eax
0x18002e646  add     rdi, rdi
0x18002e649  mov     [rsp+0E8h+arg_8], eax
0x18002e650  mov     rcx, rdi; Size
0x18002e653  call    cs:__imp_malloc
0x18002e659  mov     [r13+0], rax
0x18002e65d  mov     rbp, rax
0x18002e660  test    rax, rax
0x18002e663  jz      loc_18002E7CA
0x18002e669  mov     r8, rdi; Size
0x18002e66c  xor     edx, edx; Val
0x18002e66e  mov     rcx, rax; void *
0x18002e671  call    memset_0
0x18002e676  mov     r9d, [rsp+0E8h+arg_8]; int
0x18002e67e  mov     r8, rbp; unsigned __int16 *
0x18002e681  mov     edx, [rsp+0E8h+var_38]; int
0x18002e688  mov     rcx, rsi; unsigned __int16 *
0x18002e68b  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x18002e690  test    eax, eax
0x18002e692  jz      loc_18002E7FA
0x18002e698  inc     ebx
0x18002e69a  cmp     ebx, 2
0x18002e69d  jl      loc_18002E5DC
0x18002e6a3  mov     rsi, [rsp+0E8h+Block]
0x18002e6ab  test    rsi, rsi
0x18002e6ae  jz      loc_18002E7FA
0x18002e6b4  mov     rdi, [rsp+0E8h+var_40]
0x18002e6bc  test    rdi, rdi
0x18002e6bf  jz      loc_18002E7FA
0x18002e6c5  movzx   edx, byte ptr [r14+5]
0x18002e6ca  lea     rax, aFalse_0; "false"
0x18002e6d1  movzx   r8d, byte ptr [r14+4]
0x18002e6d6  lea     rcx, aTrue; "true"
0x18002e6dd  movzx   r10d, byte ptr [r14+3]
0x18002e6e2  lea     rbp, aWpa2psk; "WPA2PSK"
0x18002e6e9  movzx   r11d, byte ptr [r14+2]
0x18002e6ee  movzx   ebx, byte ptr [r14+1]
0x18002e6f3  cmp     [rsp+0E8h+arg_30], 0
0x18002e6fb  movzx   r9d, byte ptr [r14]
0x18002e6ff  mov     [rsp+0E8h+var_58], rdi
0x18002e707  cmovz   rcx, rax
0x18002e70b  cmp     [rsp+0E8h+arg_28], 0
0x18002e713  lea     rax, aWpa3sae; "WPA3SAE"
0x18002e71a  mov     [rsp+0E8h+var_60], rcx
0x18002e722  mov     rcx, [rsp+0E8h+arg_0]; unsigned __int16 *
0x18002e72a  cmovz   rax, rbp
0x18002e72e  mov     [rsp+0E8h+var_68], rax
0x18002e736  mov     [rsp+0E8h+var_70], edx
0x18002e73a  mov     [rsp+0E8h+var_78], r8d
0x18002e73f  mov     [rsp+0E8h+var_80], r10d
0x18002e744  mov     [rsp+0E8h+var_88], r11d
0x18002e749  mov     [rsp+0E8h+var_90], ebx
0x18002e74d  mov     [rsp+0E8h+var_98], r9d
0x18002e752  mov     [rsp+0E8h+var_A0], rsi
0x18002e757  mov     [rsp+0E8h+var_A8], edx
0x18002e75b  mov     edx, 800h; unsigned __int64
0x18002e760  mov     [rsp+0E8h+var_B0], r8d
0x18002e765  lea     r8, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18002e76c  mov     [rsp+0E8h+var_B8], r10d
0x18002e771  mov     [rsp+0E8h+var_C0], r11d
0x18002e776  mov     [rsp+0E8h+var_C8], ebx
0x18002e77a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e77f  mov     ebx, eax
0x18002e781  test    eax, eax
0x18002e783  jns     short loc_18002E7FF
0x18002e785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e78c  lea     rbp, WPP_GLOBAL_Control
0x18002e793  cmp     rcx, rbp
0x18002e796  jz      loc_18002E855
0x18002e79c  test    byte ptr [rcx+1Ch], 1
0x18002e7a0  jz      loc_18002E855
0x18002e7a6  mov     rcx, [rcx+10h]
0x18002e7aa  lea     r8, WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids
0x18002e7b1  mov     edx, 0Dh
0x18002e7b6  mov     r9d, eax
0x18002e7b9  call    WPP_SF_d
0x18002e7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7c5  jmp     loc_18002E855
0x18002e7ca  xor     ebx, ebx
0x18002e7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e7d3  lea     rbp, WPP_GLOBAL_Control
0x18002e7da  cmp     rcx, rbp
0x18002e7dd  jz      short loc_18002E855
0x18002e7df  test    byte ptr [rcx+1Ch], 1
0x18002e7e3  jz      short loc_18002E855
0x18002e7e5  mov     rcx, [rcx+10h]
0x18002e7e9  lea     edx, [rbx+0Ch]
0x18002e7ec  lea     r8, WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids
0x18002e7f3  call    WPP_SF_
0x18002e7f8  jmp     short loc_18002E7BE
0x18002e7fa  mov     ebx, 80004005h
0x18002e7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e806  lea     rbp, WPP_GLOBAL_Control
0x18002e80d  jmp     short loc_18002E855
0x18002e80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e816  lea     rbp, WPP_GLOBAL_Control
0x18002e81d  cmp     rcx, rbp
0x18002e820  jz      short loc_18002E850
0x18002e822  test    byte ptr [rcx+1Ch], 1
0x18002e826  jz      short loc_18002E850
0x18002e828  mov     rcx, [rcx+10h]
0x18002e82c  lea     rax, aSecuritykey; "SecurityKey"
0x18002e833  test    ebx, ebx
0x18002e835  mov     [rsp+0E8h+var_C8], edi
0x18002e839  lea     r9, ValueName; "SSID"
0x18002e840  cmovnz  r9, rax
0x18002e844  call    WPP_SF_SL
0x18002e849  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e850  mov     ebx, 80070057h
0x18002e855  mov     rsi, [rsp+0E8h+Block]
0x18002e85d  test    rsi, rsi
0x18002e860  jz      short loc_18002E872
0x18002e862  mov     rcx, rsi; Block
0x18002e865  call    cs:__imp_free
0x18002e86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e872  mov     rdi, [rsp+0E8h+var_40]
0x18002e87a  test    rdi, rdi
0x18002e87d  jz      short loc_18002E88F
0x18002e87f  mov     rcx, rdi; Block
0x18002e882  call    cs:__imp_free
0x18002e888  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e88f  cmp     rcx, rbp
0x18002e892  jz      short loc_18002E8B2
0x18002e894  test    byte ptr [rcx+1Ch], 8
0x18002e898  jz      short loc_18002E8B2
0x18002e89a  mov     rcx, [rcx+10h]
0x18002e89e  lea     r8, WPP_691d9bcac5de33e33e7d08030c7960cc_Traceguids
0x18002e8a5  mov     edx, 0Eh
0x18002e8aa  mov     r9d, ebx
0x18002e8ad  call    WPP_SF_d
0x18002e8b2  lea     r11, [rsp+0E8h+var_28]
0x18002e8ba  mov     eax, ebx
0x18002e8bc  mov     rbx, [r11+40h]
0x18002e8c0  mov     rbp, [r11+48h]
0x18002e8c4  mov     rsp, r11
0x18002e8c7  pop     r14
0x18002e8c9  pop     r13
0x18002e8cb  pop     r12
0x18002e8cd  pop     rdi
0x18002e8ce  pop     rsi
0x18002e8cf  retn
```
