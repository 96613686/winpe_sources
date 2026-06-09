# ?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18000d9b0`
- end: `0x18000dc9f`
- name: `?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `751`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callees

- `0x180004090`
- `0x1800050d0`
- `0x180005284`
- `0x180007988`
- `0x180007994`
- `0x180008c4c`
- `0x18000aedc`
- `0x18000d9b0`
- `0x1800232b0`
- `0x180033010`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000db58`
- `msvcrt!iswdigit` at `0x18000db58`
- `msvcrt!iswspace` at `0x18000dbac`
- `msvcrt!iswspace` at `0x18000dbac`

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
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // r8
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
  unsigned __int16 *v30; // r8
  unsigned __int16 *NullTerminated; // r8
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
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 512) + 160LL))(
        *(_QWORD *)(a1 + 512),
        NullTerminated);
    return v8;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    v30 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
    if ( v30 )
      (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 512) + 144LL))(*(_QWORD *)(a1 + 512), v30);
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
            (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 512) + 288LL))(
              *(_QWORD *)(a1 + 512),
              v16);
        }
      }
      else
      {
        v17 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
        if ( v17 )
          (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 512) + 272LL))(
            *(_QWORD *)(a1 + 512),
            v17);
      }
    }
    else
    {
      v18 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
      if ( v18 )
        (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 512) + 256LL))(
          *(_QWORD *)(a1 + 512),
          v18);
    }
    return v8;
  }
  XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v32);
  v19 = _bstr_t::length((_bstr_t *)v32) >> 1;
  v20 = _bstr_t::length((_bstr_t *)v32);
  v21 = operator new[](v19 + (v20 & 1));
  v22 = v21;
  v32[1] = v21;
  if ( !v21 )
  {
    v34 = 0;
    v35 = byte_180052608;
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
0x18000d9b0  push    rbp
0x18000d9b2  push    rbx
0x18000d9b3  push    rsi
0x18000d9b4  push    rdi
0x18000d9b5  push    r12
0x18000d9b7  push    r14
0x18000d9b9  push    r15
0x18000d9bb  mov     rbp, rsp
0x18000d9be  sub     rsp, 80h
0x18000d9c5  mov     rdi, r9
0x18000d9c8  mov     ebx, r8d
0x18000d9cb  mov     r14, rcx
0x18000d9ce  mov     al, [rbp+arg_20]
0x18000d9d1  mov     [rsp+80h+var_60], al
0x18000d9d5  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18000d9da  mov     esi, eax
0x18000d9dc  test    eax, eax
0x18000d9de  js      loc_18000DC8C
0x18000d9e4  sub     ebx, 2
0x18000d9e7  jz      loc_18000DC80
0x18000d9ed  sub     ebx, 6
0x18000d9f0  jz      loc_18000DC59
0x18000d9f6  sub     ebx, 2
0x18000d9f9  jz      loc_18000DC32
0x18000d9ff  sub     ebx, 48h ; 'H'
0x18000da02  jz      loc_18000DC25
0x18000da08  sub     ebx, 0Eh
0x18000da0b  jz      loc_18000DAA7
0x18000da11  sub     ebx, 8
0x18000da14  jz      short loc_18000DA74
0x18000da16  sub     ebx, 1
0x18000da19  jz      short loc_18000DA4C
0x18000da1b  cmp     ebx, 1
0x18000da1e  jnz     loc_18000DC8A
0x18000da24  mov     rcx, [rdi+30h]; this
0x18000da28  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000da2d  mov     r8, rax
0x18000da30  test    rax, rax
0x18000da33  jz      loc_18000DC8A
0x18000da39  mov     rcx, [r14+200h]
0x18000da40  mov     rdx, [rcx]
0x18000da43  mov     rax, [rdx+120h]
0x18000da4a  jmp     short loc_18000DA9A
0x18000da4c  mov     rcx, [rdi+30h]; this
0x18000da50  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000da55  mov     r8, rax
0x18000da58  test    rax, rax
0x18000da5b  jz      loc_18000DC8A
0x18000da61  mov     rcx, [r14+200h]
0x18000da68  mov     rdx, [rcx]
0x18000da6b  mov     rax, [rdx+110h]
0x18000da72  jmp     short loc_18000DA9A
0x18000da74  mov     rcx, [rdi+30h]; this
0x18000da78  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000da7d  mov     r8, rax
0x18000da80  test    rax, rax
0x18000da83  jz      loc_18000DC8A
0x18000da89  mov     rcx, [r14+200h]
0x18000da90  mov     rdx, [rcx]
0x18000da93  mov     rax, [rdx+100h]
0x18000da9a  mov     rdx, r8
0x18000da9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa2  jmp     loc_18000DC8A
0x18000daa7  lea     rdx, [rbp+var_50]
0x18000daab  mov     rcx, [rdi+30h]
0x18000daaf  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18000dab4  nop
0x18000dab5  lea     rcx, [rbp+var_50]; this
0x18000dab9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000dabe  mov     ebx, eax
0x18000dac0  shr     ebx, 1
0x18000dac2  lea     rcx, [rbp+var_50]; this
0x18000dac6  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000dacb  and     eax, 1
0x18000dace  lea     ecx, [rbx+rax]; unsigned __int64
0x18000dad1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dad6  mov     rbx, rax
0x18000dad9  mov     [rbp+var_48], rax
0x18000dadd  test    rax, rax
0x18000dae0  jnz     short loc_18000DB23
0x18000dae2  mov     [rbp+var_38], al
0x18000dae5  lea     rax, byte_180052608
0x18000daec  mov     [rbp+var_30], rax
0x18000daf0  mov     [rbp+var_28], rbx
0x18000daf4  mov     [rbp+var_20], rbx
0x18000daf8  mov     [rbp+var_18], 0Eh
0x18000daff  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18000db07  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000db0e  mov     [rbp+pExceptionObject], rax
0x18000db12  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000db19  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000db1d  call    _CxxThrowException_0
0x18000db23  mov     r15b, 1
0x18000db26  xor     r12d, r12d
0x18000db29  mov     rsi, rbx
0x18000db2c  lea     rcx, [rbp+var_50]; this
0x18000db30  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000db35  mov     eax, eax
0x18000db37  cmp     r12, rax
0x18000db3a  jnb     loc_18000DBC4
0x18000db40  mov     rax, [rbp+var_50]
0x18000db44  test    rax, rax
0x18000db47  jz      short loc_18000DB4E
0x18000db49  mov     rdi, [rax]
0x18000db4c  jmp     short loc_18000DB50
0x18000db4e  xor     edi, edi
0x18000db50  movzx   edi, word ptr [rdi+r12*2]
0x18000db55  movzx   ecx, di; C
0x18000db58  call    cs:__imp_iswdigit
0x18000db5f  nop     dword ptr [rax+rax+00h]
0x18000db64  test    eax, eax
0x18000db66  jz      short loc_18000DB6E
0x18000db68  sub     dil, 30h ; '0'
0x18000db6c  jmp     short loc_18000DB8A
0x18000db6e  lea     eax, [rdi-61h]
0x18000db71  cmp     ax, 5
0x18000db75  ja      short loc_18000DB7D
0x18000db77  sub     dil, 57h ; 'W'
0x18000db7b  jmp     short loc_18000DB8A
0x18000db7d  lea     eax, [rdi-41h]
0x18000db80  cmp     ax, 5
0x18000db84  ja      short loc_18000DBA9
0x18000db86  sub     dil, 37h ; '7'
0x18000db8a  test    r15b, r15b
0x18000db8d  jz      short loc_18000DB97
0x18000db8f  mov     [rsi], dil
0x18000db92  xor     r15b, r15b
0x18000db95  jmp     short loc_18000DBBC
0x18000db97  mov     al, [rsi]
0x18000db99  shl     al, 4
0x18000db9c  add     al, dil
0x18000db9f  mov     [rsi], al
0x18000dba1  inc     rsi
0x18000dba4  mov     r15b, 1
0x18000dba7  jmp     short loc_18000DBBC
0x18000dba9  movzx   ecx, di; C
0x18000dbac  call    cs:__imp_iswspace
0x18000dbb3  nop     dword ptr [rax+rax+00h]
0x18000dbb8  test    eax, eax
0x18000dbba  jz      short loc_18000DC0C
0x18000dbbc  inc     r12
0x18000dbbf  jmp     loc_18000DB2C
0x18000dbc4  test    r15b, r15b
0x18000dbc7  jz      short loc_18000DC0C
0x18000dbc9  mov     edx, esi
0x18000dbcb  sub     edx, ebx
0x18000dbcd  sub     rsi, rbx
0x18000dbd0  cmp     rdx, rsi
0x18000dbd3  jnz     short loc_18000DC0C
0x18000dbd5  cmp     edx, 0FFFFh
0x18000dbdb  ja      short loc_18000DC0C
0x18000dbdd  mov     rcx, [r14+200h]
0x18000dbe4  mov     rax, [rcx]
0x18000dbe7  mov     r8, rbx
0x18000dbea  mov     rax, [rax+0B0h]
0x18000dbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf6  mov     esi, eax
0x18000dbf8  mov     rcx, rbx; Block
0x18000dbfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc00  nop
0x18000dc01  lea     rcx, [rbp+var_50]; this
0x18000dc05  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000dc0a  jmp     short loc_18000DC8A
0x18000dc0c  mov     rcx, rbx; Block
0x18000dc0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dc14  nop
0x18000dc15  lea     rcx, [rbp+var_50]; this
0x18000dc19  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000dc1e  mov     eax, 80041318h
0x18000dc23  jmp     short loc_18000DC8C
0x18000dc25  mov     rax, [r14+200h]
0x18000dc2c  or      dword ptr [rax+58h], 2
0x18000dc30  jmp     short loc_18000DC8A
0x18000dc32  mov     rcx, [rdi+30h]; this
0x18000dc36  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000dc3b  mov     r8, rax
0x18000dc3e  test    rax, rax
0x18000dc41  jz      short loc_18000DC8A
0x18000dc43  mov     rcx, [r14+200h]
0x18000dc4a  mov     rdx, [rcx]
0x18000dc4d  mov     rax, [rdx+90h]
0x18000dc54  jmp     loc_18000DA9A
0x18000dc59  mov     rcx, [rdi+30h]; this
0x18000dc5d  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18000dc62  mov     r8, rax
0x18000dc65  test    rax, rax
0x18000dc68  jz      short loc_18000DC8A
0x18000dc6a  mov     rcx, [r14+200h]
0x18000dc71  mov     rdx, [rcx]
0x18000dc74  mov     rax, [rdx+0A0h]
0x18000dc7b  jmp     loc_18000DA9A
0x18000dc80  mov     eax, [rdi+20h]
0x18000dc83  mov     [r14+21Ch], eax
0x18000dc8a  mov     eax, esi
0x18000dc8c  add     rsp, 80h
0x18000dc93  pop     r15
0x18000dc95  pop     r14
0x18000dc97  pop     r12
0x18000dc99  pop     rdi
0x18000dc9a  pop     rsi
0x18000dc9b  pop     rbx
0x18000dc9c  pop     rbp
0x18000dc9d  retn
```
