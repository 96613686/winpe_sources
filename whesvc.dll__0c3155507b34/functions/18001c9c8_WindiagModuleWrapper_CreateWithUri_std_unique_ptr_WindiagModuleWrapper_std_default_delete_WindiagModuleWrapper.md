# WindiagModuleWrapper::CreateWithUri(std::unique_ptr<WindiagModuleWrapper,std::default_delete<WindiagModuleWrapper>> &,char const *,void * const,ulong)

- ea: `0x18001c9c8`
- end: `0x18001cbb4`
- name: `?CreateWithUri@WindiagModuleWrapper@@SAJAEAV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBDQEAXK@Z`
- size: `492`
- prototype: `__int64 __fastcall(void ***, _BYTE *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800152f8`
- `0x180016754`

## callees

- `0x180003304`
- `0x180003bd8`
- `0x180003be4`
- `0x180003da4`
- `0x180004575`
- `0x180004581`
- `0x18000f410`
- `0x18000fc50`
- `0x180011578`
- `0x18001c9c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindiagModuleWrapper::CreateWithUri(void ***a1, _BYTE *a2, const void *a3, unsigned int a4)
{
  unsigned __int64 v4; // r15
  char *v9; // rax
  __int64 v10; // r8
  void **v11; // rbx
  unsigned __int64 v12; // rdx
  void *v13; // rcx
  void **v14; // rcx
  size_t v15; // rbx
  void *v16; // rsi
  _QWORD *v17; // rax
  void *v18; // rcx
  _QWORD *v19; // rcx
  void *v20; // rbx
  unsigned __int64 v21; // rdx
  char *v22; // rcx
  void *v23; // rax
  void *v24; // rcx
  char v25; // [rsp+20h] [rbp-48h] BYREF

  v4 = a4;
  if ( !a2 )
    return 2147942487LL;
  try
  {
    v9 = (char *)operator new(0x58u);
    *((_QWORD *)v9 + 2) = 0;
    *(_QWORD *)v9 = 0;
    *((_QWORD *)v9 + 1) = 0;
    *(_OWORD *)(v9 + 24) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *((_QWORD *)v9 + 6) = 15;
    v9[24] = 0;
    *(_OWORD *)(v9 + 56) = 0;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 15;
    v9[56] = 0;
    v11 = *a1;
    *a1 = (void **)v9;
    if ( v11 )
    {
      std::string::~string(v11 + 7);
      std::string::~string(v11 + 3);
      v13 = v11[1];
      if ( v13 )
        operator delete(v13, v12);
      if ( *v11 )
        operator delete(*v11, 0x18u);
      operator delete(v11, 0x58u);
    }
    v14 = *a1 + 3;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    if ( v15 > (unsigned __int64)(*a1)[6] )
    {
      std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v14, v15, v10, a2);
    }
    else
    {
      if ( (unsigned __int64)(*a1)[6] <= 0xF )
        v16 = *a1 + 3;
      else
        v16 = *v14;
      (*a1)[5] = (void *)v15;
      memmove_0(v16, a2, v15);
      *((_BYTE *)v16 + v15) = 0;
    }
    v17 = operator new(0x18u);
    *(_OWORD *)v17 = 0;
    v17[2] = 0;
    v18 = **a1;
    **a1 = v17;
    if ( v18 )
      operator delete(v18, 0x18u);
    v19 = *a1 + 3;
    if ( (unsigned __int64)(*a1)[6] > 0xF )
      v19 = (_QWORD *)*v19;
    *(_QWORD *)**a1 = v19;
    *((_QWORD *)**a1 + 2) = *(_QWORD *)AssetLoaderSingleton::GetInstance();
    *((_DWORD *)**a1 + 2) = -1;
    if ( !a3 || !(_DWORD)v4 )
      return 0;
    *((_DWORD *)*a1 + 4) = v4;
    v20 = operator new[](v4);
    memset_0(v20, 0, v4);
    v22 = (char *)(*a1 + 1);
    if ( v22 == &v25 )
    {
      if ( v20 )
      {
        v24 = v20;
        goto LABEL_28;
      }
    }
    else
    {
      v23 = *(void **)v22;
      *(_QWORD *)v22 = v20;
      if ( v23 )
      {
        v24 = v23;
LABEL_28:
        operator delete(v24, v21);
      }
    }
    memcpy_0((*a1)[1], a3, v4);
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c9c8  push    rbx
0x18001c9ca  push    rsi
0x18001c9cb  push    rdi
0x18001c9cc  push    r12
0x18001c9ce  push    r14
0x18001c9d0  push    r15
0x18001c9d2  sub     rsp, 38h
0x18001c9d6  mov     r15d, r9d
0x18001c9d9  mov     r12, r8
0x18001c9dc  mov     r14, rdx
0x18001c9df  mov     rdi, rcx
0x18001c9e2  test    rdx, rdx
0x18001c9e5  jnz     short loc_18001C9F1
0x18001c9e7  mov     eax, 80070057h
0x18001c9ec  jmp     loc_18001CBA6
0x18001c9f1  mov     esi, 58h ; 'X'
0x18001c9f6  mov     ecx, esi; Size
0x18001c9f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c9fd  xor     ecx, ecx
0x18001c9ff  mov     [rax+10h], rcx
0x18001ca03  mov     [rax], rcx
0x18001ca06  mov     [rax+8], rcx
0x18001ca0a  xorps   xmm0, xmm0
0x18001ca0d  movups  xmmword ptr [rax+18h], xmm0
0x18001ca11  mov     [rax+28h], rcx
0x18001ca15  mov     qword ptr [rax+30h], 0Fh
0x18001ca1d  mov     [rax+18h], cl
0x18001ca20  movups  xmmword ptr [rax+38h], xmm0
0x18001ca24  mov     [rax+48h], rcx
0x18001ca28  mov     qword ptr [rax+50h], 0Fh
0x18001ca30  mov     [rax+38h], cl
0x18001ca33  mov     rbx, [rdi]
0x18001ca36  mov     [rdi], rax
0x18001ca39  test    rbx, rbx
0x18001ca3c  jz      short loc_18001CA7B
0x18001ca3e  lea     rcx, [rbx+38h]
0x18001ca42  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ca47  lea     rcx, [rbx+18h]
0x18001ca4b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ca50  mov     rcx, [rbx+8]; void *
0x18001ca54  test    rcx, rcx
0x18001ca57  jz      short loc_18001CA5E
0x18001ca59  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca5e  mov     rcx, [rbx]; void *
0x18001ca61  test    rcx, rcx
0x18001ca64  jz      short loc_18001CA70
0x18001ca66  mov     edx, 18h; unsigned __int64
0x18001ca6b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca70  mov     rdx, rsi; unsigned __int64
0x18001ca73  mov     rcx, rbx; void *
0x18001ca76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca7b  mov     rcx, [rdi]
0x18001ca7e  add     rcx, 18h
0x18001ca82  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ca86  inc     rbx
0x18001ca89  cmp     byte ptr [r14+rbx], 0
0x18001ca8e  jnz     short loc_18001CA86
0x18001ca90  cmp     rbx, [rcx+18h]
0x18001ca94  ja      short loc_18001CABD
0x18001ca96  cmp     qword ptr [rcx+18h], 0Fh
0x18001ca9b  jbe     short loc_18001CAA2
0x18001ca9d  mov     rsi, [rcx]
0x18001caa0  jmp     short loc_18001CAA5
0x18001caa2  mov     rsi, rcx
0x18001caa5  mov     [rcx+10h], rbx
0x18001caa9  mov     r8, rbx; Size
0x18001caac  mov     rdx, r14; Src
0x18001caaf  mov     rcx, rsi; void *
0x18001cab2  call    memmove_0
0x18001cab7  mov     byte ptr [rbx+rsi], 0
0x18001cabb  jmp     short loc_18001CAC8
0x18001cabd  mov     r9, r14
0x18001cac0  mov     rdx, rbx
0x18001cac3  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18001cac8  mov     ecx, 18h; Size
0x18001cacd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cad2  xorps   xmm0, xmm0
0x18001cad5  xor     ecx, ecx
0x18001cad7  movups  xmmword ptr [rax], xmm0
0x18001cada  mov     [rax+10h], rcx
0x18001cade  mov     r8, [rdi]
0x18001cae1  mov     rcx, [r8]; void *
0x18001cae4  mov     [r8], rax
0x18001cae7  test    rcx, rcx
0x18001caea  jz      short loc_18001CAF6
0x18001caec  mov     edx, 18h; unsigned __int64
0x18001caf1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001caf6  mov     rax, [rdi]
0x18001caf9  lea     rcx, [rax+18h]
0x18001cafd  cmp     qword ptr [rcx+18h], 0Fh
0x18001cb02  jbe     short loc_18001CB07
0x18001cb04  mov     rcx, [rcx]
0x18001cb07  mov     rax, [rax]
0x18001cb0a  mov     [rax], rcx
0x18001cb0d  call    ?GetInstance@AssetLoaderSingleton@@SAAEAV1@XZ; AssetLoaderSingleton::GetInstance(void)
0x18001cb12  mov     rcx, [rdi]
0x18001cb15  mov     rdx, [rcx]
0x18001cb18  mov     rax, [rax]
0x18001cb1b  mov     [rdx+10h], rax
0x18001cb1f  mov     rax, [rdi]
0x18001cb22  mov     rcx, [rax]
0x18001cb25  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x18001cb2c  test    r12, r12
0x18001cb2f  jz      short loc_18001CB96
0x18001cb31  test    r15d, r15d
0x18001cb34  jz      short loc_18001CB96
0x18001cb36  mov     rax, [rdi]
0x18001cb39  mov     [rax+10h], r15d
0x18001cb3d  mov     rcx, r15; unsigned __int64
0x18001cb40  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001cb45  mov     rbx, rax
0x18001cb48  mov     r8, r15; Size
0x18001cb4b  xor     edx, edx; Val
0x18001cb4d  mov     rcx, rax; void *
0x18001cb50  call    memset_0
0x18001cb55  mov     rcx, [rdi]
0x18001cb58  add     rcx, 8
0x18001cb5c  lea     rax, [rsp+68h+var_48]
0x18001cb61  cmp     rcx, rax
0x18001cb64  jz      short loc_18001CB76
0x18001cb66  mov     rax, [rcx]
0x18001cb69  mov     [rcx], rbx
0x18001cb6c  test    rax, rax
0x18001cb6f  jz      short loc_18001CB83
0x18001cb71  mov     rcx, rax
0x18001cb74  jmp     short loc_18001CB7E
0x18001cb76  test    rbx, rbx
0x18001cb79  jz      short loc_18001CB83
0x18001cb7b  mov     rcx, rbx; void *
0x18001cb7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cb83  mov     rcx, [rdi]
0x18001cb86  mov     r8, r15; Size
0x18001cb89  mov     rdx, r12; Src
0x18001cb8c  mov     rcx, [rcx+8]; void *
0x18001cb90  call    memcpy_0
0x18001cb95  nop
0x18001cb96  xor     eax, eax
0x18001cb98  jmp     short loc_18001CBA6
0x18001cb9a  mov     eax, 8007000Eh
0x18001cb9f  jmp     short loc_18001CBA6
0x18001cba1  mov     eax, 80004005h
0x18001cba6  add     rsp, 38h
0x18001cbaa  pop     r15
0x18001cbac  pop     r14
0x18001cbae  pop     r12
0x18001cbb0  pop     rdi
0x18001cbb1  pop     rsi
0x18001cbb2  pop     rbx
0x18001cbb3  retn
```
