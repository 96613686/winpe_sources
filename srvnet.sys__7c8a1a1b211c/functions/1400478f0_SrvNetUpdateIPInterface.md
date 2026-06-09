# SrvNetUpdateIPInterface

- ea: `0x1400478f0`
- end: `0x140047a5b`
- name: `SrvNetUpdateIPInterface`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140046d00`

## callees

- `0x140010d94`
- `0x14001111c`
- `0x14001389c`
- `0x14001a884`
- `0x14002a3e0`
- `0x140046b14`
- `0x1400478f0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047a31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047a31`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004797a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004797a`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140047954`
- `NETIO!ConvertInterfaceLuidToGuid` at `0x140047954`

## pseudocode

```c
void __fastcall SrvNetUpdateIPInterface(const NET_LUID *a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  char v4; // si
  NTSTATUS v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // eax
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  GUID InterfaceGuid; // [rsp+30h] [rbp-28h] BYREF

  v3 = a3;
  v4 = a2;
  InterfaceGuid = 0;
  if ( (_WORD)a3 != 2 && (_WORD)a3 != 23 )
  {
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
      McTemplateK0id_EtwWriteTransfer(a1, a2, a3, a1->Value, -1073741637);
    return;
  }
  v6 = ConvertInterfaceLuidToGuid(a1, &InterfaceGuid);
  if ( v6 >= 0 )
  {
    KeEnterCriticalRegion();
    if ( v4 )
    {
      SrvNetEnsureUniversalEndpoint();
      LOBYTE(v10) = v3 == 23;
      LOBYTE(v11) = v3 == 2;
      v12 = SrvNetEnableInterface(&InterfaceGuid, v11, v10);
      if ( v12 >= 0 )
        goto LABEL_21;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_21;
      }
      v14 = 50;
    }
    else
    {
      v12 = SrvNetDisableInterface(&InterfaceGuid, v3 == 2, v3 == 23);
      if ( v12 >= 0 )
        goto LABEL_21;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_21;
      }
      v14 = 51;
    }
    WPP_SF_d(v13->AttachedDevice, v14, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids, (unsigned int)v12);
LABEL_21:
    KeLeaveCriticalRegion();
    return;
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
    McTemplateK0id_EtwWriteTransfer(v8, v7, v9, a1->Value, v6);
}

```

## disassembly

```asm
0x1400478f0  mov     [rsp+arg_8], rbx
0x1400478f5  mov     [rsp+arg_10], rsi
0x1400478fa  push    rdi
0x1400478fb  sub     rsp, 50h
0x1400478ff  mov     rax, cs:__security_cookie
0x140047906  xor     rax, rsp
0x140047909  mov     [rsp+58h+var_18], rax
0x14004790e  xorps   xmm0, xmm0
0x140047911  movzx   ebx, r8w
0x140047915  mov     sil, dl
0x140047918  mov     rdi, rcx
0x14004791b  movups  xmmword ptr [rsp+58h+InterfaceGuid.Data1], xmm0
0x140047920  cmp     r8w, 2
0x140047925  jz      short loc_14004794F
0x140047927  cmp     bx, 17h
0x14004792b  jz      short loc_14004794F
0x14004792d  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x140047934  jz      loc_140047A3D
0x14004793a  mov     r9, [rcx]
0x14004793d  mov     [rsp+58h+var_38], 0C00000BBh
0x140047945  call    McTemplateK0id_EtwWriteTransfer
0x14004794a  jmp     loc_140047A3D
0x14004794f  lea     rdx, [rsp+58h+InterfaceGuid]; InterfaceGuid
0x140047954  call    cs:__imp_ConvertInterfaceLuidToGuid
0x14004795b  nop     dword ptr [rax+rax+00h]
0x140047960  test    eax, eax
0x140047962  jns     short loc_14004797A
0x140047964  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14004796b  jz      loc_140047A3D
0x140047971  mov     r9, [rdi]
0x140047974  mov     [rsp+58h+var_38], eax
0x140047978  jmp     short loc_140047945
0x14004797a  call    cs:__imp_KeEnterCriticalRegion
0x140047981  nop     dword ptr [rax+rax+00h]
0x140047986  test    sil, sil
0x140047989  jz      short loc_1400479DA
0x14004798b  call    SrvNetEnsureUniversalEndpoint
0x140047990  cmp     bx, 17h
0x140047994  lea     rcx, [rsp+58h+InterfaceGuid]
0x140047999  setz    r8b
0x14004799d  cmp     bx, 2
0x1400479a1  setz    dl
0x1400479a4  call    SrvNetEnableInterface
0x1400479a9  test    eax, eax
0x1400479ab  jns     loc_140047A31
0x1400479b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400479b8  lea     rdx, WPP_GLOBAL_Control
0x1400479bf  cmp     rcx, rdx
0x1400479c2  jz      short loc_140047A31
0x1400479c4  test    dword ptr [rcx+2Ch], 2000h
0x1400479cb  jz      short loc_140047A31
0x1400479cd  cmp     byte ptr [rcx+29h], 2
0x1400479d1  jb      short loc_140047A31
0x1400479d3  mov     edx, 32h ; '2'
0x1400479d8  jmp     short loc_140047A1E
0x1400479da  cmp     bx, 17h
0x1400479de  lea     rcx, [rsp+58h+InterfaceGuid]; Source2
0x1400479e3  setz    r8b
0x1400479e7  cmp     bx, 2
0x1400479eb  setz    dl
0x1400479ee  call    SrvNetDisableInterface
0x1400479f3  test    eax, eax
0x1400479f5  jns     short loc_140047A31
0x1400479f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400479fe  lea     rdx, WPP_GLOBAL_Control
0x140047a05  cmp     rcx, rdx
0x140047a08  jz      short loc_140047A31
0x140047a0a  test    dword ptr [rcx+2Ch], 2000h
0x140047a11  jz      short loc_140047A31
0x140047a13  cmp     byte ptr [rcx+29h], 2
0x140047a17  jb      short loc_140047A31
0x140047a19  mov     edx, 33h ; '3'
0x140047a1e  mov     rcx, [rcx+18h]
0x140047a22  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140047a29  mov     r9d, eax
0x140047a2c  call    WPP_SF_d
0x140047a31  call    cs:__imp_KeLeaveCriticalRegion
0x140047a38  nop     dword ptr [rax+rax+00h]
0x140047a3d  mov     rcx, [rsp+58h+var_18]
0x140047a42  xor     rcx, rsp; StackCookie
0x140047a45  call    __security_check_cookie
0x140047a4a  mov     rbx, [rsp+58h+arg_8]
0x140047a4f  mov     rsi, [rsp+58h+arg_10]
0x140047a54  add     rsp, 50h
0x140047a58  pop     rdi
0x140047a59  retn
```
