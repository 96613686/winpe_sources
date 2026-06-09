# SamSetSecurityObject

- ea: `0x1800120d0`
- end: `0x1800123a7`
- name: `SamSetSecurityObject`
- size: `727`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c070`
- `0x1800120d0`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001213e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001213e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012315`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012255`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012255`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800121ec`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001228a`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800121ec`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18001228a`
- `RPCRT4!NdrClientCall3` at `0x1800122c1`
- `RPCRT4!NdrClientCall3` at `0x1800122c1`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012304`
- `RPCRT4!I_RpcMapWin32Status` at `0x180012304`

## pseudocode

```c
__int64 __fastcall SamSetSecurityObject(void **a1, int a2, void *a3)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v7; // rbx
  const wchar_t *v8; // rcx
  PVOID v9; // rcx
  unsigned int SelfRelativeSD; // eax
  PVOID v12; // rcx
  NTSTATUS Pointer; // ebx
  CLIENT_CALL_RETURN v14; // rax
  PVOID v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-68h]
  void *v17; // [rsp+38h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+40h] [rbp-48h]
  __int128 v19; // [rsp+48h] [rbp-40h] BYREF
  ULONG BufferLength; // [rsp+A8h] [rbp+20h] BYREF

  BufferLength = 0;
  v17 = 0;
  v19 = 0;
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v7 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v8 = L"<unknown>";
      if ( CallingProcessInfo )
        v8 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer(
        (__int64)v8,
        (const EVENT_DESCRIPTOR *)SamSetSecurityObjectEntry,
        (__int64)a1,
        a2,
        v8);
    }
    LocalFree(v7);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a2);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v17) )
  {
    BufferLength = 0;
    SelfRelativeSD = RtlMakeSelfRelativeSD(a3, 0, &BufferLength);
    if ( SelfRelativeSD == -1073741789 )
    {
      *((_QWORD *)&v19 + 1) = LocalAlloc(0x40u, BufferLength);
      LODWORD(v19) = BufferLength;
      if ( *((_QWORD *)&v19 + 1) )
      {
        Pointer = RtlMakeSelfRelativeSD(a3, *((PSECURITY_DESCRIPTOR *)&v19 + 1), &BufferLength);
        if ( Pointer >= 0 )
        {
          v18.Simple = 0;
          LODWORD(v16) = a2;
          v14.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 2u, 0, v17, v16, &v19).Pointer;
          Pointer = (NTSTATUS)v14.Pointer;
          v18.Pointer = v14.Pointer;
        }
      }
      else
      {
        Pointer = -1073741670;
      }
      LocalFree(*((HLOCAL *)&v19 + 1));
      if ( Pointer == -1073610749 )
        Pointer = -1073741816;
      if ( Pointer < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
            (unsigned int)Pointer);
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
      }
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer(
          (__int64)v15,
          (const EVENT_DESCRIPTOR *)SamSetSecurityObjectExit,
          (unsigned int)Pointer);
      return (unsigned int)Pointer;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
          SelfRelativeSD);
      if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
        McTemplateU0d_EventWriteTransfer((__int64)v12, (const EVENT_DESCRIPTOR *)SamSetSecurityObjectExit, 3221225485LL);
      return 3221225485LL;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v9, (const EVENT_DESCRIPTOR *)SamSetSecurityObjectExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x1800120d0  mov     rax, rsp
0x1800120d3  push    rbx
0x1800120d4  push    rsi
0x1800120d5  push    r12
0x1800120d7  push    r15
0x1800120d9  sub     rsp, 68h
0x1800120dd  mov     r12, r8
0x1800120e0  mov     r15d, edx
0x1800120e3  mov     rsi, rcx
0x1800120e6  mov     dword ptr [rax+20h], 0
0x1800120ed  mov     qword ptr [rax-50h], 0
0x1800120f5  xorps   xmm0, xmm0
0x1800120f8  movups  xmmword ptr [rax-40h], xmm0
0x1800120fc  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180012103  jz      short loc_180012144
0x180012105  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x18001210a  mov     rbx, rax
0x18001210d  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180012114  jz      short loc_18001213B
0x180012116  lea     rcx, aUnknown; "<unknown>"
0x18001211d  test    rax, rax
0x180012120  cmovnz  rcx, rax
0x180012124  mov     [rsp+88h+var_68], rcx
0x180012129  mov     r9d, r15d
0x18001212c  mov     r8, rsi
0x18001212f  lea     rdx, SamSetSecurityObjectEntry
0x180012136  call    McTemplateU0pqz_EventWriteTransfer
0x18001213b  mov     rcx, rbx; hMem
0x18001213e  call    cs:__imp_LocalFree
0x180012144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001214b  test    byte ptr [rcx+1Ch], 2
0x18001214f  jz      short loc_180012174
0x180012151  cmp     byte ptr [rcx+19h], 4
0x180012155  jb      short loc_180012174
0x180012157  mov     edx, 0Ah
0x18001215c  mov     dword ptr [rsp+88h+var_68], r15d
0x180012161  mov     r9, rsi
0x180012164  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001216b  mov     rcx, [rcx+10h]
0x18001216f  call    WPP_SF_qD
0x180012174  lea     rdx, [rsp+88h+var_50]; void **
0x180012179  mov     rcx, rsi; void *
0x18001217c  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180012181  test    al, al
0x180012183  jnz     short loc_1800121D4
0x180012185  mov     rcx, cs:WPP_GLOBAL_Control
0x18001218c  test    byte ptr [rcx+1Ch], 2
0x180012190  jz      short loc_1800121B0
0x180012192  cmp     byte ptr [rcx+19h], 2
0x180012196  jb      short loc_1800121B0
0x180012198  mov     edx, 0Bh
0x18001219d  mov     r9, rsi
0x1800121a0  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800121a7  mov     rcx, [rcx+10h]
0x1800121ab  call    WPP_SF_q
0x1800121b0  mov     esi, 0C0000008h
0x1800121b5  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800121bc  jz      short loc_1800121CD
0x1800121be  mov     r8d, esi
0x1800121c1  lea     rdx, SamSetSecurityObjectExit
0x1800121c8  call    McTemplateU0d_EventWriteTransfer
0x1800121cd  mov     eax, esi
0x1800121cf  jmp     loc_18001239C
0x1800121d4  mov     [rsp+88h+BufferLength], 0
0x1800121df  lea     r8, [rsp+88h+BufferLength]; BufferLength
0x1800121e7  xor     edx, edx; SelfRelativeSD
0x1800121e9  mov     rcx, r12; AbsoluteSD
0x1800121ec  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800121f2  cmp     eax, 0C0000023h
0x1800121f7  jz      short loc_180012249
0x1800121f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012200  test    byte ptr [rcx+1Ch], 2
0x180012204  jz      short loc_180012224
0x180012206  cmp     byte ptr [rcx+19h], 2
0x18001220a  jb      short loc_180012224
0x18001220c  mov     edx, 0Ch
0x180012211  mov     r9d, eax
0x180012214  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001221b  mov     rcx, [rcx+10h]
0x18001221f  call    WPP_SF_D
0x180012224  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18001222b  jz      short loc_18001223F
0x18001222d  mov     r8d, 0C000000Dh
0x180012233  lea     rdx, SamSetSecurityObjectExit
0x18001223a  call    McTemplateU0d_EventWriteTransfer
0x18001223f  mov     eax, 0C000000Dh
0x180012244  jmp     loc_18001239C
0x180012249  mov     edx, [rsp+88h+BufferLength]; uBytes
0x180012250  mov     ecx, 40h ; '@'; uFlags
0x180012255  call    cs:__imp_LocalAlloc
0x18001225b  mov     [rsp+88h+SelfRelativeSD], rax
0x180012260  mov     ecx, [rsp+88h+BufferLength]
0x180012267  mov     [rsp+88h+var_40], ecx
0x18001226b  test    rax, rax
0x18001226e  jnz     short loc_18001227A
0x180012270  mov     ebx, 0C000009Ah
0x180012275  jmp     loc_180012310
0x18001227a  lea     r8, [rsp+88h+BufferLength]; BufferLength
0x180012282  mov     rdx, [rsp+88h+SelfRelativeSD]; SelfRelativeSD
0x180012287  mov     rcx, r12; AbsoluteSD
0x18001228a  call    cs:__imp_RtlMakeSelfRelativeSD
0x180012290  mov     ebx, eax
0x180012292  test    eax, eax
0x180012294  js      short loc_180012310
0x180012296  mov     [rsp+88h+var_48], 0
0x18001229f  lea     rax, [rsp+88h+var_40]
0x1800122a4  mov     [rsp+88h+var_60], rax
0x1800122a9  mov     dword ptr [rsp+88h+var_68], r15d
0x1800122ae  mov     r9, [rsp+88h+var_50]
0x1800122b3  xor     r8d, r8d; pReturnValue
0x1800122b6  lea     edx, [r8+2]; nProcNum
0x1800122ba  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800122c1  call    cs:__imp_NdrClientCall3
0x1800122c7  mov     rbx, rax
0x1800122ca  mov     [rsp+88h+var_48], rax
0x1800122cf  mov     [rsp+88h+var_58], eax
0x1800122d3  jmp     short loc_180012310
0x1800122d5  mov     ebx, eax
0x1800122d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122de  test    byte ptr [rcx+1Ch], 2
0x1800122e2  jz      short loc_180012302
0x1800122e4  cmp     byte ptr [rcx+19h], 3
0x1800122e8  jb      short loc_180012302
0x1800122ea  mov     r9d, eax
0x1800122ed  mov     edx, 0Dh
0x1800122f2  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800122f9  mov     rcx, [rcx+10h]
0x1800122fd  call    WPP_SF_D
0x180012302  mov     ecx, ebx; Status
0x180012304  call    cs:__imp_I_RpcMapWin32Status
0x18001230a  mov     ebx, eax
0x18001230c  mov     [rsp+88h+var_58], eax
0x180012310  mov     rcx, [rsp+88h+SelfRelativeSD]; hMem
0x180012315  call    cs:__imp_LocalFree
0x18001231b  mov     esi, 0C0000008h
0x180012320  cmp     ebx, 0C0020003h
0x180012326  cmovz   ebx, esi
0x180012329  test    ebx, ebx
0x18001232b  js      short loc_180012357
0x18001232d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012334  test    byte ptr [rcx+1Ch], 2
0x180012338  jz      short loc_180012382
0x18001233a  cmp     byte ptr [rcx+19h], 4
0x18001233e  jb      short loc_180012382
0x180012340  mov     edx, 0Eh
0x180012345  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18001234c  mov     rcx, [rcx+10h]
0x180012350  call    WPP_SF_
0x180012355  jmp     short loc_180012382
0x180012357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001235e  test    byte ptr [rcx+1Ch], 2
0x180012362  jz      short loc_180012382
0x180012364  cmp     byte ptr [rcx+19h], 2
0x180012368  jb      short loc_180012382
0x18001236a  mov     edx, 0Fh
0x18001236f  mov     r9d, ebx
0x180012372  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180012379  mov     rcx, [rcx+10h]
0x18001237d  call    WPP_SF_D
0x180012382  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180012389  jz      short loc_18001239A
0x18001238b  mov     r8d, ebx
0x18001238e  lea     rdx, SamSetSecurityObjectExit
0x180012395  call    McTemplateU0d_EventWriteTransfer
0x18001239a  mov     eax, ebx
0x18001239c  add     rsp, 68h
0x1800123a0  pop     r15
0x1800123a2  pop     r12
0x1800123a4  pop     rsi
0x1800123a5  pop     rbx
0x1800123a6  retn
0x180017dbc  push    rbp
0x180017dbe  sub     rsp, 30h
0x180017dc2  mov     rbp, rdx
0x180017dc5  mov     rcx, [rcx]
0x180017dc8  mov     ecx, [rcx]; ExceptionCode
0x180017dca  call    cs:__imp_I_RpcExceptionFilter
0x180017dd0  nop
0x180017dd1  add     rsp, 30h
0x180017dd5  pop     rbp
0x180017dd6  retn
```
