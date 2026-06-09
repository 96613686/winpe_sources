# CLogManager::CreateConversionBuffers(uint)

- ea: `0x18001e9d0`
- end: `0x18001ea98`
- name: `?CreateConversionBuffers@CLogManager@@IEAAHI@Z`
- size: `200`
- prototype: `int(CLogManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f020`

## callees

- `0x180001144`
- `0x180001b84`
- `0x18001e9d0`
- `0x18001eaa0`
- `0x180023350`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLogManager::CreateConversionBuffers(CLogManager *this, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  __int64 v4; // rax
  bool v5; // cf
  size_t v6; // rax
  unsigned __int64 *v7; // rax
  _QWORD *v8; // rsi
  unsigned int i; // esi

  v2 = a2;
  if ( !a2 )
    return 0;
  if ( *((_QWORD *)this + 9) )
    CLogManager::DestroyConversionBuffers(this);
  v4 = 16 * v2;
  if ( !is_mul_ok(v2, 0x10u) )
    v4 = -1;
  v5 = __CFADD__(v4, 8);
  v6 = v4 + 8;
  if ( v5 )
    v6 = -1;
  v7 = (unsigned __int64 *)operator new(v6);
  if ( v7 )
  {
    *v7 = v2;
    v8 = v7 + 1;
    `eh vector constructor iterator'(
      v7 + 1,
      0x10u,
      v2,
      (void (*)(void *))CBuffer::CBuffer,
      (void (*)(void *))CBuffer::~CBuffer);
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 9) = v8;
  if ( !v8 )
    return 0;
  *((_DWORD *)this + 20) = v2;
  for ( i = 0; i < (unsigned int)v2; ++i )
    CBuffer::PreAllocate((CBuffer *)(*((_QWORD *)this + 9) + 16LL * i), 0x400u);
  return 1;
}

```

## disassembly

```asm
0x18001e9d0  push    rbx
0x18001e9d2  push    rbp
0x18001e9d3  push    rsi
0x18001e9d4  push    rdi
0x18001e9d5  sub     rsp, 48h
0x18001e9d9  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18001e9e2  mov     edi, edx
0x18001e9e4  mov     rbx, rcx
0x18001e9e7  test    edx, edx
0x18001e9e9  jz      loc_18001EA8C
0x18001e9ef  cmp     qword ptr [rcx+48h], 0
0x18001e9f4  jz      short loc_18001E9FB
0x18001e9f6  call    ?DestroyConversionBuffers@CLogManager@@IEAAXXZ; CLogManager::DestroyConversionBuffers(void)
0x18001e9fb  mov     eax, 10h
0x18001ea00  mul     rdi
0x18001ea03  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ea0a  cmovb   rax, rcx
0x18001ea0e  add     rax, 8
0x18001ea12  cmovb   rax, rcx
0x18001ea16  mov     rcx, rax; Size
0x18001ea19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ea1e  mov     [rsp+68h+arg_10], rax
0x18001ea26  test    rax, rax
0x18001ea29  jz      short loc_18001EA57
0x18001ea2b  mov     [rax], rdi
0x18001ea2e  lea     rsi, [rax+8]
0x18001ea32  lea     rax, ??1CBuffer@@QEAA@XZ; CBuffer::~CBuffer(void)
0x18001ea39  mov     [rsp+68h+var_48], rax; void (*)(void *)
0x18001ea3e  lea     r9, ??0CBuffer@@QEAA@XZ; void (*)(void *)
0x18001ea45  mov     r8, rdi; unsigned __int64
0x18001ea48  mov     edx, 10h; unsigned __int64
0x18001ea4d  mov     rcx, rsi; void *
0x18001ea50  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001ea55  jmp     short loc_18001EA59
0x18001ea57  xor     esi, esi
0x18001ea59  mov     [rbx+48h], rsi
0x18001ea5d  test    rsi, rsi
0x18001ea60  jz      short loc_18001EA8C
0x18001ea62  mov     [rbx+50h], edi
0x18001ea65  xor     esi, esi
0x18001ea67  test    edi, edi
0x18001ea69  jz      short loc_18001EA85
0x18001ea6b  mov     ecx, esi
0x18001ea6d  shl     rcx, 4
0x18001ea71  add     rcx, [rbx+48h]; this
0x18001ea75  mov     edx, 400h; unsigned int
0x18001ea7a  call    ?PreAllocate@CBuffer@@QEAAHI@Z; CBuffer::PreAllocate(uint)
0x18001ea7f  inc     esi
0x18001ea81  cmp     esi, edi
0x18001ea83  jb      short loc_18001EA6B
0x18001ea85  mov     eax, 1
0x18001ea8a  jmp     short loc_18001EA8E
0x18001ea8c  xor     eax, eax
0x18001ea8e  add     rsp, 48h
0x18001ea92  pop     rdi
0x18001ea93  pop     rsi
0x18001ea94  pop     rbp
0x18001ea95  pop     rbx
0x18001ea96  retn
```
