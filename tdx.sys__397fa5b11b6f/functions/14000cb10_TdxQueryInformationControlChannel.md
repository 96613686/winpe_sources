# TdxQueryInformationControlChannel

- ea: `0x14000cb10`
- end: `0x14000cc69`
- name: `TdxQueryInformationControlChannel`
- size: `345`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005fe0`

## callees

- `0x14000cb10`
- `0x14000cc70`
- `0x14000ccfc`
- `0x1400184b0`
- `0x140018900`

## import_xrefs

- `NETIO!RtlCopyKernelBufferToMdl` at `0x14000cb83`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14000cc39`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14000cb83`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x14000cc39`

## pseudocode

```c
__int64 __fastcall TdxQueryInformationControlChannel(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  bool v10; // zf
  __int64 v12; // rdx
  _QWORD v13[2]; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v14[224]; // [rsp+40h] [rbp-108h] BYREF

  v13[0] = 0;
  v5 = TdxObjectHeaderToTransport();
  if ( !v5 )
    return 3221225486LL;
  v6 = *(_DWORD *)(a3 + 8);
  v7 = 0;
  if ( v6 == 2 )
  {
    v8 = *(_QWORD *)(a2 + 8);
    if ( v8 )
      RtlCopyKernelBufferToMdl(v5 + 112, v8, 0, 40, v13);
    v9 = v13[0];
    v10 = v13[0] == 40;
LABEL_6:
    *(_QWORD *)(a2 + 56) = v9;
    if ( !v10 )
      v7 = 9;
  }
  else
  {
    switch ( v6 )
    {
      case 1:
      case 6:
      case 7:
      case 8:
      case 9:
        v7 = -1073741637;
        break;
      case 5:
        memset(v14, 0, 0xD8u);
        v12 = *(_QWORD *)(a2 + 8);
        if ( v12 )
          RtlCopyKernelBufferToMdl(v14, v12, 0, 216, v13);
        v9 = v13[0];
        v10 = v13[0] == 216;
        goto LABEL_6;
      default:
        v7 = -1073741811;
        break;
    }
  }
  DbgTdxDereferenceTransport(v5, "minio\\netio\\session\\tdi\\channel.c", 215);
  return v7;
}

```

## disassembly

```asm
0x14000cb10  push    rbp
0x14000cb12  push    rsi
0x14000cb13  push    rdi
0x14000cb14  sub     rsp, 130h
0x14000cb1b  mov     rax, cs:__security_cookie
0x14000cb22  xor     rax, rsp
0x14000cb25  mov     [rsp+148h+var_28], rax
0x14000cb2d  mov     rbp, r8
0x14000cb30  mov     [rsp+148h+var_118], 0
0x14000cb39  mov     rsi, rdx
0x14000cb3c  call    TdxObjectHeaderToTransport
0x14000cb41  mov     rdi, rax
0x14000cb44  test    rax, rax
0x14000cb47  jz      loc_14000CBDF
0x14000cb4d  mov     eax, [rbp+8]
0x14000cb50  mov     [rsp+148h+arg_10], rbx
0x14000cb58  xor     ebx, ebx
0x14000cb5a  cmp     eax, 2
0x14000cb5d  jnz     loc_14000CBE6
0x14000cb63  mov     rdx, [rsi+8]
0x14000cb67  test    rdx, rdx
0x14000cb6a  jz      short loc_14000CB8F
0x14000cb6c  lea     rax, [rsp+148h+var_118]
0x14000cb71  mov     r9d, 28h ; '('
0x14000cb77  lea     rcx, [rdi+70h]
0x14000cb7b  mov     [rsp+148h+var_128], rax
0x14000cb80  xor     r8d, r8d
0x14000cb83  call    cs:__imp_RtlCopyKernelBufferToMdl
0x14000cb8a  nop     dword ptr [rax+rax+00h]
0x14000cb8f  mov     rax, [rsp+148h+var_118]
0x14000cb94  cmp     rax, 28h ; '('
0x14000cb98  mov     ecx, 9
0x14000cb9d  mov     [rsi+38h], rax
0x14000cba1  cmovnz  ebx, ecx
0x14000cba4  mov     r8d, 0D7h
0x14000cbaa  lea     rdx, aMinioNetioSess_3; "minio\\netio\\session\\tdi\\channel.c"
0x14000cbb1  mov     rcx, rdi
0x14000cbb4  call    DbgTdxDereferenceTransport
0x14000cbb9  mov     eax, ebx
0x14000cbbb  mov     rbx, [rsp+148h+arg_10]
0x14000cbc3  mov     rcx, [rsp+148h+var_28]
0x14000cbcb  xor     rcx, rsp; StackCookie
0x14000cbce  call    __security_check_cookie
0x14000cbd3  add     rsp, 130h
0x14000cbda  pop     rdi
0x14000cbdb  pop     rsi
0x14000cbdc  pop     rbp
0x14000cbdd  retn
0x14000cbdf  mov     eax, 0C000000Eh
0x14000cbe4  jmp     short loc_14000CBC3
0x14000cbe6  dec     eax; switch 9 cases
0x14000cbe8  cmp     eax, 8
0x14000cbeb  ja      short def_14000CC00; jumptable 000000014000CC00 default case, cases 2-4
0x14000cbed  lea     rdx, cs:140000000h
0x14000cbf4  cdqe
0x14000cbf6  mov     ecx, ds:(jpt_14000CC00 - 140000000h)[rdx+rax*4]
0x14000cbfd  add     rcx, rdx
0x14000cc00  jmp     rcx; switch jump
0x14000cc06  xor     edx, edx; jumptable 000000014000CC00 case 5
0x14000cc08  lea     rcx, [rsp+148h+var_108]; void *
0x14000cc0d  mov     r8d, 0D8h; Size
0x14000cc13  call    memset
0x14000cc18  mov     rdx, [rsi+8]
0x14000cc1c  test    rdx, rdx
0x14000cc1f  jz      short loc_14000CC45
0x14000cc21  lea     rax, [rsp+148h+var_118]
0x14000cc26  mov     r9d, 0D8h
0x14000cc2c  xor     r8d, r8d
0x14000cc2f  mov     [rsp+148h+var_128], rax
0x14000cc34  lea     rcx, [rsp+148h+var_108]
0x14000cc39  call    cs:__imp_RtlCopyKernelBufferToMdl
0x14000cc40  nop     dword ptr [rax+rax+00h]
0x14000cc45  mov     rax, [rsp+148h+var_118]
0x14000cc4a  cmp     rax, 0D8h
0x14000cc50  jmp     loc_14000CB98
0x14000cc55  mov     ebx, 0C00000BBh; jumptable 000000014000CC00 cases 1,6-9
0x14000cc5a  jmp     loc_14000CBA4
0x14000cc5f  mov     ebx, 0C000000Dh; jumptable 000000014000CC00 default case, cases 2-4
0x14000cc64  jmp     loc_14000CBA4
```
