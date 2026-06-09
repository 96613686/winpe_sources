# RouterCorePrinterDriverInstalled(ushort const *,ushort const *,_GUID,_FILETIME,unsigned __int64,int *)

- ea: `0x18000a3c0`
- end: `0x18000a42d`
- name: `?RouterCorePrinterDriverInstalled@@YAJPEBG0U_GUID@@U_FILETIME@@_KPEAH@Z`
- size: `109`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, struct _FILETIME, unsigned __int64, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a3c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a410`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a410`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a41d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a41d`

## string_xrefs

- `0x18000a416`: `RouterCorePrinterDriverInstalled`

## pseudocode

```c
__int64 __fastcall RouterCorePrinterDriverInstalled(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _FILETIME a4,
        unsigned __int64 a5,
        int *a6)
{
  __int64 (__fastcall *v6)(const unsigned __int16 *, const unsigned __int16 *, __int128 *, struct _FILETIME, unsigned __int64, int *); // rax
  __int128 v8; // [rsp+40h] [rbp-18h] BYREF

  if ( g_bSandbox )
  {
    SetLastError(0x32u);
    OutputDebugStringA("RouterCorePrinterDriverInstalled");
    return 2147942450LL;
  }
  else
  {
    v6 = (__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, __int128 *, struct _FILETIME, unsigned __int64, int *))*((_QWORD *)g_pSpoolSvForwards + 189);
    v8 = (__int128)*a3;
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v6)(a1, a2, &v8, a4, a5, a6);
  }
}

```

## disassembly

```asm
0x18000a3c0  sub     rsp, 58h
0x18000a3c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000a3cb  jnz     short loc_18000A40B
0x18000a3cd  movups  xmm0, xmmword ptr [r8]
0x18000a3d1  mov     r8, [rsp+58h+arg_28]
0x18000a3d9  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000a3e0  mov     [rsp+58h+var_30], r8
0x18000a3e5  mov     r8, [rsp+58h+arg_20]
0x18000a3ed  mov     [rsp+58h+var_38], r8
0x18000a3f2  lea     r8, [rsp+58h+var_18]
0x18000a3f7  mov     rax, [rax+5E8h]
0x18000a3fe  movdqu  [rsp+58h+var_18], xmm0
0x18000a404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a409  jmp     short loc_18000A428
0x18000a40b  mov     ecx, 32h ; '2'; dwErrCode
0x18000a410  call    cs:__imp_SetLastError
0x18000a416  lea     rcx, aRoutercoreprin_0; "RouterCorePrinterDriverInstalled"
0x18000a41d  call    cs:__imp_OutputDebugStringA
0x18000a423  mov     eax, 80070032h
0x18000a428  add     rsp, 58h
0x18000a42c  retn
```
