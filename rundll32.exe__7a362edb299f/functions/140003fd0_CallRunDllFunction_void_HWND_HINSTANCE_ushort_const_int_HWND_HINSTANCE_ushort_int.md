# CallRunDllFunction(void (*)(HWND__ *,HINSTANCE__ *,ushort const *,int),HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x140003fd0`
- end: `0x140003ff6`
- name: `?CallRunDllFunction@@YAXP6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z01PEAGH@Z`
- size: `38`
- prototype: `void __fastcall(void (*)(HWND, HINSTANCE, const unsigned __int16 *, int), HWND, HINSTANCE, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007798`

## callees

- `0x14000c010`

## pseudocode

```c
void __fastcall CallRunDllFunction(
        void (*a1)(HWND, HINSTANCE, const unsigned __int16 *, int),
        HWND a2,
        HINSTANCE a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  ((void (__fastcall *)(HWND, HINSTANCE, unsigned __int16 *, _QWORD))a1)(a2, g_hInstance, a4, a5);
}

```

## disassembly

```asm
0x140003fd0  sub     rsp, 38h
0x140003fd4  mov     r10, rdx
0x140003fd7  mov     r8, r9
0x140003fda  mov     r9d, [rsp+38h+arg_20]
0x140003fdf  mov     rax, rcx
0x140003fe2  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x140003fe9  mov     rcx, r10
0x140003fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ff1  add     rsp, 38h
0x140003ff5  retn
```
