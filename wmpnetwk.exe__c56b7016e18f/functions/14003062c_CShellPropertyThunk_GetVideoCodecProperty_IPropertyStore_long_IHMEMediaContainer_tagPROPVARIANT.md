# CShellPropertyThunk::GetVideoCodecProperty(IPropertyStore *,long,IHMEMediaContainer *,tagPROPVARIANT *)

- ea: `0x14003062c`
- end: `0x14003071c`
- name: `?GetVideoCodecProperty@CShellPropertyThunk@@SAJPEAUIPropertyStore@@JPEAUIHMEMediaContainer@@PEAUtagPROPVARIANT@@@Z`
- size: `240`
- prototype: `static int(struct IPropertyStore *, int, struct IHMEMediaContainer *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140080e20`

## callees

- `0x14003062c`
- `0x140045f20`
- `0x14009e010`

## import_xrefs

- `ole32!PropVariantClear` at `0x1400306b2`
- `ole32!PropVariantClear` at `0x1400306b2`
- `PROPSYS!InitPropVariantFromCLSID` at `0x14003070b`
- `PROPSYS!InitPropVariantFromCLSID` at `0x14003070b`

## pseudocode

```c
__int64 __fastcall CShellPropertyThunk::GetVideoCodecProperty(
        struct IPropertyStore *a1,
        int a2,
        struct IHMEMediaContainer *a3,
        PROPVARIANT *a4)
{
  HRESULT inited; // ebx
  struct IPropertyStoreVtbl *lpVtbl; // rax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  IID clsid; // [rsp+38h] [rbp-20h] BYREF

  if ( a2 )
  {
    return (unsigned int)-2147023728;
  }
  else
  {
    inited = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetValue)(
               a1,
               &PKEY_Video_Compression,
               a4);
    if ( inited < 0 || *(_WORD *)a4 <= 1u )
    {
      v10 = 0;
      lpVtbl = a1->lpVtbl;
      *(_OWORD *)pvar = 0;
      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->GetValue)(
             a1,
             &PKEY_Video_FourCC,
             pvar) >= 0
        && LOWORD(pvar[0]) == 19 )
      {
        *(_DWORD *)&clsid.Data4[4] = *(_DWORD *)&MFVideoFormat_Base.Data4[4];
        clsid.Data1 = (unsigned int)pvar[1];
        *(_QWORD *)&clsid.Data2 = *(_QWORD *)&MFVideoFormat_Base.Data2;
        inited = InitPropVariantFromCLSID(&clsid, a4);
      }
      else
      {
        inited = -2147023728;
      }
      PropVariantClear(pvar);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14003062c  mov     [rsp+arg_8], rbx
0x140030631  mov     [rsp+arg_10], rsi
0x140030636  push    rdi
0x140030637  sub     rsp, 50h
0x14003063b  mov     rax, cs:__security_cookie
0x140030642  xor     rax, rsp
0x140030645  mov     [rsp+58h+var_10], rax
0x14003064a  mov     rdi, r9
0x14003064d  mov     rsi, rcx
0x140030650  test    edx, edx
0x140030652  jnz     loc_140030715
0x140030658  mov     rax, [rcx]
0x14003065b  lea     rdx, PKEY_Video_Compression
0x140030662  mov     r8, r9
0x140030665  mov     rax, [rax+28h]
0x140030669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003066e  mov     ebx, eax
0x140030670  test    eax, eax
0x140030672  js      short loc_14003067A
0x140030674  cmp     word ptr [rdi], 1
0x140030678  ja      short loc_1400306B8
0x14003067a  xor     eax, eax
0x14003067c  lea     r8, [rsp+58h+pvar]
0x140030681  mov     [rsp+58h+var_28], rax
0x140030686  lea     rdx, PKEY_Video_FourCC
0x14003068d  mov     rax, [rsi]
0x140030690  xorps   xmm0, xmm0
0x140030693  mov     rcx, rsi
0x140030696  movups  xmmword ptr [rsp+58h+pvar], xmm0
0x14003069b  mov     rax, [rax+28h]
0x14003069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400306a4  test    eax, eax
0x1400306a6  jns     short loc_1400306D7
0x1400306a8  mov     ebx, 80070490h
0x1400306ad  lea     rcx, [rsp+58h+pvar]; pvar
0x1400306b2  call    cs:__imp_PropVariantClear
0x1400306b8  mov     eax, ebx
0x1400306ba  mov     rcx, [rsp+58h+var_10]
0x1400306bf  xor     rcx, rsp; StackCookie
0x1400306c2  call    __security_check_cookie
0x1400306c7  mov     rbx, [rsp+58h+arg_8]
0x1400306cc  mov     rsi, [rsp+58h+arg_10]
0x1400306d1  add     rsp, 50h
0x1400306d5  pop     rdi
0x1400306d6  retn
0x1400306d7  mov     eax, 13h
0x1400306dc  cmp     ax, word ptr [rsp+58h+pvar]
0x1400306e1  jnz     short loc_1400306A8
0x1400306e3  mov     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x1400306e9  lea     rcx, [rsp+58h+clsid]; clsid
0x1400306ee  movsd   xmm0, qword ptr cs:MFVideoFormat_Base.Data2
0x1400306f6  mov     rdx, rdi; ppropvar
0x1400306f9  mov     dword ptr [rsp+58h+clsid.Data4+4], eax
0x1400306fd  mov     eax, dword ptr [rsp+58h+pvar+8]
0x140030701  mov     [rsp+58h+clsid.Data1], eax
0x140030705  movsd   qword ptr [rsp+58h+clsid.Data2], xmm0
0x14003070b  call    cs:__imp_InitPropVariantFromCLSID
0x140030711  mov     ebx, eax
0x140030713  jmp     short loc_1400306AD
0x140030715  mov     ebx, 80070490h
0x14003071a  jmp     short loc_1400306B8
```
