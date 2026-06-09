# CVssDiffAreaAllocator::~CVssDiffAreaAllocator(void)

- ea: `0x18001f1b4`
- end: `0x18001f320`
- name: `??1CVssDiffAreaAllocator@@QEAA@XZ`
- size: `364`
- prototype: `void __fastcall(CVssDiffAreaAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ffe0`
- `0x180043bfc`

## callees

- `0x18000212c`
- `0x18001f1b4`
- `0x18001f378`
- `0x18001f3a4`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2e6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f2fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f26e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f26e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssDiffAreaAllocator::~CVssDiffAreaAllocator(CVssDiffAreaAllocator *this)
{
  unsigned int v2; // edx
  unsigned int v3; // ebx
  CVssDiffAreaAssociation *v4; // rcx
  unsigned int i; // r14d
  __int64 v6; // rbx
  __int64 v7; // rdi
  unsigned int j; // ebx
  CVssDiffAreaCandidate *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  _QWORD v14[3]; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h]
  int v16; // [rsp+3Ch] [rbp-C4h]
  int v17; // [rsp+40h] [rbp-C0h]
  _BYTE v18[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+C0h] [rbp-40h]
  _BYTE v20[136]; // [rsp+C8h] [rbp-38h] BYREF

  v15 = 187;
  v16 = 2;
  v14[0] = L"base\\stor\\vss\\modules\\softprv\\src\\alloc.cxx";
  v14[1] = L"CVssDiffAreaAllocator::~CVssDiffAreaAllocator";
  v17 = 255;
  v14[2] = L"SPRALLOC";
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CVssFunctionTracer::CVssFunctionTracer(
    (__int64)v20,
    (__int64)v14,
    (__int64)L"CVssDiffAreaAllocator::~CVssDiffAreaAllocator");
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v20);
  v3 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    do
    {
      v4 = *(CVssDiffAreaAssociation **)(*((_QWORD *)this + 4) + 8LL * (int)v3);
      if ( v4 )
        CVssDiffAreaAssociation::`scalar deleting destructor'(v4, v2);
      ++v3;
    }
    while ( v3 < *((_DWORD *)this + 10) );
    for ( i = 0; i < *((_DWORD *)this + 10); *(_QWORD *)(v6 + 8 * v7) = 0 )
    {
      v6 = *((_QWORD *)this + 3);
      v7 = (int)i;
      CoTaskMemFree(*(LPVOID *)(v6 + 8LL * (int)i++));
    }
  }
  for ( j = 0; j < *((_DWORD *)this + 16); ++j )
  {
    v9 = *(CVssDiffAreaCandidate **)(*((_QWORD *)this + 7) + 8LL * (int)j);
    if ( v9 )
      CVssDiffAreaCandidate::`scalar deleting destructor'(v9, v2);
  }
  v10 = (void *)*((_QWORD *)this + 6);
  if ( v10 )
  {
    free(v10);
    *((_QWORD *)this + 6) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 7);
  if ( v11 )
  {
    free(v11);
    *((_QWORD *)this + 7) = 0;
  }
  *((_DWORD *)this + 16) = 0;
  v12 = (void *)*((_QWORD *)this + 3);
  if ( v12 )
  {
    free(v12);
    *((_QWORD *)this + 3) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 4);
  if ( v13 )
  {
    free(v13);
    *((_QWORD *)this + 4) = 0;
  }
  *((_DWORD *)this + 10) = 0;
}

```

## disassembly

```asm
0x18001f1b4  push    rbp
0x18001f1b6  push    rbx
0x18001f1b7  push    rsi
0x18001f1b8  push    rdi
0x18001f1b9  push    r14
0x18001f1bb  lea     rbp, [rsp-30h]
0x18001f1c0  sub     rsp, 130h
0x18001f1c7  xor     edx, edx; Val
0x18001f1c9  mov     [rsp+150h+var_118], 0BBh
0x18001f1d1  lea     rax, aBaseStorVssMod_11; "base\\stor\\vss\\modules\\softprv\\src"...
0x18001f1d8  mov     [rsp+150h+var_114], 2
0x18001f1e0  mov     [rsp+150h+var_130], rax
0x18001f1e5  lea     rbx, aCvssdiffareaal; "CVssDiffAreaAllocator::~CVssDiffAreaAll"...
0x18001f1ec  mov     rsi, rcx
0x18001f1ef  mov     [rsp+150h+var_128], rbx
0x18001f1f4  lea     rax, aSpralloc; "SPRALLOC"
0x18001f1fb  mov     [rsp+150h+var_110], 0FFh
0x18001f203  lea     r8d, [rdx+78h]; Size
0x18001f207  mov     [rsp+150h+var_120], rax
0x18001f20c  lea     rcx, [rsp+150h+var_108]; void *
0x18001f211  mov     [rbp+50h+var_90], 1000000h
0x18001f218  call    memset_0
0x18001f21d  mov     r8, rbx
0x18001f220  lea     rdx, [rsp+150h+var_130]
0x18001f225  lea     rcx, [rbp+50h+var_88]
0x18001f229  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18001f22e  lea     rcx, [rbp+50h+var_88]; this
0x18001f232  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18001f237  xor     ebx, ebx
0x18001f239  cmp     [rsi+28h], ebx
0x18001f23c  jbe     short loc_18001F285
0x18001f23e  mov     rax, [rsi+20h]
0x18001f242  movsxd  rcx, ebx
0x18001f245  mov     rcx, [rax+rcx*8]; this
0x18001f249  test    rcx, rcx
0x18001f24c  jz      short loc_18001F253
0x18001f24e  call    ??_GCVssDiffAreaAssociation@@QEAAPEAXI@Z; CVssDiffAreaAssociation::`scalar deleting destructor'(uint)
0x18001f253  inc     ebx
0x18001f255  cmp     ebx, [rsi+28h]
0x18001f258  jb      short loc_18001F23E
0x18001f25a  xor     r14d, r14d
0x18001f25d  cmp     [rsi+28h], r14d
0x18001f261  jbe     short loc_18001F285
0x18001f263  mov     rbx, [rsi+18h]
0x18001f267  movsxd  rdi, r14d
0x18001f26a  mov     rcx, [rbx+rdi*8]; pv
0x18001f26e  call    cs:__imp_CoTaskMemFree
0x18001f274  inc     r14d
0x18001f277  mov     qword ptr [rbx+rdi*8], 0
0x18001f27f  cmp     r14d, [rsi+28h]
0x18001f283  jb      short loc_18001F263
0x18001f285  xor     ebx, ebx
0x18001f287  cmp     [rsi+40h], ebx
0x18001f28a  jbe     short loc_18001F2A8
0x18001f28c  mov     rax, [rsi+38h]
0x18001f290  movsxd  rcx, ebx
0x18001f293  mov     rcx, [rax+rcx*8]; this
0x18001f297  test    rcx, rcx
0x18001f29a  jz      short loc_18001F2A1
0x18001f29c  call    ??_GCVssDiffAreaCandidate@@QEAAPEAXI@Z; CVssDiffAreaCandidate::`scalar deleting destructor'(uint)
0x18001f2a1  inc     ebx
0x18001f2a3  cmp     ebx, [rsi+40h]
0x18001f2a6  jb      short loc_18001F28C
0x18001f2a8  mov     rcx, [rsi+30h]; Block
0x18001f2ac  test    rcx, rcx
0x18001f2af  jz      short loc_18001F2BF
0x18001f2b1  call    cs:__imp_free
0x18001f2b7  mov     qword ptr [rsi+30h], 0
0x18001f2bf  mov     rcx, [rsi+38h]; Block
0x18001f2c3  test    rcx, rcx
0x18001f2c6  jz      short loc_18001F2D6
0x18001f2c8  call    cs:__imp_free
0x18001f2ce  mov     qword ptr [rsi+38h], 0
0x18001f2d6  mov     dword ptr [rsi+40h], 0
0x18001f2dd  mov     rcx, [rsi+18h]; Block
0x18001f2e1  test    rcx, rcx
0x18001f2e4  jz      short loc_18001F2F4
0x18001f2e6  call    cs:__imp_free
0x18001f2ec  mov     qword ptr [rsi+18h], 0
0x18001f2f4  mov     rcx, [rsi+20h]; Block
0x18001f2f8  test    rcx, rcx
0x18001f2fb  jz      short loc_18001F30B
0x18001f2fd  call    cs:__imp_free
0x18001f303  mov     qword ptr [rsi+20h], 0
0x18001f30b  mov     dword ptr [rsi+28h], 0
0x18001f312  add     rsp, 130h
0x18001f319  pop     r14
0x18001f31b  pop     rdi
0x18001f31c  pop     rsi
0x18001f31d  pop     rbx
0x18001f31e  pop     rbp
0x18001f31f  retn
```
