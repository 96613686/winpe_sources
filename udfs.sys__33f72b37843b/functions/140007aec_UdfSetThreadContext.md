# UdfSetThreadContext

- ea: `0x140007aec`
- end: `0x140007b80`
- name: `UdfSetThreadContext`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140006680`
- `0x1400077f0`
- `0x1400094c0`
- `0x14000cce0`
- `0x140016170`
- `0x14002c330`
- `0x1400379c0`

## callees

- `0x140007aec`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140007b5b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007b5b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007afc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007afc`
- `ntoskrnl!IoWithinStackLimits` at `0x140007b25`
- `ntoskrnl!IoWithinStackLimits` at `0x140007b25`

## pseudocode

```c
__int64 __fastcall UdfSetThreadContext(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rbx
  ULONG_PTR TopLevelIrp; // rdi
  __int64 result; // rax

  v4 = (_DWORD *)(a1 + 28);
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( !TopLevelIrp )
    *v4 |= 0x10u;
  if ( (*v4 & 0x10) != 0
    || !IoWithinStackLimits(TopLevelIrp, 0x18u)
    || (TopLevelIrp & 3) != 0
    || *(_DWORD *)TopLevelIrp != 1397113941 )
  {
    *(_DWORD *)a2 = 1397113941;
    *(_QWORD *)(a2 + 8) = TopLevelIrp;
    *(_QWORD *)(a2 + 16) = a1;
    IoSetTopLevelIrp((PIRP)a2);
    *v4 |= 0x20u;
    result = a1;
    *(_QWORD *)(a1 + 64) = a2;
  }
  else
  {
    result = *(_QWORD *)(TopLevelIrp + 16);
  }
  *(_QWORD *)(a1 + 48) = result;
  return result;
}

```

## disassembly

```asm
0x140007aec  push    rbx
0x140007aee  push    rsi
0x140007aef  push    rdi
0x140007af0  push    r14
0x140007af2  sub     rsp, 28h
0x140007af6  mov     r14, rdx
0x140007af9  mov     rsi, rcx
0x140007afc  call    cs:__imp_IoGetTopLevelIrp
0x140007b03  nop     dword ptr [rax+rax+00h]
0x140007b08  lea     rbx, [rsi+1Ch]
0x140007b0c  mov     rdi, rax
0x140007b0f  test    rax, rax
0x140007b12  jnz     short loc_140007B17
0x140007b14  or      dword ptr [rbx], 10h
0x140007b17  mov     eax, [rbx]
0x140007b19  test    al, 10h
0x140007b1b  jnz     short loc_140007B49
0x140007b1d  mov     edx, 18h; RegionSize
0x140007b22  mov     rcx, rdi; RegionStart
0x140007b25  call    cs:__imp_IoWithinStackLimits
0x140007b2c  nop     dword ptr [rax+rax+00h]
0x140007b31  test    eax, eax
0x140007b33  jz      short loc_140007B49
0x140007b35  test    dil, 3
0x140007b39  jnz     short loc_140007B49
0x140007b3b  cmp     dword ptr [rdi], 53464455h
0x140007b41  jnz     short loc_140007B49
0x140007b43  mov     rax, [rdi+10h]
0x140007b47  jmp     short loc_140007B71
0x140007b49  mov     rcx, r14; Irp
0x140007b4c  mov     dword ptr [r14], 53464455h
0x140007b53  mov     [r14+8], rdi
0x140007b57  mov     [r14+10h], rsi
0x140007b5b  call    cs:__imp_IoSetTopLevelIrp
0x140007b62  nop     dword ptr [rax+rax+00h]
0x140007b67  or      dword ptr [rbx], 20h
0x140007b6a  mov     rax, rsi
0x140007b6d  mov     [rsi+40h], r14
0x140007b71  mov     [rsi+30h], rax
0x140007b75  add     rsp, 28h
0x140007b79  pop     r14
0x140007b7b  pop     rdi
0x140007b7c  pop     rsi
0x140007b7d  pop     rbx
0x140007b7e  retn
```
