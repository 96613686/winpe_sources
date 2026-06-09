# AslPathCombine

- ea: `0x1400100c4`
- end: `0x140010267`
- name: `AslPathCombine`
- size: `419`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int16 *, unsigned __int16 *, __int64)`
- caller_count: `8`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000f158`
- `0x14000f28c`
- `0x140012db0`
- `0x140012ea0`
- `0x140013060`
- `0x1400131a0`
- `0x140013280`
- `0x1400133f0`

## callees

- `0x14000acf4`
- `0x14001008c`
- `0x1400100c4`
- `0x140011d6c`

## string_xrefs

- `0x140010247`: `AslPathCombine`

## pseudocode

```c
__int64 __fastcall AslPathCombine(_WORD *a1, unsigned __int16 *a2, unsigned __int16 *a3, __int64 a4)
{
  unsigned __int16 *v6; // r10
  _WORD *v9; // rax
  __int64 v10; // r8
  signed int v11; // ebx
  __int64 v12; // rbp
  __int64 v13; // rcx
  unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  unsigned __int16 *v16; // r14
  unsigned int v17; // ecx
  unsigned int v18; // ebp

  v6 = a2;
  if ( !a4 )
    return 3221225507LL;
  if ( !a1 )
  {
    v11 = -1073741811;
    goto LABEL_34;
  }
  v9 = a1;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v11 = v10 == 0 ? 0xC000000D : 0;
  v12 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
    goto LABEL_34;
  if ( !a2 )
  {
    v11 = -1073741811;
    goto LABEL_34;
  }
  v13 = 0x7FFFFFFF;
  v14 = a2;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v11 = v13 == 0 ? 0xC000000D : 0;
  v15 = (0x7FFFFFFF - v13) & ((unsigned __int128)-(__int128)(unsigned __int64)v13 >> 64);
  if ( !v13 )
    goto LABEL_34;
  if ( v12 )
  {
    if ( v15 )
    {
      v16 = v6 + 1;
      v17 = (a1[v12 - 1] == 92) + 1;
      if ( *v6 != 92 )
        v17 = a1[v12 - 1] == 92;
      if ( v17 <= 1 )
        v16 = v6;
      v18 = v17 - 1;
      if ( v17 <= 1 )
        v18 = v17;
      v11 = RtlStringCchCopyW(a3, a4, a1);
      if ( v11 >= 0 )
      {
        if ( v18 || (v11 = RtlStringCchCatW(a3, a4, L"\\"), v11 >= 0) )
        {
          v11 = RtlStringCchCatW(a3, a4, v16);
          if ( v11 >= 0 )
            return 0;
        }
      }
LABEL_34:
      AslLogCallPrintf(1, "AslPathCombine", 1420, "An RtlString API failed [%x]", v11);
      return (unsigned int)v11;
    }
    v6 = a1;
LABEL_19:
    v11 = RtlStringCchCopyW(a3, a4, v6);
    if ( v11 >= 0 )
      return (unsigned int)v11;
    goto LABEL_34;
  }
  if ( v15 )
    goto LABEL_19;
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x1400100c4  push    rbx
0x1400100c6  push    rbp
0x1400100c7  push    rsi
0x1400100c8  push    rdi
0x1400100c9  push    r14
0x1400100cb  push    r15
0x1400100cd  sub     rsp, 38h
0x1400100d1  xor     r15d, r15d
0x1400100d4  mov     rsi, r9
0x1400100d7  mov     rdi, r8
0x1400100da  mov     r10, rdx
0x1400100dd  mov     r11, rcx
0x1400100e0  test    r9, r9
0x1400100e3  jnz     short loc_1400100EF
0x1400100e5  mov     eax, 0C0000023h
0x1400100ea  jmp     loc_14001025A
0x1400100ef  test    r11, r11
0x1400100f2  jz      loc_140010231
0x1400100f8  mov     r9d, 7FFFFFFFh
0x1400100fe  mov     rax, r11
0x140010101  mov     r8d, r9d
0x140010104  cmp     [rax], r15w
0x140010108  jz      short loc_140010114
0x14001010a  add     rax, 2
0x14001010e  sub     r8, 1
0x140010112  jnz     short loc_140010104
0x140010114  mov     rax, r8
0x140010117  mov     edx, 0C000000Dh
0x14001011c  neg     rax
0x14001011f  mov     rcx, r9
0x140010122  mov     rax, r8
0x140010125  sbb     ebx, ebx
0x140010127  sub     rcx, r8
0x14001012a  not     ebx
0x14001012c  and     ebx, edx
0x14001012e  neg     rax
0x140010131  sbb     rbp, rbp
0x140010134  and     rbp, rcx
0x140010137  test    r8, r8
0x14001013a  jz      loc_140010236
0x140010140  test    r10, r10
0x140010143  jz      loc_14001022D
0x140010149  mov     rcx, r9
0x14001014c  mov     rax, r10
0x14001014f  cmp     [rax], r15w
0x140010153  jz      short loc_14001015F
0x140010155  add     rax, 2
0x140010159  sub     rcx, 1
0x14001015d  jnz     short loc_14001014F
0x14001015f  mov     rax, rcx
0x140010162  neg     rax
0x140010165  mov     rax, rcx
0x140010168  sbb     ebx, ebx
0x14001016a  sub     r9, rcx
0x14001016d  not     ebx
0x14001016f  and     ebx, edx
0x140010171  neg     rax
0x140010174  sbb     rdx, rdx
0x140010177  and     rdx, r9
0x14001017a  test    rcx, rcx
0x14001017d  jz      loc_140010236
0x140010183  test    rbp, rbp
0x140010186  jnz     short loc_140010199
0x140010188  test    rdx, rdx
0x14001018b  jnz     short loc_1400101A1
0x14001018d  mov     [rdi], r15w
0x140010191  mov     ebx, r15d
0x140010194  jmp     loc_140010258
0x140010199  test    rdx, rdx
0x14001019c  jnz     short loc_1400101BB
0x14001019e  mov     r10, r11
0x1400101a1  mov     r8, r10
0x1400101a4  mov     rdx, rsi
0x1400101a7  mov     rcx, rdi
0x1400101aa  call    RtlStringCchCopyW
0x1400101af  mov     ebx, eax
0x1400101b1  test    eax, eax
0x1400101b3  jns     loc_140010258
0x1400101b9  jmp     short loc_140010236
0x1400101bb  cmp     word ptr [r11+rbp*2-2], 5Ch ; '\'
0x1400101c2  lea     r14, [r10+2]
0x1400101c6  mov     eax, r15d
0x1400101c9  mov     r8, r11
0x1400101cc  setz    al
0x1400101cf  mov     rdx, rsi
0x1400101d2  cmp     word ptr [r10], 5Ch ; '\'
0x1400101d7  lea     ecx, [rax+1]
0x1400101da  cmovnz  ecx, eax
0x1400101dd  cmp     ecx, 1
0x1400101e0  cmovbe  r14, r10
0x1400101e4  lea     ebp, [rcx-1]
0x1400101e7  cmovbe  ebp, ecx
0x1400101ea  mov     rcx, rdi
0x1400101ed  call    RtlStringCchCopyW
0x1400101f2  mov     ebx, eax
0x1400101f4  test    eax, eax
0x1400101f6  js      short loc_140010236
0x1400101f8  test    ebp, ebp
0x1400101fa  jnz     short loc_140010214
0x1400101fc  lea     r8, asc_1400326D0; "\\"
0x140010203  mov     rdx, rsi; unsigned __int64
0x140010206  mov     rcx, rdi; unsigned __int16 *
0x140010209  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001020e  mov     ebx, eax
0x140010210  test    eax, eax
0x140010212  js      short loc_140010236
0x140010214  mov     r8, r14; unsigned __int16 *
0x140010217  mov     rdx, rsi; unsigned __int64
0x14001021a  mov     rcx, rdi; unsigned __int16 *
0x14001021d  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010222  mov     ebx, eax
0x140010224  test    eax, eax
0x140010226  js      short loc_140010236
0x140010228  jmp     loc_140010191
0x14001022d  mov     ebx, edx
0x14001022f  jmp     short loc_140010236
0x140010231  mov     ebx, 0C000000Dh
0x140010236  lea     r9, aAnRtlstringApi; "An RtlString API failed [%x]"
0x14001023d  mov     [rsp+68h+var_48], ebx
0x140010241  mov     r8d, 58Ch
0x140010247  lea     rdx, aAslpathcombine; "AslPathCombine"
0x14001024e  mov     ecx, 1
0x140010253  call    AslLogCallPrintf
0x140010258  mov     eax, ebx
0x14001025a  add     rsp, 38h
0x14001025e  pop     r15
0x140010260  pop     r14
0x140010262  pop     rdi
0x140010263  pop     rsi
0x140010264  pop     rbp
0x140010265  pop     rbx
0x140010266  retn
```
