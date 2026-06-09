# CWMSDKBuffer::Create(ulong,INSSBuffer * *)

- ea: `0x180010c14`
- end: `0x180010cf7`
- name: `?Create@CWMSDKBuffer@@SAJKPEAPEAUINSSBuffer@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned int, struct INSSBuffer **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008760`
- `0x180010900`

## callees

- `0x1800011a0`
- `0x1800011ec`
- `0x1800106cc`
- `0x180010c14`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMSDKBuffer::Create(int a1, struct INSSBuffer **a2)
{
  int v4; // ebx
  CWMSDKBuffer *v5; // rax
  CWMSDKBuffer *v6; // rdi
  void *v7; // rax
  __int64 v8; // r9
  __int64 (__fastcall *v10)(CWMSDKBuffer *, GUID *, __int64 *); // rax
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = 0;
  if ( a1 < 0 )
    return (unsigned int)-2147024809;
  v5 = (CWMSDKBuffer *)operator new(0x148u);
  if ( !v5 || (v6 = CWMSDKBuffer::CWMSDKBuffer(v5)) == 0 )
    return (unsigned int)-2147024882;
  v7 = operator new[]((unsigned int)(a1 + 1));
  v8 = *(_QWORD *)v6;
  *((_QWORD *)v6 + 6) = v7;
  if ( !v7 )
  {
    (*(void (__fastcall **)(CWMSDKBuffer *, __int64))(v8 + 112))(v6, 1);
    return (unsigned int)-2147024882;
  }
  *((_QWORD *)v6 + 5) = v7;
  v10 = *(__int64 (__fastcall **)(CWMSDKBuffer *, GUID *, __int64 *))v8;
  *((_DWORD *)v6 + 15) = a1;
  *((_DWORD *)v6 + 14) = a1;
  v4 = v10(v6, &IID_IMediaBuffer, &v11);
  (*(void (__fastcall **)(CWMSDKBuffer *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct INSSBuffer **))v11)(v11, &IID_INSSBuffer, a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010c14  mov     [rsp+arg_0], rbx
0x180010c19  mov     [rsp+arg_8], rsi
0x180010c1e  push    rdi
0x180010c1f  sub     rsp, 20h
0x180010c23  mov     [rsp+28h+arg_10], 0
0x180010c2c  mov     rsi, rdx
0x180010c2f  mov     ebx, ecx
0x180010c31  test    ecx, ecx
0x180010c33  jns     short loc_180010C3C
0x180010c35  mov     ebx, 80070057h
0x180010c3a  jmp     short loc_180010C83
0x180010c3c  mov     ecx, 148h; Size
0x180010c41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010c46  test    rax, rax
0x180010c49  jz      short loc_180010C7E
0x180010c4b  mov     rcx, rax; this
0x180010c4e  call    ??0CWMSDKBuffer@@QEAA@XZ; CWMSDKBuffer::CWMSDKBuffer(void)
0x180010c53  mov     rdi, rax
0x180010c56  test    rax, rax
0x180010c59  jz      short loc_180010C7E
0x180010c5b  lea     ecx, [rbx+1]; unsigned __int64
0x180010c5e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010c63  mov     r9, [rdi]
0x180010c66  mov     rcx, rdi
0x180010c69  mov     [rdi+30h], rax
0x180010c6d  test    rax, rax
0x180010c70  jnz     short loc_180010C95
0x180010c72  lea     edx, [rax+1]
0x180010c75  mov     rax, [r9+70h]
0x180010c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c7e  mov     ebx, 8007000Eh
0x180010c83  mov     rsi, [rsp+28h+arg_8]
0x180010c88  mov     eax, ebx
0x180010c8a  mov     rbx, [rsp+28h+arg_0]
0x180010c8f  add     rsp, 20h
0x180010c93  pop     rdi
0x180010c94  retn
0x180010c95  mov     [rdi+28h], rax
0x180010c99  lea     r8, [rsp+28h+arg_10]
0x180010c9e  mov     rax, [r9]
0x180010ca1  lea     rdx, IID_IMediaBuffer
0x180010ca8  mov     [rdi+3Ch], ebx
0x180010cab  mov     [rdi+38h], ebx
0x180010cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cb3  mov     ebx, eax
0x180010cb5  mov     rcx, rdi
0x180010cb8  mov     rax, [rdi]
0x180010cbb  mov     rax, [rax+10h]
0x180010cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc4  test    ebx, ebx
0x180010cc6  js      short loc_180010C83
0x180010cc8  mov     rcx, [rsp+28h+arg_10]
0x180010ccd  lea     rdx, IID_INSSBuffer
0x180010cd4  mov     r8, rsi
0x180010cd7  mov     rax, [rcx]
0x180010cda  mov     rax, [rax]
0x180010cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce2  mov     rcx, [rsp+28h+arg_10]
0x180010ce7  mov     ebx, eax
0x180010ce9  mov     rax, [rcx]
0x180010cec  mov     rax, [rax+10h]
0x180010cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cf5  jmp     short loc_180010C83
```
