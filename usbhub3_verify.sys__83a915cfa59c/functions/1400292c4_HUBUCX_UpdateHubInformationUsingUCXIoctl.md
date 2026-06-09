# HUBUCX_UpdateHubInformationUsingUCXIoctl

- ea: `0x1400292c4`
- end: `0x14002965c`
- name: `HUBUCX_UpdateHubInformationUsingUCXIoctl`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009f00`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x1400292c4`
- `0x14003bd60`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBUCX_UpdateHubInformationUsingUCXIoctl(__int64 a1)
{
  __int64 v1; // rsi
  int v3; // eax
  int v4; // edx
  int v5; // edi
  int v6; // r9d
  int v7; // edx
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // [rsp+28h] [rbp-41h]
  __int128 v11; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+70h] [rbp+7h]
  __int64 v13; // [rsp+78h] [rbp+Fh]
  __int128 v14; // [rsp+80h] [rbp+17h]
  __int64 v15; // [rsp+90h] [rbp+27h]
  __int64 v16; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int64 v17; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+E0h] [rbp+77h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v18 = 0;
  v15 = 0;
  v16 = 0;
  v12 = 0;
  v17 = 0;
  v13 = 0x100000001LL;
  v14 = *(unsigned __int64 *)(a1 + 16);
  v11 = 0;
  LODWORD(v11) = 56;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, unsigned __int64 *))(WdfFunctions_01015
                                                                                               + 1976))(
         WdfDriverGlobals,
         &v11,
         v1,
         &v17);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v15 = 0;
    v12 = 0;
    v13 = 0x100000001LL;
    v14 = v17;
    v11 = 0;
    LODWORD(v11) = 56;
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64, __int64, __int64, __int64 *, __int64 *))(WdfFunctions_01015 + 1536))(
           WdfDriverGlobals,
           &v11,
           512,
           1748191317,
           40,
           &v18,
           &v16);
    v5 = v3;
    if ( v3 >= 0 )
    {
      v8 = v16;
      *(_OWORD *)v16 = 0;
      *(_OWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 32) = 0;
      *(_DWORD *)v16 = 40;
      *(_QWORD *)(v16 + 8) = *(_QWORD *)(a1 + 248);
      *(_QWORD *)(v16 + 16) = *(_QWORD *)(a1 + 248);
      *(_DWORD *)(v16 + 24) = *(unsigned __int16 *)(a1 + 48);
      if ( *(_DWORD *)(a1 + 256) == 2 )
      {
        _InterlockedOr((volatile signed __int32 *)(a1 + 40), 1u);
        *(_DWORD *)(v16 + 28) = 1;
        if ( HUBDESC_ParseConfigurationDescriptor(
               *(_QWORD *)(a1 + 1272),
               *(_QWORD *)(a1 + 1272),
               -1,
               -1,
               9,
               -1,
               2,
               0,
               *(_QWORD *)(a1 + 2536)) )
        {
          _InterlockedOr((volatile signed __int32 *)(a1 + 40), 2u);
          *(_DWORD *)(v16 + 28) = *(unsigned __int16 *)(a1 + 48);
        }
        *(_DWORD *)(v16 + 32) = (*(unsigned __int16 *)(a1 + 1199) >> 5) & 3;
      }
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, unsigned __int64, __int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(WdfFunctions_01015 + 1528))(
             WdfDriverGlobals,
             v1,
             v17,
             4788263,
             v18,
             0,
             0,
             0,
             0,
             0);
      v5 = v3;
      if ( v3 >= 0 )
      {
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 (__fastcall *)(), __int64))(WdfFunctions_01015 + 2080))(
          WdfDriverGlobals,
          v17,
          HUBUCX_UpdateHubInformationUsingUCXIoctlComplete,
          a1);
        result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64, _QWORD))(WdfFunctions_01015 + 2024))(
                   WdfDriverGlobals,
                   v17,
                   v1,
                   0);
        if ( (_BYTE)result )
          return result;
        result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64))(WdfFunctions_01015 + 2032))(
                   WdfDriverGlobals,
                   v17);
        v5 = result;
        if ( (int)result >= 0 )
          return result;
        goto LABEL_17;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v6 = 66;
        goto LABEL_7;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v6 = 65;
      goto LABEL_7;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = 64;
LABEL_7:
    LODWORD(v10) = v3;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v4, 3, v6, (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids, v10);
LABEL_17:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v10) = v5;
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 2536),
        v7,
        3,
        67,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
        v10);
    }
  }
  if ( v17 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  return HUBSM_AddEvent(a1 + 1280, 2038);
}

```

## disassembly

```asm
0x1400292c4  mov     [rsp-8+arg_18], rbx
0x1400292c9  push    rbp
0x1400292ca  push    rsi
0x1400292cb  push    rdi
0x1400292cc  push    r12
0x1400292ce  push    r13
0x1400292d0  lea     rbp, [rsp-37h]
0x1400292d5  sub     rsp, 0A0h
0x1400292dc  mov     rsi, [rcx+20h]
0x1400292e0  lea     r9, [rbp+57h+arg_8]
0x1400292e4  xor     eax, eax
0x1400292e6  mov     [rbp+57h+arg_10], 0
0x1400292ee  mov     [rbp+57h+var_30], rax
0x1400292f2  lea     rdx, [rbp+57h+var_60]
0x1400292f6  xorps   xmm0, xmm0
0x1400292f9  mov     [rbp+57h+arg_0], 0
0x140029301  movups  [rbp+57h+var_50], xmm0
0x140029305  mov     eax, 1
0x14002930a  mov     [rbp+57h+arg_8], 0
0x140029312  mov     dword ptr [rbp+57h+var_50+8], eax
0x140029315  mov     rbx, rcx
0x140029318  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x14002931b  mov     r8, rsi
0x14002931e  mov     rax, [rcx+10h]
0x140029322  mov     rcx, cs:WdfDriverGlobals
0x140029329  movups  [rbp+57h+var_40], xmm0
0x14002932d  mov     qword ptr [rbp+57h+var_40], rax
0x140029331  mov     rax, cs:WdfFunctions_01015
0x140029338  movups  [rbp+57h+var_60], xmm0
0x14002933c  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x140029343  mov     rax, [rax+7B8h]
0x14002934a  call    _guard_dispatch_icall
0x14002934f  lea     r13, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140029356  mov     edi, eax
0x140029358  lea     r12, WPP_RECORDER_INITIALIZED
0x14002935f  test    eax, eax
0x140029361  jns     short loc_14002937B
0x140029363  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002936a  jz      loc_140029610
0x140029370  mov     r9d, 40h ; '@'
0x140029376  jmp     loc_140029408
0x14002937b  xor     eax, eax
0x14002937d  lea     rcx, [rbp+57h+arg_0]
0x140029381  mov     [rbp+57h+var_30], rax
0x140029385  lea     rdx, [rbp+57h+var_60]
0x140029389  mov     [rsp+0C0h+var_90], rcx
0x14002938e  xorps   xmm0, xmm0
0x140029391  movups  [rbp+57h+var_50], xmm0
0x140029395  mov     eax, 1
0x14002939a  lea     rcx, [rbp+57h+arg_10]
0x14002939e  mov     dword ptr [rbp+57h+var_50+8], eax
0x1400293a1  mov     r9d, 68334855h
0x1400293a7  mov     dword ptr [rbp+57h+var_50+0Ch], eax
0x1400293aa  mov     r8d, 200h
0x1400293b0  mov     rax, [rbp+57h+arg_8]
0x1400293b4  movups  [rbp+57h+var_40], xmm0
0x1400293b8  mov     qword ptr [rbp+57h+var_40], rax
0x1400293bc  mov     rax, cs:WdfFunctions_01015
0x1400293c3  movups  [rbp+57h+var_60], xmm0
0x1400293c7  mov     [rsp+0C0h+var_98], rcx
0x1400293cc  mov     rcx, cs:WdfDriverGlobals
0x1400293d3  mov     dword ptr [rbp+57h+var_60], 38h ; '8'
0x1400293da  mov     rax, [rax+600h]
0x1400293e1  mov     [rsp+0C0h+var_A0], 28h ; '('
0x1400293ea  call    _guard_dispatch_icall
0x1400293ef  mov     edi, eax
0x1400293f1  test    eax, eax
0x1400293f3  jns     short loc_14002942A
0x1400293f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400293fc  jz      loc_140029610
0x140029402  mov     r9d, 41h ; 'A'
0x140029408  mov     rcx, [rbx+9E8h]
0x14002940f  mov     r8d, 3
0x140029415  mov     dword ptr [rsp+0C0h+var_98], eax
0x140029419  mov     dl, 2
0x14002941b  mov     [rsp+0C0h+var_A0], r13
0x140029420  call    WPP_RECORDER_SF_d
0x140029425  jmp     loc_1400295E6
0x14002942a  mov     rax, [rbp+57h+arg_0]
0x14002942e  xor     ecx, ecx
0x140029430  xorps   xmm0, xmm0
0x140029433  movups  xmmword ptr [rax], xmm0
0x140029436  movups  xmmword ptr [rax+10h], xmm0
0x14002943a  mov     [rax+20h], rcx
0x14002943e  mov     rax, [rbp+57h+arg_0]
0x140029442  mov     dword ptr [rax], 28h ; '('
0x140029448  mov     rax, [rbp+57h+arg_0]
0x14002944c  mov     rcx, [rbx+0F8h]
0x140029453  mov     [rax+8], rcx
0x140029457  mov     rax, [rbp+57h+arg_0]
0x14002945b  mov     rcx, [rbx+0F8h]
0x140029462  mov     [rax+10h], rcx
0x140029466  mov     rax, [rbp+57h+arg_0]
0x14002946a  movzx   ecx, word ptr [rbx+30h]
0x14002946e  mov     [rax+18h], ecx
0x140029471  cmp     dword ptr [rbx+100h], 2
0x140029478  jnz     short loc_1400294F3
0x14002947a  lock or dword ptr [rbx+28h], 1
0x14002947f  mov     rax, [rbp+57h+arg_0]
0x140029483  or      r8d, 0FFFFFFFFh
0x140029487  mov     r9d, r8d
0x14002948a  mov     dword ptr [rax+1Ch], 1
0x140029491  mov     rax, [rbx+9E8h]
0x140029498  mov     rcx, [rbx+4F8h]
0x14002949f  mov     [rsp+0C0h+var_80], rax
0x1400294a4  mov     rdx, rcx
0x1400294a7  mov     [rsp+0C0h+var_88], 0
0x1400294b0  mov     dword ptr [rsp+0C0h+var_90], 2
0x1400294b8  mov     dword ptr [rsp+0C0h+var_98], r8d
0x1400294bd  mov     dword ptr [rsp+0C0h+var_A0], 9
0x1400294c5  call    HUBDESC_ParseConfigurationDescriptor
0x1400294ca  test    rax, rax
0x1400294cd  jz      short loc_1400294DF
0x1400294cf  lock or dword ptr [rbx+28h], 2
0x1400294d4  mov     rax, [rbp+57h+arg_0]
0x1400294d8  movzx   ecx, word ptr [rbx+30h]
0x1400294dc  mov     [rax+1Ch], ecx
0x1400294df  movzx   ecx, word ptr [rbx+4AFh]
0x1400294e6  mov     rax, [rbp+57h+arg_0]
0x1400294ea  shr     ecx, 5
0x1400294ed  and     ecx, 3
0x1400294f0  mov     [rax+20h], ecx
0x1400294f3  mov     rcx, [rbp+57h+arg_10]
0x1400294f7  mov     r9d, 491027h
0x1400294fd  mov     rax, cs:WdfFunctions_01015
0x140029504  mov     rdx, rsi
0x140029507  mov     r8, [rbp+57h+arg_8]
0x14002950b  mov     [rsp+0C0h+var_78], 0
0x140029514  mov     [rsp+0C0h+var_80], 0
0x14002951d  mov     rax, [rax+5F8h]
0x140029524  mov     [rsp+0C0h+var_88], 0
0x14002952d  mov     [rsp+0C0h+var_90], 0
0x140029536  mov     [rsp+0C0h+var_98], 0
0x14002953f  mov     [rsp+0C0h+var_A0], rcx
0x140029544  mov     rcx, cs:WdfDriverGlobals
0x14002954b  call    _guard_dispatch_icall
0x140029550  mov     edi, eax
0x140029552  test    eax, eax
0x140029554  jns     short loc_14002956E
0x140029556  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14002955d  jz      loc_140029610
0x140029563  mov     r9d, 42h ; 'B'
0x140029569  jmp     loc_140029408
0x14002956e  mov     rax, cs:WdfFunctions_01015
0x140029575  lea     r8, HUBUCX_UpdateHubInformationUsingUCXIoctlComplete
0x14002957c  mov     rdx, [rbp+57h+arg_8]
0x140029580  mov     r9, rbx
0x140029583  mov     rcx, cs:WdfDriverGlobals
0x14002958a  mov     rax, [rax+820h]
0x140029591  call    _guard_dispatch_icall
0x140029596  mov     rax, cs:WdfFunctions_01015
0x14002959d  xor     r9d, r9d
0x1400295a0  mov     rdx, [rbp+57h+arg_8]
0x1400295a4  mov     r8, rsi
0x1400295a7  mov     rcx, cs:WdfDriverGlobals
0x1400295ae  mov     rax, [rax+7E8h]
0x1400295b5  call    _guard_dispatch_icall
0x1400295ba  test    al, al
0x1400295bc  jnz     loc_140029644
0x1400295c2  mov     rax, cs:WdfFunctions_01015
0x1400295c9  mov     rdx, [rbp+57h+arg_8]
0x1400295cd  mov     rcx, cs:WdfDriverGlobals
0x1400295d4  mov     rax, [rax+7F0h]
0x1400295db  call    _guard_dispatch_icall
0x1400295e0  mov     edi, eax
0x1400295e2  test    eax, eax
0x1400295e4  jns     short loc_140029644
0x1400295e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400295ed  jz      short loc_140029610
0x1400295ef  mov     rcx, [rbx+9E8h]
0x1400295f6  mov     r9d, 43h ; 'C'
0x1400295fc  mov     dword ptr [rsp+0C0h+var_98], edi
0x140029600  mov     dl, 2
0x140029602  mov     [rsp+0C0h+var_A0], r13
0x140029607  lea     r8d, [r9-40h]
0x14002960b  call    WPP_RECORDER_SF_d
0x140029610  mov     rdx, [rbp+57h+arg_8]
0x140029614  test    rdx, rdx
0x140029617  jz      short loc_140029633
0x140029619  mov     rax, cs:WdfFunctions_01015
0x140029620  mov     rcx, cs:WdfDriverGlobals
0x140029627  mov     rax, [rax+680h]
0x14002962e  call    _guard_dispatch_icall
0x140029633  lea     rcx, [rbx+500h]
0x14002963a  mov     edx, 7F6h
0x14002963f  call    HUBSM_AddEvent
0x140029644  mov     rbx, [rsp+0C0h+arg_18]
0x14002964c  add     rsp, 0A0h
0x140029653  pop     r13
0x140029655  pop     r12
0x140029657  pop     rdi
0x140029658  pop     rsi
0x140029659  pop     rbp
0x14002965a  retn
```
