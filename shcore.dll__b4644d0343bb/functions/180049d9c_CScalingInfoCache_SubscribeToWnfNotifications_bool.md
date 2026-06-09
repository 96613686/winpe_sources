# CScalingInfoCache::_SubscribeToWnfNotifications(bool)

- ea: `0x180049d9c`
- end: `0x180049ec7`
- name: `?_SubscribeToWnfNotifications@CScalingInfoCache@@AEAAJ_N@Z`
- size: `299`
- prototype: `__int64 __fastcall(CScalingInfoCache *__hidden this, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800266c0`
- `0x180049c9c`

## callees

- `0x180049d9c`
- `0x180049ed0`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180049ead`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180049ead`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180049e77`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180049e77`
- `ntdll!RtlQueryWnfStateData` at `0x180049e31`
- `ntdll!RtlQueryWnfStateData` at `0x180049e31`

## pseudocode

```c
__int64 __fastcall CScalingInfoCache::_SubscribeToWnfNotifications(CScalingInfoCache *this, char a2)
{
  int v2; // ebx
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  char *v10; // rdi
  __int64 v11; // [rsp+40h] [rbp-38h]
  char *v12; // [rsp+48h] [rbp-30h]
  __int64 v13; // [rsp+50h] [rbp-28h]
  char *v14; // [rsp+58h] [rbp-20h]
  __int64 v15; // [rsp+60h] [rbp-18h]
  char *v16; // [rsp+68h] [rbp-10h]
  unsigned int v17; // [rsp+B0h] [rbp+38h] BYREF

  v2 = 0;
  v11 = WNF_SPI_LOGICALDPIOVERRIDE;
  v12 = (char *)this + 160;
  v5 = 0;
  v13 = WNF_DX_MONITOR_CHANGE_NOTIFICATION;
  v14 = (char *)this + 168;
  v15 = WNF_DX_MODE_CHANGE_NOTIFICATION;
  v16 = (char *)this + 176;
  do
  {
    if ( v2 < 0 )
      break;
    v17 = 0;
    if ( a2 )
    {
      v6 = RtlQueryWnfStateData(&v17, *(&v11 + 2 * v5), CWindowTracker::WindowVisibilityChanged, 0, 0);
      v7 = ResultFromWin32FromStatus(v6);
      v2 = v7;
      if ( v7 < 0 )
      {
        if ( v7 == -2147024891 )
          v2 = 0;
      }
      else
      {
        v8 = RtlSubscribeWnfStateChangeNotification(
               (&v12)[2 * v5],
               *(&v11 + 2 * v5),
               v17,
               CScalingInfoCache::s_WnfCallback,
               this,
               0,
               0,
               1,
               v11,
               v12,
               v13,
               v14,
               v15,
               v16);
        v2 = ResultFromWin32FromStatus(v8);
      }
    }
    else
    {
      v10 = (&v12)[2 * v5];
      if ( *(_QWORD *)v10 )
      {
        RtlUnsubscribeWnfNotificationWaitForCompletion();
        *(_QWORD *)v10 = 0;
      }
    }
    ++v5;
  }
  while ( v5 < 3 );
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180049d9c  push    rbp
0x180049d9e  push    rbx
0x180049d9f  push    rsi
0x180049da0  push    rdi
0x180049da1  push    r14
0x180049da3  push    r15
0x180049da5  mov     rbp, rsp
0x180049da8  sub     rsp, 78h
0x180049dac  mov     rax, cs:WNF_SPI_LOGICALDPIOVERRIDE
0x180049db3  xor     ebx, ebx
0x180049db5  mov     [rbp+var_38], rax
0x180049db9  mov     r15b, dl
0x180049dbc  lea     rax, [rcx+0A0h]
0x180049dc3  mov     r14, rcx
0x180049dc6  mov     [rbp+var_30], rax
0x180049dca  xor     esi, esi
0x180049dcc  mov     rax, cs:WNF_DX_MONITOR_CHANGE_NOTIFICATION
0x180049dd3  mov     [rbp+var_28], rax
0x180049dd7  lea     rax, [rcx+0A8h]
0x180049dde  mov     [rbp+var_20], rax
0x180049de2  mov     rax, cs:WNF_DX_MODE_CHANGE_NOTIFICATION
0x180049de9  mov     [rbp+var_18], rax
0x180049ded  lea     rax, [rcx+0B0h]
0x180049df4  mov     [rbp+var_10], rax
0x180049df8  test    ebx, ebx
0x180049dfa  js      loc_180049E91
0x180049e00  mov     edi, esi
0x180049e02  add     rdi, rdi
0x180049e05  mov     [rbp+arg_0], 0
0x180049e0c  test    r15b, r15b
0x180049e0f  jz      loc_180049EA0
0x180049e15  mov     rdx, [rbp+rdi*8+var_38]
0x180049e1a  lea     r8, ?WindowVisibilityChanged@CWindowTracker@@UEAAJPEAUHWND__@@_N@Z; CWindowTracker::WindowVisibilityChanged(HWND__ *,bool)
0x180049e21  xor     r9d, r9d
0x180049e24  mov     [rsp+78h+var_58], 0
0x180049e2d  lea     rcx, [rbp+arg_0]
0x180049e31  call    cs:__imp_RtlQueryWnfStateData
0x180049e37  mov     ecx, eax; int
0x180049e39  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180049e3e  mov     ebx, eax
0x180049e40  test    eax, eax
0x180049e42  js      short loc_180049EBC
0x180049e44  mov     r8d, [rbp+arg_0]
0x180049e48  lea     r9, ?s_WnfCallback@CScalingInfoCache@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CScalingInfoCache::s_WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180049e4f  mov     rdx, [rbp+rdi*8+var_38]
0x180049e54  mov     rcx, [rbp+rdi*8+var_30]
0x180049e59  mov     [rsp+78h+var_40], 1
0x180049e61  mov     [rsp+78h+var_48], 0
0x180049e69  mov     [rsp+78h+var_50], 0
0x180049e72  mov     [rsp+78h+var_58], r14
0x180049e77  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180049e7d  mov     ecx, eax; int
0x180049e7f  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x180049e84  mov     ebx, eax
0x180049e86  inc     esi
0x180049e88  cmp     esi, 3
0x180049e8b  jb      loc_180049DF8
0x180049e91  mov     eax, ebx
0x180049e93  add     rsp, 78h
0x180049e97  pop     r15
0x180049e99  pop     r14
0x180049e9b  pop     rdi
0x180049e9c  pop     rsi
0x180049e9d  pop     rbx
0x180049e9e  pop     rbp
0x180049e9f  retn
0x180049ea0  mov     rdi, [rbp+rdi*8+var_30]
0x180049ea5  mov     rcx, [rdi]
0x180049ea8  test    rcx, rcx
0x180049eab  jz      short loc_180049E86
0x180049ead  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180049eb3  mov     qword ptr [rdi], 0
0x180049eba  jmp     short loc_180049E86
0x180049ebc  cmp     eax, 80070005h
0x180049ec1  jnz     short loc_180049E86
0x180049ec3  xor     ebx, ebx
0x180049ec5  jmp     short loc_180049E86
```
