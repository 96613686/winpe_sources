# ATL::CRegObject::~CRegObject(void)

- ea: `0x18001202c`
- end: `0x1800120d0`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `164`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012210`
- `0x1800157a0`
- `0x18001e8c0`

## callees

- `0x18001202c`
- `0x1800136f8`

## import_xrefs

- `msvcrt!free` at `0x18001209a`
- `msvcrt!free` at `0x1800120b0`
- `msvcrt!free` at `0x18001209a`
- `msvcrt!free` at `0x1800120b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012064`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012064`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001207d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001207d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001204f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001204f`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  ATL::CExpansionVector *v3; // rbx
  void *v4; // rcx

  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (ATL::CRegObject *)((char *)this + 8);
  ATL::CExpansionVector::ClearReplacements(v3);
  LeaveCriticalSection(v2);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  ATL::CExpansionVector::ClearReplacements(v3);
  if ( *(_QWORD *)v3 )
  {
    free(*(void **)v3);
    *(_QWORD *)v3 = 0;
  }
  v4 = (void *)*((_QWORD *)v3 + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)v3 + 1) = 0;
  }
  *((_DWORD *)v3 + 4) = 0;
}

```

## disassembly

```asm
0x18001202c  mov     [rsp+arg_10], rbx
0x180012031  mov     [rsp+arg_0], rcx
0x180012036  push    rdi
0x180012037  sub     rsp, 20h
0x18001203b  mov     rbx, rcx
0x18001203e  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180012045  mov     [rcx], rax
0x180012048  lea     rdi, [rcx+20h]
0x18001204c  mov     rcx, rdi; lpCriticalSection
0x18001204f  call    cs:__imp_EnterCriticalSection
0x180012055  add     rbx, 8
0x180012059  mov     rcx, rbx; this
0x18001205c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180012061  mov     rcx, rdi; lpCriticalSection
0x180012064  call    cs:__imp_LeaveCriticalSection
0x18001206a  nop
0x18001206b  mov     [rsp+28h+arg_8], rdi
0x180012070  cmp     byte ptr [rdi+28h], 0
0x180012074  jz      short loc_180012084
0x180012076  mov     byte ptr [rdi+28h], 0
0x18001207a  mov     rcx, rdi; lpCriticalSection
0x18001207d  call    cs:__imp_DeleteCriticalSection
0x180012083  nop
0x180012084  mov     [rsp+28h+arg_8], rbx
0x180012089  mov     rcx, rbx; this
0x18001208c  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180012091  nop
0x180012092  mov     rcx, [rbx]; Block
0x180012095  test    rcx, rcx
0x180012098  jz      short loc_1800120A7
0x18001209a  call    cs:__imp_free
0x1800120a0  mov     qword ptr [rbx], 0
0x1800120a7  mov     rcx, [rbx+8]; Block
0x1800120ab  test    rcx, rcx
0x1800120ae  jz      short loc_1800120BE
0x1800120b0  call    cs:__imp_free
0x1800120b6  mov     qword ptr [rbx+8], 0
0x1800120be  mov     dword ptr [rbx+10h], 0
0x1800120c5  mov     rbx, [rsp+28h+arg_10]
0x1800120ca  add     rsp, 20h
0x1800120ce  pop     rdi
0x1800120cf  retn
```
