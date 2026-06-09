# CMRSWLock::AllocateReaderSlot(ulong)

- ea: `0x180020910`
- end: `0x1800209e0`
- name: `?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z`
- size: `208`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020c00`

## callees

- `0x180020910`
- `0x180028a50`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180020963`
- `KERNEL32!EnterCriticalSection` at `0x180020963`
- `KERNEL32!LeaveCriticalSection` at `0x1800209c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800209c1`
- `KERNEL32!WaitForSingleObject` at `0x18002092d`
- `KERNEL32!WaitForSingleObject` at `0x18002092d`

## string_xrefs

- `0x18002094f`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800209a5`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180020942`: `WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

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
0x180020910  mov     [rsp+arg_0], rbx
0x180020915  mov     [rsp+arg_8], rsi
0x18002091a  push    rdi
0x18002091b  sub     rsp, 30h
0x18002091f  mov     esi, edx
0x180020921  mov     rbx, rcx
0x180020924  mov     rcx, [rcx+40h]; hHandle
0x180020928  or      edi, 0FFFFFFFFh
0x18002092b  or      edx, edi; dwMilliseconds
0x18002092d  call    cs:__imp_WaitForSingleObject
0x180020934  nop     dword ptr [rax+rax+00h]
0x180020939  test    eax, eax
0x18002093b  jz      short loc_180020960
0x18002093d  and     [rsp+38h+var_18], 0
0x180020942  lea     r8, aWaitforsingleo_0; "WaitForSingleObject(m_hReaderSlots, 0xF"...
0x180020949  mov     r9d, 1; int
0x18002094f  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180020956  mov     edx, 9Ch; unsigned int
0x18002095b  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180020960  mov     rcx, rbx; lpCriticalSection
0x180020963  call    cs:__imp_EnterCriticalSection
0x18002096a  nop     dword ptr [rax+rax+00h]
0x18002096f  xor     eax, eax
0x180020971  cmp     [rbx+54h], eax
0x180020974  jbe     short loc_180020993
0x180020976  mov     rcx, [rbx+60h]
0x18002097a  cmp     dword ptr [rcx+rax*8], 0
0x18002097e  jz      short loc_180020989
0x180020980  inc     eax
0x180020982  cmp     eax, [rbx+54h]
0x180020985  jb      short loc_18002097A
0x180020987  jmp     short loc_180020993
0x180020989  mov     [rcx+rax*8], esi
0x18002098c  mov     edi, eax
0x18002098e  cmp     eax, 0FFFFFFFFh
0x180020991  jnz     short loc_1800209B6
0x180020993  and     [rsp+38h+var_18], 0
0x180020998  lea     r8, aUindex0xffffff; "uIndex != 0xffffffffUL"
0x18002099f  mov     r9d, 1; int
0x1800209a5  lea     rcx, aOnecoreBaseEco_28; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800209ac  mov     edx, 0B3h; unsigned int
0x1800209b1  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800209b6  cmp     edi, [rbx+58h]
0x1800209b9  jbe     short loc_1800209BE
0x1800209bb  mov     [rbx+58h], edi
0x1800209be  mov     rcx, rbx; lpCriticalSection
0x1800209c1  call    cs:__imp_LeaveCriticalSection
0x1800209c8  nop     dword ptr [rax+rax+00h]
0x1800209cd  mov     rbx, [rsp+38h+arg_0]
0x1800209d2  mov     eax, edi
0x1800209d4  mov     rsi, [rsp+38h+arg_8]
0x1800209d9  add     rsp, 30h
0x1800209dd  pop     rdi
0x1800209de  retn
```
