# CWcnWfdClientTransport::~CWcnWfdClientTransport(void)

- ea: `0x18004ac4c`
- end: `0x18004acdc`
- name: `??1CWcnWfdClientTransport@@UEAA@XZ`
- size: `144`
- prototype: `void __fastcall(CWcnWfdClientTransport *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004acf0`

## callees

- `0x18001e490`
- `0x18004ac4c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004ac8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004acaf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004ac8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004acaf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ac75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ac75`

## pseudocode

```c
void __fastcall CWcnWfdClientTransport::~CWcnWfdClientTransport(CWcnWfdClientTransport *this)
{
  __int64 v2; // rbx

  *(_QWORD *)this = &CWcnWfdClientTransport::`vftable'{for `IWcnTransport'};
  *((_QWORD *)this + 2) = &CWcnWfdClientTransport::`vftable'{for `IWcnSinkController'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v2 = *((_QWORD *)this + 23);
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
  CWcnMessage::Clear((CWcnWfdClientTransport *)((char *)this + 112));
  CWcnMessage::Clear((CWcnWfdClientTransport *)((char *)this + 48));
  *(_QWORD *)this = &IWcnTransport::`vftable';
}

```

## disassembly

```asm
0x18004ac4c  mov     [rsp+arg_0], rbx
0x18004ac51  push    rdi
0x18004ac52  sub     rsp, 20h
0x18004ac56  lea     rax, ??_7CWcnWfdClientTransport@@6BIWcnTransport@@@; const CWcnWfdClientTransport::`vftable'{for `IWcnTransport'}
0x18004ac5d  mov     rdi, rcx
0x18004ac60  mov     [rcx], rax
0x18004ac63  lea     rax, ??_7CWcnWfdClientTransport@@6BIWcnSinkController@@@; const CWcnWfdClientTransport::`vftable'{for `IWcnSinkController'}
0x18004ac6a  mov     [rcx+10h], rax
0x18004ac6e  add     rcx, 0C0h; lpCriticalSection
0x18004ac75  call    cs:__imp_DeleteCriticalSection
0x18004ac7b  mov     rbx, [rdi+0B8h]
0x18004ac82  test    rbx, rbx
0x18004ac85  jz      short loc_18004ACB5
0x18004ac87  mov     rcx, [rbx]
0x18004ac8a  test    rcx, rcx
0x18004ac8d  jz      short loc_18004ACAC
0x18004ac8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004ac95  mov     qword ptr [rbx], 0
0x18004ac9c  mov     qword ptr [rbx+8], 0
0x18004aca4  mov     qword ptr [rbx+10h], 0
0x18004acac  mov     rcx, rbx
0x18004acaf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004acb5  lea     rcx, [rdi+70h]; this
0x18004acb9  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18004acbe  lea     rcx, [rdi+30h]; this
0x18004acc2  call    ?Clear@CWcnMessage@@QEAAXXZ; CWcnMessage::Clear(void)
0x18004acc7  mov     rbx, [rsp+28h+arg_0]
0x18004accc  lea     rax, ??_7IWcnTransport@@6B@; const IWcnTransport::`vftable'
0x18004acd3  mov     [rdi], rax
0x18004acd6  add     rsp, 20h
0x18004acda  pop     rdi
0x18004acdb  retn
```
