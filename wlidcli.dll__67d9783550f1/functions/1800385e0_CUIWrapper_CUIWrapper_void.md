# CUIWrapper::~CUIWrapper(void)

- ea: `0x1800385e0`
- end: `0x180038632`
- name: `??1CUIWrapper@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CUIWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800384b4`

## callees

- `0x1800231b8`
- `0x18003857c`
- `0x1800385e0`
- `0x18003d7d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038606`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038610`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038606`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038610`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CUIWrapper::~CUIWrapper(CUIWrapper *this)
{
  char *v2; // rdi

  v2 = (char *)this + 128;
  if ( *((_BYTE *)this + 120) )
    CUxpDllWrapper::Uninitialize((CUIWrapper *)((char *)this + 128));
  DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  CImpersonateHelper::~CImpersonateHelper((CUIWrapper *)((char *)this + 64));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((CUIWrapper *)((char *)this + 16));
}

```

## disassembly

```asm
0x1800385e0  mov     [rsp+arg_0], rbx
0x1800385e5  push    rdi
0x1800385e6  sub     rsp, 20h
0x1800385ea  mov     rbx, rcx
0x1800385ed  lea     rdi, [rcx+80h]
0x1800385f4  cmp     byte ptr [rcx+78h], 0
0x1800385f8  jz      short loc_180038602
0x1800385fa  mov     rcx, rdi; this
0x1800385fd  call    ?Uninitialize@CUxpDllWrapper@@QEAAJXZ; CUxpDllWrapper::Uninitialize(void)
0x180038602  lea     rcx, [rdi+10h]; lpCriticalSection
0x180038606  call    cs:__imp_DeleteCriticalSection
0x18003860c  lea     rcx, [rbx+50h]; lpCriticalSection
0x180038610  call    cs:__imp_DeleteCriticalSection
0x180038616  lea     rcx, [rbx+40h]; this
0x18003861a  call    ??1CImpersonateHelper@@QEAA@XZ; CImpersonateHelper::~CImpersonateHelper(void)
0x18003861f  lea     rcx, [rbx+10h]; this
0x180038623  mov     rbx, [rsp+28h+arg_0]
0x180038628  add     rsp, 20h
0x18003862c  pop     rdi
0x18003862d  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
