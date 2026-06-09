# DeserializeFromFile<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_GUID const *,_SPP_METADATA_PROP *)

- ea: `0x180021cb0`
- end: `0x1800220d2`
- name: `??$DeserializeFromFile@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@ZPEBU_GUID@@1@Z`
- size: `1058`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a6a0`

## callees

- `0x18000220c`
- `0x180020710`
- `0x180020af4`
- `0x1800215c8`
- `0x180021cb0`
- `0x180022500`
- `0x180022d4c`
- `0x180022ee8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180021e97`
- `KERNEL32!ReadFile` at `0x180021e97`
- `KERNEL32!GetFileSizeEx` at `0x180021d9c`
- `KERNEL32!GetFileSizeEx` at `0x180021d9c`
- `ntdll!RtlComputeCrc32` at `0x180021faf`
- `ntdll!RtlComputeCrc32` at `0x180021faf`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180022009`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180022009`
- `RPCRT4!MesHandleFree` at `0x18002209d`
- `RPCRT4!MesHandleFree` at `0x18002209d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e43`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f58`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f67`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f58`
- `OLEAUT32!__imp_SysFreeString` at `0x180021f67`

## string_xrefs

- `0x180021d18`: `DeserializeFromFile`

## pseudocode

```c
__int64 __fastcall DeserializeFromFile<_SPP_METADATA_PROP>(HANDLE hFile, __int64 a2, __int64 a3, _BYTE *a4)
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
    v8 = 40;
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
          v22 = *(_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v36, &stru_18003C2E0);
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
        v24 = *(_QWORD *)&v17->Data1 - 0x4B6C046FE5247137LL;
        if ( *(_QWORD *)&v17->Data1 == 0x4B6C046FE5247137LL )
          v24 = *(_QWORD *)v17->Data4 - 0x36F3F60307225691LL;
        v25 = v24 == 0;
        v10 = 210;
        if ( !v25 )
          goto LABEL_51;
        v26 = nNumberOfBytesToRead - 24;
        LastFailureAsHRESULT = 0;
        v38 = 210;
        v27 = RtlComputeCrc32(0x5EED5F15u, v17[1].Data4, nNumberOfBytesToRead - 24);
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
            v31 = InvokeCoder<_SPP_METADATA_PROP>(pHandle, &SPP_METADATA_PROP_Decode, a4);
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
0x180021cb0  mov     qword ptr [rsp-8+nNumberOfBytesToRead], r8
0x180021cb5  mov     [rsp-8+NumberOfBytesRead], rdx
0x180021cba  push    rbp
0x180021cbb  push    rbx
0x180021cbc  push    rsi
0x180021cbd  push    rdi
0x180021cbe  push    r12
0x180021cc0  push    r13
0x180021cc2  push    r14
0x180021cc4  push    r15
0x180021cc6  lea     rbp, [rsp-1Fh]
0x180021ccb  sub     rsp, 88h
0x180021cd2  xor     r12d, r12d
0x180021cd5  mov     r15, r9
0x180021cd8  mov     ebx, r12d
0x180021cdb  mov     r14, rcx
0x180021cde  mov     [rbp+57h+nNumberOfBytesToRead], ebx
0x180021ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ce8  lea     rsi, WPP_GLOBAL_Control
0x180021cef  cmp     rcx, rsi
0x180021cf2  jz      short loc_180021D12
0x180021cf4  test    dword ptr [rcx+1Ch], 20000000h
0x180021cfb  jz      short loc_180021D12
0x180021cfd  mov     rcx, [rcx+10h]
0x180021d01  lea     edx, [r12+0Eh]
0x180021d06  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180021d0d  call    WPP_SF_
0x180021d12  mov     r9d, 1; unsigned __int16
0x180021d18  lea     rdx, aDeserializefro; "DeserializeFromFile"
0x180021d1f  mov     r8d, 8Eh; unsigned __int16
0x180021d25  lea     rcx, [rbp+57h+var_78]; this
0x180021d29  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021d2e  mov     [rbp+57h+pHandle], r12
0x180021d32  mov     rdi, r12
0x180021d35  mov     qword ptr [rbp+57h+FileSize], r12
0x180021d39  mov     [rbp+57h+nNumberOfBytesToRead], r12d
0x180021d3d  mov     dword ptr [rbp+57h+NumberOfBytesRead], r12d
0x180021d41  test    r15, r15
0x180021d44  jz      short loc_180021D5A
0x180021d46  mov     ecx, 28h ; '('
0x180021d4b  mov     rax, r15
0x180021d4e  mov     [rax], r12b
0x180021d51  inc     rax
0x180021d54  sub     rcx, 1
0x180021d58  jnz     short loc_180021D4E
0x180021d5a  mov     eax, 9Fh
0x180021d5f  test    r14, r14
0x180021d62  jz      loc_180022089
0x180021d68  mov     [rbp+57h+var_74], ax
0x180021d6c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180021d70  jz      loc_180022084
0x180021d76  mov     eax, 0A2h
0x180021d7b  mov     [rbp+57h+var_74], ax
0x180021d7f  mov     eax, 0A3h
0x180021d84  test    r15, r15
0x180021d87  jz      loc_180022089
0x180021d8d  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x180021d91  mov     [rbp+57h+var_78], r12d
0x180021d95  mov     rcx, r14; hFile
0x180021d98  mov     [rbp+57h+var_74], ax
0x180021d9c  call    cs:__imp_GetFileSizeEx
0x180021da2  test    eax, eax
0x180021da4  jnz     short loc_180021DB8
0x180021da6  call    GetLastFailureAsHRESULT
0x180021dab  mov     [rbp+57h+var_78], eax
0x180021dae  mov     eax, 0A9h
0x180021db3  jmp     loc_180022090
0x180021db8  mov     eax, 0A9h
0x180021dbd  mov     [rbp+57h+var_78], r12d
0x180021dc1  mov     [rbp+57h+var_74], ax
0x180021dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021dcc  cmp     rcx, rsi
0x180021dcf  jz      short loc_180021DF1
0x180021dd1  test    dword ptr [rcx+1Ch], 8000000h
0x180021dd8  jz      short loc_180021DF1
0x180021dda  mov     eax, dword ptr [rbp+57h+FileSize]
0x180021ddd  mov     r9d, dword ptr [rbp+57h+FileSize+4]
0x180021de4  mov     rcx, [rcx+10h]
0x180021de8  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x180021dec  call    WPP_SF_LD
0x180021df1  mov     rcx, qword ptr [rbp+57h+FileSize]; __int64
0x180021df5  mov     eax, 0ACh
0x180021dfa  cmp     rcx, 10000000h
0x180021e01  jge     loc_18002207B
0x180021e07  mov     [rbp+57h+var_74], ax
0x180021e0b  mov     eax, 0ADh
0x180021e10  cmp     rcx, 18h
0x180021e14  jbe     loc_18002207B
0x180021e1a  lea     rdx, [rbp+57h+nNumberOfBytesToRead]; unsigned int *
0x180021e1e  mov     [rbp+57h+var_74], ax
0x180021e22  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180021e27  mov     [rbp+57h+var_78], eax
0x180021e2a  test    eax, eax
0x180021e2c  mov     eax, 0AEh
0x180021e31  js      loc_180022090
0x180021e37  mov     r13d, [rbp+57h+nNumberOfBytesToRead]
0x180021e3b  mov     [rbp+57h+var_74], ax
0x180021e3f  lea     ecx, [r13+7]; cb
0x180021e43  call    cs:__imp_CoTaskMemAlloc
0x180021e49  mov     [rbp+57h+pv], rax
0x180021e4d  mov     rdi, rax
0x180021e50  mov     ecx, 0B6h
0x180021e55  test    rax, rax
0x180021e58  jz      loc_18002206E
0x180021e5e  add     rdi, 7
0x180021e62  mov     [rbp+57h+var_78], r12d
0x180021e66  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180021e6a  mov     esi, r13d
0x180021e6d  mov     r12, rdi
0x180021e70  mov     [rbp+57h+var_74], cx
0x180021e74  test    esi, esi
0x180021e76  jz      short loc_180021EE8
0x180021e78  mov     r13d, 100000h
0x180021e7e  mov     [rsp+0C0h+lpOverlapped], rbx; lpOverlapped
0x180021e83  cmp     esi, r13d
0x180021e86  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180021e8a  mov     rdx, r12; lpBuffer
0x180021e8d  mov     rcx, r14; hFile
0x180021e90  cmovb   r13d, esi
0x180021e94  mov     r8d, r13d; nNumberOfBytesToRead
0x180021e97  call    cs:__imp_ReadFile
0x180021e9d  test    eax, eax
0x180021e9f  jz      short loc_180021ED9
0x180021ea1  mov     eax, 0C3h
0x180021ea6  mov     [rbp+57h+var_74], ax
0x180021eaa  mov     eax, dword ptr [rbp+57h+NumberOfBytesRead]
0x180021ead  cmp     eax, r13d
0x180021eb0  jnz     short loc_180021EC1
0x180021eb2  sub     esi, eax
0x180021eb4  mov     [rbp+57h+var_78], ebx
0x180021eb7  add     r12, rax
0x180021eba  mov     ecx, 0C5h
0x180021ebf  jmp     short loc_180021E70
0x180021ec1  mov     [rbp+57h+var_78], 8000FFFFh
0x180021ec8  mov     eax, 0C5h
0x180021ecd  mov     rdi, [rbp+57h+pv]
0x180021ed1  xor     r12d, r12d
0x180021ed4  jmp     loc_180022090
0x180021ed9  call    GetLastFailureAsHRESULT
0x180021ede  mov     [rbp+57h+var_78], eax
0x180021ee1  mov     eax, 0C3h
0x180021ee6  jmp     short loc_180021ECD
0x180021ee8  mov     rax, cs:WPP_GLOBAL_Control
0x180021eef  lea     r13, WPP_GLOBAL_Control
0x180021ef6  cmp     rax, r13
0x180021ef9  jz      short loc_180021F4C
0x180021efb  test    dword ptr [rax+1Ch], 8000000h
0x180021f02  jz      short loc_180021F4C
0x180021f04  lea     rdx, stru_18003C2E0; struct _GUID *
0x180021f0b  lea     rcx, [rbp+57h+var_80]; this
0x180021f0f  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180021f14  mov     rdx, rdi; struct _GUID *
0x180021f17  lea     rcx, [rbp+57h+bstrString]; this
0x180021f1b  mov     rbx, [rax]
0x180021f1e  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180021f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f2a  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180021f31  mov     edx, 10h
0x180021f36  mov     [rsp+0C0h+lpOverlapped], rbx
0x180021f3b  mov     r9, [rax]
0x180021f3e  mov     rcx, [rcx+10h]
0x180021f42  call    WPP_SF_SS
0x180021f47  mov     ebx, 3
0x180021f4c  test    bl, 2
0x180021f4f  jz      short loc_180021F5E
0x180021f51  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180021f55  and     ebx, 0FFFFFFFDh
0x180021f58  call    cs:__imp_SysFreeString
0x180021f5e  test    bl, 1
0x180021f61  jz      short loc_180021F6D
0x180021f63  mov     rcx, [rbp+57h+var_80]; bstrString
0x180021f67  call    cs:__imp_SysFreeString
0x180021f6d  mov     rax, [rdi]
0x180021f70  sub     rax, qword ptr cs:stru_18003C2E0.Data1
0x180021f77  jnz     short loc_180021F84
0x180021f79  mov     rax, [rdi+8]
0x180021f7d  sub     rax, qword ptr cs:stru_18003C2E0.Data4
0x180021f84  xor     r12d, r12d
0x180021f87  test    rax, rax
0x180021f8a  mov     eax, 0D2h
0x180021f8f  jnz     loc_180022065
0x180021f95  mov     esi, [rbp+57h+nNumberOfBytesToRead]
0x180021f98  lea     rdx, [rdi+18h]; Buffer
0x180021f9c  add     esi, 0FFFFFFE8h
0x180021f9f  mov     [rbp+57h+var_78], r12d
0x180021fa3  mov     r8d, esi; Length
0x180021fa6  mov     [rbp+57h+var_74], ax
0x180021faa  mov     ecx, 5EED5F15h; InitialCrc
0x180021faf  call    cs:__imp_RtlComputeCrc32
0x180021fb5  mov     ebx, eax
0x180021fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fbe  cmp     rcx, r13
0x180021fc1  jz      short loc_180021FED
0x180021fc3  test    dword ptr [rcx+1Ch], 8000000h
0x180021fca  jz      short loc_180021FED
0x180021fcc  mov     r9d, [rdi+10h]
0x180021fd0  lea     edx, [r12+11h]
0x180021fd5  mov     rcx, [rcx+10h]
0x180021fd9  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180021fe0  mov     dword ptr [rsp+0C0h+lpOverlapped], r9d
0x180021fe5  mov     r9d, eax
0x180021fe8  call    WPP_SF_dd
0x180021fed  mov     eax, 0D6h
0x180021ff2  cmp     [rdi+10h], ebx
0x180021ff5  jnz     short loc_180022065
0x180021ff7  lea     r8, [rbp+57h+pHandle]; pHandle
0x180021ffb  mov     [rbp+57h+var_78], r12d
0x180021fff  mov     edx, esi; BufferSize
0x180022001  mov     [rbp+57h+var_74], ax
0x180022005  lea     rcx, [rdi+18h]; Buffer
0x180022009  call    cs:__imp_MesDecodeBufferHandleCreate
0x18002200f  mov     ebx, 80070000h
0x180022014  test    eax, eax
0x180022016  jle     short loc_18002201D
0x180022018  movzx   eax, ax
0x18002201b  or      eax, ebx
0x18002201d  mov     [rbp+57h+var_78], eax
0x180022020  test    eax, eax
0x180022022  mov     eax, 0DBh
0x180022027  jns     short loc_18002202F
0x180022029  mov     rdi, [rbp+57h+pv]
0x18002202d  jmp     short loc_180022090
0x18002202f  mov     rcx, [rbp+57h+pHandle]
0x180022033  lea     rdx, SPP_METADATA_PROP_Decode
0x18002203a  mov     r8, r15
0x18002203d  mov     [rbp+57h+var_74], ax
0x180022041  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x180022046  test    eax, eax
0x180022048  jle     short loc_18002204F
0x18002204a  movzx   eax, ax
0x18002204d  or      eax, ebx
0x18002204f  mov     rdi, [rbp+57h+pv]
0x180022053  test    eax, eax
0x180022055  mov     [rbp+57h+var_78], eax
0x180022058  mov     eax, 0DDh
0x18002205d  js      short loc_180022090
0x18002205f  mov     [rbp+57h+var_74], ax
0x180022063  jmp     short loc_180022094
0x180022065  mov     [rbp+57h+var_78], 8007000Dh
0x18002206c  jmp     short loc_180022029
0x18002206e  mov     [rbp+57h+var_78], 8007000Eh
0x180022075  mov     [rbp+57h+var_72], cx
0x180022079  jmp     short loc_180022094
0x18002207b  mov     [rbp+57h+var_78], 8007000Dh
0x180022082  jmp     short loc_180022090
0x180022084  mov     eax, 0A0h
0x180022089  mov     [rbp+57h+var_78], 80070057h
0x180022090  mov     [rbp+57h+var_72], ax
0x180022094  mov     rcx, [rbp+57h+pHandle]; Handle
0x180022098  test    rcx, rcx
0x18002209b  jz      short loc_1800220A7
0x18002209d  call    cs:__imp_MesHandleFree
0x1800220a3  mov     [rbp+57h+pHandle], r12
0x1800220a7  mov     rcx, rdi; pv
0x1800220aa  call    cs:__imp_CoTaskMemFree
0x1800220b0  mov     ebx, [rbp+57h+var_78]
0x1800220b3  lea     rcx, [rbp+57h+var_78]; this
0x1800220b7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800220bc  mov     eax, ebx
0x1800220be  add     rsp, 88h
0x1800220c5  pop     r15
0x1800220c7  pop     r14
0x1800220c9  pop     r13
0x1800220cb  pop     r12
0x1800220cd  pop     rdi
0x1800220ce  pop     rsi
0x1800220cf  pop     rbx
0x1800220d0  pop     rbp
0x1800220d1  retn
```
