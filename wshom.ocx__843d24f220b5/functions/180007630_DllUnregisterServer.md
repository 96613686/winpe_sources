# DllUnregisterServer

- ea: `0x180007630`
- end: `0x180007681`
- name: `DllUnregisterServer`
- size: `81`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007630`
- `0x180011010`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // edi
  struct TaClassTable near **v1; // rbx
  struct TaClassTable near *v2; // rax

  v0 = 0;
  v1 = &g_TaClassTable;
  if ( (_DWORD)g_TaClassTable )
  {
    do
    {
      v2 = v1[1];
      if ( v2 && ((int (__fastcall *)(struct TaClassTable near *, _QWORD))v2)(v1[2], 0) < 0 )
        ++v0;
      v1 += 3;
    }
    while ( *(_DWORD *)v1 );
  }
  return v0 >= 1;
}

```

## disassembly

```asm
0x180007630  mov     [rsp+arg_0], rbx
0x180007635  push    rdi
0x180007636  sub     rsp, 20h
0x18000763a  xor     edi, edi
0x18000763c  lea     rbx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x180007643  cmp     cs:?g_TaClassTable@@3PAUTaClassTable@@A, edi; TaClassTable near * g_TaClassTable
0x180007649  jz      short loc_18000766E
0x18000764b  mov     rax, [rbx+8]
0x18000764f  test    rax, rax
0x180007652  jz      short loc_180007665
0x180007654  mov     rcx, [rbx+10h]
0x180007658  xor     edx, edx
0x18000765a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000765f  test    eax, eax
0x180007661  jns     short loc_180007665
0x180007663  inc     edi
0x180007665  add     rbx, 18h
0x180007669  cmp     dword ptr [rbx], 0
0x18000766c  jnz     short loc_18000764B
0x18000766e  mov     rbx, [rsp+28h+arg_0]
0x180007673  xor     eax, eax
0x180007675  cmp     edi, 1
0x180007678  setnl   al
0x18000767b  add     rsp, 20h
0x18000767f  pop     rdi
0x180007680  retn
```
