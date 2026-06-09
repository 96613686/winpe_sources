# DumpAndValidateClassSpecInterfaceDescriptor

- ea: `0x14002f590`
- end: `0x14002f8c3`
- name: `DumpAndValidateClassSpecInterfaceDescriptor`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002f2e0`

## callees

- `0x140004bac`
- `0x14002f590`
- `0x14002ffb0`
- `0x140030704`
- `0x140030af0`
- `0x140030d5c`
- `0x140031318`
- `0x140031b64`
- `0x14003204c`
- `0x1400322e4`
- `0x14003257c`
- `0x1400328a8`
- `0x140032af0`
- `0x140032dcc`
- `0x1400333c8`
- `0x14003386c`
- `0x140033ecc`
- `0x140034528`
- `0x140034b88`
- `0x1400351d8`
- `0x14003580c`
- `0x140035998`
- `0x140035cb8`
- `0x1400360a4`
- `0x14003667c`
- `0x140037410`
- `0x140037900`
- `0x140037fdc`
- `0x14003843c`
- `0x14003875c`
- `0x140038ae4`

## pseudocode

```c
__int64 __fastcall DumpAndValidateClassSpecInterfaceDescriptor(
        unsigned __int8 *a1,
        unsigned __int64 a2,
        int a3,
        unsigned __int16 *a4)
{
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned __int8 *v10; // rcx
  unsigned int v11; // eax
  int v12; // esi
  unsigned __int64 v13; // rdx
  unsigned __int8 *v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || a2 - (unsigned __int64)a1 < *a1 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v9 = 719;
      goto LABEL_76;
    }
  }
  else
  {
    v10 = &a1[*a1];
    if ( v10 <= a1 || (unsigned __int64)v10 > a2 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return 3221225473LL;
      v9 = 720;
      goto LABEL_76;
    }
  }
  if ( (unsigned __int64)(a1 + 2) < a2 )
  {
    v11 = a1[2];
    v12 = a3 - 1;
    if ( v12 )
    {
      if ( v12 == 1 )
      {
        if ( v11 > 0xB )
        {
          v23 = v11 - 12;
          if ( !v23 )
            return DumpAndValidateFormatDV(a1, a2);
          v24 = v23 - 1;
          if ( !v24 )
            return DumpAndValidateColorFormat(a1, a2);
          v25 = v24 - 1;
          if ( !v25 )
            return DumpAndValidateFormatVendor(a1, a2);
          v26 = v25 - 1;
          if ( !v26 )
            return DumpAndValidateFrameVendor(a1, a2);
          v27 = v26 - 1;
          if ( !v27 )
            return DumpAndValidateFormatFrame(a1, a2);
          v28 = v27 - 1;
          if ( !v28 )
            return DumpAndValidateFrameFrame(a1, a2);
          v29 = v28 - 1;
          if ( !v29 )
            return DumpAndValidateFormatStream(a1, a2);
          v30 = v29 - 1;
          if ( !v30 )
            return DumpAndValidateFormatH264(a1, a2);
          if ( v30 == 1 )
            return DumpAndValidateFrameH264(a1, a2);
        }
        else
        {
          if ( v11 == 11 )
            return DumpAndValidateFormatMpeg4SL(a1, a2);
          if ( v11 > 6 )
          {
            v20 = v11 - 7;
            if ( !v20 )
              return DumpAndValidateFrameMjpeg(a1, a2);
            v21 = v20 - 1;
            if ( !v21 )
              return DumpAndValidateFormatMpeg1SS(a1, a2);
            v22 = v21 - 1;
            if ( !v22 )
              return DumpAndValidateFormatMpeg2PS(a1, a2);
            if ( v22 == 1 )
              return DumpAndValidateFormatMpeg2TS(a1, a2);
          }
          else
          {
            if ( v11 == 6 )
              return DumpAndValidateFormatMjpeg(a1, a2);
            v15 = v11 - 1;
            if ( !v15 )
              return DumpAndValidateInputHeader(a1, a2);
            v16 = v15 - 1;
            if ( !v16 )
              return DumpAndValidateOutputHeader(a1, a2, *a4);
            v17 = v16 - 1;
            if ( !v17 )
              return DumpAndValidateStillImageFrame(a1, a2);
            v18 = v17 - 1;
            if ( !v18 )
              return DumpAndValidateFormatUncompressed(a1, a2);
            if ( v18 == 1 )
              return DumpAndValidateFrameUncompressed(a1, a2);
          }
        }
      }
      v13 = a2;
      v14 = a1;
    }
    else
    {
      v13 = a2;
      v14 = a1;
      v31 = v11 - 1;
      if ( !v31 )
        return DumpAndValidateHeaderUnit(a1, a2, a4);
      v32 = v31 - 1;
      if ( !v32 )
        return DumpAndValidateInputTerminal(a1, a2);
      v33 = v32 - 1;
      if ( !v33 )
        return DumpAndValidateOutputTerminal(a1, a2);
      v34 = v33 - 1;
      if ( !v34 )
        return DumpAndValidateSelectorUnit(a1, a2);
      v35 = v34 - 1;
      if ( !v35 )
        return DumpAndValidateProcessingUnit(a1, a2, *a4);
      v36 = v35 - 1;
      if ( !v36 )
        return DumpAndValidateExtensionUnit(a1, a2);
      if ( v36 == 1 )
        return DumpAndValidateH264EncodingUnit(a1, a2);
    }
    return DumpAndValidateGenericDescriptor(v14, v13);
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v9 = 721;
LABEL_76:
    WPP_SF_(v8->AttachedDevice, v9, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14002f590  push    rbx
0x14002f592  push    rsi
0x14002f593  push    rdi
0x14002f594  push    r14
0x14002f596  sub     rsp, 28h
0x14002f59a  mov     r14, r9
0x14002f59d  mov     esi, r8d
0x14002f5a0  mov     rdi, rdx
0x14002f5a3  mov     rbx, rcx
0x14002f5a6  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x14002f5ab  test    eax, eax
0x14002f5ad  jz      short loc_14002F5ED
0x14002f5af  cmp     rbx, rdi
0x14002f5b2  ja      short loc_14002F5C2
0x14002f5b4  movzx   eax, byte ptr [rbx]
0x14002f5b7  mov     r10, rdi
0x14002f5ba  sub     r10, rbx
0x14002f5bd  cmp     r10, rax
0x14002f5c0  jnb     short loc_14002F605
0x14002f5c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f5c9  lea     rax, WPP_GLOBAL_Control
0x14002f5d0  cmp     rcx, rax
0x14002f5d3  jz      loc_14002F8B3
0x14002f5d9  cmp     byte ptr [rcx+29h], 2
0x14002f5dd  jb      loc_14002F8B3
0x14002f5e3  mov     edx, 2CFh
0x14002f5e8  jmp     loc_14002F8A3
0x14002f5ed  movzx   ecx, byte ptr [rbx]
0x14002f5f0  add     rcx, rbx
0x14002f5f3  cmp     rcx, rbx
0x14002f5f6  jbe     loc_14002F885
0x14002f5fc  cmp     rcx, rdi
0x14002f5ff  ja      loc_14002F885
0x14002f605  lea     rax, [rbx+2]
0x14002f609  cmp     rax, rdi
0x14002f60c  jb      short loc_14002F639
0x14002f60e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f615  lea     rax, WPP_GLOBAL_Control
0x14002f61c  cmp     rcx, rax
0x14002f61f  jz      loc_14002F8B3
0x14002f625  cmp     byte ptr [rcx+29h], 2
0x14002f629  jb      loc_14002F8B3
0x14002f62f  mov     edx, 2D1h
0x14002f634  jmp     loc_14002F8A3
0x14002f639  movzx   eax, byte ptr [rax]
0x14002f63c  sub     esi, 1
0x14002f63f  jz      loc_14002F81D
0x14002f645  cmp     esi, 1
0x14002f648  jz      short loc_14002F655
0x14002f64a  mov     rdx, rdi
0x14002f64d  mov     rcx, rbx
0x14002f650  jmp     loc_14002F846
0x14002f655  cmp     eax, 0Bh
0x14002f658  ja      loc_14002F750
0x14002f65e  jz      loc_14002F740
0x14002f664  cmp     eax, 6
0x14002f667  ja      short loc_14002F6E8
0x14002f669  jz      short loc_14002F6D8
0x14002f66b  sub     eax, 1
0x14002f66e  jz      short loc_14002F6C8
0x14002f670  sub     eax, 1
0x14002f673  jz      short loc_14002F6B4
0x14002f675  sub     eax, 1
0x14002f678  jz      short loc_14002F6A4
0x14002f67a  sub     eax, 1
0x14002f67d  jz      short loc_14002F694
0x14002f67f  cmp     eax, 1
0x14002f682  jnz     short loc_14002F64A
0x14002f684  mov     rdx, rdi
0x14002f687  mov     rcx, rbx
0x14002f68a  call    DumpAndValidateFrameUncompressed
0x14002f68f  jmp     loc_14002F8B8
0x14002f694  mov     rdx, rdi
0x14002f697  mov     rcx, rbx
0x14002f69a  call    DumpAndValidateFormatUncompressed
0x14002f69f  jmp     loc_14002F8B8
0x14002f6a4  mov     rdx, rdi
0x14002f6a7  mov     rcx, rbx
0x14002f6aa  call    DumpAndValidateStillImageFrame
0x14002f6af  jmp     loc_14002F8B8
0x14002f6b4  movzx   r8d, word ptr [r14]
0x14002f6b8  mov     rdx, rdi
0x14002f6bb  mov     rcx, rbx
0x14002f6be  call    DumpAndValidateOutputHeader
0x14002f6c3  jmp     loc_14002F8B8
0x14002f6c8  mov     rdx, rdi
0x14002f6cb  mov     rcx, rbx
0x14002f6ce  call    DumpAndValidateInputHeader
0x14002f6d3  jmp     loc_14002F8B8
0x14002f6d8  mov     rdx, rdi
0x14002f6db  mov     rcx, rbx
0x14002f6de  call    DumpAndValidateFormatMjpeg
0x14002f6e3  jmp     loc_14002F8B8
0x14002f6e8  sub     eax, 7
0x14002f6eb  jz      short loc_14002F730
0x14002f6ed  sub     eax, 1
0x14002f6f0  jz      short loc_14002F720
0x14002f6f2  sub     eax, 1
0x14002f6f5  jz      short loc_14002F710
0x14002f6f7  cmp     eax, 1
0x14002f6fa  jnz     loc_14002F64A
0x14002f700  mov     rdx, rdi
0x14002f703  mov     rcx, rbx
0x14002f706  call    DumpAndValidateFormatMpeg2TS
0x14002f70b  jmp     loc_14002F8B8
0x14002f710  mov     rdx, rdi
0x14002f713  mov     rcx, rbx
0x14002f716  call    DumpAndValidateFormatMpeg2PS
0x14002f71b  jmp     loc_14002F8B8
0x14002f720  mov     rdx, rdi
0x14002f723  mov     rcx, rbx
0x14002f726  call    DumpAndValidateFormatMpeg1SS
0x14002f72b  jmp     loc_14002F8B8
0x14002f730  mov     rdx, rdi
0x14002f733  mov     rcx, rbx
0x14002f736  call    DumpAndValidateFrameMjpeg
0x14002f73b  jmp     loc_14002F8B8
0x14002f740  mov     rdx, rdi
0x14002f743  mov     rcx, rbx
0x14002f746  call    DumpAndValidateFormatMpeg4SL
0x14002f74b  jmp     loc_14002F8B8
0x14002f750  sub     eax, 0Ch
0x14002f753  jz      loc_14002F80D
0x14002f759  sub     eax, 1
0x14002f75c  jz      loc_14002F7FD
0x14002f762  sub     eax, 1
0x14002f765  jz      loc_14002F7ED
0x14002f76b  sub     eax, 1
0x14002f76e  jz      short loc_14002F7DD
0x14002f770  sub     eax, 1
0x14002f773  jz      short loc_14002F7CD
0x14002f775  sub     eax, 1
0x14002f778  jz      short loc_14002F7BD
0x14002f77a  sub     eax, 1
0x14002f77d  jz      short loc_14002F7AD
0x14002f77f  sub     eax, 1
0x14002f782  jz      short loc_14002F79D
0x14002f784  cmp     eax, 1
0x14002f787  jnz     loc_14002F64A
0x14002f78d  mov     rdx, rdi
0x14002f790  mov     rcx, rbx
0x14002f793  call    DumpAndValidateFrameH264
0x14002f798  jmp     loc_14002F8B8
0x14002f79d  mov     rdx, rdi
0x14002f7a0  mov     rcx, rbx
0x14002f7a3  call    DumpAndValidateFormatH264
0x14002f7a8  jmp     loc_14002F8B8
0x14002f7ad  mov     rdx, rdi
0x14002f7b0  mov     rcx, rbx
0x14002f7b3  call    DumpAndValidateFormatStream
0x14002f7b8  jmp     loc_14002F8B8
0x14002f7bd  mov     rdx, rdi
0x14002f7c0  mov     rcx, rbx
0x14002f7c3  call    DumpAndValidateFrameFrame
0x14002f7c8  jmp     loc_14002F8B8
0x14002f7cd  mov     rdx, rdi
0x14002f7d0  mov     rcx, rbx
0x14002f7d3  call    DumpAndValidateFormatFrame
0x14002f7d8  jmp     loc_14002F8B8
0x14002f7dd  mov     rdx, rdi
0x14002f7e0  mov     rcx, rbx
0x14002f7e3  call    DumpAndValidateFrameVendor
0x14002f7e8  jmp     loc_14002F8B8
0x14002f7ed  mov     rdx, rdi
0x14002f7f0  mov     rcx, rbx
0x14002f7f3  call    DumpAndValidateFormatVendor
0x14002f7f8  jmp     loc_14002F8B8
0x14002f7fd  mov     rdx, rdi
0x14002f800  mov     rcx, rbx
0x14002f803  call    DumpAndValidateColorFormat
0x14002f808  jmp     loc_14002F8B8
0x14002f80d  mov     rdx, rdi
0x14002f810  mov     rcx, rbx
0x14002f813  call    DumpAndValidateFormatDV
0x14002f818  jmp     loc_14002F8B8
0x14002f81d  mov     rdx, rdi
0x14002f820  mov     rcx, rbx
0x14002f823  sub     eax, 1
0x14002f826  jz      short loc_14002F87B
0x14002f828  sub     eax, 1
0x14002f82b  jz      short loc_14002F874
0x14002f82d  sub     eax, 1
0x14002f830  jz      short loc_14002F86D
0x14002f832  sub     eax, 1
0x14002f835  jz      short loc_14002F866
0x14002f837  sub     eax, 1
0x14002f83a  jz      short loc_14002F85B
0x14002f83c  sub     eax, 1
0x14002f83f  jz      short loc_14002F854
0x14002f841  cmp     eax, 1
0x14002f844  jz      short loc_14002F84D
0x14002f846  call    DumpAndValidateGenericDescriptor
0x14002f84b  jmp     short loc_14002F8B8
0x14002f84d  call    DumpAndValidateH264EncodingUnit
0x14002f852  jmp     short loc_14002F8B8
0x14002f854  call    DumpAndValidateExtensionUnit
0x14002f859  jmp     short loc_14002F8B8
0x14002f85b  movzx   r8d, word ptr [r14]
0x14002f85f  call    DumpAndValidateProcessingUnit
0x14002f864  jmp     short loc_14002F8B8
0x14002f866  call    DumpAndValidateSelectorUnit
0x14002f86b  jmp     short loc_14002F8B8
0x14002f86d  call    DumpAndValidateOutputTerminal
0x14002f872  jmp     short loc_14002F8B8
0x14002f874  call    DumpAndValidateInputTerminal
0x14002f879  jmp     short loc_14002F8B8
0x14002f87b  mov     r8, r14
0x14002f87e  call    DumpAndValidateHeaderUnit
0x14002f883  jmp     short loc_14002F8B8
0x14002f885  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f88c  lea     rax, WPP_GLOBAL_Control
0x14002f893  cmp     rcx, rax
0x14002f896  jz      short loc_14002F8B3
0x14002f898  cmp     byte ptr [rcx+29h], 2
0x14002f89c  jb      short loc_14002F8B3
0x14002f89e  mov     edx, 2D0h
0x14002f8a3  mov     rcx, [rcx+18h]
0x14002f8a7  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002f8ae  call    WPP_SF_
0x14002f8b3  mov     eax, 0C0000001h
0x14002f8b8  add     rsp, 28h
0x14002f8bc  pop     r14
0x14002f8be  pop     rdi
0x14002f8bf  pop     rsi
0x14002f8c0  pop     rbx
0x14002f8c1  retn
```
