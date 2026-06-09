# IASService::get_AuthPorts(ushort * *)

- ea: `0x180032a90`
- end: `0x180032bba`
- name: `?get_AuthPorts@IASService@@UEAAJPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(IASService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180027ee4`
- `0x18002cd00`
- `0x18002f240`
- `0x18003277c`
- `0x180032a90`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180032ab9`
- `OLEAUT32!__imp_VariantInit` at `0x180032ab9`

## string_xrefs

- `0x180032b07`: `GetRADIUSProtocol failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_AuthPorts(struct ISdo **this, unsigned __int16 **a2)
{
  int SdoProperty; // ebx
  int v6; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  VariantInit(&pvarg);
  if ( this[18] || (SdoProperty = IASService::GetRADIUSProtocol(this), SdoProperty >= 0) )
  {
    SdoProperty = GetSdoProperty(this[18], 0x404u, &pvarg);
    if ( SdoProperty >= 0 )
    {
      *a2 = pvarg.bstrVal;
      pvarg.vt = 0;
      goto LABEL_16;
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_16;
    }
    WppDbgPrint("GetSdoProperty(PROPERTY_RADIUS_AUTHENTICATION_PORT) failed with 0x%x");
    v6 = 24;
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_16;
    }
    WppDbgPrint("GetRADIUSProtocol failed with 0x%x");
    v6 = 23;
  }
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v6,
    (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
    (unsigned int)"NPSSDO",
    SdoProperty);
LABEL_16:
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)SdoProperty;
}

```

## disassembly

```asm
0x180032a90  mov     [rsp+arg_0], rbx
0x180032a95  mov     [rsp+arg_8], rsi
0x180032a9a  push    rdi
0x180032a9b  sub     rsp, 50h
0x180032a9f  mov     rsi, rdx
0x180032aa2  mov     rdi, rcx
0x180032aa5  test    rdx, rdx
0x180032aa8  jnz     short loc_180032AB4
0x180032aaa  mov     eax, 80004003h
0x180032aaf  jmp     loc_180032BAA
0x180032ab4  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180032ab9  call    cs:__imp_VariantInit
0x180032abf  cmp     qword ptr [rdi+90h], 0
0x180032ac7  jnz     short loc_180032B3C
0x180032ac9  mov     rcx, rdi; this
0x180032acc  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x180032ad1  mov     ebx, eax
0x180032ad3  test    eax, eax
0x180032ad5  jns     short loc_180032B3C
0x180032ad7  mov     rax, cs:WPP_GLOBAL_Control
0x180032ade  lea     rcx, WPP_GLOBAL_Control
0x180032ae5  cmp     rax, rcx
0x180032ae8  jz      loc_180032B9E
0x180032aee  cmp     byte ptr [rax+19h], 2
0x180032af2  jb      loc_180032B9E
0x180032af8  test    dword ptr [rax+1Ch], 400h
0x180032aff  jz      loc_180032B9E
0x180032b05  mov     edx, ebx
0x180032b07  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x180032b0e  call    WppDbgPrint
0x180032b13  mov     edx, 17h
0x180032b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b1f  lea     r9, aNpssdo; "NPSSDO"
0x180032b26  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180032b2d  mov     [rsp+58h+var_38], ebx
0x180032b31  mov     rcx, [rcx+10h]
0x180032b35  call    WPP_SF_sd
0x180032b3a  jmp     short loc_180032B9E
0x180032b3c  mov     rcx, [rdi+90h]; struct ISdo *
0x180032b43  lea     r8, [rsp+58h+pvarg]; struct tagVARIANT *
0x180032b48  mov     edx, 404h; unsigned int
0x180032b4d  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x180032b52  mov     ebx, eax
0x180032b54  test    eax, eax
0x180032b56  jns     short loc_180032B8F
0x180032b58  mov     rax, cs:WPP_GLOBAL_Control
0x180032b5f  lea     rcx, WPP_GLOBAL_Control
0x180032b66  cmp     rax, rcx
0x180032b69  jz      short loc_180032B9E
0x180032b6b  cmp     byte ptr [rax+19h], 2
0x180032b6f  jb      short loc_180032B9E
0x180032b71  test    dword ptr [rax+1Ch], 400h
0x180032b78  jz      short loc_180032B9E
0x180032b7a  mov     edx, ebx
0x180032b7c  lea     rcx, aGetsdoproperty_4; "GetSdoProperty(PROPERTY_RADIUS_AUTHENTI"...
0x180032b83  call    WppDbgPrint
0x180032b88  mov     edx, 18h
0x180032b8d  jmp     short loc_180032B18
0x180032b8f  mov     rax, qword ptr [rsp+58h+pvarg+8]
0x180032b94  mov     [rsi], rax
0x180032b97  xor     eax, eax
0x180032b99  mov     word ptr [rsp+58h+pvarg], ax
0x180032b9e  lea     rcx, [rsp+58h+pvarg]; this
0x180032ba3  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180032ba8  mov     eax, ebx
0x180032baa  mov     rbx, [rsp+58h+arg_0]
0x180032baf  mov     rsi, [rsp+58h+arg_8]
0x180032bb4  add     rsp, 50h
0x180032bb8  pop     rdi
0x180032bb9  retn
```
