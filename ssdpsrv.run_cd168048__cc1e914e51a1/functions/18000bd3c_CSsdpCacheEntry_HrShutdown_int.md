# CSsdpCacheEntry::HrShutdown(int)

- ea: `0x18000bd3c`
- end: `0x18000bdcd`
- name: `?HrShutdown@CSsdpCacheEntry@@QEAAJH@Z`
- size: `145`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *__hidden this, int)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180005260`
- `0x18000bdd4`
- `0x18001cc54`
- `0x18001f54c`
- `0x1800230ac`
- `0x180031944`

## callees

- `0x18000af80`
- `0x18000bd3c`
- `0x180017d28`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdb5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd54`

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
0x18000bd3c  push    rbx
0x18000bd3e  push    rbp
0x18000bd3f  push    rsi
0x18000bd40  push    rdi
0x18000bd41  sub     rsp, 28h
0x18000bd45  lea     rbp, [rcx+0D8h]
0x18000bd4c  mov     rsi, rcx
0x18000bd4f  mov     rcx, rbp; lpCriticalSection
0x18000bd52  mov     ebx, edx
0x18000bd54  call    cs:__imp_EnterCriticalSection
0x18000bd5b  nop     dword ptr [rax+rax+00h]
0x18000bd60  lea     rcx, [rsi+78h]; this
0x18000bd64  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x18000bd68  call    ?HrDelete@CTimerBase@@QEAAJPEAX@Z; CTimerBase::HrDelete(void *)
0x18000bd6d  mov     edi, eax
0x18000bd6f  test    ebx, ebx
0x18000bd71  jz      short loc_18000BD7D
0x18000bd73  mov     rcx, rsi; this
0x18000bd76  call    ?NotifyForAllAddressFamily@CSsdpCacheEntry@@QEAAJH@Z; CSsdpCacheEntry::NotifyForAllAddressFamily(int)
0x18000bd7b  mov     edi, eax
0x18000bd7d  test    edi, edi
0x18000bd7f  jz      short loc_18000BDB2
0x18000bd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd88  lea     rax, WPP_GLOBAL_Control
0x18000bd8f  cmp     rcx, rax
0x18000bd92  jz      short loc_18000BDB2
0x18000bd94  test    byte ptr [rcx+1Ch], 1
0x18000bd98  jz      short loc_18000BDB2
0x18000bd9a  mov     rcx, [rcx+10h]
0x18000bd9e  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18000bda5  mov     edx, 1Fh
0x18000bdaa  mov     r9d, edi
0x18000bdad  call    WPP_SF_d
0x18000bdb2  mov     rcx, rbp; lpCriticalSection
0x18000bdb5  call    cs:__imp_LeaveCriticalSection
0x18000bdbc  nop     dword ptr [rax+rax+00h]
0x18000bdc1  mov     eax, edi
0x18000bdc3  add     rsp, 28h
0x18000bdc7  pop     rdi
0x18000bdc8  pop     rsi
0x18000bdc9  pop     rbp
0x18000bdca  pop     rbx
0x18000bdcb  retn
```
