# CMRSWLock::AllocateReaderSlot(ulong)

- ea: `0x18003a7ac`
- end: `0x18003a86f`
- name: `?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z`
- size: `195`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003aa68`

## callees

- `0x18003a7ac`
- `0x18003c514`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18003a7c9`
- `KERNEL32!WaitForSingleObject` at `0x18003a7c9`
- `KERNEL32!EnterCriticalSection` at `0x18003a7f9`
- `KERNEL32!EnterCriticalSection` at `0x18003a7f9`
- `KERNEL32!LeaveCriticalSection` at `0x18003a851`
- `KERNEL32!LeaveCriticalSection` at `0x18003a851`

## string_xrefs

- `0x18003a7ea`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003a83a`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18003a7de`: `WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
__int64 __fastcall CMRSWLock::AllocateReaderSlot(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  unsigned int v4; // edi
  int v5; // r9d
  int v6; // r9d
  __int64 v7; // rax
  _DWORD *OwningThread; // rdx

  v4 = -1;
  if ( WaitForSingleObject(lpCriticalSection[1].LockSemaphore, 0xFFFFFFFF) )
    WdsAssert(
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
      0x9Cu,
      "WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
      v5,
      0);
  EnterCriticalSection(lpCriticalSection);
  v7 = 0;
  if ( !HIDWORD(lpCriticalSection[2].DebugInfo) )
    goto LABEL_9;
  OwningThread = lpCriticalSection[2].OwningThread;
  while ( OwningThread[2 * v7] )
  {
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= HIDWORD(lpCriticalSection[2].DebugInfo) )
      goto LABEL_9;
  }
  OwningThread[2 * v7] = a2;
  v4 = v7;
  if ( (_DWORD)v7 == -1 )
LABEL_9:
    WdsAssert("onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp", 0xB3u, "uIndex != 0xffffffffUL", v6, 0);
  if ( v4 > lpCriticalSection[2].LockCount )
    lpCriticalSection[2].LockCount = v4;
  LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x18003a7ac  mov     [rsp+arg_0], rbx
0x18003a7b1  mov     [rsp+arg_8], rsi
0x18003a7b6  push    rdi
0x18003a7b7  sub     rsp, 30h
0x18003a7bb  mov     esi, edx
0x18003a7bd  mov     rbx, rcx
0x18003a7c0  mov     rcx, [rcx+40h]; hHandle
0x18003a7c4  or      edi, 0FFFFFFFFh
0x18003a7c7  or      edx, edi; dwMilliseconds
0x18003a7c9  call    cs:__imp_WaitForSingleObject
0x18003a7d0  nop     dword ptr [rax+rax+00h]
0x18003a7d5  test    eax, eax
0x18003a7d7  jz      short loc_18003A7F6
0x18003a7d9  and     [rsp+38h+var_18], 0
0x18003a7de  lea     r8, aWaitforsingleo_0; "WaitForSingleObject(m_hReaderSlots, 0xF"...
0x18003a7e5  mov     edx, 9Ch; unsigned int
0x18003a7ea  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003a7f1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a7f6  mov     rcx, rbx; lpCriticalSection
0x18003a7f9  call    cs:__imp_EnterCriticalSection
0x18003a800  nop     dword ptr [rax+rax+00h]
0x18003a805  xor     eax, eax
0x18003a807  cmp     [rbx+54h], eax
0x18003a80a  jbe     short loc_18003A829
0x18003a80c  mov     rdx, [rbx+60h]
0x18003a810  cmp     dword ptr [rdx+rax*8], 0
0x18003a814  jz      short loc_18003A81F
0x18003a816  inc     eax
0x18003a818  cmp     eax, [rbx+54h]
0x18003a81b  jb      short loc_18003A810
0x18003a81d  jmp     short loc_18003A829
0x18003a81f  mov     [rdx+rax*8], esi
0x18003a822  mov     edi, eax
0x18003a824  cmp     eax, 0FFFFFFFFh
0x18003a827  jnz     short loc_18003A846
0x18003a829  and     [rsp+38h+var_18], 0
0x18003a82e  lea     r8, aUindex0xffffff; "uIndex != 0xffffffffUL"
0x18003a835  mov     edx, 0B3h; unsigned int
0x18003a83a  lea     rcx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18003a841  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18003a846  cmp     edi, [rbx+58h]
0x18003a849  jbe     short loc_18003A84E
0x18003a84b  mov     [rbx+58h], edi
0x18003a84e  mov     rcx, rbx; lpCriticalSection
0x18003a851  call    cs:__imp_LeaveCriticalSection
0x18003a858  nop     dword ptr [rax+rax+00h]
0x18003a85d  mov     rbx, [rsp+38h+arg_0]
0x18003a862  mov     eax, edi
0x18003a864  mov     rsi, [rsp+38h+arg_8]
0x18003a869  add     rsp, 30h
0x18003a86d  pop     rdi
0x18003a86e  retn
```
