# TdiPnPPowerComplete

- ea: `0x1400051f0`
- end: `0x1400052e1`
- name: `TdiPnPPowerComplete`
- size: `241`
- prototype: `void __stdcall(HANDLE BindingHandle, PNET_PNP_EVENT PowerEvent, NTSTATUS Status)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400051f0`
- `0x140005530`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000527f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005296`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000527f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005296`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ce`

## pseudocode

```c
void __stdcall TdiPnPPowerComplete(HANDLE BindingHandle, PNET_PNP_EVENT PowerEvent, NTSTATUS Status)
{
  ULONG_PTR v3; // rbx
  ULONG_PTR v4; // rax
  _QWORD *v5; // rcx
  void (__fastcall *v6)(PNET_PNP_EVENT, _QWORD); // rax
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  v3 = PowerEvent->TdiReserved[0];
  if ( v3 )
  {
    while ( *(_QWORD *)(v3 + 104) )
      v3 = *(_QWORD *)(v3 + 104);
    if ( Status )
      *(_DWORD *)(v3 + 56) = Status;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 96), 0xFFFFFFFF) == 1 )
    {
      v4 = PowerEvent->TdiReserved[0];
      if ( *(_QWORD *)(v4 + 104) )
      {
        do
        {
          v5 = (_QWORD *)(v4 + 104);
          v4 = *(_QWORD *)(v4 + 104);
        }
        while ( *(_QWORD *)(v4 + 104) );
        *v5 = 0;
        Status = 0;
      }
      else
      {
        *(_OWORD *)PowerEvent->TdiReserved = 0;
        *(_OWORD *)&PowerEvent->TdiReserved[2] = 0;
      }
      v6 = *(void (__fastcall **)(PNET_PNP_EVENT, _QWORD))(v3 + 48);
      if ( v6 )
        v6(PowerEvent, (unsigned int)Status);
      v7 = *(void **)(v3 + 128);
      if ( v7 )
        ExFreePoolWithTag(v7, 0);
      v8 = *(void **)(v3 + 80);
      if ( v8 )
      {
        ExFreePoolWithTag(v8, 0);
        *(_QWORD *)(v3 + 80) = 0;
      }
      v9 = *(void **)(v3 + 88);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0);
        *(_QWORD *)(v3 + 88) = 0;
      }
      ExFreePoolWithTag((PVOID)v3, 0);
    }
  }
}

```

## disassembly

```asm
0x1400051f0  push    rbx
0x1400051f2  sub     rsp, 20h
0x1400051f6  mov     rbx, [rdx+58h]
0x1400051fa  mov     r9, rdx
0x1400051fd  test    rbx, rbx
0x140005200  jz      loc_1400052DA
0x140005206  jmp     short loc_14000520C
0x140005208  mov     rbx, [rbx+68h]
0x14000520c  cmp     qword ptr [rbx+68h], 0
0x140005211  jnz     short loc_140005208
0x140005213  test    r8d, r8d
0x140005216  jz      short loc_14000521C
0x140005218  mov     [rbx+38h], r8d
0x14000521c  or      eax, 0FFFFFFFFh
0x14000521f  lock xadd [rbx+60h], eax
0x140005224  cmp     eax, 1
0x140005227  jnz     loc_1400052DA
0x14000522d  mov     rax, [rdx+58h]
0x140005231  cmp     qword ptr [rax+68h], 0
0x140005236  jz      short loc_140005252
0x140005238  lea     rcx, [rax+68h]
0x14000523c  mov     rax, [rcx]
0x14000523f  cmp     qword ptr [rax+68h], 0
0x140005244  jnz     short loc_140005238
0x140005246  mov     qword ptr [rcx], 0
0x14000524d  xor     r8d, r8d
0x140005250  jmp     short loc_14000525D
0x140005252  xorps   xmm0, xmm0
0x140005255  movups  xmmword ptr [rdx+58h], xmm0
0x140005259  movups  xmmword ptr [rdx+68h], xmm0
0x14000525d  mov     rax, [rbx+30h]
0x140005261  test    rax, rax
0x140005264  jz      short loc_140005271
0x140005266  mov     edx, r8d
0x140005269  mov     rcx, r9
0x14000526c  call    _guard_dispatch_icall
0x140005271  mov     rcx, [rbx+80h]; P
0x140005278  test    rcx, rcx
0x14000527b  jz      short loc_14000528B
0x14000527d  xor     edx, edx; Tag
0x14000527f  call    cs:__imp_ExFreePoolWithTag
0x140005286  nop     dword ptr [rax+rax+00h]
0x14000528b  mov     rcx, [rbx+50h]; P
0x14000528f  test    rcx, rcx
0x140005292  jz      short loc_1400052AA
0x140005294  xor     edx, edx; Tag
0x140005296  call    cs:__imp_ExFreePoolWithTag
0x14000529d  nop     dword ptr [rax+rax+00h]
0x1400052a2  mov     qword ptr [rbx+50h], 0
0x1400052aa  mov     rcx, [rbx+58h]; P
0x1400052ae  test    rcx, rcx
0x1400052b1  jz      short loc_1400052C9
0x1400052b3  xor     edx, edx; Tag
0x1400052b5  call    cs:__imp_ExFreePoolWithTag
0x1400052bc  nop     dword ptr [rax+rax+00h]
0x1400052c1  mov     qword ptr [rbx+58h], 0
0x1400052c9  xor     edx, edx; Tag
0x1400052cb  mov     rcx, rbx; P
0x1400052ce  call    cs:__imp_ExFreePoolWithTag
0x1400052d5  nop     dword ptr [rax+rax+00h]
0x1400052da  add     rsp, 20h
0x1400052de  pop     rbx
0x1400052df  retn
```
