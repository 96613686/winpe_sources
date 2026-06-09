# SerializeToFile<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_GUID const *,_SPP_METADATA_PROP *)

- ea: `0x18002279c`
- end: `0x180022a6c`
- name: `??$SerializeToFile@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@ZPEBU_GUID@@1@Z`
- size: `720`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ff4c`

## callees

- `0x18000220c`
- `0x180020710`
- `0x180020968`
- `0x180022500`
- `0x18002279c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180022975`
- `KERNEL32!WriteFile` at `0x1800229d4`
- `KERNEL32!WriteFile` at `0x180022975`
- `KERNEL32!WriteFile` at `0x1800229d4`
- `ntdll!RtlComputeCrc32` at `0x1800228f5`
- `ntdll!RtlComputeCrc32` at `0x1800228f5`
- `RPCRT4!MesHandleFree` at `0x180022a1a`
- `RPCRT4!MesHandleFree` at `0x180022a1a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022882`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022a2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180022955`
- `OLEAUT32!__imp_SysFreeString` at `0x180022955`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_SPP_METADATA_PROP>(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // si
  __int16 v7; // ax
  int v8; // eax
  bool v9; // sf
  __int16 v10; // ax
  signed int v11; // eax
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-39h] BYREF
  unsigned int pEncodedSize; // [rsp+34h] [rbp-35h] BYREF
  char *pBuffer; // [rsp+38h] [rbp-31h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp-29h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-21h] BYREF
  __int16 v22; // [rsp+4Ch] [rbp-1Dh]
  __int16 v23; // [rsp+4Eh] [rbp-1Bh]
  BSTR bstrString; // [rsp+80h] [rbp+17h] BYREF
  struct _GUID Buffer; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+98h] [rbp+2Fh]

  v4 = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SerializeToFile", 0x4Bu, 1u);
  pBuffer = 0;
  v26 = 0;
  pEncodedSize = 0;
  v7 = 84;
  pHandle = 0;
  NumberOfBytesWritten = 0;
  Buffer = 0;
  if ( !hFile )
    goto LABEL_5;
  v22 = 84;
  if ( hFile == (HANDLE)-1LL )
  {
    v7 = 85;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v23 = v7;
    goto LABEL_31;
  }
  v22 = 87;
  v7 = 88;
  if ( !a4 )
    goto LABEL_5;
  LastFailureAsHRESULT = 0;
  v22 = 88;
  v8 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  LastFailureAsHRESULT = v8;
  v9 = v8 < 0;
  v10 = 93;
  if ( v9 )
    goto LABEL_12;
  v22 = 93;
  v11 = InvokeCoder<_SPP_METADATA_PROP>(pHandle, &SPP_METADATA_PROP_Encode, a4);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  LastFailureAsHRESULT = v11;
  v9 = v11 < 0;
  v10 = 95;
  if ( v9 )
    goto LABEL_12;
  Buffer = stru_18003C2E0;
  v22 = 95;
  LODWORD(v26) = RtlComputeCrc32(0x5EED5F15u, (PUCHAR)pBuffer, pEncodedSize);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v12 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &Buffer);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids,
      *v12,
      v26);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
    SysFreeString(bstrString);
  if ( !WriteFile(hFile, &Buffer, 0x18u, &NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
    v10 = 109;
LABEL_12:
    v23 = v10;
    goto LABEL_29;
  }
  v22 = 109;
  v10 = 111;
  if ( NumberOfBytesWritten != 24 )
    goto LABEL_24;
  LastFailureAsHRESULT = 0;
  v22 = 111;
  if ( !WriteFile(hFile, pBuffer, pEncodedSize, &NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v10 = 116;
    goto LABEL_12;
  }
  v22 = 116;
  v10 = 118;
  if ( NumberOfBytesWritten != pEncodedSize )
  {
LABEL_24:
    LastFailureAsHRESULT = -2147418113;
    goto LABEL_12;
  }
  LastFailureAsHRESULT = 0;
  v22 = 118;
LABEL_29:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
LABEL_31:
  CoTaskMemFree(pBuffer);
  pBuffer = 0;
  v15 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v15;
}

```

## disassembly

```asm
0x18002279c  mov     [rsp-8+arg_8], rbx
0x1800227a1  mov     [rsp-8+arg_10], rsi
0x1800227a6  push    rbp
0x1800227a7  push    rdi
0x1800227a8  push    r13
0x1800227aa  lea     rbp, [rsp-47h]
0x1800227af  sub     rsp, 0B0h
0x1800227b6  mov     rax, cs:__security_cookie
0x1800227bd  xor     rax, rsp
0x1800227c0  mov     [rbp+57h+var_20], rax
0x1800227c4  xor     esi, esi
0x1800227c6  mov     rdi, r9
0x1800227c9  mov     [rbp+57h+NumberOfBytesWritten], esi
0x1800227cc  mov     rbx, rcx
0x1800227cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227d6  lea     r13, WPP_GLOBAL_Control
0x1800227dd  cmp     rcx, r13
0x1800227e0  jz      short loc_1800227FE
0x1800227e2  test    dword ptr [rcx+1Ch], 20000000h
0x1800227e9  jz      short loc_1800227FE
0x1800227eb  mov     rcx, [rcx+10h]
0x1800227ef  lea     edx, [rsi+0Ch]
0x1800227f2  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x1800227f9  call    WPP_SF_
0x1800227fe  mov     r9d, 1; unsigned __int16
0x180022804  lea     rdx, aSerializetofil; "SerializeToFile"
0x18002280b  lea     rcx, [rbp+57h+var_78]; this
0x18002280f  lea     r8d, [r9+4Ah]; unsigned __int16
0x180022813  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180022818  xor     eax, eax
0x18002281a  mov     [rbp+57h+pBuffer], rsi
0x18002281e  mov     [rbp+57h+var_28], rax
0x180022822  xorps   xmm0, xmm0
0x180022825  mov     [rbp+57h+pEncodedSize], esi
0x180022828  mov     eax, 54h ; 'T'
0x18002282d  mov     [rbp+57h+pHandle], rsi
0x180022831  mov     [rbp+57h+NumberOfBytesWritten], esi
0x180022834  movups  [rbp+57h+Buffer], xmm0
0x180022838  test    rbx, rbx
0x18002283b  jnz     short loc_18002284D
0x18002283d  mov     [rbp+57h+var_78], 80070057h
0x180022844  mov     [rbp+57h+var_72], ax
0x180022848  jmp     loc_180022A28
0x18002284d  mov     [rbp+57h+var_74], ax
0x180022851  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022855  jnz     short loc_18002285C
0x180022857  lea     eax, [rbx+56h]
0x18002285a  jmp     short loc_18002283D
0x18002285c  mov     eax, 57h ; 'W'
0x180022861  mov     [rbp+57h+var_74], ax
0x180022865  mov     eax, 58h ; 'X'
0x18002286a  test    rdi, rdi
0x18002286d  jz      short loc_18002283D
0x18002286f  lea     r8, [rbp+57h+pHandle]; pHandle
0x180022873  mov     [rbp+57h+var_78], esi
0x180022876  lea     rdx, [rbp+57h+pEncodedSize]; pEncodedSize
0x18002287a  mov     [rbp+57h+var_74], ax
0x18002287e  lea     rcx, [rbp+57h+pBuffer]; pBuffer
0x180022882  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180022888  test    eax, eax
0x18002288a  jle     short loc_180022894
0x18002288c  movzx   eax, ax
0x18002288f  or      eax, 80070000h
0x180022894  mov     [rbp+57h+var_78], eax
0x180022897  test    eax, eax
0x180022899  mov     eax, 5Dh ; ']'
0x18002289e  jns     short loc_1800228A9
0x1800228a0  mov     [rbp+57h+var_72], ax
0x1800228a4  jmp     loc_180022A11
0x1800228a9  mov     rcx, [rbp+57h+pHandle]
0x1800228ad  lea     rdx, SPP_METADATA_PROP_Encode
0x1800228b4  mov     r8, rdi
0x1800228b7  mov     [rbp+57h+var_74], ax
0x1800228bb  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x1800228c0  test    eax, eax
0x1800228c2  jle     short loc_1800228CC
0x1800228c4  movzx   eax, ax
0x1800228c7  or      eax, 80070000h
0x1800228cc  mov     [rbp+57h+var_78], eax
0x1800228cf  test    eax, eax
0x1800228d1  mov     eax, 5Fh ; '_'
0x1800228d6  js      short loc_1800228A0
0x1800228d8  movups  xmm0, xmmword ptr cs:stru_18003C2E0.Data1
0x1800228df  mov     r8d, [rbp+57h+pEncodedSize]; Length
0x1800228e3  mov     ecx, 5EED5F15h; InitialCrc
0x1800228e8  mov     rdx, [rbp+57h+pBuffer]; Buffer
0x1800228ec  movdqu  [rbp+57h+Buffer], xmm0
0x1800228f1  mov     [rbp+57h+var_74], ax
0x1800228f5  call    cs:__imp_RtlComputeCrc32
0x1800228fb  mov     dword ptr [rbp+57h+var_28], eax
0x1800228fe  mov     rax, cs:WPP_GLOBAL_Control
0x180022905  cmp     rax, r13
0x180022908  jz      short loc_18002294B
0x18002290a  test    dword ptr [rax+1Ch], 8000000h
0x180022911  jz      short loc_18002294B
0x180022913  lea     rdx, [rbp+57h+Buffer]; struct _GUID *
0x180022917  lea     rcx, [rbp+57h+bstrString]; this
0x18002291b  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180022920  mov     rcx, cs:WPP_GLOBAL_Control
0x180022927  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x18002292e  mov     edx, 0Dh
0x180022933  mov     r9, [rax]
0x180022936  mov     eax, dword ptr [rbp+57h+var_28]
0x180022939  mov     rcx, [rcx+10h]
0x18002293d  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x180022941  call    WPP_SF_Sd
0x180022946  mov     esi, 1
0x18002294b  test    sil, 1
0x18002294f  jz      short loc_18002295B
0x180022951  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180022955  call    cs:__imp_SysFreeString
0x18002295b  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002295f  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180022968  mov     r8d, 18h; nNumberOfBytesToWrite
0x18002296e  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180022972  mov     rcx, rbx; hFile
0x180022975  call    cs:__imp_WriteFile
0x18002297b  test    eax, eax
0x18002297d  jnz     short loc_180022991
0x18002297f  call    GetLastFailureAsHRESULT
0x180022984  mov     [rbp+57h+var_78], eax
0x180022987  mov     eax, 6Dh ; 'm'
0x18002298c  jmp     loc_1800228A0
0x180022991  cmp     [rbp+57h+NumberOfBytesWritten], 18h
0x180022995  mov     eax, 6Dh ; 'm'
0x18002299a  mov     [rbp+57h+var_74], ax
0x18002299e  mov     eax, 6Fh ; 'o'
0x1800229a3  jz      short loc_1800229B1
0x1800229a5  mov     [rbp+57h+var_78], 8000FFFFh
0x1800229ac  jmp     loc_1800228A0
0x1800229b1  mov     r8d, [rbp+57h+pEncodedSize]; nNumberOfBytesToWrite
0x1800229b5  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800229b9  mov     rdx, [rbp+57h+pBuffer]; lpBuffer
0x1800229bd  mov     rcx, rbx; hFile
0x1800229c0  mov     [rbp+57h+var_78], 0
0x1800229c7  mov     [rbp+57h+var_74], ax
0x1800229cb  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x1800229d4  call    cs:__imp_WriteFile
0x1800229da  test    eax, eax
0x1800229dc  jnz     short loc_1800229F0
0x1800229de  call    GetLastFailureAsHRESULT
0x1800229e3  mov     [rbp+57h+var_78], eax
0x1800229e6  mov     eax, 74h ; 't'
0x1800229eb  jmp     loc_1800228A0
0x1800229f0  mov     eax, 74h ; 't'
0x1800229f5  mov     [rbp+57h+var_74], ax
0x1800229f9  mov     eax, [rbp+57h+pEncodedSize]
0x1800229fc  cmp     [rbp+57h+NumberOfBytesWritten], eax
0x1800229ff  mov     eax, 76h ; 'v'
0x180022a04  jnz     short loc_1800229A5
0x180022a06  mov     [rbp+57h+var_78], 0
0x180022a0d  mov     [rbp+57h+var_74], ax
0x180022a11  mov     rcx, [rbp+57h+pHandle]; Handle
0x180022a15  test    rcx, rcx
0x180022a18  jz      short loc_180022A28
0x180022a1a  call    cs:__imp_MesHandleFree
0x180022a20  mov     [rbp+57h+pHandle], 0
0x180022a28  mov     rcx, [rbp+57h+pBuffer]; pv
0x180022a2c  call    cs:__imp_CoTaskMemFree
0x180022a32  mov     [rbp+57h+pBuffer], 0
0x180022a3a  mov     ebx, [rbp+57h+var_78]
0x180022a3d  lea     rcx, [rbp+57h+var_78]; this
0x180022a41  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180022a46  mov     eax, ebx
0x180022a48  mov     rcx, [rbp+57h+var_20]
0x180022a4c  xor     rcx, rsp; StackCookie
0x180022a4f  call    __security_check_cookie
0x180022a54  lea     r11, [rsp+0C0h+var_10]
0x180022a5c  mov     rbx, [r11+28h]
0x180022a60  mov     rsi, [r11+30h]
0x180022a64  mov     rsp, r11
0x180022a67  pop     r13
0x180022a69  pop     rdi
0x180022a6a  pop     rbp
0x180022a6b  retn
```
