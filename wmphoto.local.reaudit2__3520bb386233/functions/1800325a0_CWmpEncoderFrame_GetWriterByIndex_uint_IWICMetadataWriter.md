# CWmpEncoderFrame::GetWriterByIndex(uint,IWICMetadataWriter * *)

- ea: `0x1800325a0`
- end: `0x18003266a`
- name: `?GetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataWriter@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003b120`

## callees

- `0x18002b078`
- `0x1800325a0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003264e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003264e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800325c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800325c3`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::GetWriterByIndex(
        CWmpEncoderFrame *this,
        unsigned int a2,
        struct IWICMetadataWriter **a3)
{
  char *v3; // rsi
  __int64 v5; // rbx
  _QWORD *v7; // rdi
  struct IWICComponentFactory *WICFactory; // rax

  v3 = (char *)this - 64;
  v5 = a2;
  if ( *((_BYTE *)this - 16) )
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  if ( (_DWORD)v5 || !a3 )
  {
    LODWORD(v5) = -2147024809;
  }
  else
  {
    v7 = (_QWORD *)((char *)this + 152);
    if ( *((_QWORD *)this + 19) != v5
      || (WICFactory = GetWICFactory(),
          LODWORD(v5) = ((__int64 (__fastcall *)(struct IWICComponentFactory *, GUID *, __int64, _QWORD, char *))WICFactory->lpVtbl->CreateMetadataWriter)(
                          WICFactory,
                          &GUID_MetadataFormatIfd,
                          *((_QWORD *)this + 18) + 136LL,
                          0,
                          (char *)this + 152),
          (int)v5 >= 0) )
    {
      *a3 = (struct IWICMetadataWriter *)*v7;
      if ( *v7 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
    }
  }
  if ( v3 && v3[48] )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800325a0  push    rbx
0x1800325a2  push    rbp
0x1800325a3  push    rsi
0x1800325a4  push    rdi
0x1800325a5  push    r14
0x1800325a7  push    r15
0x1800325a9  sub     rsp, 38h
0x1800325ad  lea     rsi, [rcx-40h]
0x1800325b1  mov     r15, r8
0x1800325b4  cmp     byte ptr [rsi+30h], 0
0x1800325b8  mov     ebx, edx
0x1800325ba  mov     r14, rcx
0x1800325bd  jz      short loc_1800325CF
0x1800325bf  lea     rcx, [rsi+8]; lpCriticalSection
0x1800325c3  call    cs:__imp_EnterCriticalSection
0x1800325ca  nop     dword ptr [rax+rax+00h]
0x1800325cf  test    ebx, ebx
0x1800325d1  jnz     short loc_18003263A
0x1800325d3  test    r15, r15
0x1800325d6  jz      short loc_18003263A
0x1800325d8  lea     rdi, [r14+98h]
0x1800325df  cmp     [rdi], rbx
0x1800325e2  jnz     short loc_18003261E
0x1800325e4  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x1800325e9  mov     r8, [r14+90h]
0x1800325f0  lea     rdx, GUID_MetadataFormatIfd
0x1800325f7  mov     rcx, rax
0x1800325fa  mov     [rsp+68h+var_48], rdi
0x1800325ff  add     r8, 88h
0x180032606  xor     r9d, r9d
0x180032609  mov     rax, [rax]
0x18003260c  mov     rax, [rax+0F0h]
0x180032613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032618  mov     ebx, eax
0x18003261a  test    eax, eax
0x18003261c  js      short loc_18003263F
0x18003261e  mov     rcx, [rdi]
0x180032621  mov     [r15], rcx
0x180032624  mov     rcx, [rdi]
0x180032627  test    rcx, rcx
0x18003262a  jz      short loc_18003263F
0x18003262c  mov     rdx, [rcx]
0x18003262f  mov     rax, [rdx+8]
0x180032633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032638  jmp     short loc_18003263F
0x18003263a  mov     ebx, 80070057h
0x18003263f  test    rsi, rsi
0x180032642  jz      short loc_18003265A
0x180032644  cmp     byte ptr [rsi+30h], 0
0x180032648  jz      short loc_18003265A
0x18003264a  lea     rcx, [rsi+8]; lpCriticalSection
0x18003264e  call    cs:__imp_LeaveCriticalSection
0x180032655  nop     dword ptr [rax+rax+00h]
0x18003265a  mov     eax, ebx
0x18003265c  add     rsp, 38h
0x180032660  pop     r15
0x180032662  pop     r14
0x180032664  pop     rdi
0x180032665  pop     rsi
0x180032666  pop     rbp
0x180032667  pop     rbx
0x180032668  retn
```
