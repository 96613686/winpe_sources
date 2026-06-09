# UbpmStatsOperation

- ea: `0x1800182a0`
- end: `0x180018550`
- name: `UbpmStatsOperation`
- size: `688`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006820`
- `0x18000a230`
- `0x180016b50`
- `0x180016e70`
- `0x180017110`
- `0x180017590`
- `0x180018fbc`
- `0x18002ee00`
- `0x18002fde0`

## callees

- `0x1800182a0`
- `0x18001af64`
- `0x180040260`

## import_xrefs

- `ntdll!RtlStringFromGUIDEx` at `0x18001837a`
- `ntdll!RtlStringFromGUIDEx` at `0x18001837a`
- `ntdll!RtlNtStatusToDosError` at `0x1800184c7`
- `ntdll!RtlNtStatusToDosError` at `0x1800184c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183dd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001845b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001845b`

## string_xrefs

- `0x1800182c8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tasks\`

## pseudocode

```c
__int64 __fastcall UbpmStatsOperation(__int64 a1, int a2, void *a3)
{
  _QWORD *v4; // rcx
  NTSTATUS v7; // eax
  ULONG ValueW; // ebx
  int v10; // ebx
  _QWORD *v11; // rcx
  int v12; // edx
  DWORD pdwType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v15[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[70]; // [rsp+60h] [rbp-A0h] BYREF
  char v17; // [rsp+ECh] [rbp-14h] BYREF
  __int128 v18; // [rsp+EEh] [rbp-12h]
  __int128 v19; // [rsp+FEh] [rbp-2h]
  __int128 v20; // [rsp+10Eh] [rbp+Eh]
  _OWORD v21[2]; // [rsp+11Eh] [rbp+1Eh] BYREF

  v4 = *(_QWORD **)(a1 + 24);
  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\TaskCach\\Tasks\\");
  v15[0] = 5111808;
  memset(v21, 0, 28);
  pdwType = 0;
  pcbData = 0;
  v18 = 0;
  v15[1] = &v17;
  v19 = 0;
  v20 = 0;
  v7 = RtlStringFromGUIDEx(*v4, v15, 0);
  if ( v7 < 0 )
  {
    ValueW = RtlNtStatusToDosError(v7);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return ValueW;
    v12 = 10;
LABEL_24:
    WPP_SF_Sd(
      v11[2],
      v12,
      (unsigned int)WPP_d401fd39dfc6369b9feb72694b3070fb_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      ValueW);
    return ValueW;
  }
  WORD5(v21[1]) = 0;
  pcbData = 36;
  pdwType = 3;
  if ( a2 )
  {
    v10 = a2 - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
        return 0;
      else
        return 87;
    }
    ValueW = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"DynamicInfo", 3u, a3, 0x24u);
    if ( !ValueW )
      return ValueW;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return ValueW;
    v12 = 11;
    goto LABEL_24;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"DynamicInfo", 8u, &pdwType, a3, &pcbData);
  if ( ValueW )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return ValueW;
    v12 = 12;
    goto LABEL_24;
  }
  if ( pdwType != 3 || pcbData != 36 )
  {
    ValueW = 13;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 13;
      goto LABEL_24;
    }
  }
  return ValueW;
}

```

## disassembly

```asm
0x1800182a0  mov     [rsp-8+arg_8], rbx
0x1800182a5  mov     [rsp-8+arg_18], rsi
0x1800182aa  push    rbp
0x1800182ab  push    rdi
0x1800182ac  push    r14
0x1800182ae  lea     rbp, [rsp-50h]
0x1800182b3  sub     rsp, 150h
0x1800182ba  mov     rax, cs:__security_cookie
0x1800182c1  xor     rax, rsp
0x1800182c4  mov     [rbp+60h+var_20], rax
0x1800182c8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800182cf  lea     rax, [rbp+60h+var_74]
0x1800182d3  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x1800182da  mov     rsi, rcx
0x1800182dd  mov     rcx, [rcx+18h]
0x1800182e1  xor     r14d, r14d
0x1800182e4  movaps  xmmword ptr [rsp+160h+SubKey], xmm0
0x1800182e9  mov     rdi, r8
0x1800182ec  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+20h; "ft\\Windows NT\\CurrentVersion\\Schedul"...
0x1800182f3  mov     ebx, edx
0x1800182f5  movaps  [rsp+160h+var_F0], xmm1
0x1800182fa  lea     rdx, [rsp+160h+var_118]
0x1800182ff  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+30h; "ws NT\\CurrentVersion\\Schedule\\TaskCa"...
0x180018306  xor     r8d, r8d
0x180018309  movaps  [rbp+60h+var_E0], xmm0
0x18001830d  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+40h; "rrentVersion\\Schedule\\TaskCache\\Task"...
0x180018314  movaps  [rbp+60h+var_D0], xmm1
0x180018318  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+50h; "sion\\Schedule\\TaskCache\\Tasks\\"
0x18001831f  movaps  [rbp+60h+var_C0], xmm0
0x180018323  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+60h; "edule\\TaskCache\\Tasks\\"
0x18001832a  movaps  [rbp+60h+var_B0], xmm1
0x18001832e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+70h; "skCache\\Tasks\\"
0x180018335  movaps  [rbp+60h+var_90], xmm1
0x180018339  xorps   xmm1, xmm1
0x18001833c  movaps  [rbp+60h+var_A0], xmm0
0x180018340  movups  xmm0, xmmword ptr cs:aSoftwareMicros_0+7Eh; "\\Tasks\\"
0x180018347  mov     [rsp+160h+var_118], 4E0000h
0x180018350  movups  [rbp+60h+var_42], xmm1
0x180018354  mov     [rsp+160h+var_120], r14d
0x180018359  movups  [rbp+60h+var_90+0Eh], xmm0
0x18001835d  mov     [rsp+160h+var_11C], r14d
0x180018362  movups  [rbp+60h+var_72], xmm1
0x180018366  mov     [rsp+160h+var_110], rax
0x18001836b  movups  [rbp+60h+var_62], xmm1
0x18001836f  movups  [rbp+60h+var_52], xmm1
0x180018373  movups  [rbp+60h+var_42+0Ch], xmm1
0x180018377  mov     rcx, [rcx]
0x18001837a  call    cs:__imp_RtlStringFromGUIDEx
0x180018381  nop     dword ptr [rax+rax+00h]
0x180018386  test    eax, eax
0x180018388  js      loc_1800184C5
0x18001838e  mov     [rbp+60h+var_28], r14w
0x180018393  mov     [rsp+160h+var_11C], 24h ; '$'
0x18001839b  mov     [rsp+160h+var_120], 3
0x1800183a3  test    ebx, ebx
0x1800183a5  jnz     loc_180018430
0x1800183ab  lea     rax, [rsp+160h+var_11C]
0x1800183b0  mov     r9d, 8; dwFlags
0x1800183b6  mov     [rsp+160h+pcbData], rax; pcbData
0x1800183bb  lea     r8, Value; "DynamicInfo"
0x1800183c2  lea     rax, [rsp+160h+var_120]
0x1800183c7  mov     [rsp+160h+pvData], rdi; pvData
0x1800183cc  lea     rdx, [rsp+160h+SubKey]; lpSubKey
0x1800183d1  mov     [rsp+160h+pdwType], rax; pdwType
0x1800183d6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800183dd  call    cs:__imp_RegGetValueW
0x1800183e4  nop     dword ptr [rax+rax+00h]
0x1800183e9  mov     ebx, eax
0x1800183eb  test    eax, eax
0x1800183ed  jnz     loc_18001849D
0x1800183f3  cmp     [rsp+160h+var_120], 3
0x1800183f8  jnz     loc_180018507
0x1800183fe  cmp     [rsp+160h+var_11C], 24h ; '$'
0x180018403  jnz     loc_180018507
0x180018409  mov     eax, ebx
0x18001840b  mov     rcx, [rbp+60h+var_20]
0x18001840f  xor     rcx, rsp; StackCookie
0x180018412  call    __security_check_cookie
0x180018417  lea     r11, [rsp+160h+var_10]
0x18001841f  mov     rbx, [r11+28h]
0x180018423  mov     rsi, [r11+38h]
0x180018427  mov     rsp, r11
0x18001842a  pop     r14
0x18001842c  pop     rdi
0x18001842d  pop     rbp
0x18001842e  retn
0x180018430  sub     ebx, 1
0x180018433  jnz     short loc_180018490
0x180018435  mov     dword ptr [rsp+160h+pvData], 24h ; '$'; cbData
0x18001843d  lea     r8, Value; "DynamicInfo"
0x180018444  mov     r9d, 3; dwType
0x18001844a  mov     [rsp+160h+pdwType], rdi; lpData
0x18001844f  lea     rdx, [rsp+160h+SubKey]; lpSubKey
0x180018454  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001845b  call    cs:__imp_RegSetKeyValueW
0x180018462  nop     dword ptr [rax+rax+00h]
0x180018467  mov     ebx, eax
0x180018469  test    eax, eax
0x18001846b  jz      short loc_180018409
0x18001846d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018474  lea     rax, WPP_GLOBAL_Control
0x18001847b  cmp     rcx, rax
0x18001847e  jz      short loc_180018409
0x180018480  test    byte ptr [rcx+1Ch], 1
0x180018484  jz      short loc_180018409
0x180018486  mov     edx, 0Bh
0x18001848b  jmp     loc_18001852F
0x180018490  cmp     ebx, 1
0x180018493  jnz     short loc_1800184FD
0x180018495  mov     ebx, r14d
0x180018498  jmp     loc_180018409
0x18001849d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184a4  lea     rax, WPP_GLOBAL_Control
0x1800184ab  cmp     rcx, rax
0x1800184ae  jz      loc_180018409
0x1800184b4  test    byte ptr [rcx+1Ch], 1
0x1800184b8  jz      loc_180018409
0x1800184be  mov     edx, 0Ch
0x1800184c3  jmp     short loc_18001852F
0x1800184c5  mov     ecx, eax; Status
0x1800184c7  call    cs:__imp_RtlNtStatusToDosError
0x1800184ce  nop     dword ptr [rax+rax+00h]
0x1800184d3  mov     ebx, eax
0x1800184d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184dc  lea     rax, WPP_GLOBAL_Control
0x1800184e3  cmp     rcx, rax
0x1800184e6  jz      loc_180018409
0x1800184ec  test    byte ptr [rcx+1Ch], 1
0x1800184f0  jz      loc_180018409
0x1800184f6  mov     edx, 0Ah
0x1800184fb  jmp     short loc_18001852F
0x1800184fd  mov     ebx, 57h ; 'W'
0x180018502  jmp     loc_180018409
0x180018507  mov     ebx, 0Dh
0x18001850c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018513  lea     rax, WPP_GLOBAL_Control
0x18001851a  cmp     rcx, rax
0x18001851d  jz      loc_180018409
0x180018523  test    byte ptr [rcx+1Ch], 1
0x180018527  jz      loc_180018409
0x18001852d  mov     edx, ebx
0x18001852f  mov     r9, [rsi+18h]
0x180018533  lea     r8, WPP_d401fd39dfc6369b9feb72694b3070fb_Traceguids
0x18001853a  mov     rcx, [rcx+10h]
0x18001853e  mov     dword ptr [rsp+160h+pdwType], ebx
0x180018542  mov     r9, [r9+8]
0x180018546  call    WPP_SF_Sd
0x18001854b  jmp     loc_180018409
```
