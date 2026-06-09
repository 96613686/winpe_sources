# DeserializeFromFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x1800062e8`
- end: `0x180006799`
- name: `??$DeserializeFromFile@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@ZPEBU_GUID@@1@Z`
- size: `1201`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003550`

## callees

- `0x180003ce0`
- `0x1800062e8`
- `0x1800067a0`
- `0x180006f58`
- `0x180006fac`
- `0x1800070d4`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x1800063db`
- `KERNEL32!GetFileSizeEx` at `0x1800063db`
- `KERNEL32!ReadFile` at `0x1800064db`
- `KERNEL32!ReadFile` at `0x1800064db`
- `ntdll!RtlComputeCrc32` at `0x180006628`
- `ntdll!RtlComputeCrc32` at `0x180006628`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000668d`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x18000668d`
- `RPCRT4!MesHandleFree` at `0x18000674e`
- `RPCRT4!MesHandleFree` at `0x18000674e`
- `ole32!StringFromGUID2` at `0x18000656a`
- `ole32!StringFromGUID2` at `0x180006587`
- `ole32!StringFromGUID2` at `0x18000656a`
- `ole32!StringFromGUID2` at `0x180006587`
- `ole32!CoTaskMemAlloc` at `0x18000647f`
- `ole32!CoTaskMemAlloc` at `0x18000647f`
- `ole32!CoTaskMemFree` at `0x18000675c`
- `ole32!CoTaskMemFree` at `0x18000675c`
- `OLEAUT32!__imp_SysAllocString` at `0x180006574`
- `OLEAUT32!__imp_SysAllocString` at `0x180006591`
- `OLEAUT32!__imp_SysAllocString` at `0x180006574`
- `OLEAUT32!__imp_SysAllocString` at `0x180006591`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800065e0`

## string_xrefs

- `0x18000635a`: `DeserializeFromFile`

## pseudocode

```c
__int64 __fastcall DeserializeFromFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(
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
    StringFromGUID2(&stru_180019528, sz, 64);
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
  if ( *(_QWORD *)&v15->Data1 != 0x4AFA7B9C5C0B0F32LL || *(_QWORD *)v15->Data4 != 0x495A0BE65F9338A8LL )
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
      v27 = InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(pHandle, &DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode, a4);
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
0x1800062e8  mov     [rsp-8+arg_8], rbx
0x1800062ed  push    rbp
0x1800062ee  push    rsi
0x1800062ef  push    rdi
0x1800062f0  push    r12
0x1800062f2  push    r13
0x1800062f4  push    r14
0x1800062f6  push    r15
0x1800062f8  lea     rbp, [rsp-20h]
0x1800062fd  sub     rsp, 120h
0x180006304  mov     rax, cs:__security_cookie
0x18000630b  xor     rax, rsp
0x18000630e  mov     [rbp+50h+var_40], rax
0x180006312  xor     r12d, r12d
0x180006315  mov     r13, r9
0x180006318  mov     r15d, r12d
0x18000631b  mov     [rsp+150h+var_D4], r12d
0x180006320  mov     rdi, rcx
0x180006323  mov     rcx, cs:WPP_GLOBAL_Control
0x18000632a  lea     rbx, WPP_GLOBAL_Control
0x180006331  cmp     rcx, rbx
0x180006334  jz      short loc_180006354
0x180006336  test    dword ptr [rcx+1Ch], 20000000h
0x18000633d  jz      short loc_180006354
0x18000633f  mov     rcx, [rcx+10h]
0x180006343  lea     edx, [r12+0Eh]
0x180006348  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x18000634f  call    WPP_SF_
0x180006354  mov     r8d, 8Eh; unsigned __int16
0x18000635a  lea     rdx, aDeserializefro; "DeserializeFromFile"
0x180006361  lea     rcx, [rsp+150h+var_118]; this
0x180006366  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000636b  mov     [rsp+150h+pHandle], r12
0x180006370  mov     rsi, r12
0x180006373  mov     qword ptr [rbp+50h+FileSize], r12
0x180006377  mov     [rsp+150h+NumberOfBytesRead], r12d
0x18000637c  test    r13, r13
0x18000637f  jz      short loc_180006395
0x180006381  mov     ecx, 10h
0x180006386  mov     rax, r13
0x180006389  mov     [rax], r12b
0x18000638c  inc     rax
0x18000638f  sub     rcx, 1
0x180006393  jnz     short loc_180006389
0x180006395  mov     eax, 9Fh
0x18000639a  test    rdi, rdi
0x18000639d  jz      loc_180006737
0x1800063a3  mov     [rsp+150h+var_114], ax
0x1800063a8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800063ac  jz      loc_180006732
0x1800063b2  mov     eax, 0A2h
0x1800063b7  mov     [rsp+150h+var_114], ax
0x1800063bc  mov     eax, 0A3h
0x1800063c1  test    r13, r13
0x1800063c4  jz      loc_180006737
0x1800063ca  lea     rdx, [rbp+50h+FileSize]; lpFileSize
0x1800063ce  mov     [rsp+150h+var_118], r12d
0x1800063d3  mov     rcx, rdi; hFile
0x1800063d6  mov     [rsp+150h+var_114], ax
0x1800063db  call    cs:__imp_GetFileSizeEx
0x1800063e1  test    eax, eax
0x1800063e3  jnz     short loc_1800063F8
0x1800063e5  call    GetLastFailureAsHRESULT
0x1800063ea  mov     [rsp+150h+var_118], eax
0x1800063ee  mov     eax, 0A9h
0x1800063f3  jmp     loc_18000673F
0x1800063f8  mov     eax, 0A9h
0x1800063fd  mov     [rsp+150h+var_118], r12d
0x180006402  mov     [rsp+150h+var_114], ax
0x180006407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000640e  cmp     rcx, rbx
0x180006411  jz      short loc_180006430
0x180006413  test    dword ptr [rcx+1Ch], 8000000h
0x18000641a  jz      short loc_180006430
0x18000641c  mov     eax, dword ptr [rbp+50h+FileSize]
0x18000641f  mov     r9d, dword ptr [rbp+50h+FileSize+4]
0x180006423  mov     rcx, [rcx+10h]
0x180006427  mov     dword ptr [rsp+150h+lpOverlapped], eax
0x18000642b  call    WPP_SF_LD
0x180006430  mov     rbx, qword ptr [rbp+50h+FileSize]
0x180006434  mov     eax, 0ACh
0x180006439  cmp     rbx, 10000000h
0x180006440  jge     loc_180006728
0x180006446  mov     [rsp+150h+var_114], ax
0x18000644b  mov     eax, 0ADh
0x180006450  cmp     rbx, 18h
0x180006454  jbe     loc_180006728
0x18000645a  mov     [rsp+150h+var_114], ax
0x18000645f  mov     eax, 0FFFFFFFFh
0x180006464  cmp     rbx, rax
0x180006467  mov     eax, 0AEh
0x18000646c  ja      loc_18000671E
0x180006472  lea     ecx, [rbx+7]; cb
0x180006475  mov     [rsp+150h+var_118], r12d
0x18000647a  mov     [rsp+150h+var_114], ax
0x18000647f  call    cs:__imp_CoTaskMemAlloc
0x180006485  mov     [rsp+150h+pv], rax
0x18000648a  mov     rsi, rax
0x18000648d  mov     ecx, 0B6h
0x180006492  test    rax, rax
0x180006495  jz      loc_18000670F
0x18000649b  lea     r14, [rax+7]
0x18000649f  mov     [rsp+150h+var_118], r12d
0x1800064a4  and     r14, 0FFFFFFFFFFFFFFF8h
0x1800064a8  mov     [rsp+150h+var_114], cx
0x1800064ad  mov     r12, r14
0x1800064b0  mov     esi, ebx
0x1800064b2  test    ebx, ebx
0x1800064b4  jz      loc_18000653B
0x1800064ba  mov     eax, 100000h
0x1800064bf  mov     [rsp+150h+lpOverlapped], r15; lpOverlapped
0x1800064c4  cmp     esi, eax
0x1800064c6  lea     r9, [rsp+150h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800064cb  mov     rdx, r12; lpBuffer
0x1800064ce  mov     rcx, rdi; hFile
0x1800064d1  cmovb   eax, esi
0x1800064d4  mov     r8d, eax; nNumberOfBytesToRead
0x1800064d7  mov     [rsp+150h+var_D4], eax
0x1800064db  call    cs:__imp_ReadFile
0x1800064e1  test    eax, eax
0x1800064e3  jz      short loc_18000652B
0x1800064e5  mov     eax, 0C3h
0x1800064ea  mov     [rsp+150h+var_114], ax
0x1800064ef  mov     eax, [rsp+150h+NumberOfBytesRead]
0x1800064f3  cmp     eax, [rsp+150h+var_D4]
0x1800064f7  jnz     short loc_180006511
0x1800064f9  mov     [rsp+150h+var_118], r15d
0x1800064fe  mov     ecx, 0C5h
0x180006503  mov     [rsp+150h+var_114], cx
0x180006508  sub     esi, eax
0x18000650a  jz      short loc_18000653B
0x18000650c  add     r12, rax
0x18000650f  jmp     short loc_1800064BA
0x180006511  mov     [rsp+150h+var_118], 8000FFFFh
0x180006519  mov     eax, 0C5h
0x18000651e  mov     rsi, [rsp+150h+pv]
0x180006523  xor     r12d, r12d
0x180006526  jmp     loc_18000673F
0x18000652b  call    GetLastFailureAsHRESULT
0x180006530  mov     [rsp+150h+var_118], eax
0x180006534  mov     eax, 0C3h
0x180006539  jmp     short loc_18000651E
0x18000653b  mov     rax, cs:WPP_GLOBAL_Control
0x180006542  lea     rcx, WPP_GLOBAL_Control
0x180006549  cmp     rax, rcx
0x18000654c  jz      short loc_1800065BA
0x18000654e  test    dword ptr [rax+1Ch], 8000000h
0x180006555  jz      short loc_1800065BA
0x180006557  mov     edi, 40h ; '@'
0x18000655c  lea     rdx, [rbp+50h+sz]; lpsz
0x180006560  mov     r8d, edi; cchMax
0x180006563  lea     rcx, stru_180019528; rguid
0x18000656a  call    cs:__imp_StringFromGUID2
0x180006570  lea     rcx, [rbp+50h+sz]; psz
0x180006574  call    cs:__imp_SysAllocString
0x18000657a  mov     r8d, edi; cchMax
0x18000657d  lea     rdx, [rbp+50h+sz]; lpsz
0x180006581  mov     rcx, r14; rguid
0x180006584  mov     rsi, rax
0x180006587  call    cs:__imp_StringFromGUID2
0x18000658d  lea     rcx, [rbp+50h+sz]; psz
0x180006591  call    cs:__imp_SysAllocString
0x180006597  mov     rcx, cs:WPP_GLOBAL_Control
0x18000659e  mov     r9, rax
0x1800065a1  mov     rdi, rax
0x1800065a4  mov     [rsp+150h+lpOverlapped], rsi
0x1800065a9  mov     rcx, [rcx+10h]
0x1800065ad  call    WPP_SF_SS
0x1800065b2  mov     r15d, 3
0x1800065b8  jmp     short loc_1800065C4
0x1800065ba  mov     rsi, [rsp+150h+pHandle]
0x1800065bf  mov     rdi, [rsp+150h+pHandle]
0x1800065c4  test    r15b, 2
0x1800065c8  jz      short loc_1800065D7
0x1800065ca  and     r15d, 0FFFFFFFDh
0x1800065ce  mov     rcx, rdi; bstrString
0x1800065d1  call    cs:__imp_SysFreeString
0x1800065d7  test    r15b, 1
0x1800065db  jz      short loc_1800065E6
0x1800065dd  mov     rcx, rsi; bstrString
0x1800065e0  call    cs:__imp_SysFreeString
0x1800065e6  mov     rax, [r14]
0x1800065e9  cmp     rax, qword ptr cs:stru_180019528.Data1
0x1800065f0  jnz     loc_1800066FD
0x1800065f6  mov     rax, [r14+8]
0x1800065fa  cmp     rax, qword ptr cs:stru_180019528.Data4
0x180006601  jnz     loc_1800066FD
0x180006607  xor     r12d, r12d
0x18000660a  lea     edi, [rbx-18h]
0x18000660d  mov     eax, 0D2h
0x180006612  mov     [rsp+150h+var_118], r12d
0x180006617  mov     r8d, edi; Length
0x18000661a  mov     [rsp+150h+var_114], ax
0x18000661f  lea     rdx, [r14+18h]; Buffer
0x180006623  mov     ecx, 5EED5EFDh; InitialCrc
0x180006628  call    cs:__imp_RtlComputeCrc32
0x18000662e  mov     ebx, eax
0x180006630  mov     rcx, cs:WPP_GLOBAL_Control
0x180006637  lea     rax, WPP_GLOBAL_Control
0x18000663e  cmp     rcx, rax
0x180006641  jz      short loc_18000666D
0x180006643  test    dword ptr [rcx+1Ch], 8000000h
0x18000664a  jz      short loc_18000666D
0x18000664c  mov     r8d, [r14+10h]
0x180006650  lea     edx, [r12+11h]
0x180006655  mov     rcx, [rcx+10h]
0x180006659  mov     r9d, ebx
0x18000665c  mov     dword ptr [rsp+150h+lpOverlapped], r8d
0x180006661  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x180006668  call    WPP_SF_dd
0x18000666d  mov     eax, 0D6h
0x180006672  cmp     [r14+10h], ebx
0x180006676  jnz     short loc_1800066F3
0x180006678  lea     r8, [rsp+150h+pHandle]; pHandle
0x18000667d  mov     [rsp+150h+var_118], r12d
0x180006682  mov     edx, edi; BufferSize
0x180006684  mov     [rsp+150h+var_114], ax
0x180006689  lea     rcx, [r14+18h]; Buffer
0x18000668d  call    cs:__imp_MesDecodeBufferHandleCreate
0x180006693  mov     ebx, 80070000h
0x180006698  test    eax, eax
0x18000669a  jle     short loc_1800066A1
0x18000669c  movzx   eax, ax
0x18000669f  or      eax, ebx
0x1800066a1  mov     [rsp+150h+var_118], eax
0x1800066a5  test    eax, eax
0x1800066a7  mov     eax, 0DBh
0x1800066ac  jns     short loc_1800066B8
0x1800066ae  mov     rsi, [rsp+150h+pv]
0x1800066b3  jmp     loc_18000673F
0x1800066b8  mov     rcx, [rsp+150h+pHandle]
0x1800066bd  lea     rdx, DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Decode
0x1800066c4  mov     r8, r13
0x1800066c7  mov     [rsp+150h+var_114], ax
0x1800066cc  call    ??$InvokeCoder@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z1@Z; InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x1800066d1  test    eax, eax
0x1800066d3  jle     short loc_1800066DA
0x1800066d5  movzx   eax, ax
0x1800066d8  or      eax, ebx
0x1800066da  mov     rsi, [rsp+150h+pv]
0x1800066df  test    eax, eax
0x1800066e1  mov     [rsp+150h+var_118], eax
0x1800066e5  mov     eax, 0DDh
0x1800066ea  js      short loc_18000673F
0x1800066ec  mov     [rsp+150h+var_114], ax
0x1800066f1  jmp     short loc_180006744
0x1800066f3  mov     [rsp+150h+var_118], 8007000Dh
0x1800066fb  jmp     short loc_1800066AE
0x1800066fd  mov     [rsp+150h+var_118], 8007000Dh
0x180006705  mov     eax, 0D2h
0x18000670a  jmp     loc_18000651E
0x18000670f  mov     [rsp+150h+var_118], 8007000Eh
0x180006717  mov     [rsp+150h+var_112], cx
0x18000671c  jmp     short loc_180006744
0x18000671e  mov     [rsp+150h+var_118], 80070216h
0x180006726  jmp     short loc_18000673F
0x180006728  mov     [rsp+150h+var_118], 8007000Dh
0x180006730  jmp     short loc_18000673F
0x180006732  mov     eax, 0A0h
0x180006737  mov     [rsp+150h+var_118], 80070057h
0x18000673f  mov     [rsp+150h+var_112], ax
0x180006744  mov     rcx, [rsp+150h+pHandle]; Handle
0x180006749  test    rcx, rcx
0x18000674c  jz      short loc_180006759
0x18000674e  call    cs:__imp_MesHandleFree
0x180006754  mov     [rsp+150h+pHandle], r12
0x180006759  mov     rcx, rsi; pv
0x18000675c  call    cs:__imp_CoTaskMemFree
0x180006762  mov     ebx, [rsp+150h+var_118]
0x180006766  lea     rcx, [rsp+150h+var_118]; this
0x18000676b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180006770  mov     eax, ebx
0x180006772  mov     rcx, [rbp+50h+var_40]
0x180006776  xor     rcx, rsp; StackCookie
0x180006779  call    __security_check_cookie
0x18000677e  mov     rbx, [rsp+150h+arg_8]
0x180006786  add     rsp, 120h
0x18000678d  pop     r15
0x18000678f  pop     r14
0x180006791  pop     r13
0x180006793  pop     r12
0x180006795  pop     rdi
0x180006796  pop     rsi
0x180006797  pop     rbp
0x180006798  retn
```
