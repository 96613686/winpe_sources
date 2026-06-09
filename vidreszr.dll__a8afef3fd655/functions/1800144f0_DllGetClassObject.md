# DllGetClassObject

- ea: `0x1800144f0`
- end: `0x1800145e4`
- name: `DllGetClassObject`
- size: `244`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001974`
- `0x1800144f0`
- `0x1800158f9`
- `0x180016010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  const void **v8; // rsi
  _QWORD *v9; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  if ( memcmp_0(riid, &IID_IUnknown, 0x10u) && memcmp_0(riid, &IID_IClassFactory, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = (const void **)(&g_ComClassTemplates + 2 * v7);
    if ( !memcmp_0(*v8, rclsid, 0x10u) )
      break;
    if ( ++v7 >= 1 )
      return -2147221231;
  }
  v9 = operator new(0x18u);
  if ( v9 )
  {
    _InterlockedIncrement(&g_cActiveObjects);
    v9[1] = v8;
    *v9 = &CClassFactory::`vftable';
    *((_DWORD *)v9 + 4) = 0;
    *ppv = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x1800144f0  push    rbx
0x1800144f2  push    rbp
0x1800144f3  push    rsi
0x1800144f4  push    rdi
0x1800144f5  push    r15
0x1800144f7  sub     rsp, 20h
0x1800144fb  mov     rdi, r8
0x1800144fe  mov     rbx, rdx
0x180014501  mov     rbp, rcx
0x180014504  test    r8, r8
0x180014507  jnz     short loc_180014513
0x180014509  mov     eax, 80004003h
0x18001450e  jmp     loc_1800145D9
0x180014513  mov     qword ptr [r8], 0
0x18001451a  lea     rdx, IID_IUnknown; Buf2
0x180014521  mov     r15d, 10h
0x180014527  mov     rcx, rbx; Buf1
0x18001452a  mov     r8d, r15d; Size
0x18001452d  call    memcmp_0
0x180014532  test    eax, eax
0x180014534  jz      short loc_180014556
0x180014536  mov     r8d, r15d; Size
0x180014539  lea     rdx, IID_IClassFactory; Buf2
0x180014540  mov     rcx, rbx; Buf1
0x180014543  call    memcmp_0
0x180014548  test    eax, eax
0x18001454a  jz      short loc_180014556
0x18001454c  mov     eax, 80004002h
0x180014551  jmp     loc_1800145D9
0x180014556  xor     ebx, ebx
0x180014558  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18001455f  movsxd  rsi, ebx
0x180014562  shl     rsi, 4
0x180014566  mov     r8, r15; Size
0x180014569  add     rsi, rcx
0x18001456c  mov     rdx, rbp; Buf2
0x18001456f  mov     rcx, [rsi]; Buf1
0x180014572  call    memcmp_0
0x180014577  test    eax, eax
0x180014579  jz      short loc_180014589
0x18001457b  inc     ebx
0x18001457d  cmp     ebx, 1
0x180014580  jl      short loc_180014558
0x180014582  mov     eax, 80040111h
0x180014587  jmp     short loc_1800145D9
0x180014589  mov     ecx, 18h; Size
0x18001458e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014593  mov     rdx, rax
0x180014596  test    rax, rax
0x180014599  jz      short loc_1800145CD
0x18001459b  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x1800145a2  mov     [rdx+8], rsi
0x1800145a6  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800145ad  mov     [rdx], rax
0x1800145b0  mov     dword ptr [rdx+10h], 0
0x1800145b7  mov     [rdi], rdx
0x1800145ba  mov     rcx, [rdx]
0x1800145bd  mov     rax, [rcx+8]
0x1800145c1  mov     rcx, rdx
0x1800145c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145c9  xor     eax, eax
0x1800145cb  jmp     short loc_1800145D9
0x1800145cd  mov     qword ptr [rdi], 0
0x1800145d4  mov     eax, 8007000Eh
0x1800145d9  add     rsp, 20h
0x1800145dd  pop     r15
0x1800145df  pop     rdi
0x1800145e0  pop     rsi
0x1800145e1  pop     rbp
0x1800145e2  pop     rbx
0x1800145e3  retn
```
