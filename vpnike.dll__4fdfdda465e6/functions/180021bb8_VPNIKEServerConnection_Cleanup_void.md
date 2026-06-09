# VPNIKEServerConnection::Cleanup(void)

- ea: `0x180021bb8`
- end: `0x180021e6a`
- name: `?Cleanup@VPNIKEServerConnection@@AEAAXXZ`
- size: `690`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180021730`
- `0x180021a84`

## callees

- `0x180007610`
- `0x180007794`
- `0x180021bb8`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021dcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021dfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021dcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021dfa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021dec`

## string_xrefs

- `0x180021d23`: `DeleteEventHandle: %d`

## pseudocode

```c
void __fastcall VPNIKEServerConnection::Cleanup(void **this)
{
  unsigned int v2; // esi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  unsigned int v4; // edi
  _DWORD *v5; // rcx
  void *v6; // rdx
  __int128 *v7; // r9
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rdi
  HANDLE v13; // rax
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+38h] [rbp-C8h]
  __int128 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  __int128 v20; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 v22; // [rsp+7Ch] [rbp-84h]
  __int128 v23; // [rsp+8Ch] [rbp-74h]
  int v24; // [rsp+9Ch] [rbp-64h]
  int v25; // [rsp+A0h] [rbp-60h] BYREF
  char v26[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v20 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v2 = -1;
  v18 = -1;
  v19 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"VPNIKEServerConnection::Cleanup",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
  v3 = (void (__fastcall ***)(_QWORD, __int64))this[16];
  if ( v3 )
  {
    (**v3)(v3, 1);
    this[16] = 0;
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)VpnIkeProtocolEngine + 5) + 8LL))(
         *((_QWORD *)VpnIkeProtocolEngine + 5),
         *((unsigned int *)this + 2));
  if ( v4 && (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v25) = 0;
    LOWORD(v21) = 0;
    v5 = this[14];
    if ( v5 && *((_QWORD *)v5 + 2) )
      v2 = v5[4];
    ConvertPortNoToString(&v21, v2);
    FormatRRASErrorString(&v25, L"DeleteEventHandle: %d", v4);
    if ( (byte_1800AA941 & 4) != 0 )
    {
      v6 = this[14];
      LODWORD(v7) = (_DWORD)v6 + 2120;
      if ( !v6 )
        v7 = &v20;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasVpnIkeParamTraceError,
        (unsigned int)&v25,
        (_DWORD)v7,
        ((unsigned __int64)v6 + 2686) & -(__int64)(v6 != 0),
        (__int64)&v21);
    }
  }
  v8 = this[56];
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
    this[56] = 0;
  }
  v10 = this[57];
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
    this[57] = 0;
  }
  v12 = this[59];
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
    this[59] = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids);
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
}

```

## disassembly

```asm
0x180021bb8  mov     [rsp-8+arg_8], rbx
0x180021bbd  mov     [rsp-8+arg_10], rsi
0x180021bc2  push    rbp
0x180021bc3  push    rdi
0x180021bc4  push    r15
0x180021bc6  lea     rbp, [rsp-7B0h]
0x180021bce  sub     rsp, 8B0h
0x180021bd5  mov     rax, cs:__security_cookie
0x180021bdc  xor     rax, rsp
0x180021bdf  mov     [rbp+7C0h+var_20], rax
0x180021be6  mov     rbx, rcx
0x180021be9  lea     r15, WPP_GLOBAL_Control
0x180021bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bf7  cmp     rcx, r15
0x180021bfa  jz      short loc_180021C1D
0x180021bfc  test    byte ptr [rcx+1Ch], 1
0x180021c00  jz      short loc_180021C1D
0x180021c02  cmp     byte ptr [rcx+19h], 6
0x180021c06  jb      short loc_180021C1D
0x180021c08  mov     edx, 53h ; 'S'
0x180021c0d  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180021c14  mov     rcx, [rcx+10h]
0x180021c18  call    WPP_SF_
0x180021c1d  xor     eax, eax
0x180021c1f  mov     [rbp+7C0h+var_820], eax
0x180021c22  xor     edx, edx; Val
0x180021c24  mov     r8d, 7FCh; Size
0x180021c2a  lea     rcx, [rbp+7C0h+var_81C]; void *
0x180021c2e  call    memset_0
0x180021c33  xor     eax, eax
0x180021c35  mov     [rsp+8C0h+var_848], eax
0x180021c39  xorps   xmm0, xmm0
0x180021c3c  movups  [rsp+8C0h+var_844], xmm0
0x180021c41  movups  [rbp+7C0h+var_834], xmm0
0x180021c45  mov     [rbp+7C0h+var_824], eax
0x180021c48  movups  [rsp+8C0h+var_858], xmm0
0x180021c4d  xorps   xmm1, xmm1
0x180021c50  movdqu  [rsp+8C0h+var_888], xmm1
0x180021c56  mov     [rsp+8C0h+var_890], rax
0x180021c5b  movdqu  [rsp+8C0h+var_878], xmm0
0x180021c61  mov     [rsp+8C0h+var_868], rax
0x180021c66  or      esi, 0FFFFFFFFh
0x180021c69  mov     [rsp+8C0h+var_860], esi
0x180021c6d  mov     [rsp+8C0h+var_85C], eax
0x180021c71  test    cs:byte_1800AA941, 8
0x180021c78  jz      short loc_180021C9E
0x180021c7a  mov     rax, [rbx+70h]
0x180021c7e  mov     [rsp+8C0h+var_8A0], rax; void *
0x180021c83  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180021c8a  xor     r8d, r8d; unsigned int *
0x180021c8d  lea     rdx, aVpnikeserverco_19; "VPNIKEServerConnection::Cleanup"
0x180021c94  lea     rcx, [rsp+8C0h+var_890]; this
0x180021c99  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x180021c9e  mov     rcx, [rbx+80h]
0x180021ca5  test    rcx, rcx
0x180021ca8  jz      short loc_180021CC5
0x180021caa  mov     rax, [rcx]
0x180021cad  mov     edx, 1
0x180021cb2  mov     rax, [rax]
0x180021cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cba  mov     qword ptr [rbx+80h], 0
0x180021cc5  mov     rax, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x180021ccc  mov     rcx, [rax+28h]
0x180021cd0  mov     rax, [rcx]
0x180021cd3  mov     edx, [rbx+8]
0x180021cd6  mov     rax, [rax+8]
0x180021cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cdf  mov     edi, eax
0x180021ce1  test    eax, eax
0x180021ce3  jz      loc_180021D8A
0x180021ce9  test    cs:byte_1800AA941, 4
0x180021cf0  jz      loc_180021D8A
0x180021cf6  xor     ecx, ecx
0x180021cf8  mov     word ptr [rbp+7C0h+var_820], cx
0x180021cfc  mov     word ptr [rsp+8C0h+var_848], cx
0x180021d01  mov     rcx, [rbx+70h]
0x180021d05  test    rcx, rcx
0x180021d08  jz      short loc_180021D14
0x180021d0a  cmp     qword ptr [rcx+10h], 0
0x180021d0f  jz      short loc_180021D14
0x180021d11  mov     esi, [rcx+10h]
0x180021d14  mov     edx, esi
0x180021d16  lea     rcx, [rsp+8C0h+var_848]
0x180021d1b  call    ConvertPortNoToString
0x180021d20  mov     r8d, edi
0x180021d23  lea     rdx, aDeleteeventhan; "DeleteEventHandle: %d"
0x180021d2a  lea     rcx, [rbp+7C0h+var_820]
0x180021d2e  call    FormatRRASErrorString
0x180021d33  test    cs:byte_1800AA941, 4
0x180021d3a  jz      short loc_180021D8A
0x180021d3c  mov     rdx, [rbx+70h]
0x180021d40  mov     rax, rdx
0x180021d43  lea     rcx, [rdx+0A7Eh]
0x180021d4a  neg     rax
0x180021d4d  sbb     r8, r8
0x180021d50  and     r8, rcx
0x180021d53  test    rdx, rdx
0x180021d56  lea     r9, [rdx+848h]
0x180021d5d  jnz     short loc_180021D64
0x180021d5f  lea     r9, [rsp+8C0h+var_858]
0x180021d64  lea     rax, [rsp+8C0h+var_848]
0x180021d69  mov     [rsp+8C0h+var_898], rax
0x180021d6e  mov     [rsp+8C0h+var_8A0], r8
0x180021d73  lea     r8, [rbp+7C0h+var_820]
0x180021d77  lea     rdx, RasVpnIkeParamTraceError
0x180021d7e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180021d85  call    McTemplateU0zjzz_EventWriteTransfer
0x180021d8a  mov     rdi, [rbx+1C0h]
0x180021d91  test    rdi, rdi
0x180021d94  jz      short loc_180021DB5
0x180021d96  call    cs:__imp_GetProcessHeap
0x180021d9c  mov     r8, rdi; lpMem
0x180021d9f  xor     edx, edx; dwFlags
0x180021da1  mov     rcx, rax; hHeap
0x180021da4  call    cs:__imp_HeapFree
0x180021daa  mov     qword ptr [rbx+1C0h], 0
0x180021db5  mov     rdi, [rbx+1C8h]
0x180021dbc  test    rdi, rdi
0x180021dbf  jz      short loc_180021DE0
0x180021dc1  call    cs:__imp_GetProcessHeap
0x180021dc7  mov     r8, rdi; lpMem
0x180021dca  xor     edx, edx; dwFlags
0x180021dcc  mov     rcx, rax; hHeap
0x180021dcf  call    cs:__imp_HeapFree
0x180021dd5  mov     qword ptr [rbx+1C8h], 0
0x180021de0  mov     rdi, [rbx+1D8h]
0x180021de7  test    rdi, rdi
0x180021dea  jz      short loc_180021E0B
0x180021dec  call    cs:__imp_GetProcessHeap
0x180021df2  mov     r8, rdi; lpMem
0x180021df5  xor     edx, edx; dwFlags
0x180021df7  mov     rcx, rax; hHeap
0x180021dfa  call    cs:__imp_HeapFree
0x180021e00  mov     qword ptr [rbx+1D8h], 0
0x180021e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e12  cmp     rcx, r15
0x180021e15  jz      short loc_180021E39
0x180021e17  test    byte ptr [rcx+1Ch], 1
0x180021e1b  jz      short loc_180021E39
0x180021e1d  cmp     byte ptr [rcx+19h], 6
0x180021e21  jb      short loc_180021E39
0x180021e23  mov     edx, 54h ; 'T'
0x180021e28  lea     r8, WPP_01441162a14f348ab8d5b7cba18afd0a_Traceguids
0x180021e2f  mov     rcx, [rcx+10h]
0x180021e33  call    WPP_SF_
0x180021e38  nop
0x180021e39  lea     rcx, [rsp+8C0h+var_890]; this
0x180021e3e  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180021e43  mov     rcx, [rbp+7C0h+var_20]
0x180021e4a  xor     rcx, rsp; StackCookie
0x180021e4d  call    __security_check_cookie
0x180021e52  lea     r11, [rsp+8C0h+var_10]
0x180021e5a  mov     rbx, [r11+28h]
0x180021e5e  mov     rsi, [r11+30h]
0x180021e62  mov     rsp, r11
0x180021e65  pop     r15
0x180021e67  pop     rdi
0x180021e68  pop     rbp
0x180021e69  retn
```
