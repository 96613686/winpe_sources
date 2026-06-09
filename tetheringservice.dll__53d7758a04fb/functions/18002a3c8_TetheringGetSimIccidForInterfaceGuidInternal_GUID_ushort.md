# TetheringGetSimIccidForInterfaceGuidInternal(_GUID,ushort *)

- ea: `0x18002a3c8`
- end: `0x18002a63a`
- name: `?TetheringGetSimIccidForInterfaceGuidInternal@@YAJU_GUID@@PEAG@Z`
- size: `626`
- prototype: `int(struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dfd8`
- `0x18000f76c`
- `0x180013be0`
- `0x1800229b8`
- `0x18002bad8`
- `0x18002cd48`
- `0x18002d868`

## callees

- `0x180003064`
- `0x18000bf74`
- `0x18000f9a4`
- `0x18002a3c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a43d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a43d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a452`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18002a4fa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18002a4fa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002a44a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002a618`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002a44a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18002a618`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002a52b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002a605`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002a52b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002a605`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18002a470`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18002a470`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TetheringGetSimIccidForInterfaceGuidInternal(struct _GUID *a1, unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // ebx
  TetheringServiceTelemetry *v6; // rcx
  __int64 v7; // rdx
  int Interface; // eax
  __int64 v9; // rdx
  bool v10; // sf
  __int64 v11; // rcx
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v15[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v16; // [rsp+58h] [rbp-18h]
  __int64 v17; // [rsp+60h] [rbp-10h]
  char v18; // [rsp+68h] [rbp-8h]

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, a1);
  }
  v14 = 0;
  v15[0] = 0;
  v13 = -1;
  v4 = WwanOpenHandle(1, 0, v15, &v13);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v7 = 156;
    goto LABEL_29;
  }
  v15[1] = 0;
  v16 = &v14;
  v17 = 0;
  v18 = 1;
  Interface = WwanQueryInterface(v13, a1, 7);
  v5 = Interface;
  if ( Interface > 0 )
    v5 = (unsigned __int16)Interface | 0x80070000;
  if ( v18 )
  {
    v9 = *v16;
    *v16 = v17;
    if ( v9 )
      WwanFreeMemory(v9);
  }
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v7 = 157;
    goto LABEL_29;
  }
  v5 = *(_DWORD *)(v14 + 1024);
  v10 = v5 < 0;
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5 | 0x80070000;
    v10 = v5 < 0;
  }
  if ( v10 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v7 = 158;
    goto LABEL_29;
  }
  if ( !wcscpy_s(a2, 0x15u, (const wchar_t *)(v14 + 952)) )
  {
LABEL_30:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v5 = -2147418113;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_34;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 159;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, (unsigned int)v5);
    goto LABEL_30;
  }
LABEL_31:
  if ( v6 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v6 + 2), 160, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, (unsigned int)v5);
LABEL_34:
  v11 = v14;
  v14 = 0;
  if ( v11 )
    WwanFreeMemory(v11);
  if ( v13 != -1 )
    WwanCloseHandle(v13, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a3c8  mov     [rsp-28h+arg_10], rbx
0x18002a3cd  mov     [rsp-28h+arg_18], rsi
0x18002a3d2  push    rbp
0x18002a3d3  push    rdi
0x18002a3d4  push    r12
0x18002a3d6  push    r13
0x18002a3d8  push    r14
0x18002a3da  mov     rbp, rsp
0x18002a3dd  sub     rsp, 70h
0x18002a3e1  mov     r14, rdx
0x18002a3e4  mov     rsi, rcx
0x18002a3e7  lea     r12, WPP_GLOBAL_Control
0x18002a3ee  lea     r13, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002a3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3fc  cmp     rcx, r12
0x18002a3ff  jz      short loc_18002A41C
0x18002a401  test    byte ptr [rcx+1Ch], 8
0x18002a405  jz      short loc_18002A41C
0x18002a407  mov     edx, 9Bh
0x18002a40c  mov     r9, rsi
0x18002a40f  mov     r8, r13
0x18002a412  mov     rcx, [rcx+10h]
0x18002a416  call    WPP_SF__guid_
0x18002a41b  nop
0x18002a41c  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x18002a424  mov     [rbp+var_28], 0
0x18002a42c  mov     [rbp+var_20], 0
0x18002a433  mov     rdi, [rbp+var_30]
0x18002a437  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002a43b  jz      short loc_18002A459
0x18002a43d  call    cs:__imp_GetLastError
0x18002a443  mov     ebx, eax
0x18002a445  xor     edx, edx
0x18002a447  mov     rcx, rdi
0x18002a44a  call    cs:__imp_WwanCloseHandle
0x18002a450  mov     ecx, ebx; dwErrCode
0x18002a452  call    cs:__imp_SetLastError
0x18002a458  nop
0x18002a459  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x18002a461  lea     r9, [rbp+var_30]
0x18002a465  lea     r8, [rbp+var_20]
0x18002a469  xor     edx, edx
0x18002a46b  lea     edi, [rdx+1]
0x18002a46e  mov     ecx, edi
0x18002a470  call    cs:__imp_WwanOpenHandle
0x18002a476  mov     ebx, eax
0x18002a478  test    eax, eax
0x18002a47a  jle     short loc_18002A485
0x18002a47c  movzx   ebx, ax
0x18002a47f  or      ebx, 80070000h
0x18002a485  test    ebx, ebx
0x18002a487  jns     short loc_18002A4AD
0x18002a489  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a490  cmp     rcx, r12
0x18002a493  jz      loc_18002A5F4
0x18002a499  test    [rcx+1Ch], dil
0x18002a49d  jz      loc_18002A5D5
0x18002a4a3  mov     edx, 9Ch
0x18002a4a8  jmp     loc_18002A5BF
0x18002a4ad  mov     [rbp+var_1C], 0
0x18002a4b4  lea     rax, [rbp+var_28]
0x18002a4b8  mov     [rbp+var_18], rax
0x18002a4bc  mov     [rbp+var_10], 0
0x18002a4c4  mov     [rbp+var_8], dil
0x18002a4c8  mov     [rsp+70h+var_38], 0
0x18002a4d1  mov     [rsp+70h+var_40], 0
0x18002a4da  lea     rax, [rbp+var_10]
0x18002a4de  mov     [rsp+70h+var_48], rax
0x18002a4e3  lea     rax, [rbp+var_1C]
0x18002a4e7  mov     [rsp+70h+var_50], rax
0x18002a4ec  xor     r9d, r9d
0x18002a4ef  lea     r8d, [r9+7]
0x18002a4f3  mov     rdx, rsi
0x18002a4f6  mov     rcx, [rbp+var_30]
0x18002a4fa  call    cs:__imp_WwanQueryInterface
0x18002a500  mov     ebx, eax
0x18002a502  test    eax, eax
0x18002a504  jle     short loc_18002A50F
0x18002a506  movzx   ebx, ax
0x18002a509  or      ebx, 80070000h
0x18002a50f  cmp     [rbp+var_8], 0
0x18002a513  jz      short loc_18002A531
0x18002a515  mov     rcx, [rbp+var_18]
0x18002a519  mov     rdx, [rcx]
0x18002a51c  mov     rax, [rbp+var_10]
0x18002a520  mov     [rcx], rax
0x18002a523  test    rdx, rdx
0x18002a526  jz      short loc_18002A531
0x18002a528  mov     rcx, rdx
0x18002a52b  call    cs:__imp_WwanFreeMemory
0x18002a531  test    ebx, ebx
0x18002a533  jns     short loc_18002A556
0x18002a535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a53c  cmp     rcx, r12
0x18002a53f  jz      loc_18002A5F4
0x18002a545  test    [rcx+1Ch], dil
0x18002a549  jz      loc_18002A5D5
0x18002a54f  mov     edx, 9Dh
0x18002a554  jmp     short loc_18002A5BF
0x18002a556  mov     r8, [rbp+var_28]
0x18002a55a  mov     ebx, [r8+400h]
0x18002a561  test    ebx, ebx
0x18002a563  jle     short loc_18002A570
0x18002a565  movzx   ebx, bx
0x18002a568  or      ebx, 80070000h
0x18002a56e  test    ebx, ebx
0x18002a570  jns     short loc_18002A58B
0x18002a572  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a579  cmp     rcx, r12
0x18002a57c  jz      short loc_18002A5F4
0x18002a57e  test    [rcx+1Ch], dil
0x18002a582  jz      short loc_18002A5D5
0x18002a584  mov     edx, 9Eh
0x18002a589  jmp     short loc_18002A5BF
0x18002a58b  add     r8, 3B8h; Source
0x18002a592  mov     edx, 15h; SizeInWords
0x18002a597  mov     rcx, r14; Destination
0x18002a59a  call    wcscpy_s
0x18002a59f  test    eax, eax
0x18002a5a1  jz      short loc_18002A5CE
0x18002a5a3  mov     ebx, 8000FFFFh
0x18002a5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5af  cmp     rcx, r12
0x18002a5b2  jz      short loc_18002A5F4
0x18002a5b4  test    [rcx+1Ch], dil
0x18002a5b8  jz      short loc_18002A5D5
0x18002a5ba  mov     edx, 9Fh
0x18002a5bf  mov     r9d, ebx
0x18002a5c2  mov     r8, r13
0x18002a5c5  mov     rcx, [rcx+10h]
0x18002a5c9  call    WPP_SF_d
0x18002a5ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5d5  cmp     rcx, r12
0x18002a5d8  jz      short loc_18002A5F4
0x18002a5da  test    byte ptr [rcx+1Ch], 8
0x18002a5de  jz      short loc_18002A5F4
0x18002a5e0  mov     edx, 0A0h
0x18002a5e5  mov     r9d, ebx
0x18002a5e8  mov     r8, r13
0x18002a5eb  mov     rcx, [rcx+10h]
0x18002a5ef  call    WPP_SF_d
0x18002a5f4  mov     rcx, [rbp+var_28]
0x18002a5f8  mov     [rbp+var_28], 0
0x18002a600  test    rcx, rcx
0x18002a603  jz      short loc_18002A60C
0x18002a605  call    cs:__imp_WwanFreeMemory
0x18002a60b  nop
0x18002a60c  mov     rcx, [rbp+var_30]
0x18002a610  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a614  jz      short loc_18002A61F
0x18002a616  xor     edx, edx
0x18002a618  call    cs:__imp_WwanCloseHandle
0x18002a61e  nop
0x18002a61f  mov     eax, ebx
0x18002a621  lea     r11, [rsp+70h+var_s0]
0x18002a626  mov     rbx, [r11+40h]
0x18002a62a  mov     rsi, [r11+48h]
0x18002a62e  mov     rsp, r11
0x18002a631  pop     r14
0x18002a633  pop     r13
0x18002a635  pop     r12
0x18002a637  pop     rdi
0x18002a638  pop     rbp
0x18002a639  retn
```
