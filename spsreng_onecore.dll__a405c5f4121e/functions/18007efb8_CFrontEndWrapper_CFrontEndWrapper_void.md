# CFrontEndWrapper::~CFrontEndWrapper(void)

- ea: `0x18007efb8`
- end: `0x18007f0b7`
- name: `??1CFrontEndWrapper@@UEAA@XZ`
- size: `255`
- prototype: `void __fastcall(CFrontEndWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007f170`

## callees

- `0x180002db8`
- `0x1800034d4`
- `0x180006a1c`
- `0x1800073b4`
- `0x18007ef84`
- `0x18007efb8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007f07b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007f07b`

## pseudocode

```c
void __fastcall CFrontEndWrapper::~CFrontEndWrapper(CFrontEndWrapper *this)
{
  CAudioBuffer *v1; // rdi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx

  v1 = (CAudioBuffer *)*((_QWORD *)this + 3);
  *(_QWORD *)this = &CFrontEndWrapper::`vftable';
  if ( v1 )
  {
    CAudioBuffer::~CAudioBuffer(v1);
    operator delete(v1, 0x30u);
    *((_QWORD *)this + 3) = 0;
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 17);
  if ( v3 )
  {
    (**v3)(v3, 1);
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 23) = 0;
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  if ( *((_QWORD *)this + 27) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 27, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  *((_QWORD *)this + 152) = 0;
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll((char *)this + 456);
  CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll((char *)this + 408);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 216);
}

```

## disassembly

```asm
0x18007efb8  mov     [rsp+arg_0], rbx
0x18007efbd  mov     [rsp+arg_8], rsi
0x18007efc2  push    rdi
0x18007efc3  sub     rsp, 20h
0x18007efc7  mov     rdi, [rcx+18h]
0x18007efcb  lea     rax, ??_7CFrontEndWrapper@@6B@; const CFrontEndWrapper::`vftable'
0x18007efd2  xor     esi, esi
0x18007efd4  mov     [rcx], rax
0x18007efd7  mov     rbx, rcx
0x18007efda  test    rdi, rdi
0x18007efdd  jz      short loc_18007EFF6
0x18007efdf  mov     rcx, rdi; this
0x18007efe2  call    ??1CAudioBuffer@@QEAA@XZ; CAudioBuffer::~CAudioBuffer(void)
0x18007efe7  lea     edx, [rsi+30h]; unsigned __int64
0x18007efea  mov     rcx, rdi; void *
0x18007efed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007eff2  mov     [rbx+18h], rsi
0x18007eff6  mov     rcx, [rbx+88h]
0x18007effd  mov     edi, 1
0x18007f002  test    rcx, rcx
0x18007f005  jz      short loc_18007F022
0x18007f007  mov     rax, [rcx]
0x18007f00a  mov     edx, edi
0x18007f00c  mov     rax, [rax]
0x18007f00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f014  mov     [rbx+88h], rsi
0x18007f01b  mov     [rbx+90h], rsi
0x18007f022  mov     rcx, [rbx+28h]
0x18007f026  mov     [rbx+98h], rsi
0x18007f02d  mov     [rbx+0B8h], rsi
0x18007f034  test    rcx, rcx
0x18007f037  jz      short loc_18007F04E
0x18007f039  mov     rax, [rcx]
0x18007f03c  mov     edx, edi
0x18007f03e  mov     rax, [rax]
0x18007f041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f046  mov     [rbx+28h], rsi
0x18007f04a  mov     [rbx+30h], rsi
0x18007f04e  lea     rdi, [rbx+0D8h]
0x18007f055  mov     [rbx+48h], rsi
0x18007f059  mov     [rbx+60h], rsi
0x18007f05d  mov     [rbx+50h], rsi
0x18007f061  mov     [rbx+58h], rsi
0x18007f065  cmp     [rdi], rsi
0x18007f068  jz      short loc_18007F074
0x18007f06a  xor     edx, edx; struct IUnknown *
0x18007f06c  mov     rcx, rdi; struct IUnknown **
0x18007f06f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007f074  lea     rcx, [rbx+1F8h]; lpCriticalSection
0x18007f07b  call    cs:__imp_DeleteCriticalSection
0x18007f081  lea     rcx, [rbx+1C8h]
0x18007f088  mov     [rbx+4C0h], rsi
0x18007f08f  call    ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
0x18007f094  lea     rcx, [rbx+198h]
0x18007f09b  call    ?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ; CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)
0x18007f0a0  mov     rcx, rdi
0x18007f0a3  mov     rbx, [rsp+28h+arg_0]
0x18007f0a8  mov     rsi, [rsp+28h+arg_8]
0x18007f0ad  add     rsp, 20h
0x18007f0b1  pop     rdi
0x18007f0b2  jmp     ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
```
