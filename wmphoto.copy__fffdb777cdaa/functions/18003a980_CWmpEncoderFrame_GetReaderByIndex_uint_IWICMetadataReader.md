# CWmpEncoderFrame::GetReaderByIndex(uint,IWICMetadataReader * *)

- ea: `0x18003a980`
- end: `0x18003aa29`
- name: `?GetReaderByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataReader@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataReader **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002db34`
- `0x1800321c0`
- `0x18003a980`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a9aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a9aa`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::GetReaderByIndex(
        CWmpEncoderFrame *this,
        unsigned int a2,
        struct IWICMetadataReader **a3)
{
  char *v3; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  unsigned int v8; // edi
  int WriterByIndex; // eax
  struct IWICMetadataWriter *v10; // rbx
  struct IWICMetadataWriter *v12; // [rsp+30h] [rbp+8h] BYREF
  char *v13; // [rsp+40h] [rbp+18h] BYREF

  v3 = (char *)this - 64;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  v13 = v3;
  if ( LOBYTE(v5[1].DebugInfo) )
    EnterCriticalSection(v5);
  v12 = 0;
  if ( a3 )
  {
    WriterByIndex = CWmpEncoderFrame::GetWriterByIndex(this, a2, &v12);
    v10 = v12;
    v8 = WriterByIndex;
    if ( WriterByIndex >= 0 )
      v8 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, GUID *, struct IWICMetadataReader **))v12->lpVtbl->QueryInterface)(
             v12,
             &IID_IWICMetadataReader,
             a3);
    if ( v10 )
      ((void (__fastcall *)(struct IWICMetadataWriter *))v10->lpVtbl->Release)(v10);
  }
  else
  {
    v8 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v13);
  return v8;
}

```

## disassembly

```asm
0x18003a980  mov     [rsp+arg_8], rbx
0x18003a985  mov     [rsp+arg_18], rsi
0x18003a98a  push    rdi
0x18003a98b  sub     rsp, 20h
0x18003a98f  lea     rax, [rcx-40h]
0x18003a993  mov     rbx, rcx
0x18003a996  lea     rcx, [rax+8]; lpCriticalSection
0x18003a99a  mov     [rsp+28h+arg_10], rax
0x18003a99f  cmp     byte ptr [rcx+28h], 0
0x18003a9a3  mov     rsi, r8
0x18003a9a6  mov     edi, edx
0x18003a9a8  jz      short loc_18003A9B0
0x18003a9aa  call    cs:__imp_EnterCriticalSection
0x18003a9b0  mov     [rsp+28h+arg_0], 0
0x18003a9b9  test    rsi, rsi
0x18003a9bc  jnz     short loc_18003A9C5
0x18003a9be  mov     edi, 80070057h
0x18003a9c3  jmp     short loc_18003AA0D
0x18003a9c5  lea     r8, [rsp+28h+arg_0]; struct IWICMetadataWriter **
0x18003a9ca  mov     edx, edi; unsigned int
0x18003a9cc  mov     rcx, rbx; this
0x18003a9cf  call    ?GetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataWriter@@@Z; CWmpEncoderFrame::GetWriterByIndex(uint,IWICMetadataWriter * *)
0x18003a9d4  mov     rbx, [rsp+28h+arg_0]
0x18003a9d9  mov     edi, eax
0x18003a9db  test    eax, eax
0x18003a9dd  js      short loc_18003A9F9
0x18003a9df  mov     rax, [rbx]
0x18003a9e2  lea     rdx, IID_IWICMetadataReader
0x18003a9e9  mov     r8, rsi
0x18003a9ec  mov     rcx, rbx
0x18003a9ef  mov     rax, [rax]
0x18003a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9f7  mov     edi, eax
0x18003a9f9  test    rbx, rbx
0x18003a9fc  jz      short loc_18003AA0D
0x18003a9fe  mov     rax, [rbx]
0x18003aa01  mov     rcx, rbx
0x18003aa04  mov     rax, [rax+10h]
0x18003aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa0d  lea     rcx, [rsp+28h+arg_10]
0x18003aa12  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003aa17  mov     rbx, [rsp+28h+arg_8]
0x18003aa1c  mov     eax, edi
0x18003aa1e  mov     rsi, [rsp+28h+arg_18]
0x18003aa23  add     rsp, 20h
0x18003aa27  pop     rdi
0x18003aa28  retn
```
