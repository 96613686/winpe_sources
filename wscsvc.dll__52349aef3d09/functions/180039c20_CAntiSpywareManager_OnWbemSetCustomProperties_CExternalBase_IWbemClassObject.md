# CAntiSpywareManager::OnWbemSetCustomProperties(CExternalBase *,IWbemClassObject *)

- ea: `0x180039c20`
- end: `0x180039ee2`
- name: `?OnWbemSetCustomProperties@CAntiSpywareManager@@MEAAJPEAVCExternalBase@@PEAUIWbemClassObject@@@Z`
- size: `706`
- prototype: `__int64 __fastcall(CAntiSpywareManager *__hidden this, struct CExternalBase *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008cc0`
- `0x18001c858`
- `0x180039c20`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180039e7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180039e7b`
- `OLEAUT32!__imp_VariantInit` at `0x180039c74`
- `OLEAUT32!__imp_VariantInit` at `0x180039c74`
- `OLEAUT32!__imp_VariantClear` at `0x180039cd4`
- `OLEAUT32!__imp_VariantClear` at `0x180039d7c`
- `OLEAUT32!__imp_VariantClear` at `0x180039ddf`
- `OLEAUT32!__imp_VariantClear` at `0x180039e35`
- `OLEAUT32!__imp_VariantClear` at `0x180039eaf`
- `OLEAUT32!__imp_VariantClear` at `0x180039cd4`
- `OLEAUT32!__imp_VariantClear` at `0x180039d7c`
- `OLEAUT32!__imp_VariantClear` at `0x180039ddf`
- `OLEAUT32!__imp_VariantClear` at `0x180039e35`
- `OLEAUT32!__imp_VariantClear` at `0x180039eaf`

## pseudocode

```c
__int64 __fastcall CAntiSpywareManager::OnWbemSetCustomProperties(
        CAntiSpywareManager *this,
        struct CExternalBase *a2,
        struct IWbemClassObject *a3)
{
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // r14d
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-30h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-18h] BYREF

  if ( a2 && a3 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
           a3,
           L"productUptoDate",
           0,
           &pvarg,
           0,
           0);
    if ( v6 >= 0 )
    {
      if ( pvarg.vt == 1 || (v7 = 0, pvarg.iVal != -1) )
        v7 = 16;
      *((_DWORD *)a2 + 20) &= 0xFFFFFF0F;
      *((_DWORD *)a2 + 20) |= v7;
    }
    VariantClear(&pvarg);
    if ( v6 >= 0 )
    {
      v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
             a3,
             L"productHasNotifiedUser",
             0,
             &pvarg,
             0,
             0);
      if ( v6 >= 0 )
      {
        if ( pvarg.vt == 1 || (v8 = 0x10000, pvarg.iVal != -1) )
          v8 = 0;
        v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
               a3,
               L"productWantsWscNotifications",
               0,
               &pvarg,
               0,
               0);
        if ( v6 >= 0 )
        {
          if ( pvarg.vt == 1 || (v9 = 0x20000, pvarg.iVal != -1) )
            v9 = 0;
          *((_DWORD *)a2 + 20) &= 0xFFF0FFFF;
          *((_DWORD *)a2 + 20) |= v8 | v9;
        }
      }
    }
    VariantClear(&pvarg);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
           a3,
           L"productState",
           0,
           &pvarg,
           0,
           0);
    if ( v6 < 0 || pvarg.vt == 1 )
    {
      VariantClear(&pvarg);
      v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
             a3,
             L"productEnabled",
             0,
             &pvarg,
             0,
             0);
      if ( v6 < 0 )
      {
LABEL_32:
        VariantClear(&pvarg);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
                 a3,
                 L"instanceGuid",
                 0,
                 &pvarg,
                 0,
                 0);
          if ( v6 >= 0 )
          {
            pclsid = 0;
            v6 = CLSIDFromString(pvarg.bstrVal, &pclsid);
            if ( v6 >= 0 )
            {
              v12 = *(_QWORD *)&pclsid.Data1 - *((_QWORD *)this + 11);
              if ( *(_QWORD *)&pclsid.Data1 == *((_QWORD *)this + 11) )
                v12 = *(_QWORD *)pclsid.Data4 - *((_QWORD *)this + 12);
              if ( !v12 )
                CExternalBase::SetProductOwner(a2, 256);
            }
            VariantClear(&pvarg);
          }
        }
        return (unsigned int)v6;
      }
      if ( pvarg.vt == 1 || !pvarg.iVal )
        v11 = 0;
      else
        v11 = 4096;
    }
    else
    {
      v11 = 0;
      if ( pvarg.bVal == 1 )
        v11 = 4096;
      if ( pvarg.bVal == 2 )
        v11 = 0x2000;
    }
    CExternalBase::SetProductState(a2, v11, v10);
    goto LABEL_32;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180039c20  mov     [rsp-38h+arg_0], rbx
0x180039c25  push    rbp
0x180039c26  push    rsi
0x180039c27  push    rdi
0x180039c28  push    r12
0x180039c2a  push    r13
0x180039c2c  push    r14
0x180039c2e  push    r15
0x180039c30  mov     rbp, rsp
0x180039c33  sub     rsp, 70h
0x180039c37  mov     rax, cs:__security_cookie
0x180039c3e  xor     rax, rsp
0x180039c41  mov     [rbp+var_8], rax
0x180039c45  xor     r12d, r12d
0x180039c48  mov     rsi, r8
0x180039c4b  mov     rdi, rdx
0x180039c4e  mov     r15, rcx
0x180039c51  test    rdx, rdx
0x180039c54  jz      loc_180039EB9
0x180039c5a  test    r8, r8
0x180039c5d  jz      loc_180039EB9
0x180039c63  xorps   xmm0, xmm0
0x180039c66  lea     rcx, [rbp+pvarg]; pvarg
0x180039c6a  xor     eax, eax
0x180039c6c  movups  xmmword ptr [rbp+pvarg], xmm0
0x180039c70  mov     qword ptr [rbp+pvarg+10h], rax
0x180039c74  call    cs:__imp_VariantInit
0x180039c7a  mov     rax, [rsi]
0x180039c7d  lea     r9, [rbp+pvarg]
0x180039c81  mov     [rsp+70h+var_48], r12
0x180039c86  lea     rdx, aProductuptodat; "productUptoDate"
0x180039c8d  xor     r8d, r8d
0x180039c90  mov     [rsp+70h+var_50], r12
0x180039c95  mov     rcx, rsi
0x180039c98  mov     rax, [rax+20h]
0x180039c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ca1  or      r14d, 0FFFFFFFFh
0x180039ca5  lea     r13d, [r12+1]
0x180039caa  mov     ebx, eax
0x180039cac  test    eax, eax
0x180039cae  js      short loc_180039CD0
0x180039cb0  cmp     r13w, word ptr [rbp+pvarg]
0x180039cb5  jz      short loc_180039CC1
0x180039cb7  mov     eax, r12d
0x180039cba  cmp     word ptr [rbp+pvarg+8], r14w
0x180039cbf  jz      short loc_180039CC6
0x180039cc1  mov     eax, 10h
0x180039cc6  and     dword ptr [rdi+50h], 0FFFFFF0Fh
0x180039ccd  or      [rdi+50h], eax
0x180039cd0  lea     rcx, [rbp+pvarg]; pvarg
0x180039cd4  call    cs:__imp_VariantClear
0x180039cda  test    ebx, ebx
0x180039cdc  js      loc_180039D78
0x180039ce2  mov     rax, [rsi]
0x180039ce5  lea     r9, [rbp+pvarg]
0x180039ce9  mov     [rsp+70h+var_48], r12
0x180039cee  lea     rdx, aProducthasnoti; "productHasNotifiedUser"
0x180039cf5  xor     r8d, r8d
0x180039cf8  mov     [rsp+70h+var_50], r12
0x180039cfd  mov     rcx, rsi
0x180039d00  mov     rax, [rax+20h]
0x180039d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d09  mov     ebx, eax
0x180039d0b  test    eax, eax
0x180039d0d  js      short loc_180039D78
0x180039d0f  cmp     r13w, word ptr [rbp+pvarg]
0x180039d14  jz      short loc_180039D23
0x180039d16  cmp     r14w, word ptr [rbp+pvarg+8]
0x180039d1b  mov     r14d, 10000h
0x180039d21  jz      short loc_180039D26
0x180039d23  mov     r14d, r12d
0x180039d26  mov     rax, [rsi]
0x180039d29  lea     r9, [rbp+pvarg]
0x180039d2d  mov     [rsp+70h+var_48], r12
0x180039d32  lea     rdx, aProductwantsws; "productWantsWscNotifications"
0x180039d39  xor     r8d, r8d
0x180039d3c  mov     [rsp+70h+var_50], r12
0x180039d41  mov     rcx, rsi
0x180039d44  mov     rax, [rax+20h]
0x180039d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d4d  mov     ebx, eax
0x180039d4f  test    eax, eax
0x180039d51  js      short loc_180039D78
0x180039d53  cmp     r13w, word ptr [rbp+pvarg]
0x180039d58  jz      short loc_180039D68
0x180039d5a  or      eax, 0FFFFFFFFh
0x180039d5d  cmp     ax, word ptr [rbp+pvarg+8]
0x180039d61  mov     eax, 20000h
0x180039d66  jz      short loc_180039D6B
0x180039d68  mov     eax, r12d
0x180039d6b  and     dword ptr [rdi+50h], 0FFF0FFFFh
0x180039d72  or      eax, r14d
0x180039d75  or      [rdi+50h], eax
0x180039d78  lea     rcx, [rbp+pvarg]; pvarg
0x180039d7c  call    cs:__imp_VariantClear
0x180039d82  test    ebx, ebx
0x180039d84  js      loc_180039EB5
0x180039d8a  mov     rax, [rsi]
0x180039d8d  lea     r9, [rbp+pvarg]
0x180039d91  mov     [rsp+70h+var_48], r12
0x180039d96  lea     rdx, aProductstate; "productState"
0x180039d9d  xor     r8d, r8d
0x180039da0  mov     [rsp+70h+var_50], r12
0x180039da5  mov     rcx, rsi
0x180039da8  mov     rax, [rax+20h]
0x180039dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039db1  mov     ebx, eax
0x180039db3  test    eax, eax
0x180039db5  js      short loc_180039DDB
0x180039db7  cmp     word ptr [rbp+pvarg], r13w
0x180039dbc  jz      short loc_180039DDB
0x180039dbe  cmp     byte ptr [rbp+pvarg+8], r13b
0x180039dc2  mov     eax, 1000h
0x180039dc7  mov     edx, r12d
0x180039dca  cmovz   edx, eax
0x180039dcd  cmp     byte ptr [rbp+pvarg+8], 2
0x180039dd1  mov     eax, 2000h
0x180039dd6  cmovz   edx, eax
0x180039dd9  jmp     short loc_180039E29
0x180039ddb  lea     rcx, [rbp+pvarg]; pvarg
0x180039ddf  call    cs:__imp_VariantClear
0x180039de5  mov     rax, [rsi]
0x180039de8  lea     r9, [rbp+pvarg]
0x180039dec  mov     [rsp+70h+var_48], r12
0x180039df1  lea     rdx, aProductenabled; "productEnabled"
0x180039df8  xor     r8d, r8d
0x180039dfb  mov     [rsp+70h+var_50], r12
0x180039e00  mov     rcx, rsi
0x180039e03  mov     rax, [rax+20h]
0x180039e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e0c  mov     ebx, eax
0x180039e0e  test    eax, eax
0x180039e10  js      short loc_180039E31
0x180039e12  cmp     word ptr [rbp+pvarg], r13w
0x180039e17  jz      short loc_180039E27
0x180039e19  cmp     word ptr [rbp+pvarg+8], r12w
0x180039e1e  jz      short loc_180039E27
0x180039e20  mov     edx, 1000h
0x180039e25  jmp     short loc_180039E29
0x180039e27  xor     edx, edx
0x180039e29  mov     rcx, rdi
0x180039e2c  call    ?SetProductState@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductState(ProductState)
0x180039e31  lea     rcx, [rbp+pvarg]; pvarg
0x180039e35  call    cs:__imp_VariantClear
0x180039e3b  test    ebx, ebx
0x180039e3d  js      short loc_180039EB5
0x180039e3f  mov     rax, [rsi]
0x180039e42  lea     r9, [rbp+pvarg]
0x180039e46  mov     [rsp+70h+var_48], r12
0x180039e4b  lea     rdx, aInstanceguid; "instanceGuid"
0x180039e52  xor     r8d, r8d
0x180039e55  mov     [rsp+70h+var_50], r12
0x180039e5a  mov     rcx, rsi
0x180039e5d  mov     rax, [rax+20h]
0x180039e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e66  mov     ebx, eax
0x180039e68  test    eax, eax
0x180039e6a  js      short loc_180039EB5
0x180039e6c  mov     rcx, qword ptr [rbp+pvarg+8]; lpsz
0x180039e70  lea     rdx, [rbp+pclsid]; pclsid
0x180039e74  xorps   xmm0, xmm0
0x180039e77  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180039e7b  call    cs:__imp_CLSIDFromString
0x180039e81  mov     ebx, eax
0x180039e83  test    eax, eax
0x180039e85  js      short loc_180039EAB
0x180039e87  mov     rax, qword ptr [rbp+pclsid.Data1]
0x180039e8b  sub     rax, [r15+58h]
0x180039e8f  jnz     short loc_180039E99
0x180039e91  mov     rax, qword ptr [rbp+pclsid.Data4]
0x180039e95  sub     rax, [r15+60h]
0x180039e99  test    rax, rax
0x180039e9c  jnz     short loc_180039EAB
0x180039e9e  mov     edx, 100h
0x180039ea3  mov     rcx, rdi
0x180039ea6  call    ?SetProductOwner@CExternalBase@@QEAAHW4ProductOwner@@@Z; CExternalBase::SetProductOwner(ProductOwner)
0x180039eab  lea     rcx, [rbp+pvarg]; pvarg
0x180039eaf  call    cs:__imp_VariantClear
0x180039eb5  mov     eax, ebx
0x180039eb7  jmp     short loc_180039EBE
0x180039eb9  mov     eax, 80070057h
0x180039ebe  mov     rcx, [rbp+var_8]
0x180039ec2  xor     rcx, rsp; StackCookie
0x180039ec5  call    __security_check_cookie
0x180039eca  mov     rbx, [rsp+70h+arg_0]
0x180039ed2  add     rsp, 70h
0x180039ed6  pop     r15
0x180039ed8  pop     r14
0x180039eda  pop     r13
0x180039edc  pop     r12
0x180039ede  pop     rdi
0x180039edf  pop     rsi
0x180039ee0  pop     rbp
0x180039ee1  retn
```
