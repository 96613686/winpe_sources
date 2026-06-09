# CWmpDecoderFrame::GetMetadataQueryReader(IWICMetadataQueryReader * *)

- ea: `0x180039170`
- end: `0x18003923b`
- name: `?GetMetadataQueryReader@CWmpDecoderFrame@@UEAAJPEAPEAUIWICMetadataQueryReader@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, struct IWICMetadataQueryReader **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028920`
- `0x18002aec8`
- `0x18002db34`
- `0x180039170`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003919f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003919f`

## pseudocode

```c
__int64 __fastcall CWmpDecoderFrame::GetMetadataQueryReader(
        CWmpDecoderFrame *this,
        struct IWICMetadataQueryReader **a2)
{
  bool v4; // zf
  int v5; // ebx
  struct IWICComponentFactory *WICFactory; // rax
  void *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = *((_QWORD *)this + 53) + 24LL;
  if ( *(_BYTE *)(v9 + 48) )
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
  v4 = *((_DWORD *)this + 109) == 0;
  v8 = 0;
  if ( v4 )
  {
    v5 = CWmpCOMBase::InternalQueryInterface(
           (CWmpDecoderFrame *)((char *)this - 66320),
           &IID_IWICMetadataBlockReader,
           &v8);
    if ( v5 >= 0 )
    {
      WICFactory = GetWICFactory();
      v5 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, void *, struct IWICMetadataQueryReader **))WICFactory->lpVtbl->CreateQueryReaderFromBlockReader)(
             WICFactory,
             v8,
             a2);
    }
    if ( v8 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = 0;
    }
  }
  else
  {
    v5 = -2003292287;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039170  mov     [rsp+arg_8], rbx
0x180039175  mov     [rsp+arg_18], rsi
0x18003917a  push    rdi
0x18003917b  sub     rsp, 20h
0x18003917f  mov     rax, [rcx+1A8h]
0x180039186  mov     rbx, rcx
0x180039189  add     rax, 18h
0x18003918d  mov     rsi, rdx
0x180039190  mov     [rsp+28h+arg_10], rax
0x180039195  lea     rcx, [rax+8]; lpCriticalSection
0x180039199  cmp     byte ptr [rcx+28h], 0
0x18003919d  jz      short loc_1800391A5
0x18003919f  call    cs:__imp_EnterCriticalSection
0x1800391a5  cmp     dword ptr [rbx+1B4h], 0
0x1800391ac  mov     [rsp+28h+arg_0], 0
0x1800391b5  jz      short loc_1800391BE
0x1800391b7  mov     ebx, 88982F81h
0x1800391bc  jmp     short loc_18003921F
0x1800391be  lea     r8, [rsp+28h+arg_0]; void **
0x1800391c3  lea     rdx, IID_IWICMetadataBlockReader; struct _GUID *
0x1800391ca  lea     rcx, [rbx-10310h]; this
0x1800391d1  call    ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x1800391d6  mov     ebx, eax
0x1800391d8  test    eax, eax
0x1800391da  js      short loc_180039200
0x1800391dc  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x1800391e1  mov     rdx, [rsp+28h+arg_0]
0x1800391e6  mov     r9, rax
0x1800391e9  mov     r8, rsi
0x1800391ec  mov     rcx, [rax]
0x1800391ef  mov     rax, [rcx+100h]
0x1800391f6  mov     rcx, r9
0x1800391f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391fe  mov     ebx, eax
0x180039200  mov     rcx, [rsp+28h+arg_0]
0x180039205  test    rcx, rcx
0x180039208  jz      short loc_18003921F
0x18003920a  mov     rax, [rcx]
0x18003920d  mov     rax, [rax+10h]
0x180039211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039216  mov     [rsp+28h+arg_0], 0
0x18003921f  lea     rcx, [rsp+28h+arg_10]
0x180039224  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180039229  mov     rsi, [rsp+28h+arg_18]
0x18003922e  mov     eax, ebx
0x180039230  mov     rbx, [rsp+28h+arg_8]
0x180039235  add     rsp, 20h
0x180039239  pop     rdi
0x18003923a  retn
```
