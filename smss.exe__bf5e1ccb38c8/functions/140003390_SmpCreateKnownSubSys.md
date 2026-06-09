# SmpCreateKnownSubSys

- ea: `0x140003390`
- end: `0x140003442`
- name: `SmpCreateKnownSubSys`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001f60`
- `0x1400151e0`

## callees

- `0x140003390`
- `0x140018088`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1400033bb`
- `ntdll!RtlAllocateHeap` at `0x1400033bb`
- `ntdll!RtlFreeHeap` at `0x140003438`
- `ntdll!RtlFreeHeap` at `0x140003438`

## pseudocode

```c
_DWORD *__fastcall SmpCreateKnownSubSys(int a1)
{
  _DWORD *result; // rax
  _DWORD *v3; // rbx
  _DWORD *SubSysSynch; // rax

  result = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), SmBaseTag + 0x80000, 0x58u);
  v3 = result;
  if ( result )
  {
    if ( (a1 & 1) != 0 )
    {
      *((_QWORD *)result + 2) = 0;
LABEL_4:
      *(_QWORD *)v3 = 1;
      v3[2] = a1;
      result = v3;
      v3[6] = -1;
      *((_QWORD *)v3 + 4) = 0;
      *((_QWORD *)v3 + 5) = 0;
      *((_OWORD *)v3 + 3) = 0;
      return result;
    }
    SubSysSynch = SmpGetSubSysSynch();
    *((_QWORD *)v3 + 2) = SubSysSynch;
    if ( SubSysSynch )
      goto LABEL_4;
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003390  mov     [rsp+arg_8], rbx
0x140003395  push    rdi
0x140003396  sub     rsp, 20h
0x14000339a  mov     edx, cs:SmBaseTag
0x1400033a0  mov     edi, ecx
0x1400033a2  mov     rcx, gs:60h
0x1400033ab  add     edx, 80000h; Flags
0x1400033b1  mov     r8d, 58h ; 'X'; Size
0x1400033b7  mov     rcx, [rcx+30h]; HeapHandle
0x1400033bb  call    cs:__imp_RtlAllocateHeap
0x1400033c1  mov     rbx, rax
0x1400033c4  test    rax, rax
0x1400033c7  jz      short loc_14000340D
0x1400033c9  mov     [rsp+28h+arg_0], rsi
0x1400033ce  xor     esi, esi
0x1400033d0  test    dil, 1
0x1400033d4  jz      short loc_140003418
0x1400033d6  mov     [rax+10h], rsi
0x1400033da  xorps   xmm0, xmm0
0x1400033dd  mov     qword ptr [rbx], 1
0x1400033e4  mov     [rbx+8], edi
0x1400033e7  mov     rax, rbx
0x1400033ea  mov     dword ptr [rbx+18h], 0FFFFFFFFh
0x1400033f1  mov     [rbx+20h], rsi
0x1400033f5  mov     [rbx+28h], rsi
0x1400033f9  movups  xmmword ptr [rbx+30h], xmm0
0x1400033fd  mov     rsi, [rsp+28h+arg_0]
0x140003402  mov     rbx, [rsp+28h+arg_8]
0x140003407  add     rsp, 20h
0x14000340b  pop     rdi
0x14000340c  retn
0x14000340d  mov     rbx, [rsp+28h+arg_8]
0x140003412  add     rsp, 20h
0x140003416  pop     rdi
0x140003417  retn
0x140003418  call    SmpGetSubSysSynch
0x14000341d  mov     [rbx+10h], rax
0x140003421  test    rax, rax
0x140003424  jnz     short loc_1400033DA
0x140003426  mov     rcx, gs:60h
0x14000342f  mov     r8, rbx; BaseAddress
0x140003432  xor     edx, edx; Flags
0x140003434  mov     rcx, [rcx+30h]; HeapHandle
0x140003438  call    cs:__imp_RtlFreeHeap
0x14000343e  xor     eax, eax
0x140003440  jmp     short loc_1400033FD
```
