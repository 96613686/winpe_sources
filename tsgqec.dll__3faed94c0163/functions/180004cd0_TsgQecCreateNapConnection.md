# TsgQecCreateNapConnection

- ea: `0x180004cd0`
- end: `0x180004ea1`
- name: `TsgQecCreateNapConnection`
- size: `465`
- prototype: `__int64 __fastcall(__int64, struct CAANapConnection **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002ccc`
- `0x180003970`
- `0x180004cd0`
- `0x1800053ac`
- `0x180005658`
- `0x18000c010`

## string_xrefs

- `0x180004da3`: `g_pNECBinding->CreateConnection`

## pseudocode

```c
__int64 __fastcall TsgQecCreateNapConnection(__int64 a1, struct CAANapConnection **a2)
{
  int v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // eax
  __int64 v6; // r8
  int v7; // eax
  CAANapEnforcementClientCallback *v8; // rcx
  struct INapEnforcementClientConnection *v10; // [rsp+48h] [rbp+10h] BYREF
  struct CAANapConnection *v11; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v10 = 0;
  v11 = 0;
  if ( g_pNECBinding )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, struct INapEnforcementClientConnection **))(*(_QWORD *)g_pNECBinding + 40LL))(
           g_pNECBinding,
           &v10);
    v6 = (unsigned int)v5;
    if ( v5 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(struct INapEnforcementClientConnection *, __int64 *, _QWORD))(*(_QWORD *)v10 + 64LL))(
             v10,
             qword_1800101D8,
             (unsigned int)v5);
      v6 = (unsigned int)v7;
      if ( v7 >= 0 )
      {
        v3 = CAANapEnforcementClientCallback::AddConnection(v8, v10, &v11);
        if ( v3 >= 0 )
          goto LABEL_25;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
            (unsigned int)L"g_pNECCallback->AddConnection",
            v3);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
          (unsigned int)L"necConnection->SetConnectionId",
          v7);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        (unsigned int)L"g_pNECBinding->CreateConnection",
        v5);
    }
    if ( v10 )
    {
      (*(void (__fastcall **)(LPVOID, struct INapEnforcementClientConnection *, __int64))(*(_QWORD *)g_pNECBinding + 64LL))(
        g_pNECBinding,
        v10,
        v6);
      if ( v10 )
        (*(void (__fastcall **)(struct INapEnforcementClientConnection *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v3 = -2147001886;
  }
  else
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
LABEL_25:
  *a2 = v11;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004cd0  mov     [rsp+arg_0], rbx
0x180004cd5  push    rdi
0x180004cd6  sub     rsp, 30h
0x180004cda  mov     qword ptr [rdx], 0
0x180004ce1  mov     rdi, rdx
0x180004ce4  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004ceb  mov     [rsp+38h+arg_8], 0
0x180004cf4  mov     [rsp+38h+arg_10], 0
0x180004cfd  test    rcx, rcx
0x180004d00  jnz     short loc_180004D56
0x180004d02  xor     ebx, ebx
0x180004d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d0b  lea     rax, WPP_GLOBAL_Control
0x180004d12  cmp     rcx, rax
0x180004d15  jz      loc_180004E8C
0x180004d1b  test    byte ptr [rcx+1Ch], 1
0x180004d1f  jz      loc_180004E8C
0x180004d25  cmp     byte ptr [rcx+19h], 2
0x180004d29  jb      loc_180004E8C
0x180004d2f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180004d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d3b  lea     edx, [rbx+1Eh]
0x180004d3e  mov     r9d, eax
0x180004d41  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004d48  mov     rcx, [rcx+10h]
0x180004d4c  call    WPP_SF_D
0x180004d51  jmp     loc_180004E8C
0x180004d56  mov     rax, [rcx]
0x180004d59  lea     rdx, [rsp+38h+arg_8]
0x180004d5e  mov     rax, [rax+28h]
0x180004d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d67  mov     r8d, eax
0x180004d6a  test    eax, eax
0x180004d6c  jns     short loc_180004DAF
0x180004d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d75  lea     rax, WPP_GLOBAL_Control
0x180004d7c  cmp     rcx, rax
0x180004d7f  jz      loc_180004E54
0x180004d85  test    byte ptr [rcx+1Ch], 8
0x180004d89  jz      loc_180004E54
0x180004d8f  cmp     byte ptr [rcx+19h], 2
0x180004d93  jb      loc_180004E54
0x180004d99  mov     edx, 1Fh
0x180004d9e  mov     [rsp+38h+var_18], r8d
0x180004da3  lea     r9, aGPnecbindingCr; "g_pNECBinding->CreateConnection"
0x180004daa  jmp     loc_180004E44
0x180004daf  mov     rcx, [rsp+38h+arg_8]
0x180004db4  lea     rdx, qword_1800101D8
0x180004dbb  mov     rax, [rcx]
0x180004dbe  mov     rax, [rax+40h]
0x180004dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc7  mov     r8d, eax
0x180004dca  test    eax, eax
0x180004dcc  jns     short loc_180004E00
0x180004dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dd5  lea     rax, WPP_GLOBAL_Control
0x180004ddc  cmp     rcx, rax
0x180004ddf  jz      short loc_180004E54
0x180004de1  test    byte ptr [rcx+1Ch], 8
0x180004de5  jz      short loc_180004E54
0x180004de7  cmp     byte ptr [rcx+19h], 2
0x180004deb  jb      short loc_180004E54
0x180004ded  mov     edx, 20h ; ' '
0x180004df2  mov     [rsp+38h+var_18], r8d
0x180004df7  lea     r9, aNecconnectionS; "necConnection->SetConnectionId"
0x180004dfe  jmp     short loc_180004E44
0x180004e00  mov     rdx, [rsp+38h+arg_8]; struct INapEnforcementClientConnection *
0x180004e05  lea     r8, [rsp+38h+arg_10]; struct CAANapConnection **
0x180004e0a  call    ?AddConnection@CAANapEnforcementClientCallback@@QEAAJPEAUINapEnforcementClientConnection@@PEAPEAVCAANapConnection@@@Z; CAANapEnforcementClientCallback::AddConnection(INapEnforcementClientConnection *,CAANapConnection * *)
0x180004e0f  mov     ebx, eax
0x180004e11  test    eax, eax
0x180004e13  jns     short loc_180004E8C
0x180004e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e1c  lea     rax, WPP_GLOBAL_Control
0x180004e23  cmp     rcx, rax
0x180004e26  jz      short loc_180004E54
0x180004e28  test    byte ptr [rcx+1Ch], 8
0x180004e2c  jz      short loc_180004E54
0x180004e2e  cmp     byte ptr [rcx+19h], 2
0x180004e32  jb      short loc_180004E54
0x180004e34  mov     edx, 21h ; '!'
0x180004e39  mov     [rsp+38h+var_18], ebx
0x180004e3d  lea     r9, aGPneccallbackA; "g_pNECCallback->AddConnection"
0x180004e44  mov     rcx, [rcx+10h]
0x180004e48  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004e4f  call    WPP_SF_Sd
0x180004e54  mov     rdx, [rsp+38h+arg_8]
0x180004e59  test    rdx, rdx
0x180004e5c  jz      short loc_180004E87
0x180004e5e  mov     rcx, cs:?g_pNECBinding@@3PEAUINapEnforcementClientBinding@@EA; INapEnforcementClientBinding * g_pNECBinding
0x180004e65  mov     rax, [rcx]
0x180004e68  mov     rax, [rax+40h]
0x180004e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e71  mov     rcx, [rsp+38h+arg_8]
0x180004e76  test    rcx, rcx
0x180004e79  jz      short loc_180004E87
0x180004e7b  mov     rax, [rcx]
0x180004e7e  mov     rax, [rax+10h]
0x180004e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e87  mov     ebx, 800759E2h
0x180004e8c  mov     rax, [rsp+38h+arg_10]
0x180004e91  mov     [rdi], rax
0x180004e94  mov     eax, ebx
0x180004e96  mov     rbx, [rsp+38h+arg_0]
0x180004e9b  add     rsp, 30h
0x180004e9f  pop     rdi
0x180004ea0  retn
```
