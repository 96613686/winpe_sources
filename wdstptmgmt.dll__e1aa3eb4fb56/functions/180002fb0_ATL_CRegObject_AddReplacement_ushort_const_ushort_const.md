# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002fb0`
- end: `0x180003044`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `148`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005914`

## callees

- `0x180002ae8`
- `0x180002da0`
- `0x180002fb0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003002`
- `KERNEL32!LeaveCriticalSection` at `0x180003002`
- `KERNEL32!EnterCriticalSection` at `0x180002fdb`
- `KERNEL32!EnterCriticalSection` at `0x180002fdb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

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
0x180002fb0  mov     [rsp+arg_0], rbx
0x180002fb5  mov     [rsp+arg_10], rbp
0x180002fba  mov     [rsp+arg_18], rsi
0x180002fbf  push    rdi
0x180002fc0  sub     rsp, 20h
0x180002fc4  mov     rbx, r8
0x180002fc7  mov     rsi, rdx
0x180002fca  mov     rbp, rcx
0x180002fcd  test    rdx, rdx
0x180002fd0  jz      short loc_180003029
0x180002fd2  test    rbx, rbx
0x180002fd5  jz      short loc_180003029
0x180002fd7  add     rcx, 20h ; ' '; lpCriticalSection
0x180002fdb  call    cs:__imp_EnterCriticalSection
0x180002fe2  nop     dword ptr [rax+rax+00h]
0x180002fe7  and     [rsp+28h+arg_8], 0
0x180002fed  lea     rcx, [rbp+8]; this
0x180002ff1  mov     r8, rbx; unsigned __int16 *
0x180002ff4  mov     rdx, rsi; unsigned __int16 *
0x180002ff7  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002ffc  mov     ebx, eax
0x180002ffe  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003002  call    cs:__imp_LeaveCriticalSection
0x180003009  nop     dword ptr [rax+rax+00h]
0x18000300e  nop
0x18000300f  neg     ebx
0x180003011  sbb     ebx, ebx
0x180003013  not     ebx
0x180003015  and     ebx, 8007000Eh
0x18000301b  lea     rcx, [rsp+28h+arg_8]
0x180003020  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003025  mov     eax, ebx
0x180003027  jmp     short loc_18000302E
0x180003029  mov     eax, 80070057h
0x18000302e  mov     rbx, [rsp+28h+arg_0]
0x180003033  mov     rbp, [rsp+28h+arg_10]
0x180003038  mov     rsi, [rsp+28h+arg_18]
0x18000303d  add     rsp, 20h
0x180003041  pop     rdi
0x180003042  retn
```
