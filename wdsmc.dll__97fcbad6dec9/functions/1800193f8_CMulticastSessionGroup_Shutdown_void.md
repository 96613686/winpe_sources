# CMulticastSessionGroup::Shutdown(void)

- ea: `0x1800193f8`
- end: `0x1800194a6`
- name: `?Shutdown@CMulticastSessionGroup@@QEAAKXZ`
- size: `174`
- prototype: `unsigned int __fastcall(CMulticastSessionGroup *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x18000433c`
- `0x180004438`
- `0x180004c60`
- `0x180004ff8`
- `0x1800191c0`

## callees

- `0x180018988`
- `0x1800193f8`
- `0x180019874`
- `0x1800229c0`
- `0x180025850`
- `0x180026d70`

## pseudocode

```c
__int64 __fastcall CMulticastSessionGroup::Shutdown(CMulticastSessionGroup *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  unsigned int v3; // eax
  const char *v4; // rdx
  int v6; // [rsp+20h] [rbp-18h]

  CMulticastSessionGroup::Cleanup(this);
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 36);
  if ( v2 )
  {
    (**v2)(v2, 1);
    *((_QWORD *)this + 36) = 0;
  }
  if ( *((_DWORD *)this + 74) )
  {
    v6 = 1;
    CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 11, 1, v6);
    *((_DWORD *)this + 74) = 0;
  }
  if ( g_ErrLibTraceFunction )
    g_ErrLibTraceFunction(L"WDSMCSG[0x%x] Shutdown.", *((unsigned int *)this + 10));
  v3 = CBandwidthManager::RemoveMulticastSessionGroup((char *)qword_1800336E8 + 560, this);
  return ElValidateWin32(v3, v4, "base\\eco\\wds\\transport\\server\\mc\\mcsessiongroup.cpp", 0xD6u);
}

```

## disassembly

```asm
0x1800193f8  push    rbx
0x1800193fa  sub     rsp, 30h
0x1800193fe  mov     rbx, rcx
0x180019401  call    ?Cleanup@CMulticastSessionGroup@@QEAAXXZ; CMulticastSessionGroup::Cleanup(void)
0x180019406  mov     rcx, [rbx+120h]
0x18001940d  test    rcx, rcx
0x180019410  jz      short loc_18001942B
0x180019412  mov     rax, [rcx]
0x180019415  mov     edx, 1
0x18001941a  mov     rax, [rax]
0x18001941d  call    cs:__guard_dispatch_icall_fptr
0x180019423  and     qword ptr [rbx+120h], 0
0x18001942b  cmp     dword ptr [rbx+128h], 0
0x180019432  jz      short loc_18001945B
0x180019434  mov     edx, 1; unsigned int
0x180019439  mov     [rsp+38h+var_18], 1
0x180019441  mov     r9d, edx
0x180019444  lea     rcx, qword_1800336A0; this
0x18001944b  lea     r8d, [rdx+0Ah]
0x18001944f  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180019454  and     dword ptr [rbx+128h], 0
0x18001945b  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180019462  test    rax, rax
0x180019465  jz      short loc_180019477
0x180019467  mov     edx, [rbx+28h]
0x18001946a  lea     rcx, aWdsmcsg0xXShut; "WDSMCSG[0x%x] Shutdown."
0x180019471  call    cs:__guard_dispatch_icall_fptr
0x180019477  mov     rcx, cs:qword_1800336E8
0x18001947e  mov     rdx, rbx; struct CMulticastSessionGroup *
0x180019481  add     rcx, 230h; lpCriticalSection
0x180019488  call    ?RemoveMulticastSessionGroup@CBandwidthManager@@QEAAKPEAVCMulticastSessionGroup@@@Z; CBandwidthManager::RemoveMulticastSessionGroup(CMulticastSessionGroup *)
0x18001948d  mov     ecx, eax; unsigned int
0x18001948f  lea     r8, aBaseEcoWdsTran_12; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180019496  mov     r9d, 0D6h; unsigned int
0x18001949c  add     rsp, 30h
0x1800194a0  pop     rbx
0x1800194a1  jmp     ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
```
