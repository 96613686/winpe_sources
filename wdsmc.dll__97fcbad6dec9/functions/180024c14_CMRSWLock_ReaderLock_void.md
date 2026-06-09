# CMRSWLock::ReaderLock(void)

- ea: `0x180024c14`
- end: `0x180024cd7`
- name: `?ReaderLock@CMRSWLock@@QEAAXXZ`
- size: `195`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000635c`
- `0x1800063e4`
- `0x1800070ac`
- `0x180007668`
- `0x1800077b0`
- `0x1800078a8`
- `0x180009260`
- `0x18000a5a4`
- `0x18000a880`
- `0x18000f1f4`
- `0x18000f560`
- `0x180018da4`
- `0x180018f20`

## callees

- `0x1800227d4`
- `0x180024994`
- `0x180024c14`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024c21`
- `KERNEL32!GetCurrentThreadId` at `0x180024c21`
- `KERNEL32!LeaveCriticalSection` at `0x180024c57`
- `KERNEL32!LeaveCriticalSection` at `0x180024c82`
- `KERNEL32!LeaveCriticalSection` at `0x180024c57`
- `KERNEL32!LeaveCriticalSection` at `0x180024c82`
- `KERNEL32!LeaveCriticalSection` at `0x180024cd0`
- `KERNEL32!EnterCriticalSection` at `0x180024c2c`
- `KERNEL32!EnterCriticalSection` at `0x180024c6d`
- `KERNEL32!EnterCriticalSection` at `0x180024c2c`
- `KERNEL32!EnterCriticalSection` at `0x180024c6d`
- `KERNEL32!WaitForSingleObject` at `0x180024c8e`
- `KERNEL32!WaitForSingleObject` at `0x180024c8e`

## string_xrefs

- `0x180024ca9`: `onecore\base\eco\wds\wdslib\common\src\mrswlock.cpp`
- `0x180024c9d`: `WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )`

## pseudocode

```c
void __fastcall CMRSWLock::ReaderLock(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD CurrentThreadId; // edi
  _DWORD *OwningThread; // rcx
  __int64 v4; // rax
  int v5; // r9d

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(lpCriticalSection);
  if ( LODWORD(lpCriticalSection[1].SpinCount) == CurrentThreadId )
  {
    ++HIDWORD(lpCriticalSection[1].SpinCount);
  }
  else
  {
    OwningThread = lpCriticalSection[2].OwningThread;
    v4 = 0;
    do
    {
      if ( OwningThread[2 * v4] == CurrentThreadId )
      {
        ++OwningThread[2 * v4 + 1];
        goto LABEL_13;
      }
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 <= lpCriticalSection[2].LockCount );
    ++HIDWORD(lpCriticalSection[2].LockSemaphore);
    LeaveCriticalSection(lpCriticalSection);
    CMRSWLock::AllocateReaderSlot(lpCriticalSection, CurrentThreadId);
    while ( 1 )
    {
      EnterCriticalSection(lpCriticalSection);
      if ( !LODWORD(lpCriticalSection[1].SpinCount) && !LODWORD(lpCriticalSection[2].SpinCount) )
        break;
      LeaveCriticalSection(lpCriticalSection);
      if ( WaitForSingleObject(*(HANDLE *)&lpCriticalSection[1].LockCount, 0xFFFFFFFF) )
        WdsAssert(
          "onecore\\base\\eco\\wds\\wdslib\\common\\src\\mrswlock.cpp",
          0x218u,
          "WaitForSingleObject(m_hWriterDone, 0xFFFFFFFF) == ((((NTSTATUS)0x00000000L) ) + 0 )",
          v5,
          0);
    }
    ++LODWORD(lpCriticalSection[2].LockSemaphore);
    --HIDWORD(lpCriticalSection[2].LockSemaphore);
  }
LABEL_13:
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180024c14  mov     [rsp+arg_0], rbx
0x180024c19  push    rdi
0x180024c1a  sub     rsp, 30h
0x180024c1e  mov     rbx, rcx
0x180024c21  call    cs:__imp_GetCurrentThreadId
0x180024c27  mov     rcx, rbx; lpCriticalSection
0x180024c2a  mov     edi, eax
0x180024c2c  call    cs:__imp_EnterCriticalSection
0x180024c32  cmp     [rbx+48h], edi
0x180024c35  jnz     short loc_180024C3F
0x180024c37  inc     dword ptr [rbx+4Ch]
0x180024c3a  jmp     loc_180024CC3
0x180024c3f  mov     rcx, [rbx+60h]
0x180024c43  xor     eax, eax
0x180024c45  cmp     [rcx+rax*8], edi
0x180024c48  jz      short loc_180024CBF
0x180024c4a  inc     eax
0x180024c4c  cmp     eax, [rbx+58h]
0x180024c4f  jbe     short loc_180024C45
0x180024c51  inc     dword ptr [rbx+6Ch]
0x180024c54  mov     rcx, rbx; lpCriticalSection
0x180024c57  call    cs:__imp_LeaveCriticalSection
0x180024c5d  mov     edx, edi; unsigned int
0x180024c5f  mov     rcx, rbx; lpCriticalSection
0x180024c62  call    ?AllocateReaderSlot@CMRSWLock@@AEAAKK@Z; CMRSWLock::AllocateReaderSlot(ulong)
0x180024c67  or      edi, 0FFFFFFFFh
0x180024c6a  mov     rcx, rbx; lpCriticalSection
0x180024c6d  call    cs:__imp_EnterCriticalSection
0x180024c73  cmp     dword ptr [rbx+48h], 0
0x180024c77  jnz     short loc_180024C7F
0x180024c79  cmp     dword ptr [rbx+70h], 0
0x180024c7d  jz      short loc_180024CB7
0x180024c7f  mov     rcx, rbx; lpCriticalSection
0x180024c82  call    cs:__imp_LeaveCriticalSection
0x180024c88  mov     rcx, [rbx+30h]; hHandle
0x180024c8c  mov     edx, edi; dwMilliseconds
0x180024c8e  call    cs:__imp_WaitForSingleObject
0x180024c94  test    eax, eax
0x180024c96  jz      short loc_180024C6A
0x180024c98  and     [rsp+38h+var_18], 0
0x180024c9d  lea     r8, aWaitforsingleo; "WaitForSingleObject(m_hWriterDone, 0xFF"...
0x180024ca4  mov     edx, 218h; unsigned int
0x180024ca9  lea     rcx, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024cb0  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180024cb5  jmp     short loc_180024C6A
0x180024cb7  inc     dword ptr [rbx+68h]
0x180024cba  add     [rbx+6Ch], edi
0x180024cbd  jmp     short loc_180024CC3
0x180024cbf  inc     dword ptr [rcx+rax*8+4]
0x180024cc3  mov     rcx, rbx
0x180024cc6  mov     rbx, [rsp+38h+arg_0]
0x180024ccb  add     rsp, 30h
0x180024ccf  pop     rdi
0x180024cd0  jmp     cs:__imp_LeaveCriticalSection
```
