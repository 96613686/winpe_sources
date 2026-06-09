# SP_CONTROL::GetParameter(ushort *,ulong,void *)

- ea: `0x1400a2630`
- end: `0x1400a26da`
- name: `?GetParameter@SP_CONTROL@@QEAAJPEAGKPEAX@Z`
- size: `170`
- prototype: `int(SP_CONTROL *__hidden this, unsigned __int16 *, unsigned int, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400a26e0`
- `0x1400a271c`
- `0x1400a2ad0`

## callees

- `0x1400a25a0`
- `0x1400a2630`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a2663`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a2663`
- `ntoskrnl!ZwClose` at `0x1400a26c2`
- `ntoskrnl!ZwClose` at `0x1400a26c2`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::GetParameter(SP_CONTROL *this, unsigned __int16 *a2, unsigned int a3, void *a4)
{
  SP_CONTROL *v7; // rcx
  int Parameter; // ebx
  SP_CONTROL *v9; // rcx

  Parameter = IoOpenDriverRegistryKey(*((_QWORD *)this + 1), 1, 1);
  if ( Parameter >= 0 )
  {
    Parameter = SP_CONTROL::GetParameter(v7, 0x40000000u, 0, a2, a3, a4);
    if ( Parameter == -1073741772 )
      return (unsigned int)SP_CONTROL::GetParameter(v9, 1u, L"Spaceport\\Parameters", a2, a3, a4);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x1400a2630  push    rbx
0x1400a2632  push    rbp
0x1400a2633  push    rsi
0x1400a2634  push    rdi
0x1400a2635  sub     rsp, 38h
0x1400a2639  mov     rcx, [rcx+8]
0x1400a263d  lea     rax, [rsp+58h+Handle]
0x1400a2642  mov     rdi, r9
0x1400a2645  mov     [rsp+58h+Handle], 0
0x1400a264e  xor     r9d, r9d
0x1400a2651  mov     qword ptr [rsp+58h+var_38], rax
0x1400a2656  mov     rbp, rdx
0x1400a2659  mov     esi, r8d
0x1400a265c  lea     edx, [r9+1]
0x1400a2660  mov     r8d, edx
0x1400a2663  call    cs:__imp_IoOpenDriverRegistryKey
0x1400a266a  nop     dword ptr [rax+rax+00h]
0x1400a266f  mov     ebx, eax
0x1400a2671  test    eax, eax
0x1400a2673  js      short loc_1400A26B8
0x1400a2675  mov     r8, [rsp+58h+Handle]; unsigned __int16 *
0x1400a267a  mov     r9, rbp; unsigned __int16 *
0x1400a267d  mov     [rsp+58h+var_30], rdi; void *
0x1400a2682  mov     edx, 40000000h; unsigned int
0x1400a2687  mov     [rsp+58h+var_38], esi; unsigned int
0x1400a268b  call    ?GetParameter@SP_CONTROL@@QEAAJKPEAG0KPEAX@Z; SP_CONTROL::GetParameter(ulong,ushort *,ushort *,ulong,void *)
0x1400a2690  mov     ebx, eax
0x1400a2692  cmp     eax, 0C0000034h
0x1400a2697  jnz     short loc_1400A26B8
0x1400a2699  mov     [rsp+58h+var_30], rdi; void *
0x1400a269e  lea     r8, Path; "Spaceport\\Parameters"
0x1400a26a5  mov     r9, rbp; unsigned __int16 *
0x1400a26a8  mov     [rsp+58h+var_38], esi; unsigned int
0x1400a26ac  mov     edx, 1; unsigned int
0x1400a26b1  call    ?GetParameter@SP_CONTROL@@QEAAJKPEAG0KPEAX@Z; SP_CONTROL::GetParameter(ulong,ushort *,ushort *,ulong,void *)
0x1400a26b6  mov     ebx, eax
0x1400a26b8  mov     rcx, [rsp+58h+Handle]; Handle
0x1400a26bd  test    rcx, rcx
0x1400a26c0  jz      short loc_1400A26CE
0x1400a26c2  call    cs:__imp_ZwClose
0x1400a26c9  nop     dword ptr [rax+rax+00h]
0x1400a26ce  mov     eax, ebx
0x1400a26d0  add     rsp, 38h
0x1400a26d4  pop     rdi
0x1400a26d5  pop     rsi
0x1400a26d6  pop     rbp
0x1400a26d7  pop     rbx
0x1400a26d8  retn
```
