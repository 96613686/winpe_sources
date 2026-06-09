# ReadCookieFromInetDB(ushort const *,_GUID *)

- ea: `0x18000cc84`
- end: `0x18000ce2b`
- name: `?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPIID lpiid)`
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800027e0`
- `0x18000a4d0`
- `0x18000b514`
- `0x18000e28c`
- `0x1800170c8`
- `0x18001939c`

## callees

- `0x18000c1d0`
- `0x18000cc84`
- `0x18000dd40`
- `0x180018958`
- `0x180019630`
- `0x180019ae0`
- `0x18001ba08`
- `0x18001da30`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x18000cdaa`
- `SHLWAPI!StrCmpIW` at `0x18000cdaa`
- `ole32!IIDFromString` at `0x18000cce6`
- `ole32!IIDFromString` at `0x18000cce6`
- `ole32!PropVariantClear` at `0x18000ccf2`
- `ole32!PropVariantClear` at `0x18000ccf2`
- `ole32!CoTaskMemFree` at `0x18000cdbd`
- `ole32!CoTaskMemFree` at `0x18000cdbd`

## pseudocode

```c
__int64 __fastcall ReadCookieFromInetDB(const unsigned __int16 *a1, LPIID lpiid, __int64 a3, unsigned int a4)
{
  HRESULT v6; // edi
  CEnumSubscription *v7; // rax
  CEnumSubscription *v8; // rax
  CEnumSubscription *v9; // rbx
  BOOL v10; // r14d
  unsigned int v11; // r9d
  struct ISubscriptionItem *v12; // rsi
  PCWSTR psz1; // [rsp+30h] [rbp-40h] BYREF
  struct ISubscriptionItem *v15; // [rsp+38h] [rbp-38h] BYREF
  struct tagPROPVARIANT lpsz; // [rsp+40h] [rbp-30h] BYREF
  IID rclsid; // [rsp+58h] [rbp-18h] BYREF

  memset(&lpsz, 0, sizeof(lpsz));
  v6 = IntSiteHelper(a1, &c_rgPropRead, &lpsz, a4, 0);
  if ( v6 >= 0 && lpsz.vt == 31 )
    v6 = IIDFromString(lpsz.bstrVal, lpiid);
  PropVariantClear((PROPVARIANT *)&lpsz);
  if ( v6 )
  {
    v7 = (CEnumSubscription *)operator new(0x20u);
    if ( v7 )
    {
      v8 = CEnumSubscription::CEnumSubscription(v7);
      v9 = v8;
      if ( v8 )
      {
        if ( (int)CEnumSubscription::Initialize(v8, 0) >= 0 )
        {
          v10 = 0;
          rclsid = 0;
          while ( !(*(unsigned int (__fastcall **)(CEnumSubscription *, __int64, IID *))(*(_QWORD *)v9 + 24LL))(
                     v9,
                     1,
                     &rclsid) )
          {
            v15 = 0;
            if ( (int)SubscriptionItemFromCookie(0, &rclsid, &v15) >= 0 )
            {
              v12 = v15;
              psz1 = 0;
              if ( (int)ReadOLESTR(v15, L"URL", (unsigned __int16 **)&psz1) >= 0 )
              {
                v10 = StrCmpIW(psz1, a1) == 0;
                CoTaskMemFree((LPVOID)psz1);
              }
              ((void (__fastcall *)(struct ISubscriptionItem *))v12->lpVtbl->Release)(v12);
            }
            if ( v10 )
            {
              WriteCookieToInetDB(a1, &rclsid, 0, v11);
              v6 = 0;
              *lpiid = rclsid;
              break;
            }
          }
        }
        (*(void (__fastcall **)(CEnumSubscription *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000cc84  mov     [rsp-28h+arg_10], rbx
0x18000cc89  mov     [rsp-28h+arg_18], rsi
0x18000cc8e  push    rbp
0x18000cc8f  push    rdi
0x18000cc90  push    r12
0x18000cc92  push    r14
0x18000cc94  push    r15
0x18000cc96  mov     rbp, rsp
0x18000cc99  sub     rsp, 70h
0x18000cc9d  mov     rax, cs:__security_cookie
0x18000cca4  xor     rax, rsp
0x18000cca7  mov     [rbp+var_8], rax
0x18000ccab  xor     eax, eax
0x18000ccad  lea     r8, [rbp+lpsz]; struct tagPROPVARIANT *
0x18000ccb1  mov     r15, rdx
0x18000ccb4  mov     [rbp+var_20], rax
0x18000ccb8  xorps   xmm0, xmm0
0x18000ccbb  mov     [rsp+70h+var_50], eax; int
0x18000ccbf  lea     rdx, ?c_rgPropRead@@3QBUtagPROPSPEC@@B; struct tagPROPSPEC *
0x18000ccc6  mov     r12, rcx
0x18000ccc9  movups  xmmword ptr [rbp+lpsz], xmm0
0x18000cccd  call    ?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z; IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)
0x18000ccd2  mov     edi, eax
0x18000ccd4  test    eax, eax
0x18000ccd6  js      short loc_18000CCEE
0x18000ccd8  cmp     word ptr [rbp+lpsz], 1Fh
0x18000ccdd  jnz     short loc_18000CCEE
0x18000ccdf  mov     rcx, [rbp+lpsz+8]; lpsz
0x18000cce3  mov     rdx, r15; lpiid
0x18000cce6  call    cs:__imp_IIDFromString
0x18000ccec  mov     edi, eax
0x18000ccee  lea     rcx, [rbp+lpsz]; pvar
0x18000ccf2  call    cs:__imp_PropVariantClear
0x18000ccf8  test    edi, edi
0x18000ccfa  jz      loc_18000CE04
0x18000cd00  mov     ecx, 20h ; ' '; dwBytes
0x18000cd05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cd0a  test    rax, rax
0x18000cd0d  jz      loc_18000CE04
0x18000cd13  mov     rcx, rax; this
0x18000cd16  call    ??0CEnumSubscription@@QEAA@XZ; CEnumSubscription::CEnumSubscription(void)
0x18000cd1b  mov     rbx, rax
0x18000cd1e  test    rax, rax
0x18000cd21  jz      loc_18000CE04
0x18000cd27  xor     edx, edx; unsigned int
0x18000cd29  mov     rcx, rax; this
0x18000cd2c  call    ?Initialize@CEnumSubscription@@QEAAJK@Z; CEnumSubscription::Initialize(ulong)
0x18000cd31  test    eax, eax
0x18000cd33  js      loc_18000CDF5
0x18000cd39  xorps   xmm0, xmm0
0x18000cd3c  xor     r14d, r14d
0x18000cd3f  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18000cd43  mov     rax, [rbx]
0x18000cd46  lea     r8, [rbp+rclsid]
0x18000cd4a  xor     r9d, r9d
0x18000cd4d  mov     rcx, rbx
0x18000cd50  mov     rax, [rax+18h]
0x18000cd54  lea     edx, [r9+1]
0x18000cd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd5d  test    eax, eax
0x18000cd5f  jnz     loc_18000CDF5
0x18000cd65  lea     r8, [rbp+var_38]; struct ISubscriptionItem **
0x18000cd69  mov     [rbp+var_38], 0
0x18000cd71  lea     rdx, [rbp+rclsid]; struct _GUID *
0x18000cd75  xor     ecx, ecx; int
0x18000cd77  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x18000cd7c  test    eax, eax
0x18000cd7e  js      short loc_18000CDD2
0x18000cd80  mov     rsi, [rbp+var_38]
0x18000cd84  lea     r8, [rbp+psz1]; unsigned __int16 **
0x18000cd88  mov     rcx, rsi; struct ISubscriptionItem *
0x18000cd8b  mov     [rbp+psz1], 0
0x18000cd93  lea     rdx, ?c_szPropURL@@3QBGB; "URL"
0x18000cd9a  call    ?ReadOLESTR@@YAJPEAUISubscriptionItem@@PEBGPEAPEAG@Z; ReadOLESTR(ISubscriptionItem *,ushort const *,ushort * *)
0x18000cd9f  test    eax, eax
0x18000cda1  js      short loc_18000CDC3
0x18000cda3  mov     rcx, [rbp+psz1]; psz1
0x18000cda7  mov     rdx, r12; psz2
0x18000cdaa  call    cs:__imp_StrCmpIW
0x18000cdb0  mov     rcx, [rbp+psz1]; pv
0x18000cdb4  xor     r14d, r14d
0x18000cdb7  test    eax, eax
0x18000cdb9  setz    r14b
0x18000cdbd  call    cs:__imp_CoTaskMemFree
0x18000cdc3  mov     rax, [rsi]
0x18000cdc6  mov     rcx, rsi
0x18000cdc9  mov     rax, [rax+10h]
0x18000cdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd2  test    r14d, r14d
0x18000cdd5  jz      loc_18000CD43
0x18000cddb  xor     r8d, r8d; int
0x18000cdde  lea     rdx, [rbp+rclsid]; rclsid
0x18000cde2  mov     rcx, r12; unsigned __int16 *
0x18000cde5  call    ?WriteCookieToInetDB@@YAJPEBGPEBU_GUID@@H@Z; WriteCookieToInetDB(ushort const *,_GUID const *,int)
0x18000cdea  movups  xmm0, xmmword ptr [rbp+rclsid.Data1]
0x18000cdee  xor     edi, edi
0x18000cdf0  movdqu  xmmword ptr [r15], xmm0
0x18000cdf5  mov     rax, [rbx]
0x18000cdf8  mov     rcx, rbx
0x18000cdfb  mov     rax, [rax+10h]
0x18000cdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce04  mov     eax, edi
0x18000ce06  mov     rcx, [rbp+var_8]
0x18000ce0a  xor     rcx, rsp; StackCookie
0x18000ce0d  call    __security_check_cookie
0x18000ce12  lea     r11, [rsp+70h+var_s0]
0x18000ce17  mov     rbx, [r11+40h]
0x18000ce1b  mov     rsi, [r11+48h]
0x18000ce1f  mov     rsp, r11
0x18000ce22  pop     r15
0x18000ce24  pop     r14
0x18000ce26  pop     r12
0x18000ce28  pop     rdi
0x18000ce29  pop     rbp
0x18000ce2a  retn
```
