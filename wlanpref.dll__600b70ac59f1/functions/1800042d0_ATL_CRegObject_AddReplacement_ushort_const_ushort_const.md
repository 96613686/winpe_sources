# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800042d0`
- end: `0x180004343`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bfbc`
- `0x18000c234`

## callees

- `0x180002cc0`
- `0x180003fec`
- `0x1800042d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800042f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004314`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004314`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v8 = 0;
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v8);
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800042d0  push    rbx
0x1800042d2  push    rbp
0x1800042d3  push    rsi
0x1800042d4  push    rdi
0x1800042d5  sub     rsp, 28h
0x1800042d9  mov     rbx, r8
0x1800042dc  mov     rsi, rdx
0x1800042df  mov     rbp, rcx
0x1800042e2  test    rdx, rdx
0x1800042e5  jz      short loc_180004335
0x1800042e7  test    rbx, rbx
0x1800042ea  jz      short loc_180004335
0x1800042ec  add     rcx, 20h ; ' '; lpCriticalSection
0x1800042f0  call    cs:__imp_EnterCriticalSection
0x1800042f6  mov     [rsp+48h+arg_8], 0
0x1800042ff  lea     rcx, [rbp+8]; this
0x180004303  mov     r8, rbx; unsigned __int16 *
0x180004306  mov     rdx, rsi; unsigned __int16 *
0x180004309  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000430e  mov     ebx, eax
0x180004310  lea     rcx, [rbp+20h]; lpCriticalSection
0x180004314  call    cs:__imp_LeaveCriticalSection
0x18000431a  nop
0x18000431b  neg     ebx
0x18000431d  sbb     ebx, ebx
0x18000431f  not     ebx
0x180004321  and     ebx, 8007000Eh
0x180004327  lea     rcx, [rsp+48h+arg_8]
0x18000432c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004331  mov     eax, ebx
0x180004333  jmp     short loc_18000433A
0x180004335  mov     eax, 80070057h
0x18000433a  add     rsp, 28h
0x18000433e  pop     rdi
0x18000433f  pop     rsi
0x180004340  pop     rbp
0x180004341  pop     rbx
0x180004342  retn
```
