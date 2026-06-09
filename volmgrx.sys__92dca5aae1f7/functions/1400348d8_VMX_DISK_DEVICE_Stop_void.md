# VMX_DISK_DEVICE::Stop(void)

- ea: `0x1400348d8`
- end: `0x140034929`
- name: `?Stop@VMX_DISK_DEVICE@@QEAAXXZ`
- size: `81`
- prototype: `void __fastcall(VMX_DISK_DEVICE *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140034c20`
- `0x14005d780`

## callees

- `0x1400348d8`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140034910`
- `ntoskrnl!KeDelayExecutionThread` at `0x140034910`

## pseudocode

```c
void __fastcall VMX_DISK_DEVICE::Stop(VMX_DISK_DEVICE *this)
{
  bool v1; // zf
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)this + 10) == 0;
  Interval.QuadPart = 0;
  if ( v1 )
  {
    _InterlockedExchange((volatile __int32 *)this + 10, 1);
    v1 = *((_DWORD *)this + 14) == 0;
    Interval.QuadPart = -1000;
    if ( !v1 )
    {
      do
        KeDelayExecutionThread(0, 0, &Interval);
      while ( *((_DWORD *)this + 14) );
    }
  }
}

```

## disassembly

```asm
0x1400348d8  push    rbx
0x1400348da  sub     rsp, 20h
0x1400348de  cmp     dword ptr [rcx+28h], 0
0x1400348e2  mov     rbx, rcx
0x1400348e5  mov     qword ptr [rsp+28h+Interval], 0
0x1400348ee  jnz     short loc_140034922
0x1400348f0  mov     eax, 1
0x1400348f5  xchg    eax, [rcx+28h]
0x1400348f8  cmp     dword ptr [rcx+38h], 0
0x1400348fc  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFFC18h
0x140034905  jz      short loc_140034922
0x140034907  lea     r8, [rsp+28h+Interval]; Interval
0x14003490c  xor     edx, edx; Alertable
0x14003490e  xor     ecx, ecx; WaitMode
0x140034910  call    cs:__imp_KeDelayExecutionThread
0x140034917  nop     dword ptr [rax+rax+00h]
0x14003491c  cmp     dword ptr [rbx+38h], 0
0x140034920  jnz     short loc_140034907
0x140034922  add     rsp, 20h
0x140034926  pop     rbx
0x140034927  retn
```
