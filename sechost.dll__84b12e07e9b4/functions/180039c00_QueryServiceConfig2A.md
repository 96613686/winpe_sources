# QueryServiceConfig2A

- ea: `0x180039c00`
- end: `0x18003a059`
- name: `QueryServiceConfig2A`
- size: `1113`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwInfoLevel, LPBYTE lpBuffer, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000e9a0`
- `0x18000f048`
- `0x180039c00`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039d88`
- `RPCRT4!NdrClientCall2` at `0x180039e5b`
- `RPCRT4!NdrClientCall2` at `0x180039e5b`

## pseudocode

```c
BOOL __stdcall QueryServiceConfig2A(
        SC_HANDLE hService,
        DWORD dwInfoLevel,
        LPBYTE lpBuffer,
        DWORD cbBufSize,
        LPDWORD pcbBytesNeeded)
{
  int v7; // r12d
  DWORD v8; // r14d
  LPBYTE v9; // r15
  DWORD v10; // ecx
  CLIENT_CALL_RETURN v12; // rax
  int Pointer; // ebx
  DWORD v14; // ecx
  unsigned int v15; // eax
  DWORD v16; // ecx
  DWORD v17; // ecx
  __int64 v18; // rdx
  bool v19; // zf
  BYTE *v20; // rdx
  bool v21; // cf
  BYTE *v22; // r8
  BYTE *v23; // rdx
  BYTE *v24; // rcx
  BYTE *v25; // r9
  __int64 v26; // r8
  BYTE *v27; // r8
  char v28; // [rsp+68h] [rbp-B0h] BYREF
  LPBYTE v29; // [rsp+70h] [rbp-A8h]
  int v30; // [rsp+78h] [rbp-A0h] BYREF
  int v31; // [rsp+7Ch] [rbp-9Ch] BYREF
  int v32; // [rsp+80h] [rbp-98h] BYREF
  int v33; // [rsp+84h] [rbp-94h] BYREF
  int v34; // [rsp+88h] [rbp-90h] BYREF
  _DWORD v35[3]; // [rsp+8Ch] [rbp-8Ch] BYREF
  __int64 v36; // [rsp+98h] [rbp-80h] BYREF
  __int64 v37; // [rsp+A0h] [rbp-78h] BYREF
  CLIENT_CALL_RETURN v38; // [rsp+A8h] [rbp-70h]
  _BYTE v39[32]; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-48h]

  v36 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  v7 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v37 = 0;
  v35[0] = 0;
  v34 = 0;
  v28 = 0;
  v33 = 0;
  v8 = cbBufSize;
  v9 = lpBuffer;
  v29 = lpBuffer;
  if ( dwInfoLevel > 6 )
  {
    switch ( dwInfoLevel )
    {
      case 7u:
        if ( !lpBuffer || cbBufSize < 4 )
        {
          v9 = (LPBYTE)v35;
          goto LABEL_46;
        }
        goto LABEL_49;
      case 8u:
        return ScQueryServiceConfigEx(hService, 8u, lpBuffer, cbBufSize, pcbBytesNeeded);
      case 9u:
        if ( !lpBuffer || cbBufSize < 4 )
        {
          v9 = (LPBYTE)&v34;
          goto LABEL_46;
        }
        goto LABEL_49;
      case 0xBu:
        if ( !lpBuffer || !cbBufSize )
        {
          v9 = (LPBYTE)&v28;
          v8 = 1;
          v7 = 1;
LABEL_48:
          v29 = v9;
          goto LABEL_49;
        }
        goto LABEL_49;
      case 0xCu:
        if ( !lpBuffer || cbBufSize < 4 )
        {
          v9 = (LPBYTE)&v33;
          goto LABEL_46;
        }
        goto LABEL_49;
    }
    goto LABEL_31;
  }
  switch ( dwInfoLevel )
  {
    case 6u:
      if ( lpBuffer && cbBufSize >= 8 )
        goto LABEL_49;
      v9 = (LPBYTE)&v37;
      v8 = 8;
LABEL_47:
      v7 = 1;
      goto LABEL_48;
    case 1u:
      if ( !lpBuffer || cbBufSize < 4 )
      {
        v9 = (LPBYTE)&v36;
        goto LABEL_46;
      }
      goto LABEL_49;
    case 2u:
      if ( lpBuffer && cbBufSize >= 0x14 )
        goto LABEL_49;
      v9 = v39;
      v8 = 20;
      goto LABEL_47;
    case 3u:
      if ( !lpBuffer || cbBufSize < 4 )
      {
        v9 = (LPBYTE)&v32;
        goto LABEL_46;
      }
      goto LABEL_49;
  }
  if ( dwInfoLevel != 4 )
  {
    if ( dwInfoLevel == 5 )
    {
      if ( !lpBuffer || cbBufSize < 4 )
      {
        v9 = (LPBYTE)&v30;
LABEL_46:
        v8 = 4;
        goto LABEL_47;
      }
      goto LABEL_49;
    }
LABEL_31:
    v10 = 124;
LABEL_32:
    SetLastError(v10);
    return 0;
  }
  if ( !lpBuffer || cbBufSize < 4 )
  {
    v9 = (LPBYTE)&v31;
    goto LABEL_46;
  }
LABEL_49:
  v38.Simple = 0;
  v12.Pointer = NdrClientCall2(&pStubDescriptor, &byte_1800609B4, hService, dwInfoLevel, v9, v8, pcbBytesNeeded).Pointer;
  Pointer = (int)v12.Pointer;
  v38.Pointer = v12.Pointer;
  v35[1] = v12.Pointer;
  v14 = dwInfoLevel;
  if ( ((dwInfoLevel - 1) & 0xFFFFFFFA) == 0
    && dwInfoLevel != 5
    && (!LODWORD(v12.Pointer) || LODWORD(v12.Pointer) == 122) )
  {
    v15 = 13;
    switch ( dwInfoLevel )
    {
      case 1u:
        v15 = 8;
        break;
      case 2u:
        v15 = 10;
        break;
      case 6u:
        v15 = 11;
        break;
    }
    if ( !(unsigned int)ScConvertOffsets64(v15, 0, 0, 0, v9, v8, pcbBytesNeeded, 0, 0, 0, 0) )
      Pointer = 122;
    v14 = dwInfoLevel;
  }
  if ( Pointer )
  {
    v10 = Pointer;
    goto LABEL_32;
  }
  if ( v7 )
  {
    v10 = 122;
    goto LABEL_32;
  }
  v16 = v14 - 1;
  if ( !v16 )
  {
    if ( !*(_QWORD *)lpBuffer )
      return 1;
    v26 = *(unsigned int *)lpBuffer;
    v19 = &lpBuffer[v26] == 0;
    v27 = &lpBuffer[v26];
    *(_QWORD *)lpBuffer = v27;
    if ( v19 || v27 < &lpBuffer[cbBufSize] && v27 >= lpBuffer )
      return 1;
    goto LABEL_97;
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 != 4 )
      return 1;
    if ( !*(_QWORD *)lpBuffer )
      return 1;
    v18 = *(unsigned int *)lpBuffer;
    v19 = &lpBuffer[v18] == 0;
    v20 = &lpBuffer[v18];
    *(_QWORD *)lpBuffer = v20;
    if ( v19 )
      return 1;
    if ( v20 >= &lpBuffer[cbBufSize] )
      goto LABEL_97;
    v21 = v20 < lpBuffer;
LABEL_91:
    if ( !v21 )
      return 1;
LABEL_97:
    v10 = 13;
    goto LABEL_32;
  }
  if ( *((_QWORD *)lpBuffer + 1) )
  {
    v22 = &lpBuffer[*((unsigned int *)lpBuffer + 2)];
    *((_QWORD *)lpBuffer + 1) = v22;
  }
  else
  {
    v22 = 0;
  }
  if ( *((_QWORD *)lpBuffer + 2) )
  {
    v23 = &lpBuffer[*((unsigned int *)lpBuffer + 4)];
    *((_QWORD *)lpBuffer + 2) = v23;
  }
  else
  {
    v23 = 0;
  }
  if ( *((_QWORD *)lpBuffer + 4) )
  {
    v24 = &lpBuffer[*((unsigned int *)lpBuffer + 8)];
    *((_QWORD *)lpBuffer + 4) = v24;
  }
  else
  {
    v24 = 0;
  }
  v25 = &lpBuffer[cbBufSize];
  if ( v22 && (v22 >= v25 || v22 < lpBuffer) || v23 && (v23 >= v25 || v23 < lpBuffer) )
    goto LABEL_97;
  if ( v24 )
  {
    if ( v24 >= v25 )
      goto LABEL_97;
    v21 = v24 < lpBuffer;
    goto LABEL_91;
  }
  return 1;
}

```

## disassembly

```asm
0x180039c00  mov     r11, rsp
0x180039c03  mov     [r11+20h], r9d
0x180039c07  mov     [r11+18h], r8
0x180039c0b  mov     [rsp+arg_8], edx
0x180039c0f  push    rbx
0x180039c10  push    rsi
0x180039c11  push    rdi
0x180039c12  push    r12
0x180039c14  push    r13
0x180039c16  push    r14
0x180039c18  push    r15
0x180039c1a  sub     rsp, 0E0h
0x180039c21  mov     r13d, r9d
0x180039c24  mov     rdi, r8
0x180039c27  xor     esi, esi
0x180039c29  mov     [r11-80h], rsi
0x180039c2d  xorps   xmm0, xmm0
0x180039c30  xor     eax, eax
0x180039c32  movups  xmmword ptr [r11-68h], xmm0
0x180039c37  movups  xmmword ptr [r11-58h], xmm0
0x180039c3c  mov     [r11-48h], rax
0x180039c40  mov     r12d, esi
0x180039c43  mov     [rsp+118h+var_B4], esi
0x180039c47  mov     [rsp+118h+var_98], esi
0x180039c4e  mov     [rsp+118h+var_9C], esi
0x180039c52  mov     [rsp+118h+var_A0], esi
0x180039c56  mov     [r11-78h], rsi
0x180039c5a  mov     [rsp+118h+var_8C], esi
0x180039c61  mov     [rsp+118h+var_90], esi
0x180039c68  mov     [rsp+118h+var_B0], sil
0x180039c6d  mov     [rsp+118h+var_94], esi
0x180039c74  mov     r14d, r9d
0x180039c77  mov     [rsp+118h+var_B8], r9d
0x180039c7c  mov     r15, r8
0x180039c7f  mov     [rsp+118h+var_A8], r8
0x180039c84  cmp     edx, 6
0x180039c87  ja      loc_180039D64
0x180039c8d  jz      loc_180039D42
0x180039c93  mov     eax, edx
0x180039c95  sub     eax, 1
0x180039c98  jz      loc_180039D26
0x180039c9e  sub     eax, 1
0x180039ca1  jz      short loc_180039D04
0x180039ca3  sub     eax, 1
0x180039ca6  jz      short loc_180039CE8
0x180039ca8  sub     eax, 1
0x180039cab  jz      short loc_180039CCF
0x180039cad  cmp     eax, 1
0x180039cb0  jnz     loc_180039D83
0x180039cb6  test    r8, r8
0x180039cb9  jz      short loc_180039CC5
0x180039cbb  cmp     r9d, 4
0x180039cbf  jnb     loc_180039E28
0x180039cc5  lea     r15, [rsp+118h+var_A0]
0x180039cca  jmp     loc_180039E0D
0x180039ccf  test    r8, r8
0x180039cd2  jz      short loc_180039CDE
0x180039cd4  cmp     r9d, 4
0x180039cd8  jnb     loc_180039E28
0x180039cde  lea     r15, [rsp+118h+var_9C]
0x180039ce3  jmp     loc_180039E0D
0x180039ce8  test    r8, r8
0x180039ceb  jz      short loc_180039CF7
0x180039ced  cmp     r9d, 4
0x180039cf1  jnb     loc_180039E28
0x180039cf7  lea     r15, [rsp+118h+var_98]
0x180039cff  jmp     loc_180039E0D
0x180039d04  test    r8, r8
0x180039d07  jz      short loc_180039D13
0x180039d09  cmp     r9d, 14h
0x180039d0d  jnb     loc_180039E28
0x180039d13  lea     r15, [rsp+118h+var_68]
0x180039d1b  mov     r14d, 14h
0x180039d21  jmp     loc_180039E13
0x180039d26  test    r8, r8
0x180039d29  jz      short loc_180039D35
0x180039d2b  cmp     r9d, 4
0x180039d2f  jnb     loc_180039E28
0x180039d35  lea     r15, [rsp+118h+var_80]
0x180039d3d  jmp     loc_180039E0D
0x180039d42  test    r8, r8
0x180039d45  jz      short loc_180039D51
0x180039d47  cmp     r9d, 8
0x180039d4b  jnb     loc_180039E28
0x180039d51  lea     r15, [rsp+118h+var_78]
0x180039d59  mov     r14d, 8
0x180039d5f  jmp     loc_180039E13
0x180039d64  mov     eax, edx
0x180039d66  sub     eax, 7
0x180039d69  jz      loc_180039DFA
0x180039d6f  sub     eax, 1
0x180039d72  jz      short loc_180039DDE
0x180039d74  sub     eax, 1
0x180039d77  jz      short loc_180039DC9
0x180039d79  sub     eax, 2
0x180039d7c  jz      short loc_180039DAE
0x180039d7e  cmp     eax, 1
0x180039d81  jz      short loc_180039D95
0x180039d83  mov     ecx, 7Ch ; '|'; dwErrCode
0x180039d88  call    cs:__imp_SetLastError
0x180039d8e  xor     eax, eax
0x180039d90  jmp     loc_18003A01C
0x180039d95  test    r8, r8
0x180039d98  jz      short loc_180039DA4
0x180039d9a  cmp     r9d, 4
0x180039d9e  jnb     loc_180039E28
0x180039da4  lea     r15, [rsp+118h+var_94]
0x180039dac  jmp     short loc_180039E0D
0x180039dae  test    r8, r8
0x180039db1  jz      short loc_180039DB9
0x180039db3  cmp     r9d, 1
0x180039db7  jnb     short loc_180039E28
0x180039db9  lea     r15, [rsp+118h+var_B0]
0x180039dbe  mov     r14d, 1
0x180039dc4  mov     r12d, r14d
0x180039dc7  jmp     short loc_180039E19
0x180039dc9  test    r8, r8
0x180039dcc  jz      short loc_180039DD4
0x180039dce  cmp     r9d, 4
0x180039dd2  jnb     short loc_180039E28
0x180039dd4  lea     r15, [rsp+118h+var_90]
0x180039ddc  jmp     short loc_180039E0D
0x180039dde  mov     rax, [rsp+118h+pcbBytesNeeded]
0x180039de6  mov     [rsp+118h+var_F8], rax; unsigned int *
0x180039deb  mov     edx, 8; unsigned int
0x180039df0  call    ?ScQueryServiceConfigEx@@YAHPEAUSC_HANDLE__@@KPEAEKPEAK@Z; ScQueryServiceConfigEx(SC_HANDLE__ *,ulong,uchar *,ulong,ulong *)
0x180039df5  jmp     loc_18003A01C
0x180039dfa  test    r8, r8
0x180039dfd  jz      short loc_180039E05
0x180039dff  cmp     r9d, 4
0x180039e03  jnb     short loc_180039E28
0x180039e05  lea     r15, [rsp+118h+var_8C]
0x180039e0d  mov     r14d, 4
0x180039e13  mov     r12d, 1
0x180039e19  mov     [rsp+118h+var_B4], r12d
0x180039e1e  mov     [rsp+118h+var_B8], r14d
0x180039e23  mov     [rsp+118h+var_A8], r15
0x180039e28  mov     [rsp+118h+var_70], rsi
0x180039e30  mov     rax, [rsp+118h+pcbBytesNeeded]
0x180039e38  mov     [rsp+118h+var_E8], rax
0x180039e3d  mov     [rsp+118h+var_F0], r14d
0x180039e42  mov     [rsp+118h+var_F8], r15
0x180039e47  mov     r9d, edx
0x180039e4a  mov     r8, rcx
0x180039e4d  lea     rdx, byte_1800609B4; pFormat
0x180039e54  lea     rcx, pStubDescriptor; pStubDescriptor
0x180039e5b  call    cs:__imp_NdrClientCall2
0x180039e61  mov     rbx, rax
0x180039e64  mov     [rsp+118h+var_70], rax
0x180039e6c  mov     [rsp+118h+var_88], eax
0x180039e73  mov     ecx, [rsp+118h+arg_8]
0x180039e7a  jmp     short loc_180039EB4
0x180039e7c  mov     ecx, eax; unsigned int
0x180039e7e  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180039e83  mov     ebx, eax
0x180039e85  mov     [rsp+118h+var_88], eax
0x180039e8c  xor     esi, esi
0x180039e8e  mov     r13d, [rsp+118h+arg_18]
0x180039e96  mov     rdi, [rsp+118h+arg_10]
0x180039e9e  mov     ecx, [rsp+118h+arg_8]
0x180039ea5  mov     r15, [rsp+118h+var_A8]
0x180039eaa  mov     r14d, [rsp+118h+var_B8]
0x180039eaf  mov     r12d, [rsp+118h+var_B4]
0x180039eb4  lea     eax, [rcx-1]
0x180039eb7  test    eax, 0FFFFFFFAh
0x180039ebc  jnz     loc_180039F46
0x180039ec2  cmp     ecx, 5
0x180039ec5  jz      short loc_180039F46
0x180039ec7  test    ebx, ebx
0x180039ec9  jz      short loc_180039ED4
0x180039ecb  mov     eax, 7Ah ; 'z'
0x180039ed0  cmp     ebx, eax
0x180039ed2  jnz     short loc_180039F4B
0x180039ed4  mov     eax, 0Dh
0x180039ed9  sub     ecx, 1
0x180039edc  jz      short loc_180039EF4
0x180039ede  sub     ecx, 1
0x180039ee1  jz      short loc_180039EED
0x180039ee3  cmp     ecx, 4
0x180039ee6  jnz     short loc_180039EF9
0x180039ee8  lea     eax, [rcx+7]
0x180039eeb  jmp     short loc_180039EF9
0x180039eed  mov     eax, 0Ah
0x180039ef2  jmp     short loc_180039EF9
0x180039ef4  mov     eax, 8
0x180039ef9  mov     [rsp+118h+var_C8], rsi
0x180039efe  mov     [rsp+118h+var_D0], rsi
0x180039f03  mov     [rsp+118h+var_D8], rsi
0x180039f08  mov     [rsp+118h+var_E0], rsi
0x180039f0d  mov     rcx, [rsp+118h+pcbBytesNeeded]
0x180039f15  mov     [rsp+118h+var_E8], rcx
0x180039f1a  mov     [rsp+118h+var_F0], r14d
0x180039f1f  mov     [rsp+118h+var_F8], r15
0x180039f24  xor     r9d, r9d
0x180039f27  xor     r8d, r8d
0x180039f2a  xor     edx, edx
0x180039f2c  mov     ecx, eax
0x180039f2e  call    ?ScConvertOffsets64@@YAHW4SC_API_NUMBER@@PEAUSC_HANDLE__@@KKPEAEKPEAK33PEAX3@Z; ScConvertOffsets64(SC_API_NUMBER,SC_HANDLE__ *,ulong,ulong,uchar *,ulong,ulong *,ulong *,ulong *,void *,ulong *)
0x180039f33  test    eax, eax
0x180039f35  mov     eax, 7Ah ; 'z'
0x180039f3a  cmovz   ebx, eax
0x180039f3d  mov     ecx, [rsp+118h+arg_8]
0x180039f44  jmp     short loc_180039F4B
0x180039f46  mov     eax, 7Ah ; 'z'
0x180039f4b  test    ebx, ebx
0x180039f4d  jz      short loc_180039F56
0x180039f4f  mov     ecx, ebx
0x180039f51  jmp     loc_180039D88
0x180039f56  test    r12d, r12d
0x180039f59  jz      short loc_180039F62
0x180039f5b  mov     ecx, eax
0x180039f5d  jmp     loc_180039D88
0x180039f62  sub     ecx, 1
0x180039f65  jz      loc_18003A02F
0x180039f6b  sub     ecx, 1
0x180039f6e  jz      short loc_180039FA4
0x180039f70  cmp     ecx, 4
0x180039f73  jnz     loc_18003A017
0x180039f79  cmp     [rdi], rsi
0x180039f7c  jz      loc_18003A017
0x180039f82  mov     edx, [rdi]
0x180039f84  add     rdx, rdi
0x180039f87  mov     [rdi], rdx
0x180039f8a  jz      loc_18003A017
0x180039f90  mov     ecx, r13d
0x180039f93  add     rcx, rdi
0x180039f96  cmp     rdx, rcx
0x180039f99  jnb     loc_18003A04F
0x180039f9f  cmp     rdx, rdi
0x180039fa2  jmp     short loc_18003A015
0x180039fa4  cmp     [rdi+8], rsi
0x180039fa8  jz      short loc_180039FB7
0x180039faa  mov     r8d, [rdi+8]
0x180039fae  add     r8, rdi
0x180039fb1  mov     [rdi+8], r8
0x180039fb5  jmp     short loc_180039FBA
0x180039fb7  mov     r8, rsi
0x180039fba  cmp     [rdi+10h], rsi
0x180039fbe  jz      short loc_180039FCC
0x180039fc0  mov     edx, [rdi+10h]
0x180039fc3  add     rdx, rdi
0x180039fc6  mov     [rdi+10h], rdx
0x180039fca  jmp     short loc_180039FCF
0x180039fcc  mov     rdx, rsi
0x180039fcf  cmp     [rdi+20h], rsi
0x180039fd3  jz      short loc_180039FE1
0x180039fd5  mov     ecx, [rdi+20h]
0x180039fd8  add     rcx, rdi
0x180039fdb  mov     [rdi+20h], rcx
0x180039fdf  jmp     short loc_180039FE4
0x180039fe1  mov     rcx, rsi
0x180039fe4  mov     r9d, r13d
0x180039fe7  add     r9, rdi
0x180039fea  test    r8, r8
0x180039fed  jz      short loc_180039FF9
0x180039fef  cmp     r8, r9
0x180039ff2  jnb     short loc_18003A04F
0x180039ff4  cmp     r8, rdi
0x180039ff7  jb      short loc_18003A04F
0x180039ff9  test    rdx, rdx
0x180039ffc  jz      short loc_18003A008
0x180039ffe  cmp     rdx, r9
0x18003a001  jnb     short loc_18003A04F
0x18003a003  cmp     rdx, rdi
0x18003a006  jb      short loc_18003A04F
0x18003a008  test    rcx, rcx
0x18003a00b  jz      short loc_18003A017
0x18003a00d  cmp     rcx, r9
0x18003a010  jnb     short loc_18003A04F
0x18003a012  cmp     rcx, rdi
0x18003a015  jb      short loc_18003A04F
0x18003a017  mov     eax, 1
0x18003a01c  add     rsp, 0E0h
0x18003a023  pop     r15
0x18003a025  pop     r14
0x18003a027  pop     r13
0x18003a029  pop     r12
0x18003a02b  pop     rdi
0x18003a02c  pop     rsi
0x18003a02d  pop     rbx
0x18003a02e  retn
0x18003a02f  cmp     [rdi], rsi
0x18003a032  jz      short loc_18003A017
0x18003a034  mov     r8d, [rdi]
0x18003a037  add     r8, rdi
0x18003a03a  mov     [rdi], r8
0x18003a03d  jz      short loc_18003A017
0x18003a03f  mov     edx, r13d
0x18003a042  add     rdx, rdi
0x18003a045  cmp     r8, rdx
0x18003a048  jnb     short loc_18003A04F
0x18003a04a  cmp     r8, rdi
0x18003a04d  jnb     short loc_18003A017
0x18003a04f  mov     ecx, 0Dh
0x18003a054  jmp     loc_180039D88
0x1800505f0  push    rbp
0x1800505f2  sub     rsp, 60h
0x1800505f6  mov     rbp, rdx
0x1800505f9  mov     rcx, [rcx]
0x1800505fc  mov     ecx, [rcx]; ExceptionCode
  ... truncated ...
```
