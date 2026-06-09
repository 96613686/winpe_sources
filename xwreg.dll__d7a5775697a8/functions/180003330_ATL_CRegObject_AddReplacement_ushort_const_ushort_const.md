# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003330`
- end: `0x1800033a3`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800060fc`
- `0x180006374`

## callees

- `0x180002b1c`
- `0x1800030dc`
- `0x180003330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003374`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003350`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003350`

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
0x180003330  push    rbx
0x180003332  push    rbp
0x180003333  push    rsi
0x180003334  push    rdi
0x180003335  sub     rsp, 28h
0x180003339  mov     rbx, r8
0x18000333c  mov     rsi, rdx
0x18000333f  mov     rbp, rcx
0x180003342  test    rdx, rdx
0x180003345  jz      short loc_180003395
0x180003347  test    rbx, rbx
0x18000334a  jz      short loc_180003395
0x18000334c  add     rcx, 20h ; ' '; lpCriticalSection
0x180003350  call    cs:__imp_EnterCriticalSection
0x180003356  mov     [rsp+48h+arg_8], 0
0x18000335f  lea     rcx, [rbp+8]; this
0x180003363  mov     r8, rbx; unsigned __int16 *
0x180003366  mov     rdx, rsi; unsigned __int16 *
0x180003369  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000336e  mov     ebx, eax
0x180003370  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003374  call    cs:__imp_LeaveCriticalSection
0x18000337a  nop
0x18000337b  neg     ebx
0x18000337d  sbb     ebx, ebx
0x18000337f  not     ebx
0x180003381  and     ebx, 8007000Eh
0x180003387  lea     rcx, [rsp+48h+arg_8]
0x18000338c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003391  mov     eax, ebx
0x180003393  jmp     short loc_18000339A
0x180003395  mov     eax, 80070057h
0x18000339a  add     rsp, 28h
0x18000339e  pop     rdi
0x18000339f  pop     rsi
0x1800033a0  pop     rbp
0x1800033a1  pop     rbx
0x1800033a2  retn
```
