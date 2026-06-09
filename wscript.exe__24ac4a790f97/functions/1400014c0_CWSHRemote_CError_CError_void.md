# CWSHRemote::CError::~CError(void)

- ea: `0x1400014c0`
- end: `0x140001543`
- name: `??1CError@CWSHRemote@@AEAA@XZ`
- size: `131`
- prototype: `void __fastcall(CWSHRemote::CError *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001920`

## callees

- `0x1400014c0`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400014d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400014e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400014eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400014d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400014e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400014eb`
- `KERNEL32!DeleteCriticalSection` at `0x140001537`
- `KERNEL32!DeleteCriticalSection` at `0x140001537`

## pseudocode

```c
void __fastcall CWSHRemote::CError::~CError(CWSHRemote::CError *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CWSHRemote::CError::`vftable';
  SysFreeString(*((BSTR *)this + 4));
  SysFreeString(*((BSTR *)this + 5));
  SysFreeString(*((BSTR *)this + 6));
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 16LL))(*((_QWORD *)this + 8));
  }
  if ( *((_BYTE *)this + 113) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
}

```

## disassembly

```asm
0x1400014c0  push    rbx
0x1400014c2  sub     rsp, 20h
0x1400014c6  lea     rax, ??_7CError@CWSHRemote@@6B@; const CWSHRemote::CError::`vftable'
0x1400014cd  mov     rbx, rcx
0x1400014d0  mov     [rcx], rax
0x1400014d3  mov     rcx, [rcx+20h]; bstrString
0x1400014d7  call    cs:__imp_SysFreeString
0x1400014dd  mov     rcx, [rbx+28h]; bstrString
0x1400014e1  call    cs:__imp_SysFreeString
0x1400014e7  mov     rcx, [rbx+30h]; bstrString
0x1400014eb  call    cs:__imp_SysFreeString
0x1400014f1  mov     rcx, [rbx+38h]
0x1400014f5  test    rcx, rcx
0x1400014f8  jz      short loc_140001506
0x1400014fa  mov     rax, [rcx]
0x1400014fd  mov     rax, [rax+10h]
0x140001501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001506  mov     rcx, [rbx+40h]
0x14000150a  test    rcx, rcx
0x14000150d  jz      short loc_14000152D
0x14000150f  mov     rax, [rcx]
0x140001512  xor     edx, edx
0x140001514  mov     rax, [rax+20h]
0x140001518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000151d  mov     rcx, [rbx+40h]
0x140001521  mov     rax, [rcx]
0x140001524  mov     rax, [rax+10h]
0x140001528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000152d  lea     rcx, [rbx+48h]; lpCriticalSection
0x140001531  cmp     byte ptr [rcx+29h], 0
0x140001535  jz      short loc_14000153D
0x140001537  call    cs:__imp_DeleteCriticalSection
0x14000153d  add     rsp, 20h
0x140001541  pop     rbx
0x140001542  retn
```
