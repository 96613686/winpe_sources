# CWmpEncoderFrame::GetReaderByIndex(uint,IWICMetadataReader * *)

- ea: `0x18003b120`
- end: `0x18003b1d0`
- name: `?GetReaderByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataReader@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataReader **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002de30`
- `0x1800325a0`
- `0x18003b120`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b14a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b14a`

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
0x18003b120  mov     [rsp+arg_8], rbx
0x18003b125  mov     [rsp+arg_18], rsi
0x18003b12a  push    rdi
0x18003b12b  sub     rsp, 20h
0x18003b12f  lea     rax, [rcx-40h]
0x18003b133  mov     rbx, rcx
0x18003b136  lea     rcx, [rax+8]; lpCriticalSection
0x18003b13a  mov     [rsp+28h+arg_10], rax
0x18003b13f  cmp     byte ptr [rcx+28h], 0
0x18003b143  mov     rsi, r8
0x18003b146  mov     edi, edx
0x18003b148  jz      short loc_18003B156
0x18003b14a  call    cs:__imp_EnterCriticalSection
0x18003b151  nop     dword ptr [rax+rax+00h]
0x18003b156  mov     [rsp+28h+arg_0], 0
0x18003b15f  test    rsi, rsi
0x18003b162  jnz     short loc_18003B16B
0x18003b164  mov     edi, 80070057h
0x18003b169  jmp     short loc_18003B1B3
0x18003b16b  lea     r8, [rsp+28h+arg_0]; struct IWICMetadataWriter **
0x18003b170  mov     edx, edi; unsigned int
0x18003b172  mov     rcx, rbx; this
0x18003b175  call    ?GetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataWriter@@@Z; CWmpEncoderFrame::GetWriterByIndex(uint,IWICMetadataWriter * *)
0x18003b17a  mov     rbx, [rsp+28h+arg_0]
0x18003b17f  mov     edi, eax
0x18003b181  test    eax, eax
0x18003b183  js      short loc_18003B19F
0x18003b185  mov     rax, [rbx]
0x18003b188  lea     rdx, IID_IWICMetadataReader
0x18003b18f  mov     r8, rsi
0x18003b192  mov     rcx, rbx
0x18003b195  mov     rax, [rax]
0x18003b198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b19d  mov     edi, eax
0x18003b19f  test    rbx, rbx
0x18003b1a2  jz      short loc_18003B1B3
0x18003b1a4  mov     rax, [rbx]
0x18003b1a7  mov     rcx, rbx
0x18003b1aa  mov     rax, [rax+10h]
0x18003b1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1b3  lea     rcx, [rsp+28h+arg_10]
0x18003b1b8  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003b1bd  mov     rbx, [rsp+28h+arg_8]
0x18003b1c2  mov     eax, edi
0x18003b1c4  mov     rsi, [rsp+28h+arg_18]
0x18003b1c9  add     rsp, 20h
0x18003b1cd  pop     rdi
0x18003b1ce  retn
```
