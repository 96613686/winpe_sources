# CGpWmpDecoder::CopyPalette(IWICPalette *)

- ea: `0x180038830`
- end: `0x180038868`
- name: `?CopyPalette@CGpWmpDecoder@@UEAAJPEAUIWICPalette@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(CGpWmpDecoder *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002de30`
- `0x180038830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038847`

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
0x180038830  sub     rsp, 28h
0x180038834  add     rcx, 0FFFFFFFFFFFFFFC8h
0x180038838  mov     [rsp+28h+arg_0], rcx
0x18003883d  add     rcx, 8; lpCriticalSection
0x180038841  cmp     byte ptr [rcx+28h], 0
0x180038845  jz      short loc_180038853
0x180038847  call    cs:__imp_EnterCriticalSection
0x18003884e  nop     dword ptr [rax+rax+00h]
0x180038853  lea     rcx, [rsp+28h+arg_0]
0x180038858  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003885d  mov     eax, 88982F45h
0x180038862  add     rsp, 28h
0x180038866  retn
```
