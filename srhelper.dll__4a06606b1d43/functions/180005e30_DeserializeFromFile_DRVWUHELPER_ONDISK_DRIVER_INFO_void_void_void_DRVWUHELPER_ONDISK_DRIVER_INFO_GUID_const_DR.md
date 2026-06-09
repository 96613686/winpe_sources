# DeserializeFromFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)

- ea: `0x180005e30`
- end: `0x1800062e1`
- name: `??$DeserializeFromFile@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@ZPEBU_GUID@@1@Z`
- size: `1201`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003360`

## callees

- `0x180003ce0`
- `0x180005e30`
- `0x1800067a0`
- `0x180006f58`
- `0x180006fac`
- `0x1800070d4`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x180005f23`
- `KERNEL32!GetFileSizeEx` at `0x180005f23`
- `KERNEL32!ReadFile` at `0x180006023`
- `KERNEL32!ReadFile` at `0x180006023`
- `ntdll!RtlComputeCrc32` at `0x180006170`
- `ntdll!RtlComputeCrc32` at `0x180006170`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800061d5`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x1800061d5`
- `RPCRT4!MesHandleFree` at `0x180006296`
- `RPCRT4!MesHandleFree` at `0x180006296`
- `ole32!StringFromGUID2` at `0x1800060b2`
- `ole32!StringFromGUID2` at `0x1800060cf`
- `ole32!StringFromGUID2` at `0x1800060b2`
- `ole32!StringFromGUID2` at `0x1800060cf`
- `ole32!CoTaskMemAlloc` at `0x180005fc7`
- `ole32!CoTaskMemAlloc` at `0x180005fc7`
- `ole32!CoTaskMemFree` at `0x1800062a4`
- `ole32!CoTaskMemFree` at `0x1800062a4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800060bc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800060d9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800060bc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800060d9`
- `OLEAUT32!__imp_SysFreeString` at `0x180006119`
- `OLEAUT32!__imp_SysFreeString` at `0x180006128`
- `OLEAUT32!__imp_SysFreeString` at `0x180006119`
- `OLEAUT32!__imp_SysFreeString` at `0x180006128`

## string_xrefs

- `0x180005ea2`: `DeserializeFromFile`

## pseudocode

```c
__int64 __fastcall DeserializeFromFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(
        HANDLE hFile,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  char v5; // r15
  void *v7; // rsi
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // r8
  DWORD LowPart; // ebx
  LPVOID v14; // rax
  const GUID *v15; // r14
  GUID *v16; // r12
  unsigned int v17; // esi
  DWORD v18; // eax
  OLECHAR *v19; // rsi
  OLECHAR *v20; // rdi
  int v21; // edx
  int v22; // r8d
  unsigned int v23; // edi
  ULONG v24; // ebx
  int v25; // eax
  bool v26; // sf
  signed int v27; // eax
  unsigned int v28; // ebx
  LPVOID pv; // [rsp+30h] [rbp-D0h]
  int LastFailureAsHRESULT; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v32; // [rsp+3Ch] [rbp-C4h]
  __int16 v33; // [rsp+3Eh] [rbp-C2h]
  handle_t pHandle; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp-88h] BYREF
  DWORD v36; // [rsp+7Ch] [rbp-84h]
  union _LARGE_INTEGER FileSize; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[64]; // [rsp+90h] [rbp-70h] BYREF

  v5 = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "DeserializeFromFile",
    0x8Eu,
    (unsigned __int16)a4);
  pHandle = 0;
  v7 = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  if ( a4 )
  {
    v8 = 16;
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
    goto LABEL_57;
  v32 = 159;
  if ( hFile == (HANDLE)-1LL )
  {
    v10 = 160;
    goto LABEL_57;
  }
  v32 = 162;
  v10 = 163;
  if ( !a4 )
  {
LABEL_57:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_58;
  }
  LastFailureAsHRESULT = 0;
  v32 = 163;
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = 169;
    goto LABEL_58;
  }
  LastFailureAsHRESULT = 0;
  v32 = 169;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_LD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, (unsigned int)FileSize.HighPart, FileSize.LowPart);
  LowPart = FileSize.LowPart;
  v10 = 172;
  if ( FileSize.QuadPart >= 0x10000000 || (v32 = 172, v10 = 173, FileSize.QuadPart <= 0x18uLL) )
  {
    LastFailureAsHRESULT = -2147024883;
    goto LABEL_58;
  }
  v32 = 173;
  v10 = 174;
  if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
  {
    LastFailureAsHRESULT = -2147024362;
    goto LABEL_58;
  }
  LastFailureAsHRESULT = 0;
  v32 = 174;
  v14 = CoTaskMemAlloc(FileSize.LowPart + 7);
  pv = v14;
  v7 = v14;
  if ( !v14 )
  {
    LastFailureAsHRESULT = -2147024882;
    v33 = 182;
    goto LABEL_59;
  }
  LastFailureAsHRESULT = 0;
  v15 = (const GUID *)(((unsigned __int64)v14 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  v32 = 182;
  v16 = (GUID *)v15;
  v17 = LowPart;
  if ( LowPart )
  {
    while ( 1 )
    {
      v18 = 0x100000;
      if ( v17 < 0x100000 )
        v18 = v17;
      v36 = v18;
      if ( !ReadFile(hFile, v16, v18, &NumberOfBytesRead, 0) )
        break;
      v32 = 195;
      if ( NumberOfBytesRead != v36 )
      {
        LastFailureAsHRESULT = -2147418113;
        v10 = 197;
        goto LABEL_27;
      }
      LastFailureAsHRESULT = 0;
      v32 = 197;
      v17 -= NumberOfBytesRead;
      if ( !v17 )
        goto LABEL_29;
      v16 = (GUID *)((char *)v16 + NumberOfBytesRead);
    }
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = 195;
    goto LABEL_27;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
  {
    v19 = (OLECHAR *)pHandle;
    v20 = (OLECHAR *)pHandle;
  }
  else
  {
    StringFromGUID2(&rguid, sz, 64);
    v19 = SysAllocString(sz);
    StringFromGUID2(v15, sz, 64);
    v20 = SysAllocString(sz);
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, (_DWORD)v20, (__int64)v19);
    v5 = 3;
  }
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    SysFreeString(v20);
  }
  if ( (v5 & 1) != 0 )
    SysFreeString(v19);
  if ( *(_QWORD *)&v15->Data1 != 0x47618E7F5E55205CLL || *(_QWORD *)v15->Data4 != 0x1BC42D10E644DE8BLL )
  {
    LastFailureAsHRESULT = -2147024883;
    v10 = 210;
LABEL_27:
    v7 = pv;
    goto LABEL_58;
  }
  v23 = LowPart - 24;
  LastFailureAsHRESULT = 0;
  v32 = 210;
  v24 = RtlComputeCrc32(0x5EED5EFDu, v15[1].Data4, LowPart - 24);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids,
      v24,
      v15[1].Data1);
  v10 = 214;
  if ( v15[1].Data1 == v24 )
  {
    LastFailureAsHRESULT = 0;
    v32 = 214;
    v25 = MesDecodeBufferHandleCreate((char *)v15[1].Data4, v23, &pHandle);
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    LastFailureAsHRESULT = v25;
    v26 = v25 < 0;
    v10 = 219;
    if ( !v26 )
    {
      v32 = 219;
      v27 = InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(pHandle, &DRVWUHELPER_ONDISK_DRIVER_INFO_Decode, a4);
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      v7 = pv;
      v26 = v27 < 0;
      LastFailureAsHRESULT = v27;
      v10 = 221;
      if ( !v26 )
      {
        v32 = 221;
        goto LABEL_59;
      }
      goto LABEL_58;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024883;
  }
  v7 = pv;
LABEL_58:
  v33 = v10;
LABEL_59:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  CoTaskMemFree(v7);
  v28 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v28;
}

```

## disassembly

```asm
0x180005e30  mov     [rsp-8+arg_8], rbx
0x180005e35  push    rbp
0x180005e36  push    rsi
0x180005e37  push    rdi
0x180005e38  push    r12
0x180005e3a  push    r13
0x180005e3c  push    r14
0x180005e3e  push    r15
0x180005e40  lea     rbp, [rsp-20h]
0x180005e45  sub     rsp, 120h
0x180005e4c  mov     rax, cs:__security_cookie
0x180005e53  xor     rax, rsp
0x180005e56  mov     [rbp+50h+var_40], rax
0x180005e5a  xor     r12d, r12d
0x180005e5d  mov     r13, r9
0x180005e60  mov     r15d, r12d
0x180005e63  mov     [rsp+150h+var_D4], r12d
0x180005e68  mov     rdi, rcx
0x180005e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e72  lea     rbx, WPP_GLOBAL_Control
0x180005e79  cmp     rcx, rbx
0x180005e7c  jz      short loc_180005E9C
0x180005e7e  test    dword ptr [rcx+1Ch], 20000000h
0x180005e85  jz      short loc_180005E9C
0x180005e87  mov     rcx, [rcx+10h]
0x180005e8b  lea     edx, [r12+0Eh]
0x180005e90  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x180005e97  call    WPP_SF_
0x180005e9c  mov     r8d, 8Eh; unsigned __int16
0x180005ea2  lea     rdx, aDeserializefro; "DeserializeFromFile"
0x180005ea9  lea     rcx, [rsp+150h+var_118]; this
0x180005eae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005eb3  mov     [rsp+150h+pHandle], r12
0x180005eb8  mov     rsi, r12
0x180005ebb  mov     qword ptr [rbp+50h+FileSize], r12
0x180005ebf  mov     [rsp+150h+NumberOfBytesRead], r12d
0x180005ec4  test    r13, r13
0x180005ec7  jz      short loc_180005EDD
0x180005ec9  mov     ecx, 10h
0x180005ece  mov     rax, r13
0x180005ed1  mov     [rax], r12b
0x180005ed4  inc     rax
0x180005ed7  sub     rcx, 1
0x180005edb  jnz     short loc_180005ED1
0x180005edd  mov     eax, 9Fh
0x180005ee2  test    rdi, rdi
0x180005ee5  jz      loc_18000627F
0x180005eeb  mov     [rsp+150h+var_114], ax
0x180005ef0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180005ef4  jz      loc_18000627A
0x180005efa  mov     eax, 0A2h
0x180005eff  mov     [rsp+150h+var_114], ax
0x180005f04  mov     eax, 0A3h
0x180005f09  test    r13, r13
0x180005f0c  jz      loc_18000627F
0x180005f12  lea     rdx, [rbp+50h+FileSize]; lpFileSize
0x180005f16  mov     [rsp+150h+var_118], r12d
0x180005f1b  mov     rcx, rdi; hFile
0x180005f1e  mov     [rsp+150h+var_114], ax
0x180005f23  call    cs:__imp_GetFileSizeEx
0x180005f29  test    eax, eax
0x180005f2b  jnz     short loc_180005F40
0x180005f2d  call    GetLastFailureAsHRESULT
0x180005f32  mov     [rsp+150h+var_118], eax
0x180005f36  mov     eax, 0A9h
0x180005f3b  jmp     loc_180006287
0x180005f40  mov     eax, 0A9h
0x180005f45  mov     [rsp+150h+var_118], r12d
0x180005f4a  mov     [rsp+150h+var_114], ax
0x180005f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f56  cmp     rcx, rbx
0x180005f59  jz      short loc_180005F78
0x180005f5b  test    dword ptr [rcx+1Ch], 8000000h
0x180005f62  jz      short loc_180005F78
0x180005f64  mov     eax, dword ptr [rbp+50h+FileSize]
0x180005f67  mov     r9d, dword ptr [rbp+50h+FileSize+4]
0x180005f6b  mov     rcx, [rcx+10h]
0x180005f6f  mov     dword ptr [rsp+150h+lpOverlapped], eax
0x180005f73  call    WPP_SF_LD
0x180005f78  mov     rbx, qword ptr [rbp+50h+FileSize]
0x180005f7c  mov     eax, 0ACh
0x180005f81  cmp     rbx, 10000000h
0x180005f88  jge     loc_180006270
0x180005f8e  mov     [rsp+150h+var_114], ax
0x180005f93  mov     eax, 0ADh
0x180005f98  cmp     rbx, 18h
0x180005f9c  jbe     loc_180006270
0x180005fa2  mov     [rsp+150h+var_114], ax
0x180005fa7  mov     eax, 0FFFFFFFFh
0x180005fac  cmp     rbx, rax
0x180005faf  mov     eax, 0AEh
0x180005fb4  ja      loc_180006266
0x180005fba  lea     ecx, [rbx+7]; cb
0x180005fbd  mov     [rsp+150h+var_118], r12d
0x180005fc2  mov     [rsp+150h+var_114], ax
0x180005fc7  call    cs:__imp_CoTaskMemAlloc
0x180005fcd  mov     [rsp+150h+pv], rax
0x180005fd2  mov     rsi, rax
0x180005fd5  mov     ecx, 0B6h
0x180005fda  test    rax, rax
0x180005fdd  jz      loc_180006257
0x180005fe3  lea     r14, [rax+7]
0x180005fe7  mov     [rsp+150h+var_118], r12d
0x180005fec  and     r14, 0FFFFFFFFFFFFFFF8h
0x180005ff0  mov     [rsp+150h+var_114], cx
0x180005ff5  mov     r12, r14
0x180005ff8  mov     esi, ebx
0x180005ffa  test    ebx, ebx
0x180005ffc  jz      loc_180006083
0x180006002  mov     eax, 100000h
0x180006007  mov     [rsp+150h+lpOverlapped], r15; lpOverlapped
0x18000600c  cmp     esi, eax
0x18000600e  lea     r9, [rsp+150h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006013  mov     rdx, r12; lpBuffer
0x180006016  mov     rcx, rdi; hFile
0x180006019  cmovb   eax, esi
0x18000601c  mov     r8d, eax; nNumberOfBytesToRead
0x18000601f  mov     [rsp+150h+var_D4], eax
0x180006023  call    cs:__imp_ReadFile
0x180006029  test    eax, eax
0x18000602b  jz      short loc_180006073
0x18000602d  mov     eax, 0C3h
0x180006032  mov     [rsp+150h+var_114], ax
0x180006037  mov     eax, [rsp+150h+NumberOfBytesRead]
0x18000603b  cmp     eax, [rsp+150h+var_D4]
0x18000603f  jnz     short loc_180006059
0x180006041  mov     [rsp+150h+var_118], r15d
0x180006046  mov     ecx, 0C5h
0x18000604b  mov     [rsp+150h+var_114], cx
0x180006050  sub     esi, eax
0x180006052  jz      short loc_180006083
0x180006054  add     r12, rax
0x180006057  jmp     short loc_180006002
0x180006059  mov     [rsp+150h+var_118], 8000FFFFh
0x180006061  mov     eax, 0C5h
0x180006066  mov     rsi, [rsp+150h+pv]
0x18000606b  xor     r12d, r12d
0x18000606e  jmp     loc_180006287
0x180006073  call    GetLastFailureAsHRESULT
0x180006078  mov     [rsp+150h+var_118], eax
0x18000607c  mov     eax, 0C3h
0x180006081  jmp     short loc_180006066
0x180006083  mov     rax, cs:WPP_GLOBAL_Control
0x18000608a  lea     rcx, WPP_GLOBAL_Control
0x180006091  cmp     rax, rcx
0x180006094  jz      short loc_180006102
0x180006096  test    dword ptr [rax+1Ch], 8000000h
0x18000609d  jz      short loc_180006102
0x18000609f  mov     edi, 40h ; '@'
0x1800060a4  lea     rdx, [rbp+50h+sz]; lpsz
0x1800060a8  mov     r8d, edi; cchMax
0x1800060ab  lea     rcx, rguid; rguid
0x1800060b2  call    cs:__imp_StringFromGUID2
0x1800060b8  lea     rcx, [rbp+50h+sz]; psz
0x1800060bc  call    cs:__imp_SysAllocString
0x1800060c2  mov     r8d, edi; cchMax
0x1800060c5  lea     rdx, [rbp+50h+sz]; lpsz
0x1800060c9  mov     rcx, r14; rguid
0x1800060cc  mov     rsi, rax
0x1800060cf  call    cs:__imp_StringFromGUID2
0x1800060d5  lea     rcx, [rbp+50h+sz]; psz
0x1800060d9  call    cs:__imp_SysAllocString
0x1800060df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060e6  mov     r9, rax
0x1800060e9  mov     rdi, rax
0x1800060ec  mov     [rsp+150h+lpOverlapped], rsi
0x1800060f1  mov     rcx, [rcx+10h]
0x1800060f5  call    WPP_SF_SS
0x1800060fa  mov     r15d, 3
0x180006100  jmp     short loc_18000610C
0x180006102  mov     rsi, [rsp+150h+pHandle]
0x180006107  mov     rdi, [rsp+150h+pHandle]
0x18000610c  test    r15b, 2
0x180006110  jz      short loc_18000611F
0x180006112  and     r15d, 0FFFFFFFDh
0x180006116  mov     rcx, rdi; bstrString
0x180006119  call    cs:__imp_SysFreeString
0x18000611f  test    r15b, 1
0x180006123  jz      short loc_18000612E
0x180006125  mov     rcx, rsi; bstrString
0x180006128  call    cs:__imp_SysFreeString
0x18000612e  mov     rax, [r14]
0x180006131  cmp     rax, qword ptr cs:rguid.Data1
0x180006138  jnz     loc_180006245
0x18000613e  mov     rax, [r14+8]
0x180006142  cmp     rax, qword ptr cs:rguid.Data4
0x180006149  jnz     loc_180006245
0x18000614f  xor     r12d, r12d
0x180006152  lea     edi, [rbx-18h]
0x180006155  mov     eax, 0D2h
0x18000615a  mov     [rsp+150h+var_118], r12d
0x18000615f  mov     r8d, edi; Length
0x180006162  mov     [rsp+150h+var_114], ax
0x180006167  lea     rdx, [r14+18h]; Buffer
0x18000616b  mov     ecx, 5EED5EFDh; InitialCrc
0x180006170  call    cs:__imp_RtlComputeCrc32
0x180006176  mov     ebx, eax
0x180006178  mov     rcx, cs:WPP_GLOBAL_Control
0x18000617f  lea     rax, WPP_GLOBAL_Control
0x180006186  cmp     rcx, rax
0x180006189  jz      short loc_1800061B5
0x18000618b  test    dword ptr [rcx+1Ch], 8000000h
0x180006192  jz      short loc_1800061B5
0x180006194  mov     r8d, [r14+10h]
0x180006198  lea     edx, [r12+11h]
0x18000619d  mov     rcx, [rcx+10h]
0x1800061a1  mov     r9d, ebx
0x1800061a4  mov     dword ptr [rsp+150h+lpOverlapped], r8d
0x1800061a9  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x1800061b0  call    WPP_SF_dd
0x1800061b5  mov     eax, 0D6h
0x1800061ba  cmp     [r14+10h], ebx
0x1800061be  jnz     short loc_18000623B
0x1800061c0  lea     r8, [rsp+150h+pHandle]; pHandle
0x1800061c5  mov     [rsp+150h+var_118], r12d
0x1800061ca  mov     edx, edi; BufferSize
0x1800061cc  mov     [rsp+150h+var_114], ax
0x1800061d1  lea     rcx, [r14+18h]; Buffer
0x1800061d5  call    cs:__imp_MesDecodeBufferHandleCreate
0x1800061db  mov     ebx, 80070000h
0x1800061e0  test    eax, eax
0x1800061e2  jle     short loc_1800061E9
0x1800061e4  movzx   eax, ax
0x1800061e7  or      eax, ebx
0x1800061e9  mov     [rsp+150h+var_118], eax
0x1800061ed  test    eax, eax
0x1800061ef  mov     eax, 0DBh
0x1800061f4  jns     short loc_180006200
0x1800061f6  mov     rsi, [rsp+150h+pv]
0x1800061fb  jmp     loc_180006287
0x180006200  mov     rcx, [rsp+150h+pHandle]
0x180006205  lea     rdx, DRVWUHELPER_ONDISK_DRIVER_INFO_Decode
0x18000620c  mov     r8, r13
0x18000620f  mov     [rsp+150h+var_114], ax
0x180006214  call    ??$InvokeCoder@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z1@Z; InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x180006219  test    eax, eax
0x18000621b  jle     short loc_180006222
0x18000621d  movzx   eax, ax
0x180006220  or      eax, ebx
0x180006222  mov     rsi, [rsp+150h+pv]
0x180006227  test    eax, eax
0x180006229  mov     [rsp+150h+var_118], eax
0x18000622d  mov     eax, 0DDh
0x180006232  js      short loc_180006287
0x180006234  mov     [rsp+150h+var_114], ax
0x180006239  jmp     short loc_18000628C
0x18000623b  mov     [rsp+150h+var_118], 8007000Dh
0x180006243  jmp     short loc_1800061F6
0x180006245  mov     [rsp+150h+var_118], 8007000Dh
0x18000624d  mov     eax, 0D2h
0x180006252  jmp     loc_180006066
0x180006257  mov     [rsp+150h+var_118], 8007000Eh
0x18000625f  mov     [rsp+150h+var_112], cx
0x180006264  jmp     short loc_18000628C
0x180006266  mov     [rsp+150h+var_118], 80070216h
0x18000626e  jmp     short loc_180006287
0x180006270  mov     [rsp+150h+var_118], 8007000Dh
0x180006278  jmp     short loc_180006287
0x18000627a  mov     eax, 0A0h
0x18000627f  mov     [rsp+150h+var_118], 80070057h
0x180006287  mov     [rsp+150h+var_112], ax
0x18000628c  mov     rcx, [rsp+150h+pHandle]; Handle
0x180006291  test    rcx, rcx
0x180006294  jz      short loc_1800062A1
0x180006296  call    cs:__imp_MesHandleFree
0x18000629c  mov     [rsp+150h+pHandle], r12
0x1800062a1  mov     rcx, rsi; pv
0x1800062a4  call    cs:__imp_CoTaskMemFree
0x1800062aa  mov     ebx, [rsp+150h+var_118]
0x1800062ae  lea     rcx, [rsp+150h+var_118]; this
0x1800062b3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800062b8  mov     eax, ebx
0x1800062ba  mov     rcx, [rbp+50h+var_40]
0x1800062be  xor     rcx, rsp; StackCookie
0x1800062c1  call    __security_check_cookie
0x1800062c6  mov     rbx, [rsp+150h+arg_8]
0x1800062ce  add     rsp, 120h
0x1800062d5  pop     r15
0x1800062d7  pop     r14
0x1800062d9  pop     r13
0x1800062db  pop     r12
0x1800062dd  pop     rdi
0x1800062de  pop     rsi
0x1800062df  pop     rbp
0x1800062e0  retn
```
