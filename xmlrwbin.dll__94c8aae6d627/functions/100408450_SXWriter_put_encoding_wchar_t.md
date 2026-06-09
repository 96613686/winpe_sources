# SXWriter::put_encoding(wchar_t *)

- ea: `0x100408450`
- end: `0x1004084c3`
- name: `?put_encoding@SXWriter@@UEAAJPEA_W@Z`
- size: `115`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100401350`
- `0x100408450`
- `0x1004087e0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::put_encoding(SXWriter *this, wchar_t *a2)
{
  __int64 v3; // r8
  wchar_t v4; // ax

  v3 = 0;
  do
  {
    v4 = a2[v3++];
    if ( v4 != aUtf16[v3 - 1] )
    {
      MXRRaiseException(-2147024809);
      __debugbreak();
      JUMPOUT(0x1004084C3LL);
    }
  }
  while ( v3 != 7 );
  SXWriter::commitStream((SXWriter *)((char *)this - 16));
  *((_BYTE *)this + 235) = 0;
  *((_QWORD *)this + 36) = (char *)this + 337;
  return 0;
}

```

## disassembly

```asm
0x100408450  mov     [rsp+arg_0], rbx
0x100408455  push    rdi
0x100408456  sub     rsp, 40h
0x10040845a  mov     rbx, rcx
0x10040845d  xor     edi, edi
0x10040845f  mov     r8d, edi
0x100408462  lea     rcx, aUtf16; "UTF-16"
0x100408469  nop     dword ptr [rax+00000000h]
0x100408470  movzx   eax, word ptr [rdx+r8*2]
0x100408475  inc     r8
0x100408478  cmp     ax, [rcx+r8*2-2]
0x10040847e  jnz     short loc_1004084B7
0x100408480  cmp     r8, 7
0x100408484  jnz     short loc_100408470
0x100408486  lea     rcx, [rbx-10h]; this
0x10040848a  call    ?commitStream@SXWriter@@IEAAXXZ; SXWriter::commitStream(void)
0x10040848f  mov     byte ptr [rbx+0EBh], 0
0x100408496  lea     rax, [rbx+151h]
0x10040849d  mov     [rbx+120h], rax
0x1004084a4  jmp     short loc_1004084AA
0x1004084a6  mov     edi, [rsp+48h+var_28]
0x1004084aa  mov     eax, edi
0x1004084ac  mov     rbx, [rsp+48h+arg_0]
0x1004084b1  add     rsp, 40h
0x1004084b5  pop     rdi
0x1004084b6  retn
0x1004084b7  mov     ecx, 80070057h; int
0x1004084bc  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004084c1  nop
0x1004084c2  int     3; Trap to Debugger
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
