# RouterCorePrinterDriverInstalled(ushort const *,ushort const *,_GUID,_FILETIME,unsigned __int64,int *)

- ea: `0x18000ac30`
- end: `0x18000acaa`
- name: `?RouterCorePrinterDriverInstalled@@YAJPEBG0U_GUID@@U_FILETIME@@_KPEAH@Z`
- size: `122`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, struct _FILETIME, unsigned __int64, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000ac30`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ac93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ac93`

## string_xrefs

- `0x18000ac8c`: `RouterCorePrinterDriverInstalled`

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
0x18000ac30  sub     rsp, 58h
0x18000ac34  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ac3b  jnz     short loc_18000AC7B
0x18000ac3d  movups  xmm0, xmmword ptr [r8]
0x18000ac41  mov     r8, [rsp+58h+arg_28]
0x18000ac49  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ac50  mov     [rsp+58h+var_30], r8
0x18000ac55  mov     r8, [rsp+58h+arg_20]
0x18000ac5d  mov     [rsp+58h+var_38], r8
0x18000ac62  lea     r8, [rsp+58h+var_18]
0x18000ac67  mov     rax, [rax+5E8h]
0x18000ac6e  movdqu  [rsp+58h+var_18], xmm0
0x18000ac74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac79  jmp     short loc_18000ACA4
0x18000ac7b  mov     ecx, 32h ; '2'; dwErrCode
0x18000ac80  call    cs:__imp_SetLastError
0x18000ac87  nop     dword ptr [rax+rax+00h]
0x18000ac8c  lea     rcx, aRoutercoreprin_0; "RouterCorePrinterDriverInstalled"
0x18000ac93  call    cs:__imp_OutputDebugStringA
0x18000ac9a  nop     dword ptr [rax+rax+00h]
0x18000ac9f  mov     eax, 80070032h
0x18000aca4  add     rsp, 58h
0x18000aca8  retn
```
