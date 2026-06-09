# CASFScriptCommandObject::Clone(void)

- ea: `0x180019f40`
- end: `0x18001a1f8`
- name: `?Clone@CASFScriptCommandObject@@UEAAPEAVCASFLonghandObject@@XZ`
- size: `696`
- prototype: `struct CASFLonghandObject *__fastcall(CASFScriptCommandObject *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011a0`
- `0x1800011ec`
- `0x180001f1c`
- `0x18000774c`
- `0x180019f40`
- `0x18002b010`

## pseudocode

```c
struct CASFLonghandObject *__fastcall CASFScriptCommandObject::Clone(CASFScriptCommandObject *this)
{
  struct CASFLonghandObject *result; // rax
  struct CASFLonghandObject *v3; // rbx
  _QWORD *v4; // r15
  int v5; // esi
  __int128 v6; // xmm0
  void *v7; // rax
  unsigned int i; // ebp
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // kr00_8
  unsigned __int16 *v14; // rcx
  void *v15; // rax
  unsigned int j; // ebp
  __int64 v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // kr10_8
  unsigned __int16 *v23; // rcx

  result = (struct CASFLonghandObject *)operator new(0x60u);
  v3 = result;
  if ( result )
  {
    *((_QWORD *)result + 5) = 0;
    *((_QWORD *)result + 6) = 1;
    v4 = (_QWORD *)((char *)result + 80);
    *(_QWORD *)result = &CASFScriptCommandObject::`vftable';
    v5 = 0;
    *((_QWORD *)result + 1) = 116;
    *((_DWORD *)result + 18) = 0;
    *((GUID *)result + 1) = CLSID_CAsfScriptCommandObjectV0;
    *((_QWORD *)result + 10) = 0;
    *((_QWORD *)result + 11) = 0;
    *((_DWORD *)result + 2) = *((_DWORD *)this + 2);
    *((_DWORD *)result + 3) = *((_DWORD *)this + 3);
    *((_OWORD *)result + 1) = *((_OWORD *)this + 1);
    *((_QWORD *)result + 4) = *((_QWORD *)this + 4);
    *((_QWORD *)result + 5) = *((_QWORD *)this + 5);
    *((_DWORD *)result + 12) = *((_DWORD *)this + 12);
    *((_DWORD *)result + 13) = *((_DWORD *)this + 13);
    *((_DWORD *)result + 12) = 1;
    v6 = *(_OWORD *)((char *)this + 56);
    *((_QWORD *)this + 5) = 0;
    *(_OWORD *)((char *)result + 56) = v6;
    *((_WORD *)result + 37) = *((_WORD *)this + 37);
    if ( *((_WORD *)this + 37) )
    {
      v7 = operator new[](saturated_mul(*((unsigned __int16 *)this + 37), 8u));
      *v4 = v7;
      if ( !v7 )
        goto LABEL_36;
      memset_0(v7, 0, 8LL * *((unsigned __int16 *)this + 37));
      for ( i = 0; i < *((unsigned __int16 *)this + 37); ++i )
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * i);
        if ( v9 )
        {
          v10 = -1;
          do
            ++v10;
          while ( *(_WORD *)(v9 + 2 * v10) );
          v11 = v10 + 1;
          v13 = v10 + 1;
          v12 = 2 * (v10 + 1);
          if ( !is_mul_ok(v13, 2u) )
            v12 = -1;
          *(_QWORD *)(*v4 + 8LL * i) = operator new[](v12);
          v14 = *(unsigned __int16 **)(*v4 + 8LL * i);
          if ( !v14 )
          {
            v5 = -2147024882;
            break;
          }
          v5 = StringCchCopyW(v14, v11, *(unsigned __int16 **)(*((_QWORD *)this + 10) + 8LL * i));
          if ( v5 < 0 )
            goto LABEL_36;
        }
        else
        {
          *(_QWORD *)(*v4 + 8LL * i) = 0;
        }
      }
      if ( v5 < 0 )
        goto LABEL_36;
    }
    else
    {
      *v4 = 0;
    }
    *((_WORD *)v3 + 36) = *((_WORD *)this + 36);
    if ( !*((_WORD *)this + 36) )
    {
      *((_QWORD *)v3 + 11) = 0;
      return v3;
    }
    v15 = operator new[](saturated_mul(*((unsigned __int16 *)this + 36), 0xEu));
    *((_QWORD *)v3 + 11) = v15;
    if ( v15 )
    {
      memset_0(v15, 0, 14LL * *((unsigned __int16 *)this + 36));
      for ( j = 0; j < *((unsigned __int16 *)this + 36); ++j )
      {
        v17 = 14LL * j;
        *(_DWORD *)(v17 + *((_QWORD *)v3 + 11)) = *(_DWORD *)(v17 + *((_QWORD *)this + 11));
        *(_WORD *)(v17 + *((_QWORD *)v3 + 11) + 4) = *(_WORD *)(v17 + *((_QWORD *)this + 11) + 4);
        v18 = *(_QWORD *)(v17 + *((_QWORD *)this + 11) + 6);
        if ( v18 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(v18 + 2 * v19) );
          v20 = v19 + 1;
          v22 = v19 + 1;
          v21 = 2 * (v19 + 1);
          if ( !is_mul_ok(v22, 2u) )
            v21 = -1;
          *(_QWORD *)(v17 + *((_QWORD *)v3 + 11) + 6) = operator new[](v21);
          v23 = *(unsigned __int16 **)(v17 + *((_QWORD *)v3 + 11) + 6);
          if ( !v23 )
          {
            v5 = -2147024882;
            break;
          }
          v5 = StringCchCopyW(v23, v20, *(unsigned __int16 **)(v17 + *((_QWORD *)this + 11) + 6));
          if ( v5 < 0 )
            goto LABEL_36;
        }
        else
        {
          *(_QWORD *)(v17 + *((_QWORD *)v3 + 11) + 6) = 0;
        }
      }
      if ( v5 >= 0 )
        return v3;
    }
LABEL_36:
    (**(void (__fastcall ***)(struct CASFLonghandObject *, __int64))v3)(v3, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019f40  push    rbx
0x180019f42  push    rbp
0x180019f43  push    rsi
0x180019f44  push    rdi
0x180019f45  push    r12
0x180019f47  push    r13
0x180019f49  push    r14
0x180019f4b  push    r15
0x180019f4d  sub     rsp, 28h
0x180019f51  mov     rdi, rcx
0x180019f54  mov     ecx, 60h ; '`'; Size
0x180019f59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019f5e  xor     r12d, r12d
0x180019f61  mov     rbx, rax
0x180019f64  test    rax, rax
0x180019f67  jz      loc_18001A1E7
0x180019f6d  mov     [rax+28h], r12
0x180019f71  lea     ecx, [r12+1]
0x180019f76  mov     [rax+30h], rcx
0x180019f7a  lea     r15, [rbx+50h]
0x180019f7e  lea     rax, ??_7CASFScriptCommandObject@@6B@; const CASFScriptCommandObject::`vftable'
0x180019f85  or      r13, 0FFFFFFFFFFFFFFFFh
0x180019f89  mov     [rbx], rax
0x180019f8c  mov     esi, r12d
0x180019f8f  movups  xmm0, xmmword ptr cs:CLSID_CAsfScriptCommandObjectV0.Data1
0x180019f96  mov     qword ptr [rbx+8], 74h ; 't'
0x180019f9e  mov     [rbx+48h], r12d
0x180019fa2  movdqu  xmmword ptr [rbx+10h], xmm0
0x180019fa7  mov     [rbx+50h], r12
0x180019fab  mov     [rbx+58h], r12
0x180019faf  mov     eax, [rdi+8]
0x180019fb2  mov     [rbx+8], eax
0x180019fb5  mov     eax, [rdi+0Ch]
0x180019fb8  mov     [rbx+0Ch], eax
0x180019fbb  movups  xmm0, xmmword ptr [rdi+10h]
0x180019fbf  movdqu  xmmword ptr [rbx+10h], xmm0
0x180019fc4  mov     rax, [rdi+20h]
0x180019fc8  mov     [rbx+20h], rax
0x180019fcc  mov     rax, [rdi+28h]
0x180019fd0  mov     [rbx+28h], rax
0x180019fd4  mov     eax, [rdi+30h]
0x180019fd7  mov     [rbx+30h], eax
0x180019fda  mov     eax, [rdi+34h]
0x180019fdd  mov     [rbx+34h], eax
0x180019fe0  mov     [rbx+30h], ecx
0x180019fe3  movups  xmm0, xmmword ptr [rdi+38h]
0x180019fe7  mov     [rdi+28h], r12
0x180019feb  movdqu  xmmword ptr [rbx+38h], xmm0
0x180019ff0  movzx   eax, word ptr [rdi+4Ah]
0x180019ff4  mov     [rbx+4Ah], ax
0x180019ff8  cmp     [rdi+4Ah], r12w
0x180019ffd  jz      loc_18001A0C6
0x18001a003  movzx   ecx, word ptr [rdi+4Ah]
0x18001a007  lea     eax, [r12+8]
0x18001a00c  mul     rcx
0x18001a00f  cmovb   rax, r13
0x18001a013  mov     rcx, rax; unsigned __int64
0x18001a016  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a01b  mov     [r15], rax
0x18001a01e  test    rax, rax
0x18001a021  jz      loc_18001A1C8
0x18001a027  movzx   r8d, word ptr [rdi+4Ah]
0x18001a02c  xor     edx, edx; Val
0x18001a02e  shl     r8, 3; Size
0x18001a032  mov     rcx, rax; void *
0x18001a035  call    memset_0
0x18001a03a  mov     ebp, r12d
0x18001a03d  movzx   eax, word ptr [rdi+4Ah]
0x18001a041  cmp     ebp, eax
0x18001a043  jnb     short loc_18001A0BC
0x18001a045  mov     rax, [rdi+50h]
0x18001a049  mov     r14d, ebp
0x18001a04c  mov     rcx, [rax+r14*8]
0x18001a050  test    rcx, rcx
0x18001a053  jz      short loc_18001A0AC
0x18001a055  mov     rax, r13
0x18001a058  inc     rax
0x18001a05b  cmp     [rcx+rax*2], r12w
0x18001a060  jnz     short loc_18001A058
0x18001a062  lea     rsi, [rax+1]
0x18001a066  mov     eax, 2
0x18001a06b  mul     rsi
0x18001a06e  cmovb   rax, r13
0x18001a072  mov     rcx, rax; unsigned __int64
0x18001a075  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a07a  mov     rcx, rax
0x18001a07d  mov     rax, [r15]
0x18001a080  mov     [rax+r14*8], rcx
0x18001a084  mov     rax, [r15]
0x18001a087  mov     rcx, [rax+r14*8]; unsigned __int16 *
0x18001a08b  test    rcx, rcx
0x18001a08e  jz      short loc_18001A0B7
0x18001a090  mov     r8, [rdi+50h]
0x18001a094  mov     rdx, rsi; unsigned __int64
0x18001a097  mov     r8, [r8+r14*8]; unsigned __int16 *
0x18001a09b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a0a0  mov     esi, eax
0x18001a0a2  test    eax, eax
0x18001a0a4  js      loc_18001A1C8
0x18001a0aa  jmp     short loc_18001A0B3
0x18001a0ac  mov     rax, [r15]
0x18001a0af  mov     [rax+r14*8], r12
0x18001a0b3  inc     ebp
0x18001a0b5  jmp     short loc_18001A03D
0x18001a0b7  mov     esi, 8007000Eh
0x18001a0bc  test    esi, esi
0x18001a0be  js      loc_18001A1C8
0x18001a0c4  jmp     short loc_18001A0C9
0x18001a0c6  mov     [r15], r12
0x18001a0c9  movzx   eax, word ptr [rdi+48h]
0x18001a0cd  mov     [rbx+48h], ax
0x18001a0d1  cmp     [rdi+48h], r12w
0x18001a0d6  jz      loc_18001A1E0
0x18001a0dc  movzx   ecx, word ptr [rdi+48h]
0x18001a0e0  mov     eax, 0Eh
0x18001a0e5  mul     rcx
0x18001a0e8  cmovb   rax, r13
0x18001a0ec  mov     rcx, rax; unsigned __int64
0x18001a0ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a0f4  mov     [rbx+58h], rax
0x18001a0f8  test    rax, rax
0x18001a0fb  jz      loc_18001A1C8
0x18001a101  movzx   ecx, word ptr [rdi+48h]
0x18001a105  xor     edx, edx; Val
0x18001a107  imul    r8, rcx, 0Eh; Size
0x18001a10b  mov     rcx, rax; void *
0x18001a10e  call    memset_0
0x18001a113  mov     ebp, r12d
0x18001a116  movzx   eax, word ptr [rdi+48h]
0x18001a11a  cmp     ebp, eax
0x18001a11c  jnb     loc_18001A1C4
0x18001a122  mov     rcx, [rbx+58h]
0x18001a126  mov     eax, ebp
0x18001a128  imul    r14, rax, 0Eh
0x18001a12c  mov     rax, [rdi+58h]
0x18001a130  mov     eax, [r14+rax]
0x18001a134  mov     [r14+rcx], eax
0x18001a138  mov     rax, [rdi+58h]
0x18001a13c  mov     rcx, [rbx+58h]
0x18001a140  movzx   eax, word ptr [r14+rax+4]
0x18001a146  mov     [r14+rcx+4], ax
0x18001a14c  mov     rax, [rdi+58h]
0x18001a150  mov     rcx, [r14+rax+6]
0x18001a155  test    rcx, rcx
0x18001a158  jz      short loc_18001A1AF
0x18001a15a  mov     rax, r13
0x18001a15d  inc     rax
0x18001a160  cmp     [rcx+rax*2], r12w
0x18001a165  jnz     short loc_18001A15D
0x18001a167  lea     rsi, [rax+1]
0x18001a16b  mov     eax, 2
0x18001a170  mul     rsi
0x18001a173  cmovb   rax, r13
0x18001a177  mov     rcx, rax; unsigned __int64
0x18001a17a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a17f  mov     rcx, [rbx+58h]
0x18001a183  mov     [r14+rcx+6], rax
0x18001a188  mov     rax, [rbx+58h]
0x18001a18c  mov     rcx, [r14+rax+6]; unsigned __int16 *
0x18001a191  test    rcx, rcx
0x18001a194  jz      short loc_18001A1BF
0x18001a196  mov     r8, [rdi+58h]
0x18001a19a  mov     rdx, rsi; unsigned __int64
0x18001a19d  mov     r8, [r14+r8+6]; unsigned __int16 *
0x18001a1a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a1a7  mov     esi, eax
0x18001a1a9  test    eax, eax
0x18001a1ab  js      short loc_18001A1C8
0x18001a1ad  jmp     short loc_18001A1B8
0x18001a1af  mov     rax, [rbx+58h]
0x18001a1b3  mov     [r14+rax+6], r12
0x18001a1b8  inc     ebp
0x18001a1ba  jmp     loc_18001A116
0x18001a1bf  mov     esi, 8007000Eh
0x18001a1c4  test    esi, esi
0x18001a1c6  jns     short loc_18001A1E4
0x18001a1c8  mov     rax, [rbx]
0x18001a1cb  mov     edx, 1
0x18001a1d0  mov     rcx, rbx
0x18001a1d3  mov     rax, [rax]
0x18001a1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1db  mov     rbx, r12
0x18001a1de  jmp     short loc_18001A1E4
0x18001a1e0  mov     [rbx+58h], r12
0x18001a1e4  mov     rax, rbx
0x18001a1e7  add     rsp, 28h
0x18001a1eb  pop     r15
0x18001a1ed  pop     r14
0x18001a1ef  pop     r13
0x18001a1f1  pop     r12
0x18001a1f3  pop     rdi
0x18001a1f4  pop     rsi
0x18001a1f5  pop     rbp
0x18001a1f6  pop     rbx
0x18001a1f7  retn
```
