# SerializeToFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x180006b50`
- end: `0x180006e57`
- name: `??$SerializeToFile@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@ZPEBU_GUID@@1@Z`
- size: `775`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800022e4`

## callees

- `0x180003ce0`
- `0x1800067a0`
- `0x180006b50`
- `0x180007050`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180006d4b`
- `KERNEL32!WriteFile` at `0x180006db3`
- `KERNEL32!WriteFile` at `0x180006d4b`
- `KERNEL32!WriteFile` at `0x180006db3`
- `ntdll!RtlComputeCrc32` at `0x180006cbc`
- `ntdll!RtlComputeCrc32` at `0x180006cbc`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180006c41`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180006c41`
- `RPCRT4!MesHandleFree` at `0x180006e00`
- `RPCRT4!MesHandleFree` at `0x180006e00`
- `ole32!StringFromGUID2` at `0x180006ce8`
- `ole32!StringFromGUID2` at `0x180006ce8`
- `ole32!CoTaskMemFree` at `0x180006e14`
- `ole32!CoTaskMemFree` at `0x180006e14`
- `OLEAUT32!__imp_SysAllocString` at `0x180006cf2`
- `OLEAUT32!__imp_SysAllocString` at `0x180006cf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006d2a`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO>(
        HANDLE hFile,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // si
  __int16 v7; // ax
  int v8; // eax
  bool v9; // sf
  __int16 v10; // ax
  int v11; // eax
  OLECHAR *v12; // rbx
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int pEncodedSize; // [rsp+34h] [rbp-CCh] BYREF
  char *pBuffer; // [rsp+38h] [rbp-C8h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v22; // [rsp+4Ch] [rbp-B4h]
  __int16 v23; // [rsp+4Eh] [rbp-B2h]
  GUID rguid; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h]
  OLECHAR sz[64]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SerializeToFile", 0x4Bu, a4);
  pBuffer = 0;
  v25 = 0;
  pEncodedSize = 0;
  v7 = 84;
  pHandle = 0;
  NumberOfBytesWritten = 0;
  rguid = 0;
  if ( !hFile )
    goto LABEL_5;
  v22 = 84;
  if ( hFile == (HANDLE)-1LL )
  {
    v7 = 85;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v23 = v7;
    goto LABEL_32;
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
  v11 = InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(
          (__int64)pHandle,
          (void (__fastcall *)(__int64, __int64))&DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Encode,
          a4);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  LastFailureAsHRESULT = v11;
  v9 = v11 < 0;
  v10 = 95;
  if ( v9 )
    goto LABEL_12;
  rguid = stru_180019528;
  v22 = 95;
  LODWORD(v25) = RtlComputeCrc32(0x5EED5EFDu, (PUCHAR)pBuffer, pEncodedSize);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
  {
    v12 = (OLECHAR *)pHandle;
  }
  else
  {
    StringFromGUID2(&rguid, sz, 64);
    v12 = SysAllocString(sz);
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, (_DWORD)v12, v25);
    v4 = 1;
  }
  if ( (v4 & 1) != 0 )
    SysFreeString(v12);
  if ( !WriteFile(hFile, &rguid, 0x18u, &NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = 109;
LABEL_12:
    v23 = v10;
    goto LABEL_30;
  }
  v22 = 109;
  v10 = 111;
  if ( NumberOfBytesWritten != 24 )
    goto LABEL_25;
  LastFailureAsHRESULT = 0;
  v22 = 111;
  if ( !WriteFile(hFile, pBuffer, pEncodedSize, &NumberOfBytesWritten, 0) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = 116;
    goto LABEL_12;
  }
  v22 = 116;
  v10 = 118;
  if ( NumberOfBytesWritten != pEncodedSize )
  {
LABEL_25:
    LastFailureAsHRESULT = -2147418113;
    goto LABEL_12;
  }
  LastFailureAsHRESULT = 0;
  v22 = 118;
LABEL_30:
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
LABEL_32:
  CoTaskMemFree(pBuffer);
  pBuffer = 0;
  v15 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v15;
}

```

## disassembly

```asm
0x180006b50  mov     [rsp-8+arg_8], rbx
0x180006b55  mov     [rsp-8+arg_10], rsi
0x180006b5a  push    rbp
0x180006b5b  push    rdi
0x180006b5c  push    r12
0x180006b5e  lea     rbp, [rsp-30h]
0x180006b63  sub     rsp, 130h
0x180006b6a  mov     rax, cs:__security_cookie
0x180006b71  xor     rax, rsp
0x180006b74  mov     [rbp+40h+var_20], rax
0x180006b78  xor     esi, esi
0x180006b7a  mov     rbx, r9
0x180006b7d  mov     [rsp+140h+NumberOfBytesWritten], esi
0x180006b81  mov     rdi, rcx
0x180006b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b8b  lea     r12, WPP_GLOBAL_Control
0x180006b92  cmp     rcx, r12
0x180006b95  jz      short loc_180006BB3
0x180006b97  test    dword ptr [rcx+1Ch], 20000000h
0x180006b9e  jz      short loc_180006BB3
0x180006ba0  mov     rcx, [rcx+10h]
0x180006ba4  lea     edx, [rsi+0Ch]
0x180006ba7  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x180006bae  call    WPP_SF_
0x180006bb3  mov     r8d, 4Bh ; 'K'; unsigned __int16
0x180006bb9  lea     rdx, aSerializetofil; "SerializeToFile"
0x180006bc0  lea     rcx, [rsp+140h+var_F8]; this
0x180006bc5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180006bca  xor     eax, eax
0x180006bcc  mov     [rsp+140h+pBuffer], rsi
0x180006bd1  mov     [rbp+40h+var_B0], rax
0x180006bd5  xorps   xmm0, xmm0
0x180006bd8  mov     [rsp+140h+pEncodedSize], esi
0x180006bdc  mov     eax, 54h ; 'T'
0x180006be1  mov     [rsp+140h+pHandle], rsi
0x180006be6  mov     [rsp+140h+NumberOfBytesWritten], esi
0x180006bea  movups  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x180006bee  test    rdi, rdi
0x180006bf1  jnz     short loc_180006C05
0x180006bf3  mov     [rsp+140h+var_F8], 80070057h
0x180006bfb  mov     [rsp+140h+var_F2], ax
0x180006c00  jmp     loc_180006E0F
0x180006c05  mov     [rsp+140h+var_F4], ax
0x180006c0a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180006c0e  jnz     short loc_180006C15
0x180006c10  lea     eax, [rdi+56h]
0x180006c13  jmp     short loc_180006BF3
0x180006c15  mov     eax, 57h ; 'W'
0x180006c1a  mov     [rsp+140h+var_F4], ax
0x180006c1f  mov     eax, 58h ; 'X'
0x180006c24  test    rbx, rbx
0x180006c27  jz      short loc_180006BF3
0x180006c29  lea     r8, [rsp+140h+pHandle]; pHandle
0x180006c2e  mov     [rsp+140h+var_F8], esi
0x180006c32  lea     rdx, [rsp+140h+pEncodedSize]; pEncodedSize
0x180006c37  mov     [rsp+140h+var_F4], ax
0x180006c3c  lea     rcx, [rsp+140h+pBuffer]; pBuffer
0x180006c41  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180006c47  test    eax, eax
0x180006c49  jle     short loc_180006C53
0x180006c4b  movzx   eax, ax
0x180006c4e  or      eax, 80070000h
0x180006c53  mov     [rsp+140h+var_F8], eax
0x180006c57  test    eax, eax
0x180006c59  mov     eax, 5Dh ; ']'
0x180006c5e  jns     short loc_180006C6A
0x180006c60  mov     [rsp+140h+var_F2], ax
0x180006c65  jmp     loc_180006DF6
0x180006c6a  mov     rcx, [rsp+140h+pHandle]
0x180006c6f  lea     rdx, DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO_Encode
0x180006c76  mov     r8, rbx
0x180006c79  mov     [rsp+140h+var_F4], ax
0x180006c7e  call    ??$InvokeCoder@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z1@Z; InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x180006c83  test    eax, eax
0x180006c85  jle     short loc_180006C8F
0x180006c87  movzx   eax, ax
0x180006c8a  or      eax, 80070000h
0x180006c8f  mov     [rsp+140h+var_F8], eax
0x180006c93  test    eax, eax
0x180006c95  mov     eax, 5Fh ; '_'
0x180006c9a  js      short loc_180006C60
0x180006c9c  movups  xmm0, xmmword ptr cs:stru_180019528.Data1
0x180006ca3  mov     r8d, [rsp+140h+pEncodedSize]; Length
0x180006ca8  mov     ecx, 5EED5EFDh; InitialCrc
0x180006cad  mov     rdx, [rsp+140h+pBuffer]; Buffer
0x180006cb2  movdqu  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x180006cb7  mov     [rsp+140h+var_F4], ax
0x180006cbc  call    cs:__imp_RtlComputeCrc32
0x180006cc2  mov     dword ptr [rbp+40h+var_B0], eax
0x180006cc5  mov     rax, cs:WPP_GLOBAL_Control
0x180006ccc  cmp     rax, r12
0x180006ccf  jz      short loc_180006D1C
0x180006cd1  test    dword ptr [rax+1Ch], 8000000h
0x180006cd8  jz      short loc_180006D1C
0x180006cda  mov     r8d, 40h ; '@'; cchMax
0x180006ce0  lea     rdx, [rbp+40h+sz]; lpsz
0x180006ce4  lea     rcx, [rbp+40h+rguid]; rguid
0x180006ce8  call    cs:__imp_StringFromGUID2
0x180006cee  lea     rcx, [rbp+40h+sz]; psz
0x180006cf2  call    cs:__imp_SysAllocString
0x180006cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cff  mov     rbx, rax
0x180006d02  mov     eax, dword ptr [rbp+40h+var_B0]
0x180006d05  mov     r9, rbx
0x180006d08  mov     dword ptr [rsp+140h+lpOverlapped], eax
0x180006d0c  mov     rcx, [rcx+10h]
0x180006d10  call    WPP_SF_Sd
0x180006d15  mov     esi, 1
0x180006d1a  jmp     short loc_180006D21
0x180006d1c  mov     rbx, [rsp+140h+pHandle]
0x180006d21  test    sil, 1
0x180006d25  jz      short loc_180006D30
0x180006d27  mov     rcx, rbx; bstrString
0x180006d2a  call    cs:__imp_SysFreeString
0x180006d30  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006d35  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180006d3e  mov     r8d, 18h; nNumberOfBytesToWrite
0x180006d44  lea     rdx, [rbp+40h+rguid]; lpBuffer
0x180006d48  mov     rcx, rdi; hFile
0x180006d4b  call    cs:__imp_WriteFile
0x180006d51  test    eax, eax
0x180006d53  jnz     short loc_180006D68
0x180006d55  call    GetLastFailureAsHRESULT
0x180006d5a  mov     [rsp+140h+var_F8], eax
0x180006d5e  mov     eax, 6Dh ; 'm'
0x180006d63  jmp     loc_180006C60
0x180006d68  cmp     [rsp+140h+NumberOfBytesWritten], 18h
0x180006d6d  mov     eax, 6Dh ; 'm'
0x180006d72  mov     [rsp+140h+var_F4], ax
0x180006d77  mov     eax, 6Fh ; 'o'
0x180006d7c  jz      short loc_180006D8B
0x180006d7e  mov     [rsp+140h+var_F8], 8000FFFFh
0x180006d86  jmp     loc_180006C60
0x180006d8b  mov     r8d, [rsp+140h+pEncodedSize]; nNumberOfBytesToWrite
0x180006d90  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006d95  mov     rdx, [rsp+140h+pBuffer]; lpBuffer
0x180006d9a  mov     rcx, rdi; hFile
0x180006d9d  mov     [rsp+140h+var_F8], 0
0x180006da5  mov     [rsp+140h+var_F4], ax
0x180006daa  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180006db3  call    cs:__imp_WriteFile
0x180006db9  test    eax, eax
0x180006dbb  jnz     short loc_180006DD0
0x180006dbd  call    GetLastFailureAsHRESULT
0x180006dc2  mov     [rsp+140h+var_F8], eax
0x180006dc6  mov     eax, 74h ; 't'
0x180006dcb  jmp     loc_180006C60
0x180006dd0  mov     eax, 74h ; 't'
0x180006dd5  mov     [rsp+140h+var_F4], ax
0x180006dda  mov     eax, [rsp+140h+pEncodedSize]
0x180006dde  cmp     [rsp+140h+NumberOfBytesWritten], eax
0x180006de2  mov     eax, 76h ; 'v'
0x180006de7  jnz     short loc_180006D7E
0x180006de9  mov     [rsp+140h+var_F8], 0
0x180006df1  mov     [rsp+140h+var_F4], ax
0x180006df6  mov     rcx, [rsp+140h+pHandle]; Handle
0x180006dfb  test    rcx, rcx
0x180006dfe  jz      short loc_180006E0F
0x180006e00  call    cs:__imp_MesHandleFree
0x180006e06  mov     [rsp+140h+pHandle], 0
0x180006e0f  mov     rcx, [rsp+140h+pBuffer]; pv
0x180006e14  call    cs:__imp_CoTaskMemFree
0x180006e1a  mov     [rsp+140h+pBuffer], 0
0x180006e23  mov     ebx, [rsp+140h+var_F8]
0x180006e27  lea     rcx, [rsp+140h+var_F8]; this
0x180006e2c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180006e31  mov     eax, ebx
0x180006e33  mov     rcx, [rbp+40h+var_20]
0x180006e37  xor     rcx, rsp; StackCookie
0x180006e3a  call    __security_check_cookie
0x180006e3f  lea     r11, [rsp+140h+var_10]
0x180006e47  mov     rbx, [r11+28h]
0x180006e4b  mov     rsi, [r11+30h]
0x180006e4f  mov     rsp, r11
0x180006e52  pop     r12
0x180006e54  pop     rdi
0x180006e55  pop     rbp
0x180006e56  retn
```
