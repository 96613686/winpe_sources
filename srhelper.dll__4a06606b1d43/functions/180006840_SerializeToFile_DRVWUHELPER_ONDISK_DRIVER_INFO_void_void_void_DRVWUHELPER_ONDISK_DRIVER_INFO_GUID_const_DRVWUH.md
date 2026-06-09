# SerializeToFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_GUID const *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)

- ea: `0x180006840`
- end: `0x180006b47`
- name: `??$SerializeToFile@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@ZPEBU_GUID@@1@Z`
- size: `775`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002054`

## callees

- `0x180003ce0`
- `0x1800067a0`
- `0x180006840`
- `0x180007050`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180006a3b`
- `KERNEL32!WriteFile` at `0x180006aa3`
- `KERNEL32!WriteFile` at `0x180006a3b`
- `KERNEL32!WriteFile` at `0x180006aa3`
- `ntdll!RtlComputeCrc32` at `0x1800069ac`
- `ntdll!RtlComputeCrc32` at `0x1800069ac`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180006931`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x180006931`
- `RPCRT4!MesHandleFree` at `0x180006af0`
- `RPCRT4!MesHandleFree` at `0x180006af0`
- `ole32!StringFromGUID2` at `0x1800069d8`
- `ole32!StringFromGUID2` at `0x1800069d8`
- `ole32!CoTaskMemFree` at `0x180006b04`
- `ole32!CoTaskMemFree` at `0x180006b04`
- `OLEAUT32!__imp_SysAllocString` at `0x1800069e2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800069e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a1a`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_DRVWUHELPER_ONDISK_DRIVER_INFO>(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
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
          (void (__fastcall *)(__int64, __int64))&DRVWUHELPER_ONDISK_DRIVER_INFO_Encode,
          a4);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  LastFailureAsHRESULT = v11;
  v9 = v11 < 0;
  v10 = 95;
  if ( v9 )
    goto LABEL_12;
  rguid = ::rguid;
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
0x180006840  mov     [rsp-8+arg_8], rbx
0x180006845  mov     [rsp-8+arg_10], rsi
0x18000684a  push    rbp
0x18000684b  push    rdi
0x18000684c  push    r12
0x18000684e  lea     rbp, [rsp-30h]
0x180006853  sub     rsp, 130h
0x18000685a  mov     rax, cs:__security_cookie
0x180006861  xor     rax, rsp
0x180006864  mov     [rbp+40h+var_20], rax
0x180006868  xor     esi, esi
0x18000686a  mov     rbx, r9
0x18000686d  mov     [rsp+140h+NumberOfBytesWritten], esi
0x180006871  mov     rdi, rcx
0x180006874  mov     rcx, cs:WPP_GLOBAL_Control
0x18000687b  lea     r12, WPP_GLOBAL_Control
0x180006882  cmp     rcx, r12
0x180006885  jz      short loc_1800068A3
0x180006887  test    dword ptr [rcx+1Ch], 20000000h
0x18000688e  jz      short loc_1800068A3
0x180006890  mov     rcx, [rcx+10h]
0x180006894  lea     edx, [rsi+0Ch]
0x180006897  lea     r8, WPP_2c5669c0156b363454a636adea0dbbf0_Traceguids
0x18000689e  call    WPP_SF_
0x1800068a3  mov     r8d, 4Bh ; 'K'; unsigned __int16
0x1800068a9  lea     rdx, aSerializetofil; "SerializeToFile"
0x1800068b0  lea     rcx, [rsp+140h+var_F8]; this
0x1800068b5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800068ba  xor     eax, eax
0x1800068bc  mov     [rsp+140h+pBuffer], rsi
0x1800068c1  mov     [rbp+40h+var_B0], rax
0x1800068c5  xorps   xmm0, xmm0
0x1800068c8  mov     [rsp+140h+pEncodedSize], esi
0x1800068cc  mov     eax, 54h ; 'T'
0x1800068d1  mov     [rsp+140h+pHandle], rsi
0x1800068d6  mov     [rsp+140h+NumberOfBytesWritten], esi
0x1800068da  movups  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x1800068de  test    rdi, rdi
0x1800068e1  jnz     short loc_1800068F5
0x1800068e3  mov     [rsp+140h+var_F8], 80070057h
0x1800068eb  mov     [rsp+140h+var_F2], ax
0x1800068f0  jmp     loc_180006AFF
0x1800068f5  mov     [rsp+140h+var_F4], ax
0x1800068fa  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800068fe  jnz     short loc_180006905
0x180006900  lea     eax, [rdi+56h]
0x180006903  jmp     short loc_1800068E3
0x180006905  mov     eax, 57h ; 'W'
0x18000690a  mov     [rsp+140h+var_F4], ax
0x18000690f  mov     eax, 58h ; 'X'
0x180006914  test    rbx, rbx
0x180006917  jz      short loc_1800068E3
0x180006919  lea     r8, [rsp+140h+pHandle]; pHandle
0x18000691e  mov     [rsp+140h+var_F8], esi
0x180006922  lea     rdx, [rsp+140h+pEncodedSize]; pEncodedSize
0x180006927  mov     [rsp+140h+var_F4], ax
0x18000692c  lea     rcx, [rsp+140h+pBuffer]; pBuffer
0x180006931  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x180006937  test    eax, eax
0x180006939  jle     short loc_180006943
0x18000693b  movzx   eax, ax
0x18000693e  or      eax, 80070000h
0x180006943  mov     [rsp+140h+var_F8], eax
0x180006947  test    eax, eax
0x180006949  mov     eax, 5Dh ; ']'
0x18000694e  jns     short loc_18000695A
0x180006950  mov     [rsp+140h+var_F2], ax
0x180006955  jmp     loc_180006AE6
0x18000695a  mov     rcx, [rsp+140h+pHandle]
0x18000695f  lea     rdx, DRVWUHELPER_ONDISK_DRIVER_INFO_Encode
0x180006966  mov     r8, rbx
0x180006969  mov     [rsp+140h+var_F4], ax
0x18000696e  call    ??$InvokeCoder@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@@@YAJPEAXP6AX0PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z1@Z; InvokeCoder<_DRVWUHELPER_ONDISK_DRIVER_INFO>(void *,void (*)(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x180006973  test    eax, eax
0x180006975  jle     short loc_18000697F
0x180006977  movzx   eax, ax
0x18000697a  or      eax, 80070000h
0x18000697f  mov     [rsp+140h+var_F8], eax
0x180006983  test    eax, eax
0x180006985  mov     eax, 5Fh ; '_'
0x18000698a  js      short loc_180006950
0x18000698c  movups  xmm0, xmmword ptr cs:rguid.Data1
0x180006993  mov     r8d, [rsp+140h+pEncodedSize]; Length
0x180006998  mov     ecx, 5EED5EFDh; InitialCrc
0x18000699d  mov     rdx, [rsp+140h+pBuffer]; Buffer
0x1800069a2  movdqu  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x1800069a7  mov     [rsp+140h+var_F4], ax
0x1800069ac  call    cs:__imp_RtlComputeCrc32
0x1800069b2  mov     dword ptr [rbp+40h+var_B0], eax
0x1800069b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800069bc  cmp     rax, r12
0x1800069bf  jz      short loc_180006A0C
0x1800069c1  test    dword ptr [rax+1Ch], 8000000h
0x1800069c8  jz      short loc_180006A0C
0x1800069ca  mov     r8d, 40h ; '@'; cchMax
0x1800069d0  lea     rdx, [rbp+40h+sz]; lpsz
0x1800069d4  lea     rcx, [rbp+40h+rguid]; rguid
0x1800069d8  call    cs:__imp_StringFromGUID2
0x1800069de  lea     rcx, [rbp+40h+sz]; psz
0x1800069e2  call    cs:__imp_SysAllocString
0x1800069e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069ef  mov     rbx, rax
0x1800069f2  mov     eax, dword ptr [rbp+40h+var_B0]
0x1800069f5  mov     r9, rbx
0x1800069f8  mov     dword ptr [rsp+140h+lpOverlapped], eax
0x1800069fc  mov     rcx, [rcx+10h]
0x180006a00  call    WPP_SF_Sd
0x180006a05  mov     esi, 1
0x180006a0a  jmp     short loc_180006A11
0x180006a0c  mov     rbx, [rsp+140h+pHandle]
0x180006a11  test    sil, 1
0x180006a15  jz      short loc_180006A20
0x180006a17  mov     rcx, rbx; bstrString
0x180006a1a  call    cs:__imp_SysFreeString
0x180006a20  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006a25  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180006a2e  mov     r8d, 18h; nNumberOfBytesToWrite
0x180006a34  lea     rdx, [rbp+40h+rguid]; lpBuffer
0x180006a38  mov     rcx, rdi; hFile
0x180006a3b  call    cs:__imp_WriteFile
0x180006a41  test    eax, eax
0x180006a43  jnz     short loc_180006A58
0x180006a45  call    GetLastFailureAsHRESULT
0x180006a4a  mov     [rsp+140h+var_F8], eax
0x180006a4e  mov     eax, 6Dh ; 'm'
0x180006a53  jmp     loc_180006950
0x180006a58  cmp     [rsp+140h+NumberOfBytesWritten], 18h
0x180006a5d  mov     eax, 6Dh ; 'm'
0x180006a62  mov     [rsp+140h+var_F4], ax
0x180006a67  mov     eax, 6Fh ; 'o'
0x180006a6c  jz      short loc_180006A7B
0x180006a6e  mov     [rsp+140h+var_F8], 8000FFFFh
0x180006a76  jmp     loc_180006950
0x180006a7b  mov     r8d, [rsp+140h+pEncodedSize]; nNumberOfBytesToWrite
0x180006a80  lea     r9, [rsp+140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006a85  mov     rdx, [rsp+140h+pBuffer]; lpBuffer
0x180006a8a  mov     rcx, rdi; hFile
0x180006a8d  mov     [rsp+140h+var_F8], 0
0x180006a95  mov     [rsp+140h+var_F4], ax
0x180006a9a  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180006aa3  call    cs:__imp_WriteFile
0x180006aa9  test    eax, eax
0x180006aab  jnz     short loc_180006AC0
0x180006aad  call    GetLastFailureAsHRESULT
0x180006ab2  mov     [rsp+140h+var_F8], eax
0x180006ab6  mov     eax, 74h ; 't'
0x180006abb  jmp     loc_180006950
0x180006ac0  mov     eax, 74h ; 't'
0x180006ac5  mov     [rsp+140h+var_F4], ax
0x180006aca  mov     eax, [rsp+140h+pEncodedSize]
0x180006ace  cmp     [rsp+140h+NumberOfBytesWritten], eax
0x180006ad2  mov     eax, 76h ; 'v'
0x180006ad7  jnz     short loc_180006A6E
0x180006ad9  mov     [rsp+140h+var_F8], 0
0x180006ae1  mov     [rsp+140h+var_F4], ax
0x180006ae6  mov     rcx, [rsp+140h+pHandle]; Handle
0x180006aeb  test    rcx, rcx
0x180006aee  jz      short loc_180006AFF
0x180006af0  call    cs:__imp_MesHandleFree
0x180006af6  mov     [rsp+140h+pHandle], 0
0x180006aff  mov     rcx, [rsp+140h+pBuffer]; pv
0x180006b04  call    cs:__imp_CoTaskMemFree
0x180006b0a  mov     [rsp+140h+pBuffer], 0
0x180006b13  mov     ebx, [rsp+140h+var_F8]
0x180006b17  lea     rcx, [rsp+140h+var_F8]; this
0x180006b1c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180006b21  mov     eax, ebx
0x180006b23  mov     rcx, [rbp+40h+var_20]
0x180006b27  xor     rcx, rsp; StackCookie
0x180006b2a  call    __security_check_cookie
0x180006b2f  lea     r11, [rsp+140h+var_10]
0x180006b37  mov     rbx, [r11+28h]
0x180006b3b  mov     rsi, [r11+30h]
0x180006b3f  mov     rsp, r11
0x180006b42  pop     r12
0x180006b44  pop     rdi
0x180006b45  pop     rbp
0x180006b46  retn
```
