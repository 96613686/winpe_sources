# WinHvReflectChildAccessState

- ea: `0x140005220`
- end: `0x1400052a1`
- name: `WinHvReflectChildAccessState`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140002240`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## pseudocode

```c
__int64 __fastcall WinHvReflectChildAccessState(__int64 a1, unsigned __int8 a2)
{
  __int64 *v4; // r8
  _QWORD v6[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 *v7; // [rsp+70h] [rbp+8h] BYREF

  v7 = 0;
  memset(v6, 0, 0x40u);
  WinHvpSetupHypercall(&v7, 0, (__int64)v6);
  v4 = v7;
  *v7 = a1;
  *((_DWORD *)v4 + 2) ^= ((unsigned __int8)*((_DWORD *)v4 + 2) ^ a2) & 1;
  LODWORD(a1) = WinHvpSimplePoolHypercall_CallViaMacro(v6[0], 300);
  ((void (__fastcall *)(_QWORD))v6[7])(v6[0]);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x140005220  mov     [rsp+arg_8], rbx
0x140005225  push    rdi
0x140005226  sub     rsp, 60h
0x14000522a  movzx   edi, dl
0x14000522d  mov     rbx, rcx
0x140005230  xor     edx, edx; Val
0x140005232  mov     [rsp+68h+arg_0], 0
0x14000523b  lea     rcx, [rsp+68h+var_48]; void *
0x140005240  lea     r8d, [rdx+40h]; Size
0x140005244  call    memset
0x140005249  lea     r8, [rsp+68h+var_48]
0x14000524e  xor     edx, edx
0x140005250  lea     rcx, [rsp+68h+arg_0]
0x140005255  call    WinHvpSetupHypercall
0x14000525a  mov     r8, [rsp+68h+arg_0]
0x14000525f  mov     ecx, edi
0x140005261  mov     edx, 12Ch
0x140005266  mov     [r8], rbx
0x140005269  mov     eax, [r8+8]
0x14000526d  xor     ecx, eax
0x14000526f  and     ecx, 1
0x140005272  xor     ecx, eax
0x140005274  mov     [r8+8], ecx
0x140005278  mov     rcx, [rsp+68h+var_48]
0x14000527d  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140005282  mov     rcx, [rsp+68h+var_48]
0x140005287  mov     ebx, eax
0x140005289  mov     rax, [rsp+68h+var_10]
0x14000528e  call    _guard_dispatch_icall
0x140005293  mov     eax, ebx
0x140005295  mov     rbx, [rsp+68h+arg_8]
0x14000529a  add     rsp, 60h
0x14000529e  pop     rdi
0x14000529f  retn
```
