# WimCbQueryReparseData

- ea: `0x14003ee60`
- end: `0x14003eee5`
- name: `WimCbQueryReparseData`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path`

## callees

- `0x140022500`
- `0x14003ee60`

## pseudocode

```c
__int64 __fastcall WimCbQueryReparseData(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, char a5)
{
  __int64 v6; // rbx
  __int64 result; // rax
  int v9; // eax
  __int64 v10; // rdx

  v6 = a3;
  if ( *a4 >= 0x28u )
  {
    *(_OWORD *)a3 = 0;
    *(_OWORD *)(a3 + 16) = 0;
    *(_QWORD *)(a3 + 32) = 0;
    *(_OWORD *)(a3 + 16) = *(_OWORD *)(a2 + 4);
    v9 = *(_DWORD *)(a2 + 20);
    v10 = a3 + 4;
    *(_DWORD *)(a3 + 32) = v9;
    *(_DWORD *)a3 = 1;
    LOBYTE(a3) = a5;
    WimFSFGetOverlayFlags(*(_QWORD *)(a2 + 24), v10, a3);
    result = 0;
    *(_QWORD *)(v6 + 8) = *(_QWORD *)(*(_QWORD *)(a2 + 24) + 88LL);
  }
  else
  {
    result = 3221225507LL;
  }
  *a4 = 40;
  return result;
}

```

## disassembly

```asm
0x14003ee60  mov     [rsp+arg_0], rbx
0x14003ee65  mov     [rsp+arg_8], rsi
0x14003ee6a  push    rdi
0x14003ee6b  sub     rsp, 20h
0x14003ee6f  cmp     dword ptr [r9], 28h ; '('
0x14003ee73  mov     rdi, r9
0x14003ee76  mov     rbx, r8
0x14003ee79  mov     rsi, rdx
0x14003ee7c  jnb     short loc_14003EE85
0x14003ee7e  mov     eax, 0C0000023h
0x14003ee83  jmp     short loc_14003EECE
0x14003ee85  xorps   xmm0, xmm0
0x14003ee88  xor     eax, eax
0x14003ee8a  movups  xmmword ptr [r8], xmm0
0x14003ee8e  movups  xmmword ptr [r8+10h], xmm0
0x14003ee93  mov     [r8+20h], rax
0x14003ee97  movups  xmm0, xmmword ptr [rdx+4]
0x14003ee9b  movups  xmmword ptr [r8+10h], xmm0
0x14003eea0  mov     eax, [rdx+14h]
0x14003eea3  lea     rdx, [r8+4]
0x14003eea7  mov     [r8+20h], eax
0x14003eeab  mov     dword ptr [r8], 1
0x14003eeb2  mov     r8b, [rsp+28h+arg_20]
0x14003eeb7  mov     rcx, [rsi+18h]
0x14003eebb  call    WimFSFGetOverlayFlags
0x14003eec0  mov     rax, [rsi+18h]
0x14003eec4  mov     rcx, [rax+58h]
0x14003eec8  xor     eax, eax
0x14003eeca  mov     [rbx+8], rcx
0x14003eece  mov     rbx, [rsp+28h+arg_0]
0x14003eed3  mov     rsi, [rsp+28h+arg_8]
0x14003eed8  mov     dword ptr [rdi], 28h ; '('
0x14003eede  add     rsp, 20h
0x14003eee2  pop     rdi
0x14003eee3  retn
```
