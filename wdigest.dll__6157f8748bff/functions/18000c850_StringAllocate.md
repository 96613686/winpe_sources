# StringAllocate

- ea: `0x18000c850`
- end: `0x18000c97c`
- name: `StringAllocate`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a50`
- `0x180007ca0`
- `0x18000ff20`
- `0x180018298`
- `0x18001b4b0`
- `0x18001e4b0`
- `0x180024328`
- `0x18002552c`
- `0x18002dc18`

## callees

- `0x18000c850`
- `0x180013304`
- `0x180032ec8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c92a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c92a`

## pseudocode

```c
__int64 __fastcall StringAllocate(__int64 a1, __int16 a2)
{
  unsigned __int16 v3; // bx
  bool v4; // zf
  void *v5; // rax
  HLOCAL v6; // rsi
  _QWORD *v7; // rcx
  __int64 result; // rax
  __int64 v9; // r9
  __int64 v10; // rdx

  if ( a2 == -1 || !a1 )
    return 3221225485LL;
  v3 = a2 + 1;
  v4 = g_NtDigestState == 1;
  *(_WORD *)a1 = 0;
  if ( v4 )
  {
    v5 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v3);
    v6 = v5;
    if ( v5 )
      memset_0(v5, 0, v3);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_8;
    v10 = 28;
    v9 = v3;
  }
  else
  {
    v6 = LocalAlloc(0x40u, v3);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_8;
    v9 = v3;
    v10 = 29;
  }
  WPP_SF_Lq(v7[2], v10, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v9, v6);
LABEL_8:
  *(_QWORD *)(a1 + 8) = v6;
  if ( v6 )
  {
    result = 0;
    *(_WORD *)(a1 + 2) = v3;
  }
  else
  {
    *(_WORD *)(a1 + 2) = 0;
    return 2148074240LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000c850  mov     [rsp+arg_10], rbx
0x18000c855  push    rdi
0x18000c856  sub     rsp, 30h
0x18000c85a  mov     eax, 0FFFEh
0x18000c85f  movzx   ebx, dx
0x18000c862  mov     rdi, rcx
0x18000c865  cmp     dx, ax
0x18000c868  ja      loc_18000C905
0x18000c86e  test    rcx, rcx
0x18000c871  jz      loc_18000C905
0x18000c877  xor     eax, eax
0x18000c879  mov     [rsp+38h+arg_8], rsi
0x18000c87e  inc     bx
0x18000c881  mov     [rsp+38h+arg_0], rbp
0x18000c886  cmp     cs:g_NtDigestState, 1
0x18000c88d  mov     [rcx], ax
0x18000c890  jnz     loc_18000C922
0x18000c896  mov     rax, cs:g_LsaFunctions
0x18000c89d  movzx   ebp, bx
0x18000c8a0  mov     ecx, ebp
0x18000c8a2  mov     rax, [rax+28h]
0x18000c8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8ab  mov     rsi, rax
0x18000c8ae  test    rax, rax
0x18000c8b1  jz      short loc_18000C8C1
0x18000c8b3  movzx   r8d, bx; Size
0x18000c8b7  xor     edx, edx; Val
0x18000c8b9  mov     rcx, rax; void *
0x18000c8bc  call    memset_0
0x18000c8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8c8  lea     rax, WPP_GLOBAL_Control
0x18000c8cf  cmp     rcx, rax
0x18000c8d2  jz      short loc_18000C8E1
0x18000c8d4  test    dword ptr [rcx+1Ch], 100h
0x18000c8db  jnz     loc_18000C972
0x18000c8e1  mov     rbp, [rsp+38h+arg_0]
0x18000c8e6  test    rsi, rsi
0x18000c8e9  mov     [rdi+8], rsi
0x18000c8ed  mov     rsi, [rsp+38h+arg_8]
0x18000c8f2  jz      short loc_18000C90C
0x18000c8f4  xor     eax, eax
0x18000c8f6  mov     [rdi+2], bx
0x18000c8fa  mov     rbx, [rsp+38h+arg_10]
0x18000c8ff  add     rsp, 30h
0x18000c903  pop     rdi
0x18000c904  retn
0x18000c905  mov     eax, 0C000000Dh
0x18000c90a  jmp     short loc_18000C8FA
0x18000c90c  mov     rbx, [rsp+38h+arg_10]
0x18000c911  xor     eax, eax
0x18000c913  mov     [rdi+2], ax
0x18000c917  mov     eax, 80090300h
0x18000c91c  add     rsp, 30h
0x18000c920  pop     rdi
0x18000c921  retn
0x18000c922  movzx   edx, bx; uBytes
0x18000c925  mov     ecx, 40h ; '@'; uFlags
0x18000c92a  call    cs:__imp_LocalAlloc
0x18000c930  mov     rsi, rax
0x18000c933  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c93a  lea     rax, WPP_GLOBAL_Control
0x18000c941  cmp     rcx, rax
0x18000c944  jz      short loc_18000C8E1
0x18000c946  test    dword ptr [rcx+1Ch], 100h
0x18000c94d  jz      short loc_18000C8E1
0x18000c94f  movzx   r9d, bx
0x18000c953  mov     edx, 1Dh
0x18000c958  mov     rcx, [rcx+10h]
0x18000c95c  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x18000c963  mov     [rsp+38h+var_18], rsi
0x18000c968  call    WPP_SF_Lq
0x18000c96d  jmp     loc_18000C8E1
0x18000c972  mov     edx, 1Ch
0x18000c977  mov     r9d, ebp
0x18000c97a  jmp     short loc_18000C958
```
