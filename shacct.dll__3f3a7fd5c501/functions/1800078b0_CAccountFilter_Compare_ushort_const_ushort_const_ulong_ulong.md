# CAccountFilter::_Compare(ushort const *,ushort const *,ulong,ulong)

- ea: `0x1800078b0`
- end: `0x18000795d`
- name: `?_Compare@CAccountFilter@@AEAAHPEBG0KK@Z`
- size: `173`
- prototype: `int(CAccountFilter *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007690`

## callees

- `0x1800078b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000790f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000793e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000790f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000793e`

## pseudocode

```c
__int64 __fastcall CAccountFilter::_Compare(
        CAccountFilter *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  unsigned __int16 v5; // bx
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // edx
  int v12; // eax

  v5 = a4;
  if ( (a4 & 0xFFFF0000) != 0 )
  {
    if ( (a4 & 0xFFFF0000) != 0x10000 )
      return 0;
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    do
      ++v8;
    while ( a2[v8] );
    if ( (int)v8 < (int)v9 )
      return 0;
    v10 = CompareStringOrdinal(a2, v9, a3, v9, 1);
    v11 = 0;
    if ( v10 != 2 )
      return 0;
    goto LABEL_11;
  }
  v12 = CompareStringOrdinal(a2, -1, a3, -1, 1);
  v11 = 0;
  if ( v12 == 2 )
LABEL_11:
    LOBYTE(v11) = v5 == a5;
  return v11;
}

```

## disassembly

```asm
0x1800078b0  push    rbx
0x1800078b2  sub     rsp, 30h
0x1800078b6  mov     eax, r9d
0x1800078b9  mov     ebx, r9d
0x1800078bc  mov     r10, rdx
0x1800078bf  and     eax, 0FFFF0000h
0x1800078c4  jz      short loc_180007929
0x1800078c6  cmp     eax, 10000h
0x1800078cb  jz      short loc_1800078D7
0x1800078cd  xor     edx, edx
0x1800078cf  mov     eax, edx
0x1800078d1  add     rsp, 30h
0x1800078d5  pop     rbx
0x1800078d6  retn
0x1800078d7  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800078de  mov     rax, rdx
0x1800078e1  inc     rax
0x1800078e4  cmp     word ptr [r8+rax*2], 0
0x1800078ea  jnz     short loc_1800078E1
0x1800078ec  nop     dword ptr [rax+00h]
0x1800078f0  inc     rdx
0x1800078f3  cmp     word ptr [r10+rdx*2], 0
0x1800078f9  jnz     short loc_1800078F0
0x1800078fb  cmp     edx, eax
0x1800078fd  jl      short loc_1800078CD
0x1800078ff  mov     r9d, eax; cchCount2
0x180007902  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000790a  mov     edx, eax; cchCount1
0x18000790c  mov     rcx, r10; lpString1
0x18000790f  call    cs:__imp_CompareStringOrdinal
0x180007915  xor     edx, edx
0x180007917  cmp     eax, 2
0x18000791a  mov     ecx, edx
0x18000791c  setz    cl
0x18000791f  jz      short loc_18000794B
0x180007921  mov     eax, ecx
0x180007923  add     rsp, 30h
0x180007927  pop     rbx
0x180007928  retn
0x180007929  mov     rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x180007930  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180007938  mov     r9d, edx; cchCount2
0x18000793b  mov     rcx, r10; lpString1
0x18000793e  call    cs:__imp_CompareStringOrdinal
0x180007944  xor     edx, edx
0x180007946  cmp     eax, 2
0x180007949  jnz     short loc_180007955
0x18000794b  movzx   ecx, bx
0x18000794e  cmp     ecx, [rsp+38h+arg_20]
0x180007952  setz    dl
0x180007955  mov     eax, edx
0x180007957  add     rsp, 30h
0x18000795b  pop     rbx
0x18000795c  retn
```
