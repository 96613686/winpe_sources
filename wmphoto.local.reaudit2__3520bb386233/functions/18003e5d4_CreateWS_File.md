# CreateWS_File

- ea: `0x18003e5d4`
- end: `0x18003e670`
- name: `CreateWS_File`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001024`

## callees

- `0x180031720`
- `0x18003e5d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18003e644`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18003e644`

## pseudocode

```c
__int64 __fastcall CreateWS_File(__int64 **a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // r8d
  __int64 *v6; // rbx
  __int64 v7; // rax

  v4 = WMPAlloc(a1, 104);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *a1;
    v6[6] = (__int64)CloseWS_File;
    v6[7] = (__int64)EOSWS_File;
    v6[8] = (__int64)&ReadWS_File;
    v6[9] = (__int64)WriteWS_File;
    v6[11] = (__int64)SetPosWS_File;
    v6[12] = (__int64)GetPosWS_File;
    v7 = _o_fopen(a2, "w+b", (unsigned int)v4);
    v5 = 0;
    *v6 = v7;
    if ( !v7 )
      return (unsigned int)-102;
  }
  return v5;
}

```

## disassembly

```asm
0x18003e5d4  mov     [rsp+arg_0], rbx
0x18003e5d9  push    rdi
0x18003e5da  sub     rsp, 20h
0x18003e5de  mov     rdi, rdx
0x18003e5e1  mov     rbx, rcx
0x18003e5e4  mov     edx, 68h ; 'h'
0x18003e5e9  call    WMPAlloc
0x18003e5ee  mov     r8d, eax
0x18003e5f1  test    eax, eax
0x18003e5f3  js      short loc_18003E661
0x18003e5f5  mov     rbx, [rbx]
0x18003e5f8  lea     rax, CloseWS_File
0x18003e5ff  lea     rdx, aWB; "w+b"
0x18003e606  mov     rcx, rdi
0x18003e609  mov     [rbx+30h], rax
0x18003e60d  lea     rax, EOSWS_File
0x18003e614  mov     [rbx+38h], rax
0x18003e618  lea     rax, ReadWS_File
0x18003e61f  mov     [rbx+40h], rax
0x18003e623  lea     rax, WriteWS_File
0x18003e62a  mov     [rbx+48h], rax
0x18003e62e  lea     rax, SetPosWS_File
0x18003e635  mov     [rbx+58h], rax
0x18003e639  lea     rax, GetPosWS_File
0x18003e640  mov     [rbx+60h], rax
0x18003e644  call    cs:__imp__o_fopen
0x18003e64b  nop     dword ptr [rax+rax+00h]
0x18003e650  xor     r8d, r8d
0x18003e653  mov     [rbx], rax
0x18003e656  test    rax, rax
0x18003e659  lea     ecx, [r8-66h]
0x18003e65d  cmovz   r8d, ecx
0x18003e661  mov     rbx, [rsp+28h+arg_0]
0x18003e666  mov     eax, r8d
0x18003e669  add     rsp, 20h
0x18003e66d  pop     rdi
0x18003e66e  retn
```
