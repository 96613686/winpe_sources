# RemoveUSBVideoDevice

- ea: `0x1400112c0`
- end: `0x14001134c`
- name: `RemoveUSBVideoDevice`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400110f0`
- `0x14001e130`

## callees

- `0x140010020`
- `0x1400112c0`
- `0x140011354`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400112fc`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1400112fc`

## pseudocode

```c
__int64 (__fastcall *__fastcall RemoveUSBVideoDevice(__int64 a1, __int64 a2))(_QWORD)
{
  __int64 v2; // rbx
  char v3; // di
  __int64 (__fastcall *result)(_QWORD); // rax

  v2 = *(_QWORD *)(a1 + 16);
  v3 = a2;
  LOBYTE(a2) = (_BYTE)a2 == 0;
  StopUSBVideoDevice(a1, a2);
  if ( !*(_BYTE *)v2 )
    *(_BYTE *)v2 = 1;
  if ( !v3 )
  {
    IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(v2 + 768), RemoveUSBVideoDevice, 0x20u);
    ExitIrpThreadAndQueue(v2);
  }
  result = *(__int64 (__fastcall **)(_QWORD))(v2 + 1400);
  if ( result )
  {
    result = (__int64 (__fastcall *)(_QWORD))result(*(_QWORD *)(v2 + 1384));
    *(_OWORD *)(v2 + 1376) = 0;
    *(_OWORD *)(v2 + 1392) = 0;
    *(_OWORD *)(v2 + 1408) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400112c0  mov     [rsp+arg_0], rbx
0x1400112c5  push    rdi
0x1400112c6  sub     rsp, 20h
0x1400112ca  mov     rbx, [rcx+10h]
0x1400112ce  test    dl, dl
0x1400112d0  mov     dil, dl
0x1400112d3  setz    dl
0x1400112d6  call    StopUSBVideoDevice
0x1400112db  cmp     byte ptr [rbx], 0
0x1400112de  jnz     short loc_1400112E3
0x1400112e0  mov     byte ptr [rbx], 1
0x1400112e3  test    dil, dil
0x1400112e6  jnz     short loc_140011310
0x1400112e8  lea     rcx, [rbx+300h]; RemoveLock
0x1400112ef  mov     r8d, 20h ; ' '; RemlockSize
0x1400112f5  lea     rdx, RemoveUSBVideoDevice; Tag
0x1400112fc  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140011303  nop     dword ptr [rax+rax+00h]
0x140011308  mov     rcx, rbx
0x14001130b  call    ExitIrpThreadAndQueue
0x140011310  mov     rax, [rbx+578h]
0x140011317  test    rax, rax
0x14001131a  jz      short loc_140011340
0x14001131c  mov     rcx, [rbx+568h]
0x140011323  call    _guard_dispatch_icall
0x140011328  xorps   xmm0, xmm0
0x14001132b  movups  xmmword ptr [rbx+560h], xmm0
0x140011332  movups  xmmword ptr [rbx+570h], xmm0
0x140011339  movups  xmmword ptr [rbx+580h], xmm0
0x140011340  mov     rbx, [rsp+28h+arg_0]
0x140011345  add     rsp, 20h
0x140011349  pop     rdi
0x14001134a  retn
```
