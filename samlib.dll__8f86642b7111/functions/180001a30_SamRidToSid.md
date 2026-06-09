# SamRidToSid

- ea: `0x180001a30`
- end: `0x180001c3d`
- name: `SamRidToSid`
- size: `525`
- prototype: `__int64 __fastcall(void *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001a30`
- `0x180003220`
- `0x1800036b0`
- `0x18000807c`
- `0x18000ba68`
- `0x18000c070`
- `0x1800148d8`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a8e`
- `RPCRT4!NdrClientCall3` at `0x180001b5c`
- `RPCRT4!NdrClientCall3` at `0x180001b5c`

## pseudocode

```c
__int64 __fastcall SamRidToSid(void **a1, ULONG a2, void **a3)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v7; // rbp
  const wchar_t *v8; // rcx
  PVOID v9; // rcx
  unsigned int Pointer; // ebx
  CLIENT_CALL_RETURN v12; // r8
  void *v13; // rcx
  PVOID v14; // rcx
  void *v15; // r9
  __int64 v16; // [rsp+20h] [rbp-18h]

  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v7 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v8 = L"<unknown>";
      if ( CallingProcessInfo )
        v8 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)SamRidToSidEntry, (__int64)a1, a2, v8);
    }
    LocalFree(v7);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a2);
  if ( !(unsigned __int8)SampIsValidClientHandle(a1, 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 332, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0dk_EventWriteTransfer(v9, SamRidToSidExit, 3221225480LL, 0);
    return 3221225480LL;
  }
  if ( (*((_BYTE *)a1 + 12) & 1) != 0 )
  {
    *a3 = 0;
    LODWORD(v16) = a2;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x41u, 0, *a1, v16, a3).Pointer;
    goto LABEL_24;
  }
  v13 = a1[2];
  if ( v13 )
  {
    Pointer = SampMakeSid(v13, a2, a3);
LABEL_24:
    if ( (Pointer & 0x80000000) != 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return Pointer;
      v15 = 0;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x14Du, v12.Simple, (char *)*a3);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) == 0 )
        return Pointer;
      v15 = *a3;
    }
    McTemplateU0dk_EventWriteTransfer(v14, SamRidToSidExit, Pointer, v15);
    return Pointer;
  }
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0dk_EventWriteTransfer(0, SamRidToSidExit, 3221225485LL, 0);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180001a30  mov     [rsp+arg_8], rbx
0x180001a35  mov     [rsp+arg_10], rsi
0x180001a3a  push    rdi
0x180001a3b  sub     rsp, 30h
0x180001a3f  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001a46  mov     rdi, r8
0x180001a49  mov     esi, edx
0x180001a4b  mov     rbx, rcx
0x180001a4e  jz      short loc_180001A99
0x180001a50  mov     [rsp+38h+arg_0], rbp
0x180001a55  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180001a5a  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001a61  mov     rbp, rax
0x180001a64  jz      short loc_180001A8B
0x180001a66  test    rax, rax
0x180001a69  lea     rcx, aUnknown; "<unknown>"
0x180001a70  mov     r9d, esi
0x180001a73  lea     rdx, SamRidToSidEntry
0x180001a7a  cmovnz  rcx, rax
0x180001a7e  mov     r8, rbx
0x180001a81  mov     [rsp+38h+var_18], rcx
0x180001a86  call    McTemplateU0pqz_EventWriteTransfer
0x180001a8b  mov     rcx, rbp; hMem
0x180001a8e  call    cs:__imp_LocalFree
0x180001a94  mov     rbp, [rsp+38h+arg_0]
0x180001a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180001aa0  test    byte ptr [rcx+1Ch], 2
0x180001aa4  jz      short loc_180001AC8
0x180001aa6  cmp     byte ptr [rcx+19h], 5
0x180001aaa  jb      short loc_180001AC8
0x180001aac  mov     rcx, [rcx+10h]
0x180001ab0  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180001ab7  mov     edx, 14Bh
0x180001abc  mov     dword ptr [rsp+38h+var_18], esi
0x180001ac0  mov     r9, rbx
0x180001ac3  call    WPP_SF_qD
0x180001ac8  xor     edx, edx; void **
0x180001aca  mov     rcx, rbx; void *
0x180001acd  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180001ad2  test    al, al
0x180001ad4  jnz     short loc_180001B34
0x180001ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180001add  test    byte ptr [rcx+1Ch], 2
0x180001ae1  jz      short loc_180001B01
0x180001ae3  cmp     byte ptr [rcx+19h], 2
0x180001ae7  jb      short loc_180001B01
0x180001ae9  mov     rcx, [rcx+10h]
0x180001aed  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180001af4  mov     edx, 14Ch
0x180001af9  mov     r9, rbx
0x180001afc  call    WPP_SF_q
0x180001b01  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001b08  jz      short loc_180001B1F
0x180001b0a  xor     r9d, r9d
0x180001b0d  lea     rdx, SamRidToSidExit
0x180001b14  mov     r8d, 0C0000008h
0x180001b1a  call    McTemplateU0dk_EventWriteTransfer
0x180001b1f  mov     eax, 0C0000008h
0x180001b24  mov     rbx, [rsp+38h+arg_8]
0x180001b29  mov     rsi, [rsp+38h+arg_10]
0x180001b2e  add     rsp, 30h
0x180001b32  pop     rdi
0x180001b33  retn
0x180001b34  test    byte ptr [rbx+0Ch], 1
0x180001b38  jz      short loc_180001B67
0x180001b3a  mov     qword ptr [rdi], 0
0x180001b41  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180001b48  mov     r9, [rbx]
0x180001b4b  xor     r8d, r8d; pReturnValue
0x180001b4e  mov     [rsp+38h+var_10], rdi
0x180001b53  mov     edx, 41h ; 'A'; nProcNum
0x180001b58  mov     dword ptr [rsp+38h+var_18], esi
0x180001b5c  call    cs:__imp_NdrClientCall3
0x180001b62  mov     rbx, rax
0x180001b65  jmp     short loc_180001BAF
0x180001b67  mov     rcx, [rbx+10h]; SourceSid
0x180001b6b  test    rcx, rcx
0x180001b6e  jnz     short loc_180001BA3
0x180001b70  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001b77  jz      short loc_180001B8E
0x180001b79  xor     r9d, r9d
0x180001b7c  lea     rdx, SamRidToSidExit
0x180001b83  mov     r8d, 0C000000Dh
0x180001b89  call    McTemplateU0dk_EventWriteTransfer
0x180001b8e  mov     eax, 0C000000Dh
0x180001b93  mov     rbx, [rsp+38h+arg_8]
0x180001b98  mov     rsi, [rsp+38h+arg_10]
0x180001b9d  add     rsp, 30h
0x180001ba1  pop     rdi
0x180001ba2  retn
0x180001ba3  mov     r8, rdi; void **
0x180001ba6  mov     edx, esi; unsigned int
0x180001ba8  call    ?SampMakeSid@@YAJPEAXKPEAPEAX@Z; SampMakeSid(void *,ulong,void * *)
0x180001bad  mov     ebx, eax
0x180001baf  test    ebx, ebx
0x180001bb1  js      short loc_180001BE5
0x180001bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bba  test    byte ptr [rcx+1Ch], 2
0x180001bbe  jz      short loc_180001BD7
0x180001bc0  cmp     byte ptr [rcx+19h], 4
0x180001bc4  jb      short loc_180001BD7
0x180001bc6  mov     r9, [rdi]
0x180001bc9  mov     edx, 14Dh
0x180001bce  mov     rcx, [rcx+10h]; LoggerHandle
0x180001bd2  call    WPP_SF__sid_
0x180001bd7  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001bde  jz      short loc_180001C2B
0x180001be0  mov     r9, [rdi]
0x180001be3  jmp     short loc_180001C1C
0x180001be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bec  test    byte ptr [rcx+1Ch], 2
0x180001bf0  jz      short loc_180001C10
0x180001bf2  cmp     byte ptr [rcx+19h], 2
0x180001bf6  jb      short loc_180001C10
0x180001bf8  mov     rcx, [rcx+10h]
0x180001bfc  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180001c03  mov     edx, 14Eh
0x180001c08  mov     r9d, ebx
0x180001c0b  call    WPP_SF_D
0x180001c10  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001c17  jz      short loc_180001C2B
0x180001c19  xor     r9d, r9d
0x180001c1c  mov     r8d, ebx
0x180001c1f  lea     rdx, SamRidToSidExit
0x180001c26  call    McTemplateU0dk_EventWriteTransfer
0x180001c2b  mov     rsi, [rsp+38h+arg_10]
0x180001c30  mov     eax, ebx
0x180001c32  mov     rbx, [rsp+38h+arg_8]
0x180001c37  add     rsp, 30h
0x180001c3b  pop     rdi
0x180001c3c  retn
```
