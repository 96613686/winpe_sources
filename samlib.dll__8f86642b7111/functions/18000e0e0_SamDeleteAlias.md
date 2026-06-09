# SamDeleteAlias

- ea: `0x18000e0e0`
- end: `0x18000e2cb`
- name: `SamDeleteAlias`
- size: `491`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x180003370`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c210`
- `0x18000e0e0`
- `0x180014a50`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e135`
- `RPCRT4!NdrClientCall3` at `0x18000e1e2`
- `RPCRT4!NdrClientCall3` at `0x18000e1e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e225`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e225`

## pseudocode

```c
__int64 __fastcall SamDeleteAlias(struct _SAMP_CLIENT_INFO *a1)
{
  unsigned __int16 *CallingProcessInfo; // rax
  __int64 v3; // rcx
  unsigned __int16 *v4; // rdi
  const wchar_t *v5; // r9
  PVOID v6; // rcx
  CLIENT_CALL_RETURN v8; // rax
  unsigned int Pointer; // ebx
  PVOID v10; // rcx
  struct _SAMP_CLIENT_INFO *v11; // [rsp+40h] [rbp+8h] BYREF
  void *v12; // [rsp+48h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+50h] [rbp+18h]

  v11 = a1;
  v12 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v4 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v5 = L"<unknown>";
      if ( CallingProcessInfo )
        v5 = CallingProcessInfo;
      McTemplateU0pz_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SamDeleteAliasEntry, (__int64)a1, v5);
    }
    LocalFree(v4);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
  if ( (unsigned __int8)SampIsValidClientHandle((void **)a1, &v12) )
  {
    v13.Simple = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x1Eu, 0, &v12).Pointer;
    Pointer = (unsigned int)v8.Pointer;
    v13.Pointer = v8.Pointer;
    if ( SLODWORD(v8.Simple) >= 0 )
      SampFreeHandle(&v11);
    if ( Pointer == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)SamDeleteAliasExit, Pointer);
    return Pointer;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v6, (const EVENT_DESCRIPTOR *)SamDeleteAliasExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x18000e0e0  mov     [rsp+arg_18], rbx
0x18000e0e5  mov     [rsp+arg_0], rcx
0x18000e0ea  push    rdi
0x18000e0eb  sub     rsp, 30h
0x18000e0ef  mov     rbx, rcx
0x18000e0f2  mov     [rsp+38h+arg_8], 0
0x18000e0fb  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e102  jz      short loc_18000E13B
0x18000e104  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18000e109  mov     rdi, rax
0x18000e10c  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e113  jz      short loc_18000E132
0x18000e115  lea     r9, aUnknown; "<unknown>"
0x18000e11c  test    rax, rax
0x18000e11f  cmovnz  r9, rax
0x18000e123  mov     r8, rbx
0x18000e126  lea     rdx, SamDeleteAliasEntry
0x18000e12d  call    McTemplateU0pz_EventWriteTransfer
0x18000e132  mov     rcx, rdi; hMem
0x18000e135  call    cs:__imp_LocalFree
0x18000e13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e142  test    byte ptr [rcx+1Ch], 2
0x18000e146  jz      short loc_18000E166
0x18000e148  cmp     byte ptr [rcx+19h], 4
0x18000e14c  jb      short loc_18000E166
0x18000e14e  mov     edx, 0C1h
0x18000e153  mov     r9, rbx
0x18000e156  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e15d  mov     rcx, [rcx+10h]
0x18000e161  call    WPP_SF_q
0x18000e166  lea     rdx, [rsp+38h+arg_8]; void **
0x18000e16b  mov     rcx, rbx; void *
0x18000e16e  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x18000e173  test    al, al
0x18000e175  jnz     short loc_18000E1C6
0x18000e177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e17e  test    byte ptr [rcx+1Ch], 2
0x18000e182  jz      short loc_18000E1A2
0x18000e184  cmp     byte ptr [rcx+19h], 2
0x18000e188  jb      short loc_18000E1A2
0x18000e18a  mov     edx, 0C2h
0x18000e18f  mov     r9, rbx
0x18000e192  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e199  mov     rcx, [rcx+10h]
0x18000e19d  call    WPP_SF_q
0x18000e1a2  mov     edi, 0C0000008h
0x18000e1a7  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e1ae  jz      short loc_18000E1BF
0x18000e1b0  mov     r8d, edi
0x18000e1b3  lea     rdx, SamDeleteAliasExit
0x18000e1ba  call    McTemplateU0d_EventWriteTransfer
0x18000e1bf  mov     eax, edi
0x18000e1c1  jmp     loc_18000E2C0
0x18000e1c6  mov     [rsp+38h+arg_10], 0
0x18000e1cf  lea     r9, [rsp+38h+arg_8]
0x18000e1d4  xor     r8d, r8d; pReturnValue
0x18000e1d7  lea     edx, [r8+1Eh]; nProcNum
0x18000e1db  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000e1e2  call    cs:__imp_NdrClientCall3
0x18000e1e8  mov     rbx, rax
0x18000e1eb  mov     [rsp+38h+arg_10], rax
0x18000e1f0  mov     [rsp+38h+var_18], eax
0x18000e1f4  jmp     short loc_18000E231
0x18000e1f6  mov     ebx, eax
0x18000e1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ff  test    byte ptr [rcx+1Ch], 2
0x18000e203  jz      short loc_18000E223
0x18000e205  cmp     byte ptr [rcx+19h], 3
0x18000e209  jb      short loc_18000E223
0x18000e20b  mov     r9d, eax
0x18000e20e  mov     edx, 0C3h
0x18000e213  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e21a  mov     rcx, [rcx+10h]
0x18000e21e  call    WPP_SF_D
0x18000e223  mov     ecx, ebx; Status
0x18000e225  call    cs:__imp_I_RpcMapWin32Status
0x18000e22b  mov     ebx, eax
0x18000e22d  mov     [rsp+38h+var_18], eax
0x18000e231  test    ebx, ebx
0x18000e233  js      short loc_18000E23F
0x18000e235  lea     rcx, [rsp+38h+arg_0]; struct _SAMP_CLIENT_INFO **
0x18000e23a  call    ?SampFreeHandle@@YAXPEAPEAU_SAMP_CLIENT_INFO@@@Z; SampFreeHandle(_SAMP_CLIENT_INFO * *)
0x18000e23f  mov     edi, 0C0000008h
0x18000e244  cmp     ebx, 0C0020003h
0x18000e24a  cmovz   ebx, edi
0x18000e24d  test    ebx, ebx
0x18000e24f  js      short loc_18000E27B
0x18000e251  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e258  test    byte ptr [rcx+1Ch], 2
0x18000e25c  jz      short loc_18000E2A6
0x18000e25e  cmp     byte ptr [rcx+19h], 4
0x18000e262  jb      short loc_18000E2A6
0x18000e264  mov     edx, 0C4h
0x18000e269  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e270  mov     rcx, [rcx+10h]
0x18000e274  call    WPP_SF_
0x18000e279  jmp     short loc_18000E2A6
0x18000e27b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e282  test    byte ptr [rcx+1Ch], 2
0x18000e286  jz      short loc_18000E2A6
0x18000e288  cmp     byte ptr [rcx+19h], 2
0x18000e28c  jb      short loc_18000E2A6
0x18000e28e  mov     edx, 0C5h
0x18000e293  mov     r9d, ebx
0x18000e296  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000e29d  mov     rcx, [rcx+10h]
0x18000e2a1  call    WPP_SF_D
0x18000e2a6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000e2ad  jz      short loc_18000E2BE
0x18000e2af  mov     r8d, ebx
0x18000e2b2  lea     rdx, SamDeleteAliasExit
0x18000e2b9  call    McTemplateU0d_EventWriteTransfer
0x18000e2be  mov     eax, ebx
0x18000e2c0  mov     rbx, [rsp+38h+arg_18]
0x18000e2c5  add     rsp, 30h
0x18000e2c9  pop     rdi
0x18000e2ca  retn
0x180017e00  push    rbp
0x180017e02  sub     rsp, 20h
0x180017e06  mov     rbp, rdx
0x180017e09  mov     rcx, [rcx]
0x180017e0c  mov     ecx, [rcx]; ExceptionCode
0x180017e0e  call    cs:__imp_I_RpcExceptionFilter
0x180017e14  nop
0x180017e15  add     rsp, 20h
0x180017e19  pop     rbp
0x180017e1a  retn
```
