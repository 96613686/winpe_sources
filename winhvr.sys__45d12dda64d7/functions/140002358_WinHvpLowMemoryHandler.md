# WinHvpLowMemoryHandler

- ea: `0x140002358`
- end: `0x140002411`
- name: `WinHvpLowMemoryHandler`
- size: `185`
- prototype: ``
- caller_count: `17`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140001ef0`
- `0x1400037d0`
- `0x140004a00`
- `0x140005810`
- `0x140008310`
- `0x140009750`
- `0x14001b570`
- `0x14001fd40`
- `0x140020a30`
- `0x140020e60`
- `0x140021360`
- `0x140022bc0`
- `0x140023a70`
- `0x140024110`
- `0x140025ce8`
- `0x140025f30`
- `0x1400262f0`

## callees

- `0x140002358`
- `0x1400024d0`
- `0x140002bf0`
- `0x1400048f0`
- `0x140009c90`
- `0x140022504`

## pseudocode

```c
__int64 __fastcall WinHvpLowMemoryHandler(__int64 a1, unsigned int a2, unsigned int a3, int a4, int a5, char a6)
{
  unsigned int v7; // edi
  unsigned int v8; // ebx
  __int64 v10; // rax
  __int64 v11; // rsi

  v7 = a3;
  v8 = a2;
  if ( ((a1 + 1) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
    return WinHvLowMemoryPolicyAutoDeposit(0, -1, a2, a3, a4, a5);
  if ( a6 )
  {
    return (unsigned int)WinHvpRemotePartitionLowMemoryHandler(a1, a2, a3, a4, a5);
  }
  else
  {
    v10 = WinHvpReferencePartition(a1);
    v11 = v10;
    if ( v10 )
    {
      if ( v8 == -2147418113 )
        v8 = *(_DWORD *)(v10 + 40);
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, int))(v10 + 48))(
             *(_QWORD *)(v10 + 56),
             a1,
             v8,
             v7,
             a4,
             a5);
      WinHvpDereferencePartition(v11);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140002358  push    rbx
0x14000235a  push    rbp
0x14000235b  push    rsi
0x14000235c  push    rdi
0x14000235d  push    r14
0x14000235f  sub     rsp, 40h
0x140002363  lea     rax, [rcx+1]
0x140002367  mov     r14d, r9d
0x14000236a  mov     edi, r8d
0x14000236d  mov     ebx, edx
0x14000236f  mov     rbp, rcx
0x140002372  test    rax, 0FFFFFFFFFFFFFFFDh
0x140002378  jz      short loc_1400023E4
0x14000237a  cmp     [rsp+68h+arg_28], 0
0x140002382  jnz     short loc_1400023CE
0x140002384  call    WinHvpReferencePartition
0x140002389  mov     rsi, rax
0x14000238c  test    rax, rax
0x14000238f  jz      short loc_1400023E0
0x140002391  cmp     ebx, 8000FFFFh
0x140002397  jnz     short loc_14000239C
0x140002399  mov     ebx, [rax+28h]
0x14000239c  mov     ecx, [rsp+68h+arg_20]
0x1400023a3  mov     r9d, edi
0x1400023a6  mov     rax, [rax+30h]
0x1400023aa  mov     r8d, ebx
0x1400023ad  mov     [rsp+68h+var_40], ecx
0x1400023b1  mov     rdx, rbp
0x1400023b4  mov     rcx, [rsi+38h]
0x1400023b8  mov     [rsp+68h+var_48], r14d
0x1400023bd  call    _guard_dispatch_icall
0x1400023c2  mov     rcx, rsi
0x1400023c5  mov     edi, eax
0x1400023c7  call    WinHvpDereferencePartition
0x1400023cc  jmp     short loc_1400023E0
0x1400023ce  mov     eax, [rsp+68h+arg_20]
0x1400023d5  mov     [rsp+68h+var_48], eax
0x1400023d9  call    WinHvpRemotePartitionLowMemoryHandler
0x1400023de  mov     edi, eax
0x1400023e0  mov     eax, edi
0x1400023e2  jmp     short loc_140002405
0x1400023e4  mov     eax, [rsp+68h+arg_20]
0x1400023eb  mov     r9d, edi
0x1400023ee  mov     [rsp+68h+var_40], eax
0x1400023f2  mov     r8d, ebx
0x1400023f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400023f9  mov     [rsp+68h+var_48], r14d
0x1400023fe  xor     ecx, ecx
0x140002400  call    WinHvLowMemoryPolicyAutoDeposit
0x140002405  add     rsp, 40h
0x140002409  pop     r14
0x14000240b  pop     rdi
0x14000240c  pop     rsi
0x14000240d  pop     rbp
0x14000240e  pop     rbx
0x14000240f  retn
```
