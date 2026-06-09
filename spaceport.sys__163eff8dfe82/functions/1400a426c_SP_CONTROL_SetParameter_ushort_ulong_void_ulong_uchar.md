# SP_CONTROL::SetParameter(ushort *,ulong,void *,ulong,uchar)

- ea: `0x1400a426c`
- end: `0x1400a431d`
- name: `?SetParameter@SP_CONTROL@@QEAAJPEAGKPEAXKE@Z`
- size: `177`
- prototype: `int(SP_CONTROL *__hidden this, unsigned __int16 *, unsigned int, void *, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400a2ad0`
- `0x1400a4324`
- `0x1400aab30`

## callees

- `0x1400a426c`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a42ad`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400a42ad`
- `ntoskrnl!ZwClose` at `0x1400a4305`
- `ntoskrnl!ZwClose` at `0x1400a4305`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a42ed`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400a42ed`

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
0x1400a426c  push    rbx
0x1400a426e  push    rbp
0x1400a426f  push    rsi
0x1400a4270  push    rdi
0x1400a4271  sub     rsp, 48h
0x1400a4275  cmp     [rsp+68h+arg_28], 0
0x1400a427d  mov     rdi, r9
0x1400a4280  mov     esi, r8d
0x1400a4283  mov     [rsp+68h+Handle], 0
0x1400a428c  mov     rbp, rdx
0x1400a428f  mov     rax, rcx
0x1400a4292  jnz     short loc_1400A42CB
0x1400a4294  xor     r9d, r9d
0x1400a4297  lea     rcx, [rsp+68h+Handle]
0x1400a429c  mov     [rsp+68h+ValueData], rcx
0x1400a42a1  mov     rcx, [rax+8]
0x1400a42a5  lea     edx, [r9+1]
0x1400a42a9  lea     r8d, [r9+2]
0x1400a42ad  call    cs:__imp_IoOpenDriverRegistryKey
0x1400a42b4  nop     dword ptr [rax+rax+00h]
0x1400a42b9  mov     ebx, eax
0x1400a42bb  test    eax, eax
0x1400a42bd  js      short loc_1400A42FB
0x1400a42bf  mov     rdx, [rsp+68h+Handle]
0x1400a42c4  mov     ecx, 40000000h
0x1400a42c9  jmp     short loc_1400A42D7
0x1400a42cb  mov     ecx, 1; RelativeTo
0x1400a42d0  lea     rdx, Path; "Spaceport\\Parameters"
0x1400a42d7  mov     eax, [rsp+68h+arg_20]
0x1400a42de  mov     r9d, esi; ValueType
0x1400a42e1  mov     [rsp+68h+ValueLength], eax; ValueLength
0x1400a42e5  mov     r8, rbp; ValueName
0x1400a42e8  mov     [rsp+68h+ValueData], rdi; ValueData
0x1400a42ed  call    cs:__imp_RtlWriteRegistryValue
0x1400a42f4  nop     dword ptr [rax+rax+00h]
0x1400a42f9  mov     ebx, eax
0x1400a42fb  mov     rcx, [rsp+68h+Handle]; Handle
0x1400a4300  test    rcx, rcx
0x1400a4303  jz      short loc_1400A4311
0x1400a4305  call    cs:__imp_ZwClose
0x1400a430c  nop     dword ptr [rax+rax+00h]
0x1400a4311  mov     eax, ebx
0x1400a4313  add     rsp, 48h
0x1400a4317  pop     rdi
0x1400a4318  pop     rsi
0x1400a4319  pop     rbp
0x1400a431a  pop     rbx
0x1400a431b  retn
```
