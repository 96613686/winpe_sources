# CSafeArray::Trim(void)

- ea: `0x180007280`
- end: `0x1800072ec`
- name: `?Trim@CSafeArray@@QEAAHXZ`
- size: `108`
- prototype: `__int64 __fastcall(CSafeArray *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008cc0`

## callees

- `0x1800056c0`
- `0x180007280`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800072d5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800072d5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800072bb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800072bb`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800072a1`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x1800072a1`

## pseudocode

```c
__int64 __fastcall CSafeArray::Trim(CSafeArray *this)
{
  SAFEARRAYBOUND *v1; // rdi
  bool v2; // zf
  int v3; // eax
  SAFEARRAY *v5; // rcx
  VARTYPE v7; // cx
  SAFEARRAY *v8; // rax

  v1 = (SAFEARRAYBOUND *)((char *)this + 24);
  v2 = *(_DWORD *)this == -1;
  v3 = *(_DWORD *)this + 1;
  v5 = (SAFEARRAY *)*((_QWORD *)this + 4);
  v1->cElements = v3;
  if ( v2 )
  {
    SafeArrayDestroy(v5);
    v7 = *((_WORD *)this + 8);
    *((_QWORD *)this + 4) = 0;
    v8 = SafeArrayCreate(v7, 1u, v1);
    if ( v8 )
    {
      *((_QWORD *)this + 4) = v8;
      return 0;
    }
LABEL_6:
    _ThrowMemoryException_();
  }
  if ( SafeArrayRedim(v5, v1) == -2147024882 )
    goto LABEL_6;
  return 0;
}

```

## disassembly

```asm
0x180007280  mov     [rsp+arg_0], rbx
0x180007285  push    rdi
0x180007286  sub     rsp, 20h
0x18000728a  mov     eax, [rcx]
0x18000728c  lea     rdi, [rcx+18h]
0x180007290  add     eax, 1
0x180007293  mov     rbx, rcx
0x180007296  mov     rcx, [rcx+20h]; psa
0x18000729a  mov     [rdi], eax
0x18000729c  jz      short loc_1800072BB
0x18000729e  mov     rdx, rdi; psaboundNew
0x1800072a1  call    cs:__imp_SafeArrayRedim
0x1800072a7  cmp     eax, 8007000Eh
0x1800072ac  jz      short loc_1800072E6
0x1800072ae  mov     rbx, [rsp+28h+arg_0]
0x1800072b3  xor     eax, eax
0x1800072b5  add     rsp, 20h
0x1800072b9  pop     rdi
0x1800072ba  retn
0x1800072bb  call    cs:__imp_SafeArrayDestroy
0x1800072c1  movzx   ecx, word ptr [rbx+10h]; vt
0x1800072c5  mov     r8, rdi; rgsabound
0x1800072c8  mov     edx, 1; cDims
0x1800072cd  mov     qword ptr [rbx+20h], 0
0x1800072d5  call    cs:__imp_SafeArrayCreate
0x1800072db  test    rax, rax
0x1800072de  jz      short loc_1800072E6
0x1800072e0  mov     [rbx+20h], rax
0x1800072e4  jmp     short loc_1800072AE
0x1800072e6  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
```
