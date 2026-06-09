# DllGetClassObject

- ea: `0x180019010`
- end: `0x1800190dd`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002c54`
- `0x18000ff08`
- `0x180019010`
- `0x18001b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  HRESULT v11; // ebx

  if ( !anonymous_namespace_::isFeatureEnabled() )
    return -2147221230;
  if ( ppv )
    *ppv = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = (_QWORD *)*((_QWORD *)&off_18001D340 + 2 * v7);
    if ( *v8 == *(_QWORD *)&rclsid->Data1 && v8[1] == *(_QWORD *)rclsid->Data4 )
      break;
    if ( (int)++v7 >= 1 )
    {
      if ( v7 == 1 )
        return -2147221231;
      break;
    }
  }
  v9 = operator new(0x18u);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  *v9 = &CUWFCspClassFactory::`vftable';
  v9[2] = (char *)&off_18001D340 + 16 * v7;
  *((_DWORD *)v9 + 2) = 1;
  v11 = ((__int64 (__fastcall *)(_QWORD *, const IID *const, LPVOID *))CUWFCspClassFactory::`vftable')(v9, riid, ppv);
  (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  return v11;
}

```

## disassembly

```asm
0x180019010  push    rbx
0x180019012  push    rbp
0x180019013  push    rsi
0x180019014  push    rdi
0x180019015  push    r15
0x180019017  sub     rsp, 20h
0x18001901b  mov     rdi, r8
0x18001901e  mov     rbp, rdx
0x180019021  mov     rsi, rcx
0x180019024  call    _anonymous_namespace___isFeatureEnabled
0x180019029  test    al, al
0x18001902b  jnz     short loc_180019037
0x18001902d  mov     eax, 80040112h
0x180019032  jmp     loc_1800190D2
0x180019037  test    rdi, rdi
0x18001903a  jz      short loc_180019043
0x18001903c  mov     qword ptr [rdi], 0
0x180019043  xor     ebx, ebx
0x180019045  lea     r15, off_18001D340
0x18001904c  mov     eax, ebx
0x18001904e  add     rax, rax
0x180019051  mov     rcx, [r15+rax*8]
0x180019055  mov     rax, [rcx]
0x180019058  cmp     rax, [rsi]
0x18001905b  jnz     short loc_180019067
0x18001905d  mov     rax, [rcx+8]
0x180019061  cmp     rax, [rsi+8]
0x180019065  jz      short loc_180019077
0x180019067  inc     ebx
0x180019069  cmp     ebx, 1
0x18001906c  jl      short loc_18001904C
0x18001906e  jnz     short loc_180019077
0x180019070  mov     eax, 80040111h
0x180019075  jmp     short loc_1800190D2
0x180019077  mov     ecx, 18h; Size
0x18001907c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019081  mov     rsi, rax
0x180019084  test    rax, rax
0x180019087  jz      short loc_1800190CD
0x180019089  lea     rax, ??_7CUWFCspClassFactory@@6B@; const CUWFCspClassFactory::`vftable'
0x180019090  mov     ecx, ebx
0x180019092  shl     rcx, 4
0x180019096  mov     r8, rdi
0x180019099  add     rcx, r15
0x18001909c  mov     [rsi], rax
0x18001909f  mov     rax, [rax]
0x1800190a2  mov     rdx, rbp
0x1800190a5  mov     [rsi+10h], rcx
0x1800190a9  mov     rcx, rsi
0x1800190ac  mov     dword ptr [rsi+8], 1
0x1800190b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190b8  mov     rcx, [rsi]
0x1800190bb  mov     ebx, eax
0x1800190bd  mov     rax, [rcx+10h]
0x1800190c1  mov     rcx, rsi
0x1800190c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c9  mov     eax, ebx
0x1800190cb  jmp     short loc_1800190D2
0x1800190cd  mov     eax, 8007000Eh
0x1800190d2  add     rsp, 20h
0x1800190d6  pop     r15
0x1800190d8  pop     rdi
0x1800190d9  pop     rsi
0x1800190da  pop     rbp
0x1800190db  pop     rbx
0x1800190dc  retn
```
