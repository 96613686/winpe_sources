# DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x1800220d8`
- end: `0x1800224fa`
- name: `??$DeserializeFromFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z`
- size: `1058`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, _BYTE *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005360`
- `0x180006110`
- `0x18001d47c`

## callees

- `0x18000220c`
- `0x180020710`
- `0x180020af4`
- `0x1800215c8`
- `0x1800220d8`
- `0x180022500`
- `0x180022d4c`
- `0x180022ee8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800222bf`
- `KERNEL32!ReadFile` at `0x1800222bf`
- `KERNEL32!GetFileSizeEx` at `0x1800221c4`
- `KERNEL32!GetFileSizeEx` at `0x1800221c4`
- `ntdll!RtlComputeCrc32` at `0x1800223d7`
- `ntdll!RtlComputeCrc32` at `0x1800223d7`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180022431`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180022431`
- `RPCRT4!MesHandleFree` at `0x1800224c5`
- `RPCRT4!MesHandleFree` at `0x1800224c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002226b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002226b`
- `OLEAUT32!__imp_SysFreeString` at `0x180022380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002238f`
- `OLEAUT32!__imp_SysFreeString` at `0x180022380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002238f`

## string_xrefs

- `0x180022140`: `DeserializeFromFile`

## pseudocode

```c
__int64 __fastcall DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(HANDLE hFile, __int64 a2, __int64 a3, _BYTE *a4)
{
  char v5; // bl
  void *v7; // rdi
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD v14; // r13d
  LPVOID v15; // rax
  __int16 v16; // cx
  const struct _GUID *v17; // rdi
  unsigned int v18; // esi
  struct _GUID *v19; // r12
  DWORD v20; // r13d
  __int64 v21; // rcx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 v24; // rax
  bool v25; // zf
  unsigned int v26; // esi
  ULONG v27; // eax
  ULONG v28; // ebx
  int v29; // eax
  bool v30; // sf
  signed int v31; // eax
  unsigned int v32; // ebx
  handle_t pHandle; // [rsp+30h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-31h] BYREF
  BSTR v36; // [rsp+40h] [rbp-29h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-21h] BYREF
  __int16 v38; // [rsp+4Ch] [rbp-1Dh]
  __int16 v39; // [rsp+4Eh] [rbp-1Bh]
  LPVOID pv; // [rsp+D0h] [rbp+67h]
  __int64 NumberOfBytesRead; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+E0h] [rbp+77h] BYREF
  int v43; // [rsp+E4h] [rbp+7Bh]
  union _LARGE_INTEGER FileSize; // [rsp+E8h] [rbp+7Fh] BYREF

  v43 = HIDWORD(a3);
  NumberOfBytesRead = a2;
  v5 = 0;
  nNumberOfBytesToRead = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DeserializeFromFile", 0x8Eu, 1u);
  pHandle = 0;
  v7 = 0;
  FileSize.QuadPart = 0;
  nNumberOfBytesToRead = 0;
  LODWORD(NumberOfBytesRead) = 0;
  if ( a4 )
  {
    v8 = 152;
    v9 = a4;
    do
    {
      *v9++ = 0;
      --v8;
    }
    while ( v8 );
  }
  v10 = 159;
  if ( !hFile )
    goto LABEL_55;
  v38 = 159;
  if ( hFile == (HANDLE)-1LL )
  {
    v10 = 160;
    goto LABEL_55;
  }
  v38 = 162;
  v10 = 163;
  if ( !a4 )
  {
LABEL_55:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_56;
  }
  LastFailureAsHRESULT = 0;
  v38 = 163;
  if ( GetFileSizeEx(hFile, &FileSize) )
  {
    LastFailureAsHRESULT = 0;
    v38 = 169;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v13, (unsigned int)FileSize.HighPart, FileSize.LowPart);
    v10 = 172;
    if ( FileSize.QuadPart >= 0x10000000 || (v38 = 172, v10 = 173, FileSize.QuadPart <= 0x18uLL) )
    {
      LastFailureAsHRESULT = -2147024883;
    }
    else
    {
      v38 = 173;
      LastFailureAsHRESULT = LongLongToULong(FileSize.QuadPart, &nNumberOfBytesToRead);
      v10 = 174;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v14 = nNumberOfBytesToRead;
        v38 = 174;
        v15 = CoTaskMemAlloc(nNumberOfBytesToRead + 7);
        pv = v15;
        v7 = v15;
        v16 = 182;
        if ( !v15 )
        {
          LastFailureAsHRESULT = -2147024882;
          v39 = 182;
          goto LABEL_57;
        }
        LastFailureAsHRESULT = 0;
        v17 = (const struct _GUID *)(((unsigned __int64)v15 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        v18 = v14;
        v19 = (struct _GUID *)v17;
        while ( 1 )
        {
          v38 = v16;
          if ( !v18 )
            break;
          v20 = 0x100000;
          if ( v18 < 0x100000 )
            v20 = v18;
          if ( !ReadFile(hFile, v19, v20, (LPDWORD)&NumberOfBytesRead, 0) )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21);
            v10 = 195;
            goto LABEL_27;
          }
          v38 = 195;
          if ( (_DWORD)NumberOfBytesRead != v20 )
          {
            LastFailureAsHRESULT = -2147418113;
            v10 = 197;
LABEL_27:
            v7 = pv;
            goto LABEL_56;
          }
          v18 -= NumberOfBytesRead;
          LastFailureAsHRESULT = 0;
          v19 = (struct _GUID *)((char *)v19 + (unsigned int)NumberOfBytesRead);
          v16 = 197;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          v22 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v36, &stru_18003C2F0);
          v23 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v17);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)&WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids,
            *v23,
            v22);
          v5 = 3;
        }
        if ( (v5 & 2) != 0 )
        {
          v5 &= ~2u;
          SysFreeString(bstrString);
        }
        if ( (v5 & 1) != 0 )
          SysFreeString(v36);
        v24 = *(_QWORD *)&v17->Data1 - 0x47E0591A6AE1118FLL;
        if ( *(_QWORD *)&v17->Data1 == 0x47E0591A6AE1118FLL )
          v24 = *(_QWORD *)v17->Data4 + 0x7FD413D905C33C4ELL;
        v25 = v24 == 0;
        v10 = 210;
        if ( !v25 )
          goto LABEL_51;
        v26 = nNumberOfBytesToRead - 24;
        LastFailureAsHRESULT = 0;
        v38 = 210;
        v27 = RtlComputeCrc32(0x5EED5F85u, v17[1].Data4, nNumberOfBytesToRead - 24);
        v28 = v27;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids,
            v27,
            v17[1].Data1);
        v10 = 214;
        if ( v17[1].Data1 == v28 )
        {
          LastFailureAsHRESULT = 0;
          v38 = 214;
          v29 = MesDecodeBufferHandleCreate((char *)v17[1].Data4, v26, &pHandle);
          if ( v29 > 0 )
            v29 = (unsigned __int16)v29 | 0x80070000;
          LastFailureAsHRESULT = v29;
          v30 = v29 < 0;
          v10 = 219;
          if ( !v30 )
          {
            v38 = 219;
            v31 = InvokeCoder<_SPP_METADATA_PROP>(pHandle, &SPP_ONDISK_SNAPSHOT_PROP_Decode, a4);
            if ( v31 > 0 )
              v31 = (unsigned __int16)v31 | 0x80070000;
            v7 = pv;
            v30 = v31 < 0;
            LastFailureAsHRESULT = v31;
            v10 = 221;
            if ( !v30 )
            {
              v38 = 221;
              goto LABEL_57;
            }
            goto LABEL_56;
          }
        }
        else
        {
LABEL_51:
          LastFailureAsHRESULT = -2147024883;
        }
        v7 = pv;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v10 = 169;
  }
LABEL_56:
  v39 = v10;
LABEL_57:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  CoTaskMemFree(v7);
  v32 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v32;
}

```

## disassembly

```asm
0x1800220d8  mov     qword ptr [rsp-8+nNumberOfBytesToRead], r8
0x1800220dd  mov     [rsp-8+NumberOfBytesRead], rdx
0x1800220e2  push    rbp
0x1800220e3  push    rbx
0x1800220e4  push    rsi
0x1800220e5  push    rdi
0x1800220e6  push    r12
0x1800220e8  push    r13
0x1800220ea  push    r14
0x1800220ec  push    r15
0x1800220ee  lea     rbp, [rsp-1Fh]
0x1800220f3  sub     rsp, 88h
0x1800220fa  xor     r12d, r12d
0x1800220fd  mov     r15, r9
0x180022100  mov     ebx, r12d
0x180022103  mov     r14, rcx
0x180022106  mov     [rbp+57h+nNumberOfBytesToRead], ebx
0x180022109  mov     rcx, cs:WPP_GLOBAL_Control
0x180022110  lea     rsi, WPP_GLOBAL_Control
0x180022117  cmp     rcx, rsi
0x18002211a  jz      short loc_18002213A
0x18002211c  test    dword ptr [rcx+1Ch], 20000000h
0x180022123  jz      short loc_18002213A
0x180022125  mov     rcx, [rcx+10h]
0x180022129  lea     edx, [r12+0Eh]
0x18002212e  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180022135  call    WPP_SF_
0x18002213a  mov     r9d, 1; unsigned __int16
0x180022140  lea     rdx, aDeserializefro; "DeserializeFromFile"
0x180022147  mov     r8d, 8Eh; unsigned __int16
0x18002214d  lea     rcx, [rbp+57h+var_78]; this
0x180022151  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180022156  mov     [rbp+57h+pHandle], r12
0x18002215a  mov     rdi, r12
0x18002215d  mov     qword ptr [rbp+57h+FileSize], r12
0x180022161  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x180022165  mov     dword ptr [rbp+57h+NumberOfBytesRead], r12d
0x180022169  test    r15, r15
0x18002216c  jz      short loc_180022182
0x18002216e  mov     ecx, 98h
0x180022173  mov     rax, r15
0x180022176  mov     [rax], r12b
0x180022179  inc     rax
0x18002217c  sub     rcx, 1
0x180022180  jnz     short loc_180022176
0x180022182  mov     eax, 9Fh
0x180022187  test    r14, r14
0x18002218a  jz      loc_1800224B1
0x180022190  mov     [rbp+57h+var_74], ax
0x180022194  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180022198  jz      loc_1800224AC
0x18002219e  mov     eax, 0A2h
0x1800221a3  mov     [rbp+57h+var_74], ax
0x1800221a7  mov     eax, 0A3h
0x1800221ac  test    r15, r15
0x1800221af  jz      loc_1800224B1
0x1800221b5  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800221b9  mov     [rbp+57h+var_78], r12d
0x1800221bd  mov     rcx, r14; hFile
0x1800221c0  mov     [rbp+57h+var_74], ax
0x1800221c4  call    cs:__imp_GetFileSizeEx
0x1800221ca  test    eax, eax
0x1800221cc  jnz     short loc_1800221E0
0x1800221ce  call    GetLastFailureAsHRESULT
0x1800221d3  mov     [rbp+57h+var_78], eax
0x1800221d6  mov     eax, 0A9h
0x1800221db  jmp     loc_1800224B8
0x1800221e0  mov     eax, 0A9h
0x1800221e5  mov     [rbp+57h+var_78], r12d
0x1800221e9  mov     [rbp+57h+var_74], ax
0x1800221ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221f4  cmp     rcx, rsi
0x1800221f7  jz      short loc_180022219
0x1800221f9  test    dword ptr [rcx+1Ch], 8000000h
0x180022200  jz      short loc_180022219
0x180022202  mov     eax, dword ptr [rbp+57h+FileSize]
0x180022205  mov     r9d, dword ptr [rbp+57h+FileSize+4]
0x18002220c  mov     rcx, [rcx+10h]
0x180022210  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x180022214  call    WPP_SF_LD
0x180022219  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x18002221d  mov     eax, 0ACh
0x180022222  cmp     rcx, 10000000h
0x180022229  jge     loc_1800224A3
0x18002222f  mov     [rbp+57h+var_74], ax
0x180022233  mov     eax, 0ADh
0x180022238  cmp     rcx, 18h
0x18002223c  jbe     loc_1800224A3
0x180022242  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x180022246  mov     [rbp+57h+var_74], ax
0x18002224a  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18002224f  mov     [rbp+57h+var_78], eax
0x180022252  test    eax, eax
0x180022254  mov     eax, 0AEh
0x180022259  js      loc_1800224B8
0x18002225f  mov     r13d, [rbp+57h+nNumberOfBytesToRead]
0x180022263  mov     [rbp+57h+var_74], ax
0x180022267  lea     ecx, [r13+7]; cb
0x18002226b  call    cs:__imp_CoTaskMemAlloc
0x180022271  mov     [rbp+57h+pv], rax
0x180022275  mov     rdi, rax
0x180022278  mov     ecx, 0B6h
0x18002227d  test    rax, rax
0x180022280  jz      loc_180022496
0x180022286  add     rdi, 7
0x18002228a  mov     [rbp+57h+var_78], r12d
0x18002228e  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180022292  mov     esi, r13d
0x180022295  mov     r12, rdi
0x180022298  mov     [rbp+57h+var_74], cx
0x18002229c  test    esi, esi
0x18002229e  jz      short loc_180022310
0x1800222a0  mov     r13d, 100000h
0x1800222a6  mov     [rsp+0C0h+lpOverlapped], rbx; lpOverlapped
0x1800222ab  cmp     esi, r13d
0x1800222ae  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800222b2  mov     rdx, r12; lpBuffer
0x1800222b5  mov     rcx, r14; hFile
0x1800222b8  cmovb   r13d, esi
0x1800222bc  mov     r8d, r13d; nNumberOfBytesToRead
0x1800222bf  call    cs:__imp_ReadFile
0x1800222c5  test    eax, eax
0x1800222c7  jz      short loc_180022301
0x1800222c9  mov     eax, 0C3h
0x1800222ce  mov     [rbp+57h+var_74], ax
0x1800222d2  mov     eax, dword ptr [rbp+57h+NumberOfBytesRead]
0x1800222d5  cmp     eax, r13d
0x1800222d8  jnz     short loc_1800222E9
0x1800222da  sub     esi, eax
0x1800222dc  mov     [rbp+57h+var_78], ebx
0x1800222df  add     r12, rax
0x1800222e2  mov     ecx, 0C5h
0x1800222e7  jmp     short loc_180022298
0x1800222e9  mov     [rbp+57h+var_78], 8000FFFFh
0x1800222f0  mov     eax, 0C5h
0x1800222f5  mov     rdi, [rbp+57h+pv]
0x1800222f9  xor     r12d, r12d
0x1800222fc  jmp     loc_1800224B8
0x180022301  call    GetLastFailureAsHRESULT
0x180022306  mov     [rbp+57h+var_78], eax
0x180022309  mov     eax, 0C3h
0x18002230e  jmp     short loc_1800222F5
0x180022310  mov     rax, cs:WPP_GLOBAL_Control
0x180022317  lea     r13, WPP_GLOBAL_Control
0x18002231e  cmp     rax, r13
0x180022321  jz      short loc_180022374
0x180022323  test    dword ptr [rax+1Ch], 8000000h
0x18002232a  jz      short loc_180022374
0x18002232c  lea     rdx, stru_18003C2F0; struct _GUID *
0x180022333  lea     rcx, [rbp+57h+var_80]; this
0x180022337  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x18002233c  mov     rdx, rdi; struct _GUID *
0x18002233f  lea     rcx, [rbp+57h+bstrString]; this
0x180022343  mov     rbx, [rax]
0x180022346  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x18002234b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022352  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180022359  mov     edx, 10h
0x18002235e  mov     [rsp+0C0h+lpOverlapped], rbx
0x180022363  mov     r9, [rax]
0x180022366  mov     rcx, [rcx+10h]
0x18002236a  call    WPP_SF_SS
0x18002236f  mov     ebx, 3
0x180022374  test    bl, 2
0x180022377  jz      short loc_180022386
0x180022379  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18002237d  and     ebx, 0FFFFFFFDh
0x180022380  call    cs:__imp_SysFreeString
0x180022386  test    bl, 1
0x180022389  jz      short loc_180022395
0x18002238b  mov     rcx, [rbp+57h+var_80]; bstrString
0x18002238f  call    cs:__imp_SysFreeString
0x180022395  mov     rax, [rdi]
0x180022398  sub     rax, qword ptr cs:stru_18003C2F0.Data1
0x18002239f  jnz     short loc_1800223AC
0x1800223a1  mov     rax, [rdi+8]
0x1800223a5  sub     rax, qword ptr cs:stru_18003C2F0.Data4
0x1800223ac  xor     r12d, r12d
0x1800223af  test    rax, rax
0x1800223b2  mov     eax, 0D2h
0x1800223b7  jnz     loc_18002248D
0x1800223bd  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x1800223c0  lea     rdx, [rdi+18h]; Buffer
0x1800223c4  add     esi, 0FFFFFFE8h
0x1800223c7  mov     [rbp+57h+var_78], r12d
0x1800223cb  mov     r8d, esi; Length
0x1800223ce  mov     [rbp+57h+var_74], ax
0x1800223d2  mov     ecx, 5EED5F85h; InitialCrc
0x1800223d7  call    cs:__imp_RtlComputeCrc32
0x1800223dd  mov     ebx, eax
0x1800223df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223e6  cmp     rcx, r13
0x1800223e9  jz      short loc_180022415
0x1800223eb  test    dword ptr [rcx+1Ch], 8000000h
0x1800223f2  jz      short loc_180022415
0x1800223f4  mov     r9d, [rdi+10h]
0x1800223f8  lea     edx, [r12+11h]
0x1800223fd  mov     rcx, [rcx+10h]
0x180022401  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180022408  mov     dword ptr [rsp+0C0h+lpOverlapped], r9d
0x18002240d  mov     r9d, eax
0x180022410  call    WPP_SF_dd
0x180022415  mov     eax, 0D6h
0x18002241a  cmp     [rdi+10h], ebx
0x18002241d  jnz     short loc_18002248D
0x18002241f  lea     r8, [rbp+57h+pHandle]; pHandle
0x180022423  mov     [rbp+57h+var_78], r12d
0x180022427  mov     edx, esi; BufferSize
0x180022429  mov     [rbp+57h+var_74], ax
0x18002242d  lea     rcx, [rdi+18h]; Buffer
0x180022431  call    cs:__imp_MesDecodeBufferHandleCreate
0x180022437  mov     ebx, 80070000h
0x18002243c  test    eax, eax
0x18002243e  jle     short loc_180022445
0x180022440  movzx   eax, ax
0x180022443  or      eax, ebx
0x180022445  mov     [rbp+57h+var_78], eax
0x180022448  test    eax, eax
0x18002244a  mov     eax, 0DBh
0x18002244f  jns     short loc_180022457
0x180022451  mov     rdi, [rbp+57h+pv]
0x180022455  jmp     short loc_1800224B8
0x180022457  mov     rcx, [rbp+57h+pHandle]
0x18002245b  lea     rdx, SPP_ONDISK_SNAPSHOT_PROP_Decode
0x180022462  mov     r8, r15
0x180022465  mov     [rbp+57h+var_74], ax
0x180022469  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x18002246e  test    eax, eax
0x180022470  jle     short loc_180022477
0x180022472  movzx   eax, ax
0x180022475  or      eax, ebx
0x180022477  mov     rdi, [rbp+57h+pv]
0x18002247b  test    eax, eax
0x18002247d  mov     [rbp+57h+var_78], eax
0x180022480  mov     eax, 0DDh
0x180022485  js      short loc_1800224B8
0x180022487  mov     [rbp+57h+var_74], ax
0x18002248b  jmp     short loc_1800224BC
0x18002248d  mov     [rbp+57h+var_78], 8007000Dh
0x180022494  jmp     short loc_180022451
0x180022496  mov     [rbp+57h+var_78], 8007000Eh
0x18002249d  mov     [rbp+57h+var_72], cx
0x1800224a1  jmp     short loc_1800224BC
0x1800224a3  mov     [rbp+57h+var_78], 8007000Dh
0x1800224aa  jmp     short loc_1800224B8
0x1800224ac  mov     eax, 0A0h
0x1800224b1  mov     [rbp+57h+var_78], 80070057h
0x1800224b8  mov     [rbp+57h+var_72], ax
0x1800224bc  mov     rcx, [rbp+57h+pHandle]; Handle
0x1800224c0  test    rcx, rcx
0x1800224c3  jz      short loc_1800224CF
0x1800224c5  call    cs:__imp_MesHandleFree
0x1800224cb  mov     [rbp+57h+pHandle], r12
0x1800224cf  mov     rcx, rdi; pv
0x1800224d2  call    cs:__imp_CoTaskMemFree
0x1800224d8  mov     ebx, [rbp+57h+var_78]
0x1800224db  lea     rcx, [rbp+57h+var_78]; this
0x1800224df  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800224e4  mov     eax, ebx
0x1800224e6  add     rsp, 88h
0x1800224ed  pop     r15
0x1800224ef  pop     r14
0x1800224f1  pop     r13
0x1800224f3  pop     r12
0x1800224f5  pop     rdi
0x1800224f6  pop     rsi
0x1800224f7  pop     rbx
0x1800224f8  pop     rbp
0x1800224f9  retn
```
