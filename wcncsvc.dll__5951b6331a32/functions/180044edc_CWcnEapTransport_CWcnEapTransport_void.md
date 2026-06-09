# CWcnEapTransport::~CWcnEapTransport(void)

- ea: `0x180044edc`
- end: `0x180044f79`
- name: `??1CWcnEapTransport@@UEAA@XZ`
- size: `157`
- prototype: `void __fastcall(CWcnEapTransport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180044f80`

## callees

- `0x18001e490`
- `0x180044edc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180044f2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180044f4c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180044f2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180044f4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044f05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044f12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044f05`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180044f12`

## pseudocode

```c
void __fastcall CWcnEapTransport::~CWcnEapTransport(CWcnEapTransport *this)
{
  __int64 v2; // rdi

  *(_QWORD *)this = &CWcnEapTransport::`vftable'{for `IWcnTransport'};
  *((_QWORD *)this + 2) = &CWcnEapTransport::`vftable'{for `IWcnSinkController'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    if ( *(_QWORD *)v2 )
    {
      operator delete(*(void **)v2);
      *(_QWORD *)v2 = 0;
      *(_QWORD *)(v2 + 8) = 0;
      *(_QWORD *)(v2 + 16) = 0;
    }
    operator delete((void *)v2);
  }
  CWcnMessage::Clear((CWcnEapTransport *)((char *)this + 112));
  CWcnMessage::Clear((CWcnEapTransport *)((char *)this + 48));
  *(_QWORD *)this = &IWcnTransport::`vftable';
}

```

## disassembly

```asm
0x180044edc  mov     [rsp+arg_0], rbx
0x180044ee1  push    rdi
0x180044ee2  sub     rsp, 20h
0x180044ee6  lea     rax, ??_7CWcnEapTransport@@6BIWcnTransport@@@; const CWcnEapTransport::`vftable'{for `IWcnTransport'}
0x180044eed  mov     rbx, rcx
0x180044ef0  mov     [rcx], rax
0x180044ef3  lea     rax, ??_7CWcnEapTransport@@6BIWcnSinkController@@@; const CWcnEapTransport::`vftable'{for `IWcnSinkController'}
0x180044efa  mov     [rcx+10h], rax
0x180044efe  add     rcx, 0E8h; lpCriticalSection
0x180044f05  call    cs:__imp_DeleteCriticalSection
0x180044f0b  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x180044f12  call    cs:__imp_DeleteCriticalSection
0x180044f18  mov     rdi, [rbx+0E0h]
0x180044f1f  test    rdi, rdi
0x180044f22  jz      short loc_180044F52
0x180044f24  mov     rcx, [rdi]
0x180044f27  test    rcx, rcx
0x180044f2a  jz      short loc_180044F49
0x180044f2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180044f32  mov     qword ptr [rdi], 0
0x180044f39  mov     qword ptr [rdi+8], 0
0x180044f41  mov     qword ptr [rdi+10h], 0
0x180044f49  mov     rcx, rdi
0x180044f4c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180044f52  lea     rcx, [rbx+70h]; this
0x180044f56  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x180044f5b  lea     rcx, [rbx+30h]; this
0x180044f5f  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x180044f64  lea     rax, ??_7IWcnTransport@@6B@; const IWcnTransport::`vftable'
0x180044f6b  mov     [rbx], rax
0x180044f6e  mov     rbx, [rsp+28h+arg_0]
0x180044f73  add     rsp, 20h
0x180044f77  pop     rdi
0x180044f78  retn
```
