# SetupBuffer

- ea: `0x1800362dc`
- end: `0x1800364ae`
- name: `SetupBuffer`
- size: `466`
- prototype: `__int64 __fastcall(int, const void **, _WORD *, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800369a0`
- `0x180036ba0`

## callees

- `0x180018260`
- `0x18001f038`
- `0x1800229f8`
- `0x180022a10`
- `0x1800362dc`
- `0x1800364b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800363ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036473`

## string_xrefs

- `0x18003648a`: `onecore\base\ngscb\wldp\dll\endpointsecuritypolicy.cpp`

## pseudocode

```c
__int64 __fastcall SetupBuffer(int a1, const void **a2, _WORD *a3, unsigned int *a4, void **a5)
{
  int v9; // ebp
  unsigned __int64 v10; // rcx
  int v11; // ebx
  __int64 v12; // rdx
  __int16 v13; // bx
  unsigned int v15; // edi
  HLOCAL v16; // rax
  void **v17; // rdi
  void *v18; // rcx
  HLOCAL v19; // rcx
  unsigned __int64 v20[11]; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HLOCAL hMem; // [rsp+88h] [rbp+10h] BYREF

  v20[0] = 0;
  v9 = *(unsigned __int16 *)a2;
  v10 = -1;
  do
    ++v10;
  while ( a3[v10] );
  v11 = ULongLongMult(v10, (unsigned __int64)a2, v20);
  if ( v11 < 0 )
  {
    v12 = 47;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\endpointsecuritypolicy.cpp",
      (const char *)(unsigned int)v11,
      v20[0]);
    return (unsigned int)v11;
  }
  v13 = v20[0];
  if ( v20[0] > 0xFFFF )
  {
    v12 = 48;
    goto LABEL_18;
  }
  if ( !LOWORD(v20[0]) )
    return 2147942487LL;
  v15 = v9 + 20 + LOWORD(v20[0]);
  if ( v15 < v9 + 20 )
  {
    v12 = 59;
LABEL_18:
    v11 = -2147024362;
    goto LABEL_19;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v15);
  if ( hMem )
  {
    memset_0(hMem, 0, v15);
    *a4 = v15;
    v16 = hMem;
    hMem = 0;
    v17 = a5;
    v18 = *a5;
    *a5 = v16;
    if ( v18 )
      LocalFree(v18);
    *(_WORD *)*v17 = 1;
    *((_DWORD *)*v17 + 1) = a1;
    *((_WORD *)*v17 + 4) = 16;
    *((_WORD *)*v17 + 5) = v9;
    *((_WORD *)*v17 + 6) = *((_WORD *)*v17 + 4) + *((_WORD *)*v17 + 5);
    *((_WORD *)*v17 + 7) = v13;
    memcpy_0((char *)*v17 + *((unsigned __int16 *)*v17 + 4), a2[1], *((unsigned __int16 *)*v17 + 5));
    memcpy_0((char *)*v17 + *((unsigned __int16 *)*v17 + 6), a3, *((unsigned __int16 *)*v17 + 7));
    v19 = hMem;
    hMem = 0;
    if ( v19 )
      LocalFree(v19);
    return 0;
  }
  else
  {
    hMem = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800362dc  push    rbx
0x1800362de  push    rbp
0x1800362df  push    rsi
0x1800362e0  push    rdi
0x1800362e1  push    r12
0x1800362e3  push    r13
0x1800362e5  push    r14
0x1800362e7  push    r15
0x1800362e9  sub     rsp, 38h
0x1800362ed  mov     r12, r9
0x1800362f0  mov     r14, r8
0x1800362f3  mov     r15, rdx
0x1800362f6  mov     r13d, ecx
0x1800362f9  xor     r9d, r9d
0x1800362fc  mov     [rsp+78h+var_58], r9; int
0x180036301  movzx   ebp, word ptr [rdx]
0x180036304  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180036308  inc     rcx; unsigned __int64
0x18003630b  cmp     [r8+rcx*2], r9w
0x180036310  jnz     short loc_180036308
0x180036312  lea     r8, [rsp+78h+var_58]; unsigned __int64 *
0x180036317  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003631c  mov     ebx, eax
0x18003631e  test    eax, eax
0x180036320  jns     short loc_18003632C
0x180036322  mov     edx, 2Fh ; '/'
0x180036327  jmp     loc_180036487
0x18003632c  mov     rbx, [rsp+78h+var_58]
0x180036331  cmp     rbx, 0FFFFh
0x180036338  ja      loc_18003647D
0x18003633e  test    bx, bx
0x180036341  jnz     short loc_18003634D
0x180036343  mov     eax, 80070057h
0x180036348  jmp     loc_18003649D
0x18003634d  lea     ecx, [rbp+14h]
0x180036350  cmp     ecx, 14h
0x180036353  jnb     short loc_18003635F
0x180036355  mov     edx, 39h ; '9'
0x18003635a  jmp     loc_180036482
0x18003635f  movzx   edi, bx
0x180036362  add     edi, ecx
0x180036364  cmp     edi, ecx
0x180036366  jnb     short loc_180036372
0x180036368  mov     edx, 3Bh ; ';'
0x18003636d  jmp     loc_180036482
0x180036372  mov     esi, edi
0x180036374  mov     edx, edi
0x180036376  lea     rcx, [rsp+78h+hMem]
0x18003637e  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180036383  nop
0x180036384  mov     rcx, [rsp+78h+hMem]; void *
0x18003638c  test    rcx, rcx
0x18003638f  jnz     short loc_1800363BA
0x180036391  mov     rcx, [rsp+78h+hMem]; hMem
0x180036399  mov     [rsp+78h+hMem], 0
0x1800363a5  test    rcx, rcx
0x1800363a8  jz      short loc_1800363B0
0x1800363aa  call    cs:__imp_LocalFree
0x1800363b0  mov     eax, 8007000Eh
0x1800363b5  jmp     loc_18003649D
0x1800363ba  mov     r8, rsi; Size
0x1800363bd  xor     edx, edx; Val
0x1800363bf  call    memset_0
0x1800363c4  mov     [r12], edi
0x1800363c8  mov     rax, [rsp+78h+hMem]
0x1800363d0  mov     [rsp+78h+hMem], 0
0x1800363dc  mov     rdi, [rsp+78h+arg_20]
0x1800363e4  mov     rcx, [rdi]; hMem
0x1800363e7  mov     [rdi], rax
0x1800363ea  test    rcx, rcx
0x1800363ed  jz      short loc_1800363F5
0x1800363ef  call    cs:__imp_LocalFree
0x1800363f5  mov     rax, [rdi]
0x1800363f8  mov     word ptr [rax], 1
0x1800363fd  mov     rax, [rdi]
0x180036400  mov     [rax+4], r13d
0x180036404  mov     rax, [rdi]
0x180036407  mov     word ptr [rax+8], 10h
0x18003640d  mov     rax, [rdi]
0x180036410  mov     [rax+0Ah], bp
0x180036414  mov     rcx, [rdi]
0x180036417  movzx   eax, word ptr [rcx+0Ah]
0x18003641b  add     ax, [rcx+8]
0x18003641f  mov     [rcx+0Ch], ax
0x180036423  mov     rax, [rdi]
0x180036426  mov     [rax+0Eh], bx
0x18003642a  mov     rax, [rdi]
0x18003642d  movzx   r8d, word ptr [rax+0Ah]; Size
0x180036432  movzx   ecx, word ptr [rax+8]
0x180036436  add     rcx, rax; void *
0x180036439  mov     rdx, [r15+8]; Src
0x18003643d  call    memcpy_0
0x180036442  mov     rax, [rdi]
0x180036445  movzx   r8d, word ptr [rax+0Eh]; Size
0x18003644a  movzx   ecx, word ptr [rax+0Ch]
0x18003644e  add     rcx, rax; void *
0x180036451  mov     rdx, r14; Src
0x180036454  call    memcpy_0
0x180036459  nop
0x18003645a  mov     rcx, [rsp+78h+hMem]; hMem
0x180036462  mov     [rsp+78h+hMem], 0
0x18003646e  test    rcx, rcx
0x180036471  jz      short loc_180036479
0x180036473  call    cs:__imp_LocalFree
0x180036479  xor     eax, eax
0x18003647b  jmp     short loc_18003649D
0x18003647d  mov     edx, 30h ; '0'; void *
0x180036482  mov     ebx, 80070216h
0x180036487  mov     r9d, ebx; char *
0x18003648a  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\wldp\\dll\\endpoi"...
0x180036491  mov     rcx, [rsp+78h]; this
0x180036496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003649b  mov     eax, ebx
0x18003649d  add     rsp, 38h
0x1800364a1  pop     r15
0x1800364a3  pop     r14
0x1800364a5  pop     r13
0x1800364a7  pop     r12
0x1800364a9  pop     rdi
0x1800364aa  pop     rsi
0x1800364ab  pop     rbp
0x1800364ac  pop     rbx
0x1800364ad  retn
```
