# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180005da0`
- end: `0x180005e13`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `115`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000830c`
- `0x18000858c`

## callees

- `0x180005798`
- `0x180005b00`
- `0x180005da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005de4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005de4`

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
0x180005da0  push    rbx
0x180005da2  push    rbp
0x180005da3  push    rsi
0x180005da4  push    rdi
0x180005da5  sub     rsp, 28h
0x180005da9  mov     rbx, r8
0x180005dac  mov     rsi, rdx
0x180005daf  mov     rbp, rcx
0x180005db2  test    rdx, rdx
0x180005db5  jz      short loc_180005E05
0x180005db7  test    rbx, rbx
0x180005dba  jz      short loc_180005E05
0x180005dbc  add     rcx, 20h ; ' '; lpCriticalSection
0x180005dc0  call    cs:__imp_EnterCriticalSection
0x180005dc6  mov     [rsp+48h+arg_8], 0
0x180005dcf  lea     rcx, [rbp+8]; this
0x180005dd3  mov     r8, rbx; unsigned __int16 *
0x180005dd6  mov     rdx, rsi; unsigned __int16 *
0x180005dd9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005dde  mov     ebx, eax
0x180005de0  lea     rcx, [rbp+20h]; lpCriticalSection
0x180005de4  call    cs:__imp_LeaveCriticalSection
0x180005dea  nop
0x180005deb  neg     ebx
0x180005ded  sbb     ebx, ebx
0x180005def  not     ebx
0x180005df1  and     ebx, 8007000Eh
0x180005df7  lea     rcx, [rsp+48h+arg_8]
0x180005dfc  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005e01  mov     eax, ebx
0x180005e03  jmp     short loc_180005E0A
0x180005e05  mov     eax, 80070057h
0x180005e0a  add     rsp, 28h
0x180005e0e  pop     rdi
0x180005e0f  pop     rsi
0x180005e10  pop     rbp
0x180005e11  pop     rbx
0x180005e12  retn
```
