# SP_CONTROL::SetParameter(ushort *,ulong,void *,ulong,uchar)

- ea: `0x1400a413c`
- end: `0x1400a41ed`
- name: `?SetParameter@SP_CONTROL@@QEAAJPEAGKPEAXKE@Z`
- size: `177`
- prototype: `int(SP_CONTROL *__hidden this, unsigned __int16 *, unsigned int, void *, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400a29a0`
- `0x1400a41f4`
- `0x1400aa990`

## callees

- `0x1400a413c`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a417d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a417d`
- `ntoskrnl!ZwClose` at `0x1400a41d5`
- `ntoskrnl!ZwClose` at `0x1400a41d5`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a41bd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a41bd`

## pseudocode

```c
__int64 __fastcall SP_CONTROL::SetParameter(
        SP_CONTROL *this,
        unsigned __int16 *a2,
        ULONG a3,
        void *a4,
        ULONG ValueLength,
        unsigned __int8 a6)
{
  int v9; // ebx
  const WCHAR *v10; // rdx
  ULONG v11; // ecx

  if ( a6 )
  {
    v11 = 1;
    v10 = L"Spaceport\\Parameters";
    return (unsigned int)RtlWriteRegistryValue(v11, v10, a2, a3, a4, ValueLength);
  }
  v9 = IoOpenDriverRegistryKey(*((_QWORD *)this + 1), 1, 2);
  if ( v9 >= 0 )
  {
    v10 = 0;
    v11 = 0x40000000;
    return (unsigned int)RtlWriteRegistryValue(v11, v10, a2, a3, a4, ValueLength);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400a413c  push    rbx
0x1400a413e  push    rbp
0x1400a413f  push    rsi
0x1400a4140  push    rdi
0x1400a4141  sub     rsp, 48h
0x1400a4145  cmp     [rsp+68h+arg_28], 0
0x1400a414d  mov     rdi, r9
0x1400a4150  mov     esi, r8d
0x1400a4153  mov     [rsp+68h+Handle], 0
0x1400a415c  mov     rbp, rdx
0x1400a415f  mov     rax, rcx
0x1400a4162  jnz     short loc_1400A419B
0x1400a4164  xor     r9d, r9d
0x1400a4167  lea     rcx, [rsp+68h+Handle]
0x1400a416c  mov     [rsp+68h+ValueData], rcx
0x1400a4171  mov     rcx, [rax+8]
0x1400a4175  lea     edx, [r9+1]
0x1400a4179  lea     r8d, [r9+2]
0x1400a417d  call    cs:__imp_IoOpenDriverRegistryKey
0x1400a4184  nop     dword ptr [rax+rax+00h]
0x1400a4189  mov     ebx, eax
0x1400a418b  test    eax, eax
0x1400a418d  js      short loc_1400A41CB
0x1400a418f  mov     rdx, [rsp+68h+Handle]
0x1400a4194  mov     ecx, 40000000h
0x1400a4199  jmp     short loc_1400A41A7
0x1400a419b  mov     ecx, 1; RelativeTo
0x1400a41a0  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a41a7  mov     eax, [rsp+68h+arg_20]
0x1400a41ae  mov     r9d, esi; ValueType
0x1400a41b1  mov     [rsp+68h+ValueLength], eax; ValueLength
0x1400a41b5  mov     r8, rbp; ValueName
0x1400a41b8  mov     [rsp+68h+ValueData], rdi; ValueData
0x1400a41bd  call    cs:__imp_RtlWriteRegistryValue
0x1400a41c4  nop     dword ptr [rax+rax+00h]
0x1400a41c9  mov     ebx, eax
0x1400a41cb  mov     rcx, [rsp+68h+Handle]; Handle
0x1400a41d0  test    rcx, rcx
0x1400a41d3  jz      short loc_1400A41E1
0x1400a41d5  call    cs:__imp_ZwClose
0x1400a41dc  nop     dword ptr [rax+rax+00h]
0x1400a41e1  mov     eax, ebx
0x1400a41e3  add     rsp, 48h
0x1400a41e7  pop     rdi
0x1400a41e8  pop     rsi
0x1400a41e9  pop     rbp
0x1400a41ea  pop     rbx
0x1400a41eb  retn
```
