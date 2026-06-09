# CSafeArray::CSafeArray(int,int,int,int)

- ea: `0x1800242c0`
- end: `0x180024324`
- name: `??0CSafeArray@@QEAA@HHHH@Z`
- size: `100`
- prototype: `CSafeArray *__fastcall(CSafeArray *__hidden this, int, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800050c0`
- `0x180039cf0`

## callees

- `0x1800056c0`
- `0x1800242c0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800242f3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800242f3`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002430c`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x18002430c`

## pseudocode

```c
CSafeArray *__fastcall CSafeArray::CSafeArray(CSafeArray *this, int a2, int a3, int a4, int a5)
{
  SAFEARRAY *v6; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 4) = a2;
  *((_DWORD *)this + 2) = a5;
  *(_DWORD *)this = -1;
  *((_DWORD *)this + 7) = 0;
  *((_DWORD *)this + 6) = a4;
  v6 = SafeArrayCreate(a2, 1u, (SAFEARRAYBOUND *)this + 3);
  if ( !v6 )
    _ThrowMemoryException_();
  *((_QWORD *)this + 4) = v6;
  *((_DWORD *)this + 3) = 0;
  *((_DWORD *)this + 5) = SafeArrayGetElemsize(v6);
  return this;
}

```

## disassembly

```asm
0x1800242c0  push    rbx
0x1800242c2  sub     rsp, 20h
0x1800242c6  mov     eax, [rsp+28h+arg_20]
0x1800242ca  mov     rbx, rcx
0x1800242cd  mov     [rcx+4], r8d
0x1800242d1  lea     r8, [rcx+18h]; rgsabound
0x1800242d5  mov     [rcx+10h], edx
0x1800242d8  mov     [rcx+8], eax
0x1800242db  mov     dword ptr [rcx], 0FFFFFFFFh
0x1800242e1  mov     dword ptr [rcx+1Ch], 0
0x1800242e8  movzx   ecx, dx; vt
0x1800242eb  mov     edx, 1; cDims
0x1800242f0  mov     [r8], r9d
0x1800242f3  call    cs:__imp_SafeArrayCreate
0x1800242f9  test    rax, rax
0x1800242fc  jz      short loc_18002431E
0x1800242fe  mov     [rbx+20h], rax
0x180024302  mov     rcx, rax; psa
0x180024305  mov     dword ptr [rbx+0Ch], 0
0x18002430c  call    cs:__imp_SafeArrayGetElemsize
0x180024312  mov     [rbx+14h], eax
0x180024315  mov     rax, rbx
0x180024318  add     rsp, 20h
0x18002431c  pop     rbx
0x18002431d  retn
0x18002431e  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
```
