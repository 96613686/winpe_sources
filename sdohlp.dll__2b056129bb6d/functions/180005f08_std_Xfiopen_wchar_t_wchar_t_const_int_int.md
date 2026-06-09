# std::_Xfiopen<wchar_t>(wchar_t const *,int,int)

- ea: `0x180005f08`
- end: `0x180005ff3`
- name: `??$_Xfiopen@_W@std@@YAPEAU_iobuf@@PEB_WHH@Z`
- size: `235`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005ffc`

## callees

- `0x180005f08`

## import_xrefs

- `msvcrt!_wfsopen` at `0x180005f95`
- `msvcrt!_wfsopen` at `0x180005fc4`
- `msvcrt!_wfsopen` at `0x180005f95`
- `msvcrt!_wfsopen` at `0x180005fc4`
- `msvcrt!fseek` at `0x180005fdf`
- `msvcrt!fseek` at `0x180005fdf`
- `msvcrt!fclose` at `0x180005fa3`
- `msvcrt!fclose` at `0x180005fa3`

## pseudocode

```c
FILE *__fastcall std::_Xfiopen<wchar_t>(wchar_t *FileName, int a2, int a3)
{
  int v3; // ebp
  int v4; // r9d
  int v7; // r8d
  int v8; // edx
  unsigned int v9; // edx
  int v10; // ecx
  __int64 v11; // rbx
  FILE *v12; // rax
  FILE *v13; // rcx
  FILE *v15; // rax
  FILE *v16; // rbx

  v3 = a2 & 4;
  v4 = a2 | 1;
  v7 = a2 & 0x80;
  if ( (a2 & 0x40) == 0 )
    v4 = a2;
  v8 = v4 | 2;
  if ( (v4 & 8) == 0 )
    v8 = v4;
  v9 = v8 & 0xFFFFFF3B;
  v10 = 0;
  do
  {
    if ( `std::_Xfiopen<wchar_t>'::`2'::valid[v10] == v9 )
      break;
    ++v10;
  }
  while ( `std::_Xfiopen<wchar_t>'::`2'::valid[v10] );
  v11 = v10;
  if ( !`std::_Xfiopen<wchar_t>'::`2'::valid[v10] )
    return 0;
  if ( v7 )
  {
    if ( (v9 & 0xA) != 0 )
    {
      v12 = _wfsopen(FileName, L"r", a3);
      if ( v12 )
      {
        v13 = v12;
LABEL_13:
        fclose(v13);
        return 0;
      }
    }
  }
  v15 = _wfsopen(FileName, (&Mode)[v11], a3);
  v16 = v15;
  if ( !v15 )
    return 0;
  if ( v3 && fseek(v15, 0, 2) )
  {
    v13 = v16;
    goto LABEL_13;
  }
  return v16;
}

```

## disassembly

```asm
0x180005f08  push    rbx
0x180005f0a  push    rbp
0x180005f0b  push    rsi
0x180005f0c  push    rdi
0x180005f0d  push    r14
0x180005f0f  sub     rsp, 20h
0x180005f13  mov     ebp, edx
0x180005f15  lea     r14, cs:180000000h
0x180005f1c  mov     r9d, edx
0x180005f1f  and     ebp, 4
0x180005f22  or      r9d, 1
0x180005f26  mov     edi, r8d
0x180005f29  mov     r8d, edx
0x180005f2c  mov     rsi, rcx
0x180005f2f  and     r8d, 80h
0x180005f36  test    dl, 40h
0x180005f39  cmovz   r9d, edx
0x180005f3d  mov     edx, r9d
0x180005f40  or      edx, 2
0x180005f43  test    r9b, 8
0x180005f47  cmovz   edx, r9d
0x180005f4b  and     edx, 0FFFFFF3Bh
0x180005f51  xor     ecx, ecx
0x180005f53  movsxd  rax, ecx
0x180005f56  cmp     ds:rva ?valid@?1???$_Xfiopen@_W@std@@YAPEAU_iobuf@@PEB_WHH@Z@4QBHB[r14+rax*4], edx; int const near * const `std::_Xfiopen<wchar_t>(wchar_t const *,int,int)'::`2'::valid ...
0x180005f5e  jz      short loc_180005F70
0x180005f60  inc     ecx
0x180005f62  movsxd  rax, ecx
0x180005f65  cmp     ds:rva ?valid@?1???$_Xfiopen@_W@std@@YAPEAU_iobuf@@PEB_WHH@Z@4QBHB[r14+rax*4], 0; int const near * const `std::_Xfiopen<wchar_t>(wchar_t const *,int,int)'::`2'::valid ...
0x180005f6e  jnz     short loc_180005F53
0x180005f70  movsxd  rbx, ecx
0x180005f73  cmp     ds:rva ?valid@?1???$_Xfiopen@_W@std@@YAPEAU_iobuf@@PEB_WHH@Z@4QBHB[r14+rbx*4], 0; int const near * const `std::_Xfiopen<wchar_t>(wchar_t const *,int,int)'::`2'::valid ...
0x180005f7c  jz      short loc_180005FA9
0x180005f7e  test    r8d, r8d
0x180005f81  jz      short loc_180005FB6
0x180005f83  test    dl, 0Ah
0x180005f86  jz      short loc_180005FB6
0x180005f88  mov     rdx, cs:Mode; Mode
0x180005f8f  mov     r8d, edi; ShFlag
0x180005f92  mov     rcx, rsi; FileName
0x180005f95  call    cs:__imp__wfsopen
0x180005f9b  test    rax, rax
0x180005f9e  jz      short loc_180005FB6
0x180005fa0  mov     rcx, rax; Stream
0x180005fa3  call    cs:__imp_fclose
0x180005fa9  xor     eax, eax
0x180005fab  add     rsp, 20h
0x180005faf  pop     r14
0x180005fb1  pop     rdi
0x180005fb2  pop     rsi
0x180005fb3  pop     rbp
0x180005fb4  pop     rbx
0x180005fb5  retn
0x180005fb6  mov     rdx, ds:rva Mode[r14+rbx*8]; Mode
0x180005fbe  mov     r8d, edi; ShFlag
0x180005fc1  mov     rcx, rsi; FileName
0x180005fc4  call    cs:__imp__wfsopen
0x180005fca  mov     rbx, rax
0x180005fcd  test    rax, rax
0x180005fd0  jz      short loc_180005FA9
0x180005fd2  test    ebp, ebp
0x180005fd4  jz      short loc_180005FEE
0x180005fd6  xor     edx, edx; Offset
0x180005fd8  mov     rcx, rax; Stream
0x180005fdb  lea     r8d, [rdx+2]; Origin
0x180005fdf  call    cs:__imp_fseek
0x180005fe5  test    eax, eax
0x180005fe7  jz      short loc_180005FEE
0x180005fe9  mov     rcx, rbx
0x180005fec  jmp     short loc_180005FA3
0x180005fee  mov     rax, rbx
0x180005ff1  jmp     short loc_180005FAB
```
