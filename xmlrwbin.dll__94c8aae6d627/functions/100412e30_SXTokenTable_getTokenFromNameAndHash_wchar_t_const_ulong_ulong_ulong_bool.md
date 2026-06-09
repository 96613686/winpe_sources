# SXTokenTable::getTokenFromNameAndHash(wchar_t const *,ulong,ulong,ulong *,bool)

- ea: `0x100412e30`
- end: `0x1004130b7`
- name: `?getTokenFromNameAndHash@SXTokenTable@@QEAA?AW4TokenSearchResult@@PEB_WKKPEAK_N@Z`
- size: `647`
- prototype: `enum TokenSearchResult __high(const wchar_t *, unsigned int, unsigned int, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x100409da0`
- `0x10040a470`

## callees

- `0x100401300`
- `0x100401350`
- `0x100406550`
- `0x100411800`
- `0x100412e30`
- `0x1004133e0`
- `0x100413a50`
- `0x100415d60`
- `0x10041b390`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100412f59`
- `KERNEL32!HeapAlloc` at `0x100412f59`

## pseudocode

```c
__int64 __fastcall SXTokenTable::getTokenFromNameAndHash(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        unsigned int a4,
        _DWORD *a5,
        char a6)
{
  size_t v7; // rsi
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // r14
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // edx
  struct IMalloc *v18; // rcx
  __int64 v19; // rax
  CStringPtr *v20; // rax
  CStringPtr *v21; // r14
  int v22; // r15d
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // edx
  __int64 v28; // r8
  RStringPtr *v29; // rcx
  int v30; // [rsp+20h] [rbp-58h]
  CStringPtr *v31; // [rsp+40h] [rbp-38h]

  v7 = a3;
  if ( !a3 )
  {
    *a5 = 0;
    return 1;
  }
  v11 = *(unsigned int *)(a1 + 76);
  v12 = *(_QWORD *)(a1 + 64);
  v13 = v12 + 24LL * (a4 % ((int)v11 - 1));
  v14 = v12 + 24 * v11;
  while ( 1 )
  {
    v15 = *(_DWORD *)(v13 + 16);
    if ( v15 == -1 )
      break;
    if ( (_DWORD)v7 == v15 && !wcsncmp(*(const wchar_t **)(v13 + 8), a2, v7) )
    {
      *a5 = *(_DWORD *)v13;
      return 1;
    }
    v13 += 24;
    if ( v13 == v14 )
      v13 = *(_QWORD *)(a1 + 64);
  }
  if ( a6 )
  {
    if ( *(_DWORD *)(a1 + 88) > 0x80000u )
      return 3;
    v16 = *(_DWORD *)(a1 + 36);
    v17 = v16 + 1;
    if ( v16 + 1 < v16 )
      goto LABEL_34;
    if ( v17 > *(_DWORD *)(a1 + 32) )
    {
      _mm_lfence();
      _varray_base::_ensureCapacity_((_varray_base *)(a1 + 16), v17, 8u);
    }
    v18 = *(struct IMalloc **)(a1 + 8);
    v19 = (unsigned int)(v7 - 1);
    if ( v18 || (v18 = g_pMalloc) != 0 )
      v20 = (CStringPtr *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v18->lpVtbl->Alloc)(v18, 2 * v19 + 32);
    else
      v20 = (CStringPtr *)HeapAlloc(g_hHeap, 0, 2 * v19 + 32);
    v21 = v20;
    if ( !v20 )
    {
      MXRRaiseException(-2147024882);
      __debugbreak();
    }
    v31 = v20;
    CStringPtr::CStringPtr(v20, *(struct IMalloc **)(a1 + 8));
    *((_DWORD *)v21 + 4) = v7;
    if ( 2 * v7 < v7 )
    {
      MXRRaiseException(-2147467259);
      _mm_lfence();
      operator delete(v31, *(struct IMalloc **)(a1 + 8));
      MXRRaiseException(v30);
      JUMPOUT(0x1004130B7LL);
    }
    memmove((char *)v21 + 24, a2, 2 * v7);
    v22 = *(_DWORD *)(a1 + 36);
    *a5 = v22;
    if ( *(_DWORD *)(a1 + 80) == *(_DWORD *)(a1 + 72) )
      _htablesx::grow((_htablesx *)(a1 + 48));
    v23 = *(unsigned int *)(a1 + 76);
    v24 = *(_QWORD *)(a1 + 64);
    v25 = v24 + 24LL * (a4 % ((int)v23 - 1));
    while ( *(_DWORD *)(v25 + 16) != -1 )
    {
      v25 += 24;
      if ( v25 == v24 + 24 * v23 )
        v25 = *(_QWORD *)(a1 + 64);
    }
    *(_DWORD *)v25 = v22;
    *(_QWORD *)(v25 + 8) = (char *)v21 + 24;
    *(_DWORD *)(v25 + 16) = v7;
    *(_DWORD *)(v25 + 20) = a4;
    ++*(_DWORD *)(a1 + 72);
    v26 = *(_DWORD *)(a1 + 36);
    v27 = v26 + 1;
    if ( v26 + 1 < v26 )
    {
LABEL_34:
      MXRRaiseException(-2147352566);
      __debugbreak();
    }
    _mm_lfence();
    if ( v27 > *(_DWORD *)(a1 + 32) )
    {
      _mm_lfence();
      _varray_base::_ensureCapacity_((_varray_base *)(a1 + 16), v27, 8u);
    }
    v28 = *(unsigned int *)(a1 + 36);
    v29 = (RStringPtr *)(*(_QWORD *)(a1 + 40) + 8 * v28);
    *(_DWORD *)(a1 + 36) = v28 + 1;
    RStringPtr::assign(v29, v21);
    *(_DWORD *)(a1 + 88) += v7;
  }
  return 2;
}

```

## disassembly

```asm
0x100412e30  mov     [rsp+arg_8], rbx
0x100412e35  mov     [rsp+arg_10], rsi
0x100412e3a  mov     [rsp+arg_0], rcx
0x100412e3f  push    rdi
0x100412e40  push    r12
0x100412e42  push    r13
0x100412e44  push    r14
0x100412e46  push    r15
0x100412e48  sub     rsp, 50h
0x100412e4c  mov     r12d, r9d
0x100412e4f  mov     esi, r8d
0x100412e52  mov     r15, rdx
0x100412e55  mov     rdi, rcx
0x100412e58  test    r8d, r8d
0x100412e5b  jnz     short loc_100412E71
0x100412e5d  mov     rax, [rsp+78h+arg_20]
0x100412e65  mov     [rax], r8d
0x100412e68  lea     eax, [r8+1]
0x100412e6c  jmp     loc_100413059
0x100412e71  mov     r9d, [rcx+4Ch]
0x100412e75  mov     r8, [rcx+40h]
0x100412e79  lea     ecx, [r9-1]
0x100412e7d  xor     edx, edx
0x100412e7f  mov     eax, r12d
0x100412e82  div     ecx
0x100412e84  lea     rax, [rdx+rdx*2]
0x100412e88  lea     rbx, [r8+rax*8]
0x100412e8c  lea     rax, [r9+r9*2]
0x100412e90  lea     r14, [r8+rax*8]
0x100412e94  mov     eax, [rbx+10h]
0x100412e97  cmp     eax, 0FFFFFFFFh
0x100412e9a  jz      short loc_100412ED8
0x100412e9c  cmp     esi, eax
0x100412e9e  jnz     short loc_100412EB3
0x100412ea0  mov     r8, rsi; MaxCount
0x100412ea3  mov     rdx, r15; String2
0x100412ea6  mov     rcx, [rbx+8]; String1
0x100412eaa  call    wcsncmp
0x100412eaf  test    eax, eax
0x100412eb1  jz      short loc_100412EC2
0x100412eb3  add     rbx, 18h
0x100412eb7  cmp     rbx, r14
0x100412eba  jnz     short loc_100412E94
0x100412ebc  mov     rbx, [rdi+40h]
0x100412ec0  jmp     short loc_100412E94
0x100412ec2  mov     ecx, [rbx]
0x100412ec4  mov     rax, [rsp+78h+arg_20]
0x100412ecc  mov     [rax], ecx
0x100412ece  mov     eax, 1
0x100412ed3  jmp     loc_100413059
0x100412ed8  cmp     [rsp+78h+arg_28], 0
0x100412ee0  jz      loc_100413054
0x100412ee6  cmp     dword ptr [rdi+58h], 80000h
0x100412eed  jbe     short loc_100412EF9
0x100412eef  mov     eax, 3
0x100412ef4  jmp     loc_100413059
0x100412ef9  lea     rcx, [rdi+10h]; this
0x100412efd  mov     eax, [rcx+14h]
0x100412f00  lea     edx, [rax+1]; unsigned int
0x100412f03  cmp     edx, eax
0x100412f05  jb      loc_100413073
0x100412f0b  cmp     edx, [rcx+10h]
0x100412f0e  jbe     short loc_100412F1E
0x100412f10  lfence
0x100412f13  mov     r8d, 8; unsigned __int64
0x100412f19  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100412f1e  mov     rcx, [rdi+8]
0x100412f22  lea     eax, [rsi-1]
0x100412f25  lea     r8, ds:20h[rax*2]; dwBytes
0x100412f2d  test    rcx, rcx
0x100412f30  jz      short loc_100412F44
0x100412f32  mov     rax, [rcx]
0x100412f35  mov     rdx, r8
0x100412f38  mov     rax, [rax+18h]
0x100412f3c  call    cs:__guard_dispatch_icall_fptr
0x100412f42  jmp     short loc_100412F5F
0x100412f44  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100412f4b  test    rcx, rcx
0x100412f4e  jnz     short loc_100412F32
0x100412f50  xor     edx, edx; dwFlags
0x100412f52  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100412f59  call    cs:__imp_HeapAlloc
0x100412f5f  mov     r14, rax
0x100412f62  test    rax, rax
0x100412f65  jz      loc_10041307E
0x100412f6b  mov     [rsp+78h+var_38], r14
0x100412f70  mov     rdx, [rdi+8]; struct IMalloc *
0x100412f74  mov     rcx, r14; this
0x100412f77  call    ??0CStringPtr@@QEAA@PEAUIMalloc@@@Z; CStringPtr::CStringPtr(IMalloc *)
0x100412f7c  mov     [r14+10h], esi
0x100412f80  lea     r8, [rsi+rsi]; Size
0x100412f84  cmp     r8, rsi
0x100412f87  jb      loc_100413089
0x100412f8d  lea     rbx, [r14+18h]
0x100412f91  mov     rdx, r15; Src
0x100412f94  mov     rcx, rbx; void *
0x100412f97  call    memmove
0x100412f9c  mov     r15d, [rdi+24h]
0x100412fa0  mov     rax, [rsp+78h+arg_20]
0x100412fa8  mov     [rax], r15d
0x100412fab  mov     eax, [rdi+48h]
0x100412fae  cmp     [rdi+50h], eax
0x100412fb1  jnz     short loc_100412FBC
0x100412fb3  lea     rcx, [rdi+30h]; this
0x100412fb7  call    ?grow@_htablesx@@AEAAXXZ; _htablesx::grow(void)
0x100412fbc  mov     r8d, [rdi+4Ch]
0x100412fc0  mov     r9, [rdi+40h]
0x100412fc4  lea     ecx, [r8-1]
0x100412fc8  xor     edx, edx
0x100412fca  mov     eax, r12d
0x100412fcd  div     ecx
0x100412fcf  lea     rax, [rdx+rdx*2]
0x100412fd3  lea     rcx, [r9+rax*8]
0x100412fd7  mov     [rsp+78h+var_48], rcx
0x100412fdc  lea     rax, [r8+r8*2]
0x100412fe0  lea     rdx, [r9+rax*8]
0x100412fe4  cmp     dword ptr [rcx+10h], 0FFFFFFFFh
0x100412fe8  jz      short loc_100413001
0x100412fea  add     rcx, 18h
0x100412fee  mov     [rsp+78h+var_48], rcx
0x100412ff3  cmp     rcx, rdx
0x100412ff6  cmovz   rcx, r9
0x100412ffa  mov     [rsp+78h+var_48], rcx
0x100412fff  jmp     short loc_100412FE4
0x100413001  mov     [rcx], r15d
0x100413004  mov     [rcx+8], rbx
0x100413008  mov     [rcx+10h], esi
0x10041300b  mov     [rcx+14h], r12d
0x10041300f  inc     dword ptr [rdi+48h]
0x100413012  mov     eax, [rdi+24h]
0x100413015  lea     edx, [rax+1]; unsigned int
0x100413018  cmp     edx, eax
0x10041301a  jb      short loc_100413073
0x10041301c  lfence
0x10041301f  cmp     edx, [rdi+20h]
0x100413022  jbe     short loc_100413036
0x100413024  lfence
0x100413027  mov     r8d, 8; unsigned __int64
0x10041302d  lea     rcx, [rdi+10h]; this
0x100413031  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x100413036  mov     r8d, [rdi+24h]
0x10041303a  mov     rax, [rdi+28h]
0x10041303e  lea     rcx, [rax+r8*8]; this
0x100413042  lea     eax, [r8+1]
0x100413046  mov     [rdi+24h], eax
0x100413049  mov     rdx, r14; struct CStringPtr *
0x10041304c  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x100413051  add     [rdi+58h], esi
0x100413054  mov     eax, 2
0x100413059  lea     r11, [rsp+78h+var_28]
0x10041305e  mov     rbx, [r11+38h]
0x100413062  mov     rsi, [r11+40h]
0x100413066  mov     rsp, r11
0x100413069  pop     r15
0x10041306b  pop     r14
0x10041306d  pop     r13
0x10041306f  pop     r12
0x100413071  pop     rdi
0x100413072  retn
0x100413073  mov     ecx, 8002000Ah; int
0x100413078  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041307d  int     3; Trap to Debugger
0x10041307e  mov     ecx, 8007000Eh; int
0x100413083  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100413088  int     3; Trap to Debugger
0x100413089  mov     ecx, 80004005h; int
0x10041308e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100413093  nop
0x100413094  lfence
0x100413097  mov     rdx, [rsp+78h+arg_0]
0x10041309f  mov     rdx, [rdx+8]; struct IMalloc *
0x1004130a3  mov     rcx, [rsp+78h+var_38]; void *
0x1004130a8  call    ??3@YAXPEAXPEAUIMalloc@@@Z; operator delete(void *,IMalloc *)
0x1004130ad  mov     ecx, [rsp+78h+var_58]; int
0x1004130b1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004130b6  nop
0x100424f90  push    rbp
0x100424f92  sub     rsp, 20h
0x100424f96  mov     rbp, rdx
0x100424f99  mov     [rbp+48h], rcx
0x100424f9d  mov     [rbp+38h], rcx
0x100424fa1  mov     rax, [rbp+38h]
0x100424fa5  mov     rcx, [rax]
0x100424fa8  mov     [rbp+28h], rcx
0x100424fac  mov     rax, [rbp+28h]
0x100424fb0  mov     eax, [rax]
0x100424fb2  cmp     eax, 0C0000005h
0x100424fb7  jz      short loc_100424FE9
0x100424fb9  add     eax, 1FFFFFFFh
0x100424fbe  cmp     eax, 1
0x100424fc1  ja      short loc_100424FD9
0x100424fc3  mov     rax, [rbp+28h]
0x100424fc7  cmp     dword ptr [rax+18h], 1
0x100424fcb  jnz     short loc_100424FD9
0x100424fcd  mov     rax, [rbp+28h]
0x100424fd1  mov     ecx, [rax+20h]
0x100424fd4  mov     [rbp+20h], ecx
0x100424fd7  jmp     short loc_100424FE0
0x100424fd9  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424fe0  mov     dword ptr [rbp+24h], 1
0x100424fe7  jmp     short loc_100424FF0
0x100424fe9  mov     dword ptr [rbp+24h], 0
0x100424ff0  mov     eax, [rbp+24h]
0x100424ff3  add     rsp, 20h
0x100424ff7  pop     rbp
0x100424ff8  retn
```
