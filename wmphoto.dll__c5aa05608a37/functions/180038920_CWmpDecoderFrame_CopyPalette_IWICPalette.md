# CWmpDecoderFrame::CopyPalette(IWICPalette *)

- ea: `0x180038920`
- end: `0x180038958`
- name: `?CopyPalette@CWmpDecoderFrame@@UEAAJPEAUIWICPalette@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002db34`
- `0x180038920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003893e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003893e`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::CopyPalette(CWmpDecoderFrame *this, struct IWICPalette *a2)
{
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 53) + 24LL;
  if ( *(_BYTE *)(v3 + 48) )
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  CGuard<CMTALock>::~CGuard<CMTALock>(&v3);
  return 2291674949LL;
}

```

## disassembly

```asm
0x180038920  sub     rsp, 28h
0x180038924  mov     rax, [rcx+1A8h]
0x18003892b  add     rax, 18h
0x18003892f  mov     [rsp+28h+arg_0], rax
0x180038934  lea     rcx, [rax+8]; lpCriticalSection
0x180038938  cmp     byte ptr [rcx+28h], 0
0x18003893c  jz      short loc_180038944
0x18003893e  call    cs:__imp_EnterCriticalSection
0x180038944  lea     rcx, [rsp+28h+arg_0]
0x180038949  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003894e  mov     eax, 88982F45h
0x180038953  add     rsp, 28h
0x180038957  retn
```
