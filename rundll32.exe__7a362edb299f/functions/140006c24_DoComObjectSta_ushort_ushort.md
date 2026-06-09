# _DoComObjectSta(ushort *,ushort *)

- ea: `0x140006c24`
- end: `0x140006ce0`
- name: `?_DoComObjectSta@@YAXPEAG0@Z`
- size: `188`
- prototype: `void __fastcall(LPCOLESTR lpsz, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007798`

## callees

- `0x1400015a0`
- `0x140006c24`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006c93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006c93`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140006c64`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140006c64`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006c4a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006c4a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006cc2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006cc2`

## pseudocode

```c
void __fastcall _DoComObjectSta(LPCOLESTR lpsz, unsigned __int16 *a2)
{
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-20h] BYREF

  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    pclsid = 0;
    if ( CLSIDFromString(lpsz, &pclsid) >= 0 )
    {
      ppv = 0;
      if ( CoCreateInstance(&pclsid, 0, 1u, &GUID_fce4bde0_4b68_4b80_8e9c_7426315a7388, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, a2);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x140006c24  mov     [rsp+arg_10], rbx
0x140006c29  push    rdi
0x140006c2a  sub     rsp, 50h
0x140006c2e  mov     rax, cs:__security_cookie
0x140006c35  xor     rax, rsp
0x140006c38  mov     [rsp+58h+var_10], rax
0x140006c3d  mov     rdi, rdx
0x140006c40  mov     rbx, rcx
0x140006c43  mov     edx, 6; dwCoInit
0x140006c48  xor     ecx, ecx; pvReserved
0x140006c4a  call    cs:__imp_CoInitializeEx
0x140006c50  test    eax, eax
0x140006c52  js      short loc_140006CC8
0x140006c54  xorps   xmm0, xmm0
0x140006c57  lea     rdx, [rsp+58h+pclsid]; pclsid
0x140006c5c  mov     rcx, rbx; lpsz
0x140006c5f  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x140006c64  call    cs:__imp_CLSIDFromString
0x140006c6a  test    eax, eax
0x140006c6c  js      short loc_140006CC2
0x140006c6e  xor     edx, edx; pUnkOuter
0x140006c70  mov     [rsp+58h+var_28], 0
0x140006c79  lea     rax, [rsp+58h+var_28]
0x140006c7e  lea     r9, _GUID_fce4bde0_4b68_4b80_8e9c_7426315a7388; riid
0x140006c85  mov     [rsp+58h+ppv], rax; ppv
0x140006c8a  lea     rcx, [rsp+58h+pclsid]; rclsid
0x140006c8f  lea     r8d, [rdx+1]; dwClsContext
0x140006c93  call    cs:__imp_CoCreateInstance
0x140006c99  test    eax, eax
0x140006c9b  js      short loc_140006CC2
0x140006c9d  mov     rcx, [rsp+58h+var_28]
0x140006ca2  mov     rdx, rdi
0x140006ca5  mov     rax, [rcx]
0x140006ca8  mov     rax, [rax+18h]
0x140006cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cb1  mov     rcx, [rsp+58h+var_28]
0x140006cb6  mov     rax, [rcx]
0x140006cb9  mov     rax, [rax+10h]
0x140006cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cc2  call    cs:__imp_CoUninitialize
0x140006cc8  mov     rcx, [rsp+58h+var_10]
0x140006ccd  xor     rcx, rsp; StackCookie
0x140006cd0  call    __security_check_cookie
0x140006cd5  mov     rbx, [rsp+58h+arg_10]
0x140006cda  add     rsp, 50h
0x140006cde  pop     rdi
0x140006cdf  retn
```
