# CMPEG2TSFormatPlugin::GetUsbDataRangeForFormat(KSPIN_DATAFLOW,KSDATAFORMAT *,KSDATAFORMAT * *,ulong)

- ea: `0x14003eae0`
- end: `0x14003ebc2`
- name: `?GetUsbDataRangeForFormat@CMPEG2TSFormatPlugin@@UEAAPEAU_USBVIDEO_DATARANGE@@W4KSPIN_DATAFLOW@@PEATKSDATAFORMAT@@PEAPEAT4@K@Z`
- size: `226`
- prototype: `struct _USBVIDEO_DATARANGE *__fastcall(CMPEG2TSFormatPlugin *__hidden this, enum KSPIN_DATAFLOW, union KSDATAFORMAT *, union KSDATAFORMAT **, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14003eae0`

## pseudocode

```c
LONGLONG *__fastcall CMPEG2TSFormatPlugin::GetUsbDataRangeForFormat(
        CMPEG2TSFormatPlugin *this,
        enum KSPIN_DATAFLOW a2,
        union KSDATAFORMAT *a3,
        union KSDATAFORMAT **a4,
        unsigned int a5)
{
  __int64 v5; // r11
  __int64 v6; // rbx
  __int64 v7; // r10
  __int64 v9; // r8
  __int64 v11; // rdx
  __int64 i; // rsi
  union KSDATAFORMAT *v14; // rcx
  LONGLONG v15; // rax
  bool v16; // cf
  LONGLONG v18; // rax

  v5 = *(_QWORD *)&GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1;
  v6 = 0;
  v7 = *(_QWORD *)&GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1;
  v9 = *(_QWORD *)GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4;
  v11 = *(_QWORD *)GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4;
  for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
  {
    v14 = a4[i];
    v15 = *(&a3->Alignment + 4) - v5;
    if ( !v15 )
      v15 = *(&a3->Alignment + 5) - v9;
    if ( v15 )
    {
      v18 = *(&a3->Alignment + 4) - v7;
      if ( !v18 )
        v18 = *(&a3->Alignment + 5) - v11;
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids);
          v9 = *(_QWORD *)GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4;
          v5 = *(_QWORD *)&GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1;
          v11 = *(_QWORD *)GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4;
          v7 = *(_QWORD *)&GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1;
        }
        continue;
      }
      v16 = v14->FormatSize < 0x40;
    }
    else
    {
      v16 = v14->FormatSize < 0x50;
    }
    if ( v16 )
      return (LONGLONG *)v6;
    if ( a2 != KSPIN_DATAFLOW_OUT || a3->SampleSize == v14->SampleSize )
      return &v14[-2].Alignment + 4;
  }
  return (LONGLONG *)v6;
}

```

## disassembly

```asm
0x14003eae0  push    rbx
0x14003eae2  push    rbp
0x14003eae3  push    rsi
0x14003eae4  push    rdi
0x14003eae5  push    r14
0x14003eae7  sub     rsp, 20h
0x14003eaeb  mov     r11, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1
0x14003eaf2  xor     ebx, ebx
0x14003eaf4  mov     r10, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1
0x14003eafb  mov     rdi, r8
0x14003eafe  mov     r8, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4
0x14003eb05  mov     ebp, edx
0x14003eb07  mov     rdx, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4
0x14003eb0e  xor     esi, esi
0x14003eb10  mov     r14, r9
0x14003eb13  cmp     esi, [rsp+48h+arg_20]
0x14003eb17  jnb     short loc_14003EB48
0x14003eb19  mov     rax, [rdi+20h]
0x14003eb1d  mov     rcx, [r14+rsi*8]
0x14003eb21  sub     rax, r11
0x14003eb24  jnz     short loc_14003EB2D
0x14003eb26  mov     rax, [rdi+28h]
0x14003eb2a  sub     rax, r8
0x14003eb2d  test    rax, rax
0x14003eb30  jnz     short loc_14003EB57
0x14003eb32  cmp     dword ptr [rcx], 50h ; 'P'
0x14003eb35  jb      short loc_14003EB48
0x14003eb37  cmp     ebp, 2
0x14003eb3a  jnz     short loc_14003EB44
0x14003eb3c  mov     eax, [rcx+8]
0x14003eb3f  cmp     [rdi+8], eax
0x14003eb42  jnz     short loc_14003EBBB
0x14003eb44  lea     rbx, [rcx-60h]
0x14003eb48  mov     rax, rbx
0x14003eb4b  add     rsp, 20h
0x14003eb4f  pop     r14
0x14003eb51  pop     rdi
0x14003eb52  pop     rsi
0x14003eb53  pop     rbp
0x14003eb54  pop     rbx
0x14003eb55  retn
0x14003eb57  mov     rax, [rdi+20h]
0x14003eb5b  sub     rax, r10
0x14003eb5e  jnz     short loc_14003EB67
0x14003eb60  mov     rax, [rdi+28h]
0x14003eb64  sub     rax, rdx
0x14003eb67  test    rax, rax
0x14003eb6a  jnz     short loc_14003EB71
0x14003eb6c  cmp     dword ptr [rcx], 40h ; '@'
0x14003eb6f  jmp     short loc_14003EB35
0x14003eb71  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eb78  lea     rax, WPP_GLOBAL_Control
0x14003eb7f  cmp     rcx, rax
0x14003eb82  jz      short loc_14003EBBB
0x14003eb84  cmp     byte ptr [rcx+29h], 3
0x14003eb88  jb      short loc_14003EBBB
0x14003eb8a  mov     rcx, [rcx+18h]
0x14003eb8e  lea     r8, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids
0x14003eb95  mov     edx, 0Ch
0x14003eb9a  call    WPP_SF_
0x14003eb9f  mov     r8, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data4
0x14003eba6  mov     r11, qword ptr cs:_GUID_138aa9a4_1ee2_4c5b_988e_19abfdbc8a11.Data1
0x14003ebad  mov     rdx, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data4
0x14003ebb4  mov     r10, qword ptr cs:_GUID_e06d8023_db46_11cf_b4d1_00805f6cbbea.Data1
0x14003ebbb  inc     esi
0x14003ebbd  jmp     loc_14003EB13
```
