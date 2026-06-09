# QueryServiceConfig2W

- ea: `0x18000e4e0`
- end: `0x18000e998`
- name: `QueryServiceConfig2W`
- size: `1208`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwInfoLevel, LPBYTE lpBuffer, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000e4e0`
- `0x18000e9a0`
- `0x18000f048`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e69c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e69c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e6c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e887`
- `RPCRT4!NdrClientCall2` at `0x18000e5e7`
- `RPCRT4!NdrClientCall2` at `0x18000e5e7`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe1e`

## pseudocode

```c
BOOL __stdcall QueryServiceConfig2W(
        SC_HANDLE hService,
        DWORD dwInfoLevel,
        LPBYTE lpBuffer,
        DWORD cbBufSize,
        LPDWORD pcbBytesNeeded)
{
  BYTE *v8; // rdi
  DWORD v9; // r14d
  LPBYTE v10; // r15
  CLIENT_CALL_RETURN v11; // rbx
  __int64 v12; // rcx
  BOOL result; // eax
  BYTE *v14; // rcx
  BYTE *v15; // rdx
  bool v16; // cf
  __int64 v17; // rax
  BYTE *v18; // rdx
  __int64 v19; // rax
  BYTE *v20; // rcx
  __int64 v21; // rax
  BYTE *v22; // r8
  int v23; // [rsp+64h] [rbp-B4h]
  char v24; // [rsp+68h] [rbp-B0h] BYREF
  LPBYTE v25; // [rsp+70h] [rbp-A8h]
  int v26; // [rsp+78h] [rbp-A0h] BYREF
  int v27; // [rsp+7Ch] [rbp-9Ch] BYREF
  int v28; // [rsp+80h] [rbp-98h] BYREF
  int v29; // [rsp+84h] [rbp-94h] BYREF
  int v30; // [rsp+88h] [rbp-90h] BYREF
  _DWORD v31[3]; // [rsp+8Ch] [rbp-8Ch] BYREF
  __int64 v32; // [rsp+98h] [rbp-80h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-78h] BYREF
  CLIENT_CALL_RETURN v34; // [rsp+A8h] [rbp-70h]
  _BYTE v35[32]; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-48h]

  v8 = 0;
  v33 = 0;
  memset(v35, 0, sizeof(v35));
  v36 = 0;
  v23 = 0;
  v31[0] = 0;
  v26 = 0;
  v27 = 0;
  v32 = 0;
  v28 = 0;
  v29 = 0;
  v24 = 0;
  v30 = 0;
  v9 = cbBufSize;
  v10 = lpBuffer;
  v25 = lpBuffer;
  if ( dwInfoLevel == 3 )
  {
    if ( lpBuffer && cbBufSize >= 4 )
      goto LABEL_11;
    v10 = (LPBYTE)v31;
LABEL_5:
    v9 = 4;
LABEL_9:
    v23 = 1;
LABEL_10:
    v25 = v10;
LABEL_11:
    v34.Simple = 0;
    v11.Pointer = NdrClientCall2(&pStubDescriptor, &byte_1800609F8, hService, dwInfoLevel, v10, v9, pcbBytesNeeded).Pointer;
    v34.Pointer = v11.Pointer;
    v31[1] = v11.Pointer;
    if ( ((dwInfoLevel - 1) & 0xFFFFFFFA) == 0
      && dwInfoLevel != 5
      && (!LODWORD(v11.Pointer) || LODWORD(v11.Pointer) == 122) )
    {
      if ( dwInfoLevel == 1 )
      {
        v12 = 7;
      }
      else if ( dwInfoLevel == 2 )
      {
        v12 = 9;
      }
      else
      {
        v12 = 13;
        if ( dwInfoLevel == 6 )
          v12 = 12;
      }
      if ( !(unsigned int)ScConvertOffsets64(v12, 0, 0, 0, v10, v9, pcbBytesNeeded, 0, 0, 0, 0) )
      {
        LODWORD(v11.Pointer) = 122;
LABEL_18:
        SetLastError((DWORD)v11.Pointer);
        return 0;
      }
    }
    if ( LODWORD(v11.Pointer) )
      goto LABEL_18;
    if ( v23 )
    {
      SetLastError(0x7Au);
      return 0;
    }
    switch ( dwInfoLevel )
    {
      case 1u:
        if ( !*(_QWORD *)lpBuffer )
          return 1;
        v14 = &lpBuffer[(unsigned int)*(_QWORD *)lpBuffer];
        *(_QWORD *)lpBuffer = v14;
        if ( !v14 || v14 < &lpBuffer[cbBufSize] && v14 >= lpBuffer )
          return 1;
        break;
      case 2u:
        v17 = *((_QWORD *)lpBuffer + 1);
        if ( v17 )
        {
          v18 = &lpBuffer[(unsigned int)v17];
          *((_QWORD *)lpBuffer + 1) = v18;
        }
        else
        {
          v18 = 0;
        }
        v19 = *((_QWORD *)lpBuffer + 2);
        if ( v19 )
        {
          v20 = &lpBuffer[(unsigned int)v19];
          *((_QWORD *)lpBuffer + 2) = v20;
        }
        else
        {
          v20 = 0;
        }
        v21 = *((_QWORD *)lpBuffer + 4);
        if ( v21 )
        {
          v8 = &lpBuffer[(unsigned int)v21];
          *((_QWORD *)lpBuffer + 4) = v8;
        }
        v22 = &lpBuffer[cbBufSize];
        if ( v18 && (v18 >= v22 || v18 < lpBuffer) || v20 && (v20 >= v22 || v20 < lpBuffer) )
          break;
        if ( !v8 )
          return 1;
        if ( v8 >= v22 )
          break;
        v16 = v8 < lpBuffer;
        goto LABEL_70;
      case 6u:
        if ( !*(_QWORD *)lpBuffer )
          return 1;
        v15 = &lpBuffer[(unsigned int)*(_QWORD *)lpBuffer];
        *(_QWORD *)lpBuffer = v15;
        if ( !v15 )
          return 1;
        if ( v15 < &lpBuffer[cbBufSize] )
        {
          v16 = v15 < lpBuffer;
LABEL_70:
          if ( !v16 )
            return 1;
        }
        break;
      default:
        return 1;
    }
    SetLastError(0xDu);
    return 0;
  }
  if ( dwInfoLevel == 1 )
  {
    if ( lpBuffer && cbBufSize >= 8 )
      goto LABEL_11;
    v10 = (LPBYTE)&v33;
    v9 = 8;
    goto LABEL_9;
  }
  switch ( dwInfoLevel )
  {
    case 2u:
      if ( lpBuffer && cbBufSize >= 0x28 )
        goto LABEL_11;
      v10 = v35;
      v9 = 40;
      goto LABEL_9;
    case 4u:
      if ( lpBuffer && cbBufSize >= 4 )
        goto LABEL_11;
      v10 = (LPBYTE)&v26;
      goto LABEL_5;
    case 5u:
      if ( lpBuffer && cbBufSize >= 4 )
        goto LABEL_11;
      v10 = (LPBYTE)&v27;
      goto LABEL_5;
    case 6u:
      if ( lpBuffer && cbBufSize >= 8 )
        goto LABEL_11;
      v10 = (LPBYTE)&v32;
      v9 = 8;
      goto LABEL_9;
    case 7u:
      if ( lpBuffer && cbBufSize >= 4 )
        goto LABEL_11;
      v10 = (LPBYTE)&v28;
      goto LABEL_5;
    case 8u:
      result = ScQueryServiceConfigEx(hService, dwInfoLevel, lpBuffer, cbBufSize, pcbBytesNeeded);
      break;
    case 9u:
      if ( lpBuffer && cbBufSize >= 4 )
        goto LABEL_11;
      v10 = (LPBYTE)&v29;
      goto LABEL_5;
    case 0xBu:
      if ( lpBuffer && cbBufSize )
        goto LABEL_11;
      v10 = (LPBYTE)&v24;
      v9 = 1;
      v23 = 1;
      goto LABEL_10;
    case 0xCu:
      if ( lpBuffer && cbBufSize >= 4 )
        goto LABEL_11;
      v10 = (LPBYTE)&v30;
      goto LABEL_5;
    default:
      SetLastError(0x7Cu);
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18000e4e0  mov     r11, rsp
0x18000e4e3  mov     [r11+20h], r9d
0x18000e4e7  mov     [r11+18h], r8
0x18000e4eb  mov     [rsp+arg_8], edx
0x18000e4ef  push    rbx
0x18000e4f0  push    rsi
0x18000e4f1  push    rdi
0x18000e4f2  push    r12
0x18000e4f4  push    r13
0x18000e4f6  push    r14
0x18000e4f8  push    r15
0x18000e4fa  sub     rsp, 0E0h
0x18000e501  mov     r13d, r9d
0x18000e504  mov     r12, r8
0x18000e507  mov     esi, edx
0x18000e509  xor     edi, edi
0x18000e50b  mov     [r11-78h], rdi
0x18000e50f  xorps   xmm0, xmm0
0x18000e512  xor     eax, eax
0x18000e514  movups  xmmword ptr [r11-68h], xmm0
0x18000e519  movups  xmmword ptr [r11-58h], xmm0
0x18000e51e  mov     [r11-48h], rax
0x18000e522  mov     [rsp+118h+var_B4], edi
0x18000e526  mov     [rsp+118h+var_8C], edi
0x18000e52d  mov     [rsp+118h+var_A0], edi
0x18000e531  mov     [rsp+118h+var_9C], edi
0x18000e535  mov     [r11-80h], rdi
0x18000e539  mov     [rsp+118h+var_98], edi
0x18000e540  mov     [rsp+118h+var_94], edi
0x18000e547  mov     [rsp+118h+var_B0], al
0x18000e54b  mov     [rsp+118h+var_90], edi
0x18000e552  mov     r14d, r9d
0x18000e555  mov     [rsp+118h+var_B8], r9d
0x18000e55a  mov     r15, r8
0x18000e55d  mov     [rsp+118h+var_A8], r8
0x18000e562  cmp     edx, 3
0x18000e565  jnz     short loc_18000E582
0x18000e567  test    r8, r8
0x18000e56a  jz      short loc_18000E572
0x18000e56c  cmp     r9d, 4
0x18000e570  jnb     short loc_18000E5B4
0x18000e572  lea     r15, [rsp+118h+var_8C]
0x18000e57a  mov     r14d, 4
0x18000e580  jmp     short loc_18000E5A2
0x18000e582  cmp     esi, 1
0x18000e585  jnz     loc_18000E73B
0x18000e58b  test    r8, r8
0x18000e58e  jnz     loc_18000E72C
0x18000e594  lea     r15, [rsp+118h+var_78]
0x18000e59c  mov     r14d, 8
0x18000e5a2  mov     [rsp+118h+var_B4], 1
0x18000e5aa  mov     [rsp+118h+var_B8], r14d
0x18000e5af  mov     [rsp+118h+var_A8], r15
0x18000e5b4  mov     [rsp+118h+var_70], rdi
0x18000e5bc  mov     rax, [rsp+118h+pcbBytesNeeded]
0x18000e5c4  mov     [rsp+118h+var_E8], rax
0x18000e5c9  mov     [rsp+118h+var_F0], r14d
0x18000e5ce  mov     [rsp+118h+var_F8], r15
0x18000e5d3  mov     r9d, esi
0x18000e5d6  mov     r8, rcx
0x18000e5d9  lea     rdx, byte_1800609F8; pFormat
0x18000e5e0  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000e5e7  call    cs:__imp_NdrClientCall2
0x18000e5ed  mov     rbx, rax
0x18000e5f0  mov     [rsp+118h+var_70], rax
0x18000e5f8  mov     [rsp+118h+var_88], eax
0x18000e5ff  jmp     short loc_18000E634
0x18000e601  mov     ecx, eax; unsigned int
0x18000e603  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000e608  mov     ebx, eax
0x18000e60a  mov     [rsp+118h+var_88], eax
0x18000e611  xor     edi, edi
0x18000e613  mov     r13d, [rsp+118h+arg_18]
0x18000e61b  mov     r12, [rsp+118h+arg_10]
0x18000e623  mov     esi, [rsp+118h+arg_8]
0x18000e62a  mov     r15, [rsp+118h+var_A8]
0x18000e62f  mov     r14d, [rsp+118h+var_B8]
0x18000e634  lea     eax, [rsi-1]
0x18000e637  test    eax, 0FFFFFFFAh
0x18000e63c  jnz     short loc_18000E6B7
0x18000e63e  cmp     esi, 5
0x18000e641  jz      short loc_18000E6B7
0x18000e643  test    ebx, ebx
0x18000e645  jnz     loc_18000E721
0x18000e64b  cmp     esi, 1
0x18000e64e  jnz     loc_18000E773
0x18000e654  mov     ecx, 7
0x18000e659  mov     [rsp+118h+var_C8], rdi
0x18000e65e  mov     [rsp+118h+var_D0], rdi
0x18000e663  mov     [rsp+118h+var_D8], rdi
0x18000e668  mov     [rsp+118h+var_E0], rdi
0x18000e66d  mov     rax, [rsp+118h+pcbBytesNeeded]
0x18000e675  mov     [rsp+118h+var_E8], rax
0x18000e67a  mov     [rsp+118h+var_F0], r14d
0x18000e67f  mov     [rsp+118h+var_F8], r15
0x18000e684  xor     r9d, r9d
0x18000e687  xor     r8d, r8d
0x18000e68a  xor     edx, edx
0x18000e68c  call    ?ScConvertOffsets64@@YAHW4SC_API_NUMBER@@PEAUSC_HANDLE__@@KKPEAEKPEAK33PEAX3@Z; ScConvertOffsets64(SC_API_NUMBER,SC_HANDLE__ *,ulong,ulong,uchar *,ulong,ulong *,ulong *,ulong *,void *,ulong *)
0x18000e691  test    eax, eax
0x18000e693  jnz     short loc_18000E6B7
0x18000e695  mov     ebx, 7Ah ; 'z'
0x18000e69a  mov     ecx, ebx; dwErrCode
0x18000e69c  call    cs:__imp_SetLastError
0x18000e6a2  xor     eax, eax
0x18000e6a4  add     rsp, 0E0h
0x18000e6ab  pop     r15
0x18000e6ad  pop     r14
0x18000e6af  pop     r13
0x18000e6b1  pop     r12
0x18000e6b3  pop     rdi
0x18000e6b4  pop     rsi
0x18000e6b5  pop     rbx
0x18000e6b6  retn
0x18000e6b7  test    ebx, ebx
0x18000e6b9  jnz     short loc_18000E69A
0x18000e6bb  cmp     [rsp+118h+var_B4], ebx
0x18000e6bf  jz      short loc_18000E6D0
0x18000e6c1  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000e6c6  call    cs:__imp_SetLastError
0x18000e6cc  xor     eax, eax
0x18000e6ce  jmp     short loc_18000E6A4
0x18000e6d0  cmp     esi, 1
0x18000e6d3  jz      short loc_18000E6EE
0x18000e6d5  cmp     esi, 2
0x18000e6d8  jz      loc_18000E8D7
0x18000e6de  cmp     esi, 6
0x18000e6e1  jz      loc_18000E89E
0x18000e6e7  mov     eax, 1
0x18000e6ec  jmp     short loc_18000E6A4
0x18000e6ee  mov     rax, [r12]
0x18000e6f2  test    rax, rax
0x18000e6f5  jz      short loc_18000E6E7
0x18000e6f7  mov     ecx, eax
0x18000e6f9  add     rcx, r12
0x18000e6fc  mov     [r12], rcx
0x18000e700  jz      short loc_18000E6E7
0x18000e702  mov     edx, r13d
0x18000e705  add     rdx, r12
0x18000e708  cmp     rcx, rdx
0x18000e70b  jnb     short loc_18000E712
0x18000e70d  cmp     rcx, r12
0x18000e710  jnb     short loc_18000E6E7
0x18000e712  mov     ecx, 0Dh; dwErrCode
0x18000e717  call    cs:__imp_SetLastError
0x18000e71d  xor     eax, eax
0x18000e71f  jmp     short loc_18000E6A4
0x18000e721  cmp     ebx, 7Ah ; 'z'
0x18000e724  jz      loc_18000E64B
0x18000e72a  jmp     short loc_18000E6B7
0x18000e72c  cmp     r9d, 8
0x18000e730  jnb     loc_18000E5B4
0x18000e736  jmp     loc_18000E594
0x18000e73b  lea     eax, [rdx-2]; switch 11 cases
0x18000e73e  cmp     eax, 0Ah
0x18000e741  ja      def_18000E758; jumptable 000000018000E758 default case, cases 3,10
0x18000e747  lea     rdx, __ImageBase
0x18000e74e  mov     eax, ds:(jpt_18000E758 - 180000000h)[rdx+rax*4]
0x18000e755  add     rax, rdx
0x18000e758  jmp     rax; switch jump
0x18000e75a  mov     rax, [rsp+118h+pcbBytesNeeded]; jumptable 000000018000E758 case 8
0x18000e762  mov     [rsp+118h+var_F8], rax; unsigned int *
0x18000e767  mov     edx, esi; unsigned int
0x18000e769  call    ?ScQueryServiceConfigEx@@YAHPEAUSC_HANDLE__@@KPEAEKPEAK@Z; ScQueryServiceConfigEx(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x18000e76e  jmp     loc_18000E6A4
0x18000e773  cmp     esi, 2
0x18000e776  jz      loc_18000E894
0x18000e77c  mov     ecx, 0Dh
0x18000e781  cmp     esi, 6
0x18000e784  jnz     loc_18000E659
0x18000e78a  mov     ecx, 0Ch
0x18000e78f  jmp     loc_18000E659
0x18000e794  test    r8, r8; jumptable 000000018000E758 case 2
0x18000e797  jz      short loc_18000E7A3
0x18000e799  cmp     r9d, 28h ; '('
0x18000e79d  jnb     loc_18000E5B4
0x18000e7a3  lea     r15, [rsp+118h+var_68]
0x18000e7ab  mov     r14d, 28h ; '('
0x18000e7b1  jmp     loc_18000E5A2
0x18000e7b6  test    r8, r8; jumptable 000000018000E758 case 4
0x18000e7b9  jz      short loc_18000E7C5
0x18000e7bb  cmp     r9d, 4
0x18000e7bf  jnb     loc_18000E5B4
0x18000e7c5  lea     r15, [rsp+118h+var_A0]
0x18000e7ca  jmp     loc_18000E57A
0x18000e7cf  test    r8, r8; jumptable 000000018000E758 case 5
0x18000e7d2  jz      short loc_18000E7DE
0x18000e7d4  cmp     r9d, 4
0x18000e7d8  jnb     loc_18000E5B4
0x18000e7de  lea     r15, [rsp+118h+var_9C]
0x18000e7e3  jmp     loc_18000E57A
0x18000e7e8  test    r8, r8; jumptable 000000018000E758 case 7
0x18000e7eb  jz      short loc_18000E7F7
0x18000e7ed  cmp     r9d, 4
0x18000e7f1  jnb     loc_18000E5B4
0x18000e7f7  lea     r15, [rsp+118h+var_98]
0x18000e7ff  jmp     loc_18000E57A
0x18000e804  test    r8, r8; jumptable 000000018000E758 case 6
0x18000e807  jz      short loc_18000E813
0x18000e809  cmp     r9d, 8
0x18000e80d  jnb     loc_18000E5B4
0x18000e813  lea     r15, [rsp+118h+var_80]
0x18000e81b  mov     r14d, 8
0x18000e821  jmp     loc_18000E5A2
0x18000e826  test    r8, r8; jumptable 000000018000E758 case 9
0x18000e829  jz      short loc_18000E835
0x18000e82b  cmp     r9d, 4
0x18000e82f  jnb     loc_18000E5B4
0x18000e835  lea     r15, [rsp+118h+var_94]
0x18000e83d  jmp     loc_18000E57A
0x18000e842  test    r8, r8; jumptable 000000018000E758 case 11
0x18000e845  jz      short loc_18000E851
0x18000e847  cmp     r9d, 1
0x18000e84b  jnb     loc_18000E5B4
0x18000e851  lea     r15, [rsp+118h+var_B0]
0x18000e856  mov     r14d, 1
0x18000e85c  mov     [rsp+118h+var_B4], r14d
0x18000e861  jmp     loc_18000E5AA
0x18000e866  test    r8, r8; jumptable 000000018000E758 case 12
0x18000e869  jz      short loc_18000E875
0x18000e86b  cmp     r9d, 4
0x18000e86f  jnb     loc_18000E5B4
0x18000e875  lea     r15, [rsp+118h+var_90]
0x18000e87d  jmp     loc_18000E57A
0x18000e882  mov     ecx, 7Ch ; '|'; jumptable 000000018000E758 default case, cases 3,10
0x18000e887  call    cs:__imp_SetLastError
0x18000e88d  xor     eax, eax
0x18000e88f  jmp     loc_18000E6A4
0x18000e894  mov     ecx, 9
0x18000e899  jmp     loc_18000E659
0x18000e89e  mov     rax, [r12]
0x18000e8a2  test    rax, rax
0x18000e8a5  jz      loc_18000E6E7
0x18000e8ab  mov     edx, eax
0x18000e8ad  add     rdx, r12
0x18000e8b0  mov     [r12], rdx
0x18000e8b4  jz      loc_18000E6E7
0x18000e8ba  mov     ecx, r13d
0x18000e8bd  add     rcx, r12
0x18000e8c0  cmp     rdx, rcx
0x18000e8c3  jnb     loc_18000E712
0x18000e8c9  cmp     rdx, r12
0x18000e8cc  jb      loc_18000E712
0x18000e8d2  jmp     loc_18000E6E7
0x18000e8d7  mov     rax, [r12+8]
0x18000e8dc  test    rax, rax
0x18000e8df  jz      short loc_18000E8ED
0x18000e8e1  mov     edx, eax
0x18000e8e3  add     rdx, r12
0x18000e8e6  mov     [r12+8], rdx
0x18000e8eb  jmp     short loc_18000E8F0
0x18000e8ed  mov     rdx, rdi
0x18000e8f0  mov     rax, [r12+10h]
0x18000e8f5  test    rax, rax
0x18000e8f8  jz      short loc_18000E906
0x18000e8fa  mov     ecx, eax
0x18000e8fc  add     rcx, r12
0x18000e8ff  mov     [r12+10h], rcx
0x18000e904  jmp     short loc_18000E909
0x18000e906  mov     rcx, rdi
0x18000e909  mov     rax, [r12+20h]
0x18000e90e  test    rax, rax
0x18000e911  jz      short loc_18000E91D
0x18000e913  mov     edi, eax
0x18000e915  add     rdi, r12
0x18000e918  mov     [r12+20h], rdi
0x18000e91d  mov     r8d, r13d
0x18000e920  add     r8, r12
0x18000e923  test    rdx, rdx
0x18000e926  jz      short loc_18000E93A
0x18000e928  cmp     rdx, r8
0x18000e92b  jnb     loc_18000E712
0x18000e931  cmp     rdx, r12
0x18000e934  jb      loc_18000E712
0x18000e93a  test    rcx, rcx
0x18000e93d  jz      short loc_18000E951
0x18000e93f  cmp     rcx, r8
0x18000e942  jnb     loc_18000E712
0x18000e948  cmp     rcx, r12
0x18000e94b  jb      loc_18000E712
0x18000e951  test    rdi, rdi
0x18000e954  jz      loc_18000E6E7
0x18000e95a  cmp     rdi, r8
0x18000e95d  jnb     loc_18000E712
0x18000e963  cmp     rdi, r12
0x18000e966  jmp     loc_18000E8CC
0x18004fe10  push    rbp
0x18004fe12  sub     rsp, 60h
0x18004fe16  mov     rbp, rdx
0x18004fe19  mov     rcx, [rcx]
0x18004fe1c  mov     ecx, [rcx]; ExceptionCode
0x18004fe1e  call    cs:__imp_I_RpcExceptionFilter
0x18004fe24  nop
0x18004fe25  add     rsp, 60h
0x18004fe29  pop     rbp
0x18004fe2a  retn
```
