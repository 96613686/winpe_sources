# Scanner::CreateAndVerifyCharacterSource(InputSource *,Scanner::AutodetectInput *,uint)

- ea: `0x10040ee90`
- end: `0x10040f150`
- name: `?CreateAndVerifyCharacterSource@Scanner@@AEAA_NPEAVInputSource@@PEAVAutodetectInput@1@I@Z`
- size: `704`
- prototype: `bool __fastcall(Scanner *__hidden this, struct InputSource *, struct Scanner::AutodetectInput *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10040ded0`

## callees

- `0x100401780`
- `0x10040ca10`
- `0x10040ee90`
- `0x100418490`
- `0x1004186a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10040f04b`
- `KERNEL32!HeapFree` at `0x10040f04b`

## pseudocode

```c
bool __fastcall Scanner::CreateAndVerifyCharacterSource(
        Scanner *this,
        struct InputSource *a2,
        struct Scanner::AutodetectInput *a3,
        unsigned int a4)
{
  unsigned int v6; // edx
  struct IMalloc *v8; // rsi
  __int64 (__fastcall *Constructor)(struct IMalloc *, _QWORD); // rax
  MlangCharacterSource *MLangCharacterSource; // rax
  MlangCharacterSource *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rcx
  unsigned __int16 v18; // ax
  void *v19; // r8
  __int64 v20; // rsi
  struct IMalloc *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  __int64 v26; // rdx
  bool result; // al
  __int64 v28; // rcx
  unsigned int v29; // [rsp+60h] [rbp+8h] BYREF
  struct Scanner::AutodetectInput *v30; // [rsp+70h] [rbp+18h] BYREF

  v30 = a3;
  v6 = *((_DWORD *)this + 10);
  if ( v6 != -1 )
    ++v6;
  if ( *((_DWORD *)this + 11) < v6 )
  {
    _mm_lfence();
    _stack<void (Scanner::*)(void),8>::grow((__int64)this + 16, v6);
  }
  v8 = (struct IMalloc *)*((_QWORD *)this + 1);
  Constructor = (__int64 (__fastcall *)(struct IMalloc *, _QWORD))CharacterSourceFactory::FindConstructor(
                                                                    &CodeStringPtr::empty,
                                                                    a4,
                                                                    0xFFFFFFFFLL,
                                                                    &v30);
  if ( Constructor )
    MLangCharacterSource = (MlangCharacterSource *)Constructor(v8, (unsigned int)v30);
  else
    MLangCharacterSource = CharacterSourceFactory::CreateMLangCharacterSource(v8, (__int64)&CodeStringPtr::empty, a4);
  v11 = MLangCharacterSource;
  if ( !MLangCharacterSource )
  {
    MXRRaiseException(-1072894462);
    JUMPOUT(0x10040F14FLL);
  }
  *((_QWORD *)this + 8) = MLangCharacterSource;
  v12 = *((unsigned int *)this + 10);
  if ( *((_DWORD *)this + 11) == (_DWORD)v12 )
  {
    _stack<void (Scanner::*)(void),8>::grow((__int64)this + 16, 0);
    v12 = *((unsigned int *)this + 10);
  }
  *((_DWORD *)this + 10) = v12 + 1;
  *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v12) = v11;
  (*(void (__fastcall **)(_QWORD, struct InputSource *))(**((_QWORD **)this + 8) + 48LL))(*((_QWORD *)this + 8), a2);
  v13 = *((_QWORD *)this + 8);
  v14 = *((_DWORD *)this + 88) - *((_DWORD *)this + 86);
  v15 = *((_QWORD *)this + 40);
  v16 = *((unsigned int *)this + 82);
  *((_QWORD *)this + 40) = 0;
  *((_DWORD *)this + 82) = 0;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64, int))(*(_QWORD *)v13 + 56LL))(
    v13,
    v15,
    *((_QWORD *)this + 43),
    v16,
    v14);
  *((_DWORD *)this + 90) = 1;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  v17 = *((_QWORD *)this + 8);
  *(_QWORD *)(v17 + 56) = *(_QWORD *)(v17 + 48);
  *(_DWORD *)(v17 + 88) = 1;
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  if ( v18 == 60 || (*((_BYTE *)(&g_apCharTables)[(unsigned __int64)v18 >> 8] + (unsigned __int8)v18) & 0x20) != 0 )
  {
    v28 = *((_QWORD *)this + 8);
    *(_QWORD *)(v28 + 48) = *(_QWORD *)(v28 + 56);
    result = 1;
    *(_DWORD *)(v28 + 88) = 1;
  }
  else
  {
    v19 = (void *)*((_QWORD *)this + 40);
    v20 = *((_QWORD *)this + 8);
    if ( v19 )
    {
      v21 = (struct IMalloc *)*((_QWORD *)this + 39);
      if ( v21 || (v21 = g_pMalloc) != 0 )
        ((void (__fastcall *)(struct IMalloc *, _QWORD))v21->lpVtbl->Free)(v21, *((_QWORD *)this + 40));
      else
        HeapFree(g_hHeap, 0, v19);
      *((_QWORD *)this + 40) = 0;
      *((_DWORD *)this + 82) = 0;
    }
    (*(void (__fastcall **)(__int64, char *, char *, char *, unsigned int *))(*(_QWORD *)v20 + 64LL))(
      v20,
      (char *)this + 320,
      (char *)this + 344,
      (char *)this + 328,
      &v29);
    v22 = *((_QWORD *)this + 43);
    v23 = v22 + v29;
    *((_QWORD *)this + 42) = v22;
    *((_QWORD *)this + 44) = v23;
    *((_DWORD *)this + 90) = 0;
    v24 = (unsigned int)--*((_DWORD *)this + 10);
    v25 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 4) + 8 * v24);
    if ( v25 )
    {
      (**v25)(v25, 1);
      LODWORD(v24) = *((_DWORD *)this + 10);
    }
    if ( (_DWORD)v24 )
    {
      v26 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * (unsigned int)(v24 - 1));
      *((_QWORD *)this + 8) = v26;
      *(_QWORD *)(v26 + 56) = *(_QWORD *)(v26 + 48);
      result = 0;
      *(_DWORD *)(v26 + 88) = 1;
    }
    else
    {
      result = 0;
      *((_QWORD *)this + 8) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10040ee90  mov     [rsp+arg_10], r8
0x10040ee95  push    rbx
0x10040ee96  push    rbp
0x10040ee97  push    rsi
0x10040ee98  push    rdi
0x10040ee99  push    r14
0x10040ee9b  sub     rsp, 30h
0x10040ee9f  mov     r14, rdx
0x10040eea2  mov     ebp, r9d
0x10040eea5  mov     edx, [rcx+28h]
0x10040eea8  mov     rbx, rcx
0x10040eeab  lea     eax, [rdx+1]
0x10040eeae  cmp     eax, 1
0x10040eeb1  cmovnb  edx, eax
0x10040eeb4  cmp     [rcx+2Ch], edx
0x10040eeb7  jnb     short loc_10040EEC5
0x10040eeb9  lfence
0x10040eebc  add     rcx, 10h
0x10040eec0  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040eec5  mov     rsi, [rbx+8]
0x10040eec9  lea     r9, [rsp+58h+arg_10]
0x10040eece  mov     r8d, 0FFFFFFFFh
0x10040eed4  lea     rcx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040eedb  mov     edx, ebp
0x10040eedd  call    ?FindConstructor@CharacterSourceFactory@@CAP6APEAVCharacterSource@@PEAUIMalloc@@I@ZPEAUStringPtr@@IW4TriState@@PEAI@Z; CharacterSourceFactory::FindConstructor(StringPtr *,uint,TriState,uint *)
0x10040eee2  mov     rcx, rsi
0x10040eee5  test    rax, rax
0x10040eee8  jz      short loc_10040EEF6
0x10040eeea  mov     edx, dword ptr [rsp+58h+arg_10]
0x10040eeee  call    cs:__guard_dispatch_icall_fptr
0x10040eef4  jmp     short loc_10040EF05
0x10040eef6  mov     r8d, ebp
0x10040eef9  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040ef00  call    ?CreateMLangCharacterSource@CharacterSourceFactory@@CAPEAVCharacterSource@@PEAUIMalloc@@PEAUStringPtr@@IW4TriState@@@Z; CharacterSourceFactory::CreateMLangCharacterSource(IMalloc *,StringPtr *,uint,TriState)
0x10040ef05  mov     rsi, rax
0x10040ef08  test    rax, rax
0x10040ef0b  jz      loc_10040F145
0x10040ef11  mov     [rbx+40h], rax
0x10040ef15  mov     ecx, [rbx+28h]
0x10040ef18  mov     [rsp+58h+arg_8], r15
0x10040ef1d  cmp     [rbx+2Ch], ecx
0x10040ef20  jnz     short loc_10040EF30
0x10040ef22  xor     edx, edx
0x10040ef24  lea     rcx, [rbx+10h]
0x10040ef28  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040ef2d  mov     ecx, [rbx+28h]
0x10040ef30  lea     eax, [rcx+1]
0x10040ef33  mov     rdx, r14
0x10040ef36  mov     [rbx+28h], eax
0x10040ef39  mov     rax, [rbx+20h]
0x10040ef3d  mov     [rax+rcx*8], rsi
0x10040ef41  mov     rcx, [rbx+40h]
0x10040ef45  mov     rax, [rcx]
0x10040ef48  mov     rax, [rax+30h]
0x10040ef4c  call    cs:__guard_dispatch_icall_fptr
0x10040ef52  mov     rcx, [rbx+40h]
0x10040ef56  xor     ebp, ebp
0x10040ef58  mov     r8d, [rbx+160h]
0x10040ef5f  sub     r8d, [rbx+158h]
0x10040ef66  mov     rdx, [rbx+140h]
0x10040ef6d  mov     r9d, [rbx+148h]
0x10040ef74  mov     [rbx+140h], rbp
0x10040ef7b  mov     [rbx+148h], ebp
0x10040ef81  mov     rax, [rcx]
0x10040ef84  mov     dword ptr [rsp+58h+var_38], r8d
0x10040ef89  mov     r8, [rbx+158h]
0x10040ef90  mov     rax, [rax+38h]
0x10040ef94  call    cs:__guard_dispatch_icall_fptr
0x10040ef9a  mov     dword ptr [rbx+168h], 1
0x10040efa4  mov     [rbx+150h], rbp
0x10040efab  mov     [rbx+158h], rbp
0x10040efb2  mov     [rbx+160h], rbp
0x10040efb9  mov     rcx, [rbx+40h]
0x10040efbd  mov     rax, [rcx+30h]
0x10040efc1  mov     [rcx+38h], rax
0x10040efc5  mov     dword ptr [rcx+58h], 1
0x10040efcc  mov     rcx, [rbx+40h]
0x10040efd0  mov     rax, [rcx]
0x10040efd3  mov     rax, [rax+58h]
0x10040efd7  call    cs:__guard_dispatch_icall_fptr
0x10040efdd  cmp     ax, 3Ch ; '<'
0x10040efe1  jz      loc_10040F120
0x10040efe7  movzx   ecx, ax
0x10040efea  lea     rdx, ?g_apCharTables@@3PAPEAEA; uchar * near * g_apCharTables
0x10040eff1  mov     eax, ecx
0x10040eff3  movzx   ecx, cl
0x10040eff6  shr     rax, 8
0x10040effa  mov     rax, [rdx+rax*8]
0x10040effe  test    byte ptr [rcx+rax], 20h
0x10040f002  jnz     loc_10040F120
0x10040f008  mov     r8, [rbx+140h]; lpMem
0x10040f00f  mov     rsi, [rbx+40h]
0x10040f013  test    r8, r8
0x10040f016  jz      short loc_10040F05E
0x10040f018  mov     rcx, [rbx+138h]
0x10040f01f  test    rcx, rcx
0x10040f022  jnz     short loc_10040F030
0x10040f024  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040f02b  test    rcx, rcx
0x10040f02e  jz      short loc_10040F042
0x10040f030  mov     rax, [rcx]
0x10040f033  mov     rdx, r8
0x10040f036  mov     rax, [rax+28h]
0x10040f03a  call    cs:__guard_dispatch_icall_fptr
0x10040f040  jmp     short loc_10040F051
0x10040f042  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040f049  xor     edx, edx; dwFlags
0x10040f04b  call    cs:__imp_HeapFree
0x10040f051  mov     [rbx+140h], rbp
0x10040f058  mov     [rbx+148h], ebp
0x10040f05e  mov     rax, [rsi]
0x10040f061  lea     rcx, [rsp+58h+arg_0]
0x10040f066  mov     [rsp+58h+var_38], rcx
0x10040f06b  lea     r9, [rbx+148h]
0x10040f072  lea     r8, [rbx+158h]
0x10040f079  mov     rcx, rsi
0x10040f07c  lea     rdx, [rbx+140h]
0x10040f083  mov     rax, [rax+40h]
0x10040f087  call    cs:__guard_dispatch_icall_fptr
0x10040f08d  mov     rcx, [rbx+158h]
0x10040f094  mov     eax, [rsp+58h+arg_0]
0x10040f098  add     rax, rcx
0x10040f09b  mov     [rbx+150h], rcx
0x10040f0a2  mov     [rbx+160h], rax
0x10040f0a9  mov     [rbx+168h], ebp
0x10040f0af  dec     dword ptr [rbx+28h]
0x10040f0b2  mov     edx, [rbx+28h]
0x10040f0b5  mov     rax, [rbx+20h]
0x10040f0b9  mov     rcx, [rax+rdx*8]
0x10040f0bd  test    rcx, rcx
0x10040f0c0  jz      short loc_10040F0D6
0x10040f0c2  mov     rax, [rcx]
0x10040f0c5  mov     edx, 1
0x10040f0ca  mov     rax, [rax]
0x10040f0cd  call    cs:__guard_dispatch_icall_fptr
0x10040f0d3  mov     edx, [rbx+28h]
0x10040f0d6  test    edx, edx
0x10040f0d8  jz      short loc_10040F10A
0x10040f0da  mov     rax, [rbx+20h]
0x10040f0de  lea     ecx, [rdx-1]
0x10040f0e1  mov     r15, [rsp+58h+arg_8]
0x10040f0e6  mov     rdx, [rax+rcx*8]
0x10040f0ea  mov     [rbx+40h], rdx
0x10040f0ee  mov     rax, [rdx+30h]
0x10040f0f2  mov     [rdx+38h], rax
0x10040f0f6  xor     al, al
0x10040f0f8  mov     dword ptr [rdx+58h], 1
0x10040f0ff  add     rsp, 30h
0x10040f103  pop     r14
0x10040f105  pop     rdi
0x10040f106  pop     rsi
0x10040f107  pop     rbp
0x10040f108  pop     rbx
0x10040f109  retn
0x10040f10a  mov     r15, [rsp+58h+arg_8]
0x10040f10f  xor     al, al
0x10040f111  mov     [rbx+40h], rbp
0x10040f115  add     rsp, 30h
0x10040f119  pop     r14
0x10040f11b  pop     rdi
0x10040f11c  pop     rsi
0x10040f11d  pop     rbp
0x10040f11e  pop     rbx
0x10040f11f  retn
0x10040f120  mov     rcx, [rbx+40h]
0x10040f124  mov     r15, [rsp+58h+arg_8]
0x10040f129  mov     rax, [rcx+38h]
0x10040f12d  mov     [rcx+30h], rax
0x10040f131  mov     al, 1
0x10040f133  mov     dword ptr [rcx+58h], 1
0x10040f13a  add     rsp, 30h
0x10040f13e  pop     r14
0x10040f140  pop     rdi
0x10040f141  pop     rsi
0x10040f142  pop     rbp
0x10040f143  pop     rbx
0x10040f144  retn
0x10040f145  mov     ecx, 0C00CEE02h; int
0x10040f14a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
