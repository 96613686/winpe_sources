# CDSArrayBuilder::Grow(ulong)

- ea: `0x18004203c`
- end: `0x18004210e`
- name: `?Grow@CDSArrayBuilder@@IEAAJK@Z`
- size: `210`
- prototype: `int(CDSArrayBuilder *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042114`
- `0x180042158`

## callees

- `0x180003950`
- `0x18000a7b4`
- `0x18004203c`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800420ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800420ae`

## pseudocode

```c
__int64 __fastcall CDSArrayBuilder::Grow(CDSArrayBuilder *this, unsigned int a2)
{
  unsigned int v2; // ebp
  void *v5; // r8
  void *v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // ebp
  unsigned int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  char *v12; // rax
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *((_DWORD *)this + 5);
  if ( v2 >= a2 && *((_QWORD *)this + 1) )
    return 0;
  v5 = (void *)*((_QWORD *)this + 1);
  v6 = 0;
  v7 = 8;
  if ( a2 >= 8 )
    v7 = a2;
  v8 = 2 * v2;
  if ( v8 < v7 )
    v8 = v7;
  v9 = *((_DWORD *)this + 4) * v8;
  if ( v5 )
  {
    v12 = (char *)CoTaskMemRealloc(v5, v9);
    v6 = v12;
    if ( !v12 )
    {
      v10 = -2147024882;
      v11 = 81;
      goto LABEL_14;
    }
    memset(&v12[*((_DWORD *)this + 5) * *((_DWORD *)this + 4)], 0, *((_DWORD *)this + 4) * (v8 - *((_DWORD *)this + 5)));
LABEL_16:
    *((_QWORD *)this + 1) = v6;
    v10 = 0;
    *((_DWORD *)this + 5) = v8;
    return v10;
  }
  if ( !v9 )
    goto LABEL_16;
  v6 = SafeSusComAllocArray(v9, 1u);
  v10 = v6 == 0 ? 0x8007000E : 0;
  if ( v6 )
    goto LABEL_16;
  v11 = 73;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsarray.cpp",
    (const char *)v10,
    v13);
  return v10;
}

```

## disassembly

```asm
0x18004203c  mov     [rsp+arg_10], rbx
0x180042041  push    rbp
0x180042042  push    rsi
0x180042043  push    rdi; int
0x180042044  sub     rsp, 20h
0x180042048  mov     ebp, [rcx+14h]
0x18004204b  mov     rsi, rcx
0x18004204e  cmp     ebp, edx
0x180042050  jb      short loc_180042060
0x180042052  cmp     qword ptr [rcx+8], 0
0x180042057  jz      short loc_180042060
0x180042059  xor     eax, eax
0x18004205b  jmp     loc_180042101
0x180042060  mov     r8, [rcx+8]
0x180042064  xor     ebx, ebx
0x180042066  lea     eax, [rbx+8]
0x180042069  cmp     edx, eax
0x18004206b  cmovnb  eax, edx
0x18004206e  add     ebp, ebp
0x180042070  cmp     ebp, eax
0x180042072  cmovb   ebp, eax
0x180042075  mov     eax, ebp
0x180042077  imul    eax, [rcx+10h]
0x18004207b  mov     ecx, eax; unsigned __int64
0x18004207d  test    r8, r8
0x180042080  jnz     short loc_1800420A8
0x180042082  test    eax, eax
0x180042084  jz      short loc_1800420F6
0x180042086  lea     edx, [rbx+1]; unsigned __int64
0x180042089  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18004208e  mov     rbx, rax
0x180042091  neg     rax
0x180042094  sbb     edi, edi
0x180042096  not     edi
0x180042098  and     edi, 8007000Eh
0x18004209e  test    rbx, rbx
0x1800420a1  jnz     short loc_1800420F6
0x1800420a3  lea     edx, [rbx+49h]
0x1800420a6  jmp     short loc_1800420C4
0x1800420a8  mov     rdx, rcx; cb
0x1800420ab  mov     rcx, r8; pv
0x1800420ae  call    cs:__imp_CoTaskMemRealloc
0x1800420b4  mov     rbx, rax
0x1800420b7  test    rax, rax
0x1800420ba  jnz     short loc_1800420DA
0x1800420bc  mov     edi, 8007000Eh
0x1800420c1  lea     edx, [rax+51h]; void *
0x1800420c4  mov     rcx, [rsp+38h]; this
0x1800420c9  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x1800420d0  mov     r9d, edi; char *
0x1800420d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800420d8  jmp     short loc_1800420FF
0x1800420da  mov     ecx, [rsi+10h]
0x1800420dd  mov     r8d, ebp
0x1800420e0  sub     r8d, [rsi+14h]
0x1800420e4  xor     edx, edx; Val
0x1800420e6  imul    r8d, ecx; Size
0x1800420ea  imul    ecx, [rsi+14h]
0x1800420ee  add     rcx, rax; void *
0x1800420f1  call    memset
0x1800420f6  mov     [rsi+8], rbx
0x1800420fa  xor     edi, edi
0x1800420fc  mov     [rsi+14h], ebp
0x1800420ff  mov     eax, edi
0x180042101  mov     rbx, [rsp+38h+arg_10]
0x180042106  add     rsp, 20h
0x18004210a  pop     rdi
0x18004210b  pop     rsi
0x18004210c  pop     rbp
0x18004210d  retn
```
