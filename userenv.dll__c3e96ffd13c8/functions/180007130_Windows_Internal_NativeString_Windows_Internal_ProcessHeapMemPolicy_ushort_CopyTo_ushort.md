# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)

- ea: `0x180007130`
- end: `0x180007291`
- name: `?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z`
- size: `353`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003d70`
- `0x18001a540`

## callees

- `0x180007130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007201`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007201`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071f3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
        __int64 a1,
        _QWORD *a2)
{
  _WORD *v3; // rdi
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rsi
  HANDLE ProcessHeap; // rax
  _WORD *v9; // rax
  _WORD *v10; // rcx

  *a2 = 0;
  v3 = *(_WORD **)a1;
  if ( !*(_QWORD *)a1 )
    return 2147943568LL;
  v4 = *(_QWORD *)(a1 + 8);
  v5 = -1;
  if ( v4 == -1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v3[v4] );
  }
  do
    ++v5;
  while ( v3[v5] );
  if ( v4 == -1 )
  {
    v4 = v5;
  }
  else if ( v4 < v5 )
  {
    v5 = v4;
  }
  v6 = v4 + 1;
  if ( v4 + 1 < v4 || !is_mul_ok(v6, 2u) )
    return 2147942934LL;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 2 * v6);
  if ( !v9 )
    return 2147942414LL;
  *v9 = 0;
  if ( v6 )
  {
    if ( v6 > 0x7FFFFFFF )
    {
      *v9 = 0;
    }
    else if ( v5 > 0x7FFFFFFE )
    {
      *v9 = 0;
    }
    else
    {
      v10 = v9;
      while ( v5 && *v3 )
      {
        *v10++ = *v3++;
        --v5;
        if ( !--v6 )
        {
          --v10;
          break;
        }
      }
      *v10 = 0;
    }
  }
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180007130  push    rdi
0x180007132  push    r12
0x180007134  push    r15
0x180007136  sub     rsp, 30h
0x18000713a  xor     r12d, r12d
0x18000713d  mov     r15, rdx
0x180007140  mov     [rdx], r12
0x180007143  mov     rdi, [rcx]
0x180007146  test    rdi, rdi
0x180007149  jz      loc_180007287
0x18000714f  mov     rax, [rcx+8]
0x180007153  mov     [rsp+48h+arg_8], rbx
0x180007158  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000715f  mov     [rsp+48h+var_20], rsi
0x180007164  mov     [rsp+48h+var_28], r14
0x180007169  cmp     rax, rbx
0x18000716c  jnz     short loc_180007180
0x18000716e  mov     rax, rbx
0x180007171  inc     rax
0x180007174  cmp     [rdi+rax*2], r12w
0x180007179  jnz     short loc_180007171
0x18000717b  nop     dword ptr [rax+rax+00h]
0x180007180  inc     rbx
0x180007183  cmp     [rdi+rbx*2], r12w
0x180007188  jnz     short loc_180007180
0x18000718a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000718e  jz      loc_18000725E
0x180007194  cmp     rax, rbx
0x180007197  cmovb   rbx, rax
0x18000719b  lea     rsi, [rax+1]
0x18000719f  mov     [rsp+48h+arg_10], rbp
0x1800071a4  cmp     rsi, rax
0x1800071a7  jnb     short loc_1800071E3
0x1800071a9  mov     ebx, 80070216h
0x1800071ae  mov     eax, ebx
0x1800071b0  jmp     short loc_1800071C5
0x1800071b2  test    rsi, rsi
0x1800071b5  jz      loc_180007255
0x1800071bb  mov     [rcx], r12w
0x1800071bf  mov     [r15], rdx
0x1800071c2  mov     eax, r8d
0x1800071c5  mov     rbp, [rsp+48h+arg_10]
0x1800071ca  mov     rsi, [rsp+48h+var_20]
0x1800071cf  mov     rbx, [rsp+48h+arg_8]
0x1800071d4  mov     r14, [rsp+48h+var_28]
0x1800071d9  add     rsp, 30h
0x1800071dd  pop     r15
0x1800071df  pop     r12
0x1800071e1  pop     rdi
0x1800071e2  retn
0x1800071e3  mov     eax, 2
0x1800071e8  mul     rsi
0x1800071eb  mov     rbp, rax
0x1800071ee  test    rdx, rdx
0x1800071f1  jnz     short loc_1800071A9
0x1800071f3  call    cs:__imp_GetProcessHeap
0x1800071f9  mov     r8, rbp; dwBytes
0x1800071fc  xor     edx, edx; dwFlags
0x1800071fe  mov     rcx, rax; hHeap
0x180007201  call    cs:__imp_HeapAlloc
0x180007207  mov     rdx, rax
0x18000720a  test    rax, rax
0x18000720d  jz      short loc_180007266
0x18000720f  mov     [rax], r12w
0x180007213  test    rsi, rsi
0x180007216  jz      short loc_180007276
0x180007218  cmp     rsi, 7FFFFFFFh
0x18000721f  ja      short loc_180007272
0x180007221  mov     r8d, r12d
0x180007224  cmp     rbx, 7FFFFFFEh
0x18000722b  ja      short loc_18000727E
0x18000722d  mov     rcx, rax
0x180007230  test    rbx, rbx
0x180007233  jz      short loc_1800071BB
0x180007235  movzx   eax, word ptr [rdi]
0x180007238  test    ax, ax
0x18000723b  jz      loc_1800071B2
0x180007241  mov     [rcx], ax
0x180007244  add     rdi, 2
0x180007248  add     rcx, 2
0x18000724c  dec     rbx
0x18000724f  sub     rsi, 1
0x180007253  jnz     short loc_180007230
0x180007255  sub     rcx, 2
0x180007259  jmp     loc_1800071BB
0x18000725e  mov     rax, rbx
0x180007261  jmp     loc_18000719B
0x180007266  mov     ebx, 8007000Eh
0x18000726b  mov     eax, ebx
0x18000726d  jmp     loc_1800071C5
0x180007272  mov     [rax], r12w
0x180007276  mov     r8d, r12d
0x180007279  jmp     loc_1800071BF
0x18000727e  mov     [rax], r12w
0x180007282  jmp     loc_1800071BF
0x180007287  mov     eax, 80070490h
0x18000728c  jmp     loc_1800071D9
```
