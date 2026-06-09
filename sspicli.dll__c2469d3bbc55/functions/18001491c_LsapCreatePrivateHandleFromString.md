# LsapCreatePrivateHandleFromString

- ea: `0x18001491c`
- end: `0x180014978`
- name: `LsapCreatePrivateHandleFromString`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016f78`

## callees

- `0x18001491c`
- `0x180016afc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014936`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014936`

## pseudocode

```c
__int64 __fastcall LsapCreatePrivateHandleFromString(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // ebx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = a1;
  v3 = LocalAlloc(0x40u, 0x38u);
  v6 = 0;
  v8 = v3;
  if ( v3 )
  {
    v3[2] = 0;
    *(_DWORD *)v3 = 1431128404;
  }
  else
  {
    v6 = -1073741801;
    LsapFreePrivateHandle(&v8, v4, v5);
    v3 = v8;
  }
  *a2 = v3;
  return v6;
}

```

## disassembly

```asm
0x18001491c  mov     [rsp+arg_8], rbx
0x180014921  mov     [rsp+arg_0], rcx
0x180014926  push    rdi
0x180014927  sub     rsp, 20h
0x18001492b  mov     rdi, rdx
0x18001492e  mov     edx, 38h ; '8'; uBytes
0x180014933  lea     ecx, [rdx+8]; uFlags
0x180014936  call    cs:__imp_LocalAlloc
0x18001493c  xor     ebx, ebx
0x18001493e  mov     [rsp+28h+arg_0], rax
0x180014943  test    rax, rax
0x180014946  jnz     short loc_18001495E
0x180014948  mov     ebx, 0C0000017h
0x18001494d  lea     rcx, [rsp+28h+arg_0]
0x180014952  call    LsapFreePrivateHandle
0x180014957  mov     rax, [rsp+28h+arg_0]
0x18001495c  jmp     short loc_180014968
0x18001495e  mov     [rax+10h], rbx
0x180014962  mov     dword ptr [rax], 554D4954h
0x180014968  mov     [rdi], rax
0x18001496b  mov     eax, ebx
0x18001496d  mov     rbx, [rsp+28h+arg_8]
0x180014972  add     rsp, 20h
0x180014976  pop     rdi
0x180014977  retn
```
