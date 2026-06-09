# CWmpEncoderFrame::AddWriter(IWICMetadataWriter *)

- ea: `0x18003a710`
- end: `0x18003a741`
- name: `?AddWriter@CWmpEncoderFrame@@UEAAJPEAUIWICMetadataWriter@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataWriter *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002db34`
- `0x18003a710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a727`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a727`

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
0x18003a710  sub     rsp, 28h
0x18003a714  add     rcx, 0FFFFFFFFFFFFFFC0h
0x18003a718  mov     [rsp+28h+arg_0], rcx
0x18003a71d  add     rcx, 8; lpCriticalSection
0x18003a721  cmp     byte ptr [rcx+28h], 0
0x18003a725  jz      short loc_18003A72D
0x18003a727  call    cs:__imp_EnterCriticalSection
0x18003a72d  lea     rcx, [rsp+28h+arg_0]
0x18003a732  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003a737  mov     eax, 88982F81h
0x18003a73c  add     rsp, 28h
0x18003a740  retn
```
