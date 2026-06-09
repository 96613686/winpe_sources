# VAR::MoveToHeap(void)

- ea: `0x1800060b0`
- end: `0x180006177`
- name: `?MoveToHeap@VAR@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(VAR *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180005e00`
- `0x180006550`
- `0x180023ad0`
- `0x180035dc4`
- `0x180042134`
- `0x1800683f0`
- `0x180071da0`
- `0x180074900`

## callees

- `0x1800060b0`
- `0x180022b20`
- `0x1800692dc`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800060c3`
- `KERNEL32!TlsGetValue` at `0x1800060c3`

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
0x1800060b0  mov     [rsp+arg_0], rbx
0x1800060b5  push    rdi
0x1800060b6  sub     rsp, 20h
0x1800060ba  mov     rdi, rcx
0x1800060bd  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800060c3  call    cs:__imp_TlsGetValue
0x1800060c9  test    rax, rax
0x1800060cc  jz      loc_180006168
0x1800060d2  mov     rbx, [rax+20h]
0x1800060d6  test    rbx, rbx
0x1800060d9  jz      loc_180006168
0x1800060df  mov     rax, [rbx+10h]
0x1800060e3  cmp     rax, [rbx+8]
0x1800060e7  jz      short loc_180006135
0x1800060e9  inc     dword ptr [rbx+18h]
0x1800060ec  lea     rcx, [rax-18h]
0x1800060f0  xor     eax, eax
0x1800060f2  mov     [rbx+10h], rcx
0x1800060f6  mov     [rcx], ax
0x1800060f9  cmp     dword ptr [rbx+18h], 1
0x1800060fd  jnz     short loc_180006106
0x1800060ff  lock inc cs:?g_cLibRef@@3JA; long g_cLibRef
0x180006106  mov     rax, [rbx+10h]
0x18000610a  test    rax, rax
0x18000610d  jz      short loc_180006168
0x18000610f  movups  xmm0, xmmword ptr [rdi]
0x180006112  movups  xmmword ptr [rax], xmm0
0x180006115  movsd   xmm1, qword ptr [rdi+10h]
0x18000611a  movsd   qword ptr [rax+10h], xmm1
0x18000611f  mov     [rdi+8], rax
0x180006123  xor     eax, eax
0x180006125  mov     word ptr [rdi], 4Ah ; 'J'
0x18000612a  mov     rbx, [rsp+28h+arg_0]
0x18000612f  add     rsp, 20h
0x180006133  pop     rdi
0x180006134  retn
0x180006135  mov     rdx, [rbx]
0x180006138  test    rdx, rdx
0x18000613b  jz      short loc_18000615B
0x18000613d  mov     rax, [rdx+4B0h]
0x180006144  mov     [rbx], rax
0x180006147  mov     rcx, [rbx+8]
0x18000614b  lea     rax, [rdx+4B0h]
0x180006152  mov     [rax], rcx
0x180006155  mov     [rbx+8], rdx
0x180006159  jmp     short loc_1800060E9
0x18000615b  call    ?PblkAlloc@GcBlockFactory@@QEAAPEAVGcBlock@@XZ; GcBlockFactory::PblkAlloc(void)
0x180006160  mov     rdx, rax
0x180006163  test    rax, rax
0x180006166  jnz     short loc_180006147
0x180006168  mov     rcx, rdi; this
0x18000616b  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180006170  mov     eax, 8007000Eh
0x180006175  jmp     short loc_18000612A
```
