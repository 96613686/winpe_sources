# UdfCreateIrpContext

- ea: `0x14004ccb0`
- end: `0x14004cdec`
- name: `UdfCreateIrpContext`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400094c0`

## callees

- `0x14004ccb0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14004cdbd`
- `ntoskrnl!ExRaiseStatus` at `0x14004cdbd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ccf4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004ccf4`

## pseudocode

```c
_OWORD *__fastcall UdfCreateIrpContext(__int64 a1, char a2)
{
  char *v2; // rbx
  struct _DEVICE_OBJECT *v5; // rax
  char v6; // si
  __int64 *v7; // r14
  _OWORD *result; // rax
  __int64 v9; // rdx
  int v10; // ecx
  char v11; // al

  v2 = *(char **)(a1 + 184);
  v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)v2 + 5);
  if ( v5 == qword_140025B10 || v5 == DeviceObject )
  {
    v7 = (__int64 *)(v2 + 48);
    v6 = 1;
    if ( *((_QWORD *)v2 + 6) )
    {
      v11 = *v2;
      if ( *v2 )
      {
        if ( v11 != 18 && v11 != 2 )
          ExRaiseStatus(-1073741808);
      }
    }
  }
  else
  {
    v6 = 0;
    v7 = (__int64 *)(v2 + 48);
  }
  result = ExAllocateFromNPagedLookasideList(&UdfIrpContextLookasideList);
  *result = 0;
  result[1] = 0;
  result[2] = 0;
  result[3] = 0;
  result[4] = 0;
  result[5] = 0;
  *((_QWORD *)result + 12) = 0;
  *(_DWORD *)result = 6818103;
  *((_QWORD *)result + 1) = a1;
  v9 = *v7;
  if ( *v7 )
  {
    *((_QWORD *)result + 4) = *(_QWORD *)(v9 + 8);
    if ( (*(_DWORD *)(v9 + 80) & 0x10) != 0 || *v2 == 4 && (*(_DWORD *)(a1 + 16) & 1) != 0 && (v2[2] & 4) != 0 )
      *((_DWORD *)result + 7) |= 0x20000u;
  }
  if ( !v6 )
    *((_QWORD *)result + 2) = *((_QWORD *)v2 + 5) + 368LL;
  *((_BYTE *)result + 56) = *v2;
  *((_BYTE *)result + 57) = v2[1];
  v10 = 4;
  if ( !a2 )
    v10 = 8;
  *((_DWORD *)result + 7) |= v10;
  return result;
}

```

## disassembly

```asm
0x14004ccb0  push    rbx
0x14004ccb2  push    rbp
0x14004ccb3  push    rsi
0x14004ccb4  push    rdi
0x14004ccb5  push    r14
0x14004ccb7  sub     rsp, 20h
0x14004ccbb  mov     rbx, [rcx+0B8h]
0x14004ccc2  movzx   ebp, dl
0x14004ccc5  mov     rdi, rcx
0x14004ccc8  mov     rax, [rbx+28h]
0x14004cccc  cmp     rax, cs:qword_140025B10
0x14004ccd3  jz      loc_14004CD8B
0x14004ccd9  cmp     rax, cs:DeviceObject
0x14004cce0  jz      loc_14004CD8B
0x14004cce6  xor     sil, sil
0x14004cce9  lea     r14, [rbx+30h]
0x14004cced  lea     rcx, UdfIrpContextLookasideList; Lookaside
0x14004ccf4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004ccfb  nop     dword ptr [rax+rax+00h]
0x14004cd00  xorps   xmm0, xmm0
0x14004cd03  xor     ecx, ecx
0x14004cd05  movups  xmmword ptr [rax], xmm0
0x14004cd08  movups  xmmword ptr [rax+10h], xmm0
0x14004cd0c  movups  xmmword ptr [rax+20h], xmm0
0x14004cd10  movups  xmmword ptr [rax+30h], xmm0
0x14004cd14  movups  xmmword ptr [rax+40h], xmm0
0x14004cd18  movups  xmmword ptr [rax+50h], xmm0
0x14004cd1c  mov     [rax+60h], rcx
0x14004cd20  mov     dword ptr [rax], 680937h
0x14004cd26  mov     [rax+8], rdi
0x14004cd2a  mov     rdx, [r14]
0x14004cd2d  test    rdx, rdx
0x14004cd30  jz      short loc_14004CD4B
0x14004cd32  mov     rcx, [rdx+8]
0x14004cd36  mov     [rax+20h], rcx
0x14004cd3a  mov     ecx, [rdx+50h]
0x14004cd3d  test    cl, 10h
0x14004cd40  jnz     loc_14004CDE0
0x14004cd46  cmp     byte ptr [rbx], 4
0x14004cd49  jz      short loc_14004CDCA
0x14004cd4b  test    sil, sil
0x14004cd4e  jnz     short loc_14004CD5F
0x14004cd50  mov     rcx, [rbx+28h]
0x14004cd54  add     rcx, 170h
0x14004cd5b  mov     [rax+10h], rcx
0x14004cd5f  movzx   ecx, byte ptr [rbx]
0x14004cd62  test    bpl, bpl
0x14004cd65  mov     [rax+38h], cl
0x14004cd68  mov     edx, 8
0x14004cd6d  movzx   ecx, byte ptr [rbx+1]
0x14004cd71  mov     [rax+39h], cl
0x14004cd74  mov     ecx, 4
0x14004cd79  cmovz   ecx, edx
0x14004cd7c  or      [rax+1Ch], ecx
0x14004cd7f  add     rsp, 20h
0x14004cd83  pop     r14
0x14004cd85  pop     rdi
0x14004cd86  pop     rsi
0x14004cd87  pop     rbp
0x14004cd88  pop     rbx
0x14004cd89  retn
0x14004cd8b  cmp     qword ptr [rbx+30h], 0
0x14004cd90  lea     r14, [rbx+30h]
0x14004cd94  mov     sil, 1
0x14004cd97  jz      loc_14004CCED
0x14004cd9d  movzx   eax, byte ptr [rbx]
0x14004cda0  test    al, al
0x14004cda2  jz      loc_14004CCED
0x14004cda8  cmp     al, 12h
0x14004cdaa  jz      loc_14004CCED
0x14004cdb0  cmp     al, 2
0x14004cdb2  jz      loc_14004CCED
0x14004cdb8  mov     ecx, 0C0000010h; Status
0x14004cdbd  call    cs:__imp_ExRaiseStatus
0x14004cdca  mov     ecx, [rdi+10h]
0x14004cdcd  test    cl, 1
0x14004cdd0  jz      loc_14004CD4B
0x14004cdd6  test    byte ptr [rbx+2], 4
0x14004cdda  jz      loc_14004CD4B
0x14004cde0  or      dword ptr [rax+1Ch], 20000h
0x14004cde7  jmp     loc_14004CD4B
```
