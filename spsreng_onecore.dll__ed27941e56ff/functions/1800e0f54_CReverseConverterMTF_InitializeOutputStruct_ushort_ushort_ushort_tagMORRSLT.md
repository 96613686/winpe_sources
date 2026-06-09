# CReverseConverterMTF::InitializeOutputStruct(ushort,ushort,ushort,tagMORRSLT * *)

- ea: `0x1800e0f54`
- end: `0x1800e1085`
- name: `?InitializeOutputStruct@CReverseConverterMTF@@CAJGGGPEAPEAUtagMORRSLT@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(__int16, __int16, unsigned __int16, struct tagMORRSLT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e08e4`

## callees

- `0x1800040b8`
- `0x1800e0f54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e0ff4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e0ff4`

## pseudocode

```c
__int64 __fastcall CReverseConverterMTF::InitializeOutputStruct(
        __int16 a1,
        __int16 a2,
        unsigned __int16 a3,
        struct tagMORRSLT **a4)
{
  int v4; // r12d
  unsigned int v6; // edi
  unsigned int v8; // esi
  unsigned __int16 v9; // dx
  __int64 v10; // rcx
  __int16 v11; // ax
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  _WORD v22[8]; // [rsp+28h] [rbp-30h]
  _WORD v23[16]; // [rsp+38h] [rbp-20h]

  v4 = a3;
  v22[3] = 2 * a1;
  v22[2] = 2 * a2;
  v6 = 76;
  v22[4] = 2 * a2;
  v22[0] = 2 * a1 + 2;
  v22[1] = 2 * a2 + 2;
  v8 = 0;
  v22[5] = 24 * a3;
  v9 = 0;
  v10 = 0;
  do
  {
    v6 += (unsigned __int16)v22[v10];
    if ( v9 )
      v11 = v22[v10 - 1] + v22[v10 + 7];
    else
      v11 = 0;
    v23[v10] = v11;
    ++v9;
    ++v10;
  }
  while ( v9 < 6u );
  v12 = CoTaskMemAlloc(v6);
  v13 = v12;
  if ( v12 )
  {
    memset_0(v12, 0, v6);
    v14 = v23[3];
    *(_QWORD *)((char *)v13 + 4) = (char *)v13 + v23[0] + 76;
    v15 = (__int64)v13 + v23[1] + 76;
    v13[4] = (char *)v13 + v14 + 76;
    v16 = v23[4];
    *(_QWORD *)((char *)v13 + 14) = v15;
    *((_WORD *)v13 + 11) = a2;
    v17 = v23[2];
    v13[5] = (char *)v13 + v16 + 76;
    v18 = (__int64)v13 + v23[5] + 76;
    *(_DWORD *)v13 = v6;
    v13[7] = v18;
    *((_WORD *)v13 + 6) = a1;
    v13[3] = (char *)v13 + v17 + 76;
    *((_DWORD *)v13 + 16) = v4;
  }
  else
  {
    v8 = -2147024882;
  }
  *a4 = (struct tagMORRSLT *)v13;
  return v8;
}

```

## disassembly

```asm
0x1800e0f54  push    rbp
0x1800e0f56  push    rbx
0x1800e0f57  push    rsi
0x1800e0f58  push    rdi
0x1800e0f59  push    r12
0x1800e0f5b  push    r13
0x1800e0f5d  push    r14
0x1800e0f5f  push    r15
0x1800e0f61  mov     rbp, rsp
0x1800e0f64  sub     rsp, 58h
0x1800e0f68  movzx   r10d, cx
0x1800e0f6c  movzx   r12d, r8w
0x1800e0f70  movzx   r13d, cx
0x1800e0f74  mov     [rbp+var_38], dx
0x1800e0f78  movzx   ecx, dx
0x1800e0f7b  add     r10w, r10w
0x1800e0f7f  add     cx, cx
0x1800e0f82  mov     [rbp+var_2A], r10w
0x1800e0f87  mov     [rbp+var_2C], cx
0x1800e0f8b  mov     edi, 4Ch ; 'L'
0x1800e0f90  mov     [rbp+var_28], cx
0x1800e0f94  mov     r15, r9
0x1800e0f97  lea     eax, [r10+2]
0x1800e0f9b  mov     [rbp+var_30], ax
0x1800e0f9f  lea     eax, [rcx+2]
0x1800e0fa2  mov     [rbp+var_2E], ax
0x1800e0fa6  lea     r8d, [rdi-4Bh]
0x1800e0faa  movzx   eax, r12w
0x1800e0fae  add     ax, ax
0x1800e0fb1  lea     ecx, [rax+r12]
0x1800e0fb5  shl     cx, 3
0x1800e0fb9  xor     esi, esi
0x1800e0fbb  mov     [rbp+var_26], cx
0x1800e0fbf  mov     edx, esi
0x1800e0fc1  mov     ecx, esi
0x1800e0fc3  movzx   eax, [rbp+rcx*2+var_30]
0x1800e0fc8  add     edi, eax
0x1800e0fca  test    dx, dx
0x1800e0fcd  jnz     short loc_1800E0FD3
0x1800e0fcf  mov     eax, esi
0x1800e0fd1  jmp     short loc_1800E0FDD
0x1800e0fd3  movzx   eax, [rbp+rcx*2+var_22]
0x1800e0fd8  add     ax, [rbp+rcx*2+var_32]
0x1800e0fdd  mov     [rbp+rcx*2+var_20], ax
0x1800e0fe2  add     dx, r8w
0x1800e0fe6  add     rcx, r8
0x1800e0fe9  cmp     dx, 6
0x1800e0fed  jb      short loc_1800E0FC3
0x1800e0fef  mov     ecx, edi; cb
0x1800e0ff1  mov     r14d, edi
0x1800e0ff4  call    cs:__imp_CoTaskMemAlloc
0x1800e0ffa  mov     rbx, rax
0x1800e0ffd  test    rax, rax
0x1800e1000  jnz     short loc_1800E1009
0x1800e1002  mov     esi, 8007000Eh
0x1800e1007  jmp     short loc_1800E106F
0x1800e1009  mov     r8, r14; Size
0x1800e100c  xor     edx, edx; Val
0x1800e100e  mov     rcx, rbx; void *
0x1800e1011  call    memset_0
0x1800e1016  movzx   eax, [rbp+var_20]
0x1800e101a  lea     rdx, [rbx+4Ch]
0x1800e101e  movzx   ecx, [rbp+var_1A]
0x1800e1022  add     rax, rdx
0x1800e1025  mov     [rbx+4], rax
0x1800e1029  add     rcx, rdx
0x1800e102c  movzx   eax, [rbp+var_1E]
0x1800e1030  add     rax, rdx
0x1800e1033  mov     [rbx+20h], rcx
0x1800e1037  movzx   ecx, [rbp+var_18]
0x1800e103b  mov     [rbx+0Eh], rax
0x1800e103f  add     rcx, rdx
0x1800e1042  movzx   eax, [rbp+var_38]
0x1800e1046  mov     [rbx+16h], ax
0x1800e104a  movzx   eax, [rbp+var_1C]
0x1800e104e  mov     [rbx+28h], rcx
0x1800e1052  add     rax, rdx
0x1800e1055  movzx   ecx, [rbp+var_16]
0x1800e1059  add     rcx, rdx
0x1800e105c  mov     [rbx], edi
0x1800e105e  mov     [rbx+38h], rcx
0x1800e1062  mov     [rbx+0Ch], r13w
0x1800e1067  mov     [rbx+18h], rax
0x1800e106b  mov     [rbx+40h], r12d
0x1800e106f  mov     [r15], rbx
0x1800e1072  mov     eax, esi
0x1800e1074  add     rsp, 58h
0x1800e1078  pop     r15
0x1800e107a  pop     r14
0x1800e107c  pop     r13
0x1800e107e  pop     r12
0x1800e1080  pop     rdi
0x1800e1081  pop     rsi
0x1800e1082  pop     rbx
0x1800e1083  pop     rbp
0x1800e1084  retn
```
