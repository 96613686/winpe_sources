# VidTraceActivityInitialize

- ea: `0x1400246b0`
- end: `0x140024712`
- name: `VidTraceActivityInitialize`
- size: `98`
- prototype: `__int64 __fastcall(GUID *)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x14007a578`
- `0x14007a840`
- `0x14007abc8`
- `0x14007b274`
- `0x14007b724`
- `0x14007ba88`
- `0x14007bdec`
- `0x14007c1f8`
- `0x14007c5bc`
- `0x14007cad0`
- `0x14007ce94`
- `0x14007d1a4`
- `0x14007d59c`
- `0x14007d9b4`
- `0x14007de28`
- `0x14007e1ec`
- `0x14007e4fc`
- `0x14007e8d4`
- `0x14007ece4`
- `0x14007f0bc`
- `0x14007f494`
- `0x14007f888`
- `0x14007fc98`
- `0x1400800a8`
- `0x1400803f8`
- `0x140080744`
- `0x140080c14`
- `0x140080f50`
- `0x140081424`
- `0x14008880c`
- `0x140088f6c`

## callees

- `0x140021800`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x1400246d1`
- `ntoskrnl!EtwActivityIdControl` at `0x1400246e6`
- `ntoskrnl!EtwActivityIdControl` at `0x1400246d1`
- `ntoskrnl!EtwActivityIdControl` at `0x1400246e6`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400246f6`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400246f6`

## pseudocode

```c
__int64 __fastcall VidTraceActivityInitialize(GUID *a1)
{
  __int64 result; // rax

  memset(a1, 0, 0x50u);
  EtwActivityIdControl(5u, a1 + 1);
  EtwActivityIdControl(1u, a1 + 2);
  result = IoSetActivityIdThread(&a1[2]);
  *(_QWORD *)a1->Data4 = result;
  return result;
}

```

## disassembly

```asm
0x1400246b0  mov     [rsp+arg_0], rbx
0x1400246b5  push    rdi
0x1400246b6  sub     rsp, 20h
0x1400246ba  xor     edx, edx; Val
0x1400246bc  mov     rdi, rcx
0x1400246bf  lea     r8d, [rdx+50h]; Size
0x1400246c3  call    memset
0x1400246c8  lea     rdx, [rdi+10h]; ActivityId
0x1400246cc  mov     ecx, 5; ControlCode
0x1400246d1  call    cs:__imp_EtwActivityIdControl
0x1400246d8  nop     dword ptr [rax+rax+00h]
0x1400246dd  lea     rdx, [rdi+20h]; ActivityId
0x1400246e1  mov     ecx, 1; ControlCode
0x1400246e6  call    cs:__imp_EtwActivityIdControl
0x1400246ed  nop     dword ptr [rax+rax+00h]
0x1400246f2  lea     rcx, [rdi+20h]
0x1400246f6  call    cs:__imp_IoSetActivityIdThread
0x1400246fd  nop     dword ptr [rax+rax+00h]
0x140024702  mov     rbx, [rsp+28h+arg_0]
0x140024707  mov     [rdi+8], rax
0x14002470b  add     rsp, 20h
0x14002470f  pop     rdi
0x140024710  retn
```
