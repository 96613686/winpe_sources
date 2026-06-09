# WinNatLibCreateAddressPool

- ea: `0x14000d4e4`
- end: `0x14000d62b`
- name: `WinNatLibCreateAddressPool`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f130`
- `0x1400300c4`

## callees

- `0x14000d4e4`
- `0x14000d634`
- `0x14000dac8`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000d612`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d612`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d5d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d5d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d558`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d558`
- `ntoskrnl!ExAllocatePool2` at `0x14000d506`
- `ntoskrnl!ExAllocatePool2` at `0x14000d506`
- `NETIO!PtCreateTable` at `0x14000d543`
- `NETIO!PtCreateTable` at `0x14000d543`

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
0x14000d4e4  push    rbx
0x14000d4e6  push    rbp
0x14000d4e7  push    rsi
0x14000d4e8  push    rdi
0x14000d4e9  sub     rsp, 28h
0x14000d4ed  mov     rdi, r8
0x14000d4f0  mov     rbp, rdx
0x14000d4f3  mov     rsi, rcx
0x14000d4f6  mov     edx, 240h
0x14000d4fb  mov     ecx, 40h ; '@'
0x14000d500  mov     r8d, 70614E57h
0x14000d506  call    cs:__imp_ExAllocatePool2
0x14000d50d  nop     dword ptr [rax+rax+00h]
0x14000d512  mov     rbx, rax
0x14000d515  test    rax, rax
0x14000d518  jnz     short loc_14000D521
0x14000d51a  xor     eax, eax
0x14000d51c  jmp     loc_14000D621
0x14000d521  lea     rcx, [rax+1B8h]; pszDest
0x14000d528  mov     r8, rbp; pszSrc
0x14000d52b  call    RtlStringCchCopyW
0x14000d530  lea     rdx, [rbx+1A0h]
0x14000d537  mov     [rbx+1A8h], rdi
0x14000d53e  mov     ecx, 20h ; ' '
0x14000d543  call    cs:__imp_PtCreateTable
0x14000d54a  nop     dword ptr [rax+rax+00h]
0x14000d54f  mov     rcx, rbx; P
0x14000d552  test    eax, eax
0x14000d554  jns     short loc_14000D566
0x14000d556  xor     edx, edx; Tag
0x14000d558  call    cs:__imp_ExFreePoolWithTag
0x14000d55f  nop     dword ptr [rax+rax+00h]
0x14000d564  jmp     short loc_14000D51A
0x14000d566  lea     rax, [rbx+158h]
0x14000d56d  mov     [rax+8], rax
0x14000d571  mov     [rax], rax
0x14000d574  call    RtlInitializeScalableMrswLock
0x14000d579  mov     eax, 1
0x14000d57e  mov     dword ptr [rbx+180h], 1Eh
0x14000d588  lea     rdi, [rsi+500h]
0x14000d58f  mov     [rbx+18Ch], eax
0x14000d595  mov     rcx, rdi; SpinLock
0x14000d598  mov     [rbx+188h], eax
0x14000d59e  mov     [rbx+150h], rax
0x14000d5a5  mov     dword ptr [rbx+17Ch], 708h
0x14000d5af  mov     dword ptr [rbx+178h], 78h ; 'x'
0x14000d5b9  mov     dword ptr [rbx+174h], 12Ch
0x14000d5c3  mov     byte ptr [rbx+184h], 0
0x14000d5ca  mov     [rbx+198h], rdi
0x14000d5d1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d5d8  nop     dword ptr [rax+rax+00h]
0x14000d5dd  lea     rcx, [rsi+508h]
0x14000d5e4  mov     r8b, al
0x14000d5e7  mov     rdx, [rcx+8]
0x14000d5eb  cmp     [rdx], rcx
0x14000d5ee  jz      short loc_14000D5F7
0x14000d5f0  mov     ecx, 3
0x14000d5f5  int     29h; Win8: RtlFailFast(ecx)
0x14000d5f7  lea     rax, [rbx+140h]
0x14000d5fe  mov     [rax], rcx
0x14000d601  mov     [rax+8], rdx
0x14000d605  mov     [rdx], rax
0x14000d608  mov     dl, r8b; NewIrql
0x14000d60b  mov     [rcx+8], rax
0x14000d60f  mov     rcx, rdi; SpinLock
0x14000d612  call    cs:__imp_KeReleaseSpinLock
0x14000d619  nop     dword ptr [rax+rax+00h]
0x14000d61e  mov     rax, rbx
0x14000d621  add     rsp, 28h
0x14000d625  pop     rdi
0x14000d626  pop     rsi
0x14000d627  pop     rbp
0x14000d628  pop     rbx
0x14000d629  retn
```
