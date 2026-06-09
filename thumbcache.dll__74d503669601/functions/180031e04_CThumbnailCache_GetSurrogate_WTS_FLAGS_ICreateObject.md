# CThumbnailCache::_GetSurrogate(WTS_FLAGS,ICreateObject * *)

- ea: `0x180031e04`
- end: `0x180031ee8`
- name: `?_GetSurrogate@CThumbnailCache@@AEAAJW4WTS_FLAGS@@PEAPEAUICreateObject@@@Z`
- size: `228`
- prototype: `int(CThumbnailCache *__hidden this, enum WTS_FLAGS, struct ICreateObject **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011c10`

## callees

- `0x180031e04`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031e5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031ed0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031e5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031ed0`

## pseudocode

```c
HRESULT __fastcall CThumbnailCache::_GetSurrogate(CThumbnailCache *this, enum WTS_FLAGS a2, LPVOID *a3)
{
  HRESULT result; // eax
  __int16 v5; // bx
  int v6; // r14d
  LPVOID *ppv; // rsi

  result = 0;
  *a3 = 0;
  v5 = a2;
  if ( (a2 & 0x100) != 0 )
    goto LABEL_9;
  if ( (a2 & 0x400) != 0 )
  {
    v6 = 2;
    ppv = (LPVOID *)((char *)this + 776);
    do
    {
      if ( !*ppv )
        result = CoCreateInstance(
                   &GUID_4545dea0_2dfc_4906_a728_6d986ba399a9,
                   0,
                   0x4004u,
                   &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                   ppv);
      if ( result >= 0 )
      {
        result = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LPVOID *))*ppv)(
                   *ppv,
                   &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                   a3);
        if ( result >= 0 )
          break;
      }
      *a3 = 0;
      result = 1;
      *ppv = 0;
      --v6;
    }
    while ( v6 );
    goto LABEL_9;
  }
  result = CoCreateInstance(
             &GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5,
             0,
             0x4004u,
             &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
             a3);
  if ( result >= 0 )
  {
LABEL_9:
    if ( (v5 & 0x800) != 0 && !*a3 )
      return -2147175934;
    return result;
  }
  if ( (v5 & 0x800) == 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180031e04  push    rbx
0x180031e06  push    rbp
0x180031e07  push    rsi
0x180031e08  push    rdi
0x180031e09  push    r14
0x180031e0b  sub     rsp, 30h
0x180031e0f  xor     eax, eax
0x180031e11  mov     qword ptr [r8], 0
0x180031e18  mov     rdi, r8
0x180031e1b  mov     ebx, edx
0x180031e1d  bt      edx, 8
0x180031e21  jb      short loc_180031E98
0x180031e23  bt      edx, 0Ah
0x180031e27  jnb     loc_180031EB5
0x180031e2d  lea     r14d, [rax+2]
0x180031e31  lea     rsi, [rcx+308h]
0x180031e38  lea     ebp, [rax+1]
0x180031e3b  cmp     qword ptr [rsi], 0
0x180031e3f  jnz     short loc_180031E62
0x180031e41  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180031e48  mov     [rsp+58h+ppv], rsi; ppv
0x180031e4d  xor     edx, edx; pUnkOuter
0x180031e4f  lea     rcx, _GUID_4545dea0_2dfc_4906_a728_6d986ba399a9; rclsid
0x180031e56  mov     r8d, 4004h; dwClsContext
0x180031e5c  call    cs:__imp_CoCreateInstance
0x180031e62  test    eax, eax
0x180031e64  js      short loc_180031E82
0x180031e66  mov     rcx, [rsi]
0x180031e69  lea     rdx, _GUID_75121952_e0d0_43e5_9380_1d80483acf72
0x180031e70  mov     r8, rdi
0x180031e73  mov     rax, [rcx]
0x180031e76  mov     rax, [rax]
0x180031e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e7e  test    eax, eax
0x180031e80  jns     short loc_180031E98
0x180031e82  mov     qword ptr [rdi], 0
0x180031e89  mov     eax, ebp
0x180031e8b  mov     qword ptr [rsi], 0
0x180031e92  add     r14d, 0FFFFFFFFh
0x180031e96  jnz     short loc_180031E3B
0x180031e98  bt      ebx, 0Bh
0x180031e9c  jnb     short loc_180031EAA
0x180031e9e  cmp     qword ptr [rdi], 0
0x180031ea2  mov     ecx, 8004B202h
0x180031ea7  cmovz   eax, ecx
0x180031eaa  add     rsp, 30h
0x180031eae  pop     r14
0x180031eb0  pop     rdi
0x180031eb1  pop     rsi
0x180031eb2  pop     rbp
0x180031eb3  pop     rbx
0x180031eb4  retn
0x180031eb5  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180031ebc  mov     [rsp+58h+ppv], rdi; ppv
0x180031ec1  xor     edx, edx; pUnkOuter
0x180031ec3  lea     rcx, _GUID_ab8902b4_09ca_4bb6_b78d_a8f59079a8d5; rclsid
0x180031eca  mov     r8d, 4004h; dwClsContext
0x180031ed0  call    cs:__imp_CoCreateInstance
0x180031ed6  test    eax, eax
0x180031ed8  jns     short loc_180031E98
0x180031eda  bt      ebx, 0Bh
0x180031ede  mov     ebp, 1
0x180031ee3  cmovnb  eax, ebp
0x180031ee6  jmp     short loc_180031EAA
```
