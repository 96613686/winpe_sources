# CUsbBusFilter::CheckForHIDKeyboardAndMouse(_DEVICE_OBJECT *)

- ea: `0x140009eb4`
- end: `0x14000a0f5`
- name: `?CheckForHIDKeyboardAndMouse@CUsbBusFilter@@AEAAEPEAU_DEVICE_OBJECT@@@Z`
- size: `577`
- prototype: `unsigned __int8(CUsbBusFilter *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140001e80`

## callees

- `0x140004f48`
- `0x140005084`
- `0x140009134`
- `0x140009eb4`
- `0x14000a0fc`
- `0x14000a9f0`
- `0x14000ab00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0cd`
- `HIDPARSE!HidP_GetCollectionDescription` at `0x140009fff`
- `HIDPARSE!HidP_GetCollectionDescription` at `0x140009fff`
- `HIDPARSE!HidP_FreeCollectionDescription` at `0x14000a081`
- `HIDPARSE!HidP_FreeCollectionDescription` at `0x14000a081`

## pseudocode

```c
char __fastcall CUsbBusFilter::CheckForHIDKeyboardAndMouse(CUsbBusFilter *this, struct _DEVICE_OBJECT *a2)
{
  PHIDP_REPORT_DESCRIPTOR v3; // rbx
  char v4; // si
  int v5; // r9d
  CUsbBusFilter *v6; // rcx
  NTSTATUS HIDRawReportDescriptor; // r9d
  PDEVICE_OBJECT v8; // rcx
  unsigned __int16 v9; // dx
  ULONG v10; // ebx
  ULONG v11; // edx
  __int64 i; // rdx
  unsigned __int64 v14; // [rsp+28h] [rbp-D8h]
  PHIDP_REPORT_DESCRIPTOR ReportDesc; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  struct _IO_STACK_LOCATION v17; // [rsp+50h] [rbp-B0h] BYREF
  _HIDP_DEVICE_DESC DeviceDescription; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v19[2]; // [rsp+E0h] [rbp-20h] BYREF

  memset(v19, 0, 9);
  v3 = 0;
  v16 = 0;
  ReportDesc = 0;
  memset(&DeviceDescription, 0, sizeof(DeviceDescription));
  v4 = 0;
  memset(&v17, 0, sizeof(v17));
  v17.MajorFunction = 15;
  v17.Parameters.Read.ByteOffset.LowPart = 720899;
  v17.Parameters.Read.Length = 9;
  v17.Parameters.CreatePipe.Parameters = 0;
  HIDRawReportDescriptor = IopSynchronousCall(a2, &v17, v19, v5, 0, v14, &v16);
  if ( HIDRawReportDescriptor < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 10;
LABEL_28:
      WPP_SF_d(
        (__int64)v8->AttachedDevice,
        v9,
        (__int64)WPP_e71faac6a535323b68e48f556bf845d8_Traceguids,
        HIDRawReportDescriptor);
      goto LABEL_29;
    }
    goto LABEL_29;
  }
  if ( v16 != 9 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids);
    goto LABEL_29;
  }
  if ( BYTE6(v19[0]) != 34 )
  {
    HIDRawReportDescriptor = -1073741668;
    goto LABEL_25;
  }
  v10 = *(unsigned __int16 *)((char *)v19 + 7);
  HIDRawReportDescriptor = CUsbBusFilter::GetHIDRawReportDescriptor(
                             v6,
                             a2,
                             *(unsigned __int16 *)((char *)v19 + 7),
                             &ReportDesc);
  if ( HIDRawReportDescriptor < 0 )
  {
    v3 = ReportDesc;
LABEL_25:
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 12;
      goto LABEL_28;
    }
    goto LABEL_29;
  }
  v11 = v10;
  v3 = ReportDesc;
  HIDRawReportDescriptor = HidP_GetCollectionDescription(ReportDesc, v11, (POOL_TYPE)512, &DeviceDescription);
  if ( HIDRawReportDescriptor >= 0 )
  {
    for ( i = 0; (unsigned int)i < DeviceDescription.CollectionDescLength; i = (unsigned int)(i + 1) )
    {
      if ( DeviceDescription.CollectionDesc[i].UsagePage == 1
        && (DeviceDescription.CollectionDesc[i].Usage == 1
         || DeviceDescription.CollectionDesc[i].Usage == 2
         || (unsigned int)DeviceDescription.CollectionDesc[i].Usage - 6 <= 1) )
      {
        v4 = 1;
      }
    }
    HidP_FreeCollectionDescription(&DeviceDescription);
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 13;
      goto LABEL_28;
    }
  }
LABEL_29:
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return v4;
}

```

## disassembly

```asm
0x140009eb4  push    rbp
0x140009eb6  push    rbx
0x140009eb7  push    rsi
0x140009eb8  push    rdi
0x140009eb9  lea     rbp, [rsp-8]
0x140009ebe  sub     rsp, 108h
0x140009ec5  mov     rax, cs:__security_cookie
0x140009ecc  xor     rax, rsp
0x140009ecf  mov     [rbp+20h+var_30], rax
0x140009ed3  xor     eax, eax
0x140009ed5  lea     rcx, [rbp+20h+DeviceDescription]; void *
0x140009ed9  mov     rdi, rdx
0x140009edc  mov     [rbp+20h+var_40], rax
0x140009ee0  xor     ebx, ebx
0x140009ee2  mov     [rbp+20h+var_38], al
0x140009ee5  xor     edx, edx; Val
0x140009ee7  mov     [rsp+120h+var_D8], rax
0x140009eec  lea     r8d, [rax+40h]; Size
0x140009ef0  mov     [rsp+120h+ReportDesc], rbx
0x140009ef5  call    memset
0x140009efa  xor     edx, edx; Val
0x140009efc  lea     r8d, [rbx+48h]; Size
0x140009f00  lea     rcx, [rsp+120h+var_D0]; void *
0x140009f05  xor     sil, sil
0x140009f08  call    memset
0x140009f0d  lea     rax, [rsp+120h+var_D8]
0x140009f12  mov     [rsp+120h+var_D0.MajorFunction], 0Fh
0x140009f17  mov     [rsp+120h+var_F0], rax; unsigned __int64 *
0x140009f1c  lea     r8, [rbp+20h+var_40]; void *
0x140009f20  lea     rdx, [rsp+120h+var_D0]; struct _IO_STACK_LOCATION *
0x140009f25  mov     [rsp+120h+var_100], bl; char
0x140009f29  mov     rcx, rdi; struct _DEVICE_OBJECT *
0x140009f2c  mov     dword ptr [rsp+120h+var_D0.Parameters+10h], 0B0003h
0x140009f34  mov     dword ptr [rsp+120h+var_D0.Parameters], 9
0x140009f3c  mov     qword ptr [rsp+120h+var_D0.Parameters+18h], rbx
0x140009f41  call    ?IopSynchronousCall@@YAJPEAU_DEVICE_OBJECT@@PEAU_IO_STACK_LOCATION@@PEAXJE_KPEA_K@Z; IopSynchronousCall(_DEVICE_OBJECT *,_IO_STACK_LOCATION *,void *,long,uchar,unsigned __int64,unsigned __int64 *)
0x140009f46  mov     r9d, eax
0x140009f49  test    eax, eax
0x140009f4b  jns     short loc_140009F76
0x140009f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f54  lea     rax, WPP_GLOBAL_Control
0x140009f5b  cmp     rcx, rax
0x140009f5e  jz      loc_14000A0C3
0x140009f64  cmp     byte ptr [rcx+29h], 2
0x140009f68  jb      loc_14000A0C3
0x140009f6e  lea     edx, [rbx+0Ah]
0x140009f71  jmp     loc_14000A0B3
0x140009f76  mov     r9, [rsp+120h+var_D8]
0x140009f7b  cmp     r9, 9
0x140009f7f  jz      short loc_140009FBC
0x140009f81  mov     rcx, cs:WPP_GLOBAL_Control
0x140009f88  lea     rax, WPP_GLOBAL_Control
0x140009f8f  cmp     rcx, rax
0x140009f92  jz      loc_14000A0C3
0x140009f98  cmp     byte ptr [rcx+29h], 2
0x140009f9c  jb      loc_14000A0C3
0x140009fa2  mov     rcx, [rcx+18h]
0x140009fa6  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x140009fad  mov     edx, 0Bh
0x140009fb2  call    WPP_SF_i
0x140009fb7  jmp     loc_14000A0C3
0x140009fbc  cmp     byte ptr [rbp+20h+var_40+6], 22h ; '"'
0x140009fc0  jnz     loc_14000A08F
0x140009fc6  movzx   ebx, word ptr [rbp+20h+var_40+7]
0x140009fca  lea     r9, [rsp+120h+ReportDesc]; unsigned __int8 **
0x140009fcf  mov     r8d, ebx; unsigned int
0x140009fd2  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x140009fd5  call    ?GetHIDRawReportDescriptor@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@KPEAPEAE@Z; CUsbBusFilter::GetHIDRawReportDescriptor(_DEVICE_OBJECT *,ulong,uchar * *)
0x140009fda  mov     r9d, eax
0x140009fdd  test    eax, eax
0x140009fdf  jns     short loc_140009FEB
0x140009fe1  mov     rbx, [rsp+120h+ReportDesc]
0x140009fe6  jmp     loc_14000A095
0x140009feb  mov     edx, ebx; DescLength
0x140009fed  lea     r9, [rbp+20h+DeviceDescription]; DeviceDescription
0x140009ff1  mov     rbx, [rsp+120h+ReportDesc]
0x140009ff6  mov     r8d, 200h; PoolType
0x140009ffc  mov     rcx, rbx; ReportDesc
0x140009fff  call    cs:__imp_HidP_GetCollectionDescription
0x14000a006  nop     dword ptr [rax+rax+00h]
0x14000a00b  mov     r9d, eax
0x14000a00e  test    eax, eax
0x14000a010  jns     short loc_14000A03A
0x14000a012  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a019  lea     rax, WPP_GLOBAL_Control
0x14000a020  cmp     rcx, rax
0x14000a023  jz      loc_14000A0C3
0x14000a029  cmp     byte ptr [rcx+29h], 2
0x14000a02d  jb      loc_14000A0C3
0x14000a033  mov     edx, 0Dh
0x14000a038  jmp     short loc_14000A0B3
0x14000a03a  mov     r8d, [rbp+20h+DeviceDescription.CollectionDescLength]
0x14000a03e  xor     edx, edx
0x14000a040  test    r8d, r8d
0x14000a043  jz      short loc_14000A07D
0x14000a045  mov     r9, [rbp+20h+DeviceDescription.CollectionDesc]
0x14000a049  lea     r10d, [rdx+1]
0x14000a04d  lea     rcx, [rdx+rdx*4]
0x14000a051  cmp     [r9+rcx*8], r10w
0x14000a056  jnz     short loc_14000A075
0x14000a058  movzx   ecx, word ptr [r9+rcx*8+2]
0x14000a05e  sub     ecx, r10d
0x14000a061  jz      short loc_14000A072
0x14000a063  sub     ecx, r10d
0x14000a066  jz      short loc_14000A072
0x14000a068  sub     ecx, 4
0x14000a06b  jz      short loc_14000A072
0x14000a06d  cmp     ecx, r10d
0x14000a070  jnz     short loc_14000A075
0x14000a072  mov     sil, r10b
0x14000a075  add     edx, r10d
0x14000a078  cmp     edx, r8d
0x14000a07b  jb      short loc_14000A04D
0x14000a07d  lea     rcx, [rbp+20h+DeviceDescription]; DeviceDescription
0x14000a081  call    cs:__imp_HidP_FreeCollectionDescription
0x14000a088  nop     dword ptr [rax+rax+00h]
0x14000a08d  jmp     short loc_14000A0C3
0x14000a08f  mov     r9d, 0C000009Ch
0x14000a095  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a09c  lea     rax, WPP_GLOBAL_Control
0x14000a0a3  cmp     rcx, rax
0x14000a0a6  jz      short loc_14000A0C3
0x14000a0a8  cmp     byte ptr [rcx+29h], 2
0x14000a0ac  jb      short loc_14000A0C3
0x14000a0ae  mov     edx, 0Ch
0x14000a0b3  mov     rcx, [rcx+18h]
0x14000a0b7  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x14000a0be  call    WPP_SF_d
0x14000a0c3  test    rbx, rbx
0x14000a0c6  jz      short loc_14000A0D9
0x14000a0c8  xor     edx, edx; Tag
0x14000a0ca  mov     rcx, rbx; P
0x14000a0cd  call    cs:__imp_ExFreePoolWithTag
0x14000a0d4  nop     dword ptr [rax+rax+00h]
0x14000a0d9  mov     al, sil
0x14000a0dc  mov     rcx, [rbp+20h+var_30]
0x14000a0e0  xor     rcx, rsp; StackCookie
0x14000a0e3  call    __security_check_cookie
0x14000a0e8  add     rsp, 108h
0x14000a0ef  pop     rdi
0x14000a0f0  pop     rsi
0x14000a0f1  pop     rbx
0x14000a0f2  pop     rbp
0x14000a0f3  retn
```
