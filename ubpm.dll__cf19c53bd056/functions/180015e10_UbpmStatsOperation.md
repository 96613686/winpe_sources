# UbpmStatsOperation

- ea: `0x180015e10`
- end: `0x1800160a3`
- name: `UbpmStatsOperation`
- size: `659`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003050`
- `0x180005ed0`
- `0x180014840`
- `0x180014b30`
- `0x180014db0`
- `0x1800151d0`
- `0x1800169d4`
- `0x18002cd60`
- `0x18002dcc0`

## callees

- `0x180015e10`
- `0x18001e9f4`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlStringFromGUIDEx` at `0x180015eea`
- `ntdll!RtlStringFromGUIDEx` at `0x180015eea`
- `ntdll!RtlNtStatusToDosError` at `0x180016020`
- `ntdll!RtlNtStatusToDosError` at `0x180016020`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015f43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015f43`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180015fba`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180015fba`

## string_xrefs

- `0x180015e38`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\TaskCache\Tasks\`

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
0x180015e10  mov     [rsp-8+arg_8], rbx
0x180015e15  mov     [rsp-8+arg_18], rsi
0x180015e1a  push    rbp
0x180015e1b  push    rdi
0x180015e1c  push    r14
0x180015e1e  lea     rbp, [rsp-50h]
0x180015e23  sub     rsp, 150h
0x180015e2a  mov     rax, cs:__security_cookie
0x180015e31  xor     rax, rsp
0x180015e34  mov     [rbp+60h+var_20], rax
0x180015e38  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180015e3f  lea     rax, [rbp+60h+var_74]
0x180015e43  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x180015e4a  mov     rsi, rcx
0x180015e4d  mov     rcx, [rcx+18h]
0x180015e51  xor     r14d, r14d
0x180015e54  movaps  xmmword ptr [rsp+160h+SubKey], xmm0
0x180015e59  mov     rdi, r8
0x180015e5c  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+20h; "ft\\Windows NT\\CurrentVersion\\Schedul"...
0x180015e63  mov     ebx, edx
0x180015e65  movaps  [rsp+160h+var_F0], xmm1
0x180015e6a  lea     rdx, [rsp+160h+var_118]
0x180015e6f  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+30h; "ws NT\\CurrentVersion\\Schedule\\TaskCa"...
0x180015e76  xor     r8d, r8d
0x180015e79  movaps  [rbp+60h+var_E0], xmm0
0x180015e7d  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+40h; "rrentVersion\\Schedule\\TaskCache\\Task"...
0x180015e84  movaps  [rbp+60h+var_D0], xmm1
0x180015e88  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+50h; "sion\\Schedule\\TaskCache\\Tasks\\"
0x180015e8f  movaps  [rbp+60h+var_C0], xmm0
0x180015e93  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+60h; "edule\\TaskCache\\Tasks\\"
0x180015e9a  movaps  [rbp+60h+var_B0], xmm1
0x180015e9e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+70h; "skCache\\Tasks\\"
0x180015ea5  movaps  [rbp+60h+var_90], xmm1
0x180015ea9  xorps   xmm1, xmm1
0x180015eac  movaps  [rbp+60h+var_A0], xmm0
0x180015eb0  movups  xmm0, xmmword ptr cs:aSoftwareMicros_0+7Eh; "\\Tasks\\"
0x180015eb7  mov     [rsp+160h+var_118], 4E0000h
0x180015ec0  movups  [rbp+60h+var_42], xmm1
0x180015ec4  mov     [rsp+160h+var_120], r14d
0x180015ec9  movups  [rbp+60h+var_90+0Eh], xmm0
0x180015ecd  mov     [rsp+160h+var_11C], r14d
0x180015ed2  movups  [rbp+60h+var_72], xmm1
0x180015ed6  mov     [rsp+160h+var_110], rax
0x180015edb  movups  [rbp+60h+var_62], xmm1
0x180015edf  movups  [rbp+60h+var_52], xmm1
0x180015ee3  movups  [rbp+60h+var_42+0Ch], xmm1
0x180015ee7  mov     rcx, [rcx]
0x180015eea  call    cs:__imp_RtlStringFromGUIDEx
0x180015ef0  test    eax, eax
0x180015ef2  js      loc_18001601E
0x180015ef8  mov     [rbp+60h+var_28], r14w
0x180015efd  mov     [rsp+160h+var_11C], 24h ; '$'
0x180015f05  mov     [rsp+160h+var_120], 3
0x180015f0d  test    ebx, ebx
0x180015f0f  jnz     short loc_180015F8F
0x180015f11  lea     rax, [rsp+160h+var_11C]
0x180015f16  mov     r9d, 8; dwFlags
0x180015f1c  mov     [rsp+160h+pcbData], rax; pcbData
0x180015f21  lea     r8, Value; "DynamicInfo"
0x180015f28  lea     rax, [rsp+160h+var_120]
0x180015f2d  mov     [rsp+160h+pvData], rdi; pvData
0x180015f32  lea     rdx, [rsp+160h+SubKey]; lpSubKey
0x180015f37  mov     [rsp+160h+pdwType], rax; pdwType
0x180015f3c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015f43  call    cs:__imp_RegGetValueW
0x180015f49  mov     ebx, eax
0x180015f4b  test    eax, eax
0x180015f4d  jnz     loc_180015FF6
0x180015f53  cmp     [rsp+160h+var_120], 3
0x180015f58  jnz     loc_18001605A
0x180015f5e  cmp     [rsp+160h+var_11C], 24h ; '$'
0x180015f63  jnz     loc_18001605A
0x180015f69  mov     eax, ebx
0x180015f6b  mov     rcx, [rbp+60h+var_20]
0x180015f6f  xor     rcx, rsp; StackCookie
0x180015f72  call    __security_check_cookie
0x180015f77  lea     r11, [rsp+160h+var_10]
0x180015f7f  mov     rbx, [r11+28h]
0x180015f83  mov     rsi, [r11+38h]
0x180015f87  mov     rsp, r11
0x180015f8a  pop     r14
0x180015f8c  pop     rdi
0x180015f8d  pop     rbp
0x180015f8e  retn
0x180015f8f  sub     ebx, 1
0x180015f92  jnz     short loc_180015FE9
0x180015f94  mov     dword ptr [rsp+160h+pvData], 24h ; '$'; cbData
0x180015f9c  lea     r8, Value; "DynamicInfo"
0x180015fa3  mov     r9d, 3; dwType
0x180015fa9  mov     [rsp+160h+pdwType], rdi; lpData
0x180015fae  lea     rdx, [rsp+160h+SubKey]; lpSubKey
0x180015fb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015fba  call    cs:__imp_RegSetKeyValueW
0x180015fc0  mov     ebx, eax
0x180015fc2  test    eax, eax
0x180015fc4  jz      short loc_180015F69
0x180015fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fcd  lea     rax, WPP_GLOBAL_Control
0x180015fd4  cmp     rcx, rax
0x180015fd7  jz      short loc_180015F69
0x180015fd9  test    byte ptr [rcx+1Ch], 1
0x180015fdd  jz      short loc_180015F69
0x180015fdf  mov     edx, 0Bh
0x180015fe4  jmp     loc_180016082
0x180015fe9  cmp     ebx, 1
0x180015fec  jnz     short loc_180016050
0x180015fee  mov     ebx, r14d
0x180015ff1  jmp     loc_180015F69
0x180015ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ffd  lea     rax, WPP_GLOBAL_Control
0x180016004  cmp     rcx, rax
0x180016007  jz      loc_180015F69
0x18001600d  test    byte ptr [rcx+1Ch], 1
0x180016011  jz      loc_180015F69
0x180016017  mov     edx, 0Ch
0x18001601c  jmp     short loc_180016082
0x18001601e  mov     ecx, eax; Status
0x180016020  call    cs:__imp_RtlNtStatusToDosError
0x180016026  mov     ebx, eax
0x180016028  mov     rcx, cs:WPP_GLOBAL_Control
0x18001602f  lea     rax, WPP_GLOBAL_Control
0x180016036  cmp     rcx, rax
0x180016039  jz      loc_180015F69
0x18001603f  test    byte ptr [rcx+1Ch], 1
0x180016043  jz      loc_180015F69
0x180016049  mov     edx, 0Ah
0x18001604e  jmp     short loc_180016082
0x180016050  mov     ebx, 57h ; 'W'
0x180016055  jmp     loc_180015F69
0x18001605a  mov     ebx, 0Dh
0x18001605f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016066  lea     rax, WPP_GLOBAL_Control
0x18001606d  cmp     rcx, rax
0x180016070  jz      loc_180015F69
0x180016076  test    byte ptr [rcx+1Ch], 1
0x18001607a  jz      loc_180015F69
0x180016080  mov     edx, ebx
0x180016082  mov     r9, [rsi+18h]
0x180016086  lea     r8, WPP_d401fd39dfc6369b9feb72694b3070fb_Traceguids
0x18001608d  mov     rcx, [rcx+10h]
0x180016091  mov     dword ptr [rsp+160h+pdwType], ebx
0x180016095  mov     r9, [r9+8]
0x180016099  call    WPP_SF_Sd
0x18001609e  jmp     loc_180015F69
```
