# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x18006bc20`
- end: `0x18006bccb`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800054fc`
- `0x18006bc20`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18006bc3d`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18006bc3d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18006bcaf`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18006bcaf`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, __int64 a3)
{
  __int64 v3; // rbx
  char *v4; // rsi
  void *v8; // r9
  int v9; // ecx
  size_t v10; // r15
  __int64 v11; // r9

  v3 = a3;
  v4 = a2;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = **(void ***)(a1 + 64);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 88);
  else
    v9 = 0;
  if ( a3 > 0 )
  {
    if ( v9 > 0 )
    {
      v10 = v9;
      if ( a3 < v9 )
        v10 = a3;
      memcpy_0(v8, a2, v10);
      v3 -= v10;
      **(_DWORD **)(a1 + 88) -= v10;
      **(_QWORD **)(a1 + 64) += (int)v10;
      if ( v3 <= 0 )
        return a3 - v3;
      v4 += v10;
    }
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v3 -= _o_fwrite(v4, 1, v3, v11);
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x18006bc20  push    rbx
0x18006bc22  push    rbp
0x18006bc23  push    rsi
0x18006bc24  push    rdi
0x18006bc25  push    r14
0x18006bc27  push    r15
0x18006bc29  sub     rsp, 28h
0x18006bc2d  cmp     qword ptr [rcx+68h], 0
0x18006bc32  mov     rbx, r8
0x18006bc35  mov     rsi, rdx
0x18006bc38  mov     rdi, rcx
0x18006bc3b  jz      short loc_18006BC45
0x18006bc3d  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x18006bc43  jmp     short loc_18006BCBE
0x18006bc45  mov     rax, [rcx+40h]
0x18006bc49  mov     rbp, rbx
0x18006bc4c  mov     r9, [rax]
0x18006bc4f  test    r9, r9
0x18006bc52  jz      short loc_18006BC5C
0x18006bc54  mov     rax, [rcx+58h]
0x18006bc58  mov     ecx, [rax]
0x18006bc5a  jmp     short loc_18006BC5E
0x18006bc5c  xor     ecx, ecx
0x18006bc5e  test    rbx, rbx
0x18006bc61  jle     short loc_18006BCB8
0x18006bc63  test    ecx, ecx
0x18006bc65  jle     short loc_18006BC98
0x18006bc67  movsxd  r15, ecx
0x18006bc6a  mov     rcx, r9; void *
0x18006bc6d  cmp     rbx, r15
0x18006bc70  cmovl   r15, rbx
0x18006bc74  mov     r8, r15; Size
0x18006bc77  call    memcpy_0
0x18006bc7c  mov     rax, [rdi+58h]
0x18006bc80  sub     rbx, r15
0x18006bc83  sub     [rax], r15d
0x18006bc86  mov     rcx, [rdi+40h]
0x18006bc8a  movsxd  rax, r15d
0x18006bc8d  add     [rcx], rax
0x18006bc90  test    rbx, rbx
0x18006bc93  jle     short loc_18006BCB8
0x18006bc95  add     rsi, r15
0x18006bc98  mov     r9, [rdi+80h]
0x18006bc9f  test    r9, r9
0x18006bca2  jz      short loc_18006BCB8
0x18006bca4  mov     r8, rbx
0x18006bca7  mov     edx, 1
0x18006bcac  mov     rcx, rsi
0x18006bcaf  call    cs:__imp__o_fwrite
0x18006bcb5  sub     rbx, rax
0x18006bcb8  sub     rbp, rbx
0x18006bcbb  mov     rax, rbp
0x18006bcbe  add     rsp, 28h
0x18006bcc2  pop     r15
0x18006bcc4  pop     r14
0x18006bcc6  pop     rdi
0x18006bcc7  pop     rsi
0x18006bcc8  pop     rbp
0x18006bcc9  pop     rbx
0x18006bcca  retn
```
