# UL_NATIVE_REQUEST::Reset(void)

- ea: `0x18000f660`
- end: `0x18000f735`
- name: `?Reset@UL_NATIVE_REQUEST@@AEAAXXZ`
- size: `213`
- prototype: `void __fastcall(UL_NATIVE_REQUEST *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eef0`
- `0x18000f510`

## callees

- `0x18000f660`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f718`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f72a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f72a`

## pseudocode

```c
void __fastcall UL_NATIVE_REQUEST::Reset(UL_NATIVE_REQUEST *this)
{
  void *v2; // rcx
  void *v3; // rcx
  char *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 376);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 376) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 377);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 377) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 368);
  if ( v4 != (char *)this + 32 )
    LocalFree(v4);
  ++*((_DWORD *)this + 756);
  *((_DWORD *)this + 1) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 784) = 0;
  *((_QWORD *)this + 368) = (char *)this + 32;
  *((_DWORD *)this + 738) = 2912;
  *((_OWORD *)this + 194) = 0;
  *((_OWORD *)this + 195) = 0;
  *(_OWORD *)((char *)this + 3064) = 0;
  *(_OWORD *)((char *)this + 3080) = 0;
}

```

## disassembly

```asm
0x18000f660  mov     [rsp+arg_0], rbx
0x18000f665  mov     [rsp+arg_8], rsi
0x18000f66a  push    rdi
0x18000f66b  sub     rsp, 20h
0x18000f66f  mov     rbx, rcx
0x18000f672  xor     esi, esi
0x18000f674  mov     rcx, [rcx+0BC0h]; hObject
0x18000f67b  test    rcx, rcx
0x18000f67e  jnz     loc_18000F706
0x18000f684  mov     rcx, [rbx+0BC8h]; hObject
0x18000f68b  test    rcx, rcx
0x18000f68e  jnz     loc_18000F718
0x18000f694  mov     rcx, [rbx+0B80h]; hMem
0x18000f69b  lea     rdi, [rbx+20h]
0x18000f69f  cmp     rcx, rdi
0x18000f6a2  jnz     loc_18000F72A
0x18000f6a8  inc     dword ptr [rbx+0BD0h]
0x18000f6ae  xorps   xmm0, xmm0
0x18000f6b1  mov     [rbx+4], esi
0x18000f6b4  xorps   xmm1, xmm1
0x18000f6b7  mov     [rbx+8], rsi
0x18000f6bb  mov     [rbx+10h], rsi
0x18000f6bf  mov     [rbx+18h], rsi
0x18000f6c3  mov     [rbx+0C40h], esi
0x18000f6c9  mov     rsi, [rsp+28h+arg_8]
0x18000f6ce  mov     [rbx+0B80h], rdi
0x18000f6d5  mov     dword ptr [rbx+0B88h], 0B60h
0x18000f6df  movups  xmmword ptr [rbx+0C20h], xmm0
0x18000f6e6  movups  xmmword ptr [rbx+0C30h], xmm0
0x18000f6ed  movups  xmmword ptr [rbx+0BF8h], xmm1
0x18000f6f4  movups  xmmword ptr [rbx+0C08h], xmm1
0x18000f6fb  mov     rbx, [rsp+28h+arg_0]
0x18000f700  add     rsp, 20h
0x18000f704  pop     rdi
0x18000f705  retn
0x18000f706  call    cs:__imp_CloseHandle
0x18000f70c  mov     [rbx+0BC0h], rsi
0x18000f713  jmp     loc_18000F684
0x18000f718  call    cs:__imp_CloseHandle
0x18000f71e  mov     [rbx+0BC8h], rsi
0x18000f725  jmp     loc_18000F694
0x18000f72a  call    cs:__imp_LocalFree
0x18000f730  jmp     loc_18000F6A8
```
