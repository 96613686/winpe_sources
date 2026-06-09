# CWMSDKBufferPool::CreateInstance(ulong,ulong,ulong,CWMSDKBufferPool * *)

- ea: `0x180010d00`
- end: `0x180010da1`
- name: `?CreateInstance@CWMSDKBufferPool@@SAJKKKPEAPEAV1@@Z`
- size: `161`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, struct CWMSDKBufferPool **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a860`

## callees

- `0x1800011a0`
- `0x180001f1c`
- `0x180010d00`
- `0x18002971c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180010d4e`
- `KERNEL32!InitializeCriticalSection` at `0x180010d4e`

## pseudocode

```c
__int64 __fastcall CWMSDKBufferPool::CreateInstance(int a1, __int64 a2, __int64 a3, struct CWMSDKBufferPool **a4)
{
  char *v6; // rdi
  unsigned int v7; // r9d
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-38h]

  v6 = (char *)operator new(0x80u);
  if ( v6 )
  {
    *(_QWORD *)v6 = &CWMSDKBufferPool::`vftable';
    memset_0(v6 + 24, 0, 0x40u);
    *((_DWORD *)v6 + 3) = a1;
    *((_DWORD *)v6 + 2) = 0;
    *((_DWORD *)v6 + 4) = 1;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 88));
    v8 = CVCellPool::Initialize((CVCellPool *)(v6 + 24), a1 + 328, 4u, v7, v11);
    *a4 = (struct CWMSDKBufferPool *)v6;
    v9 = v8;
    if ( v8 < 0 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
      *a4 = 0;
    }
    return v9;
  }
  else
  {
    *a4 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180010d00  push    rbx
0x180010d02  push    rbp
0x180010d03  push    rsi
0x180010d04  push    rdi
0x180010d05  sub     rsp, 38h
0x180010d09  mov     ebp, ecx
0x180010d0b  mov     rsi, r9
0x180010d0e  mov     ecx, 80h; Size
0x180010d13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d18  mov     rdi, rax
0x180010d1b  test    rax, rax
0x180010d1e  jz      short loc_180010D8C
0x180010d20  xor     edx, edx; Val
0x180010d22  lea     rax, ??_7CWMSDKBufferPool@@6B@; const CWMSDKBufferPool::`vftable'
0x180010d29  lea     rcx, [rdi+18h]; void *
0x180010d2d  mov     [rdi], rax
0x180010d30  lea     r8d, [rdx+40h]; Size
0x180010d34  call    memset_0
0x180010d39  lea     rcx, [rdi+58h]; lpCriticalSection
0x180010d3d  mov     [rdi+0Ch], ebp
0x180010d40  mov     dword ptr [rdi+8], 0
0x180010d47  mov     dword ptr [rdi+10h], 1
0x180010d4e  call    cs:__imp_InitializeCriticalSection
0x180010d54  lea     edx, [rbp+148h]; unsigned int
0x180010d5a  mov     r8d, 4; unsigned int
0x180010d60  lea     rcx, [rdi+18h]; this
0x180010d64  call    ?Initialize@CVCellPool@@QEAAJKKKH@Z; CVCellPool::Initialize(ulong,ulong,ulong,int)
0x180010d69  mov     [rsi], rdi
0x180010d6c  mov     ebx, eax
0x180010d6e  test    eax, eax
0x180010d70  jns     short loc_180010D88
0x180010d72  mov     rcx, [rdi]
0x180010d75  mov     rax, [rcx+10h]
0x180010d79  mov     rcx, rdi
0x180010d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d81  mov     qword ptr [rsi], 0
0x180010d88  mov     eax, ebx
0x180010d8a  jmp     short loc_180010D98
0x180010d8c  mov     qword ptr [rsi], 0
0x180010d93  mov     eax, 8007000Eh
0x180010d98  add     rsp, 38h
0x180010d9c  pop     rdi
0x180010d9d  pop     rsi
0x180010d9e  pop     rbp
0x180010d9f  pop     rbx
0x180010da0  retn
```
