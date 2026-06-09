# CASFMetaDataObjectBase::WriteMetaRecordDataWithData(CASFMetaDataObjectBase::METADATA_REC *,uchar *,ulong *)

- ea: `0x180026500`
- end: `0x180026602`
- name: `?WriteMetaRecordDataWithData@CASFMetaDataObjectBase@@IEAAXPEAUMETADATA_REC@1@PEAEPEAK@Z`
- size: `258`
- prototype: `void __fastcall(CASFMetaDataObjectBase *__hidden this, struct CASFMetaDataObjectBase::METADATA_REC *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e2b0`

## callees

- `0x180026500`
- `0x18003f2a0`

## pseudocode

```c
void __fastcall CASFMetaDataObjectBase::WriteMetaRecordDataWithData(
        CASFMetaDataObjectBase *this,
        struct CASFMetaDataObjectBase::METADATA_REC *a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  __int64 v4; // rcx
  __int64 v6; // rbp
  unsigned __int16 v8; // bp
  unsigned __int8 *v9; // rdi
  int v10; // eax
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned __int8 *v13; // rdi

  v4 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v6) );
  *(_WORD *)a3 = *(_WORD *)a2;
  v8 = 2 * (v6 + 1);
  *((_WORD *)a3 + 1) = *((_WORD *)a2 + 1);
  *((_WORD *)a3 + 2) = v8;
  *((_WORD *)a3 + 3) = *((_WORD *)a2 + 2);
  if ( ((*((_DWORD *)a2 + 1) - 1) & 0xFFFF7FFF) != 0 )
  {
    v9 = a3 + 12;
    *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 4);
    memcpy_0(a3 + 12, *((const void **)a2 + 1), v8);
    memcpy_0(&v9[v8], *((const void **)a2 + 3), *((unsigned int *)a2 + 4));
    v10 = *((_DWORD *)a2 + 4) + v8;
  }
  else
  {
    v11 = *((_QWORD *)a2 + 3);
    if ( v11 )
    {
      do
        ++v4;
      while ( *(_WORD *)(v11 + 2 * v4) );
      v12 = 2 * v4 + 2;
    }
    else
    {
      v12 = *((unsigned __int16 *)a2 + 8);
    }
    v13 = a3 + 12;
    *((_DWORD *)a3 + 2) = v12;
    memcpy_0(a3 + 12, *((const void **)a2 + 1), v8);
    memcpy_0(&v13[v8], *((const void **)a2 + 3), v12);
    v10 = v12 + v8;
  }
  *a4 = v10 + 12;
}

```

## disassembly

```asm
0x180026500  mov     [rsp+arg_0], rbx
0x180026505  push    rbp
0x180026506  push    rsi
0x180026507  push    rdi
0x180026508  push    r14
0x18002650a  push    r15
0x18002650c  sub     rsp, 20h
0x180026510  mov     rax, [rdx+8]
0x180026514  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026518  mov     r15, r9
0x18002651b  mov     rbp, rcx
0x18002651e  xor     r9d, r9d
0x180026521  mov     rsi, rdx
0x180026524  inc     rbp
0x180026527  cmp     [rax+rbp*2], r9w
0x18002652c  jnz     short loc_180026524
0x18002652e  movzx   eax, word ptr [rsi]
0x180026531  mov     edx, 1
0x180026536  mov     [r8], ax
0x18002653a  add     bp, dx
0x18002653d  movzx   eax, word ptr [rsi+2]
0x180026541  add     bp, bp
0x180026544  mov     [r8+2], ax
0x180026549  mov     [r8+4], bp
0x18002654e  movzx   eax, word ptr [rsi+4]
0x180026552  mov     [r8+6], ax
0x180026557  mov     eax, [rsi+4]
0x18002655a  sub     eax, edx
0x18002655c  test    eax, 0FFFF7FFFh
0x180026561  jz      short loc_180026599
0x180026563  mov     eax, [rsi+10h]
0x180026566  lea     rdi, [r8+0Ch]
0x18002656a  mov     [r8+8], eax
0x18002656e  mov     rcx, rdi; void *
0x180026571  mov     rdx, [rsi+8]; Src
0x180026575  movzx   ebx, bp
0x180026578  mov     r8d, ebx; Size
0x18002657b  call    memcpy_0
0x180026580  mov     r8d, [rsi+10h]; Size
0x180026584  lea     rcx, [rbx+rdi]; void *
0x180026588  mov     rdx, [rsi+18h]; Src
0x18002658c  call    memcpy_0
0x180026591  movzx   eax, bp
0x180026594  add     eax, [rsi+10h]
0x180026597  jmp     short loc_1800265EB
0x180026599  mov     rax, [rsi+18h]
0x18002659d  test    rax, rax
0x1800265a0  jz      short loc_1800265B6
0x1800265a2  inc     rcx
0x1800265a5  cmp     [rax+rcx*2], r9w
0x1800265aa  jnz     short loc_1800265A2
0x1800265ac  lea     r14d, ds:2[rcx*2]
0x1800265b4  jmp     short loc_1800265BB
0x1800265b6  movzx   r14d, word ptr [rsi+10h]
0x1800265bb  lea     rdi, [r8+0Ch]
0x1800265bf  mov     [r8+8], r14d
0x1800265c3  mov     rdx, [rsi+8]; Src
0x1800265c7  mov     rcx, rdi; void *
0x1800265ca  movzx   ebx, bp
0x1800265cd  mov     r8d, ebx; Size
0x1800265d0  call    memcpy_0
0x1800265d5  mov     rdx, [rsi+18h]; Src
0x1800265d9  lea     rcx, [rbx+rdi]; void *
0x1800265dd  mov     r8d, r14d; Size
0x1800265e0  call    memcpy_0
0x1800265e5  movzx   eax, bp
0x1800265e8  add     eax, r14d
0x1800265eb  add     eax, 0Ch
0x1800265ee  mov     [r15], eax
0x1800265f1  mov     rbx, [rsp+48h+arg_0]
0x1800265f6  add     rsp, 20h
0x1800265fa  pop     r15
0x1800265fc  pop     r14
0x1800265fe  pop     rdi
0x1800265ff  pop     rsi
0x180026600  pop     rbp
0x180026601  retn
```
