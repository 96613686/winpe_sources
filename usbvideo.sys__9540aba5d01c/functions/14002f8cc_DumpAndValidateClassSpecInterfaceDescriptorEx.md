# DumpAndValidateClassSpecInterfaceDescriptorEx

- ea: `0x14002f8cc`
- end: `0x14002fd51`
- name: `DumpAndValidateClassSpecInterfaceDescriptorEx`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002f3e8`

## callees

- `0x140004bac`
- `0x140020704`
- `0x14002f8cc`
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

## string_xrefs

- `0x14002fd27`: `Invalid descriptor length for classSpecInterfaceDescriptor`
- `0x14002fc91`: `Invalid Extension Unit for VIDEO_SUBCLASS_CONTROL`
- `0x14002fa04`: `Invalid UNCOMPRESSED Format for VIDEO_SUBCLASS_STREAMING`
- `0x14002f9ed`: `Invalid UNCOMPRESSED Frame for VIDEO_SUBCLASS_STREAMING`
- `0x14002f99b`: `Generic Error for classSpecInterfaceDescriptor`

## pseudocode

```c
__int64 __fastcall DumpAndValidateClassSpecInterfaceDescriptorEx(
        unsigned __int8 *a1,
        unsigned __int64 a2,
        int a3,
        unsigned __int16 *a4,
        __int64 a5)
{
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  unsigned __int8 *v11; // rcx
  unsigned int v12; // eax
  int v13; // esi
  int v14; // ebx
  const wchar_t *v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
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
  unsigned int v37; // eax

  if ( (unsigned int)Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline() )
  {
    if ( (unsigned __int64)a1 > a2 || a2 - (unsigned __int64)a1 < *a1 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_85;
      v10 = 722;
LABEL_84:
      WPP_SF_(v9->AttachedDevice, v10, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids);
LABEL_85:
      v15 = L"Invalid descriptor length for classSpecInterfaceDescriptor";
      v14 = -1073741823;
      goto LABEL_86;
    }
  }
  else
  {
    v11 = &a1[*a1];
    if ( v11 <= a1 || (unsigned __int64)v11 > a2 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_85;
      v10 = 723;
      goto LABEL_84;
    }
  }
  if ( (unsigned __int64)(a1 + 2) >= a2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_85;
    v10 = 724;
    goto LABEL_84;
  }
  v12 = a1[2];
  v13 = a3 - 1;
  if ( !v13 )
  {
    v32 = v12 - 1;
    if ( !v32 )
    {
      v14 = DumpAndValidateHeaderUnit(a1, a2, a4);
      if ( v14 >= 0 )
        return (unsigned int)v14;
      v15 = L"Invalid Header Unit for VIDEO_SUBCLASS_CONTROL";
      goto LABEL_86;
    }
    v33 = v32 - 1;
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( v35 )
        {
          v36 = v35 - 1;
          if ( v36 )
          {
            v37 = v36 - 1;
            if ( v37 )
            {
              if ( v37 != 1 )
              {
                v14 = DumpAndValidateGenericDescriptor(a1, a2);
                if ( v14 >= 0 )
                  return (unsigned int)v14;
                v15 = L"Generic Error for VIDEO_SUBCLASS_CONTROL";
                goto LABEL_86;
              }
              v20 = DumpAndValidateH264EncodingUnit(a1, a2);
              v15 = L"Invalid H264 Encoding Unit for VIDEO_SUBCLASS_CONTROL";
            }
            else
            {
              v20 = DumpAndValidateExtensionUnit(a1, a2);
              v15 = L"Invalid Extension Unit for VIDEO_SUBCLASS_CONTROL";
            }
          }
          else
          {
            v20 = DumpAndValidateProcessingUnit(a1, a2, *a4);
            v15 = L"Invalid Processing Unit for VIDEO_SUBCLASS_CONTROL";
          }
        }
        else
        {
          v20 = DumpAndValidateSelectorUnit(a1, a2);
          v15 = L"Invalid Selector Unit for VIDEO_SUBCLASS_CONTROL";
        }
      }
      else
      {
        v20 = DumpAndValidateOutputTerminal(a1, a2);
        v15 = L"Invalid Output Terminal for VIDEO_SUBCLASS_CONTROL";
      }
    }
    else
    {
      v20 = DumpAndValidateInputTerminal(a1, a2);
      v15 = L"Invalid Input Terminal for VIDEO_SUBCLASS_CONTROL";
    }
    goto LABEL_77;
  }
  if ( v13 == 1 )
  {
    if ( v12 > 0xB )
    {
      v24 = v12 - 12;
      if ( !v24 )
      {
        v14 = DumpAndValidateFormatDV(a1, a2);
        if ( v14 >= 0 )
          return (unsigned int)v14;
        v15 = L"Invalid DV Format for VIDEO_SUBCLASS_STREAMING";
        goto LABEL_86;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              v29 = v28 - 1;
              if ( v29 )
              {
                v30 = v29 - 1;
                if ( v30 )
                {
                  v31 = v30 - 1;
                  if ( v31 )
                  {
                    if ( v31 != 1 )
                      goto LABEL_50;
                    v20 = DumpAndValidateFrameH264(a1, a2);
                    v15 = L"Invalid H264 Frame for VIDEO_SUBCLASS_STREAMING";
                  }
                  else
                  {
                    v20 = DumpAndValidateFormatH264(a1, a2);
                    v15 = L"Invalid H264 Format for VIDEO_SUBCLASS_STREAMING";
                  }
                }
                else
                {
                  v20 = DumpAndValidateFormatStream(a1, a2);
                  v15 = L"Invalid Stream Based Format for VIDEO_SUBCLASS_STREAMING";
                }
              }
              else
              {
                v20 = DumpAndValidateFrameFrame(a1, a2);
                v15 = L"Invalid FrameBased Frame for VIDEO_SUBCLASS_STREAMING";
              }
            }
            else
            {
              v20 = DumpAndValidateFormatFrame(a1, a2);
              v15 = L"Invalid FrameBased Format for VIDEO_SUBCLASS_STREAMING";
            }
          }
          else
          {
            v20 = DumpAndValidateFrameVendor(a1, a2);
            v15 = L"Invalid Vendor Frame for VIDEO_SUBCLASS_STREAMING";
          }
        }
        else
        {
          v20 = DumpAndValidateFormatVendor(a1, a2);
          v15 = L"Invalid Vendor Format for VIDEO_SUBCLASS_STREAMING";
        }
      }
      else
      {
        v20 = DumpAndValidateColorFormat(a1, a2);
        v15 = L"Invalid Color Format for VIDEO_SUBCLASS_STREAMING";
      }
    }
    else if ( v12 == 11 )
    {
      v20 = DumpAndValidateFormatMpeg4SL(a1, a2);
      v15 = L"Invalid Mpeg4SL Format for VIDEO_SUBCLASS_STREAMING";
    }
    else if ( v12 > 6 )
    {
      v21 = v12 - 7;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            if ( v23 != 1 )
              goto LABEL_50;
            v20 = DumpAndValidateFormatMpeg2TS(a1, a2);
            v15 = L"Invalid Mpeg2TS Format for VIDEO_SUBCLASS_STREAMING";
          }
          else
          {
            v20 = DumpAndValidateFormatMpeg2PS(a1, a2);
            v15 = L"Invalid Mpeg2PS Format for VIDEO_SUBCLASS_STREAMING";
          }
        }
        else
        {
          v20 = DumpAndValidateFormatMpeg1SS(a1, a2);
          v15 = L"Invalid Mpeg1SS Format for VIDEO_SUBCLASS_STREAMING";
        }
      }
      else
      {
        v20 = DumpAndValidateFrameMjpeg(a1, a2);
        v15 = L"Invalid Mjpeg Frame for VIDEO_SUBCLASS_STREAMING";
      }
    }
    else if ( v12 == 6 )
    {
      v20 = DumpAndValidateFormatMjpeg(a1, a2);
      v15 = L"Invalid Mjpeg Format for VIDEO_SUBCLASS_STREAMING";
    }
    else
    {
      v16 = v12 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              if ( v19 == 1 )
              {
                v20 = DumpAndValidateFrameUncompressed(a1, a2);
                v15 = L"Invalid UNCOMPRESSED Frame for VIDEO_SUBCLASS_STREAMING";
                goto LABEL_77;
              }
LABEL_50:
              v14 = DumpAndValidateGenericDescriptor(a1, a2);
              if ( v14 >= 0 )
                return (unsigned int)v14;
              v15 = L"Generic Error for VIDEO_SUBCLASS_STREAMING";
              goto LABEL_86;
            }
            v20 = DumpAndValidateFormatUncompressed(a1, a2);
            v15 = L"Invalid UNCOMPRESSED Format for VIDEO_SUBCLASS_STREAMING";
          }
          else
          {
            v20 = DumpAndValidateStillImageFrame(a1, a2);
            v15 = L"Invalid Still Image Frame for VIDEO_SUBCLASS_STREAMING";
          }
        }
        else
        {
          v20 = DumpAndValidateOutputHeader(a1, a2, *a4);
          v15 = L"Invalid OutputHeader for VIDEO_SUBCLASS_STREAMING";
        }
      }
      else
      {
        v20 = DumpAndValidateInputHeader(a1, a2);
        v15 = L"Invalid InputHeader for VIDEO_SUBCLASS_STREAMING";
      }
    }
LABEL_77:
    v14 = v20;
    if ( v20 >= 0 )
      return (unsigned int)v14;
    goto LABEL_86;
  }
  v14 = DumpAndValidateGenericDescriptor(a1, a2);
  if ( v14 >= 0 )
    return (unsigned int)v14;
  v15 = L"Generic Error for classSpecInterfaceDescriptor";
LABEL_86:
  if ( a5 )
    ReportInvalidConfigurationTelemetry(a5, (unsigned int)v14, v15);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14002f8cc  push    rbx
0x14002f8ce  push    rsi
0x14002f8cf  push    rdi
0x14002f8d0  push    r14
0x14002f8d2  sub     rsp, 28h
0x14002f8d6  mov     r14, r9
0x14002f8d9  mov     esi, r8d
0x14002f8dc  mov     rdi, rdx
0x14002f8df  mov     rbx, rcx
0x14002f8e2  call    Feature_Servicing_UvcDescriptPointerFix__private_IsEnabledNoReportingNoInline
0x14002f8e7  test    eax, eax
0x14002f8e9  jz      short loc_14002F929
0x14002f8eb  cmp     rbx, rdi
0x14002f8ee  ja      short loc_14002F8FE
0x14002f8f0  movzx   eax, byte ptr [rbx]
0x14002f8f3  mov     r9, rdi
0x14002f8f6  sub     r9, rbx
0x14002f8f9  cmp     r9, rax
0x14002f8fc  jnb     short loc_14002F941
0x14002f8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f905  lea     rax, WPP_GLOBAL_Control
0x14002f90c  cmp     rcx, rax
0x14002f90f  jz      loc_14002FD27
0x14002f915  cmp     byte ptr [rcx+29h], 2
0x14002f919  jb      loc_14002FD27
0x14002f91f  mov     edx, 2D2h
0x14002f924  jmp     loc_14002FD17
0x14002f929  movzx   ecx, byte ptr [rbx]
0x14002f92c  add     rcx, rbx
0x14002f92f  cmp     rcx, rbx
0x14002f932  jbe     loc_14002FCF9
0x14002f938  cmp     rcx, rdi
0x14002f93b  ja      loc_14002FCF9
0x14002f941  lea     rax, [rbx+2]
0x14002f945  cmp     rax, rdi
0x14002f948  jb      short loc_14002F975
0x14002f94a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f951  lea     rax, WPP_GLOBAL_Control
0x14002f958  cmp     rcx, rax
0x14002f95b  jz      loc_14002FD27
0x14002f961  cmp     byte ptr [rcx+29h], 2
0x14002f965  jb      loc_14002FD27
0x14002f96b  mov     edx, 2D4h
0x14002f970  jmp     loc_14002FD17
0x14002f975  movzx   eax, byte ptr [rax]
0x14002f978  sub     esi, 1
0x14002f97b  jz      loc_14002FC36
0x14002f981  cmp     esi, 1
0x14002f984  jz      short loc_14002F9A7
0x14002f986  mov     rdx, rdi
0x14002f989  mov     rcx, rbx
0x14002f98c  call    DumpAndValidateGenericDescriptor
0x14002f991  mov     ebx, eax
0x14002f993  test    eax, eax
0x14002f995  jns     loc_14002FD44
0x14002f99b  lea     r8, aGenericErrorFo_1; "Generic Error for classSpecInterfaceDes"...
0x14002f9a2  jmp     loc_14002FD33
0x14002f9a7  cmp     eax, 0Bh
0x14002f9aa  ja      loc_14002FAFB
0x14002f9b0  jz      loc_14002FAE4
0x14002f9b6  cmp     eax, 6
0x14002f9b9  ja      loc_14002FA70
0x14002f9bf  jz      loc_14002FA59
0x14002f9c5  sub     eax, 1
0x14002f9c8  jz      short loc_14002FA42
0x14002f9ca  sub     eax, 1
0x14002f9cd  jz      short loc_14002FA27
0x14002f9cf  sub     eax, 1
0x14002f9d2  jz      short loc_14002FA10
0x14002f9d4  sub     eax, 1
0x14002f9d7  jz      short loc_14002F9F9
0x14002f9d9  cmp     eax, 1
0x14002f9dc  jnz     loc_14002FB3C
0x14002f9e2  mov     rdx, rdi
0x14002f9e5  mov     rcx, rbx
0x14002f9e8  call    DumpAndValidateFrameUncompressed
0x14002f9ed  lea     r8, aInvalidUncompr_0; "Invalid UNCOMPRESSED Frame for VIDEO_SU"...
0x14002f9f4  jmp     loc_14002FCD4
0x14002f9f9  mov     rdx, rdi
0x14002f9fc  mov     rcx, rbx
0x14002f9ff  call    DumpAndValidateFormatUncompressed
0x14002fa04  lea     r8, aInvalidUncompr; "Invalid UNCOMPRESSED Format for VIDEO_S"...
0x14002fa0b  jmp     loc_14002FCD4
0x14002fa10  mov     rdx, rdi
0x14002fa13  mov     rcx, rbx
0x14002fa16  call    DumpAndValidateStillImageFrame
0x14002fa1b  lea     r8, aInvalidStillIm; "Invalid Still Image Frame for VIDEO_SUB"...
0x14002fa22  jmp     loc_14002FCD4
0x14002fa27  movzx   r8d, word ptr [r14]
0x14002fa2b  mov     rdx, rdi
0x14002fa2e  mov     rcx, rbx
0x14002fa31  call    DumpAndValidateOutputHeader
0x14002fa36  lea     r8, aInvalidOutputh; "Invalid OutputHeader for VIDEO_SUBCLASS"...
0x14002fa3d  jmp     loc_14002FCD4
0x14002fa42  mov     rdx, rdi
0x14002fa45  mov     rcx, rbx
0x14002fa48  call    DumpAndValidateInputHeader
0x14002fa4d  lea     r8, aInvalidInputhe; "Invalid InputHeader for VIDEO_SUBCLASS_"...
0x14002fa54  jmp     loc_14002FCD4
0x14002fa59  mov     rdx, rdi
0x14002fa5c  mov     rcx, rbx
0x14002fa5f  call    DumpAndValidateFormatMjpeg
0x14002fa64  lea     r8, aInvalidMjpegFo; "Invalid Mjpeg Format for VIDEO_SUBCLASS"...
0x14002fa6b  jmp     loc_14002FCD4
0x14002fa70  sub     eax, 7
0x14002fa73  jz      short loc_14002FACD
0x14002fa75  sub     eax, 1
0x14002fa78  jz      short loc_14002FAB6
0x14002fa7a  sub     eax, 1
0x14002fa7d  jz      short loc_14002FA9F
0x14002fa7f  cmp     eax, 1
0x14002fa82  jnz     loc_14002FB3C
0x14002fa88  mov     rdx, rdi
0x14002fa8b  mov     rcx, rbx
0x14002fa8e  call    DumpAndValidateFormatMpeg2TS
0x14002fa93  lea     r8, aInvalidMpeg2ts; "Invalid Mpeg2TS Format for VIDEO_SUBCLA"...
0x14002fa9a  jmp     loc_14002FCD4
0x14002fa9f  mov     rdx, rdi
0x14002faa2  mov     rcx, rbx
0x14002faa5  call    DumpAndValidateFormatMpeg2PS
0x14002faaa  lea     r8, aInvalidMpeg2ps; "Invalid Mpeg2PS Format for VIDEO_SUBCLA"...
0x14002fab1  jmp     loc_14002FCD4
0x14002fab6  mov     rdx, rdi
0x14002fab9  mov     rcx, rbx
0x14002fabc  call    DumpAndValidateFormatMpeg1SS
0x14002fac1  lea     r8, aInvalidMpeg1ss; "Invalid Mpeg1SS Format for VIDEO_SUBCLA"...
0x14002fac8  jmp     loc_14002FCD4
0x14002facd  mov     rdx, rdi
0x14002fad0  mov     rcx, rbx
0x14002fad3  call    DumpAndValidateFrameMjpeg
0x14002fad8  lea     r8, aInvalidMjpegFr; "Invalid Mjpeg Frame for VIDEO_SUBCLASS_"...
0x14002fadf  jmp     loc_14002FCD4
0x14002fae4  mov     rdx, rdi
0x14002fae7  mov     rcx, rbx
0x14002faea  call    DumpAndValidateFormatMpeg4SL
0x14002faef  lea     r8, aInvalidMpeg4sl; "Invalid Mpeg4SL Format for VIDEO_SUBCLA"...
0x14002faf6  jmp     loc_14002FCD4
0x14002fafb  sub     eax, 0Ch
0x14002fafe  jz      loc_14002FC15
0x14002fb04  sub     eax, 1
0x14002fb07  jz      loc_14002FBFE
0x14002fb0d  sub     eax, 1
0x14002fb10  jz      loc_14002FBE7
0x14002fb16  sub     eax, 1
0x14002fb19  jz      loc_14002FBD0
0x14002fb1f  sub     eax, 1
0x14002fb22  jz      loc_14002FBB9
0x14002fb28  sub     eax, 1
0x14002fb2b  jz      short loc_14002FBA2
0x14002fb2d  sub     eax, 1
0x14002fb30  jz      short loc_14002FB8B
0x14002fb32  sub     eax, 1
0x14002fb35  jz      short loc_14002FB74
0x14002fb37  cmp     eax, 1
0x14002fb3a  jz      short loc_14002FB5D
0x14002fb3c  mov     rdx, rdi
0x14002fb3f  mov     rcx, rbx
0x14002fb42  call    DumpAndValidateGenericDescriptor
0x14002fb47  mov     ebx, eax
0x14002fb49  test    eax, eax
0x14002fb4b  jns     loc_14002FD44
0x14002fb51  lea     r8, aGenericErrorFo_0; "Generic Error for VIDEO_SUBCLASS_STREAM"...
0x14002fb58  jmp     loc_14002FD33
0x14002fb5d  mov     rdx, rdi
0x14002fb60  mov     rcx, rbx
0x14002fb63  call    DumpAndValidateFrameH264
0x14002fb68  lea     r8, aInvalidH264Fra; "Invalid H264 Frame for VIDEO_SUBCLASS_S"...
0x14002fb6f  jmp     loc_14002FCD4
0x14002fb74  mov     rdx, rdi
0x14002fb77  mov     rcx, rbx
0x14002fb7a  call    DumpAndValidateFormatH264
0x14002fb7f  lea     r8, aInvalidH264For; "Invalid H264 Format for VIDEO_SUBCLASS_"...
0x14002fb86  jmp     loc_14002FCD4
0x14002fb8b  mov     rdx, rdi
0x14002fb8e  mov     rcx, rbx
0x14002fb91  call    DumpAndValidateFormatStream
0x14002fb96  lea     r8, aInvalidStreamB; "Invalid Stream Based Format for VIDEO_S"...
0x14002fb9d  jmp     loc_14002FCD4
0x14002fba2  mov     rdx, rdi
0x14002fba5  mov     rcx, rbx
0x14002fba8  call    DumpAndValidateFrameFrame
0x14002fbad  lea     r8, aInvalidFrameba_0; "Invalid FrameBased Frame for VIDEO_SUBC"...
0x14002fbb4  jmp     loc_14002FCD4
0x14002fbb9  mov     rdx, rdi
0x14002fbbc  mov     rcx, rbx
0x14002fbbf  call    DumpAndValidateFormatFrame
0x14002fbc4  lea     r8, aInvalidFrameba; "Invalid FrameBased Format for VIDEO_SUB"...
0x14002fbcb  jmp     loc_14002FCD4
0x14002fbd0  mov     rdx, rdi
0x14002fbd3  mov     rcx, rbx
0x14002fbd6  call    DumpAndValidateFrameVendor
0x14002fbdb  lea     r8, aInvalidVendorF; "Invalid Vendor Frame for VIDEO_SUBCLASS"...
0x14002fbe2  jmp     loc_14002FCD4
0x14002fbe7  mov     rdx, rdi
0x14002fbea  mov     rcx, rbx
0x14002fbed  call    DumpAndValidateFormatVendor
0x14002fbf2  lea     r8, aInvalidVendorF_0; "Invalid Vendor Format for VIDEO_SUBCLAS"...
0x14002fbf9  jmp     loc_14002FCD4
0x14002fbfe  mov     rdx, rdi
0x14002fc01  mov     rcx, rbx
0x14002fc04  call    DumpAndValidateColorFormat
0x14002fc09  lea     r8, aInvalidColorFo; "Invalid Color Format for VIDEO_SUBCLASS"...
0x14002fc10  jmp     loc_14002FCD4
0x14002fc15  mov     rdx, rdi
0x14002fc18  mov     rcx, rbx
0x14002fc1b  call    DumpAndValidateFormatDV
0x14002fc20  mov     ebx, eax
0x14002fc22  test    eax, eax
0x14002fc24  jns     loc_14002FD44
0x14002fc2a  lea     r8, aInvalidDvForma; "Invalid DV Format for VIDEO_SUBCLASS_ST"...
0x14002fc31  jmp     loc_14002FD33
0x14002fc36  mov     rdx, rdi
0x14002fc39  mov     rcx, rbx
0x14002fc3c  sub     eax, 1
0x14002fc3f  jz      loc_14002FCE2
0x14002fc45  sub     eax, 1
0x14002fc48  jz      short loc_14002FCC8
0x14002fc4a  sub     eax, 1
0x14002fc4d  jz      short loc_14002FCBA
0x14002fc4f  sub     eax, 1
0x14002fc52  jz      short loc_14002FCAC
0x14002fc54  sub     eax, 1
0x14002fc57  jz      short loc_14002FC9A
0x14002fc59  sub     eax, 1
0x14002fc5c  jz      short loc_14002FC8C
0x14002fc5e  cmp     eax, 1
0x14002fc61  jz      short loc_14002FC7E
0x14002fc63  call    DumpAndValidateGenericDescriptor
0x14002fc68  mov     ebx, eax
0x14002fc6a  test    eax, eax
0x14002fc6c  jns     loc_14002FD44
0x14002fc72  lea     r8, aGenericErrorFo; "Generic Error for VIDEO_SUBCLASS_CONTRO"...
0x14002fc79  jmp     loc_14002FD33
0x14002fc7e  call    DumpAndValidateH264EncodingUnit
0x14002fc83  lea     r8, aInvalidH264Enc; "Invalid H264 Encoding Unit for VIDEO_SU"...
0x14002fc8a  jmp     short loc_14002FCD4
0x14002fc8c  call    DumpAndValidateExtensionUnit
0x14002fc91  lea     r8, aInvalidExtensi; "Invalid Extension Unit for VIDEO_SUBCLA"...
0x14002fc98  jmp     short loc_14002FCD4
0x14002fc9a  movzx   r8d, word ptr [r14]
0x14002fc9e  call    DumpAndValidateProcessingUnit
0x14002fca3  lea     r8, aInvalidProcess; "Invalid Processing Unit for VIDEO_SUBCL"...
0x14002fcaa  jmp     short loc_14002FCD4
0x14002fcac  call    DumpAndValidateSelectorUnit
0x14002fcb1  lea     r8, aInvalidSelecto; "Invalid Selector Unit for VIDEO_SUBCLAS"...
0x14002fcb8  jmp     short loc_14002FCD4
0x14002fcba  call    DumpAndValidateOutputTerminal
0x14002fcbf  lea     r8, aInvalidOutputT; "Invalid Output Terminal for VIDEO_SUBCL"...
0x14002fcc6  jmp     short loc_14002FCD4
0x14002fcc8  call    DumpAndValidateInputTerminal
0x14002fccd  lea     r8, aInvalidInputTe; "Invalid Input Terminal for VIDEO_SUBCLA"...
0x14002fcd4  mov     ebx, eax
0x14002fcd6  xor     eax, eax
0x14002fcd8  test    ebx, ebx
0x14002fcda  cmovns  r8, rax
0x14002fcde  jns     short loc_14002FD44
0x14002fce0  jmp     short loc_14002FD33
0x14002fce2  mov     r8, r14
0x14002fce5  call    DumpAndValidateHeaderUnit
0x14002fcea  mov     ebx, eax
0x14002fcec  test    eax, eax
0x14002fcee  jns     short loc_14002FD44
0x14002fcf0  lea     r8, aInvalidHeaderU; "Invalid Header Unit for VIDEO_SUBCLASS_"...
0x14002fcf7  jmp     short loc_14002FD33
0x14002fcf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd00  lea     rax, WPP_GLOBAL_Control
0x14002fd07  cmp     rcx, rax
0x14002fd0a  jz      short loc_14002FD27
0x14002fd0c  cmp     byte ptr [rcx+29h], 2
0x14002fd10  jb      short loc_14002FD27
0x14002fd12  mov     edx, 2D3h
0x14002fd17  mov     rcx, [rcx+18h]
0x14002fd1b  lea     r8, WPP_0b1b18bec92a3589546aa2def1a0e782_Traceguids
0x14002fd22  call    WPP_SF_
0x14002fd27  lea     r8, aInvalidDescrip; "Invalid descriptor length for classSpec"...
0x14002fd2e  mov     ebx, 0C0000001h
0x14002fd33  mov     rcx, [rsp+48h+arg_20]
0x14002fd38  test    rcx, rcx
0x14002fd3b  jz      short loc_14002FD44
0x14002fd3d  mov     edx, ebx
0x14002fd3f  call    ReportInvalidConfigurationTelemetry
0x14002fd44  mov     eax, ebx
0x14002fd46  add     rsp, 28h
0x14002fd4a  pop     r14
0x14002fd4c  pop     rdi
0x14002fd4d  pop     rsi
0x14002fd4e  pop     rbx
0x14002fd4f  retn
```
