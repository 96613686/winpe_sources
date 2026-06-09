# CPipelineBatch::~CPipelineBatch(void)

- ea: `0x1800a0bbc`
- end: `0x1800a0c64`
- name: `??1CPipelineBatch@@QEAA@XZ`
- size: `168`
- prototype: `void __fastcall(CPipelineBatch *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800a0c70`
- `0x1800cf9fe`
- `0x1800cfb8a`

## callees

- `0x1800a0bbc`
- `0x1800d5010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800a0c05`
- `ole32!CoTaskMemFree` at `0x1800a0c0f`
- `ole32!CoTaskMemFree` at `0x1800a0c19`
- `ole32!CoTaskMemFree` at `0x1800a0c23`
- `ole32!CoTaskMemFree` at `0x1800a0c2d`
- `ole32!CoTaskMemFree` at `0x1800a0c05`
- `ole32!CoTaskMemFree` at `0x1800a0c0f`
- `ole32!CoTaskMemFree` at `0x1800a0c19`
- `ole32!CoTaskMemFree` at `0x1800a0c23`
- `ole32!CoTaskMemFree` at `0x1800a0c2d`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0c50`
- `KERNEL32!DeleteCriticalSection` at `0x1800a0c50`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CPipelineBatch::~CPipelineBatch(CPipelineBatch *this)
{
  __int64 i; // rbp
  __int64 v3; // rbx

  if ( *((_QWORD *)this + 10) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 17); i = (unsigned int)(i + 1) )
    {
      v3 = *((_QWORD *)this + 10);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 8 * i) + 16LL))(*(_QWORD *)(v3 + 8 * i));
      *(_QWORD *)(v3 + 8 * i) = 0;
    }
    CoTaskMemFree(*((LPVOID *)this + 10));
  }
  CoTaskMemFree(*((LPVOID *)this + 11));
  CoTaskMemFree(*((LPVOID *)this + 12));
  CoTaskMemFree(*((LPVOID *)this + 13));
  CoTaskMemFree(*((LPVOID *)this + 14));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800a0bbc  mov     [rsp+arg_18], rbx
0x1800a0bc1  mov     [rsp+arg_0], rcx
0x1800a0bc6  push    rbp
0x1800a0bc7  push    rsi
0x1800a0bc8  push    rdi
0x1800a0bc9  sub     rsp, 20h
0x1800a0bcd  mov     rsi, rcx
0x1800a0bd0  cmp     qword ptr [rcx+50h], 0
0x1800a0bd5  jz      short loc_1800A0C0B
0x1800a0bd7  xor     ebp, ebp
0x1800a0bd9  cmp     [rcx+44h], ebp
0x1800a0bdc  jbe     short loc_1800A0C01
0x1800a0bde  mov     rbx, [rsi+50h]
0x1800a0be2  mov     rcx, [rbx+rbp*8]
0x1800a0be6  mov     rax, [rcx]
0x1800a0be9  mov     rax, [rax+10h]
0x1800a0bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0bf2  mov     qword ptr [rbx+rbp*8], 0
0x1800a0bfa  inc     ebp
0x1800a0bfc  cmp     ebp, [rsi+44h]
0x1800a0bff  jb      short loc_1800A0BDE
0x1800a0c01  mov     rcx, [rsi+50h]; pv
0x1800a0c05  call    cs:__imp_CoTaskMemFree
0x1800a0c0b  mov     rcx, [rsi+58h]; pv
0x1800a0c0f  call    cs:__imp_CoTaskMemFree
0x1800a0c15  mov     rcx, [rsi+60h]; pv
0x1800a0c19  call    cs:__imp_CoTaskMemFree
0x1800a0c1f  mov     rcx, [rsi+68h]; pv
0x1800a0c23  call    cs:__imp_CoTaskMemFree
0x1800a0c29  mov     rcx, [rsi+70h]; pv
0x1800a0c2d  call    cs:__imp_CoTaskMemFree
0x1800a0c33  nop
0x1800a0c34  lea     rax, [rsi+8]
0x1800a0c38  mov     [rsp+38h+arg_8], rax
0x1800a0c3d  lea     rcx, [rax+8]; lpCriticalSection
0x1800a0c41  mov     [rsp+38h+arg_10], rcx
0x1800a0c46  cmp     byte ptr [rcx+28h], 0
0x1800a0c4a  jz      short loc_1800A0C57
0x1800a0c4c  mov     byte ptr [rcx+28h], 0
0x1800a0c50  call    cs:__imp_DeleteCriticalSection
0x1800a0c56  nop
0x1800a0c57  mov     rbx, [rsp+38h+arg_18]
0x1800a0c5c  add     rsp, 20h
0x1800a0c60  pop     rdi
0x1800a0c61  pop     rsi
0x1800a0c62  pop     rbp
0x1800a0c63  retn
```
