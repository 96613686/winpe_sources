# ClearSecureCommonPinContext

- ea: `0x140039120`
- end: `0x14003921c`
- name: `ClearSecureCommonPinContext`
- size: `252`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a928`
- `0x140039650`

## callees

- `0x14000146c`
- `0x14001e1e4`
- `0x140039120`
- `0x140040a30`

## pseudocode

```c
__int64 __fastcall ClearSecureCommonPinContext(__int64 *a1)
{
  __int64 v1; // rsi
  unsigned int v3; // ebx
  const wchar_t *v4; // r8
  _OWORD v6[3]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v7; // [rsp+70h] [rbp-18h]

  v1 = *a1;
  memset(v6, 0, sizeof(v6));
  v7 = 0;
  LODWORD(v6[0]) = *((_DWORD *)a1 + 6);
  DWORD1(v6[0]) = *(_DWORD *)(a1[52] + 24);
  v3 = USBVideoCallTrustlet(*(_QWORD *)(v1 + 24), 2228256, (unsigned int)v6, 56, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v4 = L"Video Capture";
    if ( *((_DWORD *)a1 + 6) )
      v4 = L"Still";
    WPP_SF_qDS(
      WPP_GLOBAL_Control->AttachedDevice,
      143,
      (unsigned int)WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
      v1,
      v3,
      (__int64)v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140039120  mov     r11, rsp
0x140039123  mov     [r11+10h], rbx
0x140039127  mov     [r11+18h], rsi
0x14003912b  push    rdi
0x14003912c  sub     rsp, 80h
0x140039133  mov     rax, cs:__security_cookie
0x14003913a  xor     rax, rsp
0x14003913d  mov     [rsp+88h+var_10], rax
0x140039142  mov     rsi, [rcx]
0x140039145  lea     r8, [r11-48h]
0x140039149  xorps   xmm0, xmm0
0x14003914c  mov     qword ptr [r11-58h], 0
0x140039154  movups  [rsp+88h+var_48], xmm0
0x140039159  xor     eax, eax
0x14003915b  mov     dword ptr [rsp+88h+var_60], 0
0x140039163  movups  [rsp+88h+var_38], xmm0
0x140039168  mov     rdi, rcx
0x14003916b  mov     r9d, 38h ; '8'
0x140039171  movups  [rsp+88h+var_28], xmm0
0x140039176  mov     [r11-18h], rax
0x14003917a  mov     edx, 220020h
0x14003917f  mov     eax, [rcx+18h]
0x140039182  mov     dword ptr [rsp+88h+var_48], eax
0x140039186  mov     rax, [rcx+1A0h]
0x14003918d  mov     qword ptr [r11-68h], 0
0x140039195  mov     ecx, [rax+18h]
0x140039198  mov     dword ptr [rsp+88h+var_48+4], ecx
0x14003919c  mov     rcx, [rsi+18h]
0x1400391a0  call    USBVideoCallTrustlet
0x1400391a5  mov     ebx, eax
0x1400391a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391ae  lea     rax, WPP_GLOBAL_Control
0x1400391b5  cmp     rcx, rax
0x1400391b8  jz      short loc_1400391F7
0x1400391ba  cmp     byte ptr [rcx+29h], 5
0x1400391be  jb      short loc_1400391F7
0x1400391c0  cmp     dword ptr [rdi+18h], 0
0x1400391c4  lea     rax, aStill; "Still"
0x1400391cb  mov     rcx, [rcx+18h]
0x1400391cf  lea     r8, aVideoCapture; "Video Capture"
0x1400391d6  cmovnz  r8, rax
0x1400391da  mov     edx, 8Fh
0x1400391df  mov     [rsp+88h+var_60], r8
0x1400391e4  mov     r9, rsi
0x1400391e7  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400391ee  mov     [rsp+88h+var_68], ebx
0x1400391f2  call    WPP_SF_qDS
0x1400391f7  mov     eax, ebx
0x1400391f9  mov     rcx, [rsp+88h+var_10]
0x1400391fe  xor     rcx, rsp; StackCookie
0x140039201  call    __security_check_cookie
0x140039206  lea     r11, [rsp+88h+var_8]
0x14003920e  mov     rbx, [r11+18h]
0x140039212  mov     rsi, [r11+20h]
0x140039216  mov     rsp, r11
0x140039219  pop     rdi
0x14003921a  retn
```
