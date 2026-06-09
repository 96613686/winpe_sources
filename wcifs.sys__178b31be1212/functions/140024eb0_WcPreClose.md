# WcPreClose

- ea: `0x140024eb0`
- end: `0x140024f9b`
- name: `WcPreClose`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001500`
- `0x140001bc8`
- `0x140002264`
- `0x140024eb0`

## import_xrefs

- `FLTMGR!FltDeleteContext` at `0x140024f3d`
- `FLTMGR!FltDeleteContext` at `0x140024f3d`
- `FLTMGR!FltReleaseContext` at `0x140024f10`
- `FLTMGR!FltReleaseContext` at `0x140024f8a`
- `FLTMGR!FltReleaseContext` at `0x140024f10`
- `FLTMGR!FltReleaseContext` at `0x140024f8a`

## pseudocode

```c
__int64 __fastcall WcPreClose(__int64 a1, __int64 a2)
{
  struct _FILE_OBJECT *v3; // rdx
  struct _FLT_INSTANCE *v4; // rcx
  char ContextFileObject; // al
  _QWORD *v6; // rbx
  __int64 v8; // rcx
  PFLT_CONTEXT Context; // [rsp+38h] [rbp+10h] BYREF
  PFLT_CONTEXT v10; // [rsp+48h] [rbp+20h] BYREF

  v3 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  v4 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v10 = 0;
  ContextFileObject = WcGetContextFileObject(v4, v3, &Context, &v10);
  v6 = v10;
  if ( ContextFileObject && v10 )
  {
    if ( !WcIsPlaceHolderDirectory((__int64)Context, (__int64)v10) )
    {
      if ( (unsigned __int8)WcUsesSourceSectionObjectPointers(*(_QWORD *)(a2 + 32), v6) )
      {
        *(_QWORD *)(v8 + 40) = v6[6];
        _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v6[4] + 24LL));
        if ( byte_14000E680 )
          _InterlockedIncrement(*(volatile signed __int32 **)(*(_QWORD *)v6[4] + 32LL));
      }
    }
    if ( *((_BYTE *)v6 + 29) )
      FltDeleteContext(v6);
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( v6 )
    FltReleaseContext(v6);
  return 1;
}

```

## disassembly

```asm
0x140024eb0  mov     [rsp+arg_0], rbx
0x140024eb5  push    rsi
0x140024eb6  sub     rsp, 20h
0x140024eba  mov     rsi, rdx
0x140024ebd  lea     r9, [rsp+28h+arg_18]
0x140024ec2  mov     rdx, [rdx+20h]; FileObject
0x140024ec6  lea     r8, [rsp+28h+Context]
0x140024ecb  xor     eax, eax
0x140024ecd  mov     [rsp+28h+Context], rax
0x140024ed2  mov     rcx, [rsi+18h]; Instance
0x140024ed6  mov     [rsp+28h+arg_18], rax
0x140024edb  call    WcGetContextFileObject
0x140024ee0  mov     rbx, [rsp+28h+arg_18]
0x140024ee5  test    al, al
0x140024ee7  jnz     short loc_140024F1E
0x140024ee9  cmp     [rsp+28h+Context], 0
0x140024eef  jnz     short loc_140024F0B
0x140024ef1  test    rbx, rbx
0x140024ef4  jnz     loc_140024F87
0x140024efa  mov     rbx, [rsp+28h+arg_0]
0x140024eff  mov     eax, 1
0x140024f04  add     rsp, 20h
0x140024f08  pop     rsi
0x140024f09  retn
0x140024f0b  mov     rcx, [rsp+28h+Context]; Context
0x140024f10  call    cs:__imp_FltReleaseContext
0x140024f17  nop     dword ptr [rax+rax+00h]
0x140024f1c  jmp     short loc_140024EF1
0x140024f1e  test    rbx, rbx
0x140024f21  jz      short loc_140024EE9
0x140024f23  mov     rcx, [rsp+28h+Context]
0x140024f28  mov     rdx, rbx
0x140024f2b  call    WcIsPlaceHolderDirectory
0x140024f30  test    al, al
0x140024f32  jz      short loc_140024F4B
0x140024f34  cmp     byte ptr [rbx+1Dh], 0
0x140024f38  jz      short loc_140024EE9
0x140024f3a  mov     rcx, rbx; Context
0x140024f3d  call    cs:__imp_FltDeleteContext
0x140024f44  nop     dword ptr [rax+rax+00h]
0x140024f49  jmp     short loc_140024EE9
0x140024f4b  mov     rcx, [rsi+20h]
0x140024f4f  mov     rdx, rbx
0x140024f52  call    WcUsesSourceSectionObjectPointers
0x140024f57  test    al, al
0x140024f59  jz      short loc_140024F34
0x140024f5b  mov     rax, [rbx+30h]
0x140024f5f  mov     [rcx+28h], rax
0x140024f63  mov     rax, [rbx+20h]
0x140024f67  mov     rcx, [rax]
0x140024f6a  lock dec dword ptr [rcx+18h]
0x140024f6e  cmp     cs:byte_14000E680, 0
0x140024f75  jz      short loc_140024F34
0x140024f77  mov     rax, [rbx+20h]
0x140024f7b  mov     rdx, [rax]
0x140024f7e  mov     rax, [rdx+20h]
0x140024f82  lock inc dword ptr [rax]
0x140024f85  jmp     short loc_140024F34
0x140024f87  mov     rcx, rbx; Context
0x140024f8a  call    cs:__imp_FltReleaseContext
0x140024f91  nop     dword ptr [rax+rax+00h]
0x140024f96  jmp     loc_140024EFA
```
