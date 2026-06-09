# DelayLoadUalApi(void)

- ea: `0x18001548c`
- end: `0x180015537`
- name: `?DelayLoadUalApi@@YAHXZ`
- size: `171`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003dc4`
- `0x180007120`
- `0x180007700`

## callees

- `0x18001548c`
- `0x18001560c`
- `0x180015acc`
- `0x180017010`

## string_xrefs

- `0x1800154c9`: `Error loading ualapi.dll.`
- `0x1800154fc`: `Error loading ualapi.dll.`

## pseudocode

```c
__int64 __fastcall DelayLoadUalApi(const CHAR *a1)
{
  unsigned int AllImportsForDll; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r8

  if ( !dword_180022CA0 )
  {
    dword_180022CA0 = 1;
    AllImportsForDll = _HrLoadAllImportsForDll(a1);
    if ( (int)ElValidateHr_5(AllImportsForDll, v2, v3, 95) >= 0 )
      goto LABEL_6;
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(0x80000u, L"Error loading ualapi.dll.");
    if ( (int)ElValidateHr_5(2147943685LL, v4, v5, 99) >= 0 )
LABEL_6:
      dword_180022C9C = 1;
  }
  return (unsigned int)dword_180022C9C;
}

```

## disassembly

```asm
0x18001548c  sub     rsp, 28h
0x180015490  cmp     cs:dword_180022CA0, 0
0x180015497  jnz     loc_18001552B
0x18001549d  mov     cs:dword_180022CA0, 1
0x1800154a7  call    __HrLoadAllImportsForDll
0x1800154ac  mov     r9d, 5Fh ; '_'
0x1800154b2  mov     ecx, eax
0x1800154b4  call    ElValidateHr_5
0x1800154b9  test    eax, eax
0x1800154bb  jns     short loc_1800154EE
0x1800154bd  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800154c4  test    rax, rax
0x1800154c7  jz      short loc_1800154DA
0x1800154c9  lea     rdx, aErrorLoadingUa; "Error loading ualapi.dll."
0x1800154d0  mov     ecx, 80000h
0x1800154d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154da  mov     ecx, 80070505h
0x1800154df  mov     r9d, 63h ; 'c'
0x1800154e5  call    ElValidateHr_5
0x1800154ea  test    eax, eax
0x1800154ec  js      short loc_18001552B
0x1800154ee  jmp     short loc_180015521
0x1800154f0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800154f7  test    rax, rax
0x1800154fa  jz      short loc_18001550D
0x1800154fc  lea     rdx, aErrorLoadingUa; "Error loading ualapi.dll."
0x180015503  mov     ecx, 80000h
0x180015508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001550d  mov     ecx, 80070505h
0x180015512  mov     r9d, 6Fh ; 'o'
0x180015518  call    ElValidateHr_5
0x18001551d  test    eax, eax
0x18001551f  js      short loc_18001552B
0x180015521  mov     cs:dword_180022C9C, 1
0x18001552b  mov     eax, cs:dword_180022C9C
0x180015531  add     rsp, 28h
0x180015535  retn
0x1800164a5  push    rbp
0x1800164a7  sub     rsp, 20h
0x1800164ab  mov     rbp, rdx
0x1800164ae  mov     rax, [rcx]
0x1800164b1  cmp     dword ptr [rax], 0C06D007Eh
0x1800164b7  jz      short loc_1800164C5
0x1800164b9  cmp     dword ptr [rax], 0C06D007Fh
0x1800164bf  jz      short loc_1800164C5
0x1800164c1  xor     eax, eax
0x1800164c3  jmp     short loc_1800164CA
0x1800164c5  mov     eax, 1
0x1800164ca  add     rsp, 20h
0x1800164ce  pop     rbp
0x1800164cf  retn
```
