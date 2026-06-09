# UmpoInternalReadValueRange

- ea: `0x1800058c4`
- end: `0x1800059ba`
- name: `UmpoInternalReadValueRange`
- size: `246`
- prototype: `__int64 __fastcall(UUID *Uuid1, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b9b8`

## callees

- `0x1800058c4`
- `0x18000681c`

## pseudocode

```c
__int64 __fastcall UmpoInternalReadValueRange(UUID *Uuid1, __int64 a2, _DWORD *a3, _DWORD *a4)
{
  unsigned int v7; // ecx
  DWORD v9; // [rsp+60h] [rbp-38h] BYREF
  int v10; // [rsp+64h] [rbp-34h] BYREF
  __int64 v11[6]; // [rsp+68h] [rbp-30h] BYREF

  v10 = 0;
  LODWORD(v11[0]) = 0;
  v9 = 4;
  v7 = UmpoReadFromSystemPowerKey(0, Uuid1, 0, 9, 0, 0, (__int64)&v10, &v9, 0);
  if ( !v7 )
  {
    v9 = 4;
    v7 = UmpoReadFromSystemPowerKey(0, Uuid1, 0, 10, 0, 0, (__int64)v11, &v9, 0);
    if ( !v7 )
    {
      if ( a3 )
        *a3 = v10;
      if ( a4 )
        *a4 = v11[0];
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800058c4  mov     r11, rsp
0x1800058c7  push    rbx
0x1800058c8  push    rbp
0x1800058c9  push    rsi
0x1800058ca  push    rdi
0x1800058cb  sub     rsp, 78h
0x1800058cf  mov     qword ptr [r11-48h], 0
0x1800058d7  lea     rax, [r11-38h]
0x1800058db  mov     [r11-50h], rax
0x1800058df  mov     rbx, r9
0x1800058e2  lea     rax, [r11-34h]
0x1800058e6  mov     [rsp+98h+var_34], 0
0x1800058ee  mov     [r11-58h], rax
0x1800058f2  mov     rsi, rdx
0x1800058f5  mov     [rsp+98h+var_60], 0; int
0x1800058fd  mov     r9, rdx
0x180005900  mov     qword ptr [r11-68h], 0
0x180005908  mov     rdi, r8
0x18000590b  mov     rbp, rcx
0x18000590e  mov     [rsp+98h+var_70], 9; int
0x180005916  mov     rdx, rcx; Uuid1
0x180005919  mov     [rsp+98h+var_78], 0; char
0x18000591e  xor     r8d, r8d
0x180005921  mov     dword ptr [rsp+98h+var_30], 0
0x180005929  xor     ecx, ecx; __int64
0x18000592b  mov     [rsp+98h+var_38], 4
0x180005933  call    UmpoReadFromSystemPowerKey
0x180005938  mov     ecx, eax
0x18000593a  test    eax, eax
0x18000593c  jz      short loc_180005949
0x18000593e  mov     eax, ecx
0x180005940  add     rsp, 78h
0x180005944  pop     rdi
0x180005945  pop     rsi
0x180005946  pop     rbp
0x180005947  pop     rbx
0x180005948  retn
0x180005949  mov     [rsp+98h+var_48], 0; __int64
0x180005952  lea     rax, [rsp+98h+var_38]
0x180005957  mov     [rsp+98h+var_50], rax; LPDWORD
0x18000595c  mov     r9, rsi
0x18000595f  lea     rax, [rsp+98h+var_30]
0x180005964  mov     [rsp+98h+var_38], 4
0x18000596c  mov     [rsp+98h+var_58], rax; __int64
0x180005971  xor     r8d, r8d
0x180005974  mov     [rsp+98h+var_60], 0; int
0x18000597c  mov     rdx, rbp; Uuid1
0x18000597f  mov     [rsp+98h+var_68], 0; __int64
0x180005988  xor     ecx, ecx; __int64
0x18000598a  mov     [rsp+98h+var_70], 0Ah; int
0x180005992  mov     [rsp+98h+var_78], 0; char
0x180005997  call    UmpoReadFromSystemPowerKey
0x18000599c  mov     ecx, eax
0x18000599e  test    eax, eax
0x1800059a0  jnz     short loc_18000593E
0x1800059a2  test    rdi, rdi
0x1800059a5  jz      short loc_1800059AD
0x1800059a7  mov     eax, [rsp+98h+var_34]
0x1800059ab  mov     [rdi], eax
0x1800059ad  test    rbx, rbx
0x1800059b0  jz      short loc_18000593E
0x1800059b2  mov     eax, dword ptr [rsp+98h+var_30]
0x1800059b6  mov     [rbx], eax
0x1800059b8  jmp     short loc_18000593E
```
