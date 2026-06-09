# DllGetClassObject

- ea: `0x1800022b0`
- end: `0x18000234d`
- name: `DllGetClassObject`
- size: `157`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001064`
- `0x1800022b0`
- `0x180005010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // edi
  char *v7; // rbx
  __int64 (__fastcall *v8)(char *, const IID *const, LPVOID *); // rax

  if ( !ppv )
    return -2147024809;
  v7 = (char *)operator new(0x20u);
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 1;
    *(_QWORD *)v7 = &CScavengeUiClassFactory::`vftable';
    _InterlockedIncrement(&dword_18000A8D4);
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
    return -2147024882;
  v8 = **(__int64 (__fastcall ***)(char *, const IID *const, LPVOID *))v7;
  *(IID *)(v7 + 12) = *rclsid;
  v6 = v8(v7, riid, ppv);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
  return v6;
}

```

## disassembly

```asm
0x1800022b0  push    rbx
0x1800022b2  push    rbp
0x1800022b3  push    rsi
0x1800022b4  push    rdi
0x1800022b5  push    r14
0x1800022b7  sub     rsp, 20h
0x1800022bb  mov     rsi, r8
0x1800022be  mov     rbp, rdx
0x1800022c1  mov     r14, rcx
0x1800022c4  test    r8, r8
0x1800022c7  jnz     short loc_1800022D0
0x1800022c9  mov     edi, 80070057h
0x1800022ce  jmp     short loc_180002340
0x1800022d0  mov     ecx, 20h ; ' '; Size
0x1800022d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800022da  mov     rbx, rax
0x1800022dd  test    rax, rax
0x1800022e0  jz      short loc_1800022FC
0x1800022e2  lea     rax, ??_7CScavengeUiClassFactory@@6B@; const CScavengeUiClassFactory::`vftable'
0x1800022e9  mov     dword ptr [rbx+8], 1
0x1800022f0  mov     [rbx], rax
0x1800022f3  lock inc cs:dword_18000A8D4
0x1800022fa  jmp     short loc_1800022FE
0x1800022fc  xor     ebx, ebx
0x1800022fe  xor     edi, edi
0x180002300  mov     eax, 8007000Eh
0x180002305  test    rbx, rbx
0x180002308  cmovz   edi, eax
0x18000230b  jz      short loc_180002340
0x18000230d  mov     rax, [rbx]
0x180002310  mov     r8, rsi
0x180002313  movups  xmm0, xmmword ptr [r14]
0x180002317  mov     rdx, rbp
0x18000231a  mov     rcx, rbx
0x18000231d  mov     rax, [rax]
0x180002320  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180002325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000232a  mov     edi, eax
0x18000232c  test    rbx, rbx
0x18000232f  jz      short loc_180002340
0x180002331  mov     rcx, [rbx]
0x180002334  mov     rax, [rcx+10h]
0x180002338  mov     rcx, rbx
0x18000233b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002340  mov     eax, edi
0x180002342  add     rsp, 20h
0x180002346  pop     r14
0x180002348  pop     rdi
0x180002349  pop     rsi
0x18000234a  pop     rbp
0x18000234b  pop     rbx
0x18000234c  retn
```
