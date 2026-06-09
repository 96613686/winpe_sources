# SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x180022a74`
- end: `0x180022d44`
- name: `??$SerializeToFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z`
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
- `0x180022a74`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180022c4d`
- `KERNEL32!WriteFile` at `0x180022cac`
- `KERNEL32!WriteFile` at `0x180022c4d`
- `KERNEL32!WriteFile` at `0x180022cac`
- `ntdll!RtlComputeCrc32` at `0x180022bcd`
- `ntdll!RtlComputeCrc32` at `0x180022bcd`
- `RPCRT4!MesHandleFree` at `0x180022cf2`
- `RPCRT4!MesHandleFree` at `0x180022cf2`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022b5a`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180022b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022d04`
- `OLEAUT32!__imp_SysFreeString` at `0x180022c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180022c2d`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
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
  v11 = InvokeCoder<_SPP_METADATA_PROP>(pHandle, &SPP_ONDISK_SNAPSHOT_PROP_Encode, a4);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  LastFailureAsHRESULT = v11;
  v9 = v11 < 0;
  v10 = 95;
  if ( v9 )
    goto LABEL_12;
  Buffer = stru_18003C2F0;
  v22 = 95;
  LODWORD(v26) = RtlComputeCrc32(0x5EED5F85u, (PUCHAR)pBuffer, pEncodedSize);
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
0x180022a74  mov     [rsp-8+arg_8], rbx
0x180022a79  mov     [rsp-8+arg_10], rsi
0x180022a7e  push    rbp
0x180022a7f  push    rdi
0x180022a80  push    r13
0x180022a82  lea     rbp, [rsp-47h]
0x180022a87  sub     rsp, 0B0h
0x180022a8e  mov     rax, cs:__security_cookie
0x180022a95  xor     rax, rsp
0x180022a98  mov     [rbp+57h+var_20], rax
0x180022a9c  xor     esi, esi
0x180022a9e  mov     rdi, r9
0x180022aa1  mov     [rbp+57h+NumberOfBytesWritten], esi
0x180022aa4  mov     rbx, rcx
0x180022aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022aae  lea     r13, WPP_GLOBAL_Control
0x180022ab5  cmp     rcx, r13
0x180022ab8  jz      short loc_180022AD6
0x180022aba  test    dword ptr [rcx+1Ch], 20000000h
0x180022ac1  jz      short loc_180022AD6
0x180022ac3  mov     rcx, [rcx+10h]
0x180022ac7  lea     edx, [rsi+0Ch]
0x180022aca  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180022ad1  call    WPP_SF_
0x180022ad6  mov     r9d, 1; unsigned __int16
0x180022adc  lea     rdx, aSerializetofil; "SerializeToFile"
0x180022ae3  lea     rcx, [rbp+57h+var_78]; this
0x180022ae7  lea     r8d, [r9+4Ah]; unsigned __int16
0x180022aeb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180022af0  xor     eax, eax
0x180022af2  mov     [rbp+57h+pBuffer], rsi
0x180022af6  mov     [rbp+57h+var_28], rax
0x180022afa  xorps   xmm0, xmm0
0x180022afd  mov     [rbp+57h+pEncodedSize], esi
0x180022b00  mov     eax, 54h ; 'T'
0x180022b05  mov     [rbp+57h+pHandle], rsi
0x180022b09  mov     [rbp+57h+NumberOfBytesWritten], esi
0x180022b0c  movups  [rbp+57h+Buffer], xmm0
0x180022b10  test    rbx, rbx
0x180022b13  jnz     short loc_180022B25
0x180022b15  mov     [rbp+57h+var_78], 80070057h
0x180022b1c  mov     [rbp+57h+var_72], ax
0x180022b20  jmp     loc_180022D00
0x180022b25  mov     [rbp+57h+var_74], ax
0x180022b29  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022b2d  jnz     short loc_180022B34
0x180022b2f  lea     eax, [rbx+56h]
0x180022b32  jmp     short loc_180022B15
0x180022b34  mov     eax, 57h ; 'W'
0x180022b39  mov     [rbp+57h+var_74], ax
0x180022b3d  mov     eax, 58h ; 'X'
0x180022b42  test    rdi, rdi
0x180022b45  jz      short loc_180022B15
0x180022b47  lea     r8, [rbp+57h+pHandle]; pHandle
0x180022b4b  mov     [rbp+57h+var_78], esi
0x180022b4e  lea     rdx, [rbp+57h+pEncodedSize]; pEncodedSize
0x180022b52  mov     [rbp+57h+var_74], ax
0x180022b56  lea     rcx, [rbp+57h+pBuffer]; pBuffer
0x180022b5a  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180022b60  test    eax, eax
0x180022b62  jle     short loc_180022B6C
0x180022b64  movzx   eax, ax
0x180022b67  or      eax, 80070000h
0x180022b6c  mov     [rbp+57h+var_78], eax
0x180022b6f  test    eax, eax
0x180022b71  mov     eax, 5Dh ; ']'
0x180022b76  jns     short loc_180022B81
0x180022b78  mov     [rbp+57h+var_72], ax
0x180022b7c  jmp     loc_180022CE9
0x180022b81  mov     rcx, [rbp+57h+pHandle]
0x180022b85  lea     rdx, SPP_ONDISK_SNAPSHOT_PROP_Encode
0x180022b8c  mov     r8, rdi
0x180022b8f  mov     [rbp+57h+var_74], ax
0x180022b93  call    ??$InvokeCoder@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@Z1@Z; InvokeCoder<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_SPP_METADATA_PROP *)
0x180022b98  test    eax, eax
0x180022b9a  jle     short loc_180022BA4
0x180022b9c  movzx   eax, ax
0x180022b9f  or      eax, 80070000h
0x180022ba4  mov     [rbp+57h+var_78], eax
0x180022ba7  test    eax, eax
0x180022ba9  mov     eax, 5Fh ; '_'
0x180022bae  js      short loc_180022B78
0x180022bb0  movups  xmm0, xmmword ptr cs:stru_18003C2F0.Data1
0x180022bb7  mov     r8d, [rbp+57h+pEncodedSize]; Length
0x180022bbb  mov     ecx, 5EED5F85h; InitialCrc
0x180022bc0  mov     rdx, [rbp+57h+pBuffer]; Buffer
0x180022bc4  movdqu  [rbp+57h+Buffer], xmm0
0x180022bc9  mov     [rbp+57h+var_74], ax
0x180022bcd  call    cs:__imp_RtlComputeCrc32
0x180022bd3  mov     dword ptr [rbp+57h+var_28], eax
0x180022bd6  mov     rax, cs:WPP_GLOBAL_Control
0x180022bdd  cmp     rax, r13
0x180022be0  jz      short loc_180022C23
0x180022be2  test    dword ptr [rax+1Ch], 8000000h
0x180022be9  jz      short loc_180022C23
0x180022beb  lea     rdx, [rbp+57h+Buffer]; struct _GUID *
0x180022bef  lea     rcx, [rbp+57h+bstrString]; this
0x180022bf3  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x180022bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bff  lea     r8, WPP_4fb2ab0666f63245bbaf83dcb0c273d6_Traceguids
0x180022c06  mov     edx, 0Dh
0x180022c0b  mov     r9, [rax]
0x180022c0e  mov     eax, dword ptr [rbp+57h+var_28]
0x180022c11  mov     rcx, [rcx+10h]
0x180022c15  mov     dword ptr [rsp+0C0h+lpOverlapped], eax
0x180022c19  call    WPP_SF_Sd
0x180022c1e  mov     esi, 1
0x180022c23  test    sil, 1
0x180022c27  jz      short loc_180022C33
0x180022c29  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180022c2d  call    cs:__imp_SysFreeString
0x180022c33  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180022c37  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180022c40  mov     r8d, 18h; nNumberOfBytesToWrite
0x180022c46  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180022c4a  mov     rcx, rbx; hFile
0x180022c4d  call    cs:__imp_WriteFile
0x180022c53  test    eax, eax
0x180022c55  jnz     short loc_180022C69
0x180022c57  call    GetLastFailureAsHRESULT
0x180022c5c  mov     [rbp+57h+var_78], eax
0x180022c5f  mov     eax, 6Dh ; 'm'
0x180022c64  jmp     loc_180022B78
0x180022c69  cmp     [rbp+57h+NumberOfBytesWritten], 18h
0x180022c6d  mov     eax, 6Dh ; 'm'
0x180022c72  mov     [rbp+57h+var_74], ax
0x180022c76  mov     eax, 6Fh ; 'o'
0x180022c7b  jz      short loc_180022C89
0x180022c7d  mov     [rbp+57h+var_78], 8000FFFFh
0x180022c84  jmp     loc_180022B78
0x180022c89  mov     r8d, [rbp+57h+pEncodedSize]; nNumberOfBytesToWrite
0x180022c8d  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180022c91  mov     rdx, [rbp+57h+pBuffer]; lpBuffer
0x180022c95  mov     rcx, rbx; hFile
0x180022c98  mov     [rbp+57h+var_78], 0
0x180022c9f  mov     [rbp+57h+var_74], ax
0x180022ca3  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180022cac  call    cs:__imp_WriteFile
0x180022cb2  test    eax, eax
0x180022cb4  jnz     short loc_180022CC8
0x180022cb6  call    GetLastFailureAsHRESULT
0x180022cbb  mov     [rbp+57h+var_78], eax
0x180022cbe  mov     eax, 74h ; 't'
0x180022cc3  jmp     loc_180022B78
0x180022cc8  mov     eax, 74h ; 't'
0x180022ccd  mov     [rbp+57h+var_74], ax
0x180022cd1  mov     eax, [rbp+57h+pEncodedSize]
0x180022cd4  cmp     [rbp+57h+NumberOfBytesWritten], eax
0x180022cd7  mov     eax, 76h ; 'v'
0x180022cdc  jnz     short loc_180022C7D
0x180022cde  mov     [rbp+57h+var_78], 0
0x180022ce5  mov     [rbp+57h+var_74], ax
0x180022ce9  mov     rcx, [rbp+57h+pHandle]; Handle
0x180022ced  test    rcx, rcx
0x180022cf0  jz      short loc_180022D00
0x180022cf2  call    cs:__imp_MesHandleFree
0x180022cf8  mov     [rbp+57h+pHandle], 0
0x180022d00  mov     rcx, [rbp+57h+pBuffer]; pv
0x180022d04  call    cs:__imp_CoTaskMemFree
0x180022d0a  mov     [rbp+57h+pBuffer], 0
0x180022d12  mov     ebx, [rbp+57h+var_78]
0x180022d15  lea     rcx, [rbp+57h+var_78]; this
0x180022d19  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180022d1e  mov     eax, ebx
0x180022d20  mov     rcx, [rbp+57h+var_20]
0x180022d24  xor     rcx, rsp; StackCookie
0x180022d27  call    __security_check_cookie
0x180022d2c  lea     r11, [rsp+0C0h+var_10]
0x180022d34  mov     rbx, [r11+28h]
0x180022d38  mov     rsi, [r11+30h]
0x180022d3c  mov     rsp, r11
0x180022d3f  pop     r13
0x180022d41  pop     rdi
0x180022d42  pop     rbp
0x180022d43  retn
```
