# VPNIKEProtocolEngine::VPNIKEProtocolEngine(void)

- ea: `0x180002a00`
- end: `0x180002b85`
- name: `??0VPNIKEProtocolEngine@@IEAA@XZ`
- size: `389`
- prototype: `VPNIKEProtocolEngine *__fastcall(char *pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003d9c`

## callees

- `0x180002a00`
- `0x180007794`
- `0x1800077bc`
- `0x1800768d4`
- `0x180076b60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002ae8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180002ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b12`

## string_xrefs

- `0x180002a9f`: `VPNIKEProtocolEngine::VPNIKEProtocolEngine`

## pseudocode

```c
VPNIKEProtocolEngine *__fastcall VPNIKEProtocolEngine::VPNIKEProtocolEngine(char *pv)
{
  PTP_WORK ThreadpoolWork; // rax
  PVOID *v3; // rcx
  DWORD LastError; // eax
  __int64 v6; // [rsp+20h] [rbp-48h] BYREF
  __int128 v7; // [rsp+28h] [rbp-40h]
  __int128 v8; // [rsp+38h] [rbp-30h]
  __int64 v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]

  *((_DWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 2) = 0;
  *(_QWORD *)pv = &VPNIKEProtocolEngine::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
  }
  v7 = 0;
  v6 = 0;
  v8 = 0;
  v9 = 0;
  v10 = -1;
  v11 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v6,
      L"VPNIKEProtocolEngine::VPNIKEProtocolEngine",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  *((_QWORD *)pv + 13) = 0;
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 14) = 0;
  *((_QWORD *)pv + 15) = 0;
  *((_DWORD *)pv + 32) = 0;
  *((_OWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 8) = 0;
  *(_OWORD *)(pv + 72) = 0;
  *((_QWORD *)pv + 11) = 0;
  ThreadpoolWork = CreateThreadpoolWork(VPNIKEProtocolEngine::s_ProcessReleaseActiveConnectionsCallback, pv, 0);
  *((_QWORD *)pv + 17) = ThreadpoolWork;
  if ( ThreadpoolWork )
    goto LABEL_12;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_17;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids, LastError);
LABEL_12:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 6u )
    WPP_SF_(v3[2], 12, &WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids);
LABEL_17:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v6);
  return (VPNIKEProtocolEngine *)pv;
}

```

## disassembly

```asm
0x180002a00  mov     [rsp+arg_8], rbx
0x180002a05  mov     [rsp+arg_10], rbp
0x180002a0a  mov     [rsp+arg_0], rcx
0x180002a0f  push    rdi
0x180002a10  sub     rsp, 60h
0x180002a14  mov     rbx, rcx
0x180002a17  xor     edi, edi
0x180002a19  mov     [rcx+20h], edi
0x180002a1c  mov     [rcx+18h], rdi
0x180002a20  mov     [rcx+8], rdi
0x180002a24  mov     [rcx+10h], rdi
0x180002a28  lea     rax, ??_7VPNIKEProtocolEngine@@6B@; const VPNIKEProtocolEngine::`vftable'
0x180002a2f  mov     [rcx], rax
0x180002a32  lea     rbp, WPP_GLOBAL_Control
0x180002a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a40  cmp     rcx, rbp
0x180002a43  jz      short loc_180002A64
0x180002a45  test    byte ptr [rcx+1Ch], 1
0x180002a49  jz      short loc_180002A64
0x180002a4b  cmp     byte ptr [rcx+19h], 6
0x180002a4f  jb      short loc_180002A64
0x180002a51  lea     edx, [rdi+0Ah]
0x180002a54  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180002a5b  mov     rcx, [rcx+10h]
0x180002a5f  call    WPP_SF_
0x180002a64  xorps   xmm0, xmm0
0x180002a67  movdqu  [rsp+68h+var_40], xmm0
0x180002a6d  mov     [rsp+68h+var_48], rdi
0x180002a72  xorps   xmm1, xmm1
0x180002a75  movdqu  [rsp+68h+var_30], xmm1
0x180002a7b  mov     [rsp+68h+var_20], rdi
0x180002a80  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x180002a88  mov     [rsp+68h+var_14], edi
0x180002a8c  test    cs:byte_1800AA941, 8
0x180002a93  jz      short loc_180002AB0
0x180002a95  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180002a9c  xor     r8d, r8d; unsigned int *
0x180002a9f  lea     rdx, aVpnikeprotocol_3; "VPNIKEProtocolEngine::VPNIKEProtocolEng"...
0x180002aa6  lea     rcx, [rsp+68h+var_48]; this
0x180002aab  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180002ab0  mov     [rbx+68h], rdi
0x180002ab4  mov     [rbx+28h], rdi
0x180002ab8  mov     [rbx+70h], rdi
0x180002abc  mov     [rbx+78h], rdi
0x180002ac0  mov     [rbx+80h], edi
0x180002ac6  xorps   xmm0, xmm0
0x180002ac9  xor     eax, eax
0x180002acb  movups  xmmword ptr [rbx+30h], xmm0
0x180002acf  mov     [rbx+40h], rax
0x180002ad3  movups  xmmword ptr [rbx+48h], xmm0
0x180002ad7  mov     [rbx+58h], rax
0x180002adb  xor     r8d, r8d; pcbe
0x180002ade  mov     rdx, rbx; pv
0x180002ae1  lea     rcx, ?s_ProcessReleaseActiveConnectionsCallback@VPNIKEProtocolEngine@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180002ae8  call    cs:__imp_CreateThreadpoolWork
0x180002aee  mov     [rbx+88h], rax
0x180002af5  test    rax, rax
0x180002af8  jnz     short loc_180002B37
0x180002afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b01  cmp     rcx, rbp
0x180002b04  jz      short loc_180002B65
0x180002b06  test    byte ptr [rcx+1Ch], 1
0x180002b0a  jz      short loc_180002B3E
0x180002b0c  cmp     byte ptr [rcx+19h], 2
0x180002b10  jb      short loc_180002B3E
0x180002b12  call    cs:__imp_GetLastError
0x180002b18  mov     edx, 0Bh
0x180002b1d  mov     r9d, eax
0x180002b20  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180002b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b2e  mov     rcx, [rcx+10h]
0x180002b32  call    WPP_SF_d
0x180002b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b3e  cmp     rcx, rbp
0x180002b41  jz      short loc_180002B65
0x180002b43  test    byte ptr [rcx+1Ch], 1
0x180002b47  jz      short loc_180002B65
0x180002b49  cmp     byte ptr [rcx+19h], 6
0x180002b4d  jb      short loc_180002B65
0x180002b4f  mov     edx, 0Ch
0x180002b54  lea     r8, WPP_5af496c13ec43a98c93897c89f9b8adf_Traceguids
0x180002b5b  mov     rcx, [rcx+10h]
0x180002b5f  call    WPP_SF_
0x180002b64  nop
0x180002b65  lea     rcx, [rsp+68h+var_48]; this
0x180002b6a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180002b6f  nop
0x180002b70  mov     rax, rbx
0x180002b73  lea     r11, [rsp+68h+var_8]
0x180002b78  mov     rbx, [r11+18h]
0x180002b7c  mov     rbp, [r11+20h]
0x180002b80  mov     rsp, r11
0x180002b83  pop     rdi
0x180002b84  retn
```
