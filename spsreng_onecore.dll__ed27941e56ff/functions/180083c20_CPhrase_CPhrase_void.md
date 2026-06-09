# CPhrase::~CPhrase(void)

- ea: `0x180083c20`
- end: `0x180083ca7`
- name: `??1CPhrase@@QEAA@XZ`
- size: `135`
- prototype: `void __fastcall(CPhrase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180075850`

## callees

- `0x180006abc`
- `0x180083c20`
- `0x1800887a4`
- `0x1800c77ac`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083c32`

## pseudocode

```c
void __fastcall CPhrase::~CPhrase(CPhrase *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 3) = 0;
  }
  CQuickStringTBase::~CQuickStringTBase((CPhrase *)((char *)this + 2296));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPhrase *)((char *)this + 2264));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPhrase *)((char *)this + 1552));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPhrase *)((char *)this + 824));
  CGrowableArrayVoid::~CGrowableArrayVoid((CPhrase *)((char *)this + 792));
  CPropertyTree::~CPropertyTree((CPhrase *)((char *)this + 32));
}

```

## disassembly

```asm
0x180083c20  push    rbx
0x180083c22  sub     rsp, 20h
0x180083c26  mov     rbx, rcx
0x180083c29  mov     rcx, [rcx+10h]; pv
0x180083c2d  test    rcx, rcx
0x180083c30  jz      short loc_180083C40
0x180083c32  call    cs:__imp_CoTaskMemFree
0x180083c38  mov     qword ptr [rbx+10h], 0
0x180083c40  mov     rcx, [rbx+18h]
0x180083c44  test    rcx, rcx
0x180083c47  jz      short loc_180083C5D
0x180083c49  mov     rax, [rcx]
0x180083c4c  mov     rax, [rax+10h]
0x180083c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c55  mov     qword ptr [rbx+18h], 0
0x180083c5d  lea     rcx, [rbx+8F8h]; this
0x180083c64  call    ??1CQuickStringTBase@@MEAA@XZ; CQuickStringTBase::~CQuickStringTBase(void)
0x180083c69  lea     rcx, [rbx+8D8h]; this
0x180083c70  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180083c75  lea     rcx, [rbx+610h]; this
0x180083c7c  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180083c81  lea     rcx, [rbx+338h]; this
0x180083c88  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180083c8d  lea     rcx, [rbx+318h]; this
0x180083c94  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x180083c99  lea     rcx, [rbx+20h]; this
0x180083c9d  add     rsp, 20h
0x180083ca1  pop     rbx
0x180083ca2  jmp     ??1CPropertyTree@@QEAA@XZ; CPropertyTree::~CPropertyTree(void)
```
