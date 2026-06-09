# SecpIsDuplicateBinding(_SECP_DLL_BINDING *,int *)

- ea: `0x18000d3a8`
- end: `0x18000d415`
- name: `?SecpIsDuplicateBinding@@YAJPEAU_SECP_DLL_BINDING@@PEAH@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800070d0`

## callees

- `0x18000d3a8`
- `0x18000d420`
- `0x180016824`

## pseudocode

```c
__int64 __fastcall SecpIsDuplicateBinding(struct _SECP_DLL_BINDING *a1, int *a2)
{
  struct _UNICODE_STRING *v2; // rsi
  unsigned int v5; // edi

  v2 = (struct _UNICODE_STRING *)((char *)a1 + 16);
  v5 = 0;
  if ( !SecpFindDll((struct _UNICODE_STRING *)a1 + 1, 1) )
  {
    if ( !SecpFindDll(v2, 0) )
      goto LABEL_6;
    v5 = SecpResolveBindingPath(a1);
    if ( (v5 & 0x80000000) != 0 )
      return v5;
    if ( !SecpFindDll(v2, 1) )
    {
LABEL_6:
      *a2 = 0;
      return v5;
    }
  }
  *a2 = 1;
  return v5;
}

```

## disassembly

```asm
0x18000d3a8  push    rbx
0x18000d3aa  push    rbp
0x18000d3ab  push    rsi
0x18000d3ac  push    rdi
0x18000d3ad  sub     rsp, 28h
0x18000d3b1  lea     rsi, [rcx+10h]
0x18000d3b5  mov     rbx, rdx
0x18000d3b8  mov     rbp, rcx
0x18000d3bb  xor     edi, edi
0x18000d3bd  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000d3c0  lea     edx, [rdi+1]; int
0x18000d3c3  call    ?SecpFindDll@@YAPEAU_SECP_DLL_BINDING@@PEAU_UNICODE_STRING@@H@Z; SecpFindDll(_UNICODE_STRING *,int)
0x18000d3c8  test    rax, rax
0x18000d3cb  jz      short loc_18000D3D5
0x18000d3cd  mov     dword ptr [rbx], 1
0x18000d3d3  jmp     short loc_18000D40A
0x18000d3d5  xor     edx, edx; int
0x18000d3d7  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000d3da  call    ?SecpFindDll@@YAPEAU_SECP_DLL_BINDING@@PEAU_UNICODE_STRING@@H@Z; SecpFindDll(_UNICODE_STRING *,int)
0x18000d3df  test    rax, rax
0x18000d3e2  jz      short loc_18000D404
0x18000d3e4  mov     rcx, rbp; struct _SECP_DLL_BINDING *
0x18000d3e7  call    ?SecpResolveBindingPath@@YAJPEAU_SECP_DLL_BINDING@@@Z; SecpResolveBindingPath(_SECP_DLL_BINDING *)
0x18000d3ec  mov     edi, eax
0x18000d3ee  test    eax, eax
0x18000d3f0  js      short loc_18000D40A
0x18000d3f2  mov     edx, 1; int
0x18000d3f7  mov     rcx, rsi; struct _UNICODE_STRING *
0x18000d3fa  call    ?SecpFindDll@@YAPEAU_SECP_DLL_BINDING@@PEAU_UNICODE_STRING@@H@Z; SecpFindDll(_UNICODE_STRING *,int)
0x18000d3ff  test    rax, rax
0x18000d402  jnz     short loc_18000D3CD
0x18000d404  mov     dword ptr [rbx], 0
0x18000d40a  mov     eax, edi
0x18000d40c  add     rsp, 28h
0x18000d410  pop     rdi
0x18000d411  pop     rsi
0x18000d412  pop     rbp
0x18000d413  pop     rbx
0x18000d414  retn
```
