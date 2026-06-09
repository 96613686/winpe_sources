# CreateWS_File

- ea: `0x18003de50`
- end: `0x18003dee5`
- name: `CreateWS_File`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001024`

## callees

- `0x1800313c4`
- `0x18003de50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18003dec0`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18003dec0`

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
0x18003de50  mov     [rsp+arg_0], rbx
0x18003de55  push    rdi
0x18003de56  sub     rsp, 20h
0x18003de5a  mov     rdi, rdx
0x18003de5d  mov     rbx, rcx
0x18003de60  mov     edx, 68h ; 'h'
0x18003de65  call    WMPAlloc
0x18003de6a  mov     r8d, eax
0x18003de6d  test    eax, eax
0x18003de6f  js      short loc_18003DED7
0x18003de71  mov     rbx, [rbx]
0x18003de74  lea     rax, CloseWS_File
0x18003de7b  lea     rdx, aWB; "w+b"
0x18003de82  mov     rcx, rdi
0x18003de85  mov     [rbx+30h], rax
0x18003de89  lea     rax, EOSWS_File
0x18003de90  mov     [rbx+38h], rax
0x18003de94  lea     rax, ReadWS_File
0x18003de9b  mov     [rbx+40h], rax
0x18003de9f  lea     rax, WriteWS_File
0x18003dea6  mov     [rbx+48h], rax
0x18003deaa  lea     rax, SetPosWS_File
0x18003deb1  mov     [rbx+58h], rax
0x18003deb5  lea     rax, GetPosWS_File
0x18003debc  mov     [rbx+60h], rax
0x18003dec0  call    cs:__imp__o_fopen
0x18003dec6  xor     r8d, r8d
0x18003dec9  mov     [rbx], rax
0x18003decc  test    rax, rax
0x18003decf  lea     ecx, [r8-66h]
0x18003ded3  cmovz   r8d, ecx
0x18003ded7  mov     rbx, [rsp+28h+arg_0]
0x18003dedc  mov     eax, r8d
0x18003dedf  add     rsp, 20h
0x18003dee3  pop     rdi
0x18003dee4  retn
```
