# CTypeLibWrapper::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180065f30`
- end: `0x180065fac`
- name: `?Invoke@CTypeLibWrapper@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `124`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this, int, const struct _GUID *, unsigned int, char, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180065f30`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180065f91`
- `OLEAUT32!__imp_VariantCopy` at `0x180065f91`

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
0x180065f30  sub     rsp, 28h
0x180065f34  test    [rsp+28h+arg_20], 2
0x180065f39  mov     r9, rcx
0x180065f3c  jz      short loc_180065FA2
0x180065f3e  cmp     dword ptr [rcx+0Ch], 0
0x180065f42  jz      short loc_180065FA2
0x180065f44  cmp     edx, [rcx+0Ch]
0x180065f47  ja      short loc_180065FA2
0x180065f49  mov     rax, [rsp+28h+arg_28]
0x180065f4e  test    rax, rax
0x180065f51  jz      short loc_180065F6D
0x180065f53  cmp     dword ptr [rax+10h], 0
0x180065f57  jz      short loc_180065F60
0x180065f59  mov     eax, 8002000Eh
0x180065f5e  jmp     short loc_180065FA7
0x180065f60  cmp     dword ptr [rax+14h], 0
0x180065f64  jz      short loc_180065F6D
0x180065f66  mov     eax, 80020007h
0x180065f6b  jmp     short loc_180065FA7
0x180065f6d  mov     rcx, [rsp+28h+pvargDest]; pvargDest
0x180065f72  test    rcx, rcx
0x180065f75  jnz     short loc_180065F7B
0x180065f77  xor     eax, eax
0x180065f79  jmp     short loc_180065FA7
0x180065f7b  lea     eax, [rdx-1]
0x180065f7e  movsxd  rdx, eax
0x180065f81  mov     rax, [r9+18h]
0x180065f85  lea     r8, [rdx+rdx*2]
0x180065f89  mov     rdx, [rax+10h]
0x180065f8d  lea     rdx, [rdx+r8*8]; pvargSrc
0x180065f91  call    cs:__imp_VariantCopy
0x180065f97  xor     ecx, ecx
0x180065f99  test    eax, eax
0x180065f9b  cmovs   ecx, eax
0x180065f9e  mov     eax, ecx
0x180065fa0  jmp     short loc_180065FA7
0x180065fa2  mov     eax, 80020003h
0x180065fa7  add     rsp, 28h
0x180065fab  retn
```
