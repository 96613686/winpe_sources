# IASService::get_AcctPorts(ushort * *)

- ea: `0x180032960`
- end: `0x180032a8a`
- name: `?get_AcctPorts@IASService@@UEAAJPEAPEAG@Z`
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
- `0x180032960`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180032989`
- `OLEAUT32!__imp_VariantInit` at `0x180032989`

## string_xrefs

- `0x1800329d7`: `GetRADIUSProtocol failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::get_AcctPorts(struct ISdo **this, unsigned __int16 **a2)
{
  int SdoProperty; // ebx
  int v6; // edx
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  VariantInit(&pvarg);
  if ( this[18] || (SdoProperty = IASService::GetRADIUSProtocol(this), SdoProperty >= 0) )
  {
    SdoProperty = GetSdoProperty(this[18], 0x403u, &pvarg);
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
    WppDbgPrint("GetSdoProperty(PROPERTY_RADIUS_ACCOUNTING_PORT) failed with 0x%x");
    v6 = 28;
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
    v6 = 27;
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
0x180032960  mov     [rsp+arg_0], rbx
0x180032965  mov     [rsp+arg_8], rsi
0x18003296a  push    rdi
0x18003296b  sub     rsp, 50h
0x18003296f  mov     rsi, rdx
0x180032972  mov     rdi, rcx
0x180032975  test    rdx, rdx
0x180032978  jnz     short loc_180032984
0x18003297a  mov     eax, 80004003h
0x18003297f  jmp     loc_180032A7A
0x180032984  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180032989  call    cs:__imp_VariantInit
0x18003298f  cmp     qword ptr [rdi+90h], 0
0x180032997  jnz     short loc_180032A0C
0x180032999  mov     rcx, rdi; this
0x18003299c  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x1800329a1  mov     ebx, eax
0x1800329a3  test    eax, eax
0x1800329a5  jns     short loc_180032A0C
0x1800329a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800329ae  lea     rcx, WPP_GLOBAL_Control
0x1800329b5  cmp     rax, rcx
0x1800329b8  jz      loc_180032A6E
0x1800329be  cmp     byte ptr [rax+19h], 2
0x1800329c2  jb      loc_180032A6E
0x1800329c8  test    dword ptr [rax+1Ch], 400h
0x1800329cf  jz      loc_180032A6E
0x1800329d5  mov     edx, ebx
0x1800329d7  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x1800329de  call    WppDbgPrint
0x1800329e3  mov     edx, 1Bh
0x1800329e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329ef  lea     r9, aNpssdo; "NPSSDO"
0x1800329f6  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800329fd  mov     [rsp+58h+var_38], ebx
0x180032a01  mov     rcx, [rcx+10h]
0x180032a05  call    WPP_SF_sd
0x180032a0a  jmp     short loc_180032A6E
0x180032a0c  mov     rcx, [rdi+90h]; struct ISdo *
0x180032a13  lea     r8, [rsp+58h+pvarg]; struct tagVARIANT *
0x180032a18  mov     edx, 403h; unsigned int
0x180032a1d  call    ?GetSdoProperty@@YAJPEAUISdo@@KPEAUtagVARIANT@@@Z; GetSdoProperty(ISdo *,ulong,tagVARIANT *)
0x180032a22  mov     ebx, eax
0x180032a24  test    eax, eax
0x180032a26  jns     short loc_180032A5F
0x180032a28  mov     rax, cs:WPP_GLOBAL_Control
0x180032a2f  lea     rcx, WPP_GLOBAL_Control
0x180032a36  cmp     rax, rcx
0x180032a39  jz      short loc_180032A6E
0x180032a3b  cmp     byte ptr [rax+19h], 2
0x180032a3f  jb      short loc_180032A6E
0x180032a41  test    dword ptr [rax+1Ch], 400h
0x180032a48  jz      short loc_180032A6E
0x180032a4a  mov     edx, ebx
0x180032a4c  lea     rcx, aGetsdoproperty_2; "GetSdoProperty(PROPERTY_RADIUS_ACCOUNTI"...
0x180032a53  call    WppDbgPrint
0x180032a58  mov     edx, 1Ch
0x180032a5d  jmp     short loc_1800329E8
0x180032a5f  mov     rax, qword ptr [rsp+58h+pvarg+8]
0x180032a64  mov     [rsi], rax
0x180032a67  xor     eax, eax
0x180032a69  mov     word ptr [rsp+58h+pvarg], ax
0x180032a6e  lea     rcx, [rsp+58h+pvarg]; this
0x180032a73  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180032a78  mov     eax, ebx
0x180032a7a  mov     rbx, [rsp+58h+arg_0]
0x180032a7f  mov     rsi, [rsp+58h+arg_8]
0x180032a84  add     rsp, 50h
0x180032a88  pop     rdi
0x180032a89  retn
```
