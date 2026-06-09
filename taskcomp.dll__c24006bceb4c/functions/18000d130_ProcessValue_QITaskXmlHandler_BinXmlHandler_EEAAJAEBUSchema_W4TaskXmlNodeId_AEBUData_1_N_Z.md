# ?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18000d130`
- end: `0x18000d40e`
- name: `?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `734`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callees

- `0x180003ec0`
- `0x180004e50`
- `0x180004fe4`
- `0x1800074c8`
- `0x1800074d4`
- `0x18000878c`
- `0x18000a8ec`
- `0x18000d130`
- `0x180021c90`
- `0x180031010`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000d2d4`
- `msvcrt!iswdigit` at `0x18000d2d4`
- `msvcrt!iswspace` at `0x18000d322`
- `msvcrt!iswspace` at `0x18000d322`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _ProcessValue__QITaskXmlHandler__BinXmlHandler__EEAAJAEBUSchema__W4TaskXmlNodeId__AEBUData_1__N_Z(
        __int64 a1,
        int *a2,
        int a3,
        __int64 a4)
{
  __int64 result; // rax
  unsigned int v8; // esi
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  BSTR v16; // r8
  BSTR v17; // r8
  BSTR v18; // r8
  unsigned int v19; // ebx
  char v20; // al
  _BYTE *v21; // rax
  _BYTE *v22; // rbx
  char v23; // r15
  unsigned __int64 v24; // r12
  _BYTE *v25; // rsi
  __int64 v26; // rdi
  wint_t v27; // di
  char v28; // di
  __int64 v29; // rsi
  BSTR v30; // r8
  BSTR NullTerminated; // r8
  _QWORD v32[2]; // [rsp+30h] [rbp-50h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  char v34; // [rsp+48h] [rbp-38h]
  char *v35; // [rsp+50h] [rbp-30h]
  __int64 v36; // [rsp+58h] [rbp-28h]
  __int64 v37; // [rsp+60h] [rbp-20h]
  int v38; // [rsp+68h] [rbp-18h]
  __int64 v39; // [rsp+6Ch] [rbp-14h]

  result = ValidationXmlHandler::ProcessValue(a1, a2, a3, a4);
  v8 = result;
  if ( (int)result < 0 )
    return result;
  v9 = a3 - 2;
  if ( !v9 )
  {
    *(_DWORD *)(a1 + 540) = *(_DWORD *)(a4 + 32);
    return v8;
  }
  v10 = v9 - 6;
  if ( !v10 )
  {
    NullTerminated = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
    if ( NullTerminated )
      (*(void (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 512) + 160LL))(*(_QWORD *)(a1 + 512), NullTerminated);
    return v8;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    v30 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
    if ( v30 )
      (*(void (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 512) + 144LL))(*(_QWORD *)(a1 + 512), v30);
    return v8;
  }
  v12 = v11 - 72;
  if ( !v12 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 512) + 88LL) |= 2u;
    return v8;
  }
  v13 = v12 - 14;
  if ( v13 )
  {
    v14 = v13 - 8;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          v16 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
          if ( v16 )
            (*(void (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 512) + 288LL))(*(_QWORD *)(a1 + 512), v16);
        }
      }
      else
      {
        v17 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
        if ( v17 )
          (*(void (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 512) + 272LL))(*(_QWORD *)(a1 + 512), v17);
      }
    }
    else
    {
      v18 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
      if ( v18 )
        (*(void (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)(a1 + 512) + 256LL))(*(_QWORD *)(a1 + 512), v18);
    }
    return v8;
  }
  XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v32);
  v19 = _bstr_t::length((_bstr_t *)v32) >> 1;
  v20 = _bstr_t::length((_bstr_t *)v32);
  v21 = operator new[](v19 + (v20 & 1));
  v22 = v21;
  v32[1] = v21;
  if ( !v21 )
  {
    v34 = 0;
    v35 = byte_1800505F8;
    v36 = 0;
    v37 = 0;
    v38 = 14;
    v39 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v23 = 1;
  v24 = 0;
  v25 = v21;
  while ( v24 < _bstr_t::length((_bstr_t *)v32) )
  {
    if ( v32[0] )
      v26 = *(_QWORD *)v32[0];
    else
      v26 = 0;
    v27 = *(_WORD *)(v26 + 2 * v24);
    if ( iswdigit(v27) )
    {
      v28 = v27 - 48;
      goto LABEL_30;
    }
    if ( (unsigned __int16)(v27 - 97) <= 5u )
    {
      v28 = v27 - 87;
      goto LABEL_30;
    }
    if ( (unsigned __int16)(v27 - 65) <= 5u )
    {
      v28 = v27 - 55;
LABEL_30:
      if ( v23 )
      {
        *v25 = v28;
        v23 = 0;
      }
      else
      {
        *v25 = v28 + 16 * *v25;
        ++v25;
        v23 = 1;
      }
      goto LABEL_34;
    }
    if ( !iswspace(v27) )
      goto LABEL_39;
LABEL_34:
    ++v24;
  }
  if ( v23 )
  {
    v29 = v25 - v22;
    if ( (unsigned int)v29 == v29 && (unsigned int)v29 <= 0xFFFF )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**(_QWORD **)(a1 + 512) + 176LL))(
             *(_QWORD *)(a1 + 512),
             (unsigned int)v29,
             v22);
      operator delete(v22);
      _bstr_t::~_bstr_t((_bstr_t *)v32);
      return v8;
    }
  }
LABEL_39:
  operator delete(v22);
  _bstr_t::~_bstr_t((_bstr_t *)v32);
  return 2147750680LL;
}

```

## disassembly

```asm
0x18000d130  push    rbp
0x18000d132  push    rbx
0x18000d133  push    rsi
0x18000d134  push    rdi
0x18000d135  push    r12
0x18000d137  push    r14
0x18000d139  push    r15
0x18000d13b  mov     rbp, rsp
0x18000d13e  sub     rsp, 80h
0x18000d145  mov     rdi, r9
0x18000d148  mov     ebx, r8d
0x18000d14b  mov     r14, rcx
0x18000d14e  mov     al, [rbp+arg_20]
0x18000d151  mov     [rsp+80h+var_60], al
0x18000d155  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18000d15a  mov     esi, eax
0x18000d15c  test    eax, eax
0x18000d15e  js      loc_18000D3FC
0x18000d164  sub     ebx, 2
0x18000d167  jz      loc_18000D3F0
0x18000d16d  sub     ebx, 6
0x18000d170  jz      loc_18000D3C9
0x18000d176  sub     ebx, 2
0x18000d179  jz      loc_18000D3A2
0x18000d17f  sub     ebx, 48h ; 'H'
0x18000d182  jz      loc_18000D395
0x18000d188  sub     ebx, 0Eh
0x18000d18b  jz      loc_18000D227
0x18000d191  sub     ebx, 8
0x18000d194  jz      short loc_18000D1F4
0x18000d196  sub     ebx, 1
0x18000d199  jz      short loc_18000D1CC
0x18000d19b  cmp     ebx, 1
0x18000d19e  jnz     loc_18000D3FA
0x18000d1a4  mov     rcx, [rdi+30h]; this
0x18000d1a8  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000d1ad  mov     r8, rax
0x18000d1b0  test    rax, rax
0x18000d1b3  jz      loc_18000D3FA
0x18000d1b9  mov     rcx, [r14+200h]
0x18000d1c0  mov     rdx, [rcx]
0x18000d1c3  mov     rax, [rdx+120h]
0x18000d1ca  jmp     short loc_18000D21A
0x18000d1cc  mov     rcx, [rdi+30h]; this
0x18000d1d0  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000d1d5  mov     r8, rax
0x18000d1d8  test    rax, rax
0x18000d1db  jz      loc_18000D3FA
0x18000d1e1  mov     rcx, [r14+200h]
0x18000d1e8  mov     rdx, [rcx]
0x18000d1eb  mov     rax, [rdx+110h]
0x18000d1f2  jmp     short loc_18000D21A
0x18000d1f4  mov     rcx, [rdi+30h]; this
0x18000d1f8  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000d1fd  mov     r8, rax
0x18000d200  test    rax, rax
0x18000d203  jz      loc_18000D3FA
0x18000d209  mov     rcx, [r14+200h]
0x18000d210  mov     rdx, [rcx]
0x18000d213  mov     rax, [rdx+100h]
0x18000d21a  mov     rdx, r8
0x18000d21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d222  jmp     loc_18000D3FA
0x18000d227  lea     rdx, [rbp+var_50]
0x18000d22b  mov     rcx, [rdi+30h]
0x18000d22f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18000d234  nop
0x18000d235  lea     rcx, [rbp+var_50]; this
0x18000d239  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000d23e  mov     ebx, eax
0x18000d240  shr     ebx, 1
0x18000d242  lea     rcx, [rbp+var_50]; this
0x18000d246  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000d24b  and     eax, 1
0x18000d24e  lea     ecx, [rbx+rax]; unsigned __int64
0x18000d251  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d256  mov     rbx, rax
0x18000d259  mov     [rbp+var_48], rax
0x18000d25d  test    rax, rax
0x18000d260  jnz     short loc_18000D2A3
0x18000d262  mov     [rbp+var_38], al
0x18000d265  lea     rax, byte_1800505F8
0x18000d26c  mov     [rbp+var_30], rax
0x18000d270  mov     [rbp+var_28], rbx
0x18000d274  mov     [rbp+var_20], rbx
0x18000d278  mov     [rbp+var_18], 0Eh
0x18000d27f  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18000d287  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000d28e  mov     [rbp+pExceptionObject], rax
0x18000d292  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000d299  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d29d  call    _CxxThrowException_0
0x18000d2a3  mov     r15b, 1
0x18000d2a6  xor     r12d, r12d
0x18000d2a9  mov     rsi, rbx
0x18000d2ac  lea     rcx, [rbp+var_50]; this
0x18000d2b0  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000d2b5  mov     eax, eax
0x18000d2b7  cmp     r12, rax
0x18000d2ba  jnb     short loc_18000D334
0x18000d2bc  mov     rax, [rbp+var_50]
0x18000d2c0  test    rax, rax
0x18000d2c3  jz      short loc_18000D2CA
0x18000d2c5  mov     rdi, [rax]
0x18000d2c8  jmp     short loc_18000D2CC
0x18000d2ca  xor     edi, edi
0x18000d2cc  movzx   edi, word ptr [rdi+r12*2]
0x18000d2d1  movzx   ecx, di; C
0x18000d2d4  call    cs:__imp_iswdigit
0x18000d2da  test    eax, eax
0x18000d2dc  jz      short loc_18000D2E4
0x18000d2de  sub     dil, 30h ; '0'
0x18000d2e2  jmp     short loc_18000D300
0x18000d2e4  lea     eax, [rdi-61h]
0x18000d2e7  cmp     ax, 5
0x18000d2eb  ja      short loc_18000D2F3
0x18000d2ed  sub     dil, 57h ; 'W'
0x18000d2f1  jmp     short loc_18000D300
0x18000d2f3  lea     eax, [rdi-41h]
0x18000d2f6  cmp     ax, 5
0x18000d2fa  ja      short loc_18000D31F
0x18000d2fc  sub     dil, 37h ; '7'
0x18000d300  test    r15b, r15b
0x18000d303  jz      short loc_18000D30D
0x18000d305  mov     [rsi], dil
0x18000d308  xor     r15b, r15b
0x18000d30b  jmp     short loc_18000D32C
0x18000d30d  mov     al, [rsi]
0x18000d30f  shl     al, 4
0x18000d312  add     al, dil
0x18000d315  mov     [rsi], al
0x18000d317  inc     rsi
0x18000d31a  mov     r15b, 1
0x18000d31d  jmp     short loc_18000D32C
0x18000d31f  movzx   ecx, di; C
0x18000d322  call    cs:__imp_iswspace
0x18000d328  test    eax, eax
0x18000d32a  jz      short loc_18000D37C
0x18000d32c  inc     r12
0x18000d32f  jmp     loc_18000D2AC
0x18000d334  test    r15b, r15b
0x18000d337  jz      short loc_18000D37C
0x18000d339  mov     edx, esi
0x18000d33b  sub     edx, ebx
0x18000d33d  sub     rsi, rbx
0x18000d340  cmp     rdx, rsi
0x18000d343  jnz     short loc_18000D37C
0x18000d345  cmp     edx, 0FFFFh
0x18000d34b  ja      short loc_18000D37C
0x18000d34d  mov     rcx, [r14+200h]
0x18000d354  mov     rax, [rcx]
0x18000d357  mov     r8, rbx
0x18000d35a  mov     rax, [rax+0B0h]
0x18000d361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d366  mov     esi, eax
0x18000d368  mov     rcx, rbx; Block
0x18000d36b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d370  nop
0x18000d371  lea     rcx, [rbp+var_50]; this
0x18000d375  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000d37a  jmp     short loc_18000D3FA
0x18000d37c  mov     rcx, rbx; Block
0x18000d37f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d384  nop
0x18000d385  lea     rcx, [rbp+var_50]; this
0x18000d389  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000d38e  mov     eax, 80041318h
0x18000d393  jmp     short loc_18000D3FC
0x18000d395  mov     rax, [r14+200h]
0x18000d39c  or      dword ptr [rax+58h], 2
0x18000d3a0  jmp     short loc_18000D3FA
0x18000d3a2  mov     rcx, [rdi+30h]; this
0x18000d3a6  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000d3ab  mov     r8, rax
0x18000d3ae  test    rax, rax
0x18000d3b1  jz      short loc_18000D3FA
0x18000d3b3  mov     rcx, [r14+200h]
0x18000d3ba  mov     rdx, [rcx]
0x18000d3bd  mov     rax, [rdx+90h]
0x18000d3c4  jmp     loc_18000D21A
0x18000d3c9  mov     rcx, [rdi+30h]; this
0x18000d3cd  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000d3d2  mov     r8, rax
0x18000d3d5  test    rax, rax
0x18000d3d8  jz      short loc_18000D3FA
0x18000d3da  mov     rcx, [r14+200h]
0x18000d3e1  mov     rdx, [rcx]
0x18000d3e4  mov     rax, [rdx+0A0h]
0x18000d3eb  jmp     loc_18000D21A
0x18000d3f0  mov     eax, [rdi+20h]
0x18000d3f3  mov     [r14+21Ch], eax
0x18000d3fa  mov     eax, esi
0x18000d3fc  add     rsp, 80h
0x18000d403  pop     r15
0x18000d405  pop     r14
0x18000d407  pop     r12
0x18000d409  pop     rdi
0x18000d40a  pop     rsi
0x18000d40b  pop     rbx
0x18000d40c  pop     rbp
0x18000d40d  retn
```
