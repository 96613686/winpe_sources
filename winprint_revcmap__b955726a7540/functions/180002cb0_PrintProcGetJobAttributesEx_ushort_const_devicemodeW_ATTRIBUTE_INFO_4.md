# PrintProcGetJobAttributesEx(ushort const *,_devicemodeW *,_ATTRIBUTE_INFO_4 *)

- ea: `0x180002cb0`
- end: `0x180002ea7`
- name: `?PrintProcGetJobAttributesEx@@YAHPEBGPEAU_devicemodeW@@PEAU_ATTRIBUTE_INFO_4@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, struct _devicemodeW *, struct _ATTRIBUTE_INFO_4 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002400`

## callees

- `0x180002cb0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002cf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002cf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002d88`
- `WINSPOOL!ClosePrinter` at `0x180002e6f`
- `WINSPOOL!ClosePrinter` at `0x180002e6f`
- `WINSPOOL!OpenPrinterW` at `0x180002d53`
- `WINSPOOL!OpenPrinterW` at `0x180002d53`

## pseudocode

```c
HMODULE __fastcall PrintProcGetJobAttributesEx(
        LPWSTR pPrinterName,
        struct _devicemodeW *a2,
        struct _ATTRIBUTE_INFO_4 *a3)
{
  HMODULE v6; // rbx
  unsigned int v7; // edi
  HMODULE result; // rax
  HMODULE v9; // r15
  FARPROC ProcAddress; // rax
  HMODULE v11; // rax
  FARPROC v12; // rax
  unsigned int (__fastcall *v13)(HANDLE, struct _devicemodeW *, __int64, struct _ATTRIBUTE_INFO_4 *); // rdi
  HANDLE phPrinter; // [rsp+78h] [rbp+20h] BYREF

  phPrinter = 0;
  v6 = 0;
  v7 = 0;
  if ( qword_18000D4D0 && qword_18000D4C8 )
    goto LABEL_25;
  result = GetModuleHandleW(L"winspool.drv");
  v9 = result;
  if ( !result )
    return result;
  qword_18000D4D0 = (__int64)GetProcAddress(result, (LPCSTR)0xD4);
  ProcAddress = GetProcAddress(v9, (LPCSTR)0xD6);
  qword_18000D4C8 = (__int64)ProcAddress;
  if ( qword_18000D4D0 )
  {
    if ( ProcAddress )
    {
LABEL_25:
      if ( OpenPrinterW(pPrinterName, &phPrinter, 0) )
      {
        v11 = (HMODULE)((__int64 (__fastcall *)(HANDLE))qword_18000D4D0)(phPrinter);
        v6 = v11;
        if ( v11 )
        {
          v12 = GetProcAddress(v11, "DrvQueryJobAttributes");
          v13 = (unsigned int (__fastcall *)(HANDLE, struct _devicemodeW *, __int64, struct _ATTRIBUTE_INFO_4 *))v12;
          if ( !v12 )
            goto LABEL_13;
          if ( ((unsigned int (__fastcall *)(HANDLE, struct _devicemodeW *, __int64, struct _ATTRIBUTE_INFO_4 *))v12)(
                 phPrinter,
                 a2,
                 4,
                 a3) )
          {
LABEL_17:
            v7 = 1;
            goto LABEL_18;
          }
          if ( v13(phPrinter, a2, 3, a3) )
          {
LABEL_16:
            *(_QWORD *)&a3->dwNupDirection = 1;
            a3->dwDuplexFlags = 0;
            a3->dwScalingPercentX = 100;
            a3->dwScalingPercentY = 100;
            goto LABEL_17;
          }
          if ( v13(phPrinter, a2, 2, a3) )
          {
LABEL_15:
            a3->dmPrintQuality = a2->dmPrintQuality;
            a3->dmYResolution = a2->dmYResolution;
            goto LABEL_16;
          }
          if ( !v13(phPrinter, a2, 1, a3) )
          {
LABEL_13:
            a3->dwJobNumberOfPagesPerSide = 1;
            *(_QWORD *)&a3->dwDrvNumberOfPagesPerSide = 1;
            *(_QWORD *)&a3->dwJobPageOrderFlags = 0;
            a3->dwJobNumberOfCopies = a2->dmCopies;
            a3->dwDrvNumberOfCopies = a2->dmCopies;
          }
          a3->dwColorOptimization = 0;
          goto LABEL_15;
        }
      }
    }
  }
LABEL_18:
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( v6 )
    ((void (__fastcall *)(HMODULE, __int64))qword_18000D4C8)(v6, 1);
  return (HMODULE)v7;
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp+arg_0], rbx
0x180002cb5  mov     [rsp+arg_8], rbp
0x180002cba  push    rsi
0x180002cbb  push    rdi
0x180002cbc  push    r12
0x180002cbe  push    r14
0x180002cc0  push    r15
0x180002cc2  sub     rsp, 30h
0x180002cc6  xor     r12d, r12d
0x180002cc9  mov     r14, r8
0x180002ccc  cmp     cs:qword_18000D4D0, r12
0x180002cd3  mov     rbp, rdx
0x180002cd6  mov     rsi, rcx
0x180002cd9  mov     [rsp+58h+phPrinter], r12
0x180002cde  mov     ebx, r12d
0x180002ce1  mov     edi, r12d
0x180002ce4  jz      short loc_180002CEF
0x180002ce6  cmp     cs:qword_18000D4C8, rbx
0x180002ced  jnz     short loc_180002D48
0x180002cef  lea     rcx, LibFileName; "winspool.drv"
0x180002cf6  call    cs:__imp_GetModuleHandleW
0x180002cfc  mov     r15, rax
0x180002cff  test    rax, rax
0x180002d02  jz      loc_180002E90
0x180002d08  mov     edx, 0D4h; lpProcName
0x180002d0d  mov     rcx, r15; hModule
0x180002d10  call    cs:__imp_GetProcAddress
0x180002d16  mov     edx, 0D6h; lpProcName
0x180002d1b  mov     rcx, r15; hModule
0x180002d1e  mov     cs:qword_18000D4D0, rax
0x180002d25  call    cs:__imp_GetProcAddress
0x180002d2b  cmp     cs:qword_18000D4D0, rbx
0x180002d32  mov     cs:qword_18000D4C8, rax
0x180002d39  jz      loc_180002E65
0x180002d3f  test    rax, rax
0x180002d42  jz      loc_180002E65
0x180002d48  xor     r8d, r8d; pDefault
0x180002d4b  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x180002d50  mov     rcx, rsi; pPrinterName
0x180002d53  call    cs:__imp_OpenPrinterW
0x180002d59  test    eax, eax
0x180002d5b  jz      loc_180002E65
0x180002d61  mov     rcx, [rsp+58h+phPrinter]
0x180002d66  mov     rax, cs:qword_18000D4D0
0x180002d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d72  mov     rbx, rax
0x180002d75  test    rax, rax
0x180002d78  jz      loc_180002E65
0x180002d7e  lea     rdx, ProcName; "DrvQueryJobAttributes"
0x180002d85  mov     rcx, rax; hModule
0x180002d88  call    cs:__imp_GetProcAddress
0x180002d8e  mov     rdi, rax
0x180002d91  test    rax, rax
0x180002d94  jz      short loc_180002E0B
0x180002d96  mov     rcx, [rsp+58h+phPrinter]
0x180002d9b  mov     r9, r14
0x180002d9e  mov     r8d, 4
0x180002da4  mov     rdx, rbp
0x180002da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dac  test    eax, eax
0x180002dae  jnz     loc_180002E60
0x180002db4  mov     rcx, [rsp+58h+phPrinter]
0x180002db9  mov     r9, r14
0x180002dbc  mov     r8d, 3
0x180002dc2  mov     rdx, rbp
0x180002dc5  mov     rax, rdi
0x180002dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dcd  test    eax, eax
0x180002dcf  jnz     short loc_180002E44
0x180002dd1  mov     rcx, [rsp+58h+phPrinter]
0x180002dd6  mov     r9, r14
0x180002dd9  mov     r8d, 2
0x180002ddf  mov     rdx, rbp
0x180002de2  mov     rax, rdi
0x180002de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dea  test    eax, eax
0x180002dec  jnz     short loc_180002E32
0x180002dee  mov     rcx, [rsp+58h+phPrinter]
0x180002df3  mov     r9, r14
0x180002df6  mov     r8d, 1
0x180002dfc  mov     rdx, rbp
0x180002dff  mov     rax, rdi
0x180002e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e07  test    eax, eax
0x180002e09  jnz     short loc_180002E2E
0x180002e0b  mov     dword ptr [r14], 1
0x180002e12  mov     qword ptr [r14+4], 1
0x180002e1a  mov     [r14+0Ch], r12
0x180002e1e  movsx   eax, word ptr [rbp+56h]
0x180002e22  mov     [r14+14h], eax
0x180002e26  movsx   eax, word ptr [rbp+56h]
0x180002e2a  mov     [r14+18h], eax
0x180002e2e  mov     [r14+1Ch], r12d
0x180002e32  movzx   eax, word ptr [rbp+5Ah]
0x180002e36  mov     [r14+20h], ax
0x180002e3b  movzx   eax, word ptr [rbp+60h]
0x180002e3f  mov     [r14+22h], ax
0x180002e44  mov     qword ptr [r14+28h], 1
0x180002e4c  mov     [r14+24h], r12d
0x180002e50  mov     dword ptr [r14+30h], 64h ; 'd'
0x180002e58  mov     dword ptr [r14+34h], 64h ; 'd'
0x180002e60  mov     edi, 1
0x180002e65  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x180002e6a  test    rcx, rcx
0x180002e6d  jz      short loc_180002E75
0x180002e6f  call    cs:__imp_ClosePrinter
0x180002e75  test    rbx, rbx
0x180002e78  jz      short loc_180002E8E
0x180002e7a  mov     rax, cs:qword_18000D4C8
0x180002e81  mov     edx, 1
0x180002e86  mov     rcx, rbx
0x180002e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8e  mov     eax, edi
0x180002e90  mov     rbx, [rsp+58h+arg_0]
0x180002e95  mov     rbp, [rsp+58h+arg_8]
0x180002e9a  add     rsp, 30h
0x180002e9e  pop     r15
0x180002ea0  pop     r14
0x180002ea2  pop     r12
0x180002ea4  pop     rdi
0x180002ea5  pop     rsi
0x180002ea6  retn
```
