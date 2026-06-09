# CMRSWLock::AllocateReaderSlot(ulong)

- ea: `0x18001f910`
- end: `0x18001f9e0`
- name: `?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z`
- size: `208`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fc00`

## callees

- `0x18001f910`
- `0x180027900`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001f963`
- `KERNEL32!EnterCriticalSection` at `0x18001f963`
- `KERNEL32!LeaveCriticalSection` at `0x18001f9c1`
- `KERNEL32!LeaveCriticalSection` at `0x18001f9c1`
- `KERNEL32!WaitForSingleObject` at `0x18001f92d`
- `KERNEL32!WaitForSingleObject` at `0x18001f92d`

## string_xrefs

- `0x18001f94f`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001f9a5`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001f942`: `WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
__int64 __fastcall CMRSWLock::AllocateReaderSlot(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  _DWORD *OwningThread; // rcx

  v4 = -1;
  if ( WaitForSingleObject(lpCriticalSection[1].LockSemaphore, 0xFFFFFFFF) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x9Cu,
      "WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
      1,
      0);
  EnterCriticalSection(lpCriticalSection);
  v5 = 0;
  if ( !HIDWORD(lpCriticalSection[2].DebugInfo) )
    goto LABEL_9;
  OwningThread = lpCriticalSection[2].OwningThread;
  while ( OwningThread[2 * v5] )
  {
    v5 = (unsigned int)(v5 + 1);
    if ( (unsigned int)v5 >= HIDWORD(lpCriticalSection[2].DebugInfo) )
      goto LABEL_9;
  }
  OwningThread[2 * v5] = a2;
  v4 = v5;
  if ( (_DWORD)v5 == -1 )
LABEL_9:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0xB3u, "uIndex != 0xffffffffUL", 1, 0);
  if ( v4 > lpCriticalSection[2].LockCount )
    lpCriticalSection[2].LockCount = v4;
  LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18001f910  mov     [rsp+arg_0], rbx
0x18001f915  mov     [rsp+arg_8], rsi
0x18001f91a  push    rdi
0x18001f91b  sub     rsp, 30h
0x18001f91f  mov     esi, edx
0x18001f921  mov     rbx, rcx
0x18001f924  mov     rcx, [rcx+40h]; hHandle
0x18001f928  or      edi, 0FFFFFFFFh
0x18001f92b  or      edx, edi; dwMilliseconds
0x18001f92d  call    cs:__imp_WaitForSingleObject
0x18001f934  nop     dword ptr [rax+rax+00h]
0x18001f939  test    eax, eax
0x18001f93b  jz      short loc_18001F960
0x18001f93d  and     [rsp+38h+var_18], 0
0x18001f942  lea     r8, aWaitforsingleo_0; "WaitForSingleObject(m_hReaderSlots, 0xF"...
0x18001f949  mov     r9d, 1; int
0x18001f94f  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f956  mov     edx, 9Ch; unsigned int
0x18001f95b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001f960  mov     rcx, rbx; lpCriticalSection
0x18001f963  call    cs:__imp_EnterCriticalSection
0x18001f96a  nop     dword ptr [rax+rax+00h]
0x18001f96f  xor     eax, eax
0x18001f971  cmp     [rbx+54h], eax
0x18001f974  jbe     short loc_18001F993
0x18001f976  mov     rcx, [rbx+60h]
0x18001f97a  cmp     dword ptr [rcx+rax*8], 0
0x18001f97e  jz      short loc_18001F989
0x18001f980  inc     eax
0x18001f982  cmp     eax, [rbx+54h]
0x18001f985  jb      short loc_18001F97A
0x18001f987  jmp     short loc_18001F993
0x18001f989  mov     [rcx+rax*8], esi
0x18001f98c  mov     edi, eax
0x18001f98e  cmp     eax, 0FFFFFFFFh
0x18001f991  jnz     short loc_18001F9B6
0x18001f993  and     [rsp+38h+var_18], 0
0x18001f998  lea     r8, aUindex0xffffff; "uIndex != 0xffffffffUL"
0x18001f99f  mov     r9d, 1; int
0x18001f9a5  lea     rcx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f9ac  mov     edx, 0B3h; unsigned int
0x18001f9b1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001f9b6  cmp     edi, [rbx+58h]
0x18001f9b9  jbe     short loc_18001F9BE
0x18001f9bb  mov     [rbx+58h], edi
0x18001f9be  mov     rcx, rbx; lpCriticalSection
0x18001f9c1  call    cs:__imp_LeaveCriticalSection
0x18001f9c8  nop     dword ptr [rax+rax+00h]
0x18001f9cd  mov     rbx, [rsp+38h+arg_0]
0x18001f9d2  mov     eax, edi
0x18001f9d4  mov     rsi, [rsp+38h+arg_8]
0x18001f9d9  add     rsp, 30h
0x18001f9dd  pop     rdi
0x18001f9de  retn
```
