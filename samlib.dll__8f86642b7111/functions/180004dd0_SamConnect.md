# SamConnect

- ea: `0x180004dd0`
- end: `0x1800054ba`
- name: `SamConnect`
- size: `1770`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800083a0`
- `0x180008dc4`
- `0x180008f5c`
- `0x18000918c`
- `0x18000a5a0`
- `0x180010cf0`
- `0x1800127a0`
- `0x180015090`
- `0x180015480`

## callees

- `0x180004dd0`
- `0x180006620`
- `0x1800078c0`
- `0x18000807c`
- `0x180008da0`
- `0x18000baf8`
- `0x180014a50`
- `0x180015194`
- `0x1800153a8`
- `0x180015998`
- `0x180015e18`
- `0x1800160d8`
- `0x180017929`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004e94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004e94`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000520b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000520b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e62`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800053e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004eeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004fdc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004eeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004fdc`
- `RPCRT4!NdrClientCall3` at `0x180005094`
- `RPCRT4!NdrClientCall3` at `0x180005177`
- `RPCRT4!NdrClientCall3` at `0x180005257`
- `RPCRT4!NdrClientCall3` at `0x180005318`
- `RPCRT4!NdrClientCall3` at `0x180005094`
- `RPCRT4!NdrClientCall3` at `0x180005177`
- `RPCRT4!NdrClientCall3` at `0x180005257`
- `RPCRT4!NdrClientCall3` at `0x180005318`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800050ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800051b9`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005299`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000535a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800050ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800051b9`
- `RPCRT4!I_RpcMapWin32Status` at `0x180005299`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000535a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c6a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c86`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017ca2`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c6a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017c86`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017ca2`

## pseudocode

```c
__int64 __fastcall SamConnect(struct _UNICODE_STRING *a1, __int64 *a2, int a3)
{
  unsigned __int16 *v5; // rsi
  unsigned __int16 *CallingProcessInfo; // rax
  int v7; // edx
  unsigned __int16 *v8; // r14
  const wchar_t *v9; // r8
  const wchar_t *v10; // rcx
  unsigned __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  unsigned __int16 v13; // dx
  _QWORD *v14; // rsi
  _QWORD *v15; // rcx
  __int64 result; // rax
  _WORD *v17; // r14
  PWSTR Buffer; // r12
  _WORD *v19; // rax
  CLIENT_CALL_RETURN v20; // rbx
  __int64 v21; // rax
  _DWORD *Value; // rax
  void *v23; // rcx
  PVOID v24; // rcx
  __int64 v25; // r9
  char v26[8]; // [rsp+20h] [rbp-2D8h]
  __int64 v27; // [rsp+28h] [rbp-2D0h]
  __int64 v28; // [rsp+28h] [rbp-2D0h]
  CLIENT_CALL_RETURN v29; // [rsp+30h] [rbp-2C8h]
  unsigned __int16 v30[2]; // [rsp+54h] [rbp-2A4h] BYREF
  int v31; // [rsp+58h] [rbp-2A0h]
  CLIENT_CALL_RETURN v32; // [rsp+60h] [rbp-298h]
  HLOCAL v33; // [rsp+68h] [rbp-290h]
  _QWORD v34[2]; // [rsp+70h] [rbp-288h] BYREF
  __int64 v35; // [rsp+80h] [rbp-278h] BYREF
  __int64 v36; // [rsp+88h] [rbp-270h] BYREF
  __int64 v37; // [rsp+90h] [rbp-268h]
  __int64 *v38; // [rsp+98h] [rbp-260h]
  WCHAR Filename[272]; // [rsp+A0h] [rbp-258h] BYREF

  v38 = a2;
  v31 = a3;
  v30[0] = 0;
  v34[0] = 0;
  *a2 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    v5 = SampDuplicateUnicodeString(a1);
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v8 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v9 = L"<unknown>";
      v10 = L"<unknown>";
      if ( CallingProcessInfo )
        v10 = CallingProcessInfo;
      if ( v5 )
        LODWORD(v9) = (_DWORD)v5;
      McTemplateU0zdz_EventWriteTransfer((_DWORD)v10, v7, (_DWORD)v9, a3, (__int64)v10);
    }
    LocalFree(v8);
    LocalFree(v5);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    if ( !GetModuleFileNameW(0, Filename, 0x10Eu) )
      RtlStringCchCopyW(Filename, v11, v12);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_ZDS(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, (__int64)Filename);
  }
  v14 = LocalAlloc(0x40u, 0x18u);
  v34[1] = v14;
  if ( v14 )
  {
    *(_OWORD *)v14 = 0;
    v14[2] = 0;
    v37 = 0;
    v17 = 0;
    v33 = 0;
    if ( a1 )
    {
      Buffer = a1->Buffer;
      if ( Buffer )
      {
        if ( a1->Length )
        {
          result = RtlUShortAdd(a1->Length, v13, v30);
          if ( (int)result < 0 )
            return result;
          if ( v30[0] < 2u )
            return 3221225711LL;
          v19 = LocalAlloc(0x40u, v30[0]);
          v17 = v19;
          v33 = v19;
          if ( !v19 )
            return 3221225626LL;
          memcpy_0(v19, Buffer, a1->Length);
          v17[(unsigned __int64)a1->Length >> 1] = 0;
        }
      }
    }
    *(_DWORD *)v30 = 0;
    v36 = 0;
    v35 = 3;
    v32.Simple = 0;
    LODWORD(v27) = 1;
    *(_DWORD *)v26 = a3;
    v20.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo,
                    0x40u,
                    0,
                    v17,
                    *(_QWORD *)v26,
                    v27,
                    &v35,
                    v30,
                    &v36,
                    v34).Pointer;
    v32.Pointer = v20.Pointer;
    v21 = 0;
    if ( SLODWORD(v20.Simple) >= 0 )
      v21 = v36;
    v37 = v21;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
        LODWORD(v20.Pointer));
    if ( LODWORD(v20.Pointer) == -1073610734 || LODWORD(v20.Pointer) == -1073610706 )
    {
      v32.Simple = 0;
      LODWORD(v29.Pointer) = a3;
      LODWORD(v28) = 2;
      v32.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x3Eu, 0, v17, v34, v28, v29.Simple).Pointer;
      LODWORD(v20.Pointer) = v32.Pointer;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
          LODWORD(v32.Pointer));
    }
    if ( SLODWORD(v20.Simple) >= 0 )
    {
      Value = TlsGetValue(dwTlsIndex);
      if ( Value )
        Value[4] = 1;
    }
    if ( LODWORD(v20.Pointer) == -1073610734 || LODWORD(v20.Pointer) == -1073610706 )
    {
      v32.Simple = 0;
      LODWORD(v28) = a3;
      v32.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x39u, 0, v17, v34, v28).Pointer;
      LODWORD(v20.Pointer) = v32.Pointer;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
          LODWORD(v32.Pointer));
    }
    if ( LODWORD(v20.Pointer) == -1073610734 || LODWORD(v20.Pointer) == -1073610706 )
    {
      v32.Simple = 0;
      LODWORD(v28) = a3;
      v32.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0, 0, v17, v34, v28).Pointer;
      LODWORD(v20.Pointer) = v32.Pointer;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
          LODWORD(v32.Pointer));
    }
    if ( v17 )
      LocalFree(v17);
    if ( SLODWORD(v20.Simple) < 0 )
    {
      v23 = (void *)v14[2];
      if ( v23 )
        LocalFree(v23);
      *(_OWORD *)v14 = 0;
      v14[2] = 0;
      LocalFree(v14);
      v14 = 0;
    }
    else
    {
      *v14 = v34[0];
      v14[1] = v37;
    }
    *v38 = (__int64)v14;
    if ( LODWORD(v20.Pointer) == -1073610749 )
      LODWORD(v20.Pointer) = -1073741816;
    if ( SLODWORD(v20.Simple) < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
          LODWORD(v20.Pointer));
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return LODWORD(v20.Pointer);
      v25 = 0;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, v14);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return LODWORD(v20.Pointer);
      v25 = *v38;
    }
    McTemplateU0dp_EventWriteTransfer(v24, SamConnectExit, LODWORD(v20.Pointer), v25);
    return LODWORD(v20.Pointer);
  }
  v15 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
      v15 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
      WPP_SF_D(v15[2], 17, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids, 3221225495LL);
  }
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v15, SamConnectExit, 3221225495LL, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180004dd0  mov     [rsp+arg_18], rbx
0x180004dd5  push    rsi
0x180004dd6  push    rdi
0x180004dd7  push    r12
0x180004dd9  push    r14
0x180004ddb  push    r15
0x180004ddd  sub     rsp, 2D0h
0x180004de4  mov     rax, cs:__security_cookie
0x180004deb  xor     rax, rsp
0x180004dee  mov     [rsp+2F8h+var_38], rax
0x180004df6  mov     r15d, r8d
0x180004df9  mov     rbx, rcx
0x180004dfc  mov     [rsp+2F8h+var_260], rdx
0x180004e04  mov     [rsp+2F8h+var_2A0], r8d
0x180004e09  xor     edi, edi
0x180004e0b  mov     [rsp+2F8h+var_2A4], di
0x180004e10  mov     [rsp+2F8h+var_288], rdi
0x180004e15  mov     [rdx], rdi
0x180004e18  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180004e1f  jz      short loc_180004E71
0x180004e21  call    ?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z; SampDuplicateUnicodeString(_UNICODE_STRING *)
0x180004e26  mov     rsi, rax
0x180004e29  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180004e2e  mov     r14, rax
0x180004e31  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180004e38  jz      short loc_180004E5F
0x180004e3a  lea     r8, aUnknown; "<unknown>"
0x180004e41  mov     rcx, r8
0x180004e44  test    rax, rax
0x180004e47  cmovnz  rcx, rax
0x180004e4b  test    rsi, rsi
0x180004e4e  cmovnz  r8, rsi
0x180004e52  mov     qword ptr [rsp+2F8h+var_2D8], rcx
0x180004e57  mov     r9d, r15d
0x180004e5a  call    McTemplateU0zdz_EventWriteTransfer
0x180004e5f  mov     rcx, r14; hMem
0x180004e62  call    cs:__imp_LocalFree
0x180004e68  mov     rcx, rsi; hMem
0x180004e6b  call    cs:__imp_LocalFree
0x180004e71  mov     rax, cs:WPP_GLOBAL_Control
0x180004e78  test    byte ptr [rax+1Ch], 2
0x180004e7c  jz      short loc_180004EE1
0x180004e7e  cmp     byte ptr [rax+19h], 4
0x180004e82  jb      short loc_180004EE1
0x180004e84  mov     r8d, 10Eh; nSize
0x180004e8a  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180004e92  xor     ecx, ecx; hModule
0x180004e94  call    cs:__imp_GetModuleFileNameW
0x180004e9a  test    eax, eax
0x180004e9c  jnz     short loc_180004EAB
0x180004e9e  lea     rcx, [rsp+2F8h+Filename]; unsigned __int16 *
0x180004ea6  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eb2  test    byte ptr [rcx+1Ch], 2
0x180004eb6  jz      short loc_180004EE1
0x180004eb8  cmp     byte ptr [rcx+19h], 4
0x180004ebc  jb      short loc_180004EE1
0x180004ebe  mov     edx, 10h
0x180004ec3  lea     rax, [rsp+2F8h+Filename]
0x180004ecb  mov     [rsp+2F8h+var_2D0], rax; __int64
0x180004ed0  mov     dword ptr [rsp+2F8h+var_2D8], r15d; char
0x180004ed5  mov     r9, rbx
0x180004ed8  mov     rcx, [rcx+10h]; LoggerHandle
0x180004edc  call    WPP_SF_ZDS
0x180004ee1  mov     edx, 18h; uBytes
0x180004ee6  mov     ecx, 40h ; '@'; uFlags
0x180004eeb  call    cs:__imp_LocalAlloc
0x180004ef1  mov     rsi, rax
0x180004ef4  mov     [rsp+2F8h+var_280], rax
0x180004ef9  test    rax, rax
0x180004efc  jnz     short loc_180004F7C
0x180004efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f05  test    byte ptr [rcx+1Ch], 2
0x180004f09  jz      short loc_180004F54
0x180004f0b  cmp     byte ptr [rcx+19h], 2
0x180004f0f  jb      short loc_180004F2D
0x180004f11  mov     edx, 2Ch ; ','
0x180004f16  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180004f1d  mov     rcx, [rcx+10h]
0x180004f21  call    WPP_SF_
0x180004f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f2d  test    byte ptr [rcx+1Ch], 2
0x180004f31  jz      short loc_180004F54
0x180004f33  cmp     byte ptr [rcx+19h], 2
0x180004f37  jb      short loc_180004F54
0x180004f39  mov     edx, 11h
0x180004f3e  mov     r9d, 0C0000017h
0x180004f44  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180004f4b  mov     rcx, [rcx+10h]
0x180004f4f  call    WPP_SF_D
0x180004f54  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180004f5b  jz      short loc_180004F72
0x180004f5d  xor     r9d, r9d
0x180004f60  mov     r8d, 0C0000017h
0x180004f66  lea     rdx, SamConnectExit
0x180004f6d  call    McTemplateU0dp_EventWriteTransfer
0x180004f72  mov     eax, 0C0000017h
0x180004f77  jmp     loc_180005492
0x180004f7c  xorps   xmm0, xmm0
0x180004f7f  xor     eax, eax
0x180004f81  movups  xmmword ptr [rsi], xmm0
0x180004f84  mov     [rsi+10h], rax
0x180004f88  mov     [rsp+2F8h+var_268], rdi
0x180004f90  mov     r14, rdi
0x180004f93  mov     [rsp+2F8h+var_290], rdi
0x180004f98  test    rbx, rbx
0x180004f9b  jz      short loc_180005013
0x180004f9d  mov     r12, [rbx+8]
0x180004fa1  test    r12, r12
0x180004fa4  jz      short loc_180005013
0x180004fa6  movzx   ecx, word ptr [rbx]; unsigned __int16
0x180004fa9  test    cx, cx
0x180004fac  jz      short loc_180005013
0x180004fae  lea     r8, [rsp+2F8h+var_2A4]; unsigned __int16 *
0x180004fb3  call    ?RtlUShortAdd@@YAJGGPEAG@Z; RtlUShortAdd(ushort,ushort,ushort *)
0x180004fb8  test    eax, eax
0x180004fba  js      loc_180005492
0x180004fc0  movzx   eax, [rsp+2F8h+var_2A4]
0x180004fc5  cmp     eax, 2
0x180004fc8  jnb     short loc_180004FD4
0x180004fca  mov     eax, 0C00000EFh
0x180004fcf  jmp     loc_180005492
0x180004fd4  mov     rdx, rax; uBytes
0x180004fd7  mov     ecx, 40h ; '@'; uFlags
0x180004fdc  call    cs:__imp_LocalAlloc
0x180004fe2  mov     r14, rax
0x180004fe5  mov     [rsp+2F8h+var_290], rax
0x180004fea  test    rax, rax
0x180004fed  jnz     short loc_180004FF9
0x180004fef  mov     eax, 0C000009Ah
0x180004ff4  jmp     loc_180005492
0x180004ff9  movzx   r8d, word ptr [rbx]; Size
0x180004ffd  mov     rdx, r12; Src
0x180005000  mov     rcx, r14; void *
0x180005003  call    memcpy_0
0x180005008  movzx   eax, word ptr [rbx]
0x18000500b  shr     rax, 1
0x18000500e  mov     [r14+rax*2], di
0x180005013  mov     [rsp+2F8h+var_278], rdi
0x18000501b  mov     [rsp+2F8h+var_270], rdi
0x180005023  mov     dword ptr [rsp+2F8h+var_2A4], edi
0x180005027  mov     [rsp+2F8h+var_278], rdi
0x18000502f  mov     [rsp+2F8h+var_270], rdi
0x180005037  mov     dword ptr [rsp+2F8h+var_278], 3
0x180005042  mov     [rsp+2F8h+var_298], rdi
0x180005047  lea     rax, [rsp+2F8h+var_288]
0x18000504c  mov     [rsp+2F8h+var_2B0], rax
0x180005051  lea     rax, [rsp+2F8h+var_270]
0x180005059  mov     [rsp+2F8h+var_2B8], rax
0x18000505e  lea     rax, [rsp+2F8h+var_2A4]
0x180005063  mov     [rsp+2F8h+var_2C0], rax
0x180005068  lea     rax, [rsp+2F8h+var_278]
0x180005070  mov     [rsp+2F8h+var_2C8], rax
0x180005075  mov     dword ptr [rsp+2F8h+var_2D0], 1
0x18000507d  mov     dword ptr [rsp+2F8h+var_2D8], r15d
0x180005082  mov     r9, r14
0x180005085  xor     r8d, r8d; pReturnValue
0x180005088  mov     edx, 40h ; '@'; nProcNum
0x18000508d  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180005094  call    cs:__imp_NdrClientCall3
0x18000509a  mov     rbx, rax
0x18000509d  mov     [rsp+2F8h+var_298], rax
0x1800050a2  mov     [rsp+2F8h+var_2A8], ebx
0x1800050a6  mov     rax, rdi
0x1800050a9  test    ebx, ebx
0x1800050ab  cmovns  rax, [rsp+2F8h+var_270]
0x1800050b4  mov     [rsp+2F8h+var_268], rax
0x1800050bc  jmp     short loc_18000510A
0x1800050be  mov     ebx, eax
0x1800050c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050c7  test    byte ptr [rcx+1Ch], 2
0x1800050cb  jz      short loc_1800050EB
0x1800050cd  cmp     byte ptr [rcx+19h], 3
0x1800050d1  jb      short loc_1800050EB
0x1800050d3  mov     r9d, eax
0x1800050d6  mov     edx, 12h
0x1800050db  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800050e2  mov     rcx, [rcx+10h]
0x1800050e6  call    WPP_SF_D
0x1800050eb  mov     ecx, ebx; Status
0x1800050ed  call    cs:__imp_I_RpcMapWin32Status
0x1800050f3  mov     ebx, eax
0x1800050f5  mov     [rsp+2F8h+var_2A8], eax
0x1800050f9  xor     edi, edi
0x1800050fb  mov     r14, [rsp+2F8h+var_290]
0x180005100  mov     rsi, [rsp+2F8h+var_280]
0x180005105  mov     r15d, [rsp+2F8h+var_2A0]
0x18000510a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005111  test    byte ptr [rcx+1Ch], 2
0x180005115  jz      short loc_180005135
0x180005117  cmp     byte ptr [rcx+19h], 4
0x18000511b  jb      short loc_180005135
0x18000511d  mov     edx, 13h
0x180005122  mov     r9d, ebx
0x180005125  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x18000512c  mov     rcx, [rcx+10h]
0x180005130  call    WPP_SF_D
0x180005135  cmp     ebx, 0C0020012h
0x18000513b  jz      short loc_180005149
0x18000513d  cmp     ebx, 0C002002Eh
0x180005143  jnz     loc_180005201
0x180005149  mov     [rsp+2F8h+var_298], rdi
0x18000514e  mov     dword ptr [rsp+2F8h+var_2C8], r15d
0x180005153  mov     dword ptr [rsp+2F8h+var_2D0], 2
0x18000515b  lea     rax, [rsp+2F8h+var_288]
0x180005160  mov     qword ptr [rsp+2F8h+var_2D8], rax
0x180005165  mov     r9, r14
0x180005168  xor     r8d, r8d; pReturnValue
0x18000516b  mov     edx, 3Eh ; '>'; nProcNum
0x180005170  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180005177  call    cs:__imp_NdrClientCall3
0x18000517d  mov     [rsp+2F8h+var_298], rax
0x180005182  mov     ebx, eax
0x180005184  mov     [rsp+2F8h+var_2A8], eax
0x180005188  jmp     short loc_1800051D6
0x18000518a  mov     ebx, eax
0x18000518c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005193  test    byte ptr [rcx+1Ch], 2
0x180005197  jz      short loc_1800051B7
0x180005199  cmp     byte ptr [rcx+19h], 3
0x18000519d  jb      short loc_1800051B7
0x18000519f  mov     r9d, eax
0x1800051a2  mov     edx, 14h
0x1800051a7  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800051ae  mov     rcx, [rcx+10h]
0x1800051b2  call    WPP_SF_D
0x1800051b7  mov     ecx, ebx; Status
0x1800051b9  call    cs:__imp_I_RpcMapWin32Status
0x1800051bf  mov     ebx, eax
0x1800051c1  mov     [rsp+2F8h+var_2A8], eax
0x1800051c5  xor     edi, edi
0x1800051c7  mov     r14, [rsp+2F8h+var_290]
0x1800051cc  mov     rsi, [rsp+2F8h+var_280]
0x1800051d1  mov     r15d, [rsp+2F8h+var_2A0]
0x1800051d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051dd  test    byte ptr [rcx+1Ch], 2
0x1800051e1  jz      short loc_180005201
0x1800051e3  cmp     byte ptr [rcx+19h], 4
0x1800051e7  jb      short loc_180005201
0x1800051e9  mov     edx, 15h
0x1800051ee  mov     r9d, ebx
0x1800051f1  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800051f8  mov     rcx, [rcx+10h]
0x1800051fc  call    WPP_SF_D
0x180005201  test    ebx, ebx
0x180005203  js      short loc_18000521D
0x180005205  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000520b  call    cs:__imp_TlsGetValue
0x180005211  test    rax, rax
0x180005214  jz      short loc_18000521D
0x180005216  mov     dword ptr [rax+10h], 1
0x18000521d  cmp     ebx, 0C0020012h
0x180005223  jz      short loc_180005231
0x180005225  cmp     ebx, 0C002002Eh
0x18000522b  jnz     loc_1800052E1
0x180005231  mov     [rsp+2F8h+var_298], rdi
0x180005236  mov     dword ptr [rsp+2F8h+var_2D0], r15d
0x18000523b  lea     rax, [rsp+2F8h+var_288]
0x180005240  mov     qword ptr [rsp+2F8h+var_2D8], rax
0x180005245  mov     r9, r14
0x180005248  xor     r8d, r8d; pReturnValue
0x18000524b  mov     edx, 39h ; '9'; nProcNum
0x180005250  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180005257  call    cs:__imp_NdrClientCall3
0x18000525d  mov     [rsp+2F8h+var_298], rax
0x180005262  mov     ebx, eax
0x180005264  mov     [rsp+2F8h+var_2A8], eax
0x180005268  jmp     short loc_1800052B6
0x18000526a  mov     ebx, eax
0x18000526c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005273  test    byte ptr [rcx+1Ch], 2
0x180005277  jz      short loc_180005297
0x180005279  cmp     byte ptr [rcx+19h], 3
0x18000527d  jb      short loc_180005297
0x18000527f  mov     r9d, eax
0x180005282  mov     edx, 16h
0x180005287  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x18000528e  mov     rcx, [rcx+10h]
0x180005292  call    WPP_SF_D
0x180005297  mov     ecx, ebx; Status
0x180005299  call    cs:__imp_I_RpcMapWin32Status
0x18000529f  mov     ebx, eax
0x1800052a1  mov     [rsp+2F8h+var_2A8], eax
0x1800052a5  xor     edi, edi
0x1800052a7  mov     r14, [rsp+2F8h+var_290]
0x1800052ac  mov     rsi, [rsp+2F8h+var_280]
0x1800052b1  mov     r15d, [rsp+2F8h+var_2A0]
0x1800052b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052bd  test    byte ptr [rcx+1Ch], 2
0x1800052c1  jz      short loc_1800052E1
0x1800052c3  cmp     byte ptr [rcx+19h], 4
0x1800052c7  jb      short loc_1800052E1
0x1800052c9  mov     edx, 17h
0x1800052ce  mov     r9d, ebx
0x1800052d1  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800052d8  mov     rcx, [rcx+10h]
0x1800052dc  call    WPP_SF_D
0x1800052e1  cmp     ebx, 0C0020012h
0x1800052e7  jz      short loc_1800052F5
0x1800052e9  cmp     ebx, 0C002002Eh
  ... truncated ...
```
