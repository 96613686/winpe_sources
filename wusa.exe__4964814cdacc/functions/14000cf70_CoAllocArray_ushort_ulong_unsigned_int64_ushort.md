# CoAllocArray<ushort *>(ulong,unsigned __int64,ushort * * *)

- ea: `0x14000cf70`
- end: `0x14000d021`
- name: `??$CoAllocArray@PEAG@@YAJK_KPEAPEAPEAG@Z`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d620`

## callees

- `0x140001a63`
- `0x14000cf70`
- `0x140015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14000cfc2`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x14000cfc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000cfa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000cfa2`

## pseudocode

```c
__int64 __fastcall CoAllocArray<unsigned short *>(__int64 a1, unsigned __int64 a2, void **a3)
{
  LPVOID v4; // rax
  LPVOID v5; // rbx
  size_t v6; // rsi
  LPMALLOC ppMalloc; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppMalloc = 0;
  if ( !is_mul_ok(a2, 8u) )
    return 2147942934LL;
  v4 = CoTaskMemAlloc(8 * a2);
  *a3 = v4;
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v6 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(LPMALLOC, LPVOID))ppMalloc->lpVtbl->GetSize)(ppMalloc, v5);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(*a3, 0, v6);
  return 0;
}

```

## disassembly

```asm
0x14000cf70  mov     [rsp+arg_0], rbx
0x14000cf75  mov     [rsp+arg_8], rsi
0x14000cf7a  push    rdi
0x14000cf7b  sub     rsp, 20h
0x14000cf7f  mov     eax, 8
0x14000cf84  mov     qword ptr [r8], 0
0x14000cf8b  mul     rdx
0x14000cf8e  mov     rdi, r8
0x14000cf91  mov     [rsp+28h+ppMalloc], 0
0x14000cf9a  test    rdx, rdx
0x14000cf9d  jnz     short loc_14000D00C
0x14000cf9f  mov     rcx, rax; cb
0x14000cfa2  call    cs:__imp_CoTaskMemAlloc
0x14000cfa8  mov     [rdi], rax
0x14000cfab  mov     rbx, rax
0x14000cfae  test    rax, rax
0x14000cfb1  jz      short loc_14000D005
0x14000cfb3  xor     esi, esi
0x14000cfb5  lea     rdx, [rsp+28h+ppMalloc]; ppMalloc
0x14000cfba  mov     [rsp+28h+ppMalloc], rsi
0x14000cfbf  lea     ecx, [rsi+1]; dwMemContext
0x14000cfc2  call    cs:__imp_CoGetMalloc
0x14000cfc8  test    eax, eax
0x14000cfca  js      short loc_14000CFF4
0x14000cfcc  mov     rcx, [rsp+28h+ppMalloc]
0x14000cfd1  mov     rdx, rbx
0x14000cfd4  mov     rax, [rcx]
0x14000cfd7  mov     rax, [rax+30h]
0x14000cfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cfe0  mov     rcx, [rsp+28h+ppMalloc]
0x14000cfe5  mov     rsi, rax
0x14000cfe8  mov     rdx, [rcx]
0x14000cfeb  mov     rax, [rdx+10h]
0x14000cfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cff4  mov     rcx, [rdi]; void *
0x14000cff7  mov     r8, rsi; Size
0x14000cffa  xor     edx, edx; Val
0x14000cffc  call    memset_0
0x14000d001  xor     eax, eax
0x14000d003  jmp     short loc_14000D011
0x14000d005  mov     eax, 8007000Eh
0x14000d00a  jmp     short loc_14000D011
0x14000d00c  mov     eax, 80070216h
0x14000d011  mov     rbx, [rsp+28h+arg_0]
0x14000d016  mov     rsi, [rsp+28h+arg_8]
0x14000d01b  add     rsp, 20h
0x14000d01f  pop     rdi
0x14000d020  retn
```
