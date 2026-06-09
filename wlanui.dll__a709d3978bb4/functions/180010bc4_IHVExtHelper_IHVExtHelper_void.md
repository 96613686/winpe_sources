# IHVExtHelper::~IHVExtHelper(void)

- ea: `0x180010bc4`
- end: `0x180010c2d`
- name: `??1IHVExtHelper@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(IHVExtHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010c34`

## callees

- `0x180010bc4`
- `0x18001d010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010c10`
- `ole32!CoTaskMemFree` at `0x180010c10`

## pseudocode

```c
void __fastcall IHVExtHelper::~IHVExtHelper(IHVExtHelper *this)
{
  __int64 i; // rdi
  __int64 v3; // rcx

  if ( *(_QWORD *)this )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)this + 8 * i);
      if ( v3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(*(_QWORD *)this + 8 * i) = 0;
      }
    }
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180010bc4  mov     [rsp+arg_0], rbx
0x180010bc9  mov     [rsp+arg_8], rsi
0x180010bce  push    rdi
0x180010bcf  sub     rsp, 20h
0x180010bd3  cmp     qword ptr [rcx], 0
0x180010bd7  mov     rbx, rcx
0x180010bda  jz      short loc_180010C1D
0x180010bdc  xor     edi, edi
0x180010bde  cmp     [rcx+8], edi
0x180010be1  jbe     short loc_180010C0D
0x180010be3  mov     rax, [rbx]
0x180010be6  mov     rcx, [rax+rdi*8]
0x180010bea  test    rcx, rcx
0x180010bed  jz      short loc_180010C06
0x180010bef  mov     rax, [rcx]
0x180010bf2  mov     rax, [rax+10h]
0x180010bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bfb  mov     rax, [rbx]
0x180010bfe  mov     qword ptr [rax+rdi*8], 0
0x180010c06  inc     edi
0x180010c08  cmp     edi, [rbx+8]
0x180010c0b  jb      short loc_180010BE3
0x180010c0d  mov     rcx, [rbx]; pv
0x180010c10  call    cs:__imp_CoTaskMemFree
0x180010c16  mov     qword ptr [rbx], 0
0x180010c1d  mov     rbx, [rsp+28h+arg_0]
0x180010c22  mov     rsi, [rsp+28h+arg_8]
0x180010c27  add     rsp, 20h
0x180010c2b  pop     rdi
0x180010c2c  retn
```
