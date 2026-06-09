# CW32System::ImmSetCompositionStringW(ulong,ulong,void *,ulong,void *,ulong)

- ea: `0x180091590`
- end: `0x1800915f5`
- name: `?ImmSetCompositionStringW@CW32System@@SAHKKPEAXK0K@Z`
- size: `101`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180053334`

## callees

- `0x180091590`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x1800915af`: `ImmSetCompositionStringW`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetCompositionStringW(unsigned int a1, unsigned int a2, void *a3, unsigned int a4)
{
  __int64 (__fastcall *v4)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD); // rax

  v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD))qword_1800A7268;
  if ( !qword_1800A7268 )
  {
    SetIMEProcAddr(&qword_1800A7268, 0, "ImmSetCompositionStringW");
    v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD, _QWORD, _DWORD))qword_1800A7268;
  }
  return v4(a1, a2, a3, a4, 0, 0);
}

```

## disassembly

```asm
0x180091590  push    rbx
0x180091592  push    rbp
0x180091593  push    rsi
0x180091594  push    rdi
0x180091595  sub     rsp, 48h
0x180091599  mov     rax, cs:qword_1800A7268
0x1800915a0  mov     ebx, r9d
0x1800915a3  mov     rdi, r8
0x1800915a6  mov     esi, edx
0x1800915a8  mov     ebp, ecx
0x1800915aa  test    rax, rax
0x1800915ad  jnz     short loc_1800915CB
0x1800915af  lea     r8, aImmsetcomposit; "ImmSetCompositionStringW"
0x1800915b6  xor     edx, edx
0x1800915b8  lea     rcx, qword_1800A7268
0x1800915bf  call    SetIMEProcAddr
0x1800915c4  mov     rax, cs:qword_1800A7268
0x1800915cb  mov     [rsp+68h+var_40], 0
0x1800915d3  mov     r9d, ebx
0x1800915d6  mov     r8, rdi
0x1800915d9  mov     [rsp+68h+var_48], 0
0x1800915e2  mov     edx, esi
0x1800915e4  mov     ecx, ebp
0x1800915e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800915eb  add     rsp, 48h
0x1800915ef  pop     rdi
0x1800915f0  pop     rsi
0x1800915f1  pop     rbp
0x1800915f2  pop     rbx
0x1800915f3  retn
```
