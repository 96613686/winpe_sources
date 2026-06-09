# CTypeLibWrapper::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180067d80`
- end: `0x180067e03`
- name: `?Invoke@CTypeLibWrapper@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `131`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this, int, const struct _GUID *, unsigned int, char, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180067d80`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180067de1`
- `OLEAUT32!__imp_VariantCopy` at `0x180067de1`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Invoke(
        CTypeLibWrapper *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        char a5,
        struct tagDISPPARAMS *a6,
        VARIANTARG *pvargDest)
{
  HRESULT v8; // eax
  unsigned int v9; // ecx

  if ( (a5 & 2) == 0 || !*((_DWORD *)this + 3) || a2 > *((_DWORD *)this + 3) )
    return 2147614723LL;
  if ( !a6 )
    goto LABEL_9;
  if ( a6->cArgs )
    return 2147614734LL;
  if ( a6->cNamedArgs )
    return 2147614727LL;
LABEL_9:
  if ( !pvargDest )
    return 0;
  v8 = VariantCopy(pvargDest, (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 3) + 16LL) + 24LL * (int)(a2 - 1)));
  v9 = 0;
  if ( v8 < 0 )
    return (unsigned int)v8;
  return v9;
}

```

## disassembly

```asm
0x180067d80  sub     rsp, 28h
0x180067d84  test    [rsp+28h+arg_20], 2
0x180067d89  mov     r9, rcx
0x180067d8c  jz      short loc_180067DF8
0x180067d8e  cmp     dword ptr [rcx+0Ch], 0
0x180067d92  jz      short loc_180067DF8
0x180067d94  cmp     edx, [rcx+0Ch]
0x180067d97  ja      short loc_180067DF8
0x180067d99  mov     rax, [rsp+28h+arg_28]
0x180067d9e  test    rax, rax
0x180067da1  jz      short loc_180067DBD
0x180067da3  cmp     dword ptr [rax+10h], 0
0x180067da7  jz      short loc_180067DB0
0x180067da9  mov     eax, 8002000Eh
0x180067dae  jmp     short loc_180067DFD
0x180067db0  cmp     dword ptr [rax+14h], 0
0x180067db4  jz      short loc_180067DBD
0x180067db6  mov     eax, 80020007h
0x180067dbb  jmp     short loc_180067DFD
0x180067dbd  mov     rcx, [rsp+28h+pvargDest]; pvargDest
0x180067dc2  test    rcx, rcx
0x180067dc5  jnz     short loc_180067DCB
0x180067dc7  xor     eax, eax
0x180067dc9  jmp     short loc_180067DFD
0x180067dcb  lea     eax, [rdx-1]
0x180067dce  movsxd  rdx, eax
0x180067dd1  mov     rax, [r9+18h]
0x180067dd5  lea     r8, [rdx+rdx*2]
0x180067dd9  mov     rdx, [rax+10h]
0x180067ddd  lea     rdx, [rdx+r8*8]; pvargSrc
0x180067de1  call    cs:__imp_VariantCopy
0x180067de8  nop     dword ptr [rax+rax+00h]
0x180067ded  xor     ecx, ecx
0x180067def  test    eax, eax
0x180067df1  cmovs   ecx, eax
0x180067df4  mov     eax, ecx
0x180067df6  jmp     short loc_180067DFD
0x180067df8  mov     eax, 80020003h
0x180067dfd  add     rsp, 28h
0x180067e01  retn
```
