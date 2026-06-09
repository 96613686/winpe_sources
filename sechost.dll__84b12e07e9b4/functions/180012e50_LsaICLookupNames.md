# LsaICLookupNames

- ea: `0x180012e50`
- end: `0x18001361b`
- name: `LsaICLookupNames`
- size: `1995`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180018390`

## callees

- `0x180012e50`
- `0x18003ee8c`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800134ae`
- `ntdll!RtlCopySid` at `0x180013509`
- `ntdll!RtlCopySid` at `0x1800134ae`
- `ntdll!RtlCopySid` at `0x180013509`
- `ntdll!RtlSubAuthoritySid` at `0x1800134dd`
- `ntdll!RtlSubAuthoritySid` at `0x1800134dd`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800134c7`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800134c7`
- `ntdll!RtlLengthSid` at `0x18001348a`
- `ntdll!RtlLengthSid` at `0x1800134f1`
- `ntdll!RtlLengthSid` at `0x18001352c`
- `ntdll!RtlLengthSid` at `0x18001348a`
- `ntdll!RtlLengthSid` at `0x1800134f1`
- `ntdll!RtlLengthSid` at `0x18001352c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001338d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001338d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001359e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001359e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135e6`
- `RPCRT4!NdrClientCall3` at `0x180012ffa`
- `RPCRT4!NdrClientCall3` at `0x1800131ed`
- `RPCRT4!NdrClientCall3` at `0x180012ffa`
- `RPCRT4!NdrClientCall3` at `0x1800131ed`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005003e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005005a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050076`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005003e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005005a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050076`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013037`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001312e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013233`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013037`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001312e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013233`

## pseudocode

```c
__int64 __fastcall LsaICLookupNames(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        HLOCAL *a5,
        HLOCAL *a6,
        int a7,
        char a8,
        __int64 a9,
        _DWORD *a10)
{
  __int64 v10; // r10
  int v12; // r8d
  HLOCAL *v14; // r11
  __int64 v15; // r9
  int v17; // esi
  int v18; // eax
  int v19; // eax
  int Pointer; // ebx
  CLIENT_CALL_RETURN v21; // rax
  unsigned int v22; // edx
  int v23; // eax
  unsigned __int64 v24; // r14
  int v25; // eax
  unsigned int v26; // ecx
  size_t v27; // r15
  HLOCAL v28; // rax
  unsigned int i; // r15d
  int v30; // r10d
  int *v31; // r8
  int v32; // ecx
  __int64 v33; // r9
  __int64 v34; // r12
  PUCHAR v35; // rax
  ULONG v36; // edx
  ULONG v37; // eax
  __int64 v38; // [rsp+20h] [rbp-148h]
  __int64 v39; // [rsp+40h] [rbp-128h]
  unsigned int v40; // [rsp+60h] [rbp-108h]
  ULONG v41; // [rsp+68h] [rbp-100h]
  char *v42; // [rsp+88h] [rbp-E0h]
  __int64 v43; // [rsp+90h] [rbp-D8h] BYREF
  HLOCAL v44; // [rsp+98h] [rbp-D0h]
  __int64 v45; // [rsp+A0h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-C0h]
  __int64 v47; // [rsp+B0h] [rbp-B8h] BYREF
  HLOCAL v48; // [rsp+B8h] [rbp-B0h]
  PSID SourceSid; // [rsp+C0h] [rbp-A8h]
  int v50; // [rsp+C8h] [rbp-A0h]
  int v51; // [rsp+D0h] [rbp-98h]
  __int64 v52; // [rsp+D8h] [rbp-90h]
  HLOCAL *v53; // [rsp+E0h] [rbp-88h]
  __int64 v54; // [rsp+E8h] [rbp-80h]
  __int64 v55; // [rsp+F0h] [rbp-78h]
  _DWORD *v56; // [rsp+F8h] [rbp-70h]
  _BYTE DestinationSid[32]; // [rsp+100h] [rbp-68h] BYREF

  v10 = a4;
  v52 = a4;
  v12 = a2;
  v50 = a2;
  v54 = a1;
  v51 = a2;
  v55 = a4;
  v53 = a5;
  v14 = a6;
  v15 = a9;
  v56 = a10;
  v43 = 0;
  v44 = 0;
  v47 = 0;
  v48 = 0;
  v45 = 0;
  hMem = 0;
  *a5 = 0;
  *a6 = 0;
  if ( !a1 )
    return 3221225480LL;
  if ( a3 > 0x3E8 )
    return 3221225677LL;
  v17 = 3;
  v40 = 0;
  if ( a10 )
    *a10 = 2;
  v18 = 3;
  if ( (a8 & 5) != 0 )
    v18 = 2;
  if ( (a8 & 2) != 0 )
  {
    v18 = 1;
LABEL_12:
    v19 = v18 - 1;
    if ( !v19 )
    {
LABEL_21:
      if ( a10 )
        *a10 = 1;
      SourceSid = 0;
      LODWORD(v39) = a7;
      LODWORD(v38) = a3;
      SourceSid = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0,
                    0xEu,
                    0,
                    *(_QWORD *)(a1 + 8),
                    v38,
                    v10,
                    a5,
                    &v45,
                    v39,
                    v15).Pointer;
      Pointer = (int)SourceSid;
      v17 = 1;
      v22 = v40;
      if ( hMem )
        v22 = v45;
      v40 = v22;
      v14 = a6;
      goto LABEL_26;
    }
    if ( v19 != 1 )
    {
      Pointer = -1073741811;
      goto LABEL_74;
    }
LABEL_17:
    Pointer = LsarLookupNames2(*(_QWORD *)(a1 + 8), a3, v10, (_DWORD)a5, (__int64)&v47, a7, v15, v12);
    v17 = 2;
    v22 = 0;
    if ( v48 )
      v22 = v47;
    v40 = v22;
    v10 = v52;
    v15 = a9;
    v14 = a6;
    if ( Pointer != -1073610734 && Pointer != -1073610706 )
      goto LABEL_26;
    goto LABEL_21;
  }
  if ( v18 != 3 )
    goto LABEL_12;
  SourceSid = 0;
  v21.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0,
                  0x44u,
                  0,
                  *(_QWORD *)(a1 + 8),
                  a3,
                  v10,
                  a5,
                  &v43,
                  a7,
                  a9,
                  a2,
                  2).Pointer;
  Pointer = (int)v21.Pointer;
  SourceSid = (PSID)v21.Simple;
  v22 = 0;
  v12 = v50;
  LODWORD(v10) = v52;
  v15 = a9;
  v14 = a6;
  if ( LODWORD(v21.Pointer) == -1073610734 || LODWORD(v21.Pointer) == -1073610706 )
    goto LABEL_17;
LABEL_26:
  if ( Pointer < 0 || !a3 )
    goto LABEL_38;
  if ( v17 == 1 && (!(_DWORD)v45 || !hMem) || v17 == 2 && (!(_DWORD)v47 || !v48) )
    goto LABEL_37;
  if ( v17 == 3 )
  {
    v23 = v43;
    if ( !(_DWORD)v43 || !v44 )
    {
LABEL_37:
      Pointer = -1073741629;
      goto LABEL_74;
    }
  }
  else
  {
LABEL_38:
    v23 = v43;
  }
  if ( v17 == 1 && !(_DWORD)v45 && hMem || v17 == 2 && !(_DWORD)v47 && v48 )
    goto LABEL_37;
  if ( v17 == 3 && !v23 && v44 )
  {
    Pointer = -1073741629;
    goto LABEL_74;
  }
  if ( (v17 != 2 || !v48) && (v17 != 1 || !hMem) )
  {
LABEL_73:
    *v14 = v44;
    v44 = 0;
    goto LABEL_74;
  }
  v24 = 24LL * v22;
  if ( v24 <= 0xFFFFFFFF )
  {
    v25 = 28 * v22;
    if ( 28 * (unsigned __int64)v22 <= 0xFFFFFFFF )
    {
      v26 = v25 + v24;
      if ( v25 + (int)v24 >= (unsigned int)v24 )
      {
        v27 = v26;
        v28 = LocalAlloc(0x40u, v26);
        v44 = v28;
        if ( !v28 )
        {
          Pointer = -1073741801;
          v14 = a6;
          goto LABEL_74;
        }
        memset_0(v28, 0, v27);
        v42 = (char *)v44 + v24;
        for ( i = 0; i < v40; ++i )
        {
          if ( v17 == 1 )
          {
            v30 = 0;
            v31 = (int *)((char *)hMem + 12 * i);
          }
          else
          {
            v31 = (int *)((char *)v48 + 16 * i);
            v30 = v31[3];
          }
          v32 = *v31;
          v41 = v31[1];
          v33 = (unsigned int)v31[2];
          v34 = 24LL * i;
          *(_DWORD *)((char *)v44 + v34) = *v31;
          *(_DWORD *)((char *)v44 + v34 + 16) = v33;
          *(_DWORD *)((char *)v44 + v34 + 20) = v30;
          if ( (unsigned int)(v32 - 6) <= 2 )
          {
            *(_QWORD *)((char *)v44 + v34 + 8) = 0;
          }
          else
          {
            if ( (_DWORD)v33 == -1
              || (SourceSid = *(PSID *)(*((_QWORD *)*a5 + 1) + 24 * v33 + 16), RtlLengthSid(SourceSid) > 0x18) )
            {
              Pointer = -1073741629;
              v14 = a6;
              goto LABEL_74;
            }
            RtlCopySid(0x1Cu, DestinationSid, SourceSid);
            if ( v41 != -1 )
            {
              v35 = RtlSubAuthorityCountSid(DestinationSid);
              v36 = *v35;
              *v35 = v36 + 1;
              *RtlSubAuthoritySid(DestinationSid, v36) = v41;
            }
            v37 = RtlLengthSid(DestinationSid);
            RtlCopySid(v37, v42, DestinationSid);
            *(_QWORD *)((char *)v44 + v34 + 8) = v42;
            v42 += RtlLengthSid(DestinationSid);
          }
        }
        v14 = a6;
        goto LABEL_73;
      }
    }
  }
  Pointer = -1073741675;
LABEL_74:
  if ( Pointer == -1073741629 || Pointer == -1073741801 || Pointer == -1073741675 )
  {
    if ( *a5 )
    {
      LocalFree(*a5);
      *a5 = 0;
      v14 = a6;
    }
    *v14 = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v48 )
    LocalFree(v48);
  if ( v44 )
    LocalFree(v44);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180012e50  push    rbx
0x180012e52  push    rsi
0x180012e53  push    rdi
0x180012e54  push    r12
0x180012e56  push    r13
0x180012e58  push    r14
0x180012e5a  push    r15
0x180012e5c  sub     rsp, 130h
0x180012e63  mov     rax, cs:__security_cookie
0x180012e6a  xor     rax, rsp
0x180012e6d  mov     [rsp+168h+var_48], rax
0x180012e75  mov     r10, r9
0x180012e78  mov     [rsp+168h+var_90], r9
0x180012e80  mov     r14d, r8d
0x180012e83  mov     r8d, edx
0x180012e86  mov     [rsp+168h+var_A0], edx
0x180012e8d  mov     r15, rcx
0x180012e90  mov     [rsp+168h+var_80], rcx
0x180012e98  mov     [rsp+168h+var_98], edx
0x180012e9f  mov     [rsp+168h+var_100], r14d
0x180012ea4  mov     [rsp+168h+var_78], r9
0x180012eac  mov     r13, [rsp+168h+arg_20]
0x180012eb4  mov     [rsp+168h+var_88], r13
0x180012ebc  mov     r11, [rsp+168h+arg_28]
0x180012ec4  mov     [rsp+168h+var_E8], r11
0x180012ecc  mov     r9, [rsp+168h+arg_40]
0x180012ed4  mov     [rsp+168h+var_E0], r9
0x180012edc  mov     r12, [rsp+168h+arg_48]
0x180012ee4  mov     [rsp+168h+var_70], r12
0x180012eec  xor     edi, edi
0x180012eee  mov     [rsp+168h+var_D8], rdi
0x180012ef6  mov     [rsp+168h+var_D0], rdi
0x180012efe  mov     [rsp+168h+var_B8], rdi
0x180012f06  mov     [rsp+168h+var_B0], rdi
0x180012f0e  mov     [rsp+168h+var_C8], rdi
0x180012f16  mov     [rsp+168h+hMem], rdi
0x180012f1e  mov     [r13+0], rdi
0x180012f22  mov     [r11], rdi
0x180012f25  test    rcx, rcx
0x180012f28  jnz     short loc_180012F34
0x180012f2a  mov     eax, 0C0000008h
0x180012f2f  jmp     loc_1800135EE
0x180012f34  cmp     r14d, 3E8h
0x180012f3b  jbe     short loc_180012F47
0x180012f3d  mov     eax, 0C00000CDh
0x180012f42  jmp     loc_1800135EE
0x180012f47  mov     esi, 3
0x180012f4c  mov     [rsp+168h+var_F4], esi
0x180012f50  mov     edx, edi
0x180012f52  mov     [rsp+168h+var_108], edx
0x180012f56  mov     [rsp+168h+var_F0], edx
0x180012f5a  test    r12, r12
0x180012f5d  jz      short loc_180012F67
0x180012f5f  mov     dword ptr [r12], 2
0x180012f67  mov     eax, esi
0x180012f69  mov     ecx, dword ptr [rsp+168h+arg_38]
0x180012f70  test    cl, 5
0x180012f73  jz      short loc_180012F7A
0x180012f75  mov     eax, 2
0x180012f7a  test    cl, 2
0x180012f7d  jz      short loc_180012F86
0x180012f7f  mov     eax, 1
0x180012f84  jmp     short loc_180012F8A
0x180012f86  cmp     eax, esi
0x180012f88  jz      short loc_180012FA6
0x180012f8a  sub     eax, 1
0x180012f8d  jz      loc_180013199
0x180012f93  cmp     eax, 1
0x180012f96  jz      loc_1800130B2
0x180012f9c  mov     ebx, 0C000000Dh
0x180012fa1  jmp     loc_18001357D
0x180012fa6  mov     [rsp+168h+SourceSid], rdi
0x180012fae  mov     [rsp+168h+var_110], 2
0x180012fb6  mov     [rsp+168h+var_118], r8d
0x180012fbb  mov     [rsp+168h+var_120], r9
0x180012fc0  mov     eax, [rsp+168h+arg_30]
0x180012fc7  mov     dword ptr [rsp+168h+var_128], eax
0x180012fcb  lea     rax, [rsp+168h+var_D8]
0x180012fd3  mov     [rsp+168h+var_130], rax
0x180012fd8  mov     [rsp+168h+var_138], r13
0x180012fdd  mov     [rsp+168h+var_140], r10
0x180012fe2  mov     dword ptr [rsp+168h+var_148], r14d
0x180012fe7  mov     r9, [r15+8]
0x180012feb  xor     r8d, r8d; pReturnValue
0x180012fee  mov     edx, 44h ; 'D'; nProcNum
0x180012ff3  lea     rcx, stru_1800524F0; pProxyInfo
0x180012ffa  call    cs:__imp_NdrClientCall3
0x180013000  mov     rbx, rax
0x180013003  mov     [rsp+168h+SourceSid], rax
0x18001300b  mov     [rsp+168h+var_F8], eax
0x18001300f  mov     edx, [rsp+168h+var_108]
0x180013013  mov     r8d, [rsp+168h+var_A0]
0x18001301b  mov     r10, [rsp+168h+var_90]
0x180013023  mov     r9, [rsp+168h+var_E0]
0x18001302b  mov     r11, [rsp+168h+var_E8]
0x180013033  jmp     short loc_18001309E
0x180013035  mov     ecx, eax; Status
0x180013037  call    cs:__imp_I_RpcMapWin32Status
0x18001303d  mov     ebx, 0C0000001h
0x180013042  test    eax, eax
0x180013044  cmovs   ebx, eax
0x180013047  mov     [rsp+168h+var_F8], ebx
0x18001304b  xor     edi, edi
0x18001304d  mov     esi, [rsp+168h+var_F4]
0x180013051  mov     edx, [rsp+168h+var_F0]
0x180013055  mov     [rsp+168h+var_108], edx
0x180013059  mov     r15, [rsp+168h+var_80]
0x180013061  mov     r8d, [rsp+168h+var_98]
0x180013069  mov     r14d, [rsp+168h+var_100]
0x18001306e  mov     r10, [rsp+168h+var_78]
0x180013076  mov     [rsp+168h+var_90], r10
0x18001307e  mov     r13, [rsp+168h+var_88]
0x180013086  mov     r11, [rsp+168h+var_E8]
0x18001308e  mov     r9, [rsp+168h+var_E0]
0x180013096  mov     r12, [rsp+168h+var_70]
0x18001309e  cmp     ebx, 0C0020012h
0x1800130a4  jz      short loc_1800130B2
0x1800130a6  cmp     ebx, 0C002002Eh
0x1800130ac  jnz     loc_18001326A
0x1800130b2  mov     dword ptr [rsp+168h+var_130], r8d
0x1800130b7  mov     [rsp+168h+var_138], r9
0x1800130bc  mov     eax, [rsp+168h+arg_30]
0x1800130c3  mov     dword ptr [rsp+168h+var_140], eax
0x1800130c7  lea     rax, [rsp+168h+var_B8]
0x1800130cf  mov     [rsp+168h+var_148], rax
0x1800130d4  mov     r9, r13
0x1800130d7  mov     r8, r10
0x1800130da  mov     edx, r14d
0x1800130dd  mov     rcx, [r15+8]
0x1800130e1  call    LsarLookupNames2
0x1800130e6  mov     ebx, eax
0x1800130e8  mov     [rsp+168h+var_F8], eax
0x1800130ec  mov     esi, 2
0x1800130f1  mov     [rsp+168h+var_F4], esi
0x1800130f5  mov     edx, [rsp+168h+var_108]
0x1800130f9  cmp     [rsp+168h+var_B0], 0
0x180013102  cmovnz  edx, dword ptr [rsp+168h+var_B8]
0x18001310a  mov     [rsp+168h+var_108], edx
0x18001310e  mov     [rsp+168h+var_F0], edx
0x180013112  mov     r10, [rsp+168h+var_90]
0x18001311a  mov     r9, [rsp+168h+var_E0]
0x180013122  mov     r11, [rsp+168h+var_E8]
0x18001312a  jmp     short loc_180013185
0x18001312c  mov     ecx, eax; Status
0x18001312e  call    cs:__imp_I_RpcMapWin32Status
0x180013134  mov     ebx, 0C0000001h
0x180013139  test    eax, eax
0x18001313b  cmovs   ebx, eax
0x18001313e  mov     [rsp+168h+var_F8], ebx
0x180013142  xor     edi, edi
0x180013144  mov     esi, [rsp+168h+var_F4]
0x180013148  mov     edx, [rsp+168h+var_F0]
0x18001314c  mov     [rsp+168h+var_108], edx
0x180013150  mov     r15, [rsp+168h+var_80]
0x180013158  mov     r14d, [rsp+168h+var_100]
0x18001315d  mov     r10, [rsp+168h+var_78]
0x180013165  mov     r13, [rsp+168h+var_88]
0x18001316d  mov     r11, [rsp+168h+var_E8]
0x180013175  mov     r9, [rsp+168h+var_E0]
0x18001317d  mov     r12, [rsp+168h+var_70]
0x180013185  cmp     ebx, 0C0020012h
0x18001318b  jz      short loc_180013199
0x18001318d  cmp     ebx, 0C002002Eh
0x180013193  jnz     loc_18001326A
0x180013199  test    r12, r12
0x18001319c  jz      short loc_1800131A6
0x18001319e  mov     dword ptr [r12], 1
0x1800131a6  mov     [rsp+168h+SourceSid], rdi
0x1800131ae  mov     [rsp+168h+var_120], r9
0x1800131b3  mov     eax, [rsp+168h+arg_30]
0x1800131ba  mov     dword ptr [rsp+168h+var_128], eax
0x1800131be  lea     rax, [rsp+168h+var_C8]
0x1800131c6  mov     [rsp+168h+var_130], rax
0x1800131cb  mov     [rsp+168h+var_138], r13
0x1800131d0  mov     [rsp+168h+var_140], r10
0x1800131d5  mov     dword ptr [rsp+168h+var_148], r14d
0x1800131da  mov     r9, [r15+8]
0x1800131de  xor     r8d, r8d; pReturnValue
0x1800131e1  mov     edx, 0Eh; nProcNum
0x1800131e6  lea     rcx, stru_1800524F0; pProxyInfo
0x1800131ed  call    cs:__imp_NdrClientCall3
0x1800131f3  mov     [rsp+168h+SourceSid], rax
0x1800131fb  mov     ebx, eax
0x1800131fd  mov     [rsp+168h+var_F8], eax
0x180013201  mov     esi, 1
0x180013206  mov     [rsp+168h+var_F4], esi
0x18001320a  mov     edx, [rsp+168h+var_108]
0x18001320e  cmp     [rsp+168h+hMem], 0
0x180013217  cmovnz  edx, dword ptr [rsp+168h+var_C8]
0x18001321f  mov     [rsp+168h+var_108], edx
0x180013223  mov     [rsp+168h+var_F0], edx
0x180013227  mov     r11, [rsp+168h+var_E8]
0x18001322f  jmp     short loc_18001326A
0x180013231  mov     ecx, eax; Status
0x180013233  call    cs:__imp_I_RpcMapWin32Status
0x180013239  mov     ebx, 0C0000001h
0x18001323e  test    eax, eax
0x180013240  cmovs   ebx, eax
0x180013243  mov     [rsp+168h+var_F8], ebx
0x180013247  xor     edi, edi
0x180013249  mov     esi, [rsp+168h+var_F4]
0x18001324d  mov     edx, [rsp+168h+var_F0]
0x180013251  mov     [rsp+168h+var_108], edx
0x180013255  mov     r14d, [rsp+168h+var_100]
0x18001325a  mov     r13, [rsp+168h+var_88]
0x180013262  mov     r11, [rsp+168h+var_E8]
0x18001326a  test    ebx, ebx
0x18001326c  js      short loc_1800132CC
0x18001326e  test    r14d, r14d
0x180013271  jz      short loc_1800132CC
0x180013273  cmp     esi, 1
0x180013276  jnz     short loc_18001328D
0x180013278  cmp     dword ptr [rsp+168h+var_C8], 0
0x180013280  jz      short loc_1800132C2
0x180013282  cmp     [rsp+168h+hMem], 0
0x18001328b  jz      short loc_1800132C2
0x18001328d  cmp     esi, 2
0x180013290  jnz     short loc_1800132A7
0x180013292  cmp     dword ptr [rsp+168h+var_B8], 0
0x18001329a  jz      short loc_1800132C2
0x18001329c  cmp     [rsp+168h+var_B0], 0
0x1800132a5  jz      short loc_1800132C2
0x1800132a7  cmp     esi, 3
0x1800132aa  jnz     short loc_1800132CC
0x1800132ac  mov     eax, dword ptr [rsp+168h+var_D8]
0x1800132b3  test    eax, eax
0x1800132b5  jz      short loc_1800132C2
0x1800132b7  cmp     [rsp+168h+var_D0], 0
0x1800132c0  jnz     short loc_1800132D3
0x1800132c2  mov     ebx, 0C00000C3h
0x1800132c7  jmp     loc_18001357D
0x1800132cc  mov     eax, dword ptr [rsp+168h+var_D8]
0x1800132d3  cmp     esi, 1
0x1800132d6  jnz     short loc_1800132ED
0x1800132d8  cmp     dword ptr [rsp+168h+var_C8], 0
0x1800132e0  jnz     short loc_1800132ED
0x1800132e2  cmp     [rsp+168h+hMem], 0
0x1800132eb  jnz     short loc_1800132C2
0x1800132ed  cmp     esi, 2
0x1800132f0  jnz     short loc_180013307
0x1800132f2  cmp     dword ptr [rsp+168h+var_B8], 0
0x1800132fa  jnz     short loc_180013307
0x1800132fc  cmp     [rsp+168h+var_B0], 0
0x180013305  jnz     short loc_1800132C2
0x180013307  cmp     esi, 3
0x18001330a  jnz     short loc_180013325
0x18001330c  test    eax, eax
0x18001330e  jnz     short loc_180013325
0x180013310  cmp     [rsp+168h+var_D0], 0
0x180013319  jz      short loc_180013325
0x18001331b  mov     ebx, 0C00000C3h
0x180013320  jmp     loc_18001357D
0x180013325  cmp     esi, 2
0x180013328  jnz     short loc_180013335
0x18001332a  cmp     [rsp+168h+var_B0], 0
0x180013333  jnz     short loc_18001334D
0x180013335  cmp     esi, 1
0x180013338  jnz     loc_18001356A
0x18001333e  cmp     [rsp+168h+hMem], 0
0x180013347  jz      loc_18001356A
0x18001334d  mov     ecx, edx
0x18001334f  lea     rax, [rcx+rcx*2]
0x180013353  lea     r14, ds:0[rax*8]
0x18001335b  mov     edx, 0FFFFFFFFh
0x180013360  cmp     r14, rdx
0x180013363  ja      loc_180013611
0x180013369  imul    rax, rcx, 1Ch
0x18001336d  cmp     rax, rdx
0x180013370  ja      loc_180013611
0x180013376  lea     ecx, [rax+r14]
0x18001337a  cmp     ecx, r14d
0x18001337d  jb      loc_180013611
0x180013383  mov     r15d, ecx
0x180013386  mov     edx, ecx; uBytes
0x180013388  mov     ecx, 40h ; '@'; uFlags
0x18001338d  call    cs:__imp_LocalAlloc
0x180013393  mov     [rsp+168h+var_D0], rax
0x18001339b  test    rax, rax
0x18001339e  jnz     short loc_1800133B2
0x1800133a0  mov     ebx, 0C0000017h
0x1800133a5  mov     r11, [rsp+168h+var_E8]
0x1800133ad  jmp     loc_18001357D
0x1800133b2  mov     r8, r15; Size
0x1800133b5  xor     edx, edx; Val
0x1800133b7  mov     rcx, rax; void *
0x1800133ba  call    memset_0
0x1800133bf  mov     rax, [rsp+168h+var_D0]
0x1800133c7  add     rax, r14
0x1800133ca  mov     [rsp+168h+var_E0], rax
0x1800133d2  mov     r15d, edi
0x1800133d5  mov     r14d, [rsp+168h+var_108]
0x1800133da  cmp     r15d, r14d
0x1800133dd  jnb     loc_180013562
0x1800133e3  mov     edx, r15d
0x1800133e6  cmp     esi, 1
0x1800133e9  jnz     short loc_180013400
0x1800133eb  mov     r10d, edi
0x1800133ee  lea     rcx, [rdx+rdx*2]
0x1800133f2  mov     rax, [rsp+168h+hMem]
0x1800133fa  lea     r8, [rax+rcx*4]
  ... truncated ...
```
