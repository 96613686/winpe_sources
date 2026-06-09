# CDVRSource::SetAsyncIOReader(IDVRAsyncReader *)

- ea: `0x180007520`
- end: `0x180007589`
- name: `?SetAsyncIOReader@CDVRSource@@UEAAJPEAUIDVRAsyncReader@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, struct IDVRAsyncReader *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007520`
- `0x18002b010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007571`
- `KERNEL32!LeaveCriticalSection` at `0x180007571`
- `KERNEL32!EnterCriticalSection` at `0x18000753f`
- `KERNEL32!EnterCriticalSection` at `0x18000753f`

## pseudocode

```c
__int64 __fastcall CDVRSource::SetAsyncIOReader(CDVRSource *this, struct IDVRAsyncReader *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int v5; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  if ( *((_QWORD *)this + 17) )
  {
    v5 = -2147418113;
  }
  else
  {
    *((_QWORD *)this + 17) = a2;
    (*(void (__fastcall **)(struct IDVRAsyncReader *))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = 0;
  }
  LeaveCriticalSection(v2);
  return v5;
}

```

## disassembly

```asm
0x180007520  mov     [rsp+arg_0], rbx
0x180007525  mov     [rsp+arg_8], rsi
0x18000752a  push    rdi
0x18000752b  sub     rsp, 20h
0x18000752f  lea     rdi, [rcx+0B8h]
0x180007536  mov     rbx, rcx
0x180007539  mov     rcx, rdi; lpCriticalSection
0x18000753c  mov     rsi, rdx
0x18000753f  call    cs:__imp_EnterCriticalSection
0x180007545  cmp     qword ptr [rbx+88h], 0
0x18000754d  jnz     short loc_180007569
0x18000754f  mov     [rbx+88h], rsi
0x180007556  mov     rcx, rsi
0x180007559  mov     rax, [rsi]
0x18000755c  mov     rax, [rax+8]
0x180007560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007565  xor     ebx, ebx
0x180007567  jmp     short loc_18000756E
0x180007569  mov     ebx, 8000FFFFh
0x18000756e  mov     rcx, rdi; lpCriticalSection
0x180007571  call    cs:__imp_LeaveCriticalSection
0x180007577  mov     rsi, [rsp+28h+arg_8]
0x18000757c  mov     eax, ebx
0x18000757e  mov     rbx, [rsp+28h+arg_0]
0x180007583  add     rsp, 20h
0x180007587  pop     rdi
0x180007588  retn
```
