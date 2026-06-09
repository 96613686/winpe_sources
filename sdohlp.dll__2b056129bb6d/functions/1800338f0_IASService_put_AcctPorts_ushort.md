# IASService::put_AcctPorts(ushort *)

- ea: `0x1800338f0`
- end: `0x180033a2a`
- name: `?put_AcctPorts@IASService@@UEAAJPEAG@Z`
- size: `314`
- prototype: `__int64 __fastcall(IASService *__hidden this, OLECHAR *psz)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180029ef4`
- `0x18002cd00`
- `0x18002f240`
- `0x18003277c`
- `0x1800338f0`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033978`
- `OLEAUT32!__imp_SysAllocString` at `0x180033978`
- `OLEAUT32!__imp_VariantInit` at `0x18003390a`
- `OLEAUT32!__imp_VariantInit` at `0x18003390a`

## string_xrefs

- `0x180033958`: `GetRADIUSProtocol failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::put_AcctPorts(IASService *this, OLECHAR *psz)
{
  int RADIUSProtocol; // ebx
  int v5; // edx
  BSTR v6; // rax
  struct ISdo *v7; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  struct tagVARIANT v10; // [rsp+50h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( *((_QWORD *)this + 18)
    || (RADIUSProtocol = IASService::GetRADIUSProtocol((struct ISdo **)this), RADIUSProtocol >= 0) )
  {
    pvarg.vt = 8;
    v6 = SysAllocString(psz);
    v7 = (struct ISdo *)*((_QWORD *)this + 18);
    pvarg.llVal = (LONGLONG)v6;
    v10 = pvarg;
    RADIUSProtocol = PutSdoProperty(v7, 0x403u, &v10);
    if ( RADIUSProtocol < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("PutSdoProperty(PROPERTY_RADIUS_ACCOUNTING_PORT) failed with 0x%x");
      v5 = 30;
      goto LABEL_12;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetRADIUSProtocol failed with 0x%x");
    v5 = 29;
LABEL_12:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids,
      (unsigned int)"NPSSDO",
      RADIUSProtocol);
  }
  _variant_t::~_variant_t((_variant_t *)&pvarg);
  return (unsigned int)RADIUSProtocol;
}

```

## disassembly

```asm
0x1800338f0  mov     [rsp+arg_0], rbx
0x1800338f5  mov     [rsp+arg_8], rsi
0x1800338fa  push    rdi
0x1800338fb  sub     rsp, 70h
0x1800338ff  mov     rdi, rcx
0x180033902  mov     rsi, rdx
0x180033905  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18003390a  call    cs:__imp_VariantInit
0x180033910  cmp     qword ptr [rdi+90h], 0
0x180033918  jnz     short loc_18003396B
0x18003391a  mov     rcx, rdi; this
0x18003391d  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x180033922  mov     ebx, eax
0x180033924  test    eax, eax
0x180033926  jns     short loc_18003396B
0x180033928  mov     rax, cs:WPP_GLOBAL_Control
0x18003392f  lea     rcx, WPP_GLOBAL_Control
0x180033936  cmp     rax, rcx
0x180033939  jz      loc_180033A0C
0x18003393f  cmp     byte ptr [rax+19h], 2
0x180033943  jb      loc_180033A0C
0x180033949  test    dword ptr [rax+1Ch], 400h
0x180033950  jz      loc_180033A0C
0x180033956  mov     edx, ebx
0x180033958  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x18003395f  call    WppDbgPrint
0x180033964  mov     edx, 1Dh
0x180033969  jmp     short loc_1800339EA
0x18003396b  mov     eax, 8
0x180033970  mov     rcx, rsi; psz
0x180033973  mov     word ptr [rsp+78h+pvarg], ax
0x180033978  call    cs:__imp_SysAllocString
0x18003397e  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x180033984  lea     r8, [rsp+78h+var_28]; struct tagVARIANT
0x180033989  mov     rcx, [rdi+90h]; struct ISdo *
0x180033990  mov     edx, 403h; unsigned int
0x180033995  mov     qword ptr [rsp+78h+pvarg+8], rax
0x18003399a  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x18003399f  movsd   qword ptr [rsp+78h+var_28+10h], xmm1
0x1800339a5  movaps  xmmword ptr [rsp+78h+var_28], xmm0
0x1800339aa  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x1800339af  mov     ebx, eax
0x1800339b1  test    eax, eax
0x1800339b3  jns     short loc_180033A0C
0x1800339b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800339bc  lea     rcx, WPP_GLOBAL_Control
0x1800339c3  cmp     rax, rcx
0x1800339c6  jz      short loc_180033A0C
0x1800339c8  cmp     byte ptr [rax+19h], 2
0x1800339cc  jb      short loc_180033A0C
0x1800339ce  test    dword ptr [rax+1Ch], 400h
0x1800339d5  jz      short loc_180033A0C
0x1800339d7  mov     edx, ebx
0x1800339d9  lea     rcx, aPutsdoproperty_0; "PutSdoProperty(PROPERTY_RADIUS_ACCOUNTI"...
0x1800339e0  call    WppDbgPrint
0x1800339e5  mov     edx, 1Eh
0x1800339ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339f1  lea     r9, aNpssdo; "NPSSDO"
0x1800339f8  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x1800339ff  mov     [rsp+78h+var_58], ebx
0x180033a03  mov     rcx, [rcx+10h]
0x180033a07  call    WPP_SF_sd
0x180033a0c  lea     rcx, [rsp+78h+pvarg]; this
0x180033a11  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033a16  lea     r11, [rsp+78h+var_8]
0x180033a1b  mov     eax, ebx
0x180033a1d  mov     rbx, [r11+10h]
0x180033a21  mov     rsi, [r11+18h]
0x180033a25  mov     rsp, r11
0x180033a28  pop     rdi
0x180033a29  retn
```
