# InvokeRPFCallbacks

- ea: `0x180017a44`
- end: `0x180017f40`
- name: `InvokeRPFCallbacks`
- size: `1276`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, __int64, __int64, __int64, int, __int64, __int64, PRTM_DEST_INFO)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180018070`

## callees

- `0x180007110`
- `0x180007220`
- `0x1800072f0`
- `0x18000a670`
- `0x180014bfc`
- `0x180015100`
- `0x1800165d4`
- `0x180017a44`
- `0x18001b548`
- `0x18001bc4c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x180017dfd`
- `rtutils!RouterLogEventA` at `0x180017dfd`

## string_xrefs

- `0x180017d98`: `InvokeRPFCallbacks : New incoming Interface not found : %x, %x, %x`
- `0x180017c7b`: `InvokeRPFCallbacks : No protocol entry forincoming interface : %x, %x`

## pseudocode

```c
__int64 __fastcall InvokeRPFCallbacks(
        __int64 *a1,
        __int64 a2,
        unsigned int *a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        int a7,
        ULONG *a8,
        _DWORD *a9,
        __int64 a10,
        int a11,
        __int64 a12,
        _QWORD *a13,
        PRTM_DEST_INFO DestInfo)
{
  __int64 v16; // r13
  unsigned int v17; // ebx
  void *Hop; // rax
  __int64 v19; // rbx
  unsigned int v20; // r15d
  _QWORD *v21; // r9
  _DWORD *v22; // r11
  __int64 ProtocolEntry; // rax
  __int64 v24; // r11
  __int64 (__fastcall *v25)(_QWORD, __int64, _QWORD, _QWORD, ULONG *, _DWORD *, __int64, int, __int64, PRTM_DEST_INFO); // rax
  unsigned int v26; // edx
  __int64 v27; // rsi
  unsigned int v28; // ebx
  __int64 v29; // r9
  __int64 v30; // r8
  bool v31; // zf
  _RTM_NEXTHOP_INFO NextHopInfo; // [rsp+88h] [rbp-78h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+C0h] [rbp-40h] BYREF
  int v37; // [rsp+E0h] [rbp-20h] BYREF
  char v38[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v16 = 0;
  *(_QWORD *)&DestAddress.AddrBits[4] = 0;
  *(_DWORD *)&DestAddress.AddrBits[12] = 0;
  v37 = 0;
  memset(&NextHopInfo, 0, 52);
  memset_0(v38, 0, sizeof(v38));
  *(_DWORD *)&DestAddress.AddressFamily = 2097154;
  *(_DWORD *)DestAddress.AddrBits = a4;
  *a1 = 0;
  if ( RtmGetMostSpecificDestination(g_hRtmHandle, &DestAddress, 0, 2u, DestInfo) )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"No Route to source %x", a4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
    }
    v17 = 1003;
    goto LABEL_34;
  }
  Hop = (void *)SelectNextHop(DestInfo);
  *a13 = Hop;
  if ( !Hop )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"No NextHop to source %x", a4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
    }
    v17 = 1003;
    goto LABEL_33;
  }
  if ( RtmGetNextHopInfo(g_hRtmHandle, Hop, &NextHopInfo) || NextHopInfo.State )
  {
    v17 = 1003;
    if ( qword_18002B8A8 )
    {
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"No Nexthop info to source %x", a4);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
    }
    goto LABEL_33;
  }
  *a8 = NextHopInfo.InterfaceIndex;
  *a9 = 0;
  v19 = 32LL * (*a8 % dword_18002B92C);
  v20 = *a8 % dword_18002B92C;
  AcquireReadLock((char *)qword_18002B9E8 + v19 + 16);
  *a3 = v20;
  FindIfEntry((char *)qword_18002B9E8 + v19, *a8, (unsigned int)*a9, a2);
  v22 = (_DWORD *)*v21;
  v17 = 0;
  if ( *v21 && v22[4] == *a8 )
  {
    ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, (unsigned int)v22[6], (unsigned int)v22[7]);
    v16 = ProtocolEntry;
    if ( ProtocolEntry )
    {
      v25 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, ULONG *, _DWORD *, __int64, int, __int64, PRTM_DEST_INFO))(ProtocolEntry + 40);
      if ( v25 )
      {
        v17 = v25(a4, 0xFFFFFFFFLL, a6, 0, a8, a9, a10, a11, a12, DestInfo);
        if ( v17 == 87 )
        {
          v26 = *a8 % dword_18002B92C;
          v20 = v26;
          v27 = 32LL * v26;
          v28 = v26;
          if ( *a3 != v26 )
          {
            ReleaseReadLock((char *)qword_18002B9E8 + 32 * *a3 + 16);
            AcquireReadLock((char *)qword_18002B9E8 + v27 + 16);
            *a3 = v28;
          }
          v17 = (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v27, *a8, (unsigned int)*a9, a2) == 0 ? 0x3EB : 0;
        }
      }
    }
    else
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v37) = 0;
        FormatRRASErrorString(
          &v37,
          L"InvokeRPFCallbacks : No protocol entry forincoming interface : %x, %x",
          *(unsigned int *)(v24 + 24),
          *(unsigned int *)(v24 + 28));
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
      }
      v17 = 1003;
    }
  }
  else
  {
    if ( qword_18002B8A8 )
    {
      v29 = (unsigned int)*a9;
      v30 = *a8;
      LOWORD(v37) = 0;
      FormatRRASErrorString(&v37, L"InvokeRPFCallbacks : New incoming Interface not found : %x, %x, %x", v30, v29, v22);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
    }
    v17 = 1003;
    if ( (unsigned int)dword_18002BA54 >= 2 )
      RouterLogEventA(qword_18002BA58, 2u, 0xC35Fu, 0, 0, 0x3EBu);
  }
  if ( RtmReleaseNextHopInfo(g_hRtmHandle, &NextHopInfo) && qword_18002B8A8 )
  {
    LOWORD(v37) = 0;
    FormatRRASErrorString(&v37, L"Failed to release next hop : %x", v17);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
  }
  if ( v17 )
  {
    ReleaseReadLock((char *)qword_18002B9E8 + 32 * v20 + 16);
LABEL_33:
    RtmReleaseDestInfo(g_hRtmHandle, DestInfo);
  }
LABEL_34:
  v31 = qword_18002B8A8 == 0;
  *a1 = v16;
  if ( !v31 )
  {
    LOWORD(v37) = 0;
    FormatRRASErrorString(&v37, L"LEAVING RPF Callback : %d", v17);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v37);
  }
  return v17;
}

```

## disassembly

```asm
0x180017a44  push    rbp
0x180017a46  push    rbx
0x180017a47  push    rsi
0x180017a48  push    rdi
0x180017a49  push    r12
0x180017a4b  push    r13
0x180017a4d  push    r14
0x180017a4f  push    r15
0x180017a51  lea     rbp, [rsp-7F8h]
0x180017a59  sub     rsp, 8F8h
0x180017a60  mov     rax, cs:__security_cookie
0x180017a67  xor     rax, rsp
0x180017a6a  mov     [rbp+830h+var_50], rax
0x180017a71  mov     rax, [rbp+830h+arg_48]
0x180017a78  xorps   xmm0, xmm0
0x180017a7b  mov     rbx, [rbp+830h+arg_68]
0x180017a82  mov     r12, r8
0x180017a85  mov     rdi, [rbp+830h+arg_38]
0x180017a8c  mov     r8d, 7FCh; Size
0x180017a92  mov     r14, [rbp+830h+arg_40]
0x180017a99  mov     esi, r9d
0x180017a9c  mov     r15, [rbp+830h+arg_60]
0x180017aa3  mov     [rbp+830h+var_8B0], rax
0x180017aa7  mov     rax, [rbp+830h+arg_58]
0x180017aae  mov     [rsp+930h+var_8C0], rcx
0x180017ab3  xor     ecx, ecx
0x180017ab5  mov     [rsp+930h+var_8B8], rax
0x180017aba  mov     r13d, ecx
0x180017abd  xor     eax, eax
0x180017abf  mov     [rsp+930h+var_8D0], rdx
0x180017ac4  mov     qword ptr [rbp+830h+DestAddress.AddrBits+4], rcx
0x180017ac8  xor     edx, edx; Val
0x180017aca  mov     dword ptr [rbp+830h+DestAddress.AddrBits+0Ch], ecx
0x180017acd  mov     [rbp+830h+var_850], ecx
0x180017ad0  lea     rcx, [rbp+830h+var_84C]; void *
0x180017ad4  mov     dword ptr [rbp+830h+NextHopInfo.RemoteNextHop], eax
0x180017ad7  mov     [rsp+930h+var_8C8], rbx
0x180017adc  movups  xmmword ptr [rbp+830h+NextHopInfo.NextHopAddress.AddressFamily], xmm0
0x180017ae0  movups  xmmword ptr [rbp+830h+NextHopInfo.NextHopAddress.AddrBits+0Ch], xmm0
0x180017ae4  movups  xmmword ptr [rbp+830h+NextHopInfo.InterfaceIndex], xmm0
0x180017ae8  call    memset_0
0x180017aed  mov     rax, [rsp+930h+var_8C0]
0x180017af2  lea     r9d, [r13+2]; TargetViews
0x180017af6  xor     r8d, r8d; ProtocolId
0x180017af9  mov     dword ptr [rbp+830h+DestAddress.AddressFamily], 200002h
0x180017b00  lea     rdx, [rbp+830h+DestAddress]; DestAddress
0x180017b04  mov     dword ptr [rbp+830h+DestAddress.AddrBits], esi
0x180017b07  mov     [rsp+930h+DestInfo], rbx; DestInfo
0x180017b0c  mov     [rax], r13
0x180017b0f  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180017b16  call    RtmGetMostSpecificDestination
0x180017b1b  test    eax, eax
0x180017b1d  jz      short loc_180017B6B
0x180017b1f  xor     r15d, r15d
0x180017b22  cmp     cs:qword_18002B8A8, r15
0x180017b29  jz      short loc_180017B61
0x180017b2b  mov     r8d, esi
0x180017b2e  mov     word ptr [rbp+830h+var_850], r15w
0x180017b33  lea     rdx, aNoRouteToSourc; "No Route to source %x"
0x180017b3a  lea     rcx, [rbp+830h+var_850]
0x180017b3e  call    FormatRRASErrorString
0x180017b43  mov     rdx, cs:qword_18002B8A8
0x180017b4a  lea     r8, [rbp+830h+var_850]
0x180017b4e  mov     rcx, cs:gMgmEtwContext
0x180017b55  mov     rax, cs:gMgmTemplateFunc
0x180017b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b61  mov     ebx, 3EBh
0x180017b66  jmp     loc_180017ED4
0x180017b6b  mov     rcx, rbx
0x180017b6e  call    SelectNextHop
0x180017b73  mov     [r15], rax
0x180017b76  xor     r15d, r15d
0x180017b79  test    rax, rax
0x180017b7c  jnz     short loc_180017BC7
0x180017b7e  cmp     cs:qword_18002B8A8, r15
0x180017b85  jz      short loc_180017BBD
0x180017b87  mov     r8d, esi
0x180017b8a  mov     word ptr [rbp+830h+var_850], r15w
0x180017b8f  lea     rdx, aNoNexthopToSou; "No NextHop to source %x"
0x180017b96  lea     rcx, [rbp+830h+var_850]
0x180017b9a  call    FormatRRASErrorString
0x180017b9f  mov     rdx, cs:qword_18002B8A8
0x180017ba6  lea     r8, [rbp+830h+var_850]
0x180017baa  mov     rcx, cs:gMgmEtwContext
0x180017bb1  mov     rax, cs:gMgmTemplateFunc
0x180017bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bbd  mov     ebx, 3EBh
0x180017bc2  jmp     loc_180017EBE
0x180017bc7  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180017bce  lea     r8, [rbp+830h+NextHopInfo]; NextHopInfo
0x180017bd2  mov     rdx, rax; NextHopHandle
0x180017bd5  call    RtmGetNextHopInfo
0x180017bda  test    eax, eax
0x180017bdc  jnz     loc_180017E7A
0x180017be2  cmp     [rbp+830h+NextHopInfo.State], r15w
0x180017be7  jnz     loc_180017E7A
0x180017bed  mov     eax, [rbp+830h+NextHopInfo.InterfaceIndex]
0x180017bf0  xor     edx, edx
0x180017bf2  mov     [rdi], eax
0x180017bf4  mov     [r14], r15d
0x180017bf7  mov     eax, [rdi]
0x180017bf9  div     cs:dword_18002B92C
0x180017bff  mov     rcx, cs:qword_18002B9E8
0x180017c06  mov     ebx, edx
0x180017c08  add     rcx, 10h
0x180017c0c  shl     rbx, 5
0x180017c10  add     rcx, rbx
0x180017c13  mov     r15d, edx
0x180017c16  call    AcquireReadLock
0x180017c1b  mov     r9, [rsp+930h+var_8D0]
0x180017c20  mov     [r12], r15d
0x180017c24  mov     rcx, cs:qword_18002B9E8
0x180017c2b  mov     edx, [rdi]
0x180017c2d  add     rcx, rbx
0x180017c30  mov     r8d, [r14]
0x180017c33  call    FindIfEntry
0x180017c38  mov     r11, [r9]
0x180017c3b  xor     ebx, ebx
0x180017c3d  test    r11, r11
0x180017c40  jz      loc_180017D8C
0x180017c46  mov     eax, [rdi]
0x180017c48  cmp     [r11+10h], eax
0x180017c4c  jnz     loc_180017D8C
0x180017c52  mov     r8d, [r11+1Ch]
0x180017c56  lea     rcx, qword_18002B9A8
0x180017c5d  mov     edx, [r11+18h]
0x180017c61  call    GetProtocolEntry
0x180017c66  mov     r13, rax
0x180017c69  test    rax, rax
0x180017c6c  jnz     short loc_180017CBB
0x180017c6e  cmp     cs:qword_18002B8A8, rbx
0x180017c75  jz      short loc_180017CB1
0x180017c77  mov     word ptr [rbp+830h+var_850], bx
0x180017c7b  lea     rdx, aInvokerpfcallb; "InvokeRPFCallbacks : No protocol entry "...
0x180017c82  mov     r9d, [r11+1Ch]
0x180017c86  lea     rcx, [rbp+830h+var_850]
0x180017c8a  mov     r8d, [r11+18h]
0x180017c8e  call    FormatRRASErrorString
0x180017c93  mov     rdx, cs:qword_18002B8A8
0x180017c9a  lea     r8, [rbp+830h+var_850]
0x180017c9e  mov     rcx, cs:gMgmEtwContext
0x180017ca5  mov     rax, cs:gMgmTemplateFunc
0x180017cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cb1  mov     ebx, 3EBh
0x180017cb6  jmp     loc_180017E03
0x180017cbb  mov     rax, [rax+28h]
0x180017cbf  test    rax, rax
0x180017cc2  jz      loc_180017E03
0x180017cc8  mov     rcx, [rsp+930h+var_8C8]
0x180017ccd  xor     r9d, r9d
0x180017cd0  mov     r8d, [rbp+830h+arg_28]
0x180017cd7  or      edx, 0FFFFFFFFh
0x180017cda  mov     [rsp+930h+var_8E8], rcx
0x180017cdf  mov     rcx, [rsp+930h+var_8B8]
0x180017ce4  mov     [rsp+930h+var_8F0], rcx
0x180017ce9  mov     ecx, [rbp+830h+arg_50]
0x180017cef  mov     [rsp+930h+var_8F8], ecx
0x180017cf3  mov     rcx, [rbp+830h+var_8B0]
0x180017cf7  mov     [rsp+930h+var_900], rcx
0x180017cfc  mov     ecx, esi
0x180017cfe  mov     qword ptr [rsp+930h+dwErrorCode], r14
0x180017d03  mov     [rsp+930h+DestInfo], rdi
0x180017d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d0d  mov     ebx, eax
0x180017d0f  cmp     eax, 57h ; 'W'
0x180017d12  jnz     loc_180017E03
0x180017d18  mov     eax, [rdi]
0x180017d1a  xor     edx, edx
0x180017d1c  div     cs:dword_18002B92C
0x180017d22  mov     esi, edx
0x180017d24  mov     r15d, edx
0x180017d27  shl     rsi, 5
0x180017d2b  mov     ebx, edx
0x180017d2d  cmp     [r12], edx
0x180017d31  jz      short loc_180017D65
0x180017d33  mov     ecx, [r12]
0x180017d37  mov     rax, cs:qword_18002B9E8
0x180017d3e  shl     rcx, 5
0x180017d42  add     rax, 10h
0x180017d46  add     rcx, rax
0x180017d49  call    ReleaseReadLock
0x180017d4e  mov     rcx, cs:qword_18002B9E8
0x180017d55  add     rcx, 10h
0x180017d59  add     rcx, rsi
0x180017d5c  call    AcquireReadLock
0x180017d61  mov     [r12], ebx
0x180017d65  mov     rcx, cs:qword_18002B9E8
0x180017d6c  mov     r9, [rsp+930h+var_8D0]
0x180017d71  add     rcx, rsi
0x180017d74  mov     edx, [rdi]
0x180017d76  mov     r8d, [r14]
0x180017d79  call    FindIfEntry
0x180017d7e  neg     eax
0x180017d80  sbb     ebx, ebx
0x180017d82  not     ebx
0x180017d84  and     ebx, 3EBh
0x180017d8a  jmp     short loc_180017E03
0x180017d8c  cmp     cs:qword_18002B8A8, rbx
0x180017d93  jz      short loc_180017DD2
0x180017d95  mov     r9d, [r14]
0x180017d98  lea     rdx, aInvokerpfcallb_0; "InvokeRPFCallbacks : New incoming Inter"...
0x180017d9f  mov     r8d, [rdi]
0x180017da2  lea     rcx, [rbp+830h+var_850]
0x180017da6  mov     word ptr [rbp+830h+var_850], bx
0x180017daa  mov     [rsp+930h+DestInfo], r11
0x180017daf  call    FormatRRASErrorString
0x180017db4  mov     rdx, cs:qword_18002B8A8
0x180017dbb  lea     r8, [rbp+830h+var_850]
0x180017dbf  mov     rcx, cs:gMgmEtwContext
0x180017dc6  mov     rax, cs:gMgmTemplateFunc
0x180017dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dd2  cmp     cs:dword_18002BA54, 2
0x180017dd9  mov     ebx, 3EBh
0x180017dde  jb      short loc_180017E03
0x180017de0  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180017de7  xor     r9d, r9d; dwSubStringCount
0x180017dea  mov     [rsp+930h+dwErrorCode], ebx; dwErrorCode
0x180017dee  mov     r8d, 0C35Fh; dwMessageId
0x180017df4  mov     [rsp+930h+DestInfo], r13; plpszSubStringArray
0x180017df9  lea     edx, [r9+2]; dwEventType
0x180017dfd  call    cs:__imp_RouterLogEventA
0x180017e03  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180017e0a  lea     rdx, [rbp+830h+NextHopInfo]; NextHopInfo
0x180017e0e  call    RtmReleaseNextHopInfo
0x180017e13  xor     ecx, ecx
0x180017e15  test    eax, eax
0x180017e17  jz      short loc_180017E57
0x180017e19  cmp     cs:qword_18002B8A8, rcx
0x180017e20  jz      short loc_180017E57
0x180017e22  mov     word ptr [rbp+830h+var_850], cx
0x180017e26  lea     rdx, aFailedToReleas_2; "Failed to release next hop : %x"
0x180017e2d  lea     rcx, [rbp+830h+var_850]
0x180017e31  mov     r8d, ebx
0x180017e34  call    FormatRRASErrorString
0x180017e39  mov     rdx, cs:qword_18002B8A8
0x180017e40  lea     r8, [rbp+830h+var_850]
0x180017e44  mov     rcx, cs:gMgmEtwContext
0x180017e4b  mov     rax, cs:gMgmTemplateFunc
0x180017e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e57  test    ebx, ebx
0x180017e59  jz      short loc_180017ED1
0x180017e5b  mov     rax, cs:qword_18002B9E8
0x180017e62  add     rax, 10h
0x180017e66  mov     ecx, r15d
0x180017e69  shl     rcx, 5
0x180017e6d  add     rcx, rax
0x180017e70  call    ReleaseReadLock
0x180017e75  xor     r15d, r15d
0x180017e78  jmp     short loc_180017EBE
0x180017e7a  cmp     cs:qword_18002B8A8, r15
0x180017e81  mov     ebx, 3EBh
0x180017e86  jz      short loc_180017EBE
0x180017e88  mov     r8d, esi
0x180017e8b  mov     word ptr [rbp+830h+var_850], r15w
0x180017e90  lea     rdx, aNoNexthopInfoT; "No Nexthop info to source %x"
0x180017e97  lea     rcx, [rbp+830h+var_850]
0x180017e9b  call    FormatRRASErrorString
0x180017ea0  mov     rdx, cs:qword_18002B8A8
0x180017ea7  lea     r8, [rbp+830h+var_850]
0x180017eab  mov     rcx, cs:gMgmEtwContext
0x180017eb2  mov     rax, cs:gMgmTemplateFunc
0x180017eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ebe  mov     rdx, [rsp+930h+var_8C8]; DestInfo
0x180017ec3  mov     rcx, cs:g_hRtmHandle; RtmRegHandle
0x180017eca  call    RtmReleaseDestInfo
0x180017ecf  jmp     short loc_180017ED4
0x180017ed1  xor     r15d, r15d
0x180017ed4  cmp     cs:qword_18002B8A8, r15
0x180017edb  mov     rax, [rsp+930h+var_8C0]
0x180017ee0  mov     [rax], r13
0x180017ee3  jz      short loc_180017F1B
0x180017ee5  mov     r8d, ebx
0x180017ee8  mov     word ptr [rbp+830h+var_850], r15w
0x180017eed  lea     rdx, aLeavingRpfCall; "LEAVING RPF Callback : %d"
0x180017ef4  lea     rcx, [rbp+830h+var_850]
0x180017ef8  call    FormatRRASErrorString
0x180017efd  mov     rdx, cs:qword_18002B8A8
0x180017f04  lea     r8, [rbp+830h+var_850]
0x180017f08  mov     rcx, cs:gMgmEtwContext
0x180017f0f  mov     rax, cs:gMgmTemplateFunc
0x180017f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f1b  mov     eax, ebx
0x180017f1d  mov     rcx, [rbp+830h+var_50]
0x180017f24  xor     rcx, rsp; StackCookie
0x180017f27  call    __security_check_cookie
0x180017f2c  add     rsp, 8F8h
0x180017f33  pop     r15
0x180017f35  pop     r14
0x180017f37  pop     r13
0x180017f39  pop     r12
0x180017f3b  pop     rdi
0x180017f3c  pop     rsi
0x180017f3d  pop     rbx
0x180017f3e  pop     rbp
0x180017f3f  retn
```
