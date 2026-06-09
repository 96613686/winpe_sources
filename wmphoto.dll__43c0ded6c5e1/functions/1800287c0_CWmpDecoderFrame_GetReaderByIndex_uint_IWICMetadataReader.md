# CWmpDecoderFrame::GetReaderByIndex(uint,IWICMetadataReader * *)

- ea: `0x1800287c0`
- end: `0x18002885b`
- name: `?GetReaderByIndex@CWmpDecoderFrame@@UEAAJIPEAPEAUIWICMetadataReader@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *this, int, struct IWICMetadataReader **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180039e90`

## callees

- `0x1800287c0`
- `0x180028870`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800287eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800287eb`

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
0x1800287c0  push    rbx
0x1800287c2  push    rbp
0x1800287c3  push    rsi
0x1800287c4  push    rdi
0x1800287c5  push    r14
0x1800287c7  push    r15
0x1800287c9  sub     rsp, 28h
0x1800287cd  mov     rdi, [rcx+198h]
0x1800287d4  mov     r14, r8
0x1800287d7  add     rdi, 18h
0x1800287db  mov     r15d, edx
0x1800287de  mov     rbp, rcx
0x1800287e1  cmp     byte ptr [rdi+30h], 0
0x1800287e5  jz      short loc_1800287F1
0x1800287e7  lea     rcx, [rdi+8]; lpCriticalSection
0x1800287eb  call    cs:__imp_EnterCriticalSection
0x1800287f1  test    r14, r14
0x1800287f4  jz      short loc_180028832
0x1800287f6  mov     edx, 3; int
0x1800287fb  lea     rcx, [rbp-10320h]; this
0x180028802  call    ?HrTestStateMinimum@CWmpCodecBase@@UEAAJH@Z; CWmpCodecBase::HrTestStateMinimum(int)
0x180028807  mov     ebx, eax
0x180028809  test    eax, eax
0x18002880b  js      short loc_180028837
0x18002880d  test    r15d, r15d
0x180028810  jnz     short loc_180028832
0x180028812  mov     rax, [rbp+68h]
0x180028816  xor     ebx, ebx
0x180028818  mov     [r14], rax
0x18002881b  mov     rcx, [rbp+68h]
0x18002881f  test    rcx, rcx
0x180028822  jz      short loc_180028837
0x180028824  mov     rax, [rcx]
0x180028827  mov     rax, [rax+8]
0x18002882b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028830  jmp     short loc_180028837
0x180028832  mov     ebx, 80070057h
0x180028837  test    rdi, rdi
0x18002883a  jz      short loc_18002884C
0x18002883c  cmp     byte ptr [rdi+30h], 0
0x180028840  jz      short loc_18002884C
0x180028842  lea     rcx, [rdi+8]; lpCriticalSection
0x180028846  call    cs:__imp_LeaveCriticalSection
0x18002884c  mov     eax, ebx
0x18002884e  add     rsp, 28h
0x180028852  pop     r15
0x180028854  pop     r14
0x180028856  pop     rdi
0x180028857  pop     rsi
0x180028858  pop     rbp
0x180028859  pop     rbx
0x18002885a  retn
```
