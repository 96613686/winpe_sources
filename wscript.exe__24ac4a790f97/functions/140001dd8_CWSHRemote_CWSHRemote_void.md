# CWSHRemote::~CWSHRemote(void)

- ea: `0x140001dd8`
- end: `0x140001ed5`
- name: `??1CWSHRemote@@QEAA@XZ`
- size: `253`
- prototype: `void __fastcall(CWSHRemote *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002b30`

## callees

- `0x140001048`
- `0x140001dd8`
- `0x140001edc`
- `0x140008950`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140001e2d`
- `OLEAUT32!__imp_SysFreeString` at `0x140001e2d`
- `KERNEL32!DeleteCriticalSection` at `0x140001ec4`
- `KERNEL32!DeleteCriticalSection` at `0x140001ec4`

## pseudocode

```c
void __fastcall CWSHRemote::~CWSHRemote(CWSHRemote *this)
{
  CHost *v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v1 = (CHost *)*((_QWORD *)this + 13);
  *(_QWORD *)this = &CWSHRemote::`vftable'{for `IWSHRemote'};
  *((_QWORD *)this + 1) = &CWSHRemote::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 2) = &CWSHRemote::`vftable'{for `IConnectionPointContainer'};
  *((_QWORD *)this + 3) = &CWSHRemote::`vftable'{for `IConnectionPoint'};
  if ( v1 )
  {
    CHost::~CHost(v1);
    operator delete(v1);
  }
  SysFreeString(*((BSTR *)this + 12));
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 10);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 8);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 11);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11));
  }
  CWSHRemote::DispTable::~DispTable((CWSHRemote *)((char *)this + 168));
  if ( *((_BYTE *)this + 161) )
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 3);
}

```

## disassembly

```asm
0x140001dd8  mov     [rsp+arg_0], rbx
0x140001ddd  push    rdi
0x140001dde  sub     rsp, 20h
0x140001de2  mov     rdi, [rcx+68h]
0x140001de6  lea     rax, ??_7CWSHRemote@@6BIWSHRemote@@@; const CWSHRemote::`vftable'{for `IWSHRemote'}
0x140001ded  mov     [rcx], rax
0x140001df0  lea     rax, ??_7CWSHRemote@@6BIProvideClassInfo@@@; const CWSHRemote::`vftable'{for `IProvideClassInfo'}
0x140001df7  mov     [rcx+8], rax
0x140001dfb  lea     rax, ??_7CWSHRemote@@6BIConnectionPointContainer@@@; const CWSHRemote::`vftable'{for `IConnectionPointContainer'}
0x140001e02  mov     [rcx+10h], rax
0x140001e06  lea     rax, ??_7CWSHRemote@@6BIConnectionPoint@@@; const CWSHRemote::`vftable'{for `IConnectionPoint'}
0x140001e0d  mov     [rcx+18h], rax
0x140001e11  mov     rbx, rcx
0x140001e14  test    rdi, rdi
0x140001e17  jz      short loc_140001E29
0x140001e19  mov     rcx, rdi; this
0x140001e1c  call    ??1CHost@@QEAA@XZ; CHost::~CHost(void)
0x140001e21  mov     rcx, rdi; Block
0x140001e24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001e29  mov     rcx, [rbx+60h]; bstrString
0x140001e2d  call    cs:__imp_SysFreeString
0x140001e33  mov     rcx, [rbx+48h]
0x140001e37  test    rcx, rcx
0x140001e3a  jz      short loc_140001E48
0x140001e3c  mov     rax, [rcx]
0x140001e3f  mov     rax, [rax+10h]
0x140001e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e48  mov     rcx, [rbx+50h]
0x140001e4c  test    rcx, rcx
0x140001e4f  jz      short loc_140001E5D
0x140001e51  mov     rax, [rcx]
0x140001e54  mov     rax, [rax+10h]
0x140001e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e5d  mov     rcx, [rbx+70h]
0x140001e61  test    rcx, rcx
0x140001e64  jz      short loc_140001E72
0x140001e66  mov     rax, [rcx]
0x140001e69  mov     rax, [rax+10h]
0x140001e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e72  mov     rcx, [rbx+40h]
0x140001e76  test    rcx, rcx
0x140001e79  jz      short loc_140001E87
0x140001e7b  mov     rax, [rcx]
0x140001e7e  mov     rax, [rax+10h]
0x140001e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e87  mov     rcx, [rbx+58h]
0x140001e8b  test    rcx, rcx
0x140001e8e  jz      short loc_140001EAE
0x140001e90  mov     rax, [rcx]
0x140001e93  xor     edx, edx
0x140001e95  mov     rax, [rax+20h]
0x140001e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e9e  mov     rcx, [rbx+58h]
0x140001ea2  mov     rax, [rcx]
0x140001ea5  mov     rax, [rax+10h]
0x140001ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001eae  lea     rcx, [rbx+0A8h]; this
0x140001eb5  call    ??1DispTable@CWSHRemote@@QEAA@XZ; CWSHRemote::DispTable::~DispTable(void)
0x140001eba  lea     rcx, [rbx+78h]; lpCriticalSection
0x140001ebe  cmp     byte ptr [rcx+29h], 0
0x140001ec2  jz      short loc_140001ECA
0x140001ec4  call    cs:__imp_DeleteCriticalSection
0x140001eca  mov     rbx, [rsp+28h+arg_0]
0x140001ecf  add     rsp, 20h
0x140001ed3  pop     rdi
0x140001ed4  retn
```
