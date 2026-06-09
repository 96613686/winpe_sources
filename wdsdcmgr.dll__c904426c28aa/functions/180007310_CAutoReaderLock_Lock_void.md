# CAutoReaderLock::Lock(void)

- ea: `0x180007310`
- end: `0x1800073e3`
- name: `?Lock@CAutoReaderLock@@QEAAXXZ`
- size: `211`
- prototype: `void __fastcall(CAutoReaderLock *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`
- `0x1800042f4`
- `0x1800051e8`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800063b4`
- `0x180006dfc`

## callees

- `0x180007310`
- `0x180012f34`
- `0x18001319c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007330`
- `KERNEL32!EnterCriticalSection` at `0x180007371`
- `KERNEL32!EnterCriticalSection` at `0x180007330`
- `KERNEL32!EnterCriticalSection` at `0x180007371`
- `KERNEL32!LeaveCriticalSection` at `0x18000735b`
- `KERNEL32!LeaveCriticalSection` at `0x180007386`
- `KERNEL32!LeaveCriticalSection` at `0x1800073ca`
- `KERNEL32!LeaveCriticalSection` at `0x18000735b`
- `KERNEL32!LeaveCriticalSection` at `0x180007386`
- `KERNEL32!LeaveCriticalSection` at `0x1800073ca`
- `KERNEL32!GetCurrentThreadId` at `0x180007325`
- `KERNEL32!GetCurrentThreadId` at `0x180007325`
- `KERNEL32!WaitForSingleObject` at `0x180007392`
- `KERNEL32!WaitForSingleObject` at `0x180007392`

## string_xrefs

- `0x1800073ad`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x1800073a1`: `WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CAutoReaderLock::Lock(CAutoReaderLock *this)
{
  __int64 v1; // rbx
  DWORD CurrentThreadId; // esi
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // r9d

  v1 = *(_QWORD *)this;
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)v1);
  if ( *(_DWORD *)(v1 + 72) == CurrentThreadId )
  {
    ++*(_DWORD *)(v1 + 76);
  }
  else
  {
    v4 = *(_QWORD *)(v1 + 96);
    v5 = 0;
    do
    {
      if ( *(_DWORD *)(v4 + 8 * v5) == CurrentThreadId )
      {
        ++*(_DWORD *)(v4 + 8 * v5 + 4);
        goto LABEL_13;
      }
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 <= *(_DWORD *)(v1 + 88) );
    ++*(_DWORD *)(v1 + 108);
    LeaveCriticalSection((LPCRITICAL_SECTION)v1);
    CMRSWLock::AllocateReaderSlot((LPCRITICAL_SECTION)v1, CurrentThreadId);
    while ( 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)v1);
      if ( !*(_DWORD *)(v1 + 72) && !*(_DWORD *)(v1 + 112) )
        break;
      LeaveCriticalSection((LPCRITICAL_SECTION)v1);
      if ( WaitForSingleObject(*(HANDLE *)(v1 + 48), 0xFFFFFFFF) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x218u,
          "WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
          v6,
          0);
    }
    ++*(_DWORD *)(v1 + 104);
    --*(_DWORD *)(v1 + 108);
  }
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)v1);
  ++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x180007310  mov     [rsp+arg_0], rbx
0x180007315  mov     [rsp+arg_8], rsi
0x18000731a  push    rdi
0x18000731b  sub     rsp, 30h
0x18000731f  mov     rbx, [rcx]
0x180007322  mov     rdi, rcx
0x180007325  call    cs:__imp_GetCurrentThreadId
0x18000732b  mov     rcx, rbx; lpCriticalSection
0x18000732e  mov     esi, eax
0x180007330  call    cs:__imp_EnterCriticalSection
0x180007336  cmp     [rbx+48h], esi
0x180007339  jnz     short loc_180007343
0x18000733b  inc     dword ptr [rbx+4Ch]
0x18000733e  jmp     loc_1800073C7
0x180007343  mov     rdx, [rbx+60h]
0x180007347  xor     eax, eax
0x180007349  cmp     [rdx+rax*8], esi
0x18000734c  jz      short loc_1800073C3
0x18000734e  inc     eax
0x180007350  cmp     eax, [rbx+58h]
0x180007353  jbe     short loc_180007349
0x180007355  inc     dword ptr [rbx+6Ch]
0x180007358  mov     rcx, rbx; lpCriticalSection
0x18000735b  call    cs:__imp_LeaveCriticalSection
0x180007361  mov     edx, esi; unsigned int
0x180007363  mov     rcx, rbx; lpCriticalSection
0x180007366  call    ?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z; CMRSWLock::AllocateReaderSlot(ulong)
0x18000736b  or      esi, 0FFFFFFFFh
0x18000736e  mov     rcx, rbx; lpCriticalSection
0x180007371  call    cs:__imp_EnterCriticalSection
0x180007377  cmp     dword ptr [rbx+48h], 0
0x18000737b  jnz     short loc_180007383
0x18000737d  cmp     dword ptr [rbx+70h], 0
0x180007381  jz      short loc_1800073BB
0x180007383  mov     rcx, rbx; lpCriticalSection
0x180007386  call    cs:__imp_LeaveCriticalSection
0x18000738c  mov     rcx, [rbx+30h]; hHandle
0x180007390  mov     edx, esi; dwMilliseconds
0x180007392  call    cs:__imp_WaitForSingleObject
0x180007398  test    eax, eax
0x18000739a  jz      short loc_18000736E
0x18000739c  and     [rsp+38h+var_18], 0
0x1800073a1  lea     r8, aWaitforsingleo; "WaitForSingleObject(m_hWriterDone, 0xFF"...
0x1800073a8  mov     edx, 218h; unsigned int
0x1800073ad  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800073b4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800073b9  jmp     short loc_18000736E
0x1800073bb  inc     dword ptr [rbx+68h]
0x1800073be  add     [rbx+6Ch], esi
0x1800073c1  jmp     short loc_1800073C7
0x1800073c3  inc     dword ptr [rdx+rax*8+4]
0x1800073c7  mov     rcx, rbx; lpCriticalSection
0x1800073ca  call    cs:__imp_LeaveCriticalSection
0x1800073d0  inc     dword ptr [rdi+8]
0x1800073d3  mov     rbx, [rsp+38h+arg_0]
0x1800073d8  mov     rsi, [rsp+38h+arg_8]
0x1800073dd  add     rsp, 30h
0x1800073e1  pop     rdi
0x1800073e2  retn
```
