# CMulticastContent::Close(int)

- ea: `0x18000433c`
- end: `0x180004430`
- name: `?Close@CMulticastContent@@QEAAKH@Z`
- size: `244`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180002810`
- `0x180002c70`
- `0x180004438`
- `0x1800074bc`

## callees

- `0x18000433c`
- `0x180004f58`
- `0x180004ff8`
- `0x1800193f8`
- `0x1800194ac`
- `0x180019628`
- `0x1800227d4`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004415`
- `KERNEL32!LeaveCriticalSection` at `0x180004415`
- `KERNEL32!EnterCriticalSection` at `0x180004353`
- `KERNEL32!EnterCriticalSection` at `0x180004353`

## string_xrefs

- `0x18000439f`: `pSessionGroup->CanDelete()`

## pseudocode

```c
__int64 __fastcall CMulticastContent::Close(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  LONG *p_LockCount; // r14
  CMulticastSessionGroup *v5; // rdi
  CMulticastSessionGroup *v6; // rbp
  int v7; // r9d
  CMulticastSessionGroup *v8; // rax
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection(lpCriticalSection);
  p_LockCount = &lpCriticalSection[7].LockCount;
  HIDWORD(lpCriticalSection[6].SpinCount) = 1;
  v5 = *(CMulticastSessionGroup **)&lpCriticalSection[7].LockCount;
  while ( v5 )
  {
    v6 = v5;
    v5 = (CMulticastSessionGroup *)*((_QWORD *)v5 + 40);
    CMulticastSessionGroup::Close(v6, a2);
    if ( a2 )
    {
      CMulticastSessionGroup::Shutdown(v6);
      if ( !(unsigned int)CMulticastSessionGroup::CanDelete((LPCRITICAL_SECTION)v6) )
        WdsAssert("base\\eco\\wds\\transport\\server\\mc\\mccontent.cpp", 0x133u, "pSessionGroup->CanDelete()", v7, 0);
    }
  }
  if ( a2 && *(_QWORD *)p_LockCount )
  {
    v10 = *(_QWORD *)p_LockCount;
    do
    {
      v8 = (CMulticastSessionGroup *)CList<CMulticastSessionGroup,CNoLock>::DeleteAt(
                                       &lpCriticalSection[7].LockCount,
                                       &v10);
      if ( v8 )
        CMulticastSessionGroup::`scalar deleting destructor'(v8);
    }
    while ( v10 );
  }
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(
      L"WDSMCCO[%u:%s] Closing...",
      LODWORD(lpCriticalSection[1].DebugInfo),
      lpCriticalSection[5].SpinCount);
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18000433c  mov     [rsp+arg_8], rbx
0x180004341  mov     [rsp+arg_10], rbp
0x180004346  push    rsi
0x180004347  push    rdi
0x180004348  push    r14
0x18000434a  sub     rsp, 30h
0x18000434e  mov     esi, edx
0x180004350  mov     rbx, rcx
0x180004353  call    cs:__imp_EnterCriticalSection
0x180004359  lea     r14, [rbx+120h]
0x180004360  mov     dword ptr [rbx+114h], 1
0x18000436a  mov     rdi, [r14]
0x18000436d  jmp     short loc_1800043B7
0x18000436f  mov     rbp, rdi
0x180004372  mov     edx, esi; int
0x180004374  mov     rdi, [rdi+140h]
0x18000437b  mov     rcx, rbp; this
0x18000437e  call    ?Close@CMulticastSessionGroup@@QEAAKH@Z; CMulticastSessionGroup::Close(int)
0x180004383  test    esi, esi
0x180004385  jz      short loc_1800043B7
0x180004387  mov     rcx, rbp; this
0x18000438a  call    ?Shutdown@CMulticastSessionGroup@@QEAAKXZ; CMulticastSessionGroup::Shutdown(void)
0x18000438f  mov     rcx, rbp; lpCriticalSection
0x180004392  call    ?CanDelete@CMulticastSessionGroup@@QEAAHXZ; CMulticastSessionGroup::CanDelete(void)
0x180004397  test    eax, eax
0x180004399  jnz     short loc_1800043B7
0x18000439b  and     [rsp+48h+var_28], eax
0x18000439f  lea     r8, aPsessiongroupC; "pSessionGroup->CanDelete()"
0x1800043a6  mov     edx, 133h; unsigned int
0x1800043ab  lea     rcx, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800043b2  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800043b7  test    rdi, rdi
0x1800043ba  jnz     short loc_18000436F
0x1800043bc  test    esi, esi
0x1800043be  jz      short loc_1800043EF
0x1800043c0  mov     rax, [r14]
0x1800043c3  test    rax, rax
0x1800043c6  jz      short loc_1800043EF
0x1800043c8  mov     [rsp+48h+arg_0], rax
0x1800043cd  lea     rdx, [rsp+48h+arg_0]
0x1800043d2  mov     rcx, r14
0x1800043d5  call    ?DeleteAt@?$CList@VCMulticastSessionGroup@@VCNoLock@@@@QEAAPEAVCMulticastSessionGroup@@AEAPEAX@Z; CList<CMulticastSessionGroup,CNoLock>::DeleteAt(void * &)
0x1800043da  test    rax, rax
0x1800043dd  jz      short loc_1800043E7
0x1800043df  mov     rcx, rax; this
0x1800043e2  call    ??_GCMulticastSessionGroup@@QEAAPEAXI@Z; CMulticastSessionGroup::`scalar deleting destructor'(uint)
0x1800043e7  cmp     [rsp+48h+arg_0], 0
0x1800043ed  jnz     short loc_1800043CD
0x1800043ef  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800043f6  test    rax, rax
0x1800043f9  jz      short loc_180004412
0x1800043fb  mov     r8, [rbx+0E8h]
0x180004402  lea     rcx, aWdsmccoUSClosi; "WDSMCCO[%u:%s] Closing..."
0x180004409  mov     edx, [rbx+28h]
0x18000440c  call    cs:__guard_dispatch_icall_fptr
0x180004412  mov     rcx, rbx; lpCriticalSection
0x180004415  call    cs:__imp_LeaveCriticalSection
0x18000441b  mov     rbx, [rsp+48h+arg_8]
0x180004420  xor     eax, eax
0x180004422  mov     rbp, [rsp+48h+arg_10]
0x180004427  add     rsp, 30h
0x18000442b  pop     r14
0x18000442d  pop     rdi
0x18000442e  pop     rsi
0x18000442f  retn
```
