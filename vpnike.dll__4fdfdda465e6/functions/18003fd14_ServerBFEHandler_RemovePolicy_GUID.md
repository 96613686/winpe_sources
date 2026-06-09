# ServerBFEHandler::RemovePolicy(_GUID &)

- ea: `0x18003fd14`
- end: `0x18003fecf`
- name: `?RemovePolicy@ServerBFEHandler@@KAKAEAU_GUID@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a470`
- `0x1800400a8`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002e6f4`
- `0x18003fd14`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003fe10`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x18003fe10`

## string_xrefs

- `0x18003fe31`: `RemovePolicy failed: %u`
- `0x18003fddf`: `ServerBFEHandler::RemovePolicy`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::RemovePolicy(GUID *key)
{
  DWORD v2; // eax
  unsigned int v3; // ebx
  unsigned int v5; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE engineHandle; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h]
  __int128 v9; // [rsp+48h] [rbp-B8h]
  __int64 v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+64h] [rbp-9Ch]
  int v13; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v5 = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v7,
      L"ServerBFEHandler::RemovePolicy",
      &v5,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  engineHandle = 0;
  BFEHandler::GetBfeHandle(&engineHandle);
  if ( engineHandle )
  {
    v2 = FwpmIPsecTunnelDeleteByKey0(engineHandle, key);
    v5 = v2;
    if ( v2 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"RemovePolicy failed: %u", v2);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v13);
      }
    }
    *key = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v5);
  }
  v3 = v5;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v7);
  return v3;
}

```

## disassembly

```asm
0x18003fd14  mov     [rsp-8+arg_8], rbx
0x18003fd19  mov     [rsp-8+arg_10], rsi
0x18003fd1e  push    rbp
0x18003fd1f  lea     rbp, [rsp-780h]
0x18003fd27  sub     rsp, 880h
0x18003fd2e  mov     rax, cs:__security_cookie
0x18003fd35  xor     rax, rsp
0x18003fd38  mov     [rbp+780h+var_10], rax
0x18003fd3f  mov     rbx, rcx
0x18003fd42  lea     rsi, WPP_GLOBAL_Control
0x18003fd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd50  cmp     rcx, rsi
0x18003fd53  jz      short loc_18003FD76
0x18003fd55  test    byte ptr [rcx+1Ch], 1
0x18003fd59  jz      short loc_18003FD76
0x18003fd5b  cmp     byte ptr [rcx+19h], 6
0x18003fd5f  jb      short loc_18003FD76
0x18003fd61  mov     edx, 3Bh ; ';'
0x18003fd66  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003fd6d  mov     rcx, [rcx+10h]
0x18003fd71  call    WPP_SF_
0x18003fd76  mov     [rsp+880h+var_860], 0
0x18003fd7e  xor     eax, eax
0x18003fd80  mov     [rsp+880h+var_810], eax
0x18003fd84  xor     edx, edx; Val
0x18003fd86  mov     r8d, 7FCh; Size
0x18003fd8c  lea     rcx, [rsp+880h+var_80C]; void *
0x18003fd91  call    memset_0
0x18003fd96  xorps   xmm0, xmm0
0x18003fd99  movdqu  [rsp+880h+var_848], xmm0
0x18003fd9f  mov     [rsp+880h+var_850], 0
0x18003fda8  xorps   xmm1, xmm1
0x18003fdab  movdqu  [rsp+880h+var_838], xmm1
0x18003fdb1  mov     [rsp+880h+var_828], 0
0x18003fdba  mov     [rsp+880h+var_820], 0FFFFFFFFh
0x18003fdc2  mov     [rsp+880h+var_81C], 0
0x18003fdca  test    cs:byte_1800AA941, 8
0x18003fdd1  jz      short loc_18003FDF0
0x18003fdd3  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003fdda  lea     r8, [rsp+880h+var_860]; unsigned int *
0x18003fddf  lea     rdx, aServerbfehandl_7; "ServerBFEHandler::RemovePolicy"
0x18003fde6  lea     rcx, [rsp+880h+var_850]; this
0x18003fdeb  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003fdf0  mov     [rsp+880h+engineHandle], 0
0x18003fdf9  lea     rcx, [rsp+880h+engineHandle]; void **
0x18003fdfe  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x18003fe03  mov     rcx, [rsp+880h+engineHandle]; engineHandle
0x18003fe08  test    rcx, rcx
0x18003fe0b  jz      short loc_18003FE69
0x18003fe0d  mov     rdx, rbx; key
0x18003fe10  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x18003fe16  mov     r8d, eax
0x18003fe19  mov     [rsp+880h+var_860], eax
0x18003fe1d  test    eax, eax
0x18003fe1f  jz      short loc_18003FE63
0x18003fe21  test    cs:byte_1800AA941, 4
0x18003fe28  jz      short loc_18003FE63
0x18003fe2a  xor     eax, eax
0x18003fe2c  mov     word ptr [rsp+880h+var_810], ax
0x18003fe31  lea     rdx, aRemovepolicyFa; "RemovePolicy failed: %u"
0x18003fe38  lea     rcx, [rsp+880h+var_810]
0x18003fe3d  call    FormatRRASErrorString
0x18003fe42  test    cs:byte_1800AA941, 4
0x18003fe49  jz      short loc_18003FE63
0x18003fe4b  lea     r8, [rsp+880h+var_810]
0x18003fe50  lea     rdx, RasVpnIkeTraceError
0x18003fe57  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003fe5e  call    McTemplateU0z_EventWriteTransfer
0x18003fe63  xorps   xmm0, xmm0
0x18003fe66  movups  xmmword ptr [rbx], xmm0
0x18003fe69  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe70  cmp     rcx, rsi
0x18003fe73  jz      short loc_18003FE9B
0x18003fe75  test    byte ptr [rcx+1Ch], 1
0x18003fe79  jz      short loc_18003FE9B
0x18003fe7b  cmp     byte ptr [rcx+19h], 6
0x18003fe7f  jb      short loc_18003FE9B
0x18003fe81  mov     edx, 3Ch ; '<'
0x18003fe86  mov     r9d, [rsp+880h+var_860]
0x18003fe8b  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003fe92  mov     rcx, [rcx+10h]
0x18003fe96  call    WPP_SF_d
0x18003fe9b  mov     ebx, [rsp+880h+var_860]
0x18003fe9f  lea     rcx, [rsp+880h+var_850]; this
0x18003fea4  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003fea9  mov     eax, ebx
0x18003feab  mov     rcx, [rbp+780h+var_10]
0x18003feb2  xor     rcx, rsp; StackCookie
0x18003feb5  call    __security_check_cookie
0x18003feba  lea     r11, [rsp+880h+var_s0]
0x18003fec2  mov     rbx, [r11+18h]
0x18003fec6  mov     rsi, [r11+20h]
0x18003feca  mov     rsp, r11
0x18003fecd  pop     rbp
0x18003fece  retn
```
