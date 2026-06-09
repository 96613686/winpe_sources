# ProviderRequest::Cleanup(void)

- ea: `0x180010a00`
- end: `0x180010a94`
- name: `?Cleanup@ProviderRequest@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(ProviderRequest *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010920`
- `0x180010a9c`
- `0x180010e90`
- `0x180012790`

## callees

- `0x180010a00`
- `0x18001c12a`
- `0x18001d010`

## pseudocode

```c
void __fastcall ProviderRequest::Cleanup(ProviderRequest *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( *(_QWORD *)this )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 80LL))(*((_QWORD *)this + 3));
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 3) = 0;
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    *((_QWORD *)this + 2) = 0;
  }
  *((_DWORD *)this + 8) = 0;
  memset_0((char *)this + 36, 0, 0x41Cu);
  memset_0((char *)this + 1088, 0, 0x41Cu);
}

```

## disassembly

```asm
0x180010a00  mov     [rsp+arg_0], rbx
0x180010a05  push    rdi
0x180010a06  sub     rsp, 20h
0x180010a0a  mov     rdx, [rcx]
0x180010a0d  mov     rbx, rcx
0x180010a10  test    rdx, rdx
0x180010a13  jz      short loc_180010A25
0x180010a15  mov     rcx, [rcx+18h]
0x180010a19  mov     rax, [rcx]
0x180010a1c  mov     rax, [rax+50h]
0x180010a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a25  and     qword ptr [rbx], 0
0x180010a29  and     qword ptr [rbx+18h], 0
0x180010a2e  mov     rcx, [rbx+8]
0x180010a32  test    rcx, rcx
0x180010a35  jz      short loc_180010A48
0x180010a37  mov     rax, [rcx]
0x180010a3a  mov     rax, [rax+8]
0x180010a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a43  and     qword ptr [rbx+8], 0
0x180010a48  mov     rcx, [rbx+10h]
0x180010a4c  test    rcx, rcx
0x180010a4f  jz      short loc_180010A62
0x180010a51  mov     rax, [rcx]
0x180010a54  mov     rax, [rax+8]
0x180010a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a5d  and     qword ptr [rbx+10h], 0
0x180010a62  and     dword ptr [rbx+20h], 0
0x180010a66  lea     rcx, [rbx+24h]; void *
0x180010a6a  mov     edi, 41Ch
0x180010a6f  xor     edx, edx; Val
0x180010a71  mov     r8d, edi; Size
0x180010a74  call    memset_0
0x180010a79  lea     rcx, [rbx+440h]; void *
0x180010a80  mov     r8d, edi; Size
0x180010a83  xor     edx, edx; Val
0x180010a85  mov     rbx, [rsp+28h+arg_0]
0x180010a8a  add     rsp, 20h
0x180010a8e  pop     rdi
0x180010a8f  jmp     memset_0
```
