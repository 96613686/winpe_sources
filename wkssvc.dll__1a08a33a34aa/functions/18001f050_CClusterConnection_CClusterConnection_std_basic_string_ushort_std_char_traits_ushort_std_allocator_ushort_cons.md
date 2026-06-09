# CClusterConnection::CClusterConnection(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const *,ulong,ulong,CProtocolHandler *,ulong,void *)

- ea: `0x18001f050`
- end: `0x18001f27f`
- name: `??0CClusterConnection@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEBU_GUID@@KKPEAVCProtocolHandler@@KPEAX@Z`
- size: `559`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64, __int64, int, char, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d6d8`

## callees

- `0x18001ddc8`
- `0x18001e2dc`
- `0x18001f050`
- `0x18001f288`
- `0x180035354`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f261`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f251`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001f251`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f22f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f22f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CClusterConnection::CClusterConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _OWORD *a6,
        int a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 a11)
{
  _QWORD *v12; // rbp
  _QWORD *v13; // r15
  _QWORD *v14; // rbx
  __int64 v15; // rbx

  *(_QWORD *)a1 = &RefCountObject::`vftable';
  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &CClusterConnection::`vftable';
  *(_DWORD *)(a1 + 16) = 1;
  std::wstring::wstring(a1 + 24);
  v12 = (_QWORD *)(a1 + 56);
  std::wstring::wstring(a1 + 56);
  v13 = (_QWORD *)(a1 + 88);
  std::wstring::wstring(a1 + 88);
  *(_WORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  std::wstring::wstring(a1 + 152, &base);
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  v14 = (_QWORD *)(a1 + 216);
  std::wstring::wstring(a1 + 216);
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  std::list<CWitnessServer *>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 408) = a11;
  *(_QWORD *)(a1 + 416) = 0;
  *(_DWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 440) = -1;
  *(_DWORD *)(a1 + 448) = a7;
  *(_DWORD *)(a1 + 452) = a8;
  *(_QWORD *)(a1 + 456) = a9;
  *(_DWORD *)(a1 + 464) = a10;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 0;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    if ( *(_QWORD *)(a1 + 240) > 7u )
      v14 = (_QWORD *)*v14;
    if ( *(_QWORD *)(a1 + 112) > 7u )
      v13 = (_QWORD *)*v13;
    if ( *(_QWORD *)(a1 + 80) > 7u )
      v12 = (_QWORD *)*v12;
    WPP_SF_SSSSdq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), (__int64)v12, (__int64)v13, (__int64)v14, a8, a1);
  }
  *(_OWORD *)(a1 + 120) = *a6;
  *(_OWORD *)(a1 + 184) = 0;
  v15 = *(_QWORD *)(a1 + 456);
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(v15 + 80));
  if ( ++*(_DWORD *)(v15 + 132) == 1 )
    ResetEvent(*(HANDLE *)(v15 + 136));
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v15 + 80));
  return a1;
}

```

## disassembly

```asm
0x18001f050  mov     [rsp+arg_0], rcx
0x18001f055  push    rbx
0x18001f056  push    rbp
0x18001f057  push    rsi
0x18001f058  push    rdi
0x18001f059  push    r14
0x18001f05b  push    r15
0x18001f05d  sub     rsp, 58h
0x18001f061  mov     rdi, r9
0x18001f064  mov     rbx, r8
0x18001f067  mov     rsi, rcx
0x18001f06a  lea     rax, ??_7RefCountObject@@6B@; const RefCountObject::`vftable'
0x18001f071  mov     [rcx], rax
0x18001f074  mov     dword ptr [rcx+8], 1
0x18001f07b  lea     rax, ??_7CClusterConnection@@6B@; const CClusterConnection::`vftable'
0x18001f082  mov     [rcx], rax
0x18001f085  mov     dword ptr [rcx+10h], 1
0x18001f08c  lea     r14, [rcx+18h]
0x18001f090  mov     rcx, r14
0x18001f093  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f098  nop
0x18001f099  lea     rbp, [rsi+38h]
0x18001f09d  mov     rdx, rbx
0x18001f0a0  mov     rcx, rbp
0x18001f0a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f0a8  nop
0x18001f0a9  lea     r15, [rsi+58h]
0x18001f0ad  mov     rdx, rdi
0x18001f0b0  mov     rcx, r15
0x18001f0b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f0b8  nop
0x18001f0b9  xor     edi, edi
0x18001f0bb  mov     [rsi+88h], di
0x18001f0c2  mov     [rsi+90h], rdi
0x18001f0c9  lea     rcx, [rsi+98h]
0x18001f0d0  lea     rdx, base
0x18001f0d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001f0dc  nop
0x18001f0dd  mov     [rsi+0C8h], rdi
0x18001f0e4  mov     [rsi+0D0h], rdi
0x18001f0eb  lea     rbx, [rsi+0D8h]
0x18001f0f2  mov     rdx, [rsp+88h+arg_20]
0x18001f0fa  mov     rcx, rbx
0x18001f0fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001f102  nop
0x18001f103  lea     rcx, [rsi+0F8h]
0x18001f10a  mov     [rcx], rdi
0x18001f10d  mov     [rcx+8], rdi
0x18001f111  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCWitnessServer@@V?$allocator@PEAVCWitnessServer@@@std@@@std@@AEAAXXZ; std::list<CWitnessServer *>::_Alloc_sentinel_and_proxy(void)
0x18001f116  nop
0x18001f117  mov     [rsi+108h], rdi
0x18001f11e  mov     [rsi+110h], rdi
0x18001f125  mov     [rsi+188h], rdi
0x18001f12c  mov     [rsi+190h], rdi
0x18001f133  mov     rax, [rsp+88h+arg_50]
0x18001f13b  mov     [rsi+198h], rax
0x18001f142  mov     [rsi+1A0h], rdi
0x18001f149  mov     [rsi+1A8h], edi
0x18001f14f  mov     qword ptr [rsi+1B8h], 0FFFFFFFFFFFFFFFFh
0x18001f15a  mov     eax, [rsp+88h+arg_30]
0x18001f161  mov     [rsi+1C0h], eax
0x18001f167  mov     edx, dword ptr [rsp+88h+arg_38]
0x18001f16e  mov     [rsi+1C4h], edx
0x18001f174  mov     rax, [rsp+88h+arg_40]
0x18001f17c  mov     [rsi+1C8h], rax
0x18001f183  mov     eax, [rsp+88h+arg_48]
0x18001f18a  mov     [rsi+1D0h], eax
0x18001f190  mov     [rsi+1D8h], rdi
0x18001f197  mov     [rsi+1E0h], rdi
0x18001f19e  lea     rax, WPP_witness_GLOBAL_Control
0x18001f1a5  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001f1ac  cmp     rcx, rax
0x18001f1af  jz      short loc_18001F20A
0x18001f1b1  test    byte ptr [rcx+1Ch], 1
0x18001f1b5  jz      short loc_18001F20A
0x18001f1b7  cmp     byte ptr [rcx+19h], 3
0x18001f1bb  jb      short loc_18001F20A
0x18001f1bd  cmp     qword ptr [rbx+18h], 7
0x18001f1c2  jbe     short loc_18001F1C7
0x18001f1c4  mov     rbx, [rbx]
0x18001f1c7  cmp     qword ptr [r15+18h], 7
0x18001f1cc  jbe     short loc_18001F1D1
0x18001f1ce  mov     r15, [r15]
0x18001f1d1  cmp     qword ptr [rbp+18h], 7
0x18001f1d6  jbe     short loc_18001F1DC
0x18001f1d8  mov     rbp, [rbp+0]
0x18001f1dc  cmp     qword ptr [r14+18h], 7
0x18001f1e1  jbe     short loc_18001F1E6
0x18001f1e3  mov     r14, [r14]
0x18001f1e6  mov     qword ptr [rsp+88h+var_48], rsi; char
0x18001f1eb  mov     dword ptr [rsp+88h+var_50], edx; char
0x18001f1ef  mov     [rsp+88h+var_58], rbx; __int64
0x18001f1f4  mov     [rsp+88h+var_60], r15; __int64
0x18001f1f9  mov     [rsp+88h+var_68], rbp; __int64
0x18001f1fe  mov     r9, r14
0x18001f201  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f205  call    WPP_SF_SSSSdq
0x18001f20a  mov     rax, [rsp+88h+arg_28]
0x18001f212  movups  xmm0, xmmword ptr [rax]
0x18001f215  movdqu  xmmword ptr [rsi+78h], xmm0
0x18001f21a  xorps   xmm1, xmm1
0x18001f21d  movups  xmmword ptr [rsi+0B8h], xmm1
0x18001f224  mov     rbx, [rsi+1C8h]
0x18001f22b  mov     rcx, [rbx+50h]; lpCriticalSection
0x18001f22f  call    cs:__imp_EnterCriticalSection
0x18001f236  nop     dword ptr [rax+rax+00h]
0x18001f23b  inc     dword ptr [rbx+84h]
0x18001f241  cmp     dword ptr [rbx+84h], 1
0x18001f248  jnz     short loc_18001F25D
0x18001f24a  mov     rcx, [rbx+88h]; hEvent
0x18001f251  call    cs:__imp_ResetEvent
0x18001f258  nop     dword ptr [rax+rax+00h]
0x18001f25d  mov     rcx, [rbx+50h]; lpCriticalSection
0x18001f261  call    cs:__imp_LeaveCriticalSection
0x18001f268  nop     dword ptr [rax+rax+00h]
0x18001f26d  nop
0x18001f26e  mov     rax, rsi
0x18001f271  add     rsp, 58h
0x18001f275  pop     r15
0x18001f277  pop     r14
0x18001f279  pop     rdi
0x18001f27a  pop     rsi
0x18001f27b  pop     rbp
0x18001f27c  pop     rbx
0x18001f27d  retn
```
