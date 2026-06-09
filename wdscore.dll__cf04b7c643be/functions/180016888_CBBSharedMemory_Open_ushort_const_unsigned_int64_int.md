# CBBSharedMemory::Open(ushort const *,unsigned __int64,int *)

- ea: `0x180016888`
- end: `0x18001694a`
- name: `?Open@CBBSharedMemory@@QEAAHPEBG_KPEAH@Z`
- size: `194`
- prototype: `__int64 __fastcall(CBBSharedMemory *__hidden this, const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001524c`
- `0x180016ae8`

## callees

- `0x180010180`
- `0x180016888`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016918`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180016918`

## pseudocode

```c
__int64 __fastcall CBBSharedMemory::Open(HANDLE *this, const unsigned __int16 *a2, int a3, int *a4)
{
  __int64 v6; // rax
  LPVOID v7; // rax

  if ( !a2 )
    return 0;
  v6 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, __int64, _QWORD, __int64, _DWORD, int, const unsigned __int16 *))(*(_QWORD *)g_Kernel32 + 592LL))(
         g_Kernel32,
         -1,
         0,
         134217732,
         0,
         a3,
         a2);
  *this = (HANDLE)v6;
  if ( !v6 )
    return 0;
  if ( a4 )
    *a4 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32) == 183;
  v7 = MapViewOfFile(*this, 0xF001Fu, 0, 0, 0);
  this[1] = v7;
  if ( !v7 )
  {
    CBBSharedMemory::Close((CBBSharedMemory *)this);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180016888  mov     [rsp+arg_0], rbx
0x18001688d  push    rdi
0x18001688e  sub     rsp, 40h
0x180016892  mov     rdi, r9
0x180016895  mov     rbx, rcx
0x180016898  test    rdx, rdx
0x18001689b  jz      loc_180016935
0x1800168a1  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800168a8  mov     r9d, 8000004h
0x1800168ae  mov     [rsp+48h+var_18], rdx
0x1800168b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800168b7  mov     [rsp+48h+var_20], r8d
0x1800168bc  xor     r8d, r8d
0x1800168bf  mov     dword ptr [rsp+48h+dwNumberOfBytesToMap], 0
0x1800168c7  mov     rax, [rcx]
0x1800168ca  mov     rax, [rax+250h]
0x1800168d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d6  mov     [rbx], rax
0x1800168d9  test    rax, rax
0x1800168dc  jz      short loc_180016935
0x1800168de  test    rdi, rdi
0x1800168e1  jz      short loc_180016901
0x1800168e3  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800168ea  mov     rax, [rcx]
0x1800168ed  mov     rax, [rax]
0x1800168f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f5  xor     ecx, ecx
0x1800168f7  cmp     eax, 0B7h
0x1800168fc  setz    cl
0x1800168ff  mov     [rdi], ecx
0x180016901  mov     rcx, [rbx]; hFileMappingObject
0x180016904  xor     r9d, r9d; dwFileOffsetLow
0x180016907  xor     r8d, r8d; dwFileOffsetHigh
0x18001690a  mov     [rsp+48h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180016913  mov     edx, 0F001Fh; dwDesiredAccess
0x180016918  call    cs:__imp_MapViewOfFile
0x18001691f  nop     dword ptr [rax+rax+00h]
0x180016924  mov     [rbx+8], rax
0x180016928  test    rax, rax
0x18001692b  jnz     short loc_180016943
0x18001692d  mov     rcx, rbx; this
0x180016930  call    ?Close@CBBSharedMemory@@QEAAXXZ; CBBSharedMemory::Close(void)
0x180016935  xor     eax, eax
0x180016937  mov     rbx, [rsp+48h+arg_0]
0x18001693c  add     rsp, 40h
0x180016940  pop     rdi
0x180016941  retn
0x180016943  mov     eax, 1
0x180016948  jmp     short loc_180016937
```
