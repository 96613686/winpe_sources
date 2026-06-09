# ?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z

- ea: `0x18004dcb0`
- end: `0x18004e1a5`
- name: `?ProcessValue@?QITaskXmlHandler@@BinXmlHandler@@EEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@1@_N@Z`
- size: `1269`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007e90`
- `0x180009150`
- `0x18000a460`
- `0x18001d3f0`
- `0x18001d650`
- `0x18002fe74`
- `0x18003e88c`
- `0x18004dcb0`
- `0x180050690`
- `0x180058010`

## import_xrefs

- `msvcrt!iswspace` at `0x18004ded9`
- `msvcrt!iswspace` at `0x18004ded9`
- `msvcrt!iswdigit` at `0x18004de80`
- `msvcrt!iswdigit` at `0x18004de80`

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
        v45 = &qword_18007B2F0;
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
0x18004dcb0  push    rbp
0x18004dcb2  push    rbx
0x18004dcb3  push    rsi
0x18004dcb4  push    rdi
0x18004dcb5  push    r12
0x18004dcb7  push    r13
0x18004dcb9  push    r14
0x18004dcbb  push    r15
0x18004dcbd  lea     rbp, [rsp-17h]
0x18004dcc2  sub     rsp, 88h
0x18004dcc9  mov     rsi, r9
0x18004dccc  mov     ebx, r8d
0x18004dccf  mov     r15, rdx
0x18004dcd2  mov     r14, rcx
0x18004dcd5  mov     al, [rbp+4Fh+arg_20]
0x18004dcd8  mov     byte ptr [rsp+0C0h+var_A0], al
0x18004dcdc  call    ?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z; ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)
0x18004dce1  mov     edi, eax
0x18004dce3  xor     r13d, r13d
0x18004dce6  test    eax, eax
0x18004dce8  js      loc_18004E190
0x18004dcee  mov     ecx, 10002h
0x18004dcf3  lea     r12d, [r13+2]
0x18004dcf7  cmp     ebx, r12d
0x18004dcfa  jz      loc_18004DFBC
0x18004dd00  cmp     [r15], ecx
0x18004dd03  jge     loc_18004DFC1
0x18004dd09  sub     ebx, r12d
0x18004dd0c  jz      loc_18004DFBC
0x18004dd12  sub     ebx, 6
0x18004dd15  jz      loc_18004DF91
0x18004dd1b  sub     ebx, r12d
0x18004dd1e  jz      loc_18004DF66
0x18004dd24  sub     ebx, 48h ; 'H'
0x18004dd27  jz      loc_18004DF5A
0x18004dd2d  sub     ebx, 0Eh
0x18004dd30  jz      loc_18004DDCE
0x18004dd36  sub     ebx, 8
0x18004dd39  jz      short loc_18004DD99
0x18004dd3b  sub     ebx, 1
0x18004dd3e  jz      short loc_18004DD71
0x18004dd40  cmp     ebx, 1
0x18004dd43  jnz     loc_18004E18E
0x18004dd49  mov     rcx, [rsi+30h]; this
0x18004dd4d  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004dd52  mov     r8, rax
0x18004dd55  test    rax, rax
0x18004dd58  jz      loc_18004E18E
0x18004dd5e  mov     rcx, [r14+208h]
0x18004dd65  mov     rdx, [rcx]
0x18004dd68  mov     rax, [rdx+120h]
0x18004dd6f  jmp     short loc_18004DDBF
0x18004dd71  mov     rcx, [rsi+30h]; this
0x18004dd75  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004dd7a  mov     r8, rax
0x18004dd7d  test    rax, rax
0x18004dd80  jz      loc_18004E18E
0x18004dd86  mov     rcx, [r14+208h]
0x18004dd8d  mov     rdx, [rcx]
0x18004dd90  mov     rax, [rdx+110h]
0x18004dd97  jmp     short loc_18004DDBF
0x18004dd99  mov     rcx, [rsi+30h]; this
0x18004dd9d  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004dda2  mov     r8, rax
0x18004dda5  test    rax, rax
0x18004dda8  jz      loc_18004E18E
0x18004ddae  mov     rcx, [r14+208h]
0x18004ddb5  mov     rdx, [rcx]
0x18004ddb8  mov     rax, [rdx+100h]
0x18004ddbf  mov     rdx, r8
0x18004ddc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddc7  mov     edi, eax
0x18004ddc9  jmp     loc_18004E18E
0x18004ddce  lea     rdx, [rbp+4Fh+var_88]
0x18004ddd2  mov     rcx, [rsi+30h]
0x18004ddd6  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18004dddb  nop
0x18004dddc  lea     rcx, [rbp+4Fh+var_88]; this
0x18004dde0  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004dde5  mov     ebx, eax
0x18004dde7  shr     ebx, 1
0x18004dde9  lea     rcx, [rbp+4Fh+var_88]; this
0x18004dded  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004ddf2  and     eax, 1
0x18004ddf5  lea     ecx, [rbx+rax]; unsigned __int64
0x18004ddf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ddfd  mov     rbx, rax
0x18004de00  mov     [rbp+4Fh+var_80], rax
0x18004de04  test    rax, rax
0x18004de07  jnz     short loc_18004DE4B
0x18004de09  mov     [rbp+4Fh+var_70], r13b
0x18004de0d  lea     rax, qword_18007B2F0
0x18004de14  mov     [rbp+4Fh+var_68], rax
0x18004de18  mov     [rbp+4Fh+var_60], r13
0x18004de1c  mov     [rbp+4Fh+var_58], r13
0x18004de20  mov     [rbp+4Fh+var_50], 0Eh
0x18004de27  mov     [rbp+4Fh+var_4C], 0FFFFFFFFFFFFFFFFh
0x18004de2f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18004de36  mov     [rbp+4Fh+pExceptionObject], rax
0x18004de3a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18004de41  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18004de45  call    _CxxThrowException_0
0x18004de4b  mov     r12d, 1
0x18004de51  mov     r15, rbx
0x18004de54  mov     rdi, [rbp+4Fh+var_88]
0x18004de58  lea     rcx, [rbp+4Fh+var_88]; this
0x18004de5c  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18004de61  mov     eax, eax
0x18004de63  cmp     r13, rax
0x18004de66  jnb     loc_18004DEF1
0x18004de6c  test    rdi, rdi
0x18004de6f  jz      short loc_18004DE76
0x18004de71  mov     rsi, [rdi]
0x18004de74  jmp     short loc_18004DE78
0x18004de76  xor     esi, esi
0x18004de78  movzx   esi, word ptr [rsi+r13*2]
0x18004de7d  movzx   ecx, si; C
0x18004de80  call    cs:__imp_iswdigit
0x18004de87  nop     dword ptr [rax+rax+00h]
0x18004de8c  test    eax, eax
0x18004de8e  jz      short loc_18004DE96
0x18004de90  sub     sil, 30h ; '0'
0x18004de94  jmp     short loc_18004DEB2
0x18004de96  lea     eax, [rsi-61h]
0x18004de99  cmp     ax, 5
0x18004de9d  ja      short loc_18004DEA5
0x18004de9f  sub     sil, 57h ; 'W'
0x18004dea3  jmp     short loc_18004DEB2
0x18004dea5  lea     eax, [rsi-41h]
0x18004dea8  cmp     ax, 5
0x18004deac  ja      short loc_18004DED6
0x18004deae  sub     sil, 37h ; '7'
0x18004deb2  test    r12d, r12d
0x18004deb5  jz      short loc_18004DEBF
0x18004deb7  mov     [r15], sil
0x18004deba  xor     r12d, r12d
0x18004debd  jmp     short loc_18004DEE9
0x18004debf  mov     al, [r15]
0x18004dec2  shl     al, 4
0x18004dec5  add     al, sil
0x18004dec8  mov     [r15], al
0x18004decb  inc     r15
0x18004dece  mov     r12d, 1
0x18004ded4  jmp     short loc_18004DEE9
0x18004ded6  movzx   ecx, si; C
0x18004ded9  call    cs:__imp_iswspace
0x18004dee0  nop     dword ptr [rax+rax+00h]
0x18004dee5  test    eax, eax
0x18004dee7  jz      short loc_18004DF3E
0x18004dee9  inc     r13
0x18004deec  jmp     loc_18004DE58
0x18004def1  test    r12d, r12d
0x18004def4  jz      short loc_18004DF3E
0x18004def6  mov     edx, r15d
0x18004def9  sub     edx, ebx
0x18004defb  sub     r15, rbx
0x18004defe  cmp     rdx, r15
0x18004df01  jnz     short loc_18004DF3E
0x18004df03  mov     edi, 0FFFFh
0x18004df08  cmp     edx, edi
0x18004df0a  ja      short loc_18004DF3E
0x18004df0c  mov     rcx, [r14+208h]
0x18004df13  mov     rax, [rcx]
0x18004df16  mov     r8, rbx
0x18004df19  mov     rax, [rax+0B0h]
0x18004df20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df25  mov     edi, eax
0x18004df27  mov     rcx, rbx; void *
0x18004df2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004df2f  nop
0x18004df30  lea     rcx, [rbp+4Fh+var_88]; this
0x18004df34  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004df39  jmp     loc_18004E18E
0x18004df3e  mov     rcx, rbx; void *
0x18004df41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004df46  nop
0x18004df47  lea     rcx, [rbp+4Fh+var_88]; this
0x18004df4b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004df50  mov     eax, 80041318h
0x18004df55  jmp     loc_18004E190
0x18004df5a  or      [r14+210h], r12d
0x18004df61  jmp     loc_18004E18E
0x18004df66  mov     rcx, [rsi+30h]; this
0x18004df6a  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004df6f  mov     r8, rax
0x18004df72  test    rax, rax
0x18004df75  jz      loc_18004E18E
0x18004df7b  mov     rcx, [r14+208h]
0x18004df82  mov     rdx, [rcx]
0x18004df85  mov     rax, [rdx+90h]
0x18004df8c  jmp     loc_18004DDBF
0x18004df91  mov     rcx, [rsi+30h]; this
0x18004df95  call    ?GetNullTerminated@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::GetNullTerminated(void)
0x18004df9a  mov     r8, rax
0x18004df9d  test    rax, rax
0x18004dfa0  jz      loc_18004E18E
0x18004dfa6  mov     rcx, [r14+208h]
0x18004dfad  mov     rdx, [rcx]
0x18004dfb0  mov     rax, [rdx+0A0h]
0x18004dfb7  jmp     loc_18004DDBF
0x18004dfbc  cmp     [rsi+20h], ecx
0x18004dfbf  jl      short loc_18004DFCB
0x18004dfc1  mov     eax, 80070032h
0x18004dfc6  jmp     loc_18004E190
0x18004dfcb  cmp     dword ptr [rsi+20h], 10000h
0x18004dfd2  jnz     short loc_18004DFDE
0x18004dfd4  mov     edi, 80004001h
0x18004dfd9  jmp     loc_18004E18E
0x18004dfde  mov     rdx, [r14+218h]
0x18004dfe5  test    rdx, rdx
0x18004dfe8  jnz     short loc_18004DFF4
0x18004dfea  mov     eax, 80070057h
0x18004dfef  jmp     loc_18004E190
0x18004dff4  cmp     word ptr [rdx], 5Ch ; '\'
0x18004dff8  jnz     short loc_18004E004
0x18004dffa  add     rdx, r12
0x18004dffd  mov     [r14+218h], rdx
0x18004e004  test    byte ptr [r14+214h], 4
0x18004e00c  jz      loc_18004E146
0x18004e012  mov     rcx, [r14+200h]
0x18004e019  lea     rbx, [r14+208h]
0x18004e020  mov     rax, [rcx]
0x18004e023  mov     r9, rbx
0x18004e026  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18004e02d  mov     rax, [rax+30h]
0x18004e031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e036  mov     edi, eax
0x18004e038  test    eax, eax
0x18004e03a  jns     short loc_18004E04E
0x18004e03c  test    [r14+214h], r12b
0x18004e043  jnz     loc_18004E146
0x18004e049  jmp     loc_18004E190
0x18004e04e  mov     [rbp+4Fh+var_90], r13w
0x18004e053  mov     rcx, [rbx]
0x18004e056  mov     rax, [rcx]
0x18004e059  lea     rdx, [rbp+4Fh+var_90]
0x18004e05d  mov     rax, [rax+28h]
0x18004e061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e066  test    eax, eax
0x18004e068  js      loc_18004E190
0x18004e06e  mov     edi, 0FFFFh
0x18004e073  movzx   eax, [rbp+4Fh+var_90]
0x18004e077  movzx   edx, ax
0x18004e07a  add     ax, di
0x18004e07d  mov     [rbp+4Fh+var_90], ax
0x18004e081  mov     rcx, [rbx]
0x18004e084  mov     rax, [rcx]
0x18004e087  test    dx, dx
0x18004e08a  jz      short loc_18004E0A0
0x18004e08c  xor     edx, edx
0x18004e08e  mov     rax, [rax+20h]
0x18004e092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e097  test    eax, eax
0x18004e099  jns     short loc_18004E073
0x18004e09b  jmp     loc_18004E190
0x18004e0a0  lea     rdi, Src
0x18004e0a7  mov     rdx, rdi
0x18004e0aa  mov     rax, [rax+90h]
0x18004e0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0b6  test    eax, eax
0x18004e0b8  js      loc_18004E190
0x18004e0be  mov     rcx, [rbx]
0x18004e0c1  mov     rax, [rcx]
0x18004e0c4  mov     rdx, rdi
0x18004e0c7  mov     rax, [rax+0A0h]
0x18004e0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0d3  test    eax, eax
0x18004e0d5  js      loc_18004E190
0x18004e0db  mov     rcx, [rbx]
0x18004e0de  mov     rax, [rcx]
0x18004e0e1  xor     edx, edx
0x18004e0e3  xor     r8d, r8d
0x18004e0e6  mov     rax, [rax+0B0h]
0x18004e0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0f2  test    eax, eax
0x18004e0f4  js      loc_18004E190
0x18004e0fa  mov     rcx, [rbx]
0x18004e0fd  mov     rax, [rcx]
0x18004e100  xor     edx, edx
0x18004e102  mov     rax, [rax+0E0h]
0x18004e109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e10e  test    eax, eax
0x18004e110  js      short loc_18004E190
0x18004e112  mov     rcx, [rbx]
0x18004e115  mov     rax, [rcx]
0x18004e118  mov     rdx, rdi
0x18004e11b  mov     rax, [rax+110h]
0x18004e122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e127  test    eax, eax
0x18004e129  js      short loc_18004E190
0x18004e12b  mov     rcx, [rbx]
0x18004e12e  mov     rax, [rcx]
0x18004e131  mov     rdx, rdi
0x18004e134  mov     rax, [rax+120h]
0x18004e13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e140  mov     edi, eax
0x18004e142  test    eax, eax
0x18004e144  js      short loc_18004E190
0x18004e146  lea     rdx, [r14+208h]
0x18004e14d  cmp     [rdx], r13
  ... truncated ...
```
