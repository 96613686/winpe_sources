# CASFScriptCommandObject::Restore(CASFArchive &)

- ea: `0x1800230f0`
- end: `0x180023452`
- name: `?Restore@CASFScriptCommandObject@@UEAAJAEAVCASFArchive@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(CASFScriptCommandObject *__hidden this, struct CASFArchive *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800011ec`
- `0x1800015f0`
- `0x180001f1c`
- `0x1800181fc`
- `0x18001d148`
- `0x18001d340`
- `0x18001d39c`
- `0x18001d484`
- `0x180022980`
- `0x1800230f0`
- `0x18002b010`

## pseudocode

```c
signed int __fastcall CASFScriptCommandObject::Restore(CASFScriptCommandObject *this, struct CASFArchive *a2)
{
  signed int result; // eax
  _WORD *v5; // r12
  _WORD *v6; // r14
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  void *v9; // rax
  unsigned int i; // r15d
  __int64 v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int8 *v13; // rdx
  void *v14; // rax
  unsigned int j; // r15d
  __int64 v16; // rdx
  __int64 v17; // rsi
  __int64 v18; // r13
  unsigned __int64 v19; // rax
  unsigned __int8 *v20; // rdx
  unsigned __int64 v21; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 v22; // [rsp+28h] [rbp-18h] BYREF

  CASFScriptCommandObject::Clear(this);
  result = CASFLonghandObject::Restore(this, a2);
  if ( result >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(CASFScriptCommandObject *))(*(_QWORD *)this + 32LL))(this) - 24;
    result = CASFArchive::LoadGUID(a2, (struct _GUID *)((char *)this + 56), &v21);
    if ( result >= 0 )
    {
      v5 = (_WORD *)((char *)this + 72);
      result = CASFArchive::LoadWORD(a2, (unsigned __int16 *)this + 36, &v21);
      if ( result >= 0 )
      {
        v6 = (_WORD *)((char *)this + 74);
        result = CASFArchive::LoadWORD(a2, (unsigned __int16 *)this + 37, &v21);
        if ( result >= 0 )
        {
          v7 = (unsigned __int16)*v6;
          v8 = v21;
          if ( v21 < 2 * v7 )
            return -1072887838;
          v9 = operator new[](saturated_mul(v7, 8u));
          *((_QWORD *)this + 10) = v9;
          if ( !v9 )
          {
            *v6 = 0;
            return -2147024882;
          }
          memset_0(v9, 0, 8LL * (unsigned __int16)*v6);
          for ( i = 0; i < (unsigned __int16)*v6; ++i )
          {
            v22 = 0;
            result = CASFArchive::LoadWORD(a2, &v22, &v21);
            if ( result < 0 )
              return result;
            if ( v22 )
            {
              v11 = v22;
              if ( v21 < v22 )
                return -1072887838;
              v12 = 2LL * ((unsigned int)v22 + 1);
              if ( !is_mul_ok((unsigned int)v22 + 1, 2u) )
                v12 = -1;
              *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * i) = operator new[](v12);
              v13 = *(unsigned __int8 **)(*((_QWORD *)this + 10) + 8LL * i);
              if ( !v13 )
                return -2147024882;
              result = CASFArchive::LoadBytes(a2, v13, 2 * v11, &v21);
              if ( result < 0 )
                return result;
              *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * i) + 2 * v11) = 0;
            }
            else
            {
              *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * i) = 0;
            }
            v8 = v21;
          }
          if ( v8 < 8 * (unsigned __int64)(unsigned __int16)*v5 )
          {
            return -1072887838;
          }
          else
          {
            v14 = operator new[](saturated_mul((unsigned __int16)*v5, 0xEu));
            *((_QWORD *)this + 11) = v14;
            if ( !v14 )
            {
              *v5 = 0;
              return -2147024882;
            }
            memset_0(v14, 0, 14LL * (unsigned __int16)*v5);
            for ( j = 0; j < (unsigned __int16)*v5; ++j )
            {
              v16 = *((_QWORD *)this + 11);
              v17 = 14LL * j;
              v22 = 0;
              result = CASFArchive::LoadDWORD(a2, (unsigned int *)(v17 + v16), &v21);
              if ( result < 0 )
                return result;
              result = CASFArchive::LoadWORD(a2, (unsigned __int16 *)(v17 + *((_QWORD *)this + 11) + 4LL), &v21);
              if ( result < 0 )
                return result;
              if ( *(_WORD *)(*((_QWORD *)this + 11) + v17 + 4) >= *v6 )
                return -1072887838;
              result = CASFArchive::LoadWORD(a2, &v22, &v21);
              if ( result < 0 )
                return result;
              if ( v22 )
              {
                v18 = v22;
                if ( v21 < v22 )
                  return -1072887838;
                v19 = 2LL * ((unsigned int)v22 + 1);
                if ( !is_mul_ok((unsigned int)v22 + 1, 2u) )
                  v19 = -1;
                *(_QWORD *)(*((_QWORD *)this + 11) + v17 + 6) = operator new[](v19);
                v20 = *(unsigned __int8 **)(*((_QWORD *)this + 11) + v17 + 6);
                if ( !v20 )
                  return -2147024882;
                result = CASFArchive::LoadBytes(a2, v20, 2 * v18, &v21);
                if ( result < 0 )
                  return result;
                *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + v17 + 6) + 2 * v18) = 0;
              }
              else
              {
                *(_QWORD *)(*((_QWORD *)this + 11) + v17 + 6) = 0;
              }
              v8 = v21;
            }
            return v8 != 0 ? 0xC00D07E2 : 0;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800230f0  mov     [rsp-38h+arg_10], rbx
0x1800230f5  push    rbp
0x1800230f6  push    rsi
0x1800230f7  push    rdi
0x1800230f8  push    r12
0x1800230fa  push    r13
0x1800230fc  push    r14
0x1800230fe  push    r15
0x180023100  mov     rbp, rsp
0x180023103  sub     rsp, 40h
0x180023107  mov     rax, cs:__security_cookie
0x18002310e  xor     rax, rsp
0x180023111  mov     [rbp+var_10], rax
0x180023115  mov     rdi, rdx
0x180023118  mov     rbx, rcx
0x18002311b  call    ?Clear@CASFScriptCommandObject@@QEAAXXZ; CASFScriptCommandObject::Clear(void)
0x180023120  mov     rdx, rdi; struct CASFArchive *
0x180023123  mov     rcx, rbx; this
0x180023126  call    ?Restore@CASFLonghandObject@@UEAAJAEAVCASFArchive@@@Z; CASFLonghandObject::Restore(CASFArchive &)
0x18002312b  xor     r13d, r13d
0x18002312e  test    eax, eax
0x180023130  js      loc_18002342E
0x180023136  mov     rax, [rbx]
0x180023139  mov     rcx, rbx
0x18002313c  mov     rax, [rax+20h]
0x180023140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023145  sub     rax, 18h
0x180023149  lea     rdx, [rbx+38h]; struct _GUID *
0x18002314d  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180023151  mov     [rbp+var_20], rax
0x180023155  mov     rcx, rdi; this
0x180023158  call    ?LoadGUID@CASFArchive@@QEAAJAEAU_GUID@@PEA_K@Z; CASFArchive::LoadGUID(_GUID &,unsigned __int64 *)
0x18002315d  test    eax, eax
0x18002315f  js      loc_18002342E
0x180023165  lea     r12, [rbx+48h]
0x180023169  mov     rcx, rdi; this
0x18002316c  mov     rdx, r12; unsigned __int16 *
0x18002316f  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180023173  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x180023178  test    eax, eax
0x18002317a  js      loc_18002342E
0x180023180  lea     r14, [rbx+4Ah]
0x180023184  mov     rcx, rdi; this
0x180023187  mov     rdx, r14; unsigned __int16 *
0x18002318a  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18002318e  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x180023193  test    eax, eax
0x180023195  js      loc_18002342E
0x18002319b  movzx   ecx, word ptr [r14]
0x18002319f  mov     rsi, [rbp+var_20]
0x1800231a3  lea     rax, [rcx+rcx]
0x1800231a7  cmp     rsi, rax
0x1800231aa  jb      loc_180023429
0x1800231b0  lea     eax, [r13+8]
0x1800231b4  mul     rcx
0x1800231b7  lea     rcx, [r13-1]
0x1800231bb  cmovb   rax, rcx
0x1800231bf  mov     rcx, rax; unsigned __int64
0x1800231c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800231c7  mov     [rbx+50h], rax
0x1800231cb  test    rax, rax
0x1800231ce  jnz     short loc_1800231DE
0x1800231d0  mov     [r14], r13w
0x1800231d4  mov     eax, 8007000Eh
0x1800231d9  jmp     loc_18002342E
0x1800231de  movzx   r8d, word ptr [r14]
0x1800231e2  xor     edx, edx; Val
0x1800231e4  shl     r8, 3; Size
0x1800231e8  mov     rcx, rax; void *
0x1800231eb  call    memset_0
0x1800231f0  mov     r15d, r13d
0x1800231f3  movzx   eax, word ptr [r14]
0x1800231f7  cmp     r15d, eax
0x1800231fa  jnb     loc_1800232AF
0x180023200  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180023204  mov     [rbp+var_18], r13w
0x180023209  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x18002320d  mov     rcx, rdi; this
0x180023210  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x180023215  test    eax, eax
0x180023217  js      loc_18002342E
0x18002321d  movzx   eax, [rbp+var_18]
0x180023221  test    ax, ax
0x180023224  jz      short loc_180023298
0x180023226  mov     esi, eax
0x180023228  cmp     [rbp+var_20], rax
0x18002322c  jb      loc_180023429
0x180023232  lea     ecx, [rax+1]
0x180023235  mov     eax, 2
0x18002323a  mul     rcx
0x18002323d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023244  cmovb   rax, rcx
0x180023248  mov     rcx, rax; unsigned __int64
0x18002324b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180023250  mov     rcx, [rbx+50h]
0x180023254  mov     r13d, r15d
0x180023257  mov     [rcx+r13*8], rax
0x18002325b  mov     rax, [rbx+50h]
0x18002325f  mov     rdx, [rax+r13*8]; unsigned __int8 *
0x180023263  test    rdx, rdx
0x180023266  jz      loc_1800231D4
0x18002326c  mov     r8d, esi
0x18002326f  lea     r9, [rbp+var_20]; unsigned __int64 *
0x180023273  add     r8d, r8d; unsigned int
0x180023276  mov     rcx, rdi; this
0x180023279  call    ?LoadBytes@CASFArchive@@QEAAJPEAEKPEA_K@Z; CASFArchive::LoadBytes(uchar *,ulong,unsigned __int64 *)
0x18002327e  test    eax, eax
0x180023280  js      loc_18002342E
0x180023286  mov     rax, [rbx+50h]
0x18002328a  mov     rcx, [rax+r13*8]
0x18002328e  xor     r13d, r13d
0x180023291  mov     [rcx+rsi*2], r13w
0x180023296  jmp     short loc_1800232A3
0x180023298  mov     rax, [rbx+50h]
0x18002329c  mov     ecx, r15d
0x18002329f  mov     [rax+rcx*8], r13
0x1800232a3  mov     rsi, [rbp+var_20]
0x1800232a7  inc     r15d
0x1800232aa  jmp     loc_1800231F3
0x1800232af  movzx   ecx, word ptr [r12]
0x1800232b4  lea     rax, ds:0[rcx*8]
0x1800232bc  cmp     rsi, rax
0x1800232bf  jb      loc_180023429
0x1800232c5  mov     eax, 0Eh
0x1800232ca  mul     rcx
0x1800232cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800232d4  cmovb   rax, rcx
0x1800232d8  mov     rcx, rax; unsigned __int64
0x1800232db  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800232e0  mov     [rbx+58h], rax
0x1800232e4  mov     rcx, rax; void *
0x1800232e7  test    rax, rax
0x1800232ea  jnz     short loc_1800232F6
0x1800232ec  mov     [r12], r13w
0x1800232f1  jmp     loc_1800231D4
0x1800232f6  movzx   eax, word ptr [r12]
0x1800232fb  xor     edx, edx; Val
0x1800232fd  imul    r8, rax, 0Eh; Size
0x180023301  call    memset_0
0x180023306  mov     r15d, r13d
0x180023309  movzx   eax, word ptr [r12]
0x18002330e  cmp     r15d, eax
0x180023311  jnb     loc_180023417
0x180023317  mov     rdx, [rbx+58h]
0x18002331b  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18002331f  mov     eax, r15d
0x180023322  mov     rcx, rdi; this
0x180023325  imul    rsi, rax, 0Eh
0x180023329  mov     [rbp+var_18], r13w
0x18002332e  add     rdx, rsi; unsigned int *
0x180023331  call    ?LoadDWORD@CASFArchive@@QEAAJAEAKPEA_K@Z; CASFArchive::LoadDWORD(ulong &,unsigned __int64 *)
0x180023336  test    eax, eax
0x180023338  js      loc_18002342E
0x18002333e  mov     rdx, [rbx+58h]
0x180023342  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180023346  add     rdx, 4
0x18002334a  mov     rcx, rdi; this
0x18002334d  add     rdx, rsi; unsigned __int16 *
0x180023350  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x180023355  test    eax, eax
0x180023357  js      loc_18002342E
0x18002335d  mov     rcx, [rbx+58h]
0x180023361  movzx   eax, word ptr [r14]
0x180023365  cmp     [rcx+rsi+4], ax
0x18002336a  jnb     loc_180023429
0x180023370  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180023374  mov     rcx, rdi; this
0x180023377  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x18002337b  call    ?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z; CASFArchive::LoadWORD(ushort &,unsigned __int64 *)
0x180023380  test    eax, eax
0x180023382  js      loc_18002342E
0x180023388  movzx   eax, [rbp+var_18]
0x18002338c  test    ax, ax
0x18002338f  jz      short loc_180023402
0x180023391  mov     r13d, eax
0x180023394  cmp     [rbp+var_20], rax
0x180023398  jb      loc_180023429
0x18002339e  lea     ecx, [rax+1]
0x1800233a1  mov     eax, 2
0x1800233a6  mul     rcx
0x1800233a9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800233b0  cmovb   rax, rcx
0x1800233b4  mov     rcx, rax; unsigned __int64
0x1800233b7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800233bc  mov     rcx, [rbx+58h]
0x1800233c0  mov     [rcx+rsi+6], rax
0x1800233c5  mov     rax, [rbx+58h]
0x1800233c9  mov     rdx, [rax+rsi+6]; unsigned __int8 *
0x1800233ce  test    rdx, rdx
0x1800233d1  jz      loc_1800231D4
0x1800233d7  mov     r8d, r13d
0x1800233da  lea     r9, [rbp+var_20]; unsigned __int64 *
0x1800233de  add     r8d, r8d; unsigned int
0x1800233e1  mov     rcx, rdi; this
0x1800233e4  call    ?LoadBytes@CASFArchive@@QEAAJPEAEKPEA_K@Z; CASFArchive::LoadBytes(uchar *,ulong,unsigned __int64 *)
0x1800233e9  xor     edx, edx
0x1800233eb  test    eax, eax
0x1800233ed  js      short loc_18002342E
0x1800233ef  mov     rax, [rbx+58h]
0x1800233f3  mov     rcx, [rax+rsi+6]
0x1800233f8  mov     [rcx+r13*2], dx
0x1800233fd  xor     r13d, r13d
0x180023400  jmp     short loc_18002340B
0x180023402  mov     rax, [rbx+58h]
0x180023406  mov     [rax+rsi+6], r13
0x18002340b  mov     rsi, [rbp+var_20]
0x18002340f  inc     r15d
0x180023412  jmp     loc_180023309
0x180023417  mov     rax, r13
0x18002341a  sub     rax, rsi
0x18002341d  neg     rax
0x180023420  sbb     eax, eax
0x180023422  and     eax, 0C00D07E2h
0x180023427  jmp     short loc_18002342E
0x180023429  mov     eax, 0C00D07E2h
0x18002342e  mov     rcx, [rbp+var_10]
0x180023432  xor     rcx, rsp; StackCookie
0x180023435  call    __security_check_cookie
0x18002343a  mov     rbx, [rsp+40h+arg_10]
0x180023442  add     rsp, 40h
0x180023446  pop     r15
0x180023448  pop     r14
0x18002344a  pop     r13
0x18002344c  pop     r12
0x18002344e  pop     rdi
0x18002344f  pop     rsi
0x180023450  pop     rbp
0x180023451  retn
```
