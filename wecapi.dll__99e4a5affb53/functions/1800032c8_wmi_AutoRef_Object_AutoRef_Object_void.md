# wmi::AutoRef<Object>::~AutoRef<Object>(void)

- ea: `0x1800032c8`
- end: `0x180003303`
- name: `??1?$AutoRef@VObject@@@wmi@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be5e`
- `0x18000bfb0`
- `0x18000c0a2`
- `0x18000c0ed`
- `0x18000c138`
- `0x18000c14a`
- `0x18000c207`
- `0x18000c261`
- `0x18000c2c9`
- `0x18000c36a`
- `0x18000c46c`
- `0x18000c516`
- `0x18000c570`
- `0x18000c582`

## callees

- `0x1800032c8`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall wmi::AutoRef<Object>::~AutoRef<Object>(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 8), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      result = (**(__int64 (__fastcall ***)(__int64, __int64))v2)(v2, 1);
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800032c8  push    rbx
0x1800032ca  sub     rsp, 20h
0x1800032ce  mov     rbx, rcx
0x1800032d1  mov     rcx, [rcx]
0x1800032d4  test    rcx, rcx
0x1800032d7  jz      short loc_1800032F6
0x1800032d9  or      eax, 0FFFFFFFFh
0x1800032dc  lock xadd [rcx+8], eax
0x1800032e1  cmp     eax, 1
0x1800032e4  jnz     short loc_1800032F6
0x1800032e6  mov     rax, [rcx]
0x1800032e9  mov     edx, 1
0x1800032ee  mov     rax, [rax]
0x1800032f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f6  mov     qword ptr [rbx], 0
0x1800032fd  add     rsp, 20h
0x180003301  pop     rbx
0x180003302  retn
```
