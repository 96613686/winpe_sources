# DllGetClassObject

- ea: `0x1800018a0`
- end: `0x180001973`
- name: `DllGetClassObject`
- size: `211`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001980`
- `0x1800060e4`
- `0x180011010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct TaClassTable near **i; // rcx
  const struct TaDescUnknown *v7; // rbx
  __int64 v8; // rax
  CClassFactory *v9; // rax
  CClassFactory *v10; // rax
  CClassFactory *v11; // rsi
  HRESULT v12; // ebx
  HRESULT result; // eax

  if ( !ppv )
    return -2147467261;
  for ( i = &g_TaClassTable; ; i += 3 )
  {
    if ( !*(_DWORD *)i )
      return -2147221231;
    v7 = i[2];
    v8 = **(_QWORD **)v7 - *(_QWORD *)&rclsid->Data1;
    if ( !v8 )
      v8 = *(_QWORD *)(*(_QWORD *)v7 + 8LL) - *(_QWORD *)rclsid->Data4;
    if ( !v8 )
      break;
  }
  v9 = (CClassFactory *)operator new(0x18u);
  if ( v9 && (v10 = CClassFactory::CClassFactory(v9, v7), (v11 = v10) != 0) )
  {
    v12 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v10)(v10, riid, ppv);
    (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v11 + 16LL))(v11);
    return v12;
  }
  else
  {
    result = -2147024882;
    *ppv = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800018a0  mov     [rsp+arg_10], rbp
0x1800018a5  push    rdi
0x1800018a6  sub     rsp, 20h
0x1800018aa  mov     rdi, r8
0x1800018ad  mov     rbp, rdx
0x1800018b0  mov     r9, rcx
0x1800018b3  test    r8, r8
0x1800018b6  jz      loc_18000196C
0x1800018bc  lea     rcx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x1800018c3  mov     [rsp+28h+arg_0], rbx
0x1800018c8  cmp     dword ptr [rcx], 0
0x1800018cb  jz      short loc_180001944
0x1800018cd  mov     rbx, [rcx+10h]
0x1800018d1  mov     rdx, [rbx]
0x1800018d4  mov     rax, [rdx]
0x1800018d7  sub     rax, [r9]
0x1800018da  jnz     short loc_1800018E4
0x1800018dc  mov     rax, [rdx+8]
0x1800018e0  sub     rax, [r9+8]
0x1800018e4  test    rax, rax
0x1800018e7  jz      short loc_1800018EF
0x1800018e9  add     rcx, 18h
0x1800018ed  jmp     short loc_1800018C8
0x1800018ef  mov     ecx, 18h; Size
0x1800018f4  mov     [rsp+28h+arg_8], rsi
0x1800018f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800018fe  test    rax, rax
0x180001901  jz      short loc_180001959
0x180001903  mov     rdx, rbx; struct TaDescUnknown *
0x180001906  mov     rcx, rax; this
0x180001909  call    ??0CClassFactory@@QEAA@PEBUTaDescUnknown@@@Z; CClassFactory::CClassFactory(TaDescUnknown const *)
0x18000190e  mov     rsi, rax
0x180001911  test    rax, rax
0x180001914  jz      short loc_180001959
0x180001916  mov     rcx, [rax]
0x180001919  mov     r8, rdi
0x18000191c  mov     rdx, rbp
0x18000191f  mov     rax, [rcx]
0x180001922  mov     rcx, rsi
0x180001925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000192a  mov     rcx, [rsi]
0x18000192d  mov     ebx, eax
0x18000192f  mov     rax, [rcx+10h]
0x180001933  mov     rcx, rsi
0x180001936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000193b  mov     rsi, [rsp+28h+arg_8]
0x180001940  mov     eax, ebx
0x180001942  jmp     short loc_180001949
0x180001944  mov     eax, 80040111h
0x180001949  mov     rbx, [rsp+28h+arg_0]
0x18000194e  mov     rbp, [rsp+28h+arg_10]
0x180001953  add     rsp, 20h
0x180001957  pop     rdi
0x180001958  retn
0x180001959  mov     rsi, [rsp+28h+arg_8]
0x18000195e  mov     eax, 8007000Eh
0x180001963  mov     qword ptr [rdi], 0
0x18000196a  jmp     short loc_180001949
0x18000196c  mov     eax, 80004003h
0x180001971  jmp     short loc_18000194E
```
