# ATL::CRegObject::~CRegObject(void)

- ea: `0x180006864`
- end: `0x1800068ff`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800063ec`
- `0x180006730`
- `0x1800089b4`
- `0x18003738e`

## callees

- `0x18000676c`
- `0x180006864`
- `0x18002ff2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006887`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006887`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000689c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000689c`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  void **v3; // rdi
  void *v4; // rcx

  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void **)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
  if ( *v3 )
  {
    free(*v3);
    *v3 = 0;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180006864  mov     [rsp+arg_0], rbx
0x180006869  mov     [rsp+arg_8], rsi
0x18000686e  push    rdi
0x18000686f  sub     rsp, 20h
0x180006873  mov     rbx, rcx
0x180006876  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000687d  mov     [rcx], rax
0x180006880  lea     rsi, [rcx+20h]
0x180006884  mov     rcx, rsi; lpCriticalSection
0x180006887  call    cs:__imp_EnterCriticalSection
0x18000688d  lea     rdi, [rbx+8]
0x180006891  mov     rcx, rdi; this
0x180006894  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180006899  mov     rcx, rsi; lpCriticalSection
0x18000689c  call    cs:__imp_LeaveCriticalSection
0x1800068a2  cmp     byte ptr [rsi+28h], 0
0x1800068a6  jz      short loc_1800068B6
0x1800068a8  mov     byte ptr [rsi+28h], 0
0x1800068ac  mov     rcx, rsi; lpCriticalSection
0x1800068af  call    cs:__imp_DeleteCriticalSection
0x1800068b5  nop
0x1800068b6  mov     rcx, rdi; this
0x1800068b9  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x1800068be  mov     rcx, [rdi]; Block
0x1800068c1  test    rcx, rcx
0x1800068c4  jz      short loc_1800068D2
0x1800068c6  call    free
0x1800068cb  mov     qword ptr [rdi], 0
0x1800068d2  mov     rcx, [rbx+10h]; Block
0x1800068d6  test    rcx, rcx
0x1800068d9  jz      short loc_1800068E8
0x1800068db  call    free
0x1800068e0  mov     qword ptr [rbx+10h], 0
0x1800068e8  mov     dword ptr [rbx+18h], 0
0x1800068ef  mov     rbx, [rsp+28h+arg_0]
0x1800068f4  mov     rsi, [rsp+28h+arg_8]
0x1800068f9  add     rsp, 20h
0x1800068fd  pop     rdi
0x1800068fe  retn
```
