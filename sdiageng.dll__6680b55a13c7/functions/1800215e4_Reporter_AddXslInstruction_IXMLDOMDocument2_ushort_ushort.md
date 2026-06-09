# Reporter::AddXslInstruction(IXMLDOMDocument2 *,ushort *,ushort *)

- ea: `0x1800215e4`
- end: `0x1800217a6`
- name: `?AddXslInstruction@Reporter@@AEAAJPEAUIXMLDOMDocument2@@PEAG1@Z`
- size: `450`
- prototype: `__int64 __fastcall(Reporter *__hidden this, struct IXMLDOMDocument2 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180021ec4`
- `0x180022174`

## callees

- `0x1800215e4`
- `0x180026fa0`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002162b`
- `OLEAUT32!__imp_SysAllocString` at `0x180021655`
- `OLEAUT32!__imp_SysAllocString` at `0x18002162b`
- `OLEAUT32!__imp_SysAllocString` at `0x180021655`
- `OLEAUT32!__imp_SysFreeString` at `0x18002177b`
- `OLEAUT32!__imp_SysFreeString` at `0x180021789`
- `OLEAUT32!__imp_SysFreeString` at `0x18002177b`
- `OLEAUT32!__imp_SysFreeString` at `0x180021789`
- `OLEAUT32!__imp_VariantInit` at `0x18002161e`
- `OLEAUT32!__imp_VariantInit` at `0x18002161e`
- `OLEAUT32!__imp_VariantClear` at `0x180021733`
- `OLEAUT32!__imp_VariantClear` at `0x180021733`

## string_xrefs

- `0x180021624`: `xml-stylesheet`

## pseudocode

```c
__int64 __fastcall Reporter::AddXslInstruction(
        Reporter *this,
        struct IXMLDOMDocument2 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  OLECHAR *v5; // r14
  unsigned int v6; // ebx
  OLECHAR *v7; // rsi
  int v8; // r9d
  int v9; // r8d
  int v10; // eax
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *insertBefore)(IXMLDOMDocument2 *, IXMLDOMNode *, VARIANT, IXMLDOMNode **); // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v17; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+38h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  v17 = 0;
  VariantInit(&pvarg);
  v5 = SysAllocString(L"xml-stylesheet");
  if ( v5 )
  {
    v7 = SysAllocString(L"type=\"text/xsl\" href=\"results.xsl\"");
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, OLECHAR *, __int64 *))a2->lpVtbl->createProcessingInstruction)(
            a2,
            v5,
            v7,
            &v17);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))a2->lpVtbl->get_documentElement)(a2, &v18);
      v6 = v10;
      if ( v10 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, ULONG *))v18)(v18, &IID_IUnknown, (ULONG *)&pvarg.cyVal);
        v6 = v10;
        if ( v10 >= 0 )
        {
          pvarg.vt = 13;
          lpVtbl = a2->lpVtbl;
          pRecInfo = pvarg.pRecInfo;
          insertBefore = lpVtbl->insertBefore;
          v15 = *(_OWORD *)&pvarg.vt;
          v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64, __int128 *, _QWORD))insertBefore)(
                  a2,
                  v17,
                  &v15,
                  0);
          v6 = v10;
          if ( v10 >= 0 )
            goto LABEL_13;
          v9 = 920;
        }
        else
        {
          v9 = 915;
        }
      }
      else
      {
        v9 = 912;
      }
    }
    else
    {
      v9 = 909;
    }
    v8 = v10;
  }
  else
  {
    v6 = -2147024882;
    v7 = 0;
    v8 = -2147024882;
    v9 = 898;
  }
  SdpDebugTrace(1u, L"Reporter::AddXslInstruction", v9, v8);
LABEL_13:
  VariantClear(&pvarg);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v5 )
    SysFreeString(v5);
  if ( v7 )
    SysFreeString(v7);
  return v6;
}

```

## disassembly

```asm
0x1800215e4  mov     rax, rsp
0x1800215e7  mov     [rax+8], rbx
0x1800215eb  mov     [rax+10h], rsi
0x1800215ef  mov     [rax+20h], r9
0x1800215f3  mov     [rax+18h], r8
0x1800215f7  push    rbp
0x1800215f8  push    rdi
0x1800215f9  push    r14
0x1800215fb  mov     rbp, rsp
0x1800215fe  sub     rsp, 70h
0x180021602  xor     eax, eax
0x180021604  lea     rcx, [rbp+pvarg]; pvarg
0x180021608  xorps   xmm0, xmm0
0x18002160b  mov     qword ptr [rbp+pvarg+10h], rax
0x18002160f  movups  xmmword ptr [rbp+pvarg], xmm0
0x180021613  mov     [rbp+arg_18], rax
0x180021617  mov     rdi, rdx
0x18002161a  mov     [rbp+arg_10], rax
0x18002161e  call    cs:__imp_VariantInit
0x180021624  lea     rcx, aXmlStylesheet; "xml-stylesheet"
0x18002162b  call    cs:__imp_SysAllocString
0x180021631  mov     r14, rax
0x180021634  test    rax, rax
0x180021637  jnz     short loc_18002164E
0x180021639  mov     ebx, 8007000Eh
0x18002163e  xor     esi, esi
0x180021640  mov     r9d, ebx
0x180021643  mov     r8d, 382h
0x180021649  jmp     loc_18002171E
0x18002164e  lea     rcx, aTypeTextXslHre; "type=\"text/xsl\" href=\"results.xsl\""
0x180021655  call    cs:__imp_SysAllocString
0x18002165b  mov     rcx, [rdi]
0x18002165e  lea     r9, [rbp+arg_10]
0x180021662  mov     rsi, rax
0x180021665  mov     rdx, r14
0x180021668  mov     r8, rsi
0x18002166b  mov     rax, [rcx+1A0h]
0x180021672  mov     rcx, rdi
0x180021675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002167a  mov     ebx, eax
0x18002167c  test    eax, eax
0x18002167e  jns     short loc_18002168B
0x180021680  mov     r8d, 38Dh
0x180021686  jmp     loc_18002171B
0x18002168b  mov     rax, [rdi]
0x18002168e  lea     rdx, [rbp+arg_18]
0x180021692  mov     rcx, rdi
0x180021695  mov     rax, [rax+168h]
0x18002169c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216a1  mov     ebx, eax
0x1800216a3  test    eax, eax
0x1800216a5  jns     short loc_1800216AF
0x1800216a7  mov     r8d, 390h
0x1800216ad  jmp     short loc_18002171B
0x1800216af  mov     rcx, [rbp+arg_18]
0x1800216b3  lea     r8, [rbp+pvarg+8]
0x1800216b7  lea     rdx, IID_IUnknown
0x1800216be  mov     rax, [rcx]
0x1800216c1  mov     rax, [rax]
0x1800216c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216c9  mov     ebx, eax
0x1800216cb  test    eax, eax
0x1800216cd  jns     short loc_1800216D7
0x1800216cf  mov     r8d, 393h
0x1800216d5  jmp     short loc_18002171B
0x1800216d7  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800216dc  lea     r8, [rbp+var_20]
0x1800216e0  mov     rdx, [rbp+arg_10]
0x1800216e4  mov     eax, 0Dh
0x1800216e9  mov     word ptr [rbp+pvarg], ax
0x1800216ed  xor     r9d, r9d
0x1800216f0  mov     rax, [rdi]
0x1800216f3  mov     rcx, rdi
0x1800216f6  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800216fa  movsd   [rbp+var_10], xmm1
0x1800216ff  mov     rax, [rax+90h]
0x180021706  movaps  [rbp+var_20], xmm0
0x18002170a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002170f  mov     ebx, eax
0x180021711  test    eax, eax
0x180021713  jns     short loc_18002172F
0x180021715  mov     r8d, 398h; int
0x18002171b  mov     r9d, eax; int
0x18002171e  lea     rdx, aReporterAddxsl; "Reporter::AddXslInstruction"
0x180021725  mov     ecx, 1; Level
0x18002172a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002172f  lea     rcx, [rbp+pvarg]; pvarg
0x180021733  call    cs:__imp_VariantClear
0x180021739  mov     rcx, [rbp+arg_18]
0x18002173d  test    rcx, rcx
0x180021740  jz      short loc_180021756
0x180021742  mov     rax, [rcx]
0x180021745  mov     rax, [rax+10h]
0x180021749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002174e  mov     [rbp+arg_18], 0
0x180021756  mov     rcx, [rbp+arg_10]
0x18002175a  test    rcx, rcx
0x18002175d  jz      short loc_180021773
0x18002175f  mov     rax, [rcx]
0x180021762  mov     rax, [rax+10h]
0x180021766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002176b  mov     [rbp+arg_10], 0
0x180021773  test    r14, r14
0x180021776  jz      short loc_180021781
0x180021778  mov     rcx, r14; bstrString
0x18002177b  call    cs:__imp_SysFreeString
0x180021781  test    rsi, rsi
0x180021784  jz      short loc_18002178F
0x180021786  mov     rcx, rsi; bstrString
0x180021789  call    cs:__imp_SysFreeString
0x18002178f  lea     r11, [rsp+70h+var_s0]
0x180021794  mov     eax, ebx
0x180021796  mov     rbx, [r11+20h]
0x18002179a  mov     rsi, [r11+28h]
0x18002179e  mov     rsp, r11
0x1800217a1  pop     r14
0x1800217a3  pop     rdi
0x1800217a4  pop     rbp
0x1800217a5  retn
```
