# WdsImgOpenImageStore

- ea: `0x1800071b0`
- end: `0x1800072cb`
- name: `WdsImgOpenImageStore`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001588`
- `0x180006fe8`
- `0x1800070dc`
- `0x1800071b0`
- `0x18000e9e4`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007231`
- `KERNEL32!GetLastError` at `0x180007231`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000724f`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x18000724f`

## pseudocode

```c
__int64 __fastcall WdsImgOpenImageStore(const unsigned __int16 *a1, unsigned __int16 ***a2)
{
  unsigned __int16 **v4; // rax
  unsigned __int16 **v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  int v8; // ebx
  __int64 v9; // rsi

  if ( !a1 || !*a1 || !a2 )
    return (unsigned int)-2147024809;
  v4 = (unsigned __int16 **)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
    return (unsigned int)-2147024882;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 4) = 1;
  v6 = 0;
  v4[3] = 0;
  *v4 = (unsigned __int16 *)&CImageStore::`vftable';
  if ( (unsigned int)DirectoryExists(a1) )
  {
    v9 = DuplicateStringW(a1, v5 + 3);
    if ( (unsigned int)ElValidateWin32_1(v9) )
    {
      if ( (int)v9 > 0 )
      {
        v8 = (unsigned __int16)v9;
        goto LABEL_12;
      }
      v6 = v9;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
    {
      v8 = (unsigned __int16)LastError;
LABEL_12:
      v6 = v8 | 0x80070000;
    }
  }
  if ( (int)ElValidateHr_2(v6) >= 0 )
    *a2 = v5;
  if ( (v6 & 0x80000000) != 0 )
    (*((void (__fastcall **)(unsigned __int16 **, __int64))*v5 + 2))(v5, 1);
  return v6;
}

```

## disassembly

```asm
0x1800071b0  mov     rax, rsp
0x1800071b3  mov     [rax+8], rbx
0x1800071b7  mov     [rax+10h], rbp
0x1800071bb  mov     [rax+18h], rsi
0x1800071bf  mov     [rax+20h], rdi
0x1800071c3  push    r14
0x1800071c5  sub     rsp, 20h
0x1800071c9  xor     ebp, ebp
0x1800071cb  mov     r14, rdx
0x1800071ce  mov     rsi, rcx
0x1800071d1  test    rcx, rcx
0x1800071d4  jz      loc_1800072A8
0x1800071da  cmp     [rcx], bp
0x1800071dd  jz      loc_1800072A8
0x1800071e3  test    rdx, rdx
0x1800071e6  jz      loc_1800072A8
0x1800071ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800071f3  lea     ecx, [rbp+20h]; unsigned __int64
0x1800071f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800071fb  mov     rdi, rax
0x1800071fe  test    rax, rax
0x180007201  jz      loc_1800072A1
0x180007207  mov     dword ptr [rax+8], 1
0x18000720e  mov     rcx, rsi
0x180007211  mov     dword ptr [rax+10h], 1
0x180007218  mov     ebx, ebp
0x18000721a  lea     rax, ??_7CImageStore@@6B@; const CImageStore::`vftable'
0x180007221  mov     [rdi+18h], rbp
0x180007225  mov     [rdi], rax
0x180007228  call    DirectoryExists
0x18000722d  test    eax, eax
0x18000722f  jnz     short loc_180007248
0x180007231  call    cs:__imp_GetLastError
0x180007238  nop     dword ptr [rax+rax+00h]
0x18000723d  mov     ebx, eax
0x18000723f  test    eax, eax
0x180007241  jle     short loc_180007279
0x180007243  movzx   ebx, ax
0x180007246  jmp     short loc_180007273
0x180007248  lea     rdx, [rdi+18h]
0x18000724c  mov     rcx, rsi
0x18000724f  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180007256  nop     dword ptr [rax+rax+00h]
0x18000725b  mov     ecx, eax
0x18000725d  mov     esi, eax
0x18000725f  call    ElValidateWin32_1
0x180007264  test    eax, eax
0x180007266  jz      short loc_180007279
0x180007268  test    esi, esi
0x18000726a  jg      short loc_180007270
0x18000726c  mov     ebx, esi
0x18000726e  jmp     short loc_180007279
0x180007270  movzx   ebx, si
0x180007273  or      ebx, 80070000h
0x180007279  mov     ecx, ebx
0x18000727b  call    ElValidateHr_2
0x180007280  test    eax, eax
0x180007282  js      short loc_180007287
0x180007284  mov     [r14], rdi
0x180007287  test    ebx, ebx
0x180007289  jns     short loc_1800072AD
0x18000728b  mov     rax, [rdi]
0x18000728e  mov     edx, 1
0x180007293  mov     rcx, rdi
0x180007296  mov     rax, [rax+10h]
0x18000729a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000729f  jmp     short loc_1800072AD
0x1800072a1  mov     ebx, 8007000Eh
0x1800072a6  jmp     short loc_1800072AD
0x1800072a8  mov     ebx, 80070057h
0x1800072ad  mov     rbp, [rsp+28h+arg_8]
0x1800072b2  mov     eax, ebx
0x1800072b4  mov     rbx, [rsp+28h+arg_0]
0x1800072b9  mov     rsi, [rsp+28h+arg_10]
0x1800072be  mov     rdi, [rsp+28h+arg_18]
0x1800072c3  add     rsp, 20h
0x1800072c7  pop     r14
0x1800072c9  retn
```
