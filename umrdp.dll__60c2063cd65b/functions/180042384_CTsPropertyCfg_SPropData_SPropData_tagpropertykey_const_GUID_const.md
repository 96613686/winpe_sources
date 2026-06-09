# CTsPropertyCfg::SPropData::SPropData(_tagpropertykey const &,_GUID const &)

- ea: `0x180042384`
- end: `0x180042456`
- name: `??0SPropData@CTsPropertyCfg@@QEAA@AEBU_tagpropertykey@@AEBU_GUID@@@Z`
- size: `210`
- prototype: `_QWORD(CTsPropertyCfg::SPropData *__hidden this, const struct _tagpropertykey *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042a10`

## callees

- `0x18000b8f8`
- `0x18000bd04`
- `0x18000f79c`
- `0x180042384`
- `0x180042960`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x1800423df`
- `PROPSYS!InitPropVariantFromCLSID` at `0x1800423df`

## pseudocode

```c
CTsPropertyCfg::SPropData *__fastcall CTsPropertyCfg::SPropData::SPropData(
        CTsPropertyCfg::SPropData *this,
        const struct _tagpropertykey *a2,
        const struct _GUID *a3)
{
  void *v5; // rax
  __int64 v6; // rdx
  PROPVARIANT *v7; // rdx
  HRESULT inited; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx

  *(struct _tagpropertykey *)this = *a2;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = -1;
  v5 = operator new(0x18u);
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v5;
  if ( v6 )
    CTsPropertyCfg::SPropData::PropVarDeleter::operator()();
  v7 = (PROPVARIANT *)*((_QWORD *)this + 3);
  if ( v7 )
  {
    inited = InitPropVariantFromCLSID(a3, v7);
    if ( inited < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          16,
          WPP_fdcbca90fd7f33414ba60dd741ad2ded_Traceguids,
          CurrentThreadActivityIdPrefix,
          inited);
      }
      v10 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
      if ( v10 )
        CTsPropertyCfg::SPropData::PropVarDeleter::operator()();
    }
  }
  return this;
}

```

## disassembly

```asm
0x180042384  mov     [rsp+arg_0], rbx
0x180042389  push    rdi
0x18004238a  sub     rsp, 30h
0x18004238e  movups  xmm0, xmmword ptr [rdx]
0x180042391  mov     rbx, rcx
0x180042394  mov     rdi, r8
0x180042397  movups  xmmword ptr [rcx], xmm0
0x18004239a  mov     eax, [rdx+10h]
0x18004239d  mov     [rcx+10h], eax
0x1800423a0  mov     qword ptr [rcx+18h], 0
0x1800423a8  mov     qword ptr [rcx+20h], 0
0x1800423b0  mov     dword ptr [rcx+28h], 0FFFFFFFFh
0x1800423b7  mov     ecx, 18h; Size
0x1800423bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800423c1  mov     rdx, [rbx+18h]
0x1800423c5  mov     [rbx+18h], rax
0x1800423c9  test    rdx, rdx
0x1800423cc  jz      short loc_1800423D3
0x1800423ce  call    ??RPropVarDeleter@SPropData@CTsPropertyCfg@@QEAAXPEAUtagPROPVARIANT@@@Z; CTsPropertyCfg::SPropData::PropVarDeleter::operator()(tagPROPVARIANT *)
0x1800423d3  mov     rdx, [rbx+18h]; ppropvar
0x1800423d7  test    rdx, rdx
0x1800423da  jz      short loc_180042448
0x1800423dc  mov     rcx, rdi; clsid
0x1800423df  call    cs:__imp_InitPropVariantFromCLSID
0x1800423e5  mov     edi, eax
0x1800423e7  test    eax, eax
0x1800423e9  jns     short loc_180042448
0x1800423eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800423f2  lea     rax, WPP_GLOBAL_Control
0x1800423f9  cmp     rcx, rax
0x1800423fc  jz      short loc_180042432
0x1800423fe  test    byte ptr [rcx+1Ch], 1
0x180042402  jz      short loc_180042432
0x180042404  cmp     byte ptr [rcx+19h], 2
0x180042408  jb      short loc_180042432
0x18004240a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004240f  mov     rcx, cs:WPP_GLOBAL_Control
0x180042416  lea     r8, WPP_fdcbca90fd7f33414ba60dd741ad2ded_Traceguids
0x18004241d  mov     edx, 10h
0x180042422  mov     [rsp+38h+var_18], edi
0x180042426  mov     r9d, eax
0x180042429  mov     rcx, [rcx+10h]
0x18004242d  call    WPP_SF_Dd
0x180042432  mov     rdx, [rbx+18h]
0x180042436  mov     qword ptr [rbx+18h], 0
0x18004243e  test    rdx, rdx
0x180042441  jz      short loc_180042448
0x180042443  call    ??RPropVarDeleter@SPropData@CTsPropertyCfg@@QEAAXPEAUtagPROPVARIANT@@@Z; CTsPropertyCfg::SPropData::PropVarDeleter::operator()(tagPROPVARIANT *)
0x180042448  mov     rax, rbx
0x18004244b  mov     rbx, [rsp+38h+arg_0]
0x180042450  add     rsp, 30h
0x180042454  pop     rdi
0x180042455  retn
```
