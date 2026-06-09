# CVarVector::MakeOptimized(int,int,int)

- ea: `0x180025840`
- end: `0x180025918`
- name: `?MakeOptimized@CVarVector@@QEAAHHHH@Z`
- size: `216`
- prototype: `__int64 __fastcall(CVarVector *this, ULONG, ULONG, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800056c0`
- `0x18000723c`
- `0x18000a290`
- `0x180025840`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800258ac`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800258ac`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800258c1`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800258c1`

## pseudocode

```c
__int64 __fastcall CVarVector::MakeOptimized(CVarVector *this, ULONG a2, ULONG a3, ULONG a4)
{
  unsigned int v8; // ebp
  SAFEARRAYBOUND *v9; // rax
  unsigned int v10; // edx
  SAFEARRAYBOUND *v11; // rbx
  int v12; // esi
  SAFEARRAY *v13; // rax

  v8 = 0;
  if ( !*((_QWORD *)this + 13) && !*((_DWORD *)this + 2) )
  {
    v9 = (SAFEARRAYBOUND *)CWin32DefaultArena::WbemMemAlloc(0x28u);
    v11 = v9;
    v12 = 1;
    if ( v9 )
    {
      v9->cElements = -1;
      v9->lLbound = 2;
      v9[1].cElements = a4;
      v9[2].cElements = a2;
      v9[3].cElements = a3;
      v9[3].lLbound = 0;
      v13 = SafeArrayCreate(a2, 1u, v9 + 3);
      if ( !v13 )
        _ThrowMemoryException_();
      v11[4] = (SAFEARRAYBOUND)v13;
      v11[1].lLbound = 0;
      v11[2].lLbound = SafeArrayGetElemsize(v13);
    }
    else
    {
      v11 = 0;
    }
    *((_QWORD *)this + 13) = v11;
    if ( v11 )
    {
      if ( v11[1].lLbound )
      {
        CSafeArray::`scalar deleting destructor'((CSafeArray *)v11, v10);
        *((_QWORD *)this + 13) = 0;
      }
      else
      {
        *(_DWORD *)this = a2;
        v8 = 1;
        v12 = 0;
      }
    }
    *((_DWORD *)this + 24) = v12;
  }
  return v8;
}

```

## disassembly

```asm
0x180025840  mov     [rsp+arg_8], rbx
0x180025845  mov     [rsp+arg_10], rbp
0x18002584a  push    rsi
0x18002584b  push    rdi
0x18002584c  push    r12
0x18002584e  push    r14
0x180025850  push    r15
0x180025852  sub     rsp, 20h
0x180025856  mov     r15d, r9d
0x180025859  mov     r12d, r8d
0x18002585c  mov     r14d, edx
0x18002585f  mov     rdi, rcx
0x180025862  xor     ebp, ebp
0x180025864  cmp     [rcx+68h], rbp
0x180025868  jnz     short loc_1800258E3
0x18002586a  cmp     [rcx+8], ebp
0x18002586d  jnz     short loc_1800258E3
0x18002586f  lea     ecx, [rbp+28h]; unsigned __int64
0x180025872  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180025877  mov     rbx, rax
0x18002587a  mov     [rsp+48h+arg_0], rax
0x18002587f  lea     esi, [rbp+1]
0x180025882  test    rax, rax
0x180025885  jz      short loc_180025902
0x180025887  mov     dword ptr [rax], 0FFFFFFFFh
0x18002588d  mov     dword ptr [rax+4], 2
0x180025894  mov     [rax+8], r15d
0x180025898  mov     [rax+10h], r14d
0x18002589c  lea     r8, [rax+18h]; rgsabound
0x1800258a0  mov     [r8], r12d
0x1800258a3  mov     [rax+1Ch], ebp
0x1800258a6  movzx   ecx, r14w; vt
0x1800258aa  mov     edx, esi; cDims
0x1800258ac  call    cs:__imp_SafeArrayCreate
0x1800258b2  test    rax, rax
0x1800258b5  jz      short loc_1800258FC
0x1800258b7  mov     [rbx+20h], rax
0x1800258bb  mov     [rbx+0Ch], ebp
0x1800258be  mov     rcx, rax; psa
0x1800258c1  call    cs:__imp_SafeArrayGetElemsize
0x1800258c7  mov     [rbx+14h], eax
0x1800258ca  mov     [rdi+68h], rbx
0x1800258ce  test    rbx, rbx
0x1800258d1  jz      short loc_1800258E0
0x1800258d3  cmp     dword ptr [rbx+0Ch], 0
0x1800258d7  jnz     short loc_180025906
0x1800258d9  mov     [rdi], r14d
0x1800258dc  mov     ebp, esi
0x1800258de  xor     esi, esi
0x1800258e0  mov     [rdi+60h], esi
0x1800258e3  mov     eax, ebp
0x1800258e5  mov     rbx, [rsp+48h+arg_8]
0x1800258ea  mov     rbp, [rsp+48h+arg_10]
0x1800258ef  add     rsp, 20h
0x1800258f3  pop     r15
0x1800258f5  pop     r14
0x1800258f7  pop     r12
0x1800258f9  pop     rdi
0x1800258fa  pop     rsi
0x1800258fb  retn
0x1800258fc  call    ?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x180025902  xor     ebx, ebx
0x180025904  jmp     short loc_1800258CA
0x180025906  mov     rcx, rbx; this
0x180025909  call    ??_GCSafeArray@@QEAAPEAXI@Z; CSafeArray::`scalar deleting destructor'(uint)
0x18002590e  mov     qword ptr [rdi+68h], 0
0x180025916  jmp     short loc_1800258E0
```
