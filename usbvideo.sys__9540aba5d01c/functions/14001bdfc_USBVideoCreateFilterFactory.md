# USBVideoCreateFilterFactory

- ea: `0x14001bdfc`
- end: `0x14001c128`
- name: `USBVideoCreateFilterFactory`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001df50`

## callees

- `0x14000e8a8`
- `0x140018b18`
- `0x14001b15c`
- `0x14001bdfc`
- `0x140021fb4`
- `0x140023150`
- `0x140023dfc`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001bef8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bef8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001bea7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001bea7`
- `ks!KsCreateFilterFactory` at `0x14001c0a7`
- `ks!KsCreateFilterFactory` at `0x14001c0a7`
- `ks!KsAddItemToObjectBag` at `0x14001bedf`
- `ks!KsAddItemToObjectBag` at `0x14001bedf`

## pseudocode

```c
int __fastcall USBVideoCreateFilterFactory(__int64 a1)
{
  __int64 v1; // rbp
  GUID *PoolWithTag; // rax
  GUID *v4; // rdi
  NTSTATUS v5; // r14d
  int result; // eax
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // r10d
  __int64 v12; // r14
  __int64 v13; // r8
  __int64 v14; // rdi
  int v15; // r11d
  __int64 v16; // r9
  int v17; // r15d
  int v18; // ecx
  __int64 v19; // rcx
  int v20; // edi
  int v21; // ebx
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF
  PKSFILTERFACTORY FilterFactory; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v22 = 0;
  FilterFactory = 0;
  memset((void *)(v1 + 48), 0, 0x68u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v1);
  *(_DWORD *)(v1 + 64) = -1;
  *(_QWORD *)(v1 + 48) = &off_1400432B8;
  *(_DWORD *)(v1 + 68) = 0;
  *(_QWORD *)(v1 + 72) = &KSNAME_Filter;
  PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x48u, 0x56425355u);
  v4 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x48u);
      goto LABEL_7;
    }
    return -1073741670;
  }
  if ( !PoolWithTag )
    return -1073741670;
LABEL_7:
  v5 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v4, FreeMem);
  if ( v5 >= 0 )
  {
    memset(v4, 0, 0x48u);
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL);
    v8 = *(unsigned __int16 *)(v7 + 8);
    *(_DWORD *)v4->Data4 = 1932930986;
    *(_DWORD *)&v4->Data4[4] = -1181400098;
    v4->Data1 = v8 - 310033109;
    *(_DWORD *)&v4->Data2 = 1134769913;
    v9 = *(unsigned __int16 *)(v7 + 10);
    *(_DWORD *)v4[1].Data4 = -622863953;
    *(_DWORD *)&v4[1].Data4[4] = 1454726460;
    v4[1].Data1 = v9 + 2081374916;
    *(_DWORD *)&v4[1].Data2 = 1285605065;
    v4[2] = (GUID)KSCOMPONENTID_USBVIDEO;
    v4[3] = GUID_NULL;
    v4[4].Data1 = *(unsigned __int8 *)(v7 + 13);
    *(_DWORD *)&v4[4].Data2 = (unsigned __int8)*(_WORD *)(v7 + 12);
    *(_QWORD *)(v1 + 144) = v4;
    result = USBVideoPinBuildDescriptors(a1, v1 + 88, v1 + 80, v1 + 84);
    if ( result >= 0 )
    {
      result = BuildUSBVideoFilterTopology(a1);
      if ( result >= 0 )
      {
        v10 = 0;
        v11 = *(_DWORD *)(v1 + 80);
        v12 = *(unsigned int *)(v1 + 84);
        v13 = *(_QWORD *)(v1 + 88);
        v14 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 200LL);
        v15 = *(_DWORD *)(v1 + 112);
        v16 = *(_QWORD *)(v1 + 120);
        v17 = *(_DWORD *)(v1 + 116);
        if ( v11 )
        {
          do
          {
            v18 = *(_DWORD *)(v14 + 4 * v10);
            if ( v18 >= 0 && v18 < v15 )
            {
              v19 = (unsigned int)(v17 * v18);
              if ( *(_DWORD *)(v19 + v16 + 44) == 1 )
              {
                *(_QWORD *)(v13 + 8) = *(_QWORD *)(v19 + v16);
                v13 += v12;
              }
            }
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < v11 );
        }
        v20 = BuildFilterAutomationTable(a1, v1 + 48, &v22, v16);
        if ( v20 >= 0 )
        {
          *(_QWORD *)(v1 + 56) = v22;
          result = KsCreateFilterFactory(
                     *(PDEVICE_OBJECT *)(a1 + 24),
                     (const KSFILTER_DESCRIPTOR *)(v1 + 48),
                     (PWSTR)L"GLOBAL",
                     0,
                     8u,
                     0,
                     0,
                     &FilterFactory);
          v21 = result;
          if ( result >= 0 )
          {
            IsCacheUVCControlEnabled(a1);
            if ( FilterFactory )
            {
              ReplicateDeviceRegistryVars(*(PDEVICE_OBJECT *)(a1 + 32), FilterFactory);
              return v21;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v1);
              return -1073741595;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_687d416b691536ceda7edcd6a9251505_Traceguids, v1);
          return v20;
        }
      }
    }
  }
  else
  {
    ExFreePoolWithTag(v4, 0x56425355u);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14001bdfc  mov     rax, rsp
0x14001bdff  mov     [rax+18h], rbx
0x14001be03  mov     [rax+20h], rbp
0x14001be07  push    rsi
0x14001be08  push    rdi
0x14001be09  push    r12
0x14001be0b  push    r14
0x14001be0d  push    r15
0x14001be0f  sub     rsp, 40h
0x14001be13  mov     rbp, [rcx+10h]
0x14001be17  xor     edx, edx; Val
0x14001be19  mov     rsi, rcx
0x14001be1c  mov     qword ptr [rax+8], 0
0x14001be24  mov     qword ptr [rax+10h], 0
0x14001be2c  lea     rbx, [rbp+30h]
0x14001be30  mov     rcx, rbx; void *
0x14001be33  lea     r8d, [rdx+68h]; Size
0x14001be37  call    memset
0x14001be3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be43  lea     rax, WPP_GLOBAL_Control
0x14001be4a  cmp     rcx, rax
0x14001be4d  jz      short loc_14001BE6D
0x14001be4f  cmp     byte ptr [rcx+29h], 2
0x14001be53  jb      short loc_14001BE6D
0x14001be55  mov     rcx, [rcx+18h]
0x14001be59  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14001be60  mov     edx, 1Eh
0x14001be65  mov     r9, rbp
0x14001be68  call    WPP_SF_q
0x14001be6d  lea     rax, off_1400432B8
0x14001be74  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x14001be7b  mov     [rbx], rax
0x14001be7e  mov     r15d, 56425355h
0x14001be84  lea     rax, KSNAME_Filter
0x14001be8b  mov     dword ptr [rbx+14h], 0
0x14001be92  mov     r12d, 48h ; 'H'
0x14001be98  mov     [rbx+18h], rax
0x14001be9c  mov     r8d, r15d; Tag
0x14001be9f  mov     edx, r12d; NumberOfBytes
0x14001bea2  mov     ecx, 600h; PoolType
0x14001bea7  call    cs:__imp_ExAllocatePoolWithTag
0x14001beae  nop     dword ptr [rax+rax+00h]
0x14001beb3  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14001beba  mov     rdi, rax
0x14001bebd  jnz     short loc_14001BF0C
0x14001bebf  test    rax, rax
0x14001bec2  jz      short loc_14001BF11
0x14001bec4  mov     r8d, r12d; Size
0x14001bec7  xor     edx, edx; Val
0x14001bec9  mov     rcx, rax; void *
0x14001becc  call    memset
0x14001bed1  mov     rcx, [rsi+8]; ObjectBag
0x14001bed5  lea     r8, FreeMem; Free
0x14001bedc  mov     rdx, rdi; Item
0x14001bedf  call    cs:__imp_KsAddItemToObjectBag
0x14001bee6  nop     dword ptr [rax+rax+00h]
0x14001beeb  mov     r14d, eax
0x14001beee  mov     rcx, rdi; void *
0x14001bef1  test    eax, eax
0x14001bef3  jns     short loc_14001BF1B
0x14001bef5  mov     edx, r15d; Tag
0x14001bef8  call    cs:__imp_ExFreePoolWithTag
0x14001beff  nop     dword ptr [rax+rax+00h]
0x14001bf04  mov     eax, r14d
0x14001bf07  jmp     loc_14001C10E
0x14001bf0c  test    rdi, rdi
0x14001bf0f  jnz     short loc_14001BED1
0x14001bf11  mov     eax, 0C000009Ah
0x14001bf16  jmp     loc_14001C10E
0x14001bf1b  mov     r8, r12; Size
0x14001bf1e  xor     edx, edx; Val
0x14001bf20  call    memset
0x14001bf25  mov     rax, [rsi+10h]
0x14001bf29  lea     r9, [rbx+24h]
0x14001bf2d  movups  xmm0, cs:KSCOMPONENTID_USBVIDEO
0x14001bf34  lea     r8, [rbx+20h]
0x14001bf38  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x14001bf3f  mov     rcx, [rax+28h]
0x14001bf43  lea     rdx, [rbx+28h]
0x14001bf47  movzx   eax, word ptr [rcx+8]
0x14001bf4b  mov     dword ptr [rdi+8], 73362FAAh
0x14001bf52  sub     eax, 127ABAD5h
0x14001bf57  mov     dword ptr [rdi+0Ch], 0B99543DEh
0x14001bf5e  mov     [rdi], eax
0x14001bf60  mov     dword ptr [rdi+4], 43A336F9h
0x14001bf67  movzx   eax, word ptr [rcx+0Ah]
0x14001bf6b  mov     dword ptr [rdi+18h], 0DADFD9AFh
0x14001bf72  add     eax, 7C0F42C4h
0x14001bf77  mov     dword ptr [rdi+1Ch], 56B55D3Ch
0x14001bf7e  mov     [rdi+10h], eax
0x14001bf81  mov     dword ptr [rdi+14h], 4CA0C6C9h
0x14001bf88  movdqu  xmmword ptr [rdi+20h], xmm0
0x14001bf8d  movdqu  xmmword ptr [rdi+30h], xmm1
0x14001bf92  movzx   eax, byte ptr [rcx+0Dh]
0x14001bf96  mov     [rdi+40h], eax
0x14001bf99  movzx   eax, word ptr [rcx+0Ch]
0x14001bf9d  movzx   ecx, al
0x14001bfa0  mov     [rdi+44h], ecx
0x14001bfa3  mov     rcx, rsi
0x14001bfa6  mov     [rbx+60h], rdi
0x14001bfaa  call    USBVideoPinBuildDescriptors
0x14001bfaf  test    eax, eax
0x14001bfb1  js      loc_14001C10E
0x14001bfb7  mov     rcx, rsi
0x14001bfba  call    BuildUSBVideoFilterTopology
0x14001bfbf  test    eax, eax
0x14001bfc1  js      loc_14001C10E
0x14001bfc7  mov     rax, [rsi+10h]
0x14001bfcb  xor     edx, edx
0x14001bfcd  mov     r10d, [rbx+20h]
0x14001bfd1  mov     r14d, [rbx+24h]
0x14001bfd5  mov     r8, [rbx+28h]
0x14001bfd9  mov     rdi, [rax+0C8h]
0x14001bfe0  mov     r11d, [rbx+40h]
0x14001bfe4  mov     r9, [rbx+48h]
0x14001bfe8  mov     r15d, [rbx+44h]
0x14001bfec  test    r10d, r10d
0x14001bfef  jz      short loc_14001C01B
0x14001bff1  mov     ecx, [rdi+rdx*4]
0x14001bff4  test    ecx, ecx
0x14001bff6  js      short loc_14001C014
0x14001bff8  cmp     ecx, r11d
0x14001bffb  jge     short loc_14001C014
0x14001bffd  imul    ecx, r15d
0x14001c001  cmp     dword ptr [rcx+r9+2Ch], 1
0x14001c007  jnz     short loc_14001C014
0x14001c009  mov     rax, [rcx+r9]
0x14001c00d  mov     [r8+8], rax
0x14001c011  add     r8, r14
0x14001c014  inc     edx
0x14001c016  cmp     edx, r10d
0x14001c019  jb      short loc_14001BFF1
0x14001c01b  lea     r8, [rsp+68h+arg_0]
0x14001c020  mov     rdx, rbx
0x14001c023  mov     rcx, rsi
0x14001c026  call    BuildFilterAutomationTable
0x14001c02b  mov     edi, eax
0x14001c02d  test    eax, eax
0x14001c02f  jns     short loc_14001C069
0x14001c031  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c038  lea     rax, WPP_GLOBAL_Control
0x14001c03f  cmp     rcx, rax
0x14001c042  jz      short loc_14001C062
0x14001c044  cmp     byte ptr [rcx+29h], 2
0x14001c048  jb      short loc_14001C062
0x14001c04a  mov     rcx, [rcx+18h]
0x14001c04e  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14001c055  mov     edx, 20h ; ' '
0x14001c05a  mov     r9, rbp
0x14001c05d  call    WPP_SF_q
0x14001c062  mov     eax, edi
0x14001c064  jmp     loc_14001C10E
0x14001c069  mov     rax, [rsp+68h+arg_0]
0x14001c06e  lea     r8, RefString; "GLOBAL"
0x14001c075  mov     [rbx+8], rax
0x14001c079  xor     r9d, r9d; SecurityDescriptor
0x14001c07c  mov     rcx, [rsi+18h]; DeviceObject
0x14001c080  lea     rax, [rsp+68h+arg_8]
0x14001c085  mov     [rsp+68h+FilterFactory], rax; FilterFactory
0x14001c08a  mov     rdx, rbx; Descriptor
0x14001c08d  mov     [rsp+68h+WakeCallback], 0; WakeCallback
0x14001c096  mov     [rsp+68h+SleepCallback], 0; SleepCallback
0x14001c09f  mov     [rsp+68h+CreateItemFlags], 8; CreateItemFlags
0x14001c0a7  call    cs:__imp_KsCreateFilterFactory
0x14001c0ae  nop     dword ptr [rax+rax+00h]
0x14001c0b3  mov     ebx, eax
0x14001c0b5  test    eax, eax
0x14001c0b7  js      short loc_14001C10E
0x14001c0b9  mov     rcx, rsi
0x14001c0bc  call    IsCacheUVCControlEnabled
0x14001c0c1  mov     rdx, [rsp+68h+arg_8]; FilterFactory
0x14001c0c6  test    rdx, rdx
0x14001c0c9  jnz     short loc_14001C103
0x14001c0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0d2  lea     rax, WPP_GLOBAL_Control
0x14001c0d9  cmp     rcx, rax
0x14001c0dc  jz      short loc_14001C0FC
0x14001c0de  cmp     byte ptr [rcx+29h], 2
0x14001c0e2  jb      short loc_14001C0FC
0x14001c0e4  mov     rcx, [rcx+18h]
0x14001c0e8  lea     r8, WPP_687d416b691536ceda7edcd6a9251505_Traceguids
0x14001c0ef  mov     edx, 21h ; '!'
0x14001c0f4  mov     r9, rbp
0x14001c0f7  call    WPP_SF_q
0x14001c0fc  mov     eax, 0C00000E5h
0x14001c101  jmp     short loc_14001C10E
0x14001c103  mov     rcx, [rsi+20h]; DeviceObject
0x14001c107  call    ReplicateDeviceRegistryVars
0x14001c10c  mov     eax, ebx
0x14001c10e  lea     r11, [rsp+68h+var_28]
0x14001c113  mov     rbx, [r11+40h]
0x14001c117  mov     rbp, [r11+48h]
0x14001c11b  mov     rsp, r11
0x14001c11e  pop     r15
0x14001c120  pop     r14
0x14001c122  pop     r12
0x14001c124  pop     rdi
0x14001c125  pop     rsi
0x14001c126  retn
```
