# SrvNetCreateListenersBasedOnListenerRuleEntry

- ea: `0x14001ea1c`
- end: `0x14001edf3`
- name: `SrvNetCreateListenersBasedOnListenerRuleEntry`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001f244`

## callees

- `0x14001389c`
- `0x140016384`
- `0x140016450`
- `0x14001ea1c`
- `0x14001ee88`
- `0x14002a3e0`
- `0x1400417a0`
- `0x14004a508`
- `0x140051778`
- `0x140054a70`

## import_xrefs

- `ntoskrnl!RtlFreeOemString` at `0x14001ed15`
- `ntoskrnl!RtlFreeOemString` at `0x14001ed15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed05`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ed05`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ebc6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ebe3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ebc6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ebe3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ebaa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ebaa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ece6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ecf9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ece6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ecf9`

## pseudocode

```c
__int64 __fastcall SrvNetCreateListenersBasedOnListenerRuleEntry(
        __int64 a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v5; // r12d
  unsigned int v6; // esi
  unsigned int ComputerName; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // r13d
  char v11; // r12
  PERESOURCE v12; // rcx
  unsigned int v13; // edi
  KSPIN_LOCK SpinLock; // r13
  int TransportTypeFromTransportName; // eax
  int v16; // ecx
  int Endpoint; // eax
  __int64 v18; // rsi
  int AddrFromTransportName; // eax
  unsigned int *v20; // rax
  int v22; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-55h]
  unsigned int v24; // [rsp+58h] [rbp-51h]
  __int128 v25; // [rsp+60h] [rbp-49h] BYREF
  _STRING OemString; // [rsp+70h] [rbp-39h] BYREF
  __int64 v27; // [rsp+80h] [rbp-29h]
  __int64 v28; // [rsp+88h] [rbp-21h] BYREF
  unsigned int *v29; // [rsp+90h] [rbp-19h]
  __int128 v30; // [rsp+98h] [rbp-11h]
  _BYTE v31[32]; // [rsp+A8h] [rbp-1h] BYREF

  v29 = a4;
  v24 = a2;
  v27 = a1;
  v28 = 0;
  v22 = 32;
  v5 = a2;
  *a4 = 0;
  v6 = 0;
  v25 = 0;
  v30 = 0;
  OemString = 0;
  if ( !a2 )
  {
LABEL_14:
    v23 = 0;
    v10 = 0;
    ComputerName = RfsRegGetComputerName((__int64)v31, (__int64)&v22);
    if ( (ComputerName & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_4b4512c1b54e30e269f755586e080b68_Traceguids,
          ComputerName,
          v22);
      }
    }
    else
    {
      *((_QWORD *)&v25 + 1) = v31;
      LOWORD(v25) = v22;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)WPP_4b4512c1b54e30e269f755586e080b68_Traceguids,
          (unsigned int)&v25,
          v22);
      }
      ComputerName = SrvNetCreateAndPadNetBiosName(&v25, &OemString);
      if ( (ComputerName & 0x80000000) == 0 )
      {
        if ( OemString.Buffer )
        {
          v11 = 0;
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
          ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
          v12 = SrvNetDeviceExtension;
          v13 = v6;
          SpinLock = SrvNetDeviceExtension[3].SpinLock;
          if ( (KSPIN_LOCK *)SpinLock != &SrvNetDeviceExtension[3].SpinLock )
          {
            LOBYTE(v22) = 0;
            do
            {
              TransportTypeFromTransportName = SrvNetGetTransportTypeFromTransportName((PCUNICODE_STRING)(SpinLock + 24));
              if ( TransportTypeFromTransportName == *(unsigned __int8 *)(v27 + 2) )
              {
                v16 = (unsigned __int8)v22;
                if ( TransportTypeFromTransportName == 1 )
                  v16 = 1;
                v22 = v16;
                Endpoint = SrvNetAllocateEndpoint((PVOID)(SpinLock + 24), 1, v16, 0, v27, (__int64)&v28);
                ComputerName = Endpoint;
                if ( Endpoint < 0 && !v11 )
                {
                  v13 = v6 + 32;
                  if ( v6 + 32 < v6 )
                  {
                    v13 = -1;
                  }
                  else if ( v13 <= v24 )
                  {
                    v18 = 8LL * v23;
                    a3[v18 + 2] = Endpoint;
                    AddrFromTransportName = SrvNetGetAddrFromTransportName(SpinLock + 24, &a3[v18 + 3]);
                    if ( AddrFromTransportName < 0 )
                      a3[v18 + 2] = AddrFromTransportName;
                    ++v23;
                    v6 = v13;
                    goto LABEL_35;
                  }
                }
                v11 = 1;
              }
LABEL_35:
              v12 = SrvNetDeviceExtension;
              SpinLock = *(_QWORD *)SpinLock;
            }
            while ( (KSPIN_LOCK *)SpinLock != &SrvNetDeviceExtension[3].SpinLock );
          }
          if ( v24 )
            ComputerName = v11 != 0 ? 0x80000005 : 0;
          ExReleaseResourceLite((PERESOURCE)((char *)v12 + 288));
          ExReleaseResourceLite(SrvNetDeviceExtension);
          KeLeaveCriticalRegion();
          RtlFreeOemString(&OemString);
          v5 = v24;
          v10 = v23;
LABEL_49:
          if ( a3 && v5 >= 8 )
          {
            v20 = v29;
            *a3 = v10;
            a3[1] = v13;
            *v20 = v6;
          }
          return ComputerName;
        }
        ComputerName = -1073741534;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids, ComputerName);
      }
    }
    v13 = v6;
    goto LABEL_49;
  }
  if ( !a3 )
  {
    ComputerName = -1073741811;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 10;
LABEL_7:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids, ComputerName);
      return ComputerName;
    }
    return ComputerName;
  }
  if ( a2 >= 8 )
  {
    v6 = 8;
    goto LABEL_14;
  }
  ComputerName = -1073741789;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v9 = 11;
    goto LABEL_7;
  }
  return ComputerName;
}

```

## disassembly

```asm
0x14001ea1c  mov     [rsp-8+arg_8], rbx
0x14001ea21  push    rbp
0x14001ea22  push    rsi
0x14001ea23  push    rdi
0x14001ea24  push    r12
0x14001ea26  push    r13
0x14001ea28  push    r14
0x14001ea2a  push    r15
0x14001ea2c  lea     rbp, [rsp-27h]
0x14001ea31  sub     rsp, 0D0h
0x14001ea38  mov     rax, cs:__security_cookie
0x14001ea3f  xor     rax, rsp
0x14001ea42  mov     [rbp+57h+var_38], rax
0x14001ea46  xor     r14d, r14d
0x14001ea49  mov     [rbp+57h+var_70], r9
0x14001ea4d  mov     [rbp+57h+var_A8], edx
0x14001ea50  xorps   xmm0, xmm0
0x14001ea53  mov     [rbp+57h+var_80], rcx
0x14001ea57  xorps   xmm1, xmm1
0x14001ea5a  mov     [rbp+57h+var_78], r14
0x14001ea5e  mov     r15, r8
0x14001ea61  mov     [rbp+57h+var_B0], 20h ; ' '
0x14001ea68  mov     r12d, edx
0x14001ea6b  mov     [r9], r14d
0x14001ea6e  mov     esi, r14d
0x14001ea71  movups  [rbp+57h+var_A0], xmm0
0x14001ea75  movups  [rbp+57h+var_68], xmm1
0x14001ea79  movups  xmmword ptr [rbp+57h+OemString.Length], xmm0
0x14001ea7d  test    edx, edx
0x14001ea7f  jz      loc_14001EB19
0x14001ea85  test    r8, r8
0x14001ea88  jnz     short loc_14001EAD7
0x14001ea8a  mov     ebx, 0C000000Dh
0x14001ea8f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ea96  lea     rdi, WPP_GLOBAL_Control
0x14001ea9d  cmp     rcx, rdi
0x14001eaa0  jz      loc_14001EDC9
0x14001eaa6  mov     eax, [rcx+2Ch]
0x14001eaa9  test    al, 10h
0x14001eaab  jz      loc_14001EDC9
0x14001eab1  cmp     byte ptr [rcx+29h], 2
0x14001eab5  jb      loc_14001EDC9
0x14001eabb  lea     edx, [r8+0Ah]
0x14001eabf  mov     rcx, [rcx+18h]
0x14001eac3  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001eaca  mov     r9d, ebx
0x14001eacd  call    WPP_SF_d
0x14001ead2  jmp     loc_14001EDC9
0x14001ead7  cmp     edx, 8
0x14001eada  jnb     short loc_14001EB14
0x14001eadc  mov     ebx, 0C0000023h
0x14001eae1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001eae8  lea     rdi, WPP_GLOBAL_Control
0x14001eaef  cmp     rcx, rdi
0x14001eaf2  jz      loc_14001EDC9
0x14001eaf8  mov     eax, [rcx+2Ch]
0x14001eafb  test    al, 10h
0x14001eafd  jz      loc_14001EDC9
0x14001eb03  cmp     byte ptr [rcx+29h], 2
0x14001eb07  jb      loc_14001EDC9
0x14001eb0d  mov     edx, 0Bh
0x14001eb12  jmp     short loc_14001EABF
0x14001eb14  mov     esi, 8
0x14001eb19  lea     rdx, [rbp+57h+var_B0]
0x14001eb1d  mov     [rbp+57h+var_AC], r14d
0x14001eb21  lea     rcx, [rbp+57h+var_58]
0x14001eb25  mov     r13d, r14d
0x14001eb28  call    RfsRegGetComputerName
0x14001eb2d  mov     ebx, eax
0x14001eb2f  test    eax, eax
0x14001eb31  js      loc_14001ED6B
0x14001eb37  mov     r8d, [rbp+57h+var_B0]
0x14001eb3b  lea     rax, [rbp+57h+var_58]
0x14001eb3f  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14001eb43  mov     word ptr [rbp+57h+var_A0], r8w
0x14001eb48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001eb4f  lea     rdi, WPP_GLOBAL_Control
0x14001eb56  cmp     rcx, rdi
0x14001eb59  jz      short loc_14001EB86
0x14001eb5b  mov     eax, [rcx+2Ch]
0x14001eb5e  test    al, 10h
0x14001eb60  jz      short loc_14001EB86
0x14001eb62  cmp     byte ptr [rcx+29h], 2
0x14001eb66  jb      short loc_14001EB86
0x14001eb68  mov     rcx, [rcx+18h]
0x14001eb6c  lea     r9, [rbp+57h+var_A0]
0x14001eb70  mov     [rsp+100h+var_E0], r8d
0x14001eb75  mov     edx, 0Dh
0x14001eb7a  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001eb81  call    WPP_SF_Zd
0x14001eb86  lea     rdx, [rbp+57h+OemString]
0x14001eb8a  lea     rcx, [rbp+57h+var_A0]
0x14001eb8e  call    SrvNetCreateAndPadNetBiosName
0x14001eb93  mov     ebx, eax
0x14001eb95  test    eax, eax
0x14001eb97  js      loc_14001ED33
0x14001eb9d  cmp     [rbp+57h+OemString.Buffer], r14
0x14001eba1  jz      loc_14001ED2E
0x14001eba7  mov     r12b, r14b
0x14001ebaa  call    cs:__imp_KeEnterCriticalRegion
0x14001ebb1  nop     dword ptr [rax+rax+00h]
0x14001ebb6  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14001ebbd  mov     r14d, 1
0x14001ebc3  mov     dl, r14b; Wait
0x14001ebc6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001ebcd  nop     dword ptr [rax+rax+00h]
0x14001ebd2  mov     rcx, cs:SrvNetDeviceExtension
0x14001ebd9  mov     dl, r14b; Wait
0x14001ebdc  add     rcx, 120h; Resource
0x14001ebe3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001ebea  nop     dword ptr [rax+rax+00h]
0x14001ebef  mov     rcx, cs:SrvNetDeviceExtension
0x14001ebf6  mov     edi, esi
0x14001ebf8  lea     rax, [rcx+198h]
0x14001ebff  mov     r13, [rax]
0x14001ec02  cmp     r13, rax
0x14001ec05  jz      loc_14001ECCE
0x14001ec0b  mov     byte ptr [rbp+57h+var_B0], r12b
0x14001ec0f  lea     rcx, [r13+18h]; String2
0x14001ec13  call    SrvNetGetTransportTypeFromTransportName
0x14001ec18  mov     rdx, [rbp+57h+var_80]
0x14001ec1c  movzx   ecx, byte ptr [rdx+2]
0x14001ec20  cmp     eax, ecx
0x14001ec22  jnz     loc_14001ECB3
0x14001ec28  mov     ecx, [rbp+57h+var_B0]
0x14001ec2b  lea     r8, [rbp+57h+var_68]
0x14001ec2f  mov     r9, [rbp+57h+OemString.Buffer]
0x14001ec33  cmp     eax, r14d
0x14001ec36  movzx   ecx, cl
0x14001ec39  lea     rax, [rbp+57h+var_78]
0x14001ec3d  mov     [rsp+100h+var_C0], rax; __int64
0x14001ec42  cmovz   ecx, r14d
0x14001ec46  mov     [rsp+100h+var_C8], rdx; __int64
0x14001ec4b  lea     rdx, [rbp+57h+var_A0]
0x14001ec4f  mov     [rsp+100h+var_D0], 0; char
0x14001ec54  mov     [rsp+100h+var_D8], cl; char
0x14001ec58  mov     [rbp+57h+var_B0], ecx
0x14001ec5b  lea     rcx, [r13+18h]; DeviceName
0x14001ec5f  mov     [rsp+100h+var_E0], r14d; int
0x14001ec64  call    SrvNetAllocateEndpoint
0x14001ec69  mov     ebx, eax
0x14001ec6b  test    eax, eax
0x14001ec6d  jns     short loc_14001ECB0
0x14001ec6f  test    r12b, r12b
0x14001ec72  jnz     short loc_14001ECB0
0x14001ec74  lea     edi, [rsi+20h]
0x14001ec77  cmp     edi, esi
0x14001ec79  jb      short loc_14001ECAD
0x14001ec7b  cmp     edi, [rbp+57h+var_A8]
0x14001ec7e  ja      short loc_14001ECB0
0x14001ec80  mov     esi, [rbp+57h+var_AC]
0x14001ec83  lea     rcx, [r13+18h]
0x14001ec87  shl     rsi, 5
0x14001ec8b  lea     rdx, [rsi+0Ch]
0x14001ec8f  mov     [rsi+r15+8], eax
0x14001ec94  add     rdx, r15
0x14001ec97  call    SrvNetGetAddrFromTransportName
0x14001ec9c  test    eax, eax
0x14001ec9e  jns     short loc_14001ECA5
0x14001eca0  mov     [rsi+r15+8], eax
0x14001eca5  add     [rbp+57h+var_AC], r14d
0x14001eca9  mov     esi, edi
0x14001ecab  jmp     short loc_14001ECB3
0x14001ecad  or      edi, 0FFFFFFFFh
0x14001ecb0  mov     r12b, r14b
0x14001ecb3  mov     rcx, cs:SrvNetDeviceExtension
0x14001ecba  mov     r13, [r13+0]
0x14001ecbe  lea     rax, [rcx+198h]
0x14001ecc5  cmp     r13, rax
0x14001ecc8  jnz     loc_14001EC0F
0x14001ecce  cmp     [rbp+57h+var_A8], 0
0x14001ecd2  jz      short loc_14001ECDF
0x14001ecd4  neg     r12b
0x14001ecd7  sbb     ebx, ebx
0x14001ecd9  and     ebx, 80000005h
0x14001ecdf  add     rcx, 120h; Resource
0x14001ece6  call    cs:__imp_ExReleaseResourceLite
0x14001eced  nop     dword ptr [rax+rax+00h]
0x14001ecf2  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x14001ecf9  call    cs:__imp_ExReleaseResourceLite
0x14001ed00  nop     dword ptr [rax+rax+00h]
0x14001ed05  call    cs:__imp_KeLeaveCriticalRegion
0x14001ed0c  nop     dword ptr [rax+rax+00h]
0x14001ed11  lea     rcx, [rbp+57h+OemString]; OemString
0x14001ed15  call    cs:__imp_RtlFreeOemString
0x14001ed1c  nop     dword ptr [rax+rax+00h]
0x14001ed21  mov     r12d, [rbp+57h+var_A8]
0x14001ed25  mov     r13d, [rbp+57h+var_AC]
0x14001ed29  jmp     loc_14001EDB1
0x14001ed2e  mov     ebx, 0C0000122h
0x14001ed33  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ed3a  cmp     rcx, rdi
0x14001ed3d  jz      short loc_14001EDAF
0x14001ed3f  mov     eax, [rcx+2Ch]
0x14001ed42  test    al, 10h
0x14001ed44  jz      short loc_14001EDAF
0x14001ed46  mov     r14d, 1
0x14001ed4c  cmp     [rcx+29h], r14b
0x14001ed50  jb      short loc_14001EDAF
0x14001ed52  mov     rcx, [rcx+18h]
0x14001ed56  lea     edx, [r14+0Eh]
0x14001ed5a  mov     r9d, ebx
0x14001ed5d  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001ed64  call    WPP_SF_d
0x14001ed69  jmp     short loc_14001EDAF
0x14001ed6b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001ed72  lea     rdi, WPP_GLOBAL_Control
0x14001ed79  cmp     rcx, rdi
0x14001ed7c  jz      short loc_14001EDAF
0x14001ed7e  mov     eax, [rcx+2Ch]
0x14001ed81  test    al, 10h
0x14001ed83  jz      short loc_14001EDAF
0x14001ed85  mov     r14d, 1
0x14001ed8b  cmp     [rcx+29h], r14b
0x14001ed8f  jb      short loc_14001EDAF
0x14001ed91  mov     eax, [rbp+57h+var_B0]
0x14001ed94  lea     edx, [r14+0Dh]
0x14001ed98  mov     rcx, [rcx+18h]
0x14001ed9c  lea     r8, WPP_4b4512c1b54e30e269f755586e080b68_Traceguids
0x14001eda3  mov     r9d, ebx
0x14001eda6  mov     [rsp+100h+var_E0], eax
0x14001edaa  call    WPP_SF_Dd
0x14001edaf  mov     edi, esi
0x14001edb1  test    r15, r15
0x14001edb4  jz      short loc_14001EDC9
0x14001edb6  cmp     r12d, 8
0x14001edba  jb      short loc_14001EDC9
0x14001edbc  mov     rax, [rbp+57h+var_70]
0x14001edc0  mov     [r15], r13d
0x14001edc3  mov     [r15+4], edi
0x14001edc7  mov     [rax], esi
0x14001edc9  mov     eax, ebx
0x14001edcb  mov     rcx, [rbp+57h+var_38]
0x14001edcf  xor     rcx, rsp; StackCookie
0x14001edd2  call    __security_check_cookie
0x14001edd7  mov     rbx, [rsp+100h+arg_8]
0x14001eddf  add     rsp, 0D0h
0x14001ede6  pop     r15
0x14001ede8  pop     r14
0x14001edea  pop     r13
0x14001edec  pop     r12
0x14001edee  pop     rdi
0x14001edef  pop     rsi
0x14001edf0  pop     rbp
0x14001edf1  retn
```
