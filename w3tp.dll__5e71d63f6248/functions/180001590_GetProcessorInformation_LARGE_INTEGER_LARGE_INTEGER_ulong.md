# GetProcessorInformation(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong)

- ea: `0x180001590`
- end: `0x18000167d`
- name: `?GetProcessorInformation@@YAJPEAT_LARGE_INTEGER@@0K@Z`
- size: `237`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *, union _LARGE_INTEGER *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180001160`
- `0x180001510`

## callees

- `0x180001590`
- `0x180001f4c`
- `0x180001f8c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800015f2`
- `ntdll!NtQuerySystemInformation` at `0x1800015f2`

## pseudocode

```c
__int64 __fastcall GetProcessorInformation(union _LARGE_INTEGER *a1, union _LARGE_INTEGER *a2, unsigned int a3)
{
  char *v6; // rax
  char *v7; // rdi
  NTSTATUS SystemInformation; // ebp
  unsigned int v9; // ebp
  LONGLONG v11; // rax
  LONGLONG v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r11
  __int64 v16; // r10

  v6 = (char *)operator new(saturated_mul(a3, 0x30u));
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  SystemInformation = NtQuerySystemInformation(SystemProcessorPerformanceInformation, v6, 48 * a3, 0);
  if ( SystemInformation )
  {
    v9 = SystemInformation | 0x10000000;
  }
  else
  {
    v11 = 0;
    v9 = 0;
    v12 = 0;
    v13 = 0;
    if ( a3 )
    {
      v14 = 0;
      do
      {
        ++v13;
        v15 = 48 * v14++;
        v16 = *(_QWORD *)&v7[v15 + 8] + *(_QWORD *)&v7[v15 + 16];
        v12 += v16;
        v11 += v16 - *(_QWORD *)&v7[v15];
      }
      while ( v13 < a3 );
    }
    a1->QuadPart = v11;
    a2->QuadPart = v12;
  }
  operator delete(v7);
  return v9;
}

```

## disassembly

```asm
0x180001590  push    rsi
0x180001592  push    rdi
0x180001593  push    r12
0x180001595  push    r14
0x180001597  push    r15
0x180001599  sub     rsp, 30h
0x18000159d  xor     r12d, r12d
0x1800015a0  mov     esi, r8d
0x1800015a3  mov     r15, rcx
0x1800015a6  mov     [rsp+58h+arg_18], r12
0x1800015ab  mov     r14, rdx
0x1800015ae  mov     [rsp+58h+var_38], r12
0x1800015b3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800015ba  mov     eax, 30h ; '0'
0x1800015bf  mul     rsi
0x1800015c2  cmovb   rax, rcx
0x1800015c6  mov     rcx, rax; Size
0x1800015c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800015ce  mov     rdi, rax
0x1800015d1  test    rax, rax
0x1800015d4  jz      loc_180001676
0x1800015da  lea     r8d, [rsi+rsi*2]
0x1800015de  mov     [rsp+58h+arg_8], rbp
0x1800015e3  shl     r8d, 4; SystemInformationLength
0x1800015e7  xor     r9d, r9d; ReturnLength
0x1800015ea  mov     rdx, rax; SystemInformation
0x1800015ed  mov     ecx, 8; SystemInformationClass
0x1800015f2  call    cs:__imp_NtQuerySystemInformation
0x1800015f8  mov     ebp, eax
0x1800015fa  test    eax, eax
0x1800015fc  jz      short loc_18000161E
0x1800015fe  bts     ebp, 1Ch
0x180001602  mov     rcx, rdi; Block
0x180001605  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000160a  mov     eax, ebp
0x18000160c  mov     rbp, [rsp+58h+arg_8]
0x180001611  add     rsp, 30h
0x180001615  pop     r15
0x180001617  pop     r14
0x180001619  pop     r12
0x18000161b  pop     rdi
0x18000161c  pop     rsi
0x18000161d  retn
0x18000161e  mov     rax, [rsp+58h+arg_18]
0x180001623  mov     ebp, r12d
0x180001626  mov     rcx, [rsp+58h+var_38]
0x18000162b  mov     [rsp+58h+arg_0], rbx
0x180001630  mov     ebx, r12d
0x180001633  test    esi, esi
0x180001635  jz      short loc_180001669
0x180001637  mov     rdx, r12
0x18000163a  nop     word ptr [rax+rax+00h]
0x180001640  lea     r11, [rdx+rdx*2]
0x180001644  inc     ebx
0x180001646  shl     r11, 4
0x18000164a  lea     rdx, [rdx+1]
0x18000164e  mov     r10, [r11+rdi+10h]
0x180001653  add     r10, [r11+rdi+8]
0x180001658  mov     r8, r10
0x18000165b  add     rcx, r10
0x18000165e  sub     r8, [r11+rdi]
0x180001662  add     rax, r8
0x180001665  cmp     ebx, esi
0x180001667  jb      short loc_180001640
0x180001669  mov     rbx, [rsp+58h+arg_0]
0x18000166e  mov     [r15], rax
0x180001671  mov     [r14], rcx
0x180001674  jmp     short loc_180001602
0x180001676  mov     eax, 8007000Eh
0x18000167b  jmp     short loc_180001611
```
