# CMulticastSessionGroup::CanDelete(void)

- ea: `0x180019628`
- end: `0x1800196ab`
- name: `?CanDelete@CMulticastSessionGroup@@QEAAHXZ`
- size: `131`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000433c`
- `0x180004438`
- `0x18000480c`

## callees

- `0x180019628`
- `0x1800227d4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180019693`
- `KERNEL32!LeaveCriticalSection` at `0x180019693`
- `KERNEL32!EnterCriticalSection` at `0x18001963a`
- `KERNEL32!EnterCriticalSection` at `0x18001963a`

## pseudocode

```c
__int64 __fastcall CMulticastSessionGroup::CanDelete(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi

  EnterCriticalSection(lpCriticalSection);
  v2 = 0;
  v3 = 0;
  if ( LODWORD(lpCriticalSection[7].SpinCount) )
  {
    while ( !*((_QWORD *)lpCriticalSection[7].LockSemaphore + 3 * v3) )
    {
      if ( ++v3 >= LODWORD(lpCriticalSection[7].SpinCount) )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    v2 = 1;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x180019628  mov     [rsp+arg_0], rbx
0x18001962d  mov     [rsp+arg_8], rsi
0x180019632  push    rdi
0x180019633  sub     rsp, 30h
0x180019637  mov     rdi, rcx
0x18001963a  call    cs:__imp_EnterCriticalSection
0x180019640  xor     ebx, ebx
0x180019642  mov     esi, ebx
0x180019644  cmp     [rdi+138h], ebx
0x18001964a  jbe     short loc_18001968B
0x18001964c  cmp     ebx, [rdi+138h]
0x180019652  jb      short loc_18001966E
0x180019654  lea     r8, aUindexMUcount; "uIndex < m_uCount"
0x18001965b  mov     [rsp+38h+var_18], ebx; int
0x18001965f  lea     edx, [rbx+4Ah]; unsigned int
0x180019662  lea     rcx, aInternalOnecor_1; "internal\\onecorebase\\private\\inc\\ec"...
0x180019669  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x18001966e  mov     eax, esi
0x180019670  lea     rcx, [rax+rax*2]
0x180019674  mov     rax, [rdi+130h]
0x18001967b  cmp     [rax+rcx*8], rbx
0x18001967f  jnz     short loc_180019690
0x180019681  inc     esi
0x180019683  cmp     esi, [rdi+138h]
0x180019689  jb      short loc_18001966E
0x18001968b  mov     ebx, 1
0x180019690  mov     rcx, rdi; lpCriticalSection
0x180019693  call    cs:__imp_LeaveCriticalSection
0x180019699  mov     rsi, [rsp+38h+arg_8]
0x18001969e  mov     eax, ebx
0x1800196a0  mov     rbx, [rsp+38h+arg_0]
0x1800196a5  add     rsp, 30h
0x1800196a9  pop     rdi
0x1800196aa  retn
```
