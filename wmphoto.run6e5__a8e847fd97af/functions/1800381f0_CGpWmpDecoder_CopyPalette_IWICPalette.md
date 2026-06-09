# CGpWmpDecoder::CopyPalette(IWICPalette *)

- ea: `0x1800381f0`
- end: `0x180038221`
- name: `?CopyPalette@CGpWmpDecoder@@UEAAJPEAUIWICPalette@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(CGpWmpDecoder *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002db34`
- `0x1800381f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038207`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038207`

## pseudocode

```c
__int64 __fastcall CGpWmpDecoder::CopyPalette(CGpWmpDecoder *this, struct IWICPalette *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = (char *)this - 56;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  if ( LOBYTE(v2[1].DebugInfo) )
    EnterCriticalSection(v2);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v4);
  return 2291674949LL;
}

```

## disassembly

```asm
0x1800381f0  sub     rsp, 28h
0x1800381f4  add     rcx, 0FFFFFFFFFFFFFFC8h
0x1800381f8  mov     [rsp+28h+arg_0], rcx
0x1800381fd  add     rcx, 8; lpCriticalSection
0x180038201  cmp     byte ptr [rcx+28h], 0
0x180038205  jz      short loc_18003820D
0x180038207  call    cs:__imp_EnterCriticalSection
0x18003820d  lea     rcx, [rsp+28h+arg_0]
0x180038212  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180038217  mov     eax, 88982F45h
0x18003821c  add     rsp, 28h
0x180038220  retn
```
