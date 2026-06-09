# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800063fc`
- end: `0x1800064eb`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800072a4`

## callees

- `0x1800063fc`
- `0x1800076c0`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006458`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006458`
- `ole32!CoGetObject` at `0x1800064c1`
- `ole32!CoGetObject` at `0x1800064c1`

## pseudocode

```c
HRESULT __fastcall CoCreateInstanceAsAdmin(HWND a1, const struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  HRESULT result; // eax
  BIND_OPTS pBindOptions[3]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR sz[56]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszName[304]; // [rsp+C0h] [rbp-40h] BYREF

  *a4 = 0;
  memset(pBindOptions, 0, sizeof(pBindOptions));
  if ( !StringFromGUID2(&CLSID_WscAdmin, sz, 50) )
    return -2147024882;
  result = StringCchPrintfW(
             pszName,
             0x12Cu,
             L"Elevation:Administrator!new:%s",
             sz,
             *(_QWORD *)&pBindOptions[0].cbStruct,
             *(_QWORD *)&pBindOptions[0].grfMode,
             *(_OWORD *)&pBindOptions[1],
             *(_OWORD *)&pBindOptions[2]);
  if ( result >= 0 )
  {
    pBindOptions[0].cbStruct = 48;
    *(_QWORD *)&pBindOptions[2].grfMode = a1;
    pBindOptions[1].grfFlags = 4;
    *(_OWORD *)&pBindOptions[0].grfFlags = 0;
    *(_OWORD *)&pBindOptions[1].grfMode = 0;
    return CoGetObject(pszName, pBindOptions, &GUID_49acaa99_f009_4524_9d2a_d751c9a38f60, a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800063fc  mov     [rsp-8+arg_8], rbx
0x180006401  mov     [rsp-8+arg_10], rdi
0x180006406  push    rbp
0x180006407  lea     rbp, [rsp-230h]
0x18000640f  sub     rsp, 330h
0x180006416  mov     rax, cs:__security_cookie
0x18000641d  xor     rax, rsp
0x180006420  mov     [rbp+230h+var_10], rax
0x180006427  xorps   xmm0, xmm0
0x18000642a  mov     qword ptr [r9], 0
0x180006431  mov     rdi, rcx
0x180006434  lea     rdx, [rsp+330h+sz]; lpsz
0x180006439  lea     rcx, CLSID_WscAdmin; rguid
0x180006440  mov     r8d, 32h ; '2'; cchMax
0x180006446  movups  xmmword ptr [rsp+330h+pBindOptions.cbStruct], xmm0
0x18000644b  mov     rbx, r9
0x18000644e  movups  [rsp+330h+var_300], xmm0
0x180006453  movups  [rsp+330h+var_2F0], xmm0
0x180006458  call    cs:__imp_StringFromGUID2
0x18000645e  test    eax, eax
0x180006460  jnz     short loc_180006469
0x180006462  mov     eax, 8007000Eh
0x180006467  jmp     short loc_1800064C7
0x180006469  lea     r9, [rsp+330h+sz]
0x18000646e  mov     edx, 12Ch; unsigned __int64
0x180006473  lea     r8, aElevationAdmin; "Elevation:Administrator!new:%s"
0x18000647a  lea     rcx, [rbp+230h+pszName]; unsigned __int16 *
0x18000647e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006483  test    eax, eax
0x180006485  js      short loc_1800064C7
0x180006487  xorps   xmm0, xmm0
0x18000648a  mov     [rsp+330h+pBindOptions.cbStruct], 30h ; '0'
0x180006492  xorps   xmm1, xmm1
0x180006495  mov     qword ptr [rsp+330h+var_2F0+8], rdi
0x18000649a  mov     r9, rbx; ppv
0x18000649d  mov     dword ptr [rsp+330h+var_300+4], 4
0x1800064a5  lea     r8, _GUID_49acaa99_f009_4524_9d2a_d751c9a38f60; riid
0x1800064ac  lea     rdx, [rsp+330h+pBindOptions]; pBindOptions
0x1800064b1  lea     rcx, [rbp+230h+pszName]; pszName
0x1800064b5  movdqu  xmmword ptr [rsp+330h+pBindOptions.grfFlags], xmm0
0x1800064bb  movdqu  [rsp+330h+var_300+8], xmm1
0x1800064c1  call    cs:__imp_CoGetObject
0x1800064c7  mov     rcx, [rbp+230h+var_10]
0x1800064ce  xor     rcx, rsp; StackCookie
0x1800064d1  call    __security_check_cookie
0x1800064d6  lea     r11, [rsp+330h+var_s0]
0x1800064de  mov     rbx, [r11+18h]
0x1800064e2  mov     rdi, [r11+20h]
0x1800064e6  mov     rsp, r11
0x1800064e9  pop     rbp
0x1800064ea  retn
```
