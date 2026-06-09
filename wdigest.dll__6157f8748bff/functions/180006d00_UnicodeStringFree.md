# UnicodeStringFree

- ea: `0x180006d00`
- end: `0x180006dd7`
- name: `UnicodeStringFree`
- size: `215`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x180006260`
- `0x180008498`
- `0x1800085dc`
- `0x1800087f4`
- `0x180010510`
- `0x180011ce0`
- `0x180017efc`
- `0x180019090`
- `0x18001a4b4`
- `0x18001b4b0`
- `0x18001baac`
- `0x18001bf40`
- `0x18002272c`
- `0x18002357c`
- `0x180024000`
- `0x180024ea0`
- `0x180025a14`
- `0x1800272f0`
- `0x1800277a0`
- `0x180029c98`
- `0x18002af40`
- `0x18002c364`
- `0x180033020`

## callees

- `0x180006d00`
- `0x1800192a8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d8e`

## pseudocode

```c
__int64 __fastcall UnicodeStringFree(__int64 a1)
{
  void *v2; // rdi
  __int64 result; // rax

  if ( !a1 )
    return 0;
  v2 = *(void **)(a1 + 8);
  if ( !v2 )
    return 0;
  if ( g_NtDigestState == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)&g_LsaFunctions + 48LL))(v2);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v2);
    LocalFree(v2);
  }
  result = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180006d00  push    rbx
0x180006d02  sub     rsp, 20h
0x180006d06  mov     rbx, rcx
0x180006d09  test    rcx, rcx
0x180006d0c  jz      loc_180006DD3
0x180006d12  mov     [rsp+28h+arg_0], rdi
0x180006d17  mov     rdi, [rcx+8]
0x180006d1b  test    rdi, rdi
0x180006d1e  jz      short loc_180006D6B
0x180006d20  cmp     cs:g_NtDigestState, 1
0x180006d27  jnz     short loc_180006D78
0x180006d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d30  lea     rax, WPP_GLOBAL_Control
0x180006d37  cmp     rcx, rax
0x180006d3a  jz      short loc_180006D45
0x180006d3c  test    dword ptr [rcx+1Ch], 100h
0x180006d43  jnz     short loc_180006D96
0x180006d45  mov     rax, cs:g_LsaFunctions
0x180006d4c  mov     rcx, rdi
0x180006d4f  mov     rax, [rax+30h]
0x180006d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d58  mov     rdi, [rsp+28h+arg_0]
0x180006d5d  xor     eax, eax
0x180006d5f  mov     [rbx], eax
0x180006d61  mov     [rbx+8], rax
0x180006d65  add     rsp, 20h
0x180006d69  pop     rbx
0x180006d6a  retn
0x180006d6b  mov     rdi, [rsp+28h+arg_0]
0x180006d70  xor     eax, eax
0x180006d72  add     rsp, 20h
0x180006d76  pop     rbx
0x180006d77  retn
0x180006d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d7f  lea     rax, WPP_GLOBAL_Control
0x180006d86  cmp     rcx, rax
0x180006d89  jnz     short loc_180006DB0
0x180006d8b  mov     rcx, rdi; hMem
0x180006d8e  call    cs:__imp_LocalFree
0x180006d94  jmp     short loc_180006D58
0x180006d96  mov     rcx, [rcx+10h]
0x180006d9a  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180006da1  mov     edx, 1Eh
0x180006da6  mov     r9, rdi
0x180006da9  call    WPP_SF_q
0x180006dae  jmp     short loc_180006D45
0x180006db0  test    dword ptr [rcx+1Ch], 100h
0x180006db7  jz      short loc_180006D8B
0x180006db9  mov     rcx, [rcx+10h]
0x180006dbd  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180006dc4  mov     edx, 1Fh
0x180006dc9  mov     r9, rdi
0x180006dcc  call    WPP_SF_q
0x180006dd1  jmp     short loc_180006D8B
0x180006dd3  xor     eax, eax
0x180006dd5  jmp     short loc_180006D65
```
