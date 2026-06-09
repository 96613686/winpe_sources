# Windows::UI::Composition::EffectInstance::CreateConstantBufferForAllSubgraphs(void)

- ea: `0x180014210`
- end: `0x180014360`
- name: `?CreateConstantBufferForAllSubgraphs@EffectInstance@Composition@UI@Windows@@AEAAXXZ`
- size: `336`
- prototype: `void __fastcall(Windows::UI::Composition::EffectInstance *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180013bcc`

## callees

- `0x180013a70`
- `0x180014210`
- `0x180014370`
- `0x1800143d0`
- `0x180014448`
- `0x180014490`
- `0x180021cd4`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180014359`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180014359`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectInstance::CreateConstantBufferForAllSubgraphs(
        Windows::UI::Composition::EffectInstance *this)
{
  unsigned int i; // edi
  __int64 v3; // rcx
  unsigned __int64 v4; // rax
  void **v5; // r14
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rbp
  unsigned int v9; // eax
  size_t v10; // r15
  void *v11; // rax
  void *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r9
  const void *v15; // rdx
  unsigned int v16; // esi
  unsigned int ConstantBufferUpdaterCount; // ebp
  const struct Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *ConstantBufferUpdaterAt; // rax
  __int64 v19; // rdx

  for ( i = 0; ; ++i )
  {
    v3 = *((_QWORD *)this + 5);
    v4 = (*((_QWORD *)this + 6) - v3) >> 4;
    if ( i >= (unsigned int)v4 )
      break;
    if ( v4 <= i )
      goto LABEL_19;
    v5 = (void **)(v3 + 16LL * i);
    if ( !*v5 )
    {
      v6 = *((_QWORD *)this + 3);
      v7 = *(_QWORD *)(v6 + 16);
      if ( 0xF0F0F0F0F0F0F0F1uLL * ((*(_QWORD *)(v6 + 24) - v7) >> 3) <= i )
        goto LABEL_19;
      v8 = 136LL * i;
      v9 = *(_DWORD *)(v7 + v8 + 72) - *(_DWORD *)(v7 + v8 + 64);
      if ( v9 )
      {
        v10 = v9;
        v11 = operator new[](v9);
        v12 = *v5;
        *v5 = v11;
        if ( v12 )
          operator delete(v12);
        v13 = *((_QWORD *)this + 3);
        v14 = *(_QWORD *)(v13 + 16);
        if ( 0xF0F0F0F0F0F0F0F1uLL * ((*(_QWORD *)(v13 + 24) - v14) >> 3) <= i
          || (v15 = *(const void **)(v14 + v8 + 64), *(const void **)(v14 + v8 + 72) == v15) )
        {
LABEL_19:
          std::_Xout_of_range("invalid vector subscript");
          JUMPOUT(0x18001435FLL);
        }
        memcpy_0(*v5, v15, v10);
        if ( *((_QWORD *)this + 4) )
        {
          v16 = 0;
          ConstantBufferUpdaterCount = Windows::UI::Composition::CompiledEffect::GetConstantBufferUpdaterCount(
                                         *((Windows::UI::Composition::CompiledEffect **)this + 3),
                                         i);
          if ( ConstantBufferUpdaterCount )
          {
            do
            {
              ConstantBufferUpdaterAt = Windows::UI::Composition::CompiledEffect::GetConstantBufferUpdaterAt(
                                          *((Windows::UI::Composition::CompiledEffect **)this + 3),
                                          i,
                                          v16);
              v19 = *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * *(unsigned int *)ConstantBufferUpdaterAt);
              if ( v19 )
                std::_Func_class<void,void const *,void *>::operator()(
                  (char *)ConstantBufferUpdaterAt + 8,
                  v19,
                  (char *)*v5 + *((unsigned int *)ConstantBufferUpdaterAt + 1));
              ++v16;
            }
            while ( v16 < ConstantBufferUpdaterCount );
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180014210  push    rbx
0x180014212  push    rbp
0x180014213  push    rsi
0x180014214  push    rdi
0x180014215  push    r12
0x180014217  push    r14
0x180014219  sub     rsp, 28h
0x18001421d  mov     rbx, rcx
0x180014220  mov     [rsp+58h+arg_0], r15
0x180014225  xor     edi, edi
0x180014227  mov     r12, 0F0F0F0F0F0F0F0F1h
0x180014231  mov     rcx, [rbx+28h]
0x180014235  mov     rax, [rbx+30h]
0x180014239  sub     rax, rcx
0x18001423c  sar     rax, 4
0x180014240  cmp     edi, eax
0x180014242  jnb     short loc_180014294
0x180014244  mov     esi, edi
0x180014246  cmp     rax, rsi
0x180014249  jbe     loc_180014352
0x18001424f  mov     r14d, esi
0x180014252  shl     r14, 4
0x180014256  add     r14, rcx
0x180014259  cmp     qword ptr [r14], 0
0x18001425d  jnz     short loc_180014290
0x18001425f  mov     rax, [rbx+18h]
0x180014263  mov     rdx, [rax+10h]
0x180014267  mov     rcx, [rax+18h]
0x18001426b  sub     rcx, rdx
0x18001426e  sar     rcx, 3
0x180014272  imul    rcx, r12
0x180014276  cmp     rcx, rsi
0x180014279  jbe     loc_180014352
0x18001427f  imul    rbp, rsi, 88h
0x180014286  mov     eax, [rdx+rbp+48h]
0x18001428a  sub     eax, [rdx+rbp+40h]
0x18001428e  jnz     short loc_1800142A6
0x180014290  inc     edi
0x180014292  jmp     short loc_180014231
0x180014294  mov     r15, [rsp+58h+arg_0]
0x180014299  add     rsp, 28h
0x18001429d  pop     r14
0x18001429f  pop     r12
0x1800142a1  pop     rdi
0x1800142a2  pop     rsi
0x1800142a3  pop     rbp
0x1800142a4  pop     rbx
0x1800142a5  retn
0x1800142a6  mov     ecx, eax; dwBytes
0x1800142a8  mov     r15d, eax
0x1800142ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800142b0  mov     rcx, [r14]; lpMem
0x1800142b3  mov     [r14], rax
0x1800142b6  test    rcx, rcx
0x1800142b9  jnz     loc_180014348
0x1800142bf  mov     rax, [rbx+18h]
0x1800142c3  mov     r9, [rax+10h]
0x1800142c7  mov     rcx, [rax+18h]
0x1800142cb  sub     rcx, r9
0x1800142ce  sar     rcx, 3
0x1800142d2  imul    rcx, r12
0x1800142d6  cmp     rcx, rsi
0x1800142d9  jbe     short loc_180014352
0x1800142db  mov     rdx, [r9+rbp+40h]; Src
0x1800142e0  cmp     [r9+rbp+48h], rdx
0x1800142e5  jz      short loc_180014352
0x1800142e7  mov     rcx, [r14]; void *
0x1800142ea  mov     r8, r15; Size
0x1800142ed  call    memcpy_0
0x1800142f2  cmp     qword ptr [rbx+20h], 0
0x1800142f7  jz      short loc_180014290
0x1800142f9  mov     rcx, [rbx+18h]; this
0x1800142fd  mov     edx, edi; unsigned int
0x1800142ff  call    ?GetConstantBufferUpdaterCount@CompiledEffect@Composition@UI@Windows@@QEBAII@Z; Windows::UI::Composition::CompiledEffect::GetConstantBufferUpdaterCount(uint)
0x180014304  xor     esi, esi
0x180014306  mov     ebp, eax
0x180014308  test    eax, eax
0x18001430a  jz      short loc_180014290
0x18001430c  nop     dword ptr [rax+00h]
0x180014310  mov     rcx, [rbx+18h]; this
0x180014314  mov     r8d, esi; unsigned int
0x180014317  mov     edx, edi; unsigned int
0x180014319  call    ?GetConstantBufferUpdaterAt@CompiledEffect@Composition@UI@Windows@@QEBAAEBUConstantBufferUpdater@CompiledEffectSubgraph@234@II@Z; Windows::UI::Composition::CompiledEffect::GetConstantBufferUpdaterAt(uint,uint)
0x18001431e  mov     rcx, [rbx+20h]
0x180014322  mov     edx, [rax]
0x180014324  mov     rdx, [rcx+rdx*8]
0x180014328  test    rdx, rdx
0x18001432b  jz      short loc_18001433D
0x18001432d  mov     r8d, [rax+4]
0x180014331  lea     rcx, [rax+8]
0x180014335  add     r8, [r14]
0x180014338  call    ??R?$_Func_class@XPEBXPEAX@std@@QEBAXPEBXPEAX@Z; std::_Func_class<void,void const *,void *>::operator()(void const *,void *)
0x18001433d  inc     esi
0x18001433f  cmp     esi, ebp
0x180014341  jb      short loc_180014310
0x180014343  jmp     loc_180014290
0x180014348  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001434d  jmp     loc_1800142BF
0x180014352  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180014359  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
