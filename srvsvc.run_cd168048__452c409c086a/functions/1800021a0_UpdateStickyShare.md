# UpdateStickyShare

- ea: `0x1800021a0`
- end: `0x1800023db`
- name: `UpdateStickyShare`
- size: `571`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1800021a0`
- `0x1800023f0`
- `0x180003f60`
- `0x18001deb0`
- `0x18001e80c`
- `0x180026b94`
- `0x180026cd8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800023d0`

## string_xrefs

- `0x180002383`: `UpdateStickyShare`

## pseudocode

```c
__int64 __fastcall UpdateStickyShare(const WCHAR *Src, int a2, WCHAR *a3, __int64 a4, int a5, int *a6)
{
  int v9; // esi
  HLOCAL v10; // rdx
  unsigned int v11; // r8d
  unsigned __int16 i; // r9
  unsigned __int64 v13; // rax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  HLOCAL v21[2]; // [rsp+50h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-98h]
  HLOCAL v23; // [rsp+78h] [rbp-80h]
  HLOCAL v24; // [rsp+88h] [rbp-70h]
  HLOCAL v25; // [rsp+98h] [rbp-60h]

  memset_0(v21, 0, 0x78u);
  v9 = *a6;
  if ( GetStickyShareInfo(Src, a2, a3, (__int64 *)v21) )
  {
    v10 = v23;
    v11 = 0x80000000;
    for ( i = 65; i <= 0x5Au && v9; ++i )
    {
      if ( (v9 & v11) != 0 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *((_WORD *)v23 + v13) );
        if ( v13 >= 3 )
        {
          v15 = *(unsigned __int16 *)v23;
          if ( ((_WORD)v15 == i || v15 == i + 32) && *((_WORD *)v23 + 1) == 58 && *((_WORD *)v23 + 2) == 92 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_sS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                92,
                (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
                (unsigned int)"UpdateStickyShare",
                (__int64)Src);
            }
            v16 = I_NetrShareAdd(0, 505, (wint_t *)v21, 0, 1, 1, 1u, 0, 0, 0);
            if ( v16
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_sSSl(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v19, (__int64)Src, (__int64)v23, v16);
            }
            v10 = v23;
            break;
          }
        }
      }
      v14 = v11;
      v11 >>= 1;
      v9 &= ~v14;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      v10 = v23;
    }
    if ( v10 )
      LocalFree(v10);
    if ( v24 )
      LocalFree(v24);
    if ( v21[0] )
      LocalFree(v21[0]);
    if ( v25 )
      LocalFree(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x1800021a0  mov     [rsp+arg_18], rbx
0x1800021a5  push    rbp
0x1800021a6  push    rsi
0x1800021a7  push    rdi
0x1800021a8  sub     rsp, 0E0h
0x1800021af  mov     rax, cs:__security_cookie
0x1800021b6  xor     rax, rsp
0x1800021b9  mov     [rsp+0F8h+var_28], rax
0x1800021c1  mov     rdi, r8
0x1800021c4  mov     ebx, edx
0x1800021c6  mov     rbp, rcx
0x1800021c9  xor     edx, edx; Val
0x1800021cb  mov     r8d, 78h ; 'x'; Size
0x1800021d1  lea     rcx, [rsp+0F8h+var_A8]; void *
0x1800021d6  call    memset_0
0x1800021db  mov     rax, [rsp+0F8h+arg_28]
0x1800021e3  lea     r9, [rsp+0F8h+var_A8]
0x1800021e8  mov     r8, rdi
0x1800021eb  mov     edx, ebx
0x1800021ed  mov     rcx, rbp; Src
0x1800021f0  mov     esi, [rax]
0x1800021f2  call    GetStickyShareInfo
0x1800021f7  test    al, al
0x1800021f9  jz      loc_180002334
0x1800021ff  mov     rdx, [rsp+0F8h+var_80]
0x180002204  mov     r8d, 80000000h
0x18000220a  mov     r9d, 41h ; 'A'
0x180002210  cmp     r9w, 5Ah ; 'Z'
0x180002215  ja      loc_1800022E3
0x18000221b  test    esi, esi
0x18000221d  jz      loc_1800022E3
0x180002223  test    r8d, esi
0x180002226  jz      short loc_180002240
0x180002228  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000222f  nop
0x180002230  inc     rax
0x180002233  cmp     word ptr [rdx+rax*2], 0
0x180002238  jnz     short loc_180002230
0x18000223a  cmp     rax, 3
0x18000223e  jnb     short loc_180002250
0x180002240  mov     eax, r8d
0x180002243  shr     r8d, 1
0x180002246  not     eax
0x180002248  and     esi, eax
0x18000224a  inc     r9w
0x18000224e  jmp     short loc_180002210
0x180002250  movzx   eax, word ptr [rdx]
0x180002253  cmp     ax, r9w
0x180002257  jnz     loc_180002361
0x18000225d  cmp     word ptr [rdx+2], 3Ah ; ':'
0x180002262  jnz     short loc_180002240
0x180002264  cmp     word ptr [rdx+4], 5Ch ; '\'
0x180002269  jnz     short loc_180002240
0x18000226b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002272  lea     rbx, WPP_GLOBAL_Control
0x180002279  cmp     rcx, rbx
0x18000227c  jz      short loc_18000228B
0x18000227e  test    dword ptr [rcx+1Ch], 100h
0x180002285  jnz     loc_180002375
0x18000228b  mov     [rsp+0F8h+var_B0], 0
0x180002294  lea     r8, [rsp+0F8h+var_A8]
0x180002299  mov     [rsp+0F8h+var_B8], 0
0x18000229e  xor     r9d, r9d
0x1800022a1  mov     [rsp+0F8h+var_C0], 0
0x1800022a6  mov     edx, 1F9h
0x1800022ab  mov     byte ptr [rsp+0F8h+var_C8], 1
0x1800022b0  xor     ecx, ecx
0x1800022b2  mov     byte ptr [rsp+0F8h+var_D0], 1
0x1800022b7  mov     byte ptr [rsp+0F8h+var_D8], 1
0x1800022bc  call    I_NetrShareAdd
0x1800022c1  test    eax, eax
0x1800022c3  jz      short loc_1800022DE
0x1800022c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022cc  cmp     rcx, rbx
0x1800022cf  jz      short loc_1800022DE
0x1800022d1  test    dword ptr [rcx+1Ch], 100h
0x1800022d8  jnz     loc_1800023A5
0x1800022de  mov     rdx, [rsp+0F8h+var_80]
0x1800022e3  mov     rcx, [rsp+0F8h+hMem]; hMem
0x1800022e8  test    rcx, rcx
0x1800022eb  jz      short loc_1800022F8
0x1800022ed  call    cs:__imp_LocalFree
0x1800022f3  mov     rdx, [rsp+0F8h+var_80]
0x1800022f8  test    rdx, rdx
0x1800022fb  jz      short loc_180002306
0x1800022fd  mov     rcx, rdx; hMem
0x180002300  call    cs:__imp_LocalFree
0x180002306  mov     rcx, [rsp+0F8h+var_70]; hMem
0x18000230e  test    rcx, rcx
0x180002311  jnz     loc_1800023D0
0x180002317  mov     rcx, [rsp+0F8h+var_A8]; hMem
0x18000231c  test    rcx, rcx
0x18000231f  jz      short loc_180002327
0x180002321  call    cs:__imp_LocalFree
0x180002327  mov     rcx, [rsp+0F8h+var_60]; hMem
0x18000232f  test    rcx, rcx
0x180002332  jnz     short loc_180002359
0x180002334  xor     eax, eax
0x180002336  mov     rcx, [rsp+0F8h+var_28]
0x18000233e  xor     rcx, rsp; StackCookie
0x180002341  call    __security_check_cookie
0x180002346  mov     rbx, [rsp+0F8h+arg_18]
0x18000234e  add     rsp, 0E0h
0x180002355  pop     rdi
0x180002356  pop     rsi
0x180002357  pop     rbp
0x180002358  retn
0x180002359  call    cs:__imp_LocalFree
0x18000235f  jmp     short loc_180002334
0x180002361  movzx   ecx, r9w
0x180002365  add     ecx, 20h ; ' '
0x180002368  cmp     eax, ecx
0x18000236a  jnz     loc_180002240
0x180002370  jmp     loc_18000225D
0x180002375  cmp     byte ptr [rcx+19h], 2
0x180002379  jb      loc_18000228B
0x18000237f  mov     rcx, [rcx+10h]
0x180002383  lea     r9, aUpdatestickysh; "UpdateStickyShare"
0x18000238a  mov     edx, 5Ch ; '\'
0x18000238f  mov     [rsp+0F8h+var_D8], rbp
0x180002394  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x18000239b  call    WPP_SF_sS
0x1800023a0  jmp     loc_18000228B
0x1800023a5  cmp     byte ptr [rcx+19h], 1
0x1800023a9  jb      loc_1800022DE
0x1800023af  mov     rcx, [rcx+10h]
0x1800023b3  mov     [rsp+0F8h+var_C8], eax
0x1800023b7  mov     rax, [rsp+0F8h+var_80]
0x1800023bc  mov     [rsp+0F8h+var_D0], rax
0x1800023c1  mov     [rsp+0F8h+var_D8], rbp
0x1800023c6  call    WPP_SF_sSSl
0x1800023cb  jmp     loc_1800022DE
0x1800023d0  call    cs:__imp_LocalFree
0x1800023d6  jmp     loc_180002317
```
