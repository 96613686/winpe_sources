# CWmpDecoderFrame::GetReaderByIndex(uint,IWICMetadataReader * *)

- ea: `0x180032690`
- end: `0x180032738`
- name: `?GetReaderByIndex@CWmpDecoderFrame@@UEAAJIPEAPEAUIWICMetadataReader@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, unsigned int, struct IWICMetadataReader **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003a5c0`

## callees

- `0x18002b160`
- `0x180032690`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003271c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003271c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326bb`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::GetReaderByIndex(CWmpDecoderFrame *this, int a2, struct IWICMetadataReader **a3)
{
  __int64 v4; // rdi
  int v7; // ebx
  __int64 v8; // rcx

  v4 = *((_QWORD *)this + 51) + 24LL;
  if ( *(_BYTE *)(*((_QWORD *)this + 51) + 72LL) )
    EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 51) + 32LL));
  if ( !a3 )
    goto LABEL_8;
  v7 = CWmpCodecBase::HrTestStateMinimum((CWmpDecoderFrame *)((char *)this - 66336), 3);
  if ( v7 < 0 )
    goto LABEL_9;
  if ( a2 )
  {
LABEL_8:
    v7 = -2147024809;
    goto LABEL_9;
  }
  v7 = 0;
  *a3 = (struct IWICMetadataReader *)*((_QWORD *)this + 13);
  v8 = *((_QWORD *)this + 13);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_9:
  if ( v4 && *(_BYTE *)(v4 + 48) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032690  push    rbx
0x180032692  push    rbp
0x180032693  push    rsi
0x180032694  push    rdi
0x180032695  push    r14
0x180032697  push    r15
0x180032699  sub     rsp, 28h
0x18003269d  mov     rdi, [rcx+198h]
0x1800326a4  mov     r14, r8
0x1800326a7  add     rdi, 18h
0x1800326ab  mov     r15d, edx
0x1800326ae  mov     rbp, rcx
0x1800326b1  cmp     byte ptr [rdi+30h], 0
0x1800326b5  jz      short loc_1800326C7
0x1800326b7  lea     rcx, [rdi+8]; lpCriticalSection
0x1800326bb  call    cs:__imp_EnterCriticalSection
0x1800326c2  nop     dword ptr [rax+rax+00h]
0x1800326c7  test    r14, r14
0x1800326ca  jz      short loc_180032708
0x1800326cc  mov     edx, 3; int
0x1800326d1  lea     rcx, [rbp-10320h]; this
0x1800326d8  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x1800326dd  mov     ebx, eax
0x1800326df  test    eax, eax
0x1800326e1  js      short loc_18003270D
0x1800326e3  test    r15d, r15d
0x1800326e6  jnz     short loc_180032708
0x1800326e8  mov     rax, [rbp+68h]
0x1800326ec  xor     ebx, ebx
0x1800326ee  mov     [r14], rax
0x1800326f1  mov     rcx, [rbp+68h]
0x1800326f5  test    rcx, rcx
0x1800326f8  jz      short loc_18003270D
0x1800326fa  mov     rax, [rcx]
0x1800326fd  mov     rax, [rax+8]
0x180032701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032706  jmp     short loc_18003270D
0x180032708  mov     ebx, 80070057h
0x18003270d  test    rdi, rdi
0x180032710  jz      short loc_180032728
0x180032712  cmp     byte ptr [rdi+30h], 0
0x180032716  jz      short loc_180032728
0x180032718  lea     rcx, [rdi+8]; lpCriticalSection
0x18003271c  call    cs:__imp_LeaveCriticalSection
0x180032723  nop     dword ptr [rax+rax+00h]
0x180032728  mov     eax, ebx
0x18003272a  add     rsp, 28h
0x18003272e  pop     r15
0x180032730  pop     r14
0x180032732  pop     rdi
0x180032733  pop     rsi
0x180032734  pop     rbp
0x180032735  pop     rbx
0x180032736  retn
```
