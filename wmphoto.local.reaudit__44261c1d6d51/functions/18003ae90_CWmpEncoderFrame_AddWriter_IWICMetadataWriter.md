# CWmpEncoderFrame::AddWriter(IWICMetadataWriter *)

- ea: `0x18003ae90`
- end: `0x18003aec8`
- name: `?AddWriter@CWmpEncoderFrame@@UEAAJPEAUIWICMetadataWriter@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataWriter *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002de30`
- `0x18003ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aea7`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::AddWriter(CWmpEncoderFrame *this, struct IWICMetadataWriter *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  char *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = (char *)this - 64;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  if ( LOBYTE(v2[1].DebugInfo) )
    EnterCriticalSection(v2);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v4);
  return 2291675009LL;
}

```

## disassembly

```asm
0x18003ae90  sub     rsp, 28h
0x18003ae94  add     rcx, 0FFFFFFFFFFFFFFC0h
0x18003ae98  mov     [rsp+28h+arg_0], rcx
0x18003ae9d  add     rcx, 8; lpCriticalSection
0x18003aea1  cmp     byte ptr [rcx+28h], 0
0x18003aea5  jz      short loc_18003AEB3
0x18003aea7  call    cs:__imp_EnterCriticalSection
0x18003aeae  nop     dword ptr [rax+rax+00h]
0x18003aeb3  lea     rcx, [rsp+28h+arg_0]
0x18003aeb8  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003aebd  mov     eax, 88982F81h
0x18003aec2  add     rsp, 28h
0x18003aec6  retn
```
