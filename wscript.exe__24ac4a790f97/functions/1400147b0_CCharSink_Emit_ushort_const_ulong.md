# CCharSink::Emit(ushort const *,ulong)

- ea: `0x1400147b0`
- end: `0x1400148be`
- name: `?Emit@CCharSink@@QEAAJPEBGK@Z`
- size: `270`
- prototype: `int(CCharSink *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400057f0`
- `0x14000d190`
- `0x14000f540`
- `0x140011e90`

## callees

- `0x1400147b0`
- `0x140017542`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14001483e`
- `KERNEL32!GetProcessHeap` at `0x14001483e`
- `KERNEL32!HeapReAlloc` at `0x14001484f`
- `KERNEL32!HeapReAlloc` at `0x14001484f`

## pseudocode

```c
__int64 __fastcall CCharSink::Emit(CCharSink *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned __int64 v5; // rbp
  unsigned int v7; // esi
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned __int64 v10; // rdx
  unsigned int v11; // eax
  SIZE_T v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v15; // rax

  v3 = *((_DWORD *)this + 2);
  v5 = a3;
  v7 = v3 + a3;
  if ( v3 + a3 < v3 || v7 + 1 < v7 )
    return 2147942934LL;
  v8 = *((_DWORD *)this + 3);
  if ( v7 + 1 >= v8 )
  {
    v9 = v8 + a3;
    if ( v8 + a3 < v8 )
      return 2147942934LL;
    v10 = 50LL * v9;
    *((_DWORD *)this + 3) = v9;
    if ( v10 > 0xFFFFFFFF )
      return 2147942934LL;
    v11 = (unsigned int)v10 / 0x64 + v9;
    if ( v11 < v9 )
      return 2147942934LL;
    *((_DWORD *)this + 3) = v11;
    v12 = 2LL * v11;
    if ( !is_mul_ok(v11, 2u) )
      return 2147942934LL;
    v13 = *(void **)this;
    ProcessHeap = GetProcessHeap();
    v15 = HeapReAlloc(ProcessHeap, 0, v13, v12);
    if ( !v15 )
      return 2147942414LL;
    *(_QWORD *)this = v15;
  }
  if ( !*(_QWORD *)this )
    return 0;
  if ( !(_DWORD)v5 )
  {
LABEL_15:
    *(_WORD *)(*(_QWORD *)this + 2LL * *((unsigned int *)this + 2)) = 0;
    return 0;
  }
  if ( is_mul_ok(v5, 2u) )
  {
    memcpy_0((void *)(*(_QWORD *)this + 2LL * *((unsigned int *)this + 2)), a2, 2 * v5);
    *((_DWORD *)this + 2) = v7;
    goto LABEL_15;
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x1400147b0  push    rbx
0x1400147b2  push    rbp
0x1400147b3  push    rsi
0x1400147b4  push    rdi
0x1400147b5  push    r14
0x1400147b7  push    r15
0x1400147b9  sub     rsp, 28h
0x1400147bd  mov     eax, [rcx+8]
0x1400147c0  mov     r15, rdx
0x1400147c3  mov     ebp, r8d
0x1400147c6  mov     rdi, rcx
0x1400147c9  lea     esi, [rax+rbp]
0x1400147cc  cmp     esi, eax
0x1400147ce  jb      loc_1400148AC
0x1400147d4  lea     ecx, [rsi+1]
0x1400147d7  cmp     ecx, esi
0x1400147d9  jb      loc_1400148AC
0x1400147df  mov     eax, [rdi+0Ch]
0x1400147e2  cmp     ecx, eax
0x1400147e4  jb      short loc_140014864
0x1400147e6  lea     ecx, [rax+rbp]
0x1400147e9  cmp     ecx, eax
0x1400147eb  jb      loc_1400148AC
0x1400147f1  mov     eax, ecx
0x1400147f3  imul    rdx, rax, 32h ; '2'
0x1400147f7  mov     eax, 0FFFFFFFFh
0x1400147fc  mov     [rdi+0Ch], ecx
0x1400147ff  cmp     rdx, rax
0x140014802  ja      loc_1400148AC
0x140014808  mov     eax, 51EB851Fh
0x14001480d  mul     edx
0x14001480f  shr     edx, 5
0x140014812  lea     eax, [rdx+rcx]
0x140014815  cmp     eax, ecx
0x140014817  jb      loc_1400148AC
0x14001481d  mov     [rdi+0Ch], eax
0x140014820  mov     ecx, eax
0x140014822  mov     eax, 2
0x140014827  mul     rcx
0x14001482a  mov     [rsp+58h+arg_0], 0
0x140014833  mov     r14, rax
0x140014836  test    rdx, rdx
0x140014839  jnz     short loc_1400148AC
0x14001483b  mov     rbx, [rdi]
0x14001483e  call    cs:__imp_GetProcessHeap
0x140014844  mov     r9, r14; dwBytes
0x140014847  mov     r8, rbx; lpMem
0x14001484a  mov     rcx, rax; hHeap
0x14001484d  xor     edx, edx; dwFlags
0x14001484f  call    cs:__imp_HeapReAlloc
0x140014855  test    rax, rax
0x140014858  jnz     short loc_140014861
0x14001485a  mov     eax, 8007000Eh
0x14001485f  jmp     short loc_1400148B1
0x140014861  mov     [rdi], rax
0x140014864  mov     r9, [rdi]
0x140014867  test    r9, r9
0x14001486a  jz      short loc_1400148A8
0x14001486c  cmp     ebp, 1
0x14001486f  jb      short loc_14001489C
0x140014871  mov     eax, 2
0x140014876  mov     [rsp+58h+arg_0], 0
0x14001487f  mul     rbp
0x140014882  mov     r8, rax; Size
0x140014885  test    rdx, rdx
0x140014888  jnz     short loc_1400148AC
0x14001488a  mov     eax, [rdi+8]
0x14001488d  mov     rdx, r15; Src
0x140014890  lea     rcx, [r9+rax*2]; void *
0x140014894  call    memcpy_0
0x140014899  mov     [rdi+8], esi
0x14001489c  mov     edx, [rdi+8]
0x14001489f  xor     eax, eax
0x1400148a1  mov     rcx, [rdi]
0x1400148a4  mov     [rcx+rdx*2], ax
0x1400148a8  xor     eax, eax
0x1400148aa  jmp     short loc_1400148B1
0x1400148ac  mov     eax, 80070216h
0x1400148b1  add     rsp, 28h
0x1400148b5  pop     r15
0x1400148b7  pop     r14
0x1400148b9  pop     rdi
0x1400148ba  pop     rsi
0x1400148bb  pop     rbp
0x1400148bc  pop     rbx
0x1400148bd  retn
```
