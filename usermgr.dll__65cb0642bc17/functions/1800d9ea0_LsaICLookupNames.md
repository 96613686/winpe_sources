# LsaICLookupNames

- ea: `0x1800d9ea0`
- end: `0x1800da538`
- name: `LsaICLookupNames`
- size: `1688`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800da968`

## callees

- `0x18006f1c9`
- `0x1800d9ea0`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800da4fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800da2b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800da2b2`
- `ntdll!RtlSubAuthoritySid` at `0x1800da3f6`
- `ntdll!RtlSubAuthoritySid` at `0x1800da3f6`
- `ntdll!RtlCopySid` at `0x1800da3c4`
- `ntdll!RtlCopySid` at `0x1800da425`
- `ntdll!RtlCopySid` at `0x1800da3c4`
- `ntdll!RtlCopySid` at `0x1800da425`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800da3e0`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800da3e0`
- `ntdll!RtlLengthSid` at `0x1800da3a3`
- `ntdll!RtlLengthSid` at `0x1800da40d`
- `ntdll!RtlLengthSid` at `0x1800da448`
- `ntdll!RtlLengthSid` at `0x1800da3a3`
- `ntdll!RtlLengthSid` at `0x1800da40d`
- `ntdll!RtlLengthSid` at `0x1800da448`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800d9fbe`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800da0b3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800da17d`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800d9fbe`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800da0b3`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800da17d`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eabc9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eabe5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eac01`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eabc9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eabe5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800eac01`
- `RPCRT4!NdrClientCall3` at `0x1800d9f98`
- `RPCRT4!NdrClientCall3` at `0x1800da06f`
- `RPCRT4!NdrClientCall3` at `0x1800da149`
- `RPCRT4!NdrClientCall3` at `0x1800d9f98`
- `RPCRT4!NdrClientCall3` at `0x1800da06f`
- `RPCRT4!NdrClientCall3` at `0x1800da149`

## pseudocode

```c
__int64 __fastcall LsaICLookupNames(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        HLOCAL *a5,
        HLOCAL *a6,
        int a7,
        int a8,
        __int64 a9)
{
  HLOCAL *v10; // r13
  int Pointer; // ebx
  int v13; // esi
  unsigned int v14; // r12d
  HLOCAL *v15; // rsi
  unsigned __int64 v16; // r15
  int v17; // eax
  unsigned int v18; // ecx
  HLOCAL v19; // rax
  unsigned int i; // r15d
  int v21; // r10d
  int *v22; // r8
  int v23; // ecx
  __int64 v24; // r9
  __int64 v25; // r13
  PUCHAR v26; // rax
  ULONG v27; // edx
  PULONG v28; // rax
  ULONG v29; // eax
  CLIENT_CALL_RETURN v30; // [rsp+20h] [rbp-108h]
  CLIENT_CALL_RETURN v31; // [rsp+20h] [rbp-108h]
  CLIENT_CALL_RETURN v32; // [rsp+40h] [rbp-E8h]
  CLIENT_CALL_RETURN v33; // [rsp+40h] [rbp-E8h]
  CLIENT_CALL_RETURN v34; // [rsp+50h] [rbp-D8h]
  CLIENT_CALL_RETURN v35; // [rsp+58h] [rbp-D0h]
  size_t Size; // [rsp+78h] [rbp-B0h]
  void *Sizea; // [rsp+78h] [rbp-B0h]
  char *v39; // [rsp+80h] [rbp-A8h]
  __int64 v40; // [rsp+88h] [rbp-A0h] BYREF
  HLOCAL v41; // [rsp+90h] [rbp-98h]
  __int64 v42; // [rsp+98h] [rbp-90h]
  __int64 v43; // [rsp+A0h] [rbp-88h]
  __int64 v44; // [rsp+A8h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-78h]
  __int64 v46; // [rsp+B8h] [rbp-70h] BYREF
  HLOCAL v47; // [rsp+C0h] [rbp-68h]
  __int64 v48; // [rsp+C8h] [rbp-60h]
  __int64 v49; // [rsp+D0h] [rbp-58h]
  _BYTE DestinationSid[32]; // [rsp+D8h] [rbp-50h] BYREF

  v48 = a1;
  v49 = a4;
  v10 = a5;
  v43 = (__int64)a5;
  v42 = a9;
  v40 = 0;
  v41 = 0;
  v46 = 0;
  v47 = 0;
  v44 = 0;
  hMem = 0;
  *a5 = 0;
  *a6 = 0;
  if ( !a1 )
    return 3221225480LL;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x44u,
                            0,
                            *(_QWORD *)(a1 + 8),
                            1,
                            a4,
                            a5,
                            &v40,
                            1,
                            a9,
                            0,
                            2).Pointer;
  v13 = 3;
  v14 = 0;
  if ( Pointer == -1073610734 || Pointer == -1073610706 )
  {
    LODWORD(v35.Pointer) = 2;
    LODWORD(v34.Pointer) = 0;
    LODWORD(v32.Pointer) = 1;
    LODWORD(v30.Pointer) = 1;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x3Au,
                              0,
                              *(_QWORD *)(a1 + 8),
                              v30.Simple,
                              a4,
                              a5,
                              &v46,
                              v32.Simple,
                              v42,
                              v34.Simple,
                              v35.Simple).Pointer;
    v13 = 2;
    if ( v47 )
      v14 = v46;
    if ( Pointer == -1073610734 || Pointer == -1073610706 )
    {
      LODWORD(v33.Pointer) = 1;
      LODWORD(v31.Pointer) = 1;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0xEu,
                                0,
                                *(_QWORD *)(a1 + 8),
                                v31.Simple,
                                a4,
                                a5,
                                &v44,
                                v33.Simple,
                                v42).Pointer;
      v13 = 1;
      if ( hMem )
        v14 = v44;
    }
  }
  if ( Pointer >= 0
    && (v13 == 1 && (!(_DWORD)v44 || !hMem) || v13 == 2 && (!(_DWORD)v46 || !v47) || v13 == 3 && (!(_DWORD)v40 || !v41))
    || v13 == 1 && !(_DWORD)v44 && hMem
    || v13 == 2 && !(_DWORD)v46 && v47
    || v13 == 3 && !(_DWORD)v40 && v41 )
  {
LABEL_21:
    Pointer = -1073741629;
LABEL_22:
    v15 = a6;
    goto LABEL_57;
  }
  if ( v13 == 2 && v47 || v13 == 1 && hMem )
  {
    v16 = 24LL * v14;
    if ( v16 > 0xFFFFFFFF
      || (v17 = 28 * v14, 28 * (unsigned __int64)v14 > 0xFFFFFFFF)
      || (v18 = v17 + v16, v17 + (int)v16 < (unsigned int)v16) )
    {
      Pointer = -1073741675;
      goto LABEL_22;
    }
    Size = v18;
    v19 = LocalAlloc(0x40u, v18);
    v41 = v19;
    if ( !v19 )
    {
      Pointer = -1073741801;
      goto LABEL_22;
    }
    memset_0(v19, 0, Size);
    v39 = (char *)v41 + v16;
    for ( i = 0; i < v14; ++i )
    {
      if ( v13 == 1 )
      {
        v21 = 0;
        v22 = (int *)((char *)hMem + 12 * i);
      }
      else
      {
        v22 = (int *)((char *)v47 + 16 * i);
        v21 = v22[3];
      }
      v23 = *v22;
      LODWORD(v42) = v22[1];
      v24 = (unsigned int)v22[2];
      v25 = 3LL * i;
      *((_DWORD *)v41 + 2 * v25) = v23;
      *((_DWORD *)v41 + 2 * v25 + 4) = v24;
      *((_DWORD *)v41 + 2 * v25 + 5) = v21;
      if ( (unsigned int)(v23 - 6) <= 2 )
      {
        *((_QWORD *)v41 + 3 * i + 1) = 0;
      }
      else
      {
        if ( (_DWORD)v24 == -1
          || (Sizea = *(void **)(*(_QWORD *)(*(_QWORD *)v43 + 8LL) + 24 * v24 + 16), RtlLengthSid(Sizea) > 0x18) )
        {
          v10 = (HLOCAL *)v43;
          goto LABEL_21;
        }
        RtlCopySid(0x1Cu, DestinationSid, Sizea);
        if ( (_DWORD)v42 != -1 )
        {
          v26 = RtlSubAuthorityCountSid(DestinationSid);
          v27 = *v26;
          *v26 = v27 + 1;
          v28 = RtlSubAuthoritySid(DestinationSid, v27);
          *v28 = v42;
        }
        v29 = RtlLengthSid(DestinationSid);
        RtlCopySid(v29, v39, DestinationSid);
        *((_QWORD *)v41 + 3 * i + 1) = v39;
        v39 += RtlLengthSid(DestinationSid);
      }
    }
    v10 = (HLOCAL *)v43;
  }
  v15 = a6;
  *a6 = v41;
  v41 = 0;
LABEL_57:
  if ( Pointer == -1073741629 || Pointer == -1073741801 || Pointer == -1073741675 )
  {
    if ( *v10 )
    {
      LocalFree(*v10);
      *v10 = 0;
    }
    *v15 = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v47 )
    LocalFree(v47);
  if ( v41 )
    LocalFree(v41);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800d9ea0  mov     r11, rsp
0x1800d9ea3  mov     [r11+10h], rbx
0x1800d9ea7  push    rsi
0x1800d9ea8  push    rdi
0x1800d9ea9  push    r12
0x1800d9eab  push    r13
0x1800d9ead  push    r15
0x1800d9eaf  sub     rsp, 100h
0x1800d9eb6  mov     rax, cs:__security_cookie
0x1800d9ebd  xor     rax, rsp
0x1800d9ec0  mov     [rsp+128h+var_30], rax
0x1800d9ec8  mov     rax, r9
0x1800d9ecb  mov     [rsp+128h+var_A8], rax
0x1800d9ed3  mov     r15, rcx
0x1800d9ed6  mov     [rsp+128h+var_60], rcx
0x1800d9ede  mov     [rsp+128h+var_58], rax
0x1800d9ee6  mov     r13, [rsp+128h+arg_20]
0x1800d9eee  mov     [rsp+128h+var_88], r13
0x1800d9ef6  mov     rdx, [rsp+128h+arg_28]
0x1800d9efe  mov     [rsp+128h+var_C8], rdx
0x1800d9f03  mov     rcx, [rsp+128h+arg_40]
0x1800d9f0b  mov     [rsp+128h+var_90], rcx
0x1800d9f13  xor     edi, edi
0x1800d9f15  mov     [r11-0A0h], rdi
0x1800d9f1c  mov     [r11-98h], rdi
0x1800d9f23  mov     [r11-70h], rdi
0x1800d9f27  mov     [r11-68h], rdi
0x1800d9f2b  mov     [r11-80h], rdi
0x1800d9f2f  mov     [r11-78h], rdi
0x1800d9f33  mov     [r13+0], rdi
0x1800d9f37  mov     [rdx], rdi
0x1800d9f3a  test    r15, r15
0x1800d9f3d  jnz     short loc_1800D9F49
0x1800d9f3f  mov     eax, 0C0000008h
0x1800d9f44  jmp     loc_1800DA506
0x1800d9f49  mov     [rsp+128h+Size], rdi
0x1800d9f4e  mov     dword ptr [rsp+128h+var_D0], 2
0x1800d9f56  mov     dword ptr [rsp+128h+var_D8], edi
0x1800d9f5a  mov     [rsp+128h+var_E0], rcx
0x1800d9f5f  mov     dword ptr [rsp+128h+var_E8], 1
0x1800d9f67  lea     rcx, [rsp+128h+var_A0]
0x1800d9f6f  mov     [rsp+128h+var_F0], rcx
0x1800d9f74  mov     [rsp+128h+var_F8], r13
0x1800d9f79  mov     [rsp+128h+var_100], rax
0x1800d9f7e  mov     dword ptr [rsp+128h+var_108], 1
0x1800d9f86  mov     r9, [r15+8]
0x1800d9f8a  xor     r8d, r8d; pReturnValue
0x1800d9f8d  lea     edx, [r8+44h]; nProcNum
0x1800d9f91  lea     rcx, pProxyInfo; pProxyInfo
0x1800d9f98  call    cs:__imp_NdrClientCall3
0x1800d9f9e  mov     rbx, rax
0x1800d9fa1  mov     [rsp+128h+Size], rax
0x1800d9fa6  mov     [rsp+128h+var_C0], eax
0x1800d9faa  mov     rax, [rsp+128h+var_A8]
0x1800d9fb2  mov     rcx, [rsp+128h+var_90]
0x1800d9fba  jmp     short loc_1800D9FFC
0x1800d9fbc  mov     ecx, eax; Status
0x1800d9fbe  call    cs:__imp_I_RpcMapWin32Status
0x1800d9fc4  mov     ebx, 0C0000001h
0x1800d9fc9  test    eax, eax
0x1800d9fcb  cmovs   ebx, eax
0x1800d9fce  mov     [rsp+128h+var_C0], ebx
0x1800d9fd2  xor     edi, edi
0x1800d9fd4  mov     r15, [rsp+128h+var_60]
0x1800d9fdc  mov     rax, [rsp+128h+var_58]
0x1800d9fe4  mov     [rsp+128h+var_A8], rax
0x1800d9fec  mov     r13, [rsp+128h+var_88]
0x1800d9ff4  mov     rcx, [rsp+128h+var_90]
0x1800d9ffc  mov     esi, 3
0x1800da001  mov     [rsp+128h+var_BC], esi
0x1800da005  mov     r12d, edi
0x1800da008  mov     [rsp+128h+var_B8], edi
0x1800da00c  cmp     ebx, 0C0020012h
0x1800da012  jz      short loc_1800DA020
0x1800da014  cmp     ebx, 0C002002Eh
0x1800da01a  jnz     loc_1800DA1A4
0x1800da020  mov     [rsp+128h+Size], rdi
0x1800da025  mov     dword ptr [rsp+128h+var_D0], 2
0x1800da02d  mov     dword ptr [rsp+128h+var_D8], edi
0x1800da031  mov     [rsp+128h+var_E0], rcx
0x1800da036  mov     dword ptr [rsp+128h+var_E8], 1
0x1800da03e  lea     rcx, [rsp+128h+var_70]
0x1800da046  mov     [rsp+128h+var_F0], rcx
0x1800da04b  mov     [rsp+128h+var_F8], r13
0x1800da050  mov     [rsp+128h+var_100], rax
0x1800da055  mov     dword ptr [rsp+128h+var_108], 1
0x1800da05d  mov     r9, [r15+8]
0x1800da061  xor     r8d, r8d; pReturnValue
0x1800da064  lea     edx, [r8+3Ah]; nProcNum
0x1800da068  lea     rcx, pProxyInfo; pProxyInfo
0x1800da06f  call    cs:__imp_NdrClientCall3
0x1800da075  mov     [rsp+128h+Size], rax
0x1800da07a  mov     ebx, eax
0x1800da07c  mov     [rsp+128h+var_C0], eax
0x1800da080  mov     esi, 2
0x1800da085  mov     [rsp+128h+var_BC], esi
0x1800da089  cmp     [rsp+128h+var_68], rdi
0x1800da091  cmovnz  r12d, dword ptr [rsp+128h+var_70]
0x1800da09a  mov     [rsp+128h+var_B8], r12d
0x1800da09f  mov     rax, [rsp+128h+var_A8]
0x1800da0a7  mov     rcx, [rsp+128h+var_90]
0x1800da0af  jmp     short loc_1800DA0F2
0x1800da0b1  mov     ecx, eax; Status
0x1800da0b3  call    cs:__imp_I_RpcMapWin32Status
0x1800da0b9  mov     ebx, 0C0000001h
0x1800da0be  test    eax, eax
0x1800da0c0  cmovs   ebx, eax
0x1800da0c3  mov     [rsp+128h+var_C0], ebx
0x1800da0c7  xor     edi, edi
0x1800da0c9  mov     esi, [rsp+128h+var_BC]
0x1800da0cd  mov     r12d, [rsp+128h+var_B8]
0x1800da0d2  mov     r15, [rsp+128h+var_60]
0x1800da0da  mov     rax, [rsp+128h+var_58]
0x1800da0e2  mov     r13, [rsp+128h+var_88]
0x1800da0ea  mov     rcx, [rsp+128h+var_90]
0x1800da0f2  cmp     ebx, 0C0020012h
0x1800da0f8  jz      short loc_1800DA106
0x1800da0fa  cmp     ebx, 0C002002Eh
0x1800da100  jnz     loc_1800DA1A4
0x1800da106  mov     [rsp+128h+Size], rdi
0x1800da10b  mov     [rsp+128h+var_E0], rcx
0x1800da110  mov     dword ptr [rsp+128h+var_E8], 1
0x1800da118  lea     rcx, [rsp+128h+var_80]
0x1800da120  mov     [rsp+128h+var_F0], rcx
0x1800da125  mov     [rsp+128h+var_F8], r13
0x1800da12a  mov     [rsp+128h+var_100], rax
0x1800da12f  mov     dword ptr [rsp+128h+var_108], 1
0x1800da137  mov     r9, [r15+8]
0x1800da13b  xor     r8d, r8d; pReturnValue
0x1800da13e  lea     edx, [r8+0Eh]; nProcNum
0x1800da142  lea     rcx, pProxyInfo; pProxyInfo
0x1800da149  call    cs:__imp_NdrClientCall3
0x1800da14f  mov     [rsp+128h+Size], rax
0x1800da154  mov     ebx, eax
0x1800da156  mov     [rsp+128h+var_C0], eax
0x1800da15a  mov     esi, 1
0x1800da15f  mov     [rsp+128h+var_BC], esi
0x1800da163  cmp     [rsp+128h+hMem], rdi
0x1800da16b  cmovnz  r12d, dword ptr [rsp+128h+var_80]
0x1800da174  mov     [rsp+128h+var_B8], r12d
0x1800da179  jmp     short loc_1800DA1A4
0x1800da17b  mov     ecx, eax; Status
0x1800da17d  call    cs:__imp_I_RpcMapWin32Status
0x1800da183  mov     ebx, 0C0000001h
0x1800da188  test    eax, eax
0x1800da18a  cmovs   ebx, eax
0x1800da18d  mov     [rsp+128h+var_C0], ebx
0x1800da191  xor     edi, edi
0x1800da193  mov     esi, [rsp+128h+var_BC]
0x1800da197  mov     r12d, [rsp+128h+var_B8]
0x1800da19c  mov     r13, [rsp+128h+var_88]
0x1800da1a4  test    ebx, ebx
0x1800da1a6  js      short loc_1800DA1FF
0x1800da1a8  cmp     esi, 1
0x1800da1ab  jnz     short loc_1800DA1C0
0x1800da1ad  cmp     dword ptr [rsp+128h+var_80], edi
0x1800da1b4  jz      short loc_1800DA1F0
0x1800da1b6  cmp     [rsp+128h+hMem], rdi
0x1800da1be  jz      short loc_1800DA1F0
0x1800da1c0  cmp     esi, 2
0x1800da1c3  jnz     short loc_1800DA1D8
0x1800da1c5  cmp     dword ptr [rsp+128h+var_70], edi
0x1800da1cc  jz      short loc_1800DA1F0
0x1800da1ce  cmp     [rsp+128h+var_68], rdi
0x1800da1d6  jz      short loc_1800DA1F0
0x1800da1d8  cmp     esi, 3
0x1800da1db  jnz     short loc_1800DA1FF
0x1800da1dd  cmp     dword ptr [rsp+128h+var_A0], edi
0x1800da1e4  jz      short loc_1800DA1F0
0x1800da1e6  cmp     [rsp+128h+var_98], rdi
0x1800da1ee  jnz     short loc_1800DA1FF
0x1800da1f0  mov     ebx, 0C00000C3h
0x1800da1f5  mov     rsi, [rsp+128h+var_C8]
0x1800da1fa  jmp     loc_1800DA49C
0x1800da1ff  cmp     esi, 1
0x1800da202  jnz     short loc_1800DA217
0x1800da204  cmp     dword ptr [rsp+128h+var_80], edi
0x1800da20b  jnz     short loc_1800DA217
0x1800da20d  cmp     [rsp+128h+hMem], rdi
0x1800da215  jnz     short loc_1800DA1F0
0x1800da217  cmp     esi, 2
0x1800da21a  jnz     short loc_1800DA22F
0x1800da21c  cmp     dword ptr [rsp+128h+var_70], edi
0x1800da223  jnz     short loc_1800DA22F
0x1800da225  cmp     [rsp+128h+var_68], rdi
0x1800da22d  jnz     short loc_1800DA1F0
0x1800da22f  cmp     esi, 3
0x1800da232  jnz     short loc_1800DA247
0x1800da234  cmp     dword ptr [rsp+128h+var_A0], edi
0x1800da23b  jnz     short loc_1800DA247
0x1800da23d  cmp     [rsp+128h+var_98], rdi
0x1800da245  jnz     short loc_1800DA1F0
0x1800da247  cmp     esi, 2
0x1800da24a  jnz     short loc_1800DA256
0x1800da24c  cmp     [rsp+128h+var_68], rdi
0x1800da254  jnz     short loc_1800DA26D
0x1800da256  cmp     esi, 1
0x1800da259  jnz     loc_1800DA484
0x1800da25f  cmp     [rsp+128h+hMem], rdi
0x1800da267  jz      loc_1800DA484
0x1800da26d  mov     ecx, r12d
0x1800da270  lea     rax, [rcx+rcx*2]
0x1800da274  lea     r15, ds:0[rax*8]
0x1800da27c  mov     edx, 0FFFFFFFFh
0x1800da281  cmp     r15, rdx
0x1800da284  ja      loc_1800DA52E
0x1800da28a  imul    rax, rcx, 1Ch
0x1800da28e  cmp     rax, rdx
0x1800da291  ja      loc_1800DA52E
0x1800da297  lea     ecx, [rax+r15]
0x1800da29b  cmp     ecx, r15d
0x1800da29e  jb      loc_1800DA52E
0x1800da2a4  mov     eax, ecx
0x1800da2a6  mov     [rsp+128h+Size], rax
0x1800da2ab  mov     edx, ecx; uBytes
0x1800da2ad  mov     ecx, 40h ; '@'; uFlags
0x1800da2b2  call    cs:__imp_LocalAlloc
0x1800da2b8  mov     [rsp+128h+var_98], rax
0x1800da2c0  test    rax, rax
0x1800da2c3  jnz     short loc_1800DA2CF
0x1800da2c5  mov     ebx, 0C0000017h
0x1800da2ca  jmp     loc_1800DA1F5
0x1800da2cf  mov     r8, [rsp+128h+Size]; Size
0x1800da2d4  xor     edx, edx; Val
0x1800da2d6  mov     rcx, rax; void *
0x1800da2d9  call    memset_0
0x1800da2de  mov     rax, [rsp+128h+var_98]
0x1800da2e6  add     rax, r15
0x1800da2e9  mov     [rsp+128h+var_A8], rax
0x1800da2f1  mov     r15d, edi
0x1800da2f4  cmp     r15d, r12d
0x1800da2f7  jnb     loc_1800DA47C
0x1800da2fd  mov     edx, r15d
0x1800da300  cmp     esi, 1
0x1800da303  jnz     short loc_1800DA31A
0x1800da305  mov     r10d, edi
0x1800da308  lea     rcx, [rdx+rdx*2]
0x1800da30c  mov     rax, [rsp+128h+hMem]
0x1800da314  lea     r8, [rax+rcx*4]
0x1800da318  jmp     short loc_1800DA32D
0x1800da31a  mov     r8, rdx
0x1800da31d  shl     r8, 4
0x1800da321  add     r8, [rsp+128h+var_68]
0x1800da329  mov     r10d, [r8+0Ch]
0x1800da32d  mov     ecx, [r8]
0x1800da330  mov     eax, [r8+4]
0x1800da334  mov     dword ptr [rsp+128h+var_90], eax
0x1800da33b  mov     r9d, [r8+8]
0x1800da33f  lea     r13, [rdx+rdx*2]
0x1800da343  mov     rax, [rsp+128h+var_98]
0x1800da34b  mov     [rax+r13*8], ecx
0x1800da34f  mov     rax, [rsp+128h+var_98]
0x1800da357  mov     [rax+r13*8+10h], r9d
0x1800da35c  mov     rax, [rsp+128h+var_98]
0x1800da364  mov     [rax+r13*8+14h], r10d
0x1800da369  lea     eax, [rcx-6]
0x1800da36c  cmp     eax, 2
0x1800da36f  jbe     loc_1800DA45A
0x1800da375  mov     eax, 0FFFFFFFFh
0x1800da37a  cmp     r9d, eax
0x1800da37d  jz      loc_1800DA46F
0x1800da383  lea     rdx, [r9+r9*2]
0x1800da387  mov     rax, [rsp+128h+var_88]
0x1800da38f  mov     rax, [rax]
0x1800da392  mov     rcx, [rax+8]
0x1800da396  mov     rax, [rcx+rdx*8+10h]
0x1800da39b  mov     [rsp+128h+Size], rax
0x1800da3a0  mov     rcx, rax; Sid
0x1800da3a3  call    cs:__imp_RtlLengthSid
0x1800da3a9  cmp     eax, 18h
0x1800da3ac  ja      loc_1800DA46F
0x1800da3b2  mov     r8, [rsp+128h+Size]; SourceSid
0x1800da3b7  lea     rdx, [rsp+128h+DestinationSid]; DestinationSid
0x1800da3bf  mov     ecx, 1Ch; DestinationSidLength
0x1800da3c4  call    cs:__imp_RtlCopySid
0x1800da3ca  mov     eax, 0FFFFFFFFh
0x1800da3cf  cmp     dword ptr [rsp+128h+var_90], eax
0x1800da3d6  jz      short loc_1800DA405
0x1800da3d8  lea     rcx, [rsp+128h+DestinationSid]; Sid
0x1800da3e0  call    cs:__imp_RtlSubAuthorityCountSid
0x1800da3e6  movzx   edx, byte ptr [rax]; SubAuthority
0x1800da3e9  lea     ecx, [rdx+1]
0x1800da3ec  mov     [rax], cl
0x1800da3ee  lea     rcx, [rsp+128h+DestinationSid]; Sid
0x1800da3f6  call    cs:__imp_RtlSubAuthoritySid
0x1800da3fc  mov     ecx, dword ptr [rsp+128h+var_90]
0x1800da403  mov     [rax], ecx
0x1800da405  lea     rcx, [rsp+128h+DestinationSid]; Sid
0x1800da40d  call    cs:__imp_RtlLengthSid
0x1800da413  lea     r8, [rsp+128h+DestinationSid]; SourceSid
0x1800da41b  mov     rdx, [rsp+128h+var_A8]; DestinationSid
0x1800da423  mov     ecx, eax; DestinationSidLength
0x1800da425  call    cs:__imp_RtlCopySid
0x1800da42b  mov     rax, [rsp+128h+var_98]
0x1800da433  mov     rcx, [rsp+128h+var_A8]
0x1800da43b  mov     [rax+r13*8+8], rcx
0x1800da440  lea     rcx, [rsp+128h+DestinationSid]; Sid
0x1800da448  call    cs:__imp_RtlLengthSid
0x1800da44e  mov     eax, eax
0x1800da450  add     [rsp+128h+var_A8], rax
  ... truncated ...
```
