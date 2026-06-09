# CThumbnailMoniker::Initialize(unsigned __int64,ushort const *,int,TRIBIT,ulong)

- ea: `0x180014888`
- end: `0x180014a32`
- name: `?Initialize@CThumbnailMoniker@@QEAAJ_KPEBGHW4TRIBIT@@K@Z`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013870`
- `0x180015390`
- `0x180040cd0`
- `0x1800415a0`

## callees

- `0x180014888`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800148f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014906`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014954`

## pseudocode

```c
__int64 __fastcall CThumbnailMoniker::Initialize(__int64 a1, __int64 a2, _WORD *a3, __int64 a4, int a5, int a6)
{
  _WORD *v6; // r15
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rsi
  signed int v11; // edi
  _WORD *v12; // rbx
  void *v13; // rcx
  void *v14; // rcx
  unsigned __int64 v16; // rdx
  _WORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r9
  _WORD *v20; // rcx
  __int64 v21; // rsi
  bool v22; // cf

  v6 = a3;
  if ( !a3 )
  {
    v11 = 0;
    v12 = 0;
    goto LABEL_8;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = v9 + 1;
  if ( v9 + 1 < v9 || !is_mul_ok(v10, 2u) )
  {
    v11 = -2147024362;
    v12 = 0;
    goto LABEL_7;
  }
  v12 = CoTaskMemAlloc(2 * v10);
  v11 = v12 == 0 ? 0x8007000E : 0;
  if ( v12 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      if ( v9 < 0x7FFFFFFF )
      {
        v16 = v9 + 1;
        v17 = v12;
        v18 = 0;
        do
        {
          if ( !v9 )
            break;
          if ( !*v6 )
            break;
          *v17++ = *v6++;
          --v9;
          ++v18;
          --v16;
        }
        while ( v16 );
        v19 = v18 - 1;
        if ( v16 )
          v19 = v18;
        v20 = v17 - 1;
        if ( v16 )
          v20 = v17;
        *v20 = 0;
        if ( v16 )
        {
          v22 = v10 == v19;
          v21 = v10 - v19;
          if ( !v22 && v21 != 1 && (unsigned __int64)(2 * v21) > 2 )
            memset_0(&v12[v19 + 1], 0, 2 * v21 - 2);
        }
        goto LABEL_7;
      }
      if ( v9 == -1 )
        goto LABEL_7;
    }
    *v12 = 0;
  }
LABEL_7:
  if ( v11 >= 0 )
  {
LABEL_8:
    v13 = *(void **)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    CoTaskMemFree(v13);
    v14 = *(void **)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    CoTaskMemFree(v14);
    *(_QWORD *)(a1 + 16) = v12;
    *(_DWORD *)(a1 + 28) = a5;
    *(_DWORD *)(a1 + 12) = a6;
    *(_QWORD *)a1 = a2;
    *(_DWORD *)(a1 + 8) = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014888  mov     [rsp+arg_8], rbx
0x18001488d  push    rbp
0x18001488e  push    rsi
0x18001488f  push    rdi
0x180014890  push    r12
0x180014892  push    r13
0x180014894  push    r14
0x180014896  push    r15
0x180014898  sub     rsp, 30h
0x18001489c  mov     rax, cs:__security_cookie
0x1800148a3  xor     rax, rsp
0x1800148a6  mov     [rsp+68h+var_40], rax
0x1800148ab  xor     r13d, r13d
0x1800148ae  mov     r15, r8
0x1800148b1  mov     r12, rdx
0x1800148b4  mov     r14, rcx
0x1800148b7  test    r8, r8
0x1800148ba  jz      loc_180014A15
0x1800148c0  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800148c4  inc     rbp
0x1800148c7  cmp     [r8+rbp*2], r13w
0x1800148cc  jnz     short loc_1800148C4
0x1800148ce  lea     rsi, [rbp+1]
0x1800148d2  cmp     rsi, rbp
0x1800148d5  jb      short loc_1800148E4
0x1800148d7  mov     eax, 2
0x1800148dc  mul     rsi
0x1800148df  test    rdx, rdx
0x1800148e2  jz      short loc_180014951
0x1800148e4  mov     edi, 80070216h
0x1800148e9  mov     rbx, r13
0x1800148ec  test    edi, edi
0x1800148ee  js      short loc_18001492D
0x1800148f0  mov     rcx, [r14+10h]; pv
0x1800148f4  mov     [r14+10h], r13
0x1800148f8  call    cs:__imp_CoTaskMemFree
0x1800148fe  mov     rcx, [r14+10h]; pv
0x180014902  mov     [r14+10h], r13
0x180014906  call    cs:__imp_CoTaskMemFree
0x18001490c  mov     ecx, [rsp+68h+arg_20]
0x180014913  mov     [r14+10h], rbx
0x180014917  mov     [r14+1Ch], ecx
0x18001491b  mov     ecx, [rsp+68h+arg_28]
0x180014922  mov     [r14+0Ch], ecx
0x180014926  mov     [r14], r12
0x180014929  mov     [r14+8], r13d
0x18001492d  mov     eax, edi
0x18001492f  mov     rcx, [rsp+68h+var_40]
0x180014934  xor     rcx, rsp; StackCookie
0x180014937  call    __security_check_cookie
0x18001493c  mov     rbx, [rsp+68h+arg_8]
0x180014941  add     rsp, 30h
0x180014945  pop     r15
0x180014947  pop     r14
0x180014949  pop     r13
0x18001494b  pop     r12
0x18001494d  pop     rdi
0x18001494e  pop     rsi
0x18001494f  pop     rbp
0x180014950  retn
0x180014951  mov     rcx, rax; cb
0x180014954  call    cs:__imp_CoTaskMemAlloc
0x18001495a  mov     rcx, rax
0x18001495d  mov     rbx, rax
0x180014960  neg     rcx
0x180014963  sbb     edi, edi
0x180014965  not     edi
0x180014967  and     edi, 8007000Eh
0x18001496d  test    rax, rax
0x180014970  jz      loc_1800148EC
0x180014976  mov     eax, 7FFFFFFFh
0x18001497b  cmp     rsi, rax
0x18001497e  ja      loc_180014A29
0x180014984  cmp     rbp, rax
0x180014987  jnb     loc_180014A20
0x18001498d  test    rsi, rsi
0x180014990  jz      loc_1800148EC
0x180014996  mov     rdx, rsi
0x180014999  mov     rax, rbx
0x18001499c  mov     rcx, r13
0x18001499f  test    rbp, rbp
0x1800149a2  jz      short loc_1800149C6
0x1800149a4  movzx   r8d, word ptr [r15]
0x1800149a8  test    r8w, r8w
0x1800149ac  jz      short loc_1800149C6
0x1800149ae  mov     [rax], r8w
0x1800149b2  add     r15, 2
0x1800149b6  add     rax, 2
0x1800149ba  dec     rbp
0x1800149bd  inc     rcx
0x1800149c0  sub     rdx, 1
0x1800149c4  jnz     short loc_18001499F
0x1800149c6  lea     r9, [rcx-1]
0x1800149ca  test    rdx, rdx
0x1800149cd  cmovnz  r9, rcx
0x1800149d1  lea     rcx, [rax-2]
0x1800149d5  cmovnz  rcx, rax
0x1800149d9  mov     [rcx], r13w
0x1800149dd  jz      loc_1800148EC
0x1800149e3  sub     rsi, r9
0x1800149e6  cmp     rsi, 1
0x1800149ea  jbe     loc_1800148EC
0x1800149f0  lea     r8, [rsi+rsi]
0x1800149f4  cmp     r8, 2
0x1800149f8  jbe     loc_1800148EC
0x1800149fe  inc     r9
0x180014a01  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180014a05  xor     edx, edx; Val
0x180014a07  lea     rcx, [rbx+r9*2]; void *
0x180014a0b  call    memset_0
0x180014a10  jmp     loc_1800148EC
0x180014a15  mov     edi, r13d
0x180014a18  mov     rbx, r13
0x180014a1b  jmp     loc_1800148F0
0x180014a20  test    rsi, rsi
0x180014a23  jz      loc_1800148EC
0x180014a29  mov     [rbx], r13w
0x180014a2d  jmp     loc_1800148EC
```
