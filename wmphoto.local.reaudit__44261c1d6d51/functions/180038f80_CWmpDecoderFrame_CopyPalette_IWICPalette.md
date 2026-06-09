# CWmpDecoderFrame::CopyPalette(IWICPalette *)

- ea: `0x180038f80`
- end: `0x180038fbf`
- name: `?CopyPalette@CWmpDecoderFrame@@UEAAJPEAUIWICPalette@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002de30`
- `0x180038f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038f9e`

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
0x180038f80  sub     rsp, 28h
0x180038f84  mov     rax, [rcx+1A8h]
0x180038f8b  add     rax, 18h
0x180038f8f  mov     [rsp+28h+arg_0], rax
0x180038f94  lea     rcx, [rax+8]; lpCriticalSection
0x180038f98  cmp     byte ptr [rcx+28h], 0
0x180038f9c  jz      short loc_180038FAA
0x180038f9e  call    cs:__imp_EnterCriticalSection
0x180038fa5  nop     dword ptr [rax+rax+00h]
0x180038faa  lea     rcx, [rsp+28h+arg_0]
0x180038faf  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180038fb4  mov     eax, 88982F45h
0x180038fb9  add     rsp, 28h
0x180038fbd  retn
```
