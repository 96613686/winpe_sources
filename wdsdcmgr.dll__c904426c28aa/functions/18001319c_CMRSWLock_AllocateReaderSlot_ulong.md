# CMRSWLock::AllocateReaderSlot(ulong)

- ea: `0x18001319c`
- end: `0x18001324d`
- name: `?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z`
- size: `177`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007310`

## callees

- `0x180012f34`
- `0x18001319c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800131e3`
- `KERNEL32!EnterCriticalSection` at `0x1800131e3`
- `KERNEL32!LeaveCriticalSection` at `0x180013235`
- `KERNEL32!LeaveCriticalSection` at `0x180013235`
- `KERNEL32!WaitForSingleObject` at `0x1800131b9`
- `KERNEL32!WaitForSingleObject` at `0x1800131b9`

## string_xrefs

- `0x1800131d4`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x18001321e`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800131c8`: `WaitForSingleObject(m_hReaderSlots, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

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
0x18001319c  mov     [rsp+arg_0], rbx
0x1800131a1  mov     [rsp+arg_8], rsi
0x1800131a6  push    rdi
0x1800131a7  sub     rsp, 30h
0x1800131ab  mov     esi, edx
0x1800131ad  mov     rbx, rcx
0x1800131b0  mov     rcx, [rcx+40h]; hHandle
0x1800131b4  or      edi, 0FFFFFFFFh
0x1800131b7  or      edx, edi; dwMilliseconds
0x1800131b9  call    cs:__imp_WaitForSingleObject
0x1800131bf  test    eax, eax
0x1800131c1  jz      short loc_1800131E0
0x1800131c3  and     [rsp+38h+var_18], 0
0x1800131c8  lea     r8, aWaitforsingleo_0; "WaitForSingleObject(m_hReaderSlots, 0xF"...
0x1800131cf  mov     edx, 9Ch; unsigned int
0x1800131d4  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800131db  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800131e0  mov     rcx, rbx; lpCriticalSection
0x1800131e3  call    cs:__imp_EnterCriticalSection
0x1800131e9  xor     eax, eax
0x1800131eb  cmp     [rbx+54h], eax
0x1800131ee  jbe     short loc_18001320D
0x1800131f0  mov     rdx, [rbx+60h]
0x1800131f4  cmp     dword ptr [rdx+rax*8], 0
0x1800131f8  jz      short loc_180013203
0x1800131fa  inc     eax
0x1800131fc  cmp     eax, [rbx+54h]
0x1800131ff  jb      short loc_1800131F4
0x180013201  jmp     short loc_18001320D
0x180013203  mov     [rdx+rax*8], esi
0x180013206  mov     edi, eax
0x180013208  cmp     eax, 0FFFFFFFFh
0x18001320b  jnz     short loc_18001322A
0x18001320d  and     [rsp+38h+var_18], 0
0x180013212  lea     r8, aUindex0xffffff; "uIndex != 0xffffffffUL"
0x180013219  mov     edx, 0B3h; unsigned int
0x18001321e  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013225  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001322a  cmp     edi, [rbx+58h]
0x18001322d  jbe     short loc_180013232
0x18001322f  mov     [rbx+58h], edi
0x180013232  mov     rcx, rbx; lpCriticalSection
0x180013235  call    cs:__imp_LeaveCriticalSection
0x18001323b  mov     rbx, [rsp+38h+arg_0]
0x180013240  mov     eax, edi
0x180013242  mov     rsi, [rsp+38h+arg_8]
0x180013247  add     rsp, 30h
0x18001324b  pop     rdi
0x18001324c  retn
```
