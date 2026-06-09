# VAR::MoveToHeap(void)

- ea: `0x180003f00`
- end: `0x180003fce`
- name: `?MoveToHeap@VAR@@QEAAJXZ`
- size: `206`
- prototype: `__int64 __fastcall(VAR *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c40`
- `0x180004400`
- `0x18001f0f0`
- `0x180037330`
- `0x1800437fc`
- `0x18006a4a0`
- `0x180074300`
- `0x180077260`

## callees

- `0x180003f00`
- `0x18001ed10`
- `0x18006b41c`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180003f13`
- `KERNEL32!TlsGetValue` at `0x180003f13`

## pseudocode

```c
__int64 __fastcall VAR::MoveToHeap(VAR *this)
{
  _QWORD *Value; // rax
  GcBlockFactory *v3; // rcx
  __int64 v4; // rbx
  char *v5; // rax
  __int64 v6; // rax
  __int64 result; // rax
  struct GcBlock *v8; // rdx

  Value = TlsGetValue(g_luTls);
  if ( !Value )
    goto LABEL_12;
  v4 = Value[4];
  if ( !v4 )
    goto LABEL_12;
  v5 = *(char **)(v4 + 16);
  if ( v5 == *(char **)(v4 + 8) )
  {
    v8 = *(struct GcBlock **)v4;
    if ( *(_QWORD *)v4 )
    {
      *(_QWORD *)v4 = *((_QWORD *)v8 + 150);
    }
    else
    {
      v8 = GcBlockFactory::PblkAlloc(v3);
      if ( !v8 )
        goto LABEL_12;
    }
    v5 = (char *)v8 + 1200;
    *((_QWORD *)v8 + 150) = *(_QWORD *)(v4 + 8);
    *(_QWORD *)(v4 + 8) = v8;
  }
  ++*(_DWORD *)(v4 + 24);
  *(_QWORD *)(v4 + 16) = v5 - 24;
  *((_WORD *)v5 - 12) = 0;
  if ( *(_DWORD *)(v4 + 24) == 1 )
    _InterlockedIncrement(&g_cLibRef);
  v6 = *(_QWORD *)(v4 + 16);
  if ( v6 )
  {
    *(_OWORD *)v6 = *(_OWORD *)this;
    *(_QWORD *)(v6 + 16) = *((_QWORD *)this + 2);
    *((_QWORD *)this + 1) = v6;
    result = 0;
    *(_WORD *)this = 74;
    return result;
  }
LABEL_12:
  VAR::Clear(this);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003f00  mov     [rsp+arg_0], rbx
0x180003f05  push    rdi
0x180003f06  sub     rsp, 20h
0x180003f0a  mov     rdi, rcx
0x180003f0d  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180003f13  call    cs:__imp_TlsGetValue
0x180003f1a  nop     dword ptr [rax+rax+00h]
0x180003f1f  test    rax, rax
0x180003f22  jz      loc_180003FBF
0x180003f28  mov     rbx, [rax+20h]
0x180003f2c  test    rbx, rbx
0x180003f2f  jz      loc_180003FBF
0x180003f35  mov     rax, [rbx+10h]
0x180003f39  cmp     rax, [rbx+8]
0x180003f3d  jz      short loc_180003F8C
0x180003f3f  inc     dword ptr [rbx+18h]
0x180003f42  lea     rcx, [rax-18h]
0x180003f46  xor     eax, eax
0x180003f48  mov     [rbx+10h], rcx
0x180003f4c  mov     [rcx], ax
0x180003f4f  cmp     dword ptr [rbx+18h], 1
0x180003f53  jnz     short loc_180003F5C
0x180003f55  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180003f5c  mov     rax, [rbx+10h]
0x180003f60  test    rax, rax
0x180003f63  jz      short loc_180003FBF
0x180003f65  movups  xmm0, xmmword ptr [rdi]
0x180003f68  movups  xmmword ptr [rax], xmm0
0x180003f6b  movsd   xmm1, qword ptr [rdi+10h]
0x180003f70  movsd   qword ptr [rax+10h], xmm1
0x180003f75  mov     [rdi+8], rax
0x180003f79  xor     eax, eax
0x180003f7b  mov     word ptr [rdi], 4Ah ; 'J'
0x180003f80  mov     rbx, [rsp+28h+arg_0]
0x180003f85  add     rsp, 20h
0x180003f89  pop     rdi
0x180003f8a  retn
0x180003f8c  mov     rdx, [rbx]
0x180003f8f  test    rdx, rdx
0x180003f92  jz      short loc_180003FB2
0x180003f94  mov     rax, [rdx+4B0h]
0x180003f9b  mov     [rbx], rax
0x180003f9e  mov     rcx, [rbx+8]
0x180003fa2  lea     rax, [rdx+4B0h]
0x180003fa9  mov     [rax], rcx
0x180003fac  mov     [rbx+8], rdx
0x180003fb0  jmp     short loc_180003F3F
0x180003fb2  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x180003fb7  mov     rdx, rax
0x180003fba  test    rax, rax
0x180003fbd  jnz     short loc_180003F9E
0x180003fbf  mov     rcx, rdi; this
0x180003fc2  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180003fc7  mov     eax, 8007000Eh
0x180003fcc  jmp     short loc_180003F80
```
