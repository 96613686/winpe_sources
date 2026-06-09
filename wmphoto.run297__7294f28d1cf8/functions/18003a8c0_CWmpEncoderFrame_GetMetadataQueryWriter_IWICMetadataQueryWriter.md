# CWmpEncoderFrame::GetMetadataQueryWriter(IWICMetadataQueryWriter * *)

- ea: `0x18003a8c0`
- end: `0x18003a976`
- name: `?GetMetadataQueryWriter@CWmpEncoderFrame@@UEAAJPEAPEAUIWICMetadataQueryWriter@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this, struct IWICMetadataQueryWriter **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028920`
- `0x18002aec8`
- `0x18002db34`
- `0x18003a8c0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a8e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a8e3`

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
0x18003a8c0  mov     [rsp+arg_10], rbx
0x18003a8c5  push    rdi
0x18003a8c6  sub     rsp, 20h
0x18003a8ca  lea     rax, [rcx-38h]
0x18003a8ce  mov     rbx, rcx
0x18003a8d1  lea     rcx, [rax+8]; lpCriticalSection
0x18003a8d5  mov     [rsp+28h+arg_8], rax
0x18003a8da  cmp     byte ptr [rcx+28h], 0
0x18003a8de  mov     rdi, rdx
0x18003a8e1  jz      short loc_18003A8E9
0x18003a8e3  call    cs:__imp_EnterCriticalSection
0x18003a8e9  mov     [rsp+28h+arg_0], 0
0x18003a8f2  test    rdi, rdi
0x18003a8f5  jnz     short loc_18003A8FE
0x18003a8f7  mov     ebx, 80070057h
0x18003a8fc  jmp     short loc_18003A95F
0x18003a8fe  lea     rcx, [rbx-10348h]; this
0x18003a905  lea     r8, [rsp+28h+arg_0]; void **
0x18003a90a  lea     rdx, IID_IWICMetadataBlockWriter; struct _GUID *
0x18003a911  call    ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x18003a916  mov     ebx, eax
0x18003a918  test    eax, eax
0x18003a91a  js      short loc_18003A940
0x18003a91c  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x18003a921  mov     rdx, [rsp+28h+arg_0]
0x18003a926  mov     r9, rax
0x18003a929  mov     r8, rdi
0x18003a92c  mov     rcx, [rax]
0x18003a92f  mov     rax, [rcx+108h]
0x18003a936  mov     rcx, r9
0x18003a939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a93e  mov     ebx, eax
0x18003a940  mov     rcx, [rsp+28h+arg_0]
0x18003a945  test    rcx, rcx
0x18003a948  jz      short loc_18003A95F
0x18003a94a  mov     rax, [rcx]
0x18003a94d  mov     rax, [rax+10h]
0x18003a951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a956  mov     [rsp+28h+arg_0], 0
0x18003a95f  lea     rcx, [rsp+28h+arg_8]
0x18003a964  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003a969  mov     eax, ebx
0x18003a96b  mov     rbx, [rsp+28h+arg_10]
0x18003a970  add     rsp, 20h
0x18003a974  pop     rdi
0x18003a975  retn
```
