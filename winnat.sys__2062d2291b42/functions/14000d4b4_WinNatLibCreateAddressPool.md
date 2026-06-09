# WinNatLibCreateAddressPool

- ea: `0x14000d4b4`
- end: `0x14000d5fb`
- name: `WinNatLibCreateAddressPool`
- size: `327`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f188`
- `0x1400311f4`

## callees

- `0x14000d4b4`
- `0x14000d604`
- `0x14000da98`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d5a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d5a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d528`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d528`
- `ntoskrnl!ExAllocatePool2` at `0x14000d4d6`
- `ntoskrnl!ExAllocatePool2` at `0x14000d4d6`
- `NETIO!PtCreateTable` at `0x14000d513`
- `NETIO!PtCreateTable` at `0x14000d513`

## pseudocode

```c
__int64 __fastcall WinNatLibCreateAddressPool(__int64 a1, const wchar_t *a2, __int64 a3)
{
  __int64 Pool2; // rax
  size_t v7; // rdx
  __int64 v8; // rbx
  KIRQL v10; // r8
  _QWORD *v11; // rdx

  Pool2 = ExAllocatePool2(64, 576, 1885425239);
  v8 = Pool2;
  if ( !Pool2 )
    return 0;
  RtlStringCchCopyW((NTSTRSAFE_PWSTR)(Pool2 + 440), v7, a2);
  *(_QWORD *)(v8 + 424) = a3;
  if ( (int)PtCreateTable(32, v8 + 416) < 0 )
  {
    ExFreePoolWithTag((PVOID)v8, 0);
    return 0;
  }
  *(_QWORD *)(v8 + 352) = v8 + 344;
  *(_QWORD *)(v8 + 344) = v8 + 344;
  RtlInitializeScalableMrswLock(v8);
  *(_DWORD *)(v8 + 384) = 30;
  *(_DWORD *)(v8 + 396) = 1;
  *(_DWORD *)(v8 + 392) = 1;
  *(_QWORD *)(v8 + 336) = 1;
  *(_DWORD *)(v8 + 380) = 1800;
  *(_DWORD *)(v8 + 376) = 120;
  *(_DWORD *)(v8 + 372) = 300;
  *(_BYTE *)(v8 + 388) = 0;
  *(_QWORD *)(v8 + 408) = a1 + 1280;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1280));
  v11 = *(_QWORD **)(a1 + 1296);
  if ( *v11 != a1 + 1288 )
    __fastfail(3u);
  *(_QWORD *)(v8 + 320) = a1 + 1288;
  *(_QWORD *)(v8 + 328) = v11;
  *v11 = v8 + 320;
  *(_QWORD *)(a1 + 1296) = v8 + 320;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1280), v10);
  return v8;
}

```

## disassembly

```asm
0x14000d4b4  push    rbx
0x14000d4b6  push    rbp
0x14000d4b7  push    rsi
0x14000d4b8  push    rdi
0x14000d4b9  sub     rsp, 28h
0x14000d4bd  mov     rdi, r8
0x14000d4c0  mov     rbp, rdx
0x14000d4c3  mov     rsi, rcx
0x14000d4c6  mov     edx, 240h
0x14000d4cb  mov     ecx, 40h ; '@'
0x14000d4d0  mov     r8d, 70614E57h
0x14000d4d6  call    cs:__imp_ExAllocatePool2
0x14000d4dd  nop     dword ptr [rax+rax+00h]
0x14000d4e2  mov     rbx, rax
0x14000d4e5  test    rax, rax
0x14000d4e8  jnz     short loc_14000D4F1
0x14000d4ea  xor     eax, eax
0x14000d4ec  jmp     loc_14000D5F1
0x14000d4f1  lea     rcx, [rax+1B8h]; pszDest
0x14000d4f8  mov     r8, rbp; pszSrc
0x14000d4fb  call    RtlStringCchCopyW
0x14000d500  lea     rdx, [rbx+1A0h]
0x14000d507  mov     [rbx+1A8h], rdi
0x14000d50e  mov     ecx, 20h ; ' '
0x14000d513  call    cs:__imp_PtCreateTable
0x14000d51a  nop     dword ptr [rax+rax+00h]
0x14000d51f  mov     rcx, rbx; P
0x14000d522  test    eax, eax
0x14000d524  jns     short loc_14000D536
0x14000d526  xor     edx, edx; Tag
0x14000d528  call    cs:__imp_ExFreePoolWithTag
0x14000d52f  nop     dword ptr [rax+rax+00h]
0x14000d534  jmp     short loc_14000D4EA
0x14000d536  lea     rax, [rbx+158h]
0x14000d53d  mov     [rax+8], rax
0x14000d541  mov     [rax], rax
0x14000d544  call    RtlInitializeScalableMrswLock
0x14000d549  mov     eax, 1
0x14000d54e  mov     dword ptr [rbx+180h], 1Eh
0x14000d558  lea     rdi, [rsi+500h]
0x14000d55f  mov     [rbx+18Ch], eax
0x14000d565  mov     rcx, rdi; SpinLock
0x14000d568  mov     [rbx+188h], eax
0x14000d56e  mov     [rbx+150h], rax
0x14000d575  mov     dword ptr [rbx+17Ch], 708h
0x14000d57f  mov     dword ptr [rbx+178h], 78h ; 'x'
0x14000d589  mov     dword ptr [rbx+174h], 12Ch
0x14000d593  mov     byte ptr [rbx+184h], 0
0x14000d59a  mov     [rbx+198h], rdi
0x14000d5a1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d5a8  nop     dword ptr [rax+rax+00h]
0x14000d5ad  lea     rcx, [rsi+508h]
0x14000d5b4  mov     r8b, al
0x14000d5b7  mov     rdx, [rcx+8]
0x14000d5bb  cmp     [rdx], rcx
0x14000d5be  jz      short loc_14000D5C7
0x14000d5c0  mov     ecx, 3
0x14000d5c5  int     29h; Win8: RtlFailFast(ecx)
0x14000d5c7  lea     rax, [rbx+140h]
0x14000d5ce  mov     [rax], rcx
0x14000d5d1  mov     [rax+8], rdx
0x14000d5d5  mov     [rdx], rax
0x14000d5d8  mov     dl, r8b; NewIrql
0x14000d5db  mov     [rcx+8], rax
0x14000d5df  mov     rcx, rdi; SpinLock
0x14000d5e2  call    cs:__imp_KeReleaseSpinLock
0x14000d5e9  nop     dword ptr [rax+rax+00h]
0x14000d5ee  mov     rax, rbx
0x14000d5f1  add     rsp, 28h
0x14000d5f5  pop     rdi
0x14000d5f6  pop     rsi
0x14000d5f7  pop     rbp
0x14000d5f8  pop     rbx
0x14000d5f9  retn
```
