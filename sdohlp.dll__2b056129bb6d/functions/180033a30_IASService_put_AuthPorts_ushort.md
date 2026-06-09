# IASService::put_AuthPorts(ushort *)

- ea: `0x180033a30`
- end: `0x180033b6a`
- name: `?put_AuthPorts@IASService@@UEAAJPEAG@Z`
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
- `0x180033a30`
- `0x180042a80`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180033ab8`
- `OLEAUT32!__imp_SysAllocString` at `0x180033ab8`
- `OLEAUT32!__imp_VariantInit` at `0x180033a4a`
- `OLEAUT32!__imp_VariantInit` at `0x180033a4a`

## string_xrefs

- `0x180033a98`: `GetRADIUSProtocol failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASService::put_AuthPorts(IASService *this, OLECHAR *psz)
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
    RADIUSProtocol = PutSdoProperty(v7, 0x404u, &v10);
    if ( RADIUSProtocol < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("PutSdoProperty(PROPERTY_RADIUS_AUTHENTICATION_PORT) failed with 0x%x");
      v5 = 26;
      goto LABEL_12;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetRADIUSProtocol failed with 0x%x");
    v5 = 25;
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
0x180033a30  mov     [rsp+arg_0], rbx
0x180033a35  mov     [rsp+arg_8], rsi
0x180033a3a  push    rdi
0x180033a3b  sub     rsp, 70h
0x180033a3f  mov     rdi, rcx
0x180033a42  mov     rsi, rdx
0x180033a45  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180033a4a  call    cs:__imp_VariantInit
0x180033a50  cmp     qword ptr [rdi+90h], 0
0x180033a58  jnz     short loc_180033AAB
0x180033a5a  mov     rcx, rdi; this
0x180033a5d  call    ?GetRADIUSProtocol@IASService@@QEAAJXZ; IASService::GetRADIUSProtocol(void)
0x180033a62  mov     ebx, eax
0x180033a64  test    eax, eax
0x180033a66  jns     short loc_180033AAB
0x180033a68  mov     rax, cs:WPP_GLOBAL_Control
0x180033a6f  lea     rcx, WPP_GLOBAL_Control
0x180033a76  cmp     rax, rcx
0x180033a79  jz      loc_180033B4C
0x180033a7f  cmp     byte ptr [rax+19h], 2
0x180033a83  jb      loc_180033B4C
0x180033a89  test    dword ptr [rax+1Ch], 400h
0x180033a90  jz      loc_180033B4C
0x180033a96  mov     edx, ebx
0x180033a98  lea     rcx, aGetradiusproto; "GetRADIUSProtocol failed with 0x%x"
0x180033a9f  call    WppDbgPrint
0x180033aa4  mov     edx, 19h
0x180033aa9  jmp     short loc_180033B2A
0x180033aab  mov     eax, 8
0x180033ab0  mov     rcx, rsi; psz
0x180033ab3  mov     word ptr [rsp+78h+pvarg], ax
0x180033ab8  call    cs:__imp_SysAllocString
0x180033abe  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x180033ac4  lea     r8, [rsp+78h+var_28]; struct tagVARIANT
0x180033ac9  mov     rcx, [rdi+90h]; struct ISdo *
0x180033ad0  mov     edx, 404h; unsigned int
0x180033ad5  mov     qword ptr [rsp+78h+pvarg+8], rax
0x180033ada  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x180033adf  movsd   qword ptr [rsp+78h+var_28+10h], xmm1
0x180033ae5  movaps  xmmword ptr [rsp+78h+var_28], xmm0
0x180033aea  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x180033aef  mov     ebx, eax
0x180033af1  test    eax, eax
0x180033af3  jns     short loc_180033B4C
0x180033af5  mov     rax, cs:WPP_GLOBAL_Control
0x180033afc  lea     rcx, WPP_GLOBAL_Control
0x180033b03  cmp     rax, rcx
0x180033b06  jz      short loc_180033B4C
0x180033b08  cmp     byte ptr [rax+19h], 2
0x180033b0c  jb      short loc_180033B4C
0x180033b0e  test    dword ptr [rax+1Ch], 400h
0x180033b15  jz      short loc_180033B4C
0x180033b17  mov     edx, ebx
0x180033b19  lea     rcx, aPutsdoproperty_2; "PutSdoProperty(PROPERTY_RADIUS_AUTHENTI"...
0x180033b20  call    WppDbgPrint
0x180033b25  mov     edx, 1Ah
0x180033b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b31  lea     r9, aNpssdo; "NPSSDO"
0x180033b38  lea     r8, WPP_04df665a9b3b399515f1538d3fd7f441_Traceguids
0x180033b3f  mov     [rsp+78h+var_58], ebx
0x180033b43  mov     rcx, [rcx+10h]
0x180033b47  call    WPP_SF_sd
0x180033b4c  lea     rcx, [rsp+78h+pvarg]; this
0x180033b51  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180033b56  lea     r11, [rsp+78h+var_8]
0x180033b5b  mov     eax, ebx
0x180033b5d  mov     rbx, [r11+10h]
0x180033b61  mov     rsi, [r11+18h]
0x180033b65  mov     rsp, r11
0x180033b68  pop     rdi
0x180033b69  retn
```
