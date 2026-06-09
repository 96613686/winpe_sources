# UnloadConfig(void)

- ea: `0x1400022f0`
- end: `0x140002421`
- name: `?UnloadConfig@@YAXXZ`
- size: `305`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001a94`
- `0x14001ffd0`
- `0x140022078`

## callees

- `0x1400022f0`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002342`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000235e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002342`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000235e`
- `ntoskrnl!KeReleaseMutex` at `0x14000240e`
- `ntoskrnl!KeReleaseMutex` at `0x14000240e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000231c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000231c`

## pseudocode

```c
void UnloadConfig(void)
{
  void *v0; // rcx
  _QWORD *v1; // rbx

  if ( byte_140019370 )
  {
    KeWaitForSingleObject(&Mutex, Executive, 0, 0, 0);
    while ( 1 )
    {
      v1 = P;
      if ( !P )
        break;
      P = *(PVOID *)P;
      v0 = (void *)v1[2];
      if ( v0 )
      {
        ExFreePoolWithTag(v0, 0x6E6D7377u);
        v1[2] = 0;
      }
      ExFreePoolWithTag(v1, 0x6E6D7377u);
    }
    if ( qword_140019360 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019360 + 8LL))(qword_140019360);
      qword_140019360 = 0;
    }
    if ( qword_140019358 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019358 + 8LL))(qword_140019358);
      qword_140019358 = 0;
    }
    if ( qword_140019350 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019350 + 8LL))(qword_140019350);
      qword_140019350 = 0;
    }
    if ( qword_140019348 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140019348 + 8LL))(qword_140019348);
      qword_140019348 = 0;
    }
    byte_140019370 = 0;
    KeReleaseMutex(&Mutex, 0);
  }
}

```

## disassembly

```asm
0x1400022f0  push    rbx
0x1400022f2  sub     rsp, 30h
0x1400022f6  mov     al, cs:byte_140019370
0x1400022fc  test    al, al
0x1400022fe  jz      loc_14000241A
0x140002304  xor     r9d, r9d; Alertable
0x140002307  mov     [rsp+38h+Timeout], 0; Timeout
0x140002310  xor     r8d, r8d; WaitMode
0x140002313  lea     rcx, Mutex; Object
0x14000231a  xor     edx, edx; WaitReason
0x14000231c  call    cs:__imp_KeWaitForSingleObject
0x140002323  nop     dword ptr [rax+rax+00h]
0x140002328  jmp     short loc_14000236A
0x14000232a  mov     rax, [rbx]
0x14000232d  mov     cs:P, rax
0x140002334  mov     rcx, [rbx+10h]; P
0x140002338  test    rcx, rcx
0x14000233b  jz      short loc_140002356
0x14000233d  mov     edx, 6E6D7377h; Tag
0x140002342  call    cs:__imp_ExFreePoolWithTag
0x140002349  nop     dword ptr [rax+rax+00h]
0x14000234e  mov     qword ptr [rbx+10h], 0
0x140002356  mov     edx, 6E6D7377h; Tag
0x14000235b  mov     rcx, rbx; P
0x14000235e  call    cs:__imp_ExFreePoolWithTag
0x140002365  nop     dword ptr [rax+rax+00h]
0x14000236a  mov     rbx, cs:P
0x140002371  test    rbx, rbx
0x140002374  jnz     short loc_14000232A
0x140002376  mov     rcx, cs:qword_140019360
0x14000237d  test    rcx, rcx
0x140002380  jz      short loc_140002395
0x140002382  mov     rax, [rcx]
0x140002385  mov     rax, [rax+8]
0x140002389  call    _guard_dispatch_icall
0x14000238e  mov     cs:qword_140019360, rbx
0x140002395  mov     rcx, cs:qword_140019358
0x14000239c  test    rcx, rcx
0x14000239f  jz      short loc_1400023B8
0x1400023a1  mov     rax, [rcx]
0x1400023a4  mov     rax, [rax+8]
0x1400023a8  call    _guard_dispatch_icall
0x1400023ad  mov     cs:qword_140019358, 0
0x1400023b8  mov     rcx, cs:qword_140019350
0x1400023bf  test    rcx, rcx
0x1400023c2  jz      short loc_1400023DB
0x1400023c4  mov     rax, [rcx]
0x1400023c7  mov     rax, [rax+8]
0x1400023cb  call    _guard_dispatch_icall
0x1400023d0  mov     cs:qword_140019350, 0
0x1400023db  mov     rcx, cs:qword_140019348
0x1400023e2  test    rcx, rcx
0x1400023e5  jz      short loc_1400023FE
0x1400023e7  mov     rax, [rcx]
0x1400023ea  mov     rax, [rax+8]
0x1400023ee  call    _guard_dispatch_icall
0x1400023f3  mov     cs:qword_140019348, 0
0x1400023fe  xor     edx, edx; Wait
0x140002400  mov     cs:byte_140019370, 0
0x140002407  lea     rcx, Mutex; Mutex
0x14000240e  call    cs:__imp_KeReleaseMutex
0x140002415  nop     dword ptr [rax+rax+00h]
0x14000241a  add     rsp, 30h
0x14000241e  pop     rbx
0x14000241f  retn
```
