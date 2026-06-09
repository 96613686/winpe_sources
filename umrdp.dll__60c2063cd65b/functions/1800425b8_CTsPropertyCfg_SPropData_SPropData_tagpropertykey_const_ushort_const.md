# CTsPropertyCfg::SPropData::SPropData(_tagpropertykey const &,ushort const *)

- ea: `0x1800425b8`
- end: `0x1800426d5`
- name: `??0SPropData@CTsPropertyCfg@@QEAA@AEBU_tagpropertykey@@PEBG@Z`
- size: `285`
- prototype: `_QWORD(CTsPropertyCfg::SPropData *__hidden this, const struct _tagpropertykey *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042bc0`

## callees

- `0x18000b8f8`
- `0x18000bd04`
- `0x18000f79c`
- `0x1800425b8`
- `0x180042960`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800426bc`
- `msvcrt!memcpy_s` at `0x1800426bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042635`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042635`

## pseudocode

```c
CTsPropertyCfg::SPropData *__fastcall CTsPropertyCfg::SPropData::SPropData(
        CTsPropertyCfg::SPropData *this,
        const struct _tagpropertykey *a2,
        const unsigned __int16 *a3)
{
  void *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdi
  int v8; // esi
  __int64 v9; // rax
  __int64 v10; // rsi
  void *v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v13; // rdx

  *(struct _tagpropertykey *)this = *a2;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = -1;
  v5 = operator new(0x18u);
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = v5;
  if ( v6 )
    CTsPropertyCfg::SPropData::PropVarDeleter::operator()();
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
      v10 = 2 * v9 + 2;
      v11 = CoTaskMemAlloc(v10);
      *(_QWORD *)(v7 + 8) = v11;
      if ( v11 )
      {
        memcpy_s(v11, v10, a3, v10);
        *(_WORD *)v7 = 31;
        return this;
      }
      v8 = -2147024882;
    }
    else
    {
      v8 = -2147024809;
    }
    *(_OWORD *)v7 = 0;
    *(_QWORD *)(v7 + 16) = 0;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        15,
        WPP_fdcbca90fd7f33414ba60dd741ad2ded_Traceguids,
        CurrentThreadActivityIdPrefix,
        v8);
    }
    v13 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = 0;
    if ( v13 )
      CTsPropertyCfg::SPropData::PropVarDeleter::operator()();
  }
  return this;
}

```

## disassembly

```asm
0x1800425b8  push    rbx
0x1800425ba  push    rbp
0x1800425bb  push    rsi
0x1800425bc  push    rdi
0x1800425bd  push    r14
0x1800425bf  sub     rsp, 30h
0x1800425c3  movups  xmm0, xmmword ptr [rdx]
0x1800425c6  xor     r14d, r14d
0x1800425c9  mov     rbx, rcx
0x1800425cc  mov     rbp, r8
0x1800425cf  movups  xmmword ptr [rcx], xmm0
0x1800425d2  mov     eax, [rdx+10h]
0x1800425d5  mov     [rcx+10h], eax
0x1800425d8  mov     [rcx+18h], r14
0x1800425dc  mov     [rcx+20h], r14
0x1800425e0  mov     dword ptr [rcx+28h], 0FFFFFFFFh
0x1800425e7  lea     ecx, [r14+18h]; Size
0x1800425eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800425f0  mov     rdx, [rbx+18h]
0x1800425f4  mov     [rbx+18h], rax
0x1800425f8  test    rdx, rdx
0x1800425fb  jz      short loc_180042602
0x1800425fd  call    ??RPropVarDeleter@SPropData@CTsPropertyCfg@@QEAAXPEAUtagPROPVARIANT@@@Z; CTsPropertyCfg::SPropData::PropVarDeleter::operator()(tagPROPVARIANT *)
0x180042602  mov     rdi, [rbx+18h]
0x180042606  test    rdi, rdi
0x180042609  jz      loc_1800426C7
0x18004260f  test    rbp, rbp
0x180042612  jnz     short loc_18004261B
0x180042614  mov     esi, 80070057h
0x180042619  jmp     short loc_180042649
0x18004261b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004261f  inc     rax
0x180042622  cmp     [rbp+rax*2+0], r14w
0x180042628  jnz     short loc_18004261F
0x18004262a  lea     rsi, ds:2[rax*2]
0x180042632  mov     rcx, rsi; cb
0x180042635  call    cs:__imp_CoTaskMemAlloc
0x18004263b  mov     [rdi+8], rax
0x18004263f  test    rax, rax
0x180042642  jnz     short loc_1800426B0
0x180042644  mov     esi, 8007000Eh
0x180042649  xorps   xmm0, xmm0
0x18004264c  xor     eax, eax
0x18004264e  movups  xmmword ptr [rdi], xmm0
0x180042651  mov     [rdi+10h], rax
0x180042655  mov     rax, cs:WPP_GLOBAL_Control
0x18004265c  lea     rcx, WPP_GLOBAL_Control
0x180042663  cmp     rax, rcx
0x180042666  jz      short loc_18004269C
0x180042668  test    byte ptr [rax+1Ch], 1
0x18004266c  jz      short loc_18004269C
0x18004266e  cmp     byte ptr [rax+19h], 2
0x180042672  jb      short loc_18004269C
0x180042674  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180042679  mov     rcx, cs:WPP_GLOBAL_Control
0x180042680  lea     r8, WPP_fdcbca90fd7f33414ba60dd741ad2ded_Traceguids
0x180042687  mov     edx, 0Fh
0x18004268c  mov     [rsp+58h+var_38], esi
0x180042690  mov     r9d, eax
0x180042693  mov     rcx, [rcx+10h]
0x180042697  call    WPP_SF_Dd
0x18004269c  mov     rdx, [rbx+18h]
0x1800426a0  mov     [rbx+18h], r14
0x1800426a4  test    rdx, rdx
0x1800426a7  jz      short loc_1800426C7
0x1800426a9  call    ??RPropVarDeleter@SPropData@CTsPropertyCfg@@QEAAXPEAUtagPROPVARIANT@@@Z; CTsPropertyCfg::SPropData::PropVarDeleter::operator()(tagPROPVARIANT *)
0x1800426ae  jmp     short loc_1800426C7
0x1800426b0  mov     r9, rsi; SourceSize
0x1800426b3  mov     r8, rbp; Source
0x1800426b6  mov     rdx, rsi; DestinationSize
0x1800426b9  mov     rcx, rax; Destination
0x1800426bc  call    cs:__imp_memcpy_s
0x1800426c2  mov     word ptr [rdi], 1Fh
0x1800426c7  mov     rax, rbx
0x1800426ca  add     rsp, 30h
0x1800426ce  pop     r14
0x1800426d0  pop     rdi
0x1800426d1  pop     rsi
0x1800426d2  pop     rbp
0x1800426d3  pop     rbx
0x1800426d4  retn
```
