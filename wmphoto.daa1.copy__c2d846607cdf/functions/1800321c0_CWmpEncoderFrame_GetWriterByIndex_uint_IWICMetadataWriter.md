# CWmpEncoderFrame::GetWriterByIndex(uint,IWICMetadataWriter * *)

- ea: `0x1800321c0`
- end: `0x18003227d`
- name: `?GetWriterByIndex@CWmpEncoderFrame@@UEAAJIPEAPEAUIWICMetadataWriter@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, unsigned int, struct IWICMetadataWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a980`

## callees

- `0x18002aec8`
- `0x1800321c0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800321e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800321e3`

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
0x1800321c0  push    rbx
0x1800321c2  push    rbp
0x1800321c3  push    rsi
0x1800321c4  push    rdi
0x1800321c5  push    r14
0x1800321c7  push    r15
0x1800321c9  sub     rsp, 38h
0x1800321cd  lea     rsi, [rcx-40h]
0x1800321d1  mov     r15, r8
0x1800321d4  cmp     byte ptr [rsi+30h], 0
0x1800321d8  mov     ebx, edx
0x1800321da  mov     r14, rcx
0x1800321dd  jz      short loc_1800321E9
0x1800321df  lea     rcx, [rsi+8]; lpCriticalSection
0x1800321e3  call    cs:__imp_EnterCriticalSection
0x1800321e9  test    ebx, ebx
0x1800321eb  jnz     short loc_180032254
0x1800321ed  test    r15, r15
0x1800321f0  jz      short loc_180032254
0x1800321f2  lea     rdi, [r14+98h]
0x1800321f9  cmp     [rdi], rbx
0x1800321fc  jnz     short loc_180032238
0x1800321fe  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x180032203  mov     r8, [r14+90h]
0x18003220a  lea     rdx, GUID_MetadataFormatIfd
0x180032211  mov     rcx, rax
0x180032214  mov     [rsp+68h+var_48], rdi
0x180032219  add     r8, 88h
0x180032220  xor     r9d, r9d
0x180032223  mov     rax, [rax]
0x180032226  mov     rax, [rax+0F0h]
0x18003222d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032232  mov     ebx, eax
0x180032234  test    eax, eax
0x180032236  js      short loc_180032259
0x180032238  mov     rcx, [rdi]
0x18003223b  mov     [r15], rcx
0x18003223e  mov     rcx, [rdi]
0x180032241  test    rcx, rcx
0x180032244  jz      short loc_180032259
0x180032246  mov     rdx, [rcx]
0x180032249  mov     rax, [rdx+8]
0x18003224d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032252  jmp     short loc_180032259
0x180032254  mov     ebx, 80070057h
0x180032259  test    rsi, rsi
0x18003225c  jz      short loc_18003226E
0x18003225e  cmp     byte ptr [rsi+30h], 0
0x180032262  jz      short loc_18003226E
0x180032264  lea     rcx, [rsi+8]; lpCriticalSection
0x180032268  call    cs:__imp_LeaveCriticalSection
0x18003226e  mov     eax, ebx
0x180032270  add     rsp, 38h
0x180032274  pop     r15
0x180032276  pop     r14
0x180032278  pop     rdi
0x180032279  pop     rsi
0x18003227a  pop     rbp
0x18003227b  pop     rbx
0x18003227c  retn
```
