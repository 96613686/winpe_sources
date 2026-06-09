# ATL::CRegObject::~CRegObject(void)

- ea: `0x1800058f8`
- end: `0x180005932`
- name: `??1CRegObject@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005a20`
- `0x18000830c`
- `0x18000858c`

## callees

- `0x1800058b4`
- `0x1800058f8`
- `0x180006a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000591e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000591e`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  *(_QWORD *)this = &ATL::CRegObject::`vftable';
  ATL::CRegObject::ClearReplacements(this);
  if ( *((_BYTE *)this + 72) )
  {
    *((_BYTE *)this + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
  ATL::CExpansionVector::~CExpansionVector((ATL::CRegObject *)((char *)this + 8));
}

```

## disassembly

```asm
0x1800058f8  push    rbx
0x1800058fa  sub     rsp, 20h
0x1800058fe  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005905  mov     rbx, rcx
0x180005908  mov     [rcx], rax
0x18000590b  call    ?ClearReplacements@CRegObject@ATL@@UEAAJXZ; ATL::CRegObject::ClearReplacements(void)
0x180005910  lea     rcx, [rbx+20h]; lpCriticalSection
0x180005914  cmp     byte ptr [rcx+28h], 0
0x180005918  jz      short loc_180005924
0x18000591a  mov     byte ptr [rcx+28h], 0
0x18000591e  call    cs:__imp_DeleteCriticalSection
0x180005924  lea     rcx, [rbx+8]; this
0x180005928  add     rsp, 20h
0x18000592c  pop     rbx
0x18000592d  jmp     ??1CExpansionVector@ATL@@QEAA@XZ; ATL::CExpansionVector::~CExpansionVector(void)
```
