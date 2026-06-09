# WinHvpRemotePartitionLowMemoryHandler

- ea: `0x140022504`
- end: `0x1400225b9`
- name: `WinHvpRemotePartitionLowMemoryHandler`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002358`
- `0x1400218a0`
- `0x1400220e0`

## callees

- `0x140009c90`
- `0x140022504`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002255f`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002255f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022528`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022528`

## pseudocode

```c
__int64 __fastcall WinHvpRemotePartitionLowMemoryHandler(void *a1, unsigned int a2, unsigned int a3, int a4, int a5)
{
  _UNKNOWN **v6; // rbx
  char v7; // si
  _UNKNOWN **i; // rax
  unsigned int (__fastcall *v12)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD); // rax

  v6 = 0;
  v7 = 0;
  ExAcquireFastMutex(&WinHvpRemoteIdMapLock);
  for ( i = (_UNKNOWN **)WinHvpRemoteIdMap; i != &WinHvpRemoteIdMap; i = (_UNKNOWN **)*i )
  {
    if ( i[3] == a1 )
    {
      v6 = i;
      v7 = 1;
      break;
    }
  }
  ExReleaseFastMutex(&WinHvpRemoteIdMapLock);
  if ( v7 )
  {
    v12 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))v6[5];
    if ( v12 )
    {
      if ( a2 == -2147418113 )
        a2 = *((_DWORD *)v6 + 8);
      return v12(v6[6], v6[2], a2, a3, a4, a5);
    }
  }
  return a3;
}

```

## disassembly

```asm
0x140022504  push    rbx
0x140022506  push    rbp
0x140022507  push    rsi
0x140022508  push    rdi
0x140022509  push    r14
0x14002250b  push    r15
0x14002250d  sub     rsp, 48h
0x140022511  mov     r14, rcx
0x140022514  xor     ebx, ebx
0x140022516  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x14002251d  xor     sil, sil
0x140022520  mov     r15d, r9d
0x140022523  mov     ebp, r8d
0x140022526  mov     edi, edx
0x140022528  call    cs:__imp_ExAcquireFastMutex
0x14002252f  nop     dword ptr [rax+rax+00h]
0x140022534  mov     rax, cs:WinHvpRemoteIdMap
0x14002253b  lea     rcx, WinHvpRemoteIdMap
0x140022542  cmp     rax, rcx
0x140022545  jz      short loc_140022558
0x140022547  cmp     [rax+18h], r14
0x14002254b  jz      short loc_140022552
0x14002254d  mov     rax, [rax]
0x140022550  jmp     short loc_14002253B
0x140022552  mov     rbx, rax
0x140022555  mov     sil, 1
0x140022558  lea     rcx, WinHvpRemoteIdMapLock; FastMutex
0x14002255f  call    cs:__imp_ExReleaseFastMutex
0x140022566  nop     dword ptr [rax+rax+00h]
0x14002256b  test    sil, sil
0x14002256e  jz      short loc_1400225A9
0x140022570  mov     rax, [rbx+28h]
0x140022574  test    rax, rax
0x140022577  jz      short loc_1400225A9
0x140022579  cmp     edi, 8000FFFFh
0x14002257f  jnz     short loc_140022584
0x140022581  mov     edi, [rbx+20h]
0x140022584  mov     edx, [rsp+78h+arg_20]
0x14002258b  mov     r9d, ebp
0x14002258e  mov     rcx, [rbx+30h]
0x140022592  mov     r8d, edi
0x140022595  mov     [rsp+78h+var_50], edx
0x140022599  mov     rdx, [rbx+10h]
0x14002259d  mov     [rsp+78h+var_58], r15d
0x1400225a2  call    _guard_dispatch_icall
0x1400225a7  mov     ebp, eax
0x1400225a9  mov     eax, ebp
0x1400225ab  add     rsp, 48h
0x1400225af  pop     r15
0x1400225b1  pop     r14
0x1400225b3  pop     rdi
0x1400225b4  pop     rsi
0x1400225b5  pop     rbp
0x1400225b6  pop     rbx
0x1400225b7  retn
```
