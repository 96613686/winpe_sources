# SamQuerySecurityObject

- ea: `0x180001450`
- end: `0x180001690`
- name: `SamQuerySecurityObject`
- size: `576`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001450`
- `0x180003220`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c070`
- `0x180014a50`
- `0x180014a90`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800014c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800014c4`
- `RPCRT4!NdrClientCall3` at `0x18000159a`
- `RPCRT4!NdrClientCall3` at `0x18000159a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800015dd`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800015dd`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800179ee`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800179ee`

## pseudocode

```c
__int64 __fastcall SamQuerySecurityObject(void **a1, int a2, _QWORD *a3)
{
  unsigned __int16 *CallingProcessInfo; // rax
  unsigned __int16 *v7; // r14
  const wchar_t *v8; // rcx
  PVOID v9; // rcx
  CLIENT_CALL_RETURN v11; // rax
  unsigned int Pointer; // ebx
  PVOID v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+38h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+40h] [rbp-38h]
  __int128 v17; // [rsp+48h] [rbp-30h] BYREF
  __int128 *v18; // [rsp+98h] [rbp+20h] BYREF

  v15 = 0;
  v17 = 0;
  v18 = 0;
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
        (const EVENT_DESCRIPTOR *)SamQuerySecurityObjectEntry,
        (__int64)a1,
        a2,
        v8);
    }
    LocalFree(v7);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, a2);
  if ( (unsigned __int8)SampIsValidClientHandle(a1, &v15) )
  {
    LODWORD(v17) = 0;
    *((_QWORD *)&v17 + 1) = 0;
    v18 = &v17;
    v16.Simple = 0;
    LODWORD(v14) = a2;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 3u, 0, v15, v14, &v18).Pointer;
    Pointer = (unsigned int)v11.Pointer;
    v16.Pointer = v11.Pointer;
    *a3 = *((_QWORD *)&v17 + 1);
    if ( LODWORD(v11.Pointer) == -1073610749 )
      Pointer = -1073741816;
    if ( (Pointer & 0x80000000) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, Pointer);
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    }
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v13, (const EVENT_DESCRIPTOR *)SamQuerySecurityObjectExit, Pointer);
    return Pointer;
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
      McTemplateU0d_EventWriteTransfer((__int64)v9, (const EVENT_DESCRIPTOR *)SamQuerySecurityObjectExit, 3221225480LL);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180001450  mov     rax, rsp
0x180001453  mov     [rax+8], rbx
0x180001457  mov     [rax+10h], rsi
0x18000145b  mov     [rax+18h], r8
0x18000145f  push    rdi
0x180001460  push    r14
0x180001462  push    r15
0x180001464  sub     rsp, 60h
0x180001468  mov     rdi, r8
0x18000146b  mov     esi, edx
0x18000146d  mov     rbx, rcx
0x180001470  xor     r15d, r15d
0x180001473  mov     [rax-40h], r15
0x180001477  xorps   xmm0, xmm0
0x18000147a  movups  xmmword ptr [rax-30h], xmm0
0x18000147e  mov     [rax+20h], r15
0x180001482  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001489  jz      short loc_1800014CA
0x18000148b  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180001490  mov     r14, rax
0x180001493  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000149a  jz      short loc_1800014C1
0x18000149c  lea     rcx, aUnknown; "<unknown>"
0x1800014a3  test    rax, rax
0x1800014a6  cmovnz  rcx, rax
0x1800014aa  mov     [rsp+78h+var_58], rcx
0x1800014af  mov     r9d, esi
0x1800014b2  mov     r8, rbx
0x1800014b5  lea     rdx, SamQuerySecurityObjectEntry
0x1800014bc  call    McTemplateU0pqz_EventWriteTransfer
0x1800014c1  mov     rcx, r14; hMem
0x1800014c4  call    cs:__imp_LocalFree
0x1800014ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014d1  test    byte ptr [rcx+1Ch], 2
0x1800014d5  jz      short loc_1800014F9
0x1800014d7  cmp     byte ptr [rcx+19h], 4
0x1800014db  jb      short loc_1800014F9
0x1800014dd  mov     edx, 10h
0x1800014e2  mov     dword ptr [rsp+78h+var_58], esi
0x1800014e6  mov     r9, rbx
0x1800014e9  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800014f0  mov     rcx, [rcx+10h]
0x1800014f4  call    WPP_SF_qD
0x1800014f9  lea     rdx, [rsp+78h+var_40]; void **
0x1800014fe  mov     rcx, rbx; void *
0x180001501  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180001506  test    al, al
0x180001508  jnz     short loc_180001559
0x18000150a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001511  test    byte ptr [rcx+1Ch], 2
0x180001515  jz      short loc_180001535
0x180001517  cmp     byte ptr [rcx+19h], 2
0x18000151b  jb      short loc_180001535
0x18000151d  mov     edx, 11h
0x180001522  mov     r9, rbx
0x180001525  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000152c  mov     rcx, [rcx+10h]
0x180001530  call    WPP_SF_q
0x180001535  mov     edi, 0C0000008h
0x18000153a  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001541  jz      short loc_180001552
0x180001543  mov     r8d, edi
0x180001546  lea     rdx, SamQuerySecurityObjectExit
0x18000154d  call    McTemplateU0d_EventWriteTransfer
0x180001552  mov     eax, edi
0x180001554  jmp     loc_18000167A
0x180001559  mov     [rsp+78h+var_30], r15d
0x18000155e  mov     [rsp+78h+var_28], r15
0x180001563  lea     rax, [rsp+78h+var_30]
0x180001568  mov     [rsp+78h+arg_18], rax
0x180001570  mov     [rsp+78h+var_38], r15
0x180001575  lea     rax, [rsp+78h+arg_18]
0x18000157d  mov     [rsp+78h+var_50], rax
0x180001582  mov     dword ptr [rsp+78h+var_58], esi
0x180001586  mov     r9, [rsp+78h+var_40]
0x18000158b  xor     r8d, r8d; pReturnValue
0x18000158e  mov     edx, 3; nProcNum
0x180001593  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000159a  call    cs:__imp_NdrClientCall3
0x1800015a0  mov     rbx, rax
0x1800015a3  mov     [rsp+78h+var_38], rax
0x1800015a8  mov     [rsp+78h+var_48], eax
0x1800015ac  jmp     short loc_1800015F1
0x1800015ae  mov     ebx, eax
0x1800015b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015b7  test    byte ptr [rcx+1Ch], 2
0x1800015bb  jz      short loc_1800015DB
0x1800015bd  cmp     byte ptr [rcx+19h], 3
0x1800015c1  jb      short loc_1800015DB
0x1800015c3  mov     r9d, eax
0x1800015c6  mov     edx, 12h
0x1800015cb  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800015d2  mov     rcx, [rcx+10h]
0x1800015d6  call    WPP_SF_D
0x1800015db  mov     ecx, ebx; Status
0x1800015dd  call    cs:__imp_I_RpcMapWin32Status
0x1800015e3  mov     ebx, eax
0x1800015e5  mov     [rsp+78h+var_48], eax
0x1800015e9  mov     rdi, [rsp+78h+arg_10]
0x1800015f1  mov     rax, [rsp+78h+var_28]
0x1800015f6  mov     [rdi], rax
0x1800015f9  mov     edi, 0C0000008h
0x1800015fe  cmp     ebx, 0C0020003h
0x180001604  cmovz   ebx, edi
0x180001607  test    ebx, ebx
0x180001609  js      short loc_180001635
0x18000160b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001612  test    byte ptr [rcx+1Ch], 2
0x180001616  jz      short loc_180001660
0x180001618  cmp     byte ptr [rcx+19h], 4
0x18000161c  jb      short loc_180001660
0x18000161e  mov     edx, 13h
0x180001623  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000162a  mov     rcx, [rcx+10h]
0x18000162e  call    WPP_SF_
0x180001633  jmp     short loc_180001660
0x180001635  mov     rcx, cs:WPP_GLOBAL_Control
0x18000163c  test    byte ptr [rcx+1Ch], 2
0x180001640  jz      short loc_180001660
0x180001642  cmp     byte ptr [rcx+19h], 2
0x180001646  jb      short loc_180001660
0x180001648  mov     edx, 14h
0x18000164d  mov     r9d, ebx
0x180001650  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180001657  mov     rcx, [rcx+10h]
0x18000165b  call    WPP_SF_D
0x180001660  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x180001667  jz      short loc_180001678
0x180001669  mov     r8d, ebx
0x18000166c  lea     rdx, SamQuerySecurityObjectExit
0x180001673  call    McTemplateU0d_EventWriteTransfer
0x180001678  mov     eax, ebx
0x18000167a  lea     r11, [rsp+78h+var_18]
0x18000167f  mov     rbx, [r11+20h]
0x180001683  mov     rsi, [r11+28h]
0x180001687  mov     rsp, r11
0x18000168a  pop     r15
0x18000168c  pop     r14
0x18000168e  pop     rdi
0x18000168f  retn
0x1800179e0  push    rbp
0x1800179e2  sub     rsp, 30h
0x1800179e6  mov     rbp, rdx
0x1800179e9  mov     rcx, [rcx]
0x1800179ec  mov     ecx, [rcx]; ExceptionCode
0x1800179ee  call    cs:__imp_I_RpcExceptionFilter
0x1800179f4  nop
0x1800179f5  add     rsp, 30h
0x1800179f9  pop     rbp
0x1800179fa  retn
```
