# SamOpenUser

- ea: `0x180002e90`
- end: `0x180003211`
- name: `SamOpenUser`
- size: `897`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008590`
- `0x18000918c`

## callees

- `0x180002e90`
- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000baf8`
- `0x18000bfa8`
- `0x180014a50`
- `0x180014ae0`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003048`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003143`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003158`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003048`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003143`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003158`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002fac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003026`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002fac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003026`
- `ntdll!RtlLengthSid` at `0x180003017`
- `ntdll!RtlLengthSid` at `0x180003017`
- `ntdll!RtlCopySid` at `0x18000303d`
- `ntdll!RtlCopySid` at `0x18000303d`
- `RPCRT4!NdrClientCall3` at `0x1800030ce`
- `RPCRT4!NdrClientCall3` at `0x1800030ce`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003111`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003111`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017b7e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017b7e`

## pseudocode

```c
__int64 __fastcall SamOpenUser(void *a1, int a2, __int64 a3, __int64 *a4)
{
  int v5; // r12d
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v9; // rdi
  const wchar_t *v10; // rcx
  PVOID v11; // rcx
  _QWORD *v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  void *v16; // r15
  SIZE_T v17; // rbx
  HLOCAL v18; // rax
  CLIENT_CALL_RETURN v19; // rax
  unsigned int Pointer; // ebx
  void *v21; // rcx
  PVOID v22; // rcx
  __int64 v23; // r9
  __int64 v24; // [rsp+20h] [rbp-78h]
  __int64 v25; // [rsp+28h] [rbp-70h]
  void *v26; // [rsp+48h] [rbp-50h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h] BYREF
  CLIENT_CALL_RETURN v28; // [rsp+58h] [rbp-40h]
  _QWORD *v29; // [rsp+60h] [rbp-38h]

  v5 = a3;
  v26 = 0;
  v27 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v9 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v10 = L"<unknown>";
      if ( CallingProcessInfo )
        v10 = CallingProcessInfo;
      McTemplateU0pqqz_EventWriteTransfer((_DWORD)v10, (unsigned int)SamOpenUserEntry, (_DWORD)a1, a2, v5, (__int64)v10);
    }
    LocalFree(v9);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, a3, a1, a2, v5);
  if ( !SampIsValidClientHandle(a1, &v26) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dp_EventWriteTransfer(v11, SamOpenUserExit, 3221225480LL, 0);
    return 3221225480LL;
  }
  v13 = LocalAlloc(0x40u, 0x18u);
  v29 = v13;
  if ( v13 )
  {
    v16 = 0;
    *(_OWORD *)v13 = 0;
    v13[2] = 0;
    if ( a1 )
    {
      v13[1] = *((_QWORD *)a1 + 1);
      if ( *((_QWORD *)a1 + 2) )
        v16 = (void *)*((_QWORD *)a1 + 2);
    }
    if ( v16 )
    {
      v17 = RtlLengthSid(v16);
      v18 = LocalAlloc(0x40u, v17);
      v13[2] = v18;
      if ( !v18 )
      {
        LocalFree(v13);
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_31;
        v15 = 45;
        goto LABEL_30;
      }
      RtlCopySid(v17, v18, v16);
    }
    *a4 = 0;
    v28.Simple = 0;
    LODWORD(v25) = v5;
    LODWORD(v24) = a2;
    v19.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x22u, 0, v26, v24, v25, &v27).Pointer;
    Pointer = (unsigned int)v19.Pointer;
    v28.Pointer = v19.Pointer;
    if ( SLODWORD(v19.Simple) < 0 )
    {
      v21 = (void *)v13[2];
      if ( v21 )
        LocalFree(v21);
      *(_OWORD *)v13 = 0;
      v13[2] = 0;
      LocalFree(v13);
      v13 = 0;
    }
    else
    {
      *v13 = v27;
    }
    *a4 = (__int64)v13;
    if ( Pointer == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return Pointer;
      v23 = 0;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v13);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return Pointer;
      v23 = *a4;
    }
    McTemplateU0dp_EventWriteTransfer(v22, SamOpenUserExit, Pointer, v23);
    return Pointer;
  }
  v14 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_31;
  v15 = 44;
LABEL_30:
  WPP_SF_(v14[2], v15, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
LABEL_31:
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dp_EventWriteTransfer(v14, SamOpenUserExit, 3221225495LL, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  mov     [rsp+arg_8], rsi
0x180002e9a  mov     [rsp+arg_18], r9
0x180002e9f  push    rdi
0x180002ea0  push    r12
0x180002ea2  push    r13
0x180002ea4  push    r14
0x180002ea6  push    r15
0x180002ea8  sub     rsp, 70h
0x180002eac  mov     r14, r9
0x180002eaf  mov     r12d, r8d
0x180002eb2  mov     r13d, edx
0x180002eb5  mov     rbx, rcx
0x180002eb8  xor     esi, esi
0x180002eba  mov     [rsp+98h+var_50], rsi
0x180002ebf  mov     [rsp+98h+var_48], rsi
0x180002ec4  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002ecb  jz      short loc_180002F11
0x180002ecd  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180002ed2  mov     rdi, rax
0x180002ed5  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002edc  jz      short loc_180002F08
0x180002ede  lea     rcx, aUnknown; "<unknown>"
0x180002ee5  test    rax, rax
0x180002ee8  cmovnz  rcx, rax
0x180002eec  mov     [rsp+98h+var_70], rcx
0x180002ef1  mov     dword ptr [rsp+98h+var_78], r12d
0x180002ef6  mov     r9d, r13d
0x180002ef9  mov     r8, rbx
0x180002efc  lea     rdx, SamOpenUserEntry
0x180002f03  call    McTemplateU0pqqz_EventWriteTransfer
0x180002f08  mov     rcx, rdi; hMem
0x180002f0b  call    cs:__imp_LocalFree
0x180002f11  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f18  test    byte ptr [rcx+1Ch], 2
0x180002f1c  jz      short loc_180002F3F
0x180002f1e  cmp     byte ptr [rcx+19h], 4
0x180002f22  jb      short loc_180002F3F
0x180002f24  mov     edx, 0E4h
0x180002f29  mov     dword ptr [rsp+98h+var_70], r12d
0x180002f2e  mov     dword ptr [rsp+98h+var_78], r13d
0x180002f33  mov     r9, rbx
0x180002f36  mov     rcx, [rcx+10h]
0x180002f3a  call    WPP_SF_qDD
0x180002f3f  lea     rdx, [rsp+98h+var_50]; void **
0x180002f44  mov     rcx, rbx; void *
0x180002f47  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180002f4c  test    al, al
0x180002f4e  jnz     short loc_180002FA2
0x180002f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f57  test    byte ptr [rcx+1Ch], 2
0x180002f5b  jz      short loc_180002F7B
0x180002f5d  cmp     byte ptr [rcx+19h], 2
0x180002f61  jb      short loc_180002F7B
0x180002f63  mov     edx, 0E5h
0x180002f68  mov     r9, rbx
0x180002f6b  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180002f72  mov     rcx, [rcx+10h]
0x180002f76  call    WPP_SF_q
0x180002f7b  mov     esi, 0C0000008h
0x180002f80  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180002f87  jz      short loc_180002F9B
0x180002f89  xor     r9d, r9d
0x180002f8c  mov     r8d, esi
0x180002f8f  lea     rdx, SamOpenUserExit
0x180002f96  call    McTemplateU0dp_EventWriteTransfer
0x180002f9b  mov     eax, esi
0x180002f9d  jmp     loc_1800031F7
0x180002fa2  mov     edx, 18h; uBytes
0x180002fa7  mov     ecx, 40h ; '@'; uFlags
0x180002fac  call    cs:__imp_LocalAlloc
0x180002fb2  mov     rdi, rax
0x180002fb5  mov     [rsp+98h+var_38], rax
0x180002fba  test    rax, rax
0x180002fbd  jnz     short loc_180002FE4
0x180002fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc6  test    byte ptr [rcx+1Ch], 2
0x180002fca  jz      loc_180003076
0x180002fd0  cmp     byte ptr [rcx+19h], 2
0x180002fd4  jb      loc_180003076
0x180002fda  mov     edx, 2Ch ; ','
0x180002fdf  jmp     loc_180003066
0x180002fe4  mov     r15, rsi
0x180002fe7  xorps   xmm0, xmm0
0x180002fea  xor     eax, eax
0x180002fec  movups  xmmword ptr [rdi], xmm0
0x180002fef  mov     [rdi+10h], rax
0x180002ff3  test    rbx, rbx
0x180002ff6  jz      short loc_18000300B
0x180002ff8  mov     rax, [rbx+8]
0x180002ffc  mov     [rdi+8], rax
0x180003000  mov     rax, [rbx+10h]
0x180003004  test    rax, rax
0x180003007  cmovnz  r15, rax
0x18000300b  test    r15, r15
0x18000300e  jz      loc_18000309E
0x180003014  mov     rcx, r15; Sid
0x180003017  call    cs:__imp_RtlLengthSid
0x18000301d  mov     ebx, eax
0x18000301f  mov     edx, eax; uBytes
0x180003021  mov     ecx, 40h ; '@'; uFlags
0x180003026  call    cs:__imp_LocalAlloc
0x18000302c  mov     [rdi+10h], rax
0x180003030  test    rax, rax
0x180003033  jz      short loc_180003045
0x180003035  mov     r8, r15; SourceSid
0x180003038  mov     rdx, rax; DestinationSid
0x18000303b  mov     ecx, ebx; DestinationSidLength
0x18000303d  call    cs:__imp_RtlCopySid
0x180003043  jmp     short loc_18000309E
0x180003045  mov     rcx, rdi; hMem
0x180003048  call    cs:__imp_LocalFree
0x18000304e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003055  test    byte ptr [rcx+1Ch], 2
0x180003059  jz      short loc_180003076
0x18000305b  cmp     byte ptr [rcx+19h], 2
0x18000305f  jb      short loc_180003076
0x180003061  mov     edx, 2Dh ; '-'
0x180003066  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x18000306d  mov     rcx, [rcx+10h]
0x180003071  call    WPP_SF_
0x180003076  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000307d  jz      short loc_180003094
0x18000307f  xor     r9d, r9d
0x180003082  mov     r8d, 0C0000017h
0x180003088  lea     rdx, SamOpenUserExit
0x18000308f  call    McTemplateU0dp_EventWriteTransfer
0x180003094  mov     eax, 0C0000017h
0x180003099  jmp     loc_1800031F7
0x18000309e  mov     [r14], rsi
0x1800030a1  mov     [rsp+98h+var_40], rsi
0x1800030a6  lea     rax, [rsp+98h+var_48]
0x1800030ab  mov     [rsp+98h+var_68], rax
0x1800030b0  mov     dword ptr [rsp+98h+var_70], r12d
0x1800030b5  mov     dword ptr [rsp+98h+var_78], r13d
0x1800030ba  mov     r9, [rsp+98h+var_50]
0x1800030bf  xor     r8d, r8d; pReturnValue
0x1800030c2  mov     edx, 22h ; '"'; nProcNum
0x1800030c7  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800030ce  call    cs:__imp_NdrClientCall3
0x1800030d4  mov     rbx, rax
0x1800030d7  mov     [rsp+98h+var_40], rax
0x1800030dc  mov     [rsp+98h+var_58], eax
0x1800030e0  jmp     short loc_18000312C
0x1800030e2  mov     ebx, eax
0x1800030e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030eb  test    byte ptr [rcx+1Ch], 2
0x1800030ef  jz      short loc_18000310F
0x1800030f1  cmp     byte ptr [rcx+19h], 3
0x1800030f5  jb      short loc_18000310F
0x1800030f7  mov     r9d, eax
0x1800030fa  mov     edx, 0E6h
0x1800030ff  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003106  mov     rcx, [rcx+10h]
0x18000310a  call    WPP_SF_D
0x18000310f  mov     ecx, ebx; Status
0x180003111  call    cs:__imp_I_RpcMapWin32Status
0x180003117  mov     ebx, eax
0x180003119  mov     [rsp+98h+var_58], eax
0x18000311d  xor     esi, esi
0x18000311f  mov     r14, [rsp+98h+arg_18]
0x180003127  mov     rdi, [rsp+98h+var_38]
0x18000312c  test    ebx, ebx
0x18000312e  js      short loc_18000313A
0x180003130  mov     rax, [rsp+98h+var_48]
0x180003135  mov     [rdi], rax
0x180003138  jmp     short loc_180003161
0x18000313a  mov     rcx, [rdi+10h]; hMem
0x18000313e  test    rcx, rcx
0x180003141  jz      short loc_180003149
0x180003143  call    cs:__imp_LocalFree
0x180003149  xorps   xmm0, xmm0
0x18000314c  xor     eax, eax
0x18000314e  movups  xmmword ptr [rdi], xmm0
0x180003151  mov     [rdi+10h], rax
0x180003155  mov     rcx, rdi; hMem
0x180003158  call    cs:__imp_LocalFree
0x18000315e  mov     rdi, rsi
0x180003161  mov     [r14], rdi
0x180003164  mov     esi, 0C0000008h
0x180003169  cmp     ebx, 0C0020003h
0x18000316f  cmovz   ebx, esi
0x180003172  test    ebx, ebx
0x180003174  js      short loc_1800031AF
0x180003176  mov     rcx, cs:WPP_GLOBAL_Control
0x18000317d  test    byte ptr [rcx+1Ch], 2
0x180003181  jz      short loc_1800031A1
0x180003183  cmp     byte ptr [rcx+19h], 4
0x180003187  jb      short loc_1800031A1
0x180003189  mov     edx, 0E7h
0x18000318e  mov     r9, rdi
0x180003191  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003198  mov     rcx, [rcx+10h]
0x18000319c  call    WPP_SF_q
0x1800031a1  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800031a8  jz      short loc_1800031F5
0x1800031aa  mov     r9, [r14]
0x1800031ad  jmp     short loc_1800031E6
0x1800031af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031b6  test    byte ptr [rcx+1Ch], 2
0x1800031ba  jz      short loc_1800031DA
0x1800031bc  cmp     byte ptr [rcx+19h], 2
0x1800031c0  jb      short loc_1800031DA
0x1800031c2  mov     edx, 0E8h
0x1800031c7  mov     r9d, ebx
0x1800031ca  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800031d1  mov     rcx, [rcx+10h]
0x1800031d5  call    WPP_SF_D
0x1800031da  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800031e1  jz      short loc_1800031F5
0x1800031e3  xor     r9d, r9d
0x1800031e6  mov     r8d, ebx
0x1800031e9  lea     rdx, SamOpenUserExit
0x1800031f0  call    McTemplateU0dp_EventWriteTransfer
0x1800031f5  mov     eax, ebx
0x1800031f7  lea     r11, [rsp+98h+var_28]
0x1800031fc  mov     rbx, [r11+30h]
0x180003200  mov     rsi, [r11+38h]
0x180003204  mov     rsp, r11
0x180003207  pop     r15
0x180003209  pop     r14
0x18000320b  pop     r13
0x18000320d  pop     r12
0x18000320f  pop     rdi
0x180003210  retn
0x180017b70  push    rbp
0x180017b72  sub     rsp, 40h
0x180017b76  mov     rbp, rdx
0x180017b79  mov     rcx, [rcx]
0x180017b7c  mov     ecx, [rcx]; ExceptionCode
0x180017b7e  call    cs:__imp_I_RpcExceptionFilter
0x180017b84  nop
0x180017b85  add     rsp, 40h
0x180017b89  pop     rbp
0x180017b8a  retn
```
