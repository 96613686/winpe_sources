# StillProbeCommitSetHandler

- ea: `0x140023c70`
- end: `0x140023df6`
- name: `StillProbeCommitSetHandler`
- size: `390`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015388`
- `0x14001f4f4`
- `0x140023934`

## callees

- `0x140009dc8`
- `0x14001b15c`
- `0x140023c70`
- `0x140040a30`

## pseudocode

```c
__int64 __fastcall StillProbeCommitSetHandler(int a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  char v5; // al
  char *v6; // rsi
  __int64 v7; // rbx
  char v8; // r9
  char v10; // al
  int v11; // edx
  int SetInterfaceControl; // edi
  int v13; // r8d
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v15; // rdx
  int v16; // edx
  int v17; // r8d
  PDEVICE_OBJECT v18; // rax
  int v19; // eax
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-40h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-40h]
  SIZE_T NumberOfBytesb; // [rsp+28h] [rbp-40h]
  _BYTE Src[11]; // [rsp+30h] [rbp-38h] BYREF

  v5 = *(_BYTE *)(a3 + 76);
  v6 = (char *)(a2 + 184);
  v7 = a2;
  v8 = *(_BYTE *)(a2 + 177);
  *(_QWORD *)Src = *(_QWORD *)(a2 + 184);
  LOBYTE(a2) = 1;
  Src[0] = v5;
  v10 = *(_BYTE *)(a3 + 77);
  LOBYTE(a3) = 3;
  Src[1] = v10;
  LODWORD(NumberOfBytes) = 11;
  *(_DWORD *)&Src[7] = 0;
  SetInterfaceControl = GetSetInterfaceControl(a1, a2, a3, v8, Src, NumberOfBytes);
  if ( SetInterfaceControl >= 0 )
  {
    LODWORD(NumberOfBytesa) = 11;
    LOBYTE(v13) = 3;
    LOBYTE(v11) = -127;
    SetInterfaceControl = GetSetInterfaceControl(a1, v11, v13, *(_BYTE *)(v7 + 177), Src, NumberOfBytesa);
    if ( SetInterfaceControl >= 0 )
    {
      v19 = *(_DWORD *)&Src[7];
      *(_QWORD *)v6 = *(_QWORD *)Src;
      *(_DWORD *)(v6 + 7) = v19;
      if ( !a5 )
        return (unsigned int)SetInterfaceControl;
      LOBYTE(v17) = 4;
      LODWORD(NumberOfBytesb) = 11;
      LOBYTE(v16) = 1;
      SetInterfaceControl = GetSetInterfaceControl(a1, v16, v17, *(_BYTE *)(v7 + 177), v6, NumberOfBytesb);
      if ( SetInterfaceControl >= 0 )
        return (unsigned int)SetInterfaceControl;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        return (unsigned int)SetInterfaceControl;
      v15 = 18;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        return (unsigned int)SetInterfaceControl;
      v15 = 17;
    }
    AttachedDevice = v18->AttachedDevice;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v15 = 16;
LABEL_15:
    WPP_SF_q(AttachedDevice, v15, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v7);
  }
  return (unsigned int)SetInterfaceControl;
}

```

## disassembly

```asm
0x140023c70  mov     [rsp+arg_18], rbx
0x140023c75  push    rbp
0x140023c76  push    rsi
0x140023c77  push    rdi
0x140023c78  sub     rsp, 50h
0x140023c7c  mov     rax, cs:__security_cookie
0x140023c83  xor     rax, rsp
0x140023c86  mov     [rsp+68h+var_28], rax
0x140023c8b  mov     al, [r8+4Ch]
0x140023c8f  lea     rsi, [rdx+0B8h]
0x140023c96  movsd   xmm0, qword ptr [rsi]
0x140023c9a  mov     rbx, rdx
0x140023c9d  mov     r9b, [rdx+0B1h]; int
0x140023ca4  mov     rbp, rcx
0x140023ca7  movsd   [rsp+68h+var_38], xmm0
0x140023cad  mov     dl, 1; int
0x140023caf  mov     byte ptr [rsp+68h+var_38], al
0x140023cb3  mov     al, [r8+4Dh]
0x140023cb7  mov     r8b, 3; int
0x140023cba  mov     byte ptr [rsp+68h+var_38+1], al
0x140023cbe  lea     rax, [rsp+68h+var_38]
0x140023cc3  mov     dword ptr [rsp+68h+NumberOfBytes], 0Bh; NumberOfBytes
0x140023ccb  mov     [rsp+68h+Src], rax; Src
0x140023cd0  mov     dword ptr [rsp+68h+var_38+7], 0
0x140023cd8  call    GetSetInterfaceControl
0x140023cdd  mov     edi, eax
0x140023cdf  test    eax, eax
0x140023ce1  jns     short loc_140023D13
0x140023ce3  mov     r10, cs:WPP_GLOBAL_Control
0x140023cea  lea     rcx, WPP_GLOBAL_Control
0x140023cf1  cmp     r10, rcx
0x140023cf4  jz      loc_140023DD6
0x140023cfa  cmp     byte ptr [r10+29h], 3
0x140023cff  jb      loc_140023DD6
0x140023d05  mov     rcx, [r10+18h]
0x140023d09  mov     edx, 10h
0x140023d0e  jmp     loc_140023DC7
0x140023d13  mov     r9b, [rbx+0B1h]; int
0x140023d1a  lea     rax, [rsp+68h+var_38]
0x140023d1f  mov     dword ptr [rsp+68h+NumberOfBytes], 0Bh; NumberOfBytes
0x140023d27  mov     r8b, 3; int
0x140023d2a  mov     dl, 81h; int
0x140023d2c  mov     [rsp+68h+Src], rax; Src
0x140023d31  mov     rcx, rbp; int
0x140023d34  call    GetSetInterfaceControl
0x140023d39  mov     edi, eax
0x140023d3b  test    eax, eax
0x140023d3d  jns     short loc_140023D63
0x140023d3f  mov     rax, cs:WPP_GLOBAL_Control
0x140023d46  lea     rcx, WPP_GLOBAL_Control
0x140023d4d  cmp     rax, rcx
0x140023d50  jz      loc_140023DD6
0x140023d56  cmp     byte ptr [rax+29h], 3
0x140023d5a  jb      short loc_140023DD6
0x140023d5c  mov     edx, 11h
0x140023d61  jmp     short loc_140023DC3
0x140023d63  cmp     [rsp+68h+arg_20], 0
0x140023d6b  movsd   xmm0, [rsp+68h+var_38]
0x140023d71  mov     eax, dword ptr [rsp+68h+var_38+7]
0x140023d75  movsd   qword ptr [rsi], xmm0
0x140023d79  mov     [rsi+7], eax
0x140023d7c  jz      short loc_140023DD6
0x140023d7e  mov     r9b, [rbx+0B1h]; int
0x140023d85  mov     r8b, 4; int
0x140023d88  mov     dword ptr [rsp+68h+NumberOfBytes], 0Bh; NumberOfBytes
0x140023d90  mov     dl, 1; int
0x140023d92  mov     rcx, rbp; int
0x140023d95  mov     [rsp+68h+Src], rsi; Src
0x140023d9a  call    GetSetInterfaceControl
0x140023d9f  mov     edi, eax
0x140023da1  test    eax, eax
0x140023da3  jns     short loc_140023DD6
0x140023da5  mov     rax, cs:WPP_GLOBAL_Control
0x140023dac  lea     rcx, WPP_GLOBAL_Control
0x140023db3  cmp     rax, rcx
0x140023db6  jz      short loc_140023DD6
0x140023db8  cmp     byte ptr [rax+29h], 3
0x140023dbc  jb      short loc_140023DD6
0x140023dbe  mov     edx, 12h
0x140023dc3  mov     rcx, [rax+18h]
0x140023dc7  mov     r9, rbx
0x140023dca  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x140023dd1  call    WPP_SF_q
0x140023dd6  mov     eax, edi
0x140023dd8  mov     rcx, [rsp+68h+var_28]
0x140023ddd  xor     rcx, rsp; StackCookie
0x140023de0  call    __security_check_cookie
0x140023de5  mov     rbx, [rsp+68h+arg_18]
0x140023ded  add     rsp, 50h
0x140023df1  pop     rdi
0x140023df2  pop     rsi
0x140023df3  pop     rbp
0x140023df4  retn
```
