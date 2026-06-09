# CSsdpCacheEntry::HrShutdown(int)

- ea: `0x18000a590`
- end: `0x18000a614`
- name: `?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, int)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a00`
- `0x180015ac8`
- `0x18001b914`
- `0x18001e068`
- `0x18002179c`
- `0x18002f680`

## callees

- `0x1800099c8`
- `0x18000a590`
- `0x180015720`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a603`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5a8`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::HrShutdown(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // edx
  unsigned int v6; // edi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 216));
  v6 = CTimerBase::HrDelete(this + 3, (char *)0xFFFFFFFFFFFFFFFFLL);
  if ( a2 )
    v6 = CSsdpCacheEntry::NotifyForAllAddressFamily((CSsdpCacheEntry *)this, v5);
  if ( v6 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v6);
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x18000a590  push    rbx
0x18000a592  push    rbp
0x18000a593  push    rsi
0x18000a594  push    rdi
0x18000a595  sub     rsp, 28h
0x18000a599  lea     rbp, [rcx+0D8h]
0x18000a5a0  mov     rsi, rcx
0x18000a5a3  mov     rcx, rbp; lpCriticalSection
0x18000a5a6  mov     ebx, edx
0x18000a5a8  call    cs:__imp_EnterCriticalSection
0x18000a5ae  lea     rcx, [rsi+78h]; this
0x18000a5b2  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x18000a5b6  call    ?HrDelete@CTimerBase@@QEAAJPEAX@Z; CTimerBase::HrDelete(void *)
0x18000a5bb  mov     edi, eax
0x18000a5bd  test    ebx, ebx
0x18000a5bf  jz      short loc_18000A5CB
0x18000a5c1  mov     rcx, rsi; this
0x18000a5c4  call    ?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::NotifyForAllAddressFamily(int)
0x18000a5c9  mov     edi, eax
0x18000a5cb  test    edi, edi
0x18000a5cd  jz      short loc_18000A600
0x18000a5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5d6  lea     rax, WPP_GLOBAL_Control
0x18000a5dd  cmp     rcx, rax
0x18000a5e0  jz      short loc_18000A600
0x18000a5e2  test    byte ptr [rcx+1Ch], 1
0x18000a5e6  jz      short loc_18000A600
0x18000a5e8  mov     rcx, [rcx+10h]
0x18000a5ec  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000a5f3  mov     edx, 1Fh
0x18000a5f8  mov     r9d, edi
0x18000a5fb  call    WPP_SF_d
0x18000a600  mov     rcx, rbp; lpCriticalSection
0x18000a603  call    cs:__imp_LeaveCriticalSection
0x18000a609  mov     eax, edi
0x18000a60b  add     rsp, 28h
0x18000a60f  pop     rdi
0x18000a610  pop     rsi
0x18000a611  pop     rbp
0x18000a612  pop     rbx
0x18000a613  retn
```
