# SdpXmlLoad(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x180028988`
- end: `0x180028b2b`
- name: `?SdpXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bef0`

## callees

- `0x180026fa0`
- `0x180028988`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180028a1c`
- `ole32!CoCreateInstance` at `0x180028a1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a5c`
- `OLEAUT32!__imp_SysAllocString` at `0x180028a5c`
- `OLEAUT32!__imp_VariantInit` at `0x1800289c2`
- `OLEAUT32!__imp_VariantInit` at `0x1800289c2`
- `OLEAUT32!__imp_VariantClear` at `0x180028af9`
- `OLEAUT32!__imp_VariantClear` at `0x180028af9`

## string_xrefs

- `0x1800289dc`: `SdpXmlLoad`

## pseudocode

```c
__int64 __fastcall SdpXmlLoad(OLECHAR *psz, LPVOID *a2)
{
  unsigned int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  HRESULT v7; // eax
  int v8; // eax
  __int64 (__fastcall *v9)(LPVOID, __int128 *, __int16 *); // rax
  int v10; // eax
  LPVOID v11; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int16 v16; // [rsp+90h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+30h] BYREF

  v16 = -1;
  ppv = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !psz )
  {
    v4 = 528;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlLoad", v4, v5);
    goto LABEL_18;
  }
  if ( !a2 )
  {
    v4 = 529;
    goto LABEL_3;
  }
  v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 0x15u, &IID_IXMLDOMDocument2, &ppv);
  v6 = v7;
  if ( v7 < 0 )
  {
    v5 = v7;
    v4 = 536;
    goto LABEL_4;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  v6 = v8;
  if ( v8 < 0 )
  {
    v5 = v8;
    v4 = 539;
    goto LABEL_4;
  }
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
  {
    v6 = -2147024882;
    v4 = 542;
    v5 = -2147024882;
    goto LABEL_4;
  }
  pRecInfo = pvarg.pRecInfo;
  pvarg.vt = 8;
  v9 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)ppv + 464LL);
  v14 = *(_OWORD *)&pvarg.vt;
  v10 = v9(ppv, &v14, &v16);
  v6 = v10;
  if ( v10 < 0 )
  {
    v5 = v10;
    v4 = 547;
    goto LABEL_4;
  }
  if ( !v16 )
  {
    v6 = -2147467259;
    v4 = 548;
    v5 = -2147467259;
    goto LABEL_4;
  }
  v11 = ppv;
  *a2 = ppv;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 8LL))(v11);
LABEL_18:
  VariantClear(&pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v6;
}

```

## disassembly

```asm
0x180028988  mov     [rsp-18h+arg_8], rbx
0x18002898d  mov     [rsp-18h+arg_18], rsi
0x180028992  push    rbp
0x180028993  push    rdi
0x180028994  push    r14
0x180028996  mov     rbp, rsp
0x180028999  sub     rsp, 70h
0x18002899d  xor     eax, eax
0x18002899f  mov     rsi, rcx
0x1800289a2  mov     qword ptr [rbp+pvarg+10h], rax
0x1800289a6  lea     rcx, [rbp+pvarg]; pvarg
0x1800289aa  or      eax, 0FFFFFFFFh
0x1800289ad  xorps   xmm0, xmm0
0x1800289b0  xor     r14d, r14d
0x1800289b3  mov     [rbp+arg_0], ax
0x1800289b7  mov     rdi, rdx
0x1800289ba  mov     [rbp+arg_10], r14
0x1800289be  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800289c2  call    cs:__imp_VariantInit
0x1800289c8  test    rsi, rsi
0x1800289cb  jnz     short loc_1800289F2
0x1800289cd  mov     r8d, 210h; int
0x1800289d3  mov     r9d, 80070057h; int
0x1800289d9  mov     ebx, r9d
0x1800289dc  lea     rdx, aSdpxmlload; "SdpXmlLoad"
0x1800289e3  mov     ecx, 1; Level
0x1800289e8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800289ed  jmp     loc_180028AF5
0x1800289f2  test    rdi, rdi
0x1800289f5  jnz     short loc_1800289FF
0x1800289f7  mov     r8d, 211h
0x1800289fd  jmp     short loc_1800289D3
0x1800289ff  xor     edx, edx; pUnkOuter
0x180028a01  lea     rax, [rbp+arg_10]
0x180028a05  lea     r9, IID_IXMLDOMDocument2; riid
0x180028a0c  mov     [rsp+70h+ppv], rax; ppv
0x180028a11  lea     rcx, CLSID_DOMDocument60; rclsid
0x180028a18  lea     r8d, [rdx+15h]; dwClsContext
0x180028a1c  call    cs:__imp_CoCreateInstance
0x180028a22  mov     ebx, eax
0x180028a24  test    eax, eax
0x180028a26  jns     short loc_180028A33
0x180028a28  mov     r9d, eax
0x180028a2b  mov     r8d, 218h
0x180028a31  jmp     short loc_1800289DC
0x180028a33  mov     rcx, [rbp+arg_10]
0x180028a37  xor     edx, edx
0x180028a39  mov     rax, [rcx]
0x180028a3c  mov     rax, [rax+1F8h]
0x180028a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a48  mov     ebx, eax
0x180028a4a  test    eax, eax
0x180028a4c  jns     short loc_180028A59
0x180028a4e  mov     r9d, eax
0x180028a51  mov     r8d, 21Bh
0x180028a57  jmp     short loc_1800289DC
0x180028a59  mov     rcx, rsi; psz
0x180028a5c  call    cs:__imp_SysAllocString
0x180028a62  mov     qword ptr [rbp+pvarg+8], rax
0x180028a66  test    rax, rax
0x180028a69  jnz     short loc_180028A7E
0x180028a6b  mov     ebx, 8007000Eh
0x180028a70  mov     r8d, 21Eh
0x180028a76  mov     r9d, ebx
0x180028a79  jmp     loc_1800289DC
0x180028a7e  mov     rcx, [rbp+arg_10]
0x180028a82  lea     r8, [rbp+arg_0]
0x180028a86  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180028a8b  lea     rdx, [rbp+var_20]
0x180028a8f  mov     eax, 8
0x180028a94  movsd   [rbp+var_10], xmm1
0x180028a99  mov     word ptr [rbp+pvarg], ax
0x180028a9d  mov     rax, [rcx]
0x180028aa0  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180028aa4  mov     rax, [rax+1D0h]
0x180028aab  movaps  [rbp+var_20], xmm0
0x180028aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ab4  mov     ebx, eax
0x180028ab6  test    eax, eax
0x180028ab8  jns     short loc_180028AC8
0x180028aba  mov     r9d, eax
0x180028abd  mov     r8d, 223h
0x180028ac3  jmp     loc_1800289DC
0x180028ac8  cmp     [rbp+arg_0], r14w
0x180028acd  jnz     short loc_180028AE2
0x180028acf  mov     ebx, 80004005h
0x180028ad4  mov     r8d, 224h
0x180028ada  mov     r9d, ebx
0x180028add  jmp     loc_1800289DC
0x180028ae2  mov     rcx, [rbp+arg_10]
0x180028ae6  mov     [rdi], rcx
0x180028ae9  mov     rax, [rcx]
0x180028aec  mov     rax, [rax+8]
0x180028af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028af5  lea     rcx, [rbp+pvarg]; pvarg
0x180028af9  call    cs:__imp_VariantClear
0x180028aff  mov     rcx, [rbp+arg_10]
0x180028b03  test    rcx, rcx
0x180028b06  jz      short loc_180028B14
0x180028b08  mov     rax, [rcx]
0x180028b0b  mov     rax, [rax+10h]
0x180028b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b14  lea     r11, [rsp+70h+var_s0]
0x180028b19  mov     eax, ebx
0x180028b1b  mov     rbx, [r11+28h]
0x180028b1f  mov     rsi, [r11+38h]
0x180028b23  mov     rsp, r11
0x180028b26  pop     r14
0x180028b28  pop     rdi
0x180028b29  pop     rbp
0x180028b2a  retn
```
