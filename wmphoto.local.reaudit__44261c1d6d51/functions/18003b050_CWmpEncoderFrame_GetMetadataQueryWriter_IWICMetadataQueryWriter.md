# CWmpEncoderFrame::GetMetadataQueryWriter(IWICMetadataQueryWriter * *)

- ea: `0x18003b050`
- end: `0x18003b10d`
- name: `?GetMetadataQueryWriter@CWmpEncoderFrame@@UEAAJPEAPEAUIWICMetadataQueryWriter@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataQueryWriter **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028ec0`
- `0x18002b078`
- `0x18002de30`
- `0x18003b050`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b073`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::GetMetadataQueryWriter(
        CWmpEncoderFrame *this,
        struct IWICMetadataQueryWriter **a2)
{
  char *v2; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  int v6; // ebx
  struct IWICComponentFactory *WICFactory; // rax
  void *v9; // [rsp+30h] [rbp+8h] BYREF
  char *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = (char *)this - 56;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v10 = v2;
  if ( LOBYTE(v4[1].DebugInfo) )
    EnterCriticalSection(v4);
  v9 = 0;
  if ( a2 )
  {
    v6 = CWmpCOMBase::InternalQueryInterface(
           (CWmpEncoderFrame *)((char *)this - 66376),
           &IID_IWICMetadataBlockWriter,
           &v9);
    if ( v6 >= 0 )
    {
      WICFactory = GetWICFactory();
      v6 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, void *, struct IWICMetadataQueryWriter **))WICFactory->lpVtbl->CreateQueryWriterFromBlockWriter)(
             WICFactory,
             v9,
             a2);
    }
    if ( v9 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      v9 = 0;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003b050  mov     [rsp+arg_10], rbx
0x18003b055  push    rdi
0x18003b056  sub     rsp, 20h
0x18003b05a  lea     rax, [rcx-38h]
0x18003b05e  mov     rbx, rcx
0x18003b061  lea     rcx, [rax+8]; lpCriticalSection
0x18003b065  mov     [rsp+28h+arg_8], rax
0x18003b06a  cmp     byte ptr [rcx+28h], 0
0x18003b06e  mov     rdi, rdx
0x18003b071  jz      short loc_18003B07F
0x18003b073  call    cs:__imp_EnterCriticalSection
0x18003b07a  nop     dword ptr [rax+rax+00h]
0x18003b07f  mov     [rsp+28h+arg_0], 0
0x18003b088  test    rdi, rdi
0x18003b08b  jnz     short loc_18003B094
0x18003b08d  mov     ebx, 80070057h
0x18003b092  jmp     short loc_18003B0F5
0x18003b094  lea     rcx, [rbx-10348h]; this
0x18003b09b  lea     r8, [rsp+28h+arg_0]; void **
0x18003b0a0  lea     rdx, IID_IWICMetadataBlockWriter; struct _GUID *
0x18003b0a7  call    ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x18003b0ac  mov     ebx, eax
0x18003b0ae  test    eax, eax
0x18003b0b0  js      short loc_18003B0D6
0x18003b0b2  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18003b0b7  mov     rdx, [rsp+28h+arg_0]
0x18003b0bc  mov     r9, rax
0x18003b0bf  mov     r8, rdi
0x18003b0c2  mov     rcx, [rax]
0x18003b0c5  mov     rax, [rcx+108h]
0x18003b0cc  mov     rcx, r9
0x18003b0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0d4  mov     ebx, eax
0x18003b0d6  mov     rcx, [rsp+28h+arg_0]
0x18003b0db  test    rcx, rcx
0x18003b0de  jz      short loc_18003B0F5
0x18003b0e0  mov     rax, [rcx]
0x18003b0e3  mov     rax, [rax+10h]
0x18003b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0ec  mov     [rsp+28h+arg_0], 0
0x18003b0f5  lea     rcx, [rsp+28h+arg_8]
0x18003b0fa  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003b0ff  mov     eax, ebx
0x18003b101  mov     rbx, [rsp+28h+arg_10]
0x18003b106  add     rsp, 20h
0x18003b10a  pop     rdi
0x18003b10b  retn
```
