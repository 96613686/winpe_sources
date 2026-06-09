# CTDCArr::DeleteColumns(__int64,__int64,__int64 *)

- ea: `0x18000b870`
- end: `0x18000b97f`
- name: `?DeleteColumns@CTDCArr@@UEAAJ_J0PEA_J@Z`
- size: `271`
- prototype: `__int64 __fastcall(CTDCArr *__hidden this, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b870`
- `0x18000b988`
- `0x18000cf50`
- `0x180014232`

## pseudocode

```c
__int64 __fastcall CTDCArr::DeleteColumns(CTDCArr *this, __int64 a2, __int64 a3, __int64 *a4)
{
  int v7; // eax
  unsigned int v8; // ebp
  int v9; // r15d
  __int64 v10; // r14
  int v11; // eax

  if ( (int)a2 < 1
    || (int)a2 > *((_DWORD *)this + 28)
    || a2 <= 0
    || a3 < 0
    || (v7 = a3 + a2 - 1, v7 < 1)
    || v7 > *((_DWORD *)this + 28) )
  {
    v8 = -2147024809;
    *a4 = 0;
  }
  else
  {
    v8 = 0;
    *a4 = a3;
    if ( a3 > 0 )
    {
      v9 = 0;
      if ( *((int *)this + 27) <= 0 )
      {
        v10 = a2 - 1;
      }
      else
      {
        do
        {
          v10 = a2 - 1;
          TSTDArray<CTDCCell>::DeleteElems(*(_QWORD *)(*((_QWORD *)this + 16) + 8LL * v9++), a2 - 1, a3);
        }
        while ( v9 < *((_DWORD *)this + 27) );
      }
      memmove_0(
        (void *)(*((_QWORD *)this + 22) + 8 * v10),
        (const void *)(*((_QWORD *)this + 22) + 8 * (v10 + a3)),
        8 * (*((_QWORD *)this + 23) - v10 - a3));
      *((_QWORD *)this + 23) -= a3;
      if ( *((_QWORD *)this + 17) )
        v11 = *(_DWORD *)(**((_QWORD **)this + 16) + 8LL);
      else
        v11 = 0;
      *((_DWORD *)this + 28) = v11;
      if ( !*((_BYTE *)this + 92) )
        CTDCArr::RenumberColumnHeadings(this);
      *((_BYTE *)this + 48) = 1;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000b870  push    rbx
0x18000b872  push    rbp
0x18000b873  push    rsi
0x18000b874  push    rdi
0x18000b875  push    r14
0x18000b877  push    r15
0x18000b879  sub     rsp, 28h
0x18000b87d  mov     rdi, r8
0x18000b880  mov     rsi, rdx
0x18000b883  mov     rbx, rcx
0x18000b886  cmp     edx, 1
0x18000b889  jl      loc_18000B964
0x18000b88f  cmp     esi, [rcx+70h]
0x18000b892  jg      loc_18000B964
0x18000b898  test    rdx, rdx
0x18000b89b  jle     loc_18000B964
0x18000b8a1  test    r8, r8
0x18000b8a4  js      loc_18000B964
0x18000b8aa  lea     eax, [rdx-1]
0x18000b8ad  add     eax, edi
0x18000b8af  cmp     eax, 1
0x18000b8b2  jl      loc_18000B964
0x18000b8b8  cmp     eax, [rcx+70h]
0x18000b8bb  jg      loc_18000B964
0x18000b8c1  xor     ebp, ebp
0x18000b8c3  mov     [r9], r8
0x18000b8c6  test    r8, r8
0x18000b8c9  jle     loc_18000B970
0x18000b8cf  xor     r15d, r15d
0x18000b8d2  cmp     [rcx+6Ch], ebp
0x18000b8d5  jle     short loc_18000B8FF
0x18000b8d7  mov     rcx, [rbx+80h]
0x18000b8de  lea     r14, [rsi-1]
0x18000b8e2  movsxd  rax, r15d
0x18000b8e5  mov     r8, rdi
0x18000b8e8  mov     rdx, r14
0x18000b8eb  mov     rcx, [rcx+rax*8]
0x18000b8ef  call    ?DeleteElems@?$TSTDArray@VCTDCCell@@@@QEAAX_K0@Z; TSTDArray<CTDCCell>::DeleteElems(unsigned __int64,unsigned __int64)
0x18000b8f4  inc     r15d
0x18000b8f7  cmp     r15d, [rbx+6Ch]
0x18000b8fb  jl      short loc_18000B8D7
0x18000b8fd  jmp     short loc_18000B903
0x18000b8ff  lea     r14, [rdx-1]
0x18000b903  mov     rcx, [rbx+0B0h]
0x18000b90a  lea     rax, [r14+rdi]
0x18000b90e  mov     r8, [rbx+0B8h]
0x18000b915  sub     r8, r14
0x18000b918  sub     r8, rdi
0x18000b91b  lea     rdx, [rcx+rax*8]; Src
0x18000b91f  shl     r8, 3; Size
0x18000b923  lea     rcx, [rcx+r14*8]; void *
0x18000b927  call    memmove_0
0x18000b92c  sub     [rbx+0B8h], rdi
0x18000b933  cmp     [rbx+88h], rbp
0x18000b93a  jbe     short loc_18000B94B
0x18000b93c  mov     rax, [rbx+80h]
0x18000b943  mov     rcx, [rax]
0x18000b946  mov     eax, [rcx+8]
0x18000b949  jmp     short loc_18000B94D
0x18000b94b  xor     eax, eax
0x18000b94d  mov     [rbx+70h], eax
0x18000b950  cmp     [rbx+5Ch], bpl
0x18000b954  jnz     short loc_18000B95E
0x18000b956  mov     rcx, rbx; this
0x18000b959  call    ?RenumberColumnHeadings@CTDCArr@@AEAAXXZ; CTDCArr::RenumberColumnHeadings(void)
0x18000b95e  mov     byte ptr [rbx+30h], 1
0x18000b962  jmp     short loc_18000B970
0x18000b964  mov     ebp, 80070057h
0x18000b969  mov     qword ptr [r9], 0
0x18000b970  mov     eax, ebp
0x18000b972  add     rsp, 28h
0x18000b976  pop     r15
0x18000b978  pop     r14
0x18000b97a  pop     rdi
0x18000b97b  pop     rsi
0x18000b97c  pop     rbp
0x18000b97d  pop     rbx
0x18000b97e  retn
```
