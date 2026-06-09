# CWmpDecoderFrame::GetMetadataQueryReader(IWICMetadataQueryReader * *)

- ea: `0x180039850`
- end: `0x180039922`
- name: `?GetMetadataQueryReader@CWmpDecoderFrame@@UEAAJPEAPEAUIWICMetadataQueryReader@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CWmpDecoderFrame *__hidden this, struct IWICMetadataQueryReader **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028ec0`
- `0x18002b078`
- `0x18002de30`
- `0x180039850`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003987f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003987f`

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
0x180039850  mov     [rsp+arg_8], rbx
0x180039855  mov     [rsp+arg_18], rsi
0x18003985a  push    rdi
0x18003985b  sub     rsp, 20h
0x18003985f  mov     rax, [rcx+1A8h]
0x180039866  mov     rbx, rcx
0x180039869  add     rax, 18h
0x18003986d  mov     rsi, rdx
0x180039870  mov     [rsp+28h+arg_10], rax
0x180039875  lea     rcx, [rax+8]; lpCriticalSection
0x180039879  cmp     byte ptr [rcx+28h], 0
0x18003987d  jz      short loc_18003988B
0x18003987f  call    cs:__imp_EnterCriticalSection
0x180039886  nop     dword ptr [rax+rax+00h]
0x18003988b  cmp     dword ptr [rbx+1B4h], 0
0x180039892  mov     [rsp+28h+arg_0], 0
0x18003989b  jz      short loc_1800398A4
0x18003989d  mov     ebx, 88982F81h
0x1800398a2  jmp     short loc_180039905
0x1800398a4  lea     r8, [rsp+28h+arg_0]; void **
0x1800398a9  lea     rdx, IID_IWICMetadataBlockReader; struct _GUID *
0x1800398b0  lea     rcx, [rbx-10310h]; this
0x1800398b7  call    ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
0x1800398bc  mov     ebx, eax
0x1800398be  test    eax, eax
0x1800398c0  js      short loc_1800398E6
0x1800398c2  call    ?GetWICFactory@@YAPEAUIWICComponentFactory@@XZ; GetWICFactory(void)
0x1800398c7  mov     rdx, [rsp+28h+arg_0]
0x1800398cc  mov     r9, rax
0x1800398cf  mov     r8, rsi
0x1800398d2  mov     rcx, [rax]
0x1800398d5  mov     rax, [rcx+100h]
0x1800398dc  mov     rcx, r9
0x1800398df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398e4  mov     ebx, eax
0x1800398e6  mov     rcx, [rsp+28h+arg_0]
0x1800398eb  test    rcx, rcx
0x1800398ee  jz      short loc_180039905
0x1800398f0  mov     rax, [rcx]
0x1800398f3  mov     rax, [rax+10h]
0x1800398f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800398fc  mov     [rsp+28h+arg_0], 0
0x180039905  lea     rcx, [rsp+28h+arg_10]
0x18003990a  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18003990f  mov     rsi, [rsp+28h+arg_18]
0x180039914  mov     eax, ebx
0x180039916  mov     rbx, [rsp+28h+arg_8]
0x18003991b  add     rsp, 20h
0x18003991f  pop     rdi
0x180039920  retn
```
