# ?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18004a100`
- end: `0x18004a5e4`
- name: `?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `1252`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007aa0`
- `0x180008d30`
- `0x180009a78`
- `0x18001c280`
- `0x18001c4b0`
- `0x18002da34`
- `0x18003b51c`
- `0x18004a100`
- `0x18004ca50`
- `0x180054010`

## import_xrefs

- `msvcrt!iswspace` at `0x18004a31f`
- `msvcrt!iswspace` at `0x18004a31f`
- `msvcrt!iswdigit` at `0x18004a2cc`
- `msvcrt!iswdigit` at `0x18004a2cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _ProcessValue__QITaskXmlHandler__BinXmlHandler__EEAAJAEBUSchema__W4TaskXmlNodeId__AEBUData_1__N_Z(
        __int64 a1,
        int *a2,
        int a3,
        __int64 a4,
        char a5)
{
  __int64 result; // rax
  unsigned int v10; // edi
  unsigned __int64 v11; // r13
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  unsigned __int16 *v19; // r8
  unsigned __int16 *v21; // r8
  unsigned __int16 *v22; // r8
  unsigned int v23; // ebx
  char v24; // al
  _BYTE *v25; // rax
  _BYTE *v26; // rbx
  int v27; // r12d
  _BYTE *v28; // r15
  __int64 *v29; // rdi
  __int64 v30; // rsi
  wint_t v31; // si
  char v32; // si
  __int64 v33; // r15
  unsigned __int16 *v34; // r8
  unsigned __int16 *NullTerminated; // r8
  _WORD *v36; // rdx
  __int64 **v37; // rbx
  __int16 v38; // dx
  __int64 *v39; // rcx
  __int64 v40; // rax
  __int16 v41; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v42[2]; // [rsp+38h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-29h] BYREF
  char v44; // [rsp+50h] [rbp-21h]
  __int64 *v45; // [rsp+58h] [rbp-19h]
  __int64 v46; // [rsp+60h] [rbp-11h]
  __int64 v47; // [rsp+68h] [rbp-9h]
  int v48; // [rsp+70h] [rbp-1h]
  __int64 v49; // [rsp+74h] [rbp+3h]

  result = ValidationXmlHandler::ProcessValue(a1, a2, a3, a4);
  v10 = result;
  v11 = 0;
  if ( (int)result < 0 )
    return result;
  if ( a3 != 2 )
  {
    if ( *a2 >= 65538 )
      return 2147942450LL;
    v12 = a3 - 2;
    if ( v12 )
    {
      v13 = v12 - 6;
      if ( !v13 )
      {
        NullTerminated = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
        if ( !NullTerminated )
          return v10;
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 520) + 160LL))(
                               *(_QWORD *)(a1 + 520),
                               NullTerminated);
      }
      v14 = v13 - 2;
      if ( !v14 )
      {
        v34 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
        if ( !v34 )
          return v10;
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 520) + 144LL))(
                               *(_QWORD *)(a1 + 520),
                               v34);
      }
      v15 = v14 - 72;
      if ( !v15 )
      {
        *(_DWORD *)(a1 + 528) |= 2u;
        return v10;
      }
      v16 = v15 - 14;
      if ( v16 )
      {
        v17 = v16 - 8;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 != 1 )
              return v10;
            v19 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
            if ( !v19 )
              return v10;
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 520) + 288LL))(
                                   *(_QWORD *)(a1 + 520),
                                   v19);
          }
          v21 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
          if ( v21 )
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 520) + 272LL))(
                                   *(_QWORD *)(a1 + 520),
                                   v21);
        }
        else
        {
          v22 = XmlParserTempString::GetNullTerminated(*(XmlParserTempString **)(a4 + 48));
          if ( v22 )
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 520) + 256LL))(
                                   *(_QWORD *)(a1 + 520),
                                   v22);
        }
        return v10;
      }
      XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v42);
      v23 = _bstr_t::length((_bstr_t *)v42) >> 1;
      v24 = _bstr_t::length((_bstr_t *)v42);
      v25 = operator new(v23 + (v24 & 1));
      v26 = v25;
      v42[1] = v25;
      if ( !v25 )
      {
        v44 = 0;
        v45 = &qword_180077320;
        v46 = 0;
        v47 = 0;
        v48 = 14;
        v49 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v27 = 1;
      v28 = v25;
      v29 = (__int64 *)v42[0];
      while ( 1 )
      {
        if ( v11 >= _bstr_t::length((_bstr_t *)v42) )
        {
          if ( v27 )
          {
            v33 = v28 - v26;
            if ( (unsigned int)v33 == v33 && (unsigned int)v33 <= 0xFFFF )
            {
              v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))(**(_QWORD **)(a1 + 520) + 176LL))(
                      *(_QWORD *)(a1 + 520),
                      (unsigned int)v33,
                      v26);
              operator delete(v26);
              _bstr_t::_Free((_bstr_t *)v42);
              return v10;
            }
          }
LABEL_41:
          operator delete(v26);
          _bstr_t::_Free((_bstr_t *)v42);
          return 2147750680LL;
        }
        if ( v29 )
          v30 = *v29;
        else
          v30 = 0;
        v31 = *(_WORD *)(v30 + 2 * v11);
        if ( iswdigit(v31) )
        {
          v32 = v31 - 48;
          goto LABEL_32;
        }
        if ( (unsigned __int16)(v31 - 97) <= 5u )
          break;
        if ( (unsigned __int16)(v31 - 65) <= 5u )
        {
          v32 = v31 - 55;
LABEL_32:
          if ( v27 )
          {
            *v28 = v32;
            v27 = 0;
          }
          else
          {
            *v28 = v32 + 16 * *v28;
            ++v28;
            v27 = 1;
          }
          goto LABEL_36;
        }
        if ( !iswspace(v31) )
          goto LABEL_41;
LABEL_36:
        ++v11;
      }
      v32 = v31 - 87;
      goto LABEL_32;
    }
  }
  if ( *(int *)(a4 + 32) >= 65538 )
    return 2147942450LL;
  if ( *(_DWORD *)(a4 + 32) == 0x10000 )
    return (unsigned int)-2147467263;
  v36 = *(_WORD **)(a1 + 536);
  if ( !v36 )
    return 2147942487LL;
  if ( *v36 == 92 )
    *(_QWORD *)(a1 + 536) = ++v36;
  if ( (*(_BYTE *)(a1 + 532) & 4) == 0 )
    goto LABEL_69;
  v37 = (__int64 **)(a1 + 520);
  result = (*(__int64 (__fastcall **)(_QWORD, _WORD *, GUID *, __int64, char))(**(_QWORD **)(a1 + 512) + 48LL))(
             *(_QWORD *)(a1 + 512),
             v36,
             &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
             a1 + 520,
             a5);
  v10 = result;
  if ( (int)result < 0 )
  {
    if ( (*(_BYTE *)(a1 + 532) & 2) == 0 )
      return result;
    goto LABEL_69;
  }
  v41 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(**v37 + 40))(*v37, &v41);
  if ( (int)result < 0 )
    return result;
  while ( 1 )
  {
    v38 = v41--;
    v39 = *v37;
    v40 = **v37;
    if ( !v38 )
      break;
    result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v40 + 32))(v39, 0);
    if ( (int)result < 0 )
      return result;
  }
  result = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(v40 + 144))(v39, &Src);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(**v37 + 160))(*v37, &Src);
    if ( (int)result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(**v37 + 176))(*v37, 0, 0);
      if ( (int)result >= 0 )
      {
        result = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(**v37 + 224))(*v37, 0);
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(**v37 + 272))(*v37, &Src);
          if ( (int)result >= 0 )
          {
            result = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *))(**v37 + 288))(*v37, &Src);
            v10 = result;
            if ( (int)result >= 0 )
            {
LABEL_69:
              if ( !*(_QWORD *)(a1 + 520) && (*(_BYTE *)(a1 + 532) & 2) != 0 )
              {
                result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, GUID *, __int64))(**(_QWORD **)(a1 + 512)
                                                                                            + 64LL))(
                           *(_QWORD *)(a1 + 512),
                           *(_QWORD *)(a1 + 536),
                           &CLSID_CTask,
                           &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                           a1 + 520);
                v10 = result;
                if ( (int)result < 0 )
                  return result;
              }
              return v10;
            }
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
0x18004a100  push    rbp
0x18004a102  push    rbx
0x18004a103  push    rsi
0x18004a104  push    rdi
0x18004a105  push    r12
0x18004a107  push    r13
0x18004a109  push    r14
0x18004a10b  push    r15
0x18004a10d  lea     rbp, [rsp-17h]
0x18004a112  sub     rsp, 88h
0x18004a119  mov     rsi, r9
0x18004a11c  mov     ebx, r8d
0x18004a11f  mov     r15, rdx
0x18004a122  mov     r14, rcx
0x18004a125  mov     al, [rbp+4Fh+arg_20]
0x18004a128  mov     byte ptr [rsp+0C0h+var_A0], al
0x18004a12c  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18004a131  mov     edi, eax
0x18004a133  xor     r13d, r13d
0x18004a136  test    eax, eax
0x18004a138  js      loc_18004A5D0
0x18004a13e  mov     ecx, 10002h
0x18004a143  lea     r12d, [r13+2]
0x18004a147  cmp     ebx, r12d
0x18004a14a  jz      loc_18004A3FC
0x18004a150  cmp     [r15], ecx
0x18004a153  jge     loc_18004A401
0x18004a159  sub     ebx, r12d
0x18004a15c  jz      loc_18004A3FC
0x18004a162  sub     ebx, 6
0x18004a165  jz      loc_18004A3D1
0x18004a16b  sub     ebx, r12d
0x18004a16e  jz      loc_18004A3A6
0x18004a174  sub     ebx, 48h ; 'H'
0x18004a177  jz      loc_18004A39A
0x18004a17d  sub     ebx, 0Eh
0x18004a180  jz      loc_18004A21E
0x18004a186  sub     ebx, 8
0x18004a189  jz      short loc_18004A1E9
0x18004a18b  sub     ebx, 1
0x18004a18e  jz      short loc_18004A1C1
0x18004a190  cmp     ebx, 1
0x18004a193  jnz     loc_18004A5CE
0x18004a199  mov     rcx, [rsi+30h]; this
0x18004a19d  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004a1a2  mov     r8, rax
0x18004a1a5  test    rax, rax
0x18004a1a8  jz      loc_18004A5CE
0x18004a1ae  mov     rcx, [r14+208h]
0x18004a1b5  mov     rdx, [rcx]
0x18004a1b8  mov     rax, [rdx+120h]
0x18004a1bf  jmp     short loc_18004A20F
0x18004a1c1  mov     rcx, [rsi+30h]; this
0x18004a1c5  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004a1ca  mov     r8, rax
0x18004a1cd  test    rax, rax
0x18004a1d0  jz      loc_18004A5CE
0x18004a1d6  mov     rcx, [r14+208h]
0x18004a1dd  mov     rdx, [rcx]
0x18004a1e0  mov     rax, [rdx+110h]
0x18004a1e7  jmp     short loc_18004A20F
0x18004a1e9  mov     rcx, [rsi+30h]; this
0x18004a1ed  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004a1f2  mov     r8, rax
0x18004a1f5  test    rax, rax
0x18004a1f8  jz      loc_18004A5CE
0x18004a1fe  mov     rcx, [r14+208h]
0x18004a205  mov     rdx, [rcx]
0x18004a208  mov     rax, [rdx+100h]
0x18004a20f  mov     rdx, r8
0x18004a212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a217  mov     edi, eax
0x18004a219  jmp     loc_18004A5CE
0x18004a21e  lea     rdx, [rbp+4Fh+var_88]
0x18004a222  mov     rcx, [rsi+30h]
0x18004a226  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18004a22b  nop
0x18004a22c  lea     rcx, [rbp+4Fh+var_88]; this
0x18004a230  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004a235  mov     ebx, eax
0x18004a237  shr     ebx, 1
0x18004a239  lea     rcx, [rbp+4Fh+var_88]; this
0x18004a23d  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004a242  and     eax, 1
0x18004a245  lea     ecx, [rbx+rax]; unsigned __int64
0x18004a248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a24d  mov     rbx, rax
0x18004a250  mov     [rbp+4Fh+var_80], rax
0x18004a254  test    rax, rax
0x18004a257  jnz     short loc_18004A29B
0x18004a259  mov     [rbp+4Fh+var_70], r13b
0x18004a25d  lea     rax, qword_180077320
0x18004a264  mov     [rbp+4Fh+var_68], rax
0x18004a268  mov     [rbp+4Fh+var_60], r13
0x18004a26c  mov     [rbp+4Fh+var_58], r13
0x18004a270  mov     [rbp+4Fh+var_50], 0Eh
0x18004a277  mov     [rbp+4Fh+var_4C], 0FFFFFFFFFFFFFFFFh
0x18004a27f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004a286  mov     [rbp+4Fh+pExceptionObject], rax
0x18004a28a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18004a291  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004a295  call    _CxxThrowException_0
0x18004a29b  mov     r12d, 1
0x18004a2a1  mov     r15, rbx
0x18004a2a4  mov     rdi, [rbp+4Fh+var_88]
0x18004a2a8  lea     rcx, [rbp+4Fh+var_88]; this
0x18004a2ac  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004a2b1  mov     eax, eax
0x18004a2b3  cmp     r13, rax
0x18004a2b6  jnb     short loc_18004A331
0x18004a2b8  test    rdi, rdi
0x18004a2bb  jz      short loc_18004A2C2
0x18004a2bd  mov     rsi, [rdi]
0x18004a2c0  jmp     short loc_18004A2C4
0x18004a2c2  xor     esi, esi
0x18004a2c4  movzx   esi, word ptr [rsi+r13*2]
0x18004a2c9  movzx   ecx, si; C
0x18004a2cc  call    cs:__imp_iswdigit
0x18004a2d2  test    eax, eax
0x18004a2d4  jz      short loc_18004A2DC
0x18004a2d6  sub     sil, 30h ; '0'
0x18004a2da  jmp     short loc_18004A2F8
0x18004a2dc  lea     eax, [rsi-61h]
0x18004a2df  cmp     ax, 5
0x18004a2e3  ja      short loc_18004A2EB
0x18004a2e5  sub     sil, 57h ; 'W'
0x18004a2e9  jmp     short loc_18004A2F8
0x18004a2eb  lea     eax, [rsi-41h]
0x18004a2ee  cmp     ax, 5
0x18004a2f2  ja      short loc_18004A31C
0x18004a2f4  sub     sil, 37h ; '7'
0x18004a2f8  test    r12d, r12d
0x18004a2fb  jz      short loc_18004A305
0x18004a2fd  mov     [r15], sil
0x18004a300  xor     r12d, r12d
0x18004a303  jmp     short loc_18004A329
0x18004a305  mov     al, [r15]
0x18004a308  shl     al, 4
0x18004a30b  add     al, sil
0x18004a30e  mov     [r15], al
0x18004a311  inc     r15
0x18004a314  mov     r12d, 1
0x18004a31a  jmp     short loc_18004A329
0x18004a31c  movzx   ecx, si; C
0x18004a31f  call    cs:__imp_iswspace
0x18004a325  test    eax, eax
0x18004a327  jz      short loc_18004A37E
0x18004a329  inc     r13
0x18004a32c  jmp     loc_18004A2A8
0x18004a331  test    r12d, r12d
0x18004a334  jz      short loc_18004A37E
0x18004a336  mov     edx, r15d
0x18004a339  sub     edx, ebx
0x18004a33b  sub     r15, rbx
0x18004a33e  cmp     rdx, r15
0x18004a341  jnz     short loc_18004A37E
0x18004a343  mov     edi, 0FFFFh
0x18004a348  cmp     edx, edi
0x18004a34a  ja      short loc_18004A37E
0x18004a34c  mov     rcx, [r14+208h]
0x18004a353  mov     rax, [rcx]
0x18004a356  mov     r8, rbx
0x18004a359  mov     rax, [rax+0B0h]
0x18004a360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a365  mov     edi, eax
0x18004a367  mov     rcx, rbx; void *
0x18004a36a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a36f  nop
0x18004a370  lea     rcx, [rbp+4Fh+var_88]; this
0x18004a374  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a379  jmp     loc_18004A5CE
0x18004a37e  mov     rcx, rbx; void *
0x18004a381  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a386  nop
0x18004a387  lea     rcx, [rbp+4Fh+var_88]; this
0x18004a38b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004a390  mov     eax, 80041318h
0x18004a395  jmp     loc_18004A5D0
0x18004a39a  or      [r14+210h], r12d
0x18004a3a1  jmp     loc_18004A5CE
0x18004a3a6  mov     rcx, [rsi+30h]; this
0x18004a3aa  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004a3af  mov     r8, rax
0x18004a3b2  test    rax, rax
0x18004a3b5  jz      loc_18004A5CE
0x18004a3bb  mov     rcx, [r14+208h]
0x18004a3c2  mov     rdx, [rcx]
0x18004a3c5  mov     rax, [rdx+90h]
0x18004a3cc  jmp     loc_18004A20F
0x18004a3d1  mov     rcx, [rsi+30h]; this
0x18004a3d5  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004a3da  mov     r8, rax
0x18004a3dd  test    rax, rax
0x18004a3e0  jz      loc_18004A5CE
0x18004a3e6  mov     rcx, [r14+208h]
0x18004a3ed  mov     rdx, [rcx]
0x18004a3f0  mov     rax, [rdx+0A0h]
0x18004a3f7  jmp     loc_18004A20F
0x18004a3fc  cmp     [rsi+20h], ecx
0x18004a3ff  jl      short loc_18004A40B
0x18004a401  mov     eax, 80070032h
0x18004a406  jmp     loc_18004A5D0
0x18004a40b  cmp     dword ptr [rsi+20h], 10000h
0x18004a412  jnz     short loc_18004A41E
0x18004a414  mov     edi, 80004001h
0x18004a419  jmp     loc_18004A5CE
0x18004a41e  mov     rdx, [r14+218h]
0x18004a425  test    rdx, rdx
0x18004a428  jnz     short loc_18004A434
0x18004a42a  mov     eax, 80070057h
0x18004a42f  jmp     loc_18004A5D0
0x18004a434  cmp     word ptr [rdx], 5Ch ; '\'
0x18004a438  jnz     short loc_18004A444
0x18004a43a  add     rdx, r12
0x18004a43d  mov     [r14+218h], rdx
0x18004a444  test    byte ptr [r14+214h], 4
0x18004a44c  jz      loc_18004A586
0x18004a452  mov     rcx, [r14+200h]
0x18004a459  lea     rbx, [r14+208h]
0x18004a460  mov     rax, [rcx]
0x18004a463  mov     r9, rbx
0x18004a466  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18004a46d  mov     rax, [rax+30h]
0x18004a471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a476  mov     edi, eax
0x18004a478  test    eax, eax
0x18004a47a  jns     short loc_18004A48E
0x18004a47c  test    [r14+214h], r12b
0x18004a483  jnz     loc_18004A586
0x18004a489  jmp     loc_18004A5D0
0x18004a48e  mov     [rbp+4Fh+var_90], r13w
0x18004a493  mov     rcx, [rbx]
0x18004a496  mov     rax, [rcx]
0x18004a499  lea     rdx, [rbp+4Fh+var_90]
0x18004a49d  mov     rax, [rax+28h]
0x18004a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4a6  test    eax, eax
0x18004a4a8  js      loc_18004A5D0
0x18004a4ae  mov     edi, 0FFFFh
0x18004a4b3  movzx   eax, [rbp+4Fh+var_90]
0x18004a4b7  movzx   edx, ax
0x18004a4ba  add     ax, di
0x18004a4bd  mov     [rbp+4Fh+var_90], ax
0x18004a4c1  mov     rcx, [rbx]
0x18004a4c4  mov     rax, [rcx]
0x18004a4c7  test    dx, dx
0x18004a4ca  jz      short loc_18004A4E0
0x18004a4cc  xor     edx, edx
0x18004a4ce  mov     rax, [rax+20h]
0x18004a4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4d7  test    eax, eax
0x18004a4d9  jns     short loc_18004A4B3
0x18004a4db  jmp     loc_18004A5D0
0x18004a4e0  lea     rdi, Src
0x18004a4e7  mov     rdx, rdi
0x18004a4ea  mov     rax, [rax+90h]
0x18004a4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4f6  test    eax, eax
0x18004a4f8  js      loc_18004A5D0
0x18004a4fe  mov     rcx, [rbx]
0x18004a501  mov     rax, [rcx]
0x18004a504  mov     rdx, rdi
0x18004a507  mov     rax, [rax+0A0h]
0x18004a50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a513  test    eax, eax
0x18004a515  js      loc_18004A5D0
0x18004a51b  mov     rcx, [rbx]
0x18004a51e  mov     rax, [rcx]
0x18004a521  xor     edx, edx
0x18004a523  xor     r8d, r8d
0x18004a526  mov     rax, [rax+0B0h]
0x18004a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a532  test    eax, eax
0x18004a534  js      loc_18004A5D0
0x18004a53a  mov     rcx, [rbx]
0x18004a53d  mov     rax, [rcx]
0x18004a540  xor     edx, edx
0x18004a542  mov     rax, [rax+0E0h]
0x18004a549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a54e  test    eax, eax
0x18004a550  js      short loc_18004A5D0
0x18004a552  mov     rcx, [rbx]
0x18004a555  mov     rax, [rcx]
0x18004a558  mov     rdx, rdi
0x18004a55b  mov     rax, [rax+110h]
0x18004a562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a567  test    eax, eax
0x18004a569  js      short loc_18004A5D0
0x18004a56b  mov     rcx, [rbx]
0x18004a56e  mov     rax, [rcx]
0x18004a571  mov     rdx, rdi
0x18004a574  mov     rax, [rax+120h]
0x18004a57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a580  mov     edi, eax
0x18004a582  test    eax, eax
0x18004a584  js      short loc_18004A5D0
0x18004a586  lea     rdx, [r14+208h]
0x18004a58d  cmp     [rdx], r13
0x18004a590  jnz     short loc_18004A5CE
0x18004a592  test    [r14+214h], r12b
  ... truncated ...
```
