# WdipDecrementDMShutdownSyncObject

- ea: `0x180006a90`
- end: `0x180006b36`
- name: `WdipDecrementDMShutdownSyncObject`
- size: `166`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042c0`
- `0x18000d228`

## callees

- `0x180002ba0`
- `0x1800068f0`
- `0x180006a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006aa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ae3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006b1b`

## pseudocode

```c
__int64 __fastcall WdipDecrementDMShutdownSyncObject(__int64 a1)
{
  unsigned int v2; // edi

  EnterCriticalSection(&g_csWDI);
  if ( !a1 )
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
      (int)L"WdipDecrementDMShutdownSyncObject",
      874,
      (int)L"Error = %d",
      87);
LABEL_3:
    LeaveCriticalSection(&g_csWDI);
    return v2;
  }
  v2 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 96), 0xFFFFFFFF) != 1 || *(_DWORD *)(a1 + 16) != 4 )
    goto LABEL_3;
  *(_DWORD *)(a1 + 16) = 8;
  LeaveCriticalSection(&g_csWDI);
  WdipUnloadDM(a1);
  return 0;
}

```

## disassembly

```asm
0x180006a90  mov     [rsp+arg_0], rbx
0x180006a95  push    rdi
0x180006a96  sub     rsp, 30h
0x180006a9a  mov     rbx, rcx
0x180006a9d  lea     rcx, g_csWDI; lpCriticalSection
0x180006aa4  call    cs:__imp_EnterCriticalSection
0x180006aaa  test    rbx, rbx
0x180006aad  jnz     short loc_180006AF6
0x180006aaf  lea     r9, aErrorD_0; "Error = %d"
0x180006ab6  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180006abe  mov     r8d, 36Ah; int
0x180006ac4  lea     rdx, aWdipdecrementd; "WdipDecrementDMShutdownSyncObject"
0x180006acb  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006ad2  mov     edi, 80070057h
0x180006ad7  call    WdipTraceError
0x180006adc  lea     rcx, g_csWDI; lpCriticalSection
0x180006ae3  call    cs:__imp_LeaveCriticalSection
0x180006ae9  mov     eax, edi
0x180006aeb  mov     rbx, [rsp+38h+arg_0]
0x180006af0  add     rsp, 30h
0x180006af4  pop     rdi
0x180006af5  retn
0x180006af6  xor     edi, edi
0x180006af8  mov     eax, 0FFFFFFFFh
0x180006afd  lock xadd [rbx+60h], eax
0x180006b02  cmp     eax, 1
0x180006b05  jnz     short loc_180006ADC
0x180006b07  cmp     dword ptr [rbx+10h], 4
0x180006b0b  jnz     short loc_180006ADC
0x180006b0d  lea     rcx, g_csWDI; lpCriticalSection
0x180006b14  mov     dword ptr [rbx+10h], 8
0x180006b1b  call    cs:__imp_LeaveCriticalSection
0x180006b21  mov     rcx, rbx
0x180006b24  call    WdipUnloadDM
0x180006b29  mov     rbx, [rsp+38h+arg_0]
0x180006b2e  xor     eax, eax
0x180006b30  add     rsp, 30h
0x180006b34  pop     rdi
0x180006b35  retn
```
