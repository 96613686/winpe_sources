# CRegPropertyBag::Write(ushort const *,tagVARIANT *)

- ea: `0x1800097e0`
- end: `0x1800099e2`
- name: `?Write@CRegPropertyBag@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(CRegPropertyBag *__hidden this, const unsigned __int16 *, VARIANTARG *pvarSrc)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800097e0`
- `0x1800099e8`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180009961`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180009961`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180009917`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180009917`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800098e0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000998a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800099ca`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800098e0`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18000998a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x1800099ca`
- `OLEAUT32!__imp_VariantClear` at `0x18000999e`
- `OLEAUT32!__imp_VariantClear` at `0x18000999e`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800098b7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009951`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800098b7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009951`

## pseudocode

```c
__int64 __fastcall CRegPropertyBag::Write(CRegPropertyBag *this, const unsigned __int16 *a2, VARIANTARG *pvarSrc)
{
  int v5; // ecx
  HRESULT v6; // ebx
  unsigned int vt; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, struct IStream **); // rcx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  bool v18; // zf
  int v19; // eax
  struct IStream *v20; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvargDest; // [rsp+38h] [rbp-28h] BYREF

  v5 = *((_DWORD *)this + 7) & 3;
  v6 = v5 == 0 ? 0x80070005 : 0;
  if ( !v5 )
    return (unsigned int)v6;
  vt = pvarSrc->vt;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( vt <= 0x11 )
  {
    if ( vt != 17 )
    {
      if ( !vt )
      {
        SHDeleteValueW(*((HKEY *)this + 4), 0, a2);
        return (unsigned int)v6;
      }
      v8 = vt - 2;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 8;
          if ( v10 )
          {
            v11 = v10 - 2;
            if ( !v11 )
            {
              llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IStream **))pvarSrc->llVal;
              v20 = 0;
              v6 = (**llVal)(llVal, &GUID_0000000c_0000_0000_c000_000000000046, &v20);
              if ( v6 >= 0 )
              {
                v6 = CRegPropertyBag::_WriteStream(this, a2, v20);
                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v20 + 16LL))(v20);
              }
              return (unsigned int)v6;
            }
            v18 = v11 == 3;
LABEL_21:
            if ( !v18 )
            {
              v6 = VariantChangeType(&pvargDest, pvarSrc, 0, 8u);
              if ( v6 >= 0 )
              {
                v19 = lstrlenW(pvargDest.bstrVal);
                if ( SHSetValueW(*((HKEY *)this + 4), 0, a2, 1u, pvargDest.bstrVal, 2 * v19 + 2) )
                  v6 = -2147467259;
                VariantClear(&pvargDest);
              }
              return (unsigned int)v6;
            }
            goto LABEL_11;
          }
        }
      }
    }
    goto LABEL_11;
  }
  v14 = vt - 18;
  if ( !v14 )
    goto LABEL_11;
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_11;
  v16 = v15 - 2;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 == 1;
      goto LABEL_21;
    }
LABEL_11:
    v6 = VariantChangeType(&pvargDest, pvarSrc, 0, 0x13u);
    if ( v6 >= 0 && SHSetValueW(*((HKEY *)this + 4), 0, a2, 4u, &pvargDest.decVal.8, 4u) )
      return (unsigned int)-2147467259;
    return (unsigned int)v6;
  }
  if ( SHSetValueW(*((HKEY *)this + 4), 0, a2, 0xBu, &pvarSrc->decVal.8, 8u) )
    return (unsigned int)-2147467259;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800097e0  mov     [rsp-18h+arg_18], rbx
0x1800097e5  push    rbp
0x1800097e6  push    rsi
0x1800097e7  push    rdi
0x1800097e8  mov     rbp, rsp
0x1800097eb  sub     rsp, 60h
0x1800097ef  mov     rax, cs:__security_cookie
0x1800097f6  xor     rax, rsp
0x1800097f9  mov     [rbp+var_10], rax
0x1800097fd  mov     rdi, rcx
0x180009800  mov     r10, r8
0x180009803  mov     ecx, [rcx+1Ch]
0x180009806  mov     rsi, rdx
0x180009809  and     ecx, 3
0x18000980c  mov     eax, ecx
0x18000980e  neg     eax
0x180009810  sbb     ebx, ebx
0x180009812  not     ebx
0x180009814  and     ebx, 80070005h
0x18000981a  test    ecx, ecx
0x18000981c  jz      loc_1800098F0
0x180009822  movzx   ecx, word ptr [r8]
0x180009826  xor     eax, eax
0x180009828  mov     qword ptr [rbp+pvargDest+10h], rax
0x18000982c  xorps   xmm0, xmm0
0x18000982f  movups  xmmword ptr [rbp+pvargDest], xmm0
0x180009833  lea     edx, [rax+8]
0x180009836  cmp     ecx, 11h
0x180009839  ja      loc_18000991F
0x18000983f  jz      short loc_1800098A7
0x180009841  test    ecx, ecx
0x180009843  jz      loc_18000990E
0x180009849  sub     ecx, 2
0x18000984c  jz      short loc_1800098A7
0x18000984e  sub     ecx, 1
0x180009851  jz      short loc_1800098A7
0x180009853  sub     ecx, edx
0x180009855  jz      short loc_1800098A7
0x180009857  sub     ecx, 2
0x18000985a  jnz     loc_1800099A9
0x180009860  mov     rcx, [r8+8]
0x180009864  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000986b  mov     [rbp+var_30], rax
0x18000986f  lea     r8, [rbp+var_30]
0x180009873  mov     rax, [rcx]
0x180009876  mov     rax, [rax]
0x180009879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000987e  mov     ebx, eax
0x180009880  test    eax, eax
0x180009882  js      short loc_1800098F0
0x180009884  mov     r8, [rbp+var_30]; struct IStream *
0x180009888  mov     rdx, rsi; unsigned __int16 *
0x18000988b  mov     rcx, rdi; this
0x18000988e  call    ?_WriteStream@CRegPropertyBag@@AEAAJPEBGPEAUIStream@@@Z; CRegPropertyBag::_WriteStream(ushort const *,IStream *)
0x180009893  mov     rcx, [rbp+var_30]
0x180009897  mov     ebx, eax
0x180009899  mov     rax, [rcx]
0x18000989c  mov     rax, [rax+10h]
0x1800098a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a5  jmp     short loc_1800098F0
0x1800098a7  mov     r9d, 13h; vt
0x1800098ad  lea     rcx, [rbp+pvargDest]; pvargDest
0x1800098b1  xor     r8d, r8d; wFlags
0x1800098b4  mov     rdx, r10; pvarSrc
0x1800098b7  call    cs:__imp_VariantChangeType
0x1800098bd  mov     ebx, eax
0x1800098bf  test    eax, eax
0x1800098c1  js      short loc_1800098F0
0x1800098c3  mov     rcx, [rdi+20h]; hkey
0x1800098c7  lea     rax, [rbp+pvargDest+8]
0x1800098cb  mov     r9d, 4; dwType
0x1800098d1  mov     r8, rsi; pszValue
0x1800098d4  mov     [rsp+60h+cbData], r9d; cbData
0x1800098d9  xor     edx, edx; pszSubKey
0x1800098db  mov     [rsp+60h+pvData], rax; pvData
0x1800098e0  call    cs:__imp_SHSetValueW
0x1800098e6  test    eax, eax
0x1800098e8  mov     ecx, 80004005h
0x1800098ed  cmovnz  ebx, ecx
0x1800098f0  mov     eax, ebx
0x1800098f2  mov     rcx, [rbp+var_10]
0x1800098f6  xor     rcx, rsp; StackCookie
0x1800098f9  call    __security_check_cookie
0x1800098fe  mov     rbx, [rsp+60h+arg_18]
0x180009906  add     rsp, 60h
0x18000990a  pop     rdi
0x18000990b  pop     rsi
0x18000990c  pop     rbp
0x18000990d  retn
0x18000990e  mov     rcx, [rdi+20h]; hkey
0x180009912  mov     r8, rsi; pszValue
0x180009915  xor     edx, edx; pszSubKey
0x180009917  call    cs:__imp_SHDeleteValueW
0x18000991d  jmp     short loc_1800098F0
0x18000991f  sub     ecx, 12h
0x180009922  jz      short loc_1800098A7
0x180009924  sub     ecx, 1
0x180009927  jz      loc_1800098A7
0x18000992d  sub     ecx, 2
0x180009930  jz      short loc_1800099AE
0x180009932  sub     ecx, 1
0x180009935  jz      loc_1800098A7
0x18000993b  cmp     ecx, 1
0x18000993e  jz      loc_1800098A7
0x180009944  mov     r9d, edx; vt
0x180009947  lea     rcx, [rbp+pvargDest]; pvargDest
0x18000994b  mov     rdx, r10; pvarSrc
0x18000994e  xor     r8d, r8d; wFlags
0x180009951  call    cs:__imp_VariantChangeType
0x180009957  mov     ebx, eax
0x180009959  test    eax, eax
0x18000995b  js      short loc_1800098F0
0x18000995d  mov     rcx, qword ptr [rbp+pvargDest+8]; lpString
0x180009961  call    cs:__imp_lstrlenW
0x180009967  mov     rcx, [rdi+20h]; hkey
0x18000996b  mov     r9d, 1; dwType
0x180009971  mov     r8, rsi; pszValue
0x180009974  xor     edx, edx; pszSubKey
0x180009976  lea     eax, ds:2[rax*2]
0x18000997d  mov     [rsp+60h+cbData], eax; cbData
0x180009981  mov     rax, qword ptr [rbp+pvargDest+8]
0x180009985  mov     [rsp+60h+pvData], rax; pvData
0x18000998a  call    cs:__imp_SHSetValueW
0x180009990  test    eax, eax
0x180009992  mov     ecx, 80004005h
0x180009997  cmovnz  ebx, ecx
0x18000999a  lea     rcx, [rbp+pvargDest]; pvarg
0x18000999e  call    cs:__imp_VariantClear
0x1800099a4  jmp     loc_1800098F0
0x1800099a9  cmp     ecx, 3
0x1800099ac  jmp     short loc_18000993E
0x1800099ae  mov     rcx, [rdi+20h]; hkey
0x1800099b2  lea     rax, [r8+8]
0x1800099b6  mov     [rsp+60h+cbData], edx; cbData
0x1800099ba  mov     r8, rsi; pszValue
0x1800099bd  xor     edx, edx; pszSubKey
0x1800099bf  mov     [rsp+60h+pvData], rax; pvData
0x1800099c4  mov     r9d, 0Bh; dwType
0x1800099ca  call    cs:__imp_SHSetValueW
0x1800099d0  test    eax, eax
0x1800099d2  jz      loc_1800098F0
0x1800099d8  mov     ebx, 80004005h
0x1800099dd  jmp     loc_1800098F0
```
