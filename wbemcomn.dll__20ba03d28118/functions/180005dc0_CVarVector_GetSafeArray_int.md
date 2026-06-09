# CVarVector::GetSafeArray(int)

- ea: `0x180005dc0`
- end: `0x180005e2b`
- name: `?GetSafeArray@CVarVector@@QEAAPEAUtagSAFEARRAY@@H@Z`
- size: `107`
- prototype: `struct tagSAFEARRAY *__fastcall(CVarVector *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005dc0`
- `0x18000723c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005e19`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005e19`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall CVarVector::GetSafeArray(CVarVector *this, unsigned int a2)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v5; // rax
  CSafeArray *v6; // rcx

  v2 = *((_QWORD *)this + 13);
  v3 = 0;
  if ( v2 )
  {
    if ( a2 )
    {
      if ( *((_QWORD *)this + 14) )
      {
        SafeArrayUnaccessData(*(SAFEARRAY **)(v2 + 32));
        *((_QWORD *)this + 14) = 0;
      }
      v5 = *((_QWORD *)this + 13);
      v3 = *(_QWORD *)(v5 + 32);
      *(_DWORD *)(v5 + 4) = 1;
      v6 = (CSafeArray *)*((_QWORD *)this + 13);
      if ( v6 )
        CSafeArray::`scalar deleting destructor'(v6, a2);
      *((_QWORD *)this + 13) = 0;
    }
    else
    {
      return *(struct tagSAFEARRAY **)(v2 + 32);
    }
  }
  return (struct tagSAFEARRAY *)v3;
}

```

## disassembly

```asm
0x180005dc0  mov     [rsp+arg_0], rbx
0x180005dc5  push    rdi
0x180005dc6  sub     rsp, 20h
0x180005dca  mov     rax, [rcx+68h]
0x180005dce  xor     edi, edi
0x180005dd0  mov     rbx, rcx
0x180005dd3  test    rax, rax
0x180005dd6  jz      short loc_180005E07
0x180005dd8  test    edx, edx
0x180005dda  jz      short loc_180005E25
0x180005ddc  cmp     [rcx+70h], rdi
0x180005de0  jnz     short loc_180005E15
0x180005de2  mov     rax, [rbx+68h]
0x180005de6  mov     rdi, [rax+20h]
0x180005dea  mov     dword ptr [rax+4], 1
0x180005df1  mov     rcx, [rbx+68h]; this
0x180005df5  test    rcx, rcx
0x180005df8  jz      short loc_180005DFF
0x180005dfa  call    ??_GCSafeArray@@QEAAPEAXI@Z; CSafeArray::`scalar deleting destructor'(uint)
0x180005dff  mov     qword ptr [rbx+68h], 0
0x180005e07  mov     rbx, [rsp+28h+arg_0]
0x180005e0c  mov     rax, rdi
0x180005e0f  add     rsp, 20h
0x180005e13  pop     rdi
0x180005e14  retn
0x180005e15  mov     rcx, [rax+20h]; psa
0x180005e19  call    cs:__imp_SafeArrayUnaccessData
0x180005e1f  mov     [rbx+70h], rdi
0x180005e23  jmp     short loc_180005DE2
0x180005e25  mov     rdi, [rax+20h]
0x180005e29  jmp     short loc_180005E07
```
