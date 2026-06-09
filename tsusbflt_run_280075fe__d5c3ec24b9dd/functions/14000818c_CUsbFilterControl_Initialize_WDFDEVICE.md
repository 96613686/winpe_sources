# CUsbFilterControl::Initialize(WDFDEVICE__ *)

- ea: `0x14000818c`
- end: `0x1400085de`
- name: `?Initialize@CUsbFilterControl@@AEAAJPEAUWDFDEVICE__@@@Z`
- size: `1106`
- prototype: `__int64 __fastcall(CUsbFilterControl *__hidden this, struct WDFDEVICE__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400068dc`

## callees

- `0x1400048d4`
- `0x140004f18`
- `0x140004f48`
- `0x14000818c`
- `0x140008ad8`
- `0x1400090d4`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008585`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008585`
- `ntoskrnl!ExAllocatePool2` at `0x14000832a`
- `ntoskrnl!ExAllocatePool2` at `0x14000832a`

## string_xrefs

- `0x1400081e1`: `\DosDevices\TerminalServicesUSBFilterDriverControlObject`
- `0x1400082a5`: `\REGISTRY\MACHINE\Software\Policies\Microsoft\Windows NT\Terminal Services\Client`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::Initialize(CUsbFilterControl *this, struct WDFDEVICE__ *a2)
{
  int UsbEnableMode; // eax
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int *Pool2; // rax
  __int64 v14; // rdx
  bool v15; // zf
  __int64 v16; // rdx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h]
  __int128 v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  _QWORD v25[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v27[12]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v28[7]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v29; // [rsp+160h] [rbp+60h]

  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset(v27, 0, sizeof(v27));
  v28[0] = *(_OWORD *)L"\\DosDevices\\TerminalServicesUSBFilterDriverControlObject";
  v28[2] = *(_OWORD *)L"inalServicesUSBFilterDriverControlObject";
  v28[1] = *(_OWORD *)L"ces\\TerminalServicesUSBFilterDriverControlObject";
  v28[4] = *(_OWORD *)L"ilterDriverControlObject";
  v28[3] = *(_OWORD *)L"icesUSBFilterDriverControlObject";
  v29 = aDosdevicesTerm[56];
  v28[6] = *(_OWORD *)L"olObject";
  v26 = 0;
  v28[5] = *(_OWORD *)L"verControlObject";
  v25[0] = 7471216;
  v25[1] = v28;
  v20 = 0;
  *(_QWORD *)this = a2;
  UsbEnableMode = CUsbFilterControl::QueryUsbEnableMode();
  *((_DWORD *)this + 10) = UsbEnableMode;
  if ( !UsbEnableMode
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
  }
  v5 = CUsbBusFilter::QueryRegistryData(
         L"\\REGISTRY\\MACHINE\\Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Client",
         L"MaxNumInterfaceGuidRecycle",
         &v20);
  v8 = v5;
  if ( v5 == -1073741772 )
  {
    v9 = 64;
    goto LABEL_13;
  }
  if ( v5 >= 0 )
  {
    v9 = v20;
LABEL_13:
    if ( v9 > 0x40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, v6, v7, v9);
      v9 = 64;
    }
    Pool2 = (unsigned int *)ExAllocatePool2(256, 68, 1917088324);
    if ( Pool2 )
    {
      v14 = 0;
      *Pool2 = 64;
      do
      {
        *((_BYTE *)Pool2 + v14 + 4) = 0;
        v14 = (unsigned int)(v14 + 1);
      }
      while ( (unsigned int)v14 < *Pool2 );
      if ( v9 <= *Pool2 )
      {
        *Pool2 = v9;
        v15 = *((_DWORD *)this + 10) == 0;
        *((_QWORD *)this + 4) = Pool2;
        if ( v15
          || (v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[40].Flink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     *(_QWORD *)this,
                     v25),
              v8 = v5,
              v5 >= 0) )
        {
          memset(v27, 0, sizeof(v27));
          v16 = *(_QWORD *)this;
          v27[5] = &FcEvtIoDeviceControl;
          v27[0] = 0x100000060LL;
          v24 = 0;
          *(_QWORD *)&v22 = 0;
          LODWORD(v27[1]) = 2;
          v21 = 0;
          BYTE5(v27[1]) = 1;
          v23 = 0;
          LODWORD(v21) = 56;
          *((_QWORD *)&v22 + 1) = 0x100000001LL;
          v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD *, __int128 *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[76].Flink)(
                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                 v16,
                 v27,
                 &v21,
                 &v26);
          v8 = v5;
          if ( v5 >= 0 )
          {
            v24 = 0;
            v17 = *(_QWORD *)this;
            *(_QWORD *)&v22 = 0;
            *((_QWORD *)&v22 + 1) = 0x100000001LL;
            v23 = v17;
            v21 = 0;
            LODWORD(v21) = 56;
            v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, char *))WPP_MAIN_CB.Queue.ListEntry.Flink[6].Blink)(
                   WPP_MAIN_CB.Queue.ListEntry.Blink,
                   &v21,
                   (char *)this + 8);
            v8 = v5;
            if ( v5 >= 0 )
            {
              v24 = 0;
              v18 = *(_QWORD *)this;
              *(_QWORD *)&v22 = 0;
              *((_QWORD *)&v22 + 1) = 0x100000001LL;
              v23 = v18;
              v21 = 0;
              LODWORD(v21) = 56;
              v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, char *))WPP_MAIN_CB.Queue.ListEntry.Flink[6].Blink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     &v21,
                     (char *)this + 16);
              v8 = v5;
              if ( v5 >= 0 )
              {
                ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[13].Blink)(
                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                  *(_QWORD *)this);
                return 0;
              }
              else
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v11 = 32;
                  goto LABEL_11;
                }
              }
            }
            else
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v11 = 31;
                goto LABEL_11;
              }
            }
          }
          else
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v11 = 30;
              goto LABEL_11;
            }
          }
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v11 = 29;
            goto LABEL_11;
          }
        }
        return v8;
      }
      v8 = -1073741811;
      ExFreePoolWithTag(Pool2, 0);
    }
    else
    {
      v8 = -1073741801;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v11 = 28;
      v12 = v8;
      goto LABEL_45;
    }
    return v8;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v11 = 26;
LABEL_11:
    v12 = (unsigned int)v5;
LABEL_45:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, v12);
  }
  return v8;
}

```

## disassembly

```asm
0x14000818c  push    rbp
0x14000818e  push    rbx
0x14000818f  push    rdi
0x140008190  push    r12
0x140008192  push    r13
0x140008194  push    r15
0x140008196  lea     rbp, [rsp-88h]
0x14000819e  sub     rsp, 188h
0x1400081a5  mov     rax, cs:__security_cookie
0x1400081ac  xor     rax, rsp
0x1400081af  mov     [rbp+0B0h+var_40], rax
0x1400081b3  xorps   xmm0, xmm0
0x1400081b6  xor     eax, eax
0x1400081b8  mov     rbx, rdx
0x1400081bb  mov     [rsp+1B0h+var_148], rax
0x1400081c0  mov     rdi, rcx
0x1400081c3  xor     edx, edx; Val
0x1400081c5  lea     rcx, [rbp+0B0h+var_120]; void *
0x1400081c9  lea     r8d, [rax+60h]; Size
0x1400081cd  movups  [rsp+1B0h+var_178], xmm0
0x1400081d2  movups  [rsp+1B0h+var_168], xmm0
0x1400081d7  movups  [rsp+1B0h+var_158], xmm0
0x1400081dc  call    memset
0x1400081e1  movaps  xmm0, xmmword ptr cs:aDosdevicesTerm; "\\DosDevices\\TerminalServicesUSBFilter"...
0x1400081e8  movaps  xmm1, xmmword ptr cs:aDosdevicesTerm+10h; "ces\\TerminalServicesUSBFilterDriverCon"...
0x1400081ef  movzx   eax, word ptr cs:aDosdevicesTerm+70h; ""
0x1400081f6  movaps  [rbp+0B0h+var_C0], xmm0
0x1400081fa  movaps  xmm0, xmmword ptr cs:aDosdevicesTerm+20h; "inalServicesUSBFilterDriverControlObjec"...
0x140008201  movaps  [rbp+0B0h+var_A0], xmm0
0x140008205  movaps  xmm0, xmmword ptr cs:aDosdevicesTerm+40h; "ilterDriverControlObject"
0x14000820c  movaps  [rbp+0B0h+var_B0], xmm1
0x140008210  movaps  xmm1, xmmword ptr cs:aDosdevicesTerm+30h; "icesUSBFilterDriverControlObject"
0x140008217  movaps  [rbp+0B0h+var_80], xmm0
0x14000821b  movaps  xmm0, xmmword ptr cs:aDosdevicesTerm+60h; "olObject"
0x140008222  movaps  [rbp+0B0h+var_90], xmm1
0x140008226  movaps  xmm1, xmmword ptr cs:aDosdevicesTerm+50h; "verControlObject"
0x14000822d  mov     [rbp+0B0h+var_50], ax
0x140008231  lea     rax, [rbp+0B0h+var_C0]
0x140008235  movaps  [rbp+0B0h+var_60], xmm0
0x140008239  mov     [rbp+0B0h+var_130], 0
0x140008241  movaps  [rbp+0B0h+var_70], xmm1
0x140008245  mov     [rsp+1B0h+var_140], 720070h
0x14000824e  mov     [rsp+1B0h+var_138], rax
0x140008253  mov     [rsp+1B0h+var_180], 0
0x14000825b  mov     [rdi], rbx
0x14000825e  call    ?QueryUsbEnableMode@CUsbFilterControl@@AEAA?AW4_USB_MODE@@XZ; CUsbFilterControl::QueryUsbEnableMode(void)
0x140008263  mov     [rdi+28h], eax
0x140008266  lea     r13, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x14000826d  lea     r15, WPP_GLOBAL_Control
0x140008274  test    eax, eax
0x140008276  jnz     short loc_140008299
0x140008278  mov     rcx, cs:WPP_GLOBAL_Control
0x14000827f  cmp     rcx, r15
0x140008282  jz      short loc_140008299
0x140008284  cmp     byte ptr [rcx+29h], 2
0x140008288  jb      short loc_140008299
0x14000828a  mov     rcx, [rcx+18h]
0x14000828e  lea     edx, [rax+19h]
0x140008291  mov     r8, r13
0x140008294  call    WPP_SF_
0x140008299  lea     r8, [rsp+1B0h+var_180]; unsigned int *
0x14000829e  lea     rdx, aMaxnuminterfac; "MaxNumInterfaceGuidRecycle"
0x1400082a5  lea     rcx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\Software\\Policies"...
0x1400082ac  call    ?QueryRegistryData@CUsbBusFilter@@SAJPEBG0PEAK@Z; CUsbBusFilter::QueryRegistryData(ushort const *,ushort const *,ulong *)
0x1400082b1  mov     ebx, eax
0x1400082b3  mov     r12d, 40h ; '@'
0x1400082b9  cmp     eax, 0C0000034h
0x1400082be  jnz     short loc_1400082C5
0x1400082c0  mov     ebx, r12d
0x1400082c3  jmp     short loc_1400082F4
0x1400082c5  test    eax, eax
0x1400082c7  jns     short loc_1400082F0
0x1400082c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082d0  cmp     rcx, r15
0x1400082d3  jz      loc_1400085BE
0x1400082d9  cmp     byte ptr [rcx+29h], 2
0x1400082dd  jb      loc_1400085BE
0x1400082e3  mov     edx, 1Ah
0x1400082e8  mov     r9d, eax
0x1400082eb  jmp     loc_1400085B2
0x1400082f0  mov     ebx, [rsp+1B0h+var_180]
0x1400082f4  cmp     ebx, r12d
0x1400082f7  jbe     short loc_14000831A
0x1400082f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008300  cmp     rcx, r15
0x140008303  jz      short loc_140008317
0x140008305  cmp     byte ptr [rcx+29h], 2
0x140008309  jb      short loc_140008317
0x14000830b  mov     rcx, [rcx+18h]
0x14000830f  mov     r9d, ebx
0x140008312  call    WPP_SF_DD
0x140008317  mov     ebx, r12d
0x14000831a  mov     edx, 44h ; 'D'
0x14000831f  mov     ecx, 100h
0x140008324  mov     r8d, 72447244h
0x14000832a  call    cs:__imp_ExAllocatePool2
0x140008331  nop     dword ptr [rax+rax+00h]
0x140008336  mov     rcx, rax; P
0x140008339  test    rax, rax
0x14000833c  jz      loc_140008593
0x140008342  xor     edx, edx
0x140008344  mov     [rax], r12d
0x140008347  lea     r12d, [rdx+1]
0x14000834b  mov     byte ptr [rdx+rax+4], 0
0x140008350  add     edx, r12d
0x140008353  cmp     edx, [rax]
0x140008355  jb      short loc_14000834B
0x140008357  cmp     ebx, [rax]
0x140008359  ja      loc_14000857E
0x14000835f  mov     [rax], ebx
0x140008361  cmp     dword ptr [rdi+28h], 0
0x140008365  mov     [rdi+20h], rcx
0x140008369  jz      short loc_1400083B7
0x14000836b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008372  lea     r8, [rsp+1B0h+var_140]
0x140008377  mov     rdx, [rdi]
0x14000837a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008381  mov     rax, [rax+280h]
0x140008388  call    _guard_dispatch_icall
0x14000838d  mov     ebx, eax
0x14000838f  test    eax, eax
0x140008391  jns     short loc_1400083B7
0x140008393  mov     rcx, cs:WPP_GLOBAL_Control
0x14000839a  cmp     rcx, r15
0x14000839d  jz      loc_1400085BE
0x1400083a3  cmp     byte ptr [rcx+29h], 2
0x1400083a7  jb      loc_1400085BE
0x1400083ad  mov     edx, 1Dh
0x1400083b2  jmp     loc_1400082E8
0x1400083b7  mov     ebx, 60h ; '`'
0x1400083bc  lea     rcx, [rbp+0B0h+var_120]; void *
0x1400083c0  mov     r8d, ebx; Size
0x1400083c3  xor     edx, edx; Val
0x1400083c5  call    memset
0x1400083ca  mov     rdx, [rdi]
0x1400083cd  lea     rax, FcEvtIoDeviceControl
0x1400083d4  mov     [rbp+0B0h+var_F8], rax
0x1400083d8  lea     rcx, [rbp+0B0h+var_130]
0x1400083dc  xor     eax, eax
0x1400083de  mov     [rbp+0B0h+var_120], ebx
0x1400083e1  xorps   xmm0, xmm0
0x1400083e4  mov     [rsp+1B0h+var_148], rax
0x1400083e9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400083f0  lea     r9, [rsp+1B0h+var_178]
0x1400083f5  movups  [rsp+1B0h+var_168], xmm0
0x1400083fa  mov     [rbp+0B0h+var_118], 2
0x140008401  lea     r8, [rbp+0B0h+var_120]
0x140008405  movups  [rsp+1B0h+var_178], xmm0
0x14000840a  mov     [rbp+0B0h+var_113], r12b
0x14000840e  mov     [rbp+0B0h+var_11C], r12d
0x140008412  movups  [rsp+1B0h+var_158], xmm0
0x140008417  mov     dword ptr [rsp+1B0h+var_178], 38h ; '8'
0x14000841f  mov     dword ptr [rsp+1B0h+var_168+0Ch], r12d
0x140008424  mov     dword ptr [rsp+1B0h+var_168+8], r12d
0x140008429  mov     rax, [rax+4C0h]
0x140008430  mov     [rsp+1B0h+var_190], rcx
0x140008435  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000843c  call    _guard_dispatch_icall
0x140008441  mov     ebx, eax
0x140008443  test    eax, eax
0x140008445  jns     short loc_14000846B
0x140008447  mov     rcx, cs:WPP_GLOBAL_Control
0x14000844e  cmp     rcx, r15
0x140008451  jz      loc_1400085BE
0x140008457  cmp     byte ptr [rcx+29h], 2
0x14000845b  jb      loc_1400085BE
0x140008461  mov     edx, 1Eh
0x140008466  jmp     loc_1400082E8
0x14000846b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008472  lea     r8, [rdi+8]
0x140008476  xor     eax, eax
0x140008478  lea     rdx, [rsp+1B0h+var_178]
0x14000847d  mov     [rsp+1B0h+var_148], rax
0x140008482  xorps   xmm0, xmm0
0x140008485  mov     rax, [rdi]
0x140008488  movups  [rsp+1B0h+var_168], xmm0
0x14000848d  mov     dword ptr [rsp+1B0h+var_168+8], r12d
0x140008492  movups  [rsp+1B0h+var_158], xmm0
0x140008497  mov     qword ptr [rsp+1B0h+var_158], rax
0x14000849c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400084a3  movups  [rsp+1B0h+var_178], xmm0
0x1400084a8  mov     dword ptr [rsp+1B0h+var_178], 38h ; '8'
0x1400084b0  mov     dword ptr [rsp+1B0h+var_168+0Ch], r12d
0x1400084b5  mov     rax, [rax+68h]
0x1400084b9  call    _guard_dispatch_icall
0x1400084be  mov     ebx, eax
0x1400084c0  test    eax, eax
0x1400084c2  jns     short loc_1400084E8
0x1400084c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084cb  cmp     rcx, r15
0x1400084ce  jz      loc_1400085BE
0x1400084d4  cmp     byte ptr [rcx+29h], 2
0x1400084d8  jb      loc_1400085BE
0x1400084de  mov     edx, 1Fh
0x1400084e3  jmp     loc_1400082E8
0x1400084e8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400084ef  lea     r8, [rdi+10h]
0x1400084f3  xor     eax, eax
0x1400084f5  lea     rdx, [rsp+1B0h+var_178]
0x1400084fa  mov     [rsp+1B0h+var_148], rax
0x1400084ff  xorps   xmm0, xmm0
0x140008502  mov     rax, [rdi]
0x140008505  movups  [rsp+1B0h+var_168], xmm0
0x14000850a  mov     dword ptr [rsp+1B0h+var_168+8], r12d
0x14000850f  movups  [rsp+1B0h+var_158], xmm0
0x140008514  mov     qword ptr [rsp+1B0h+var_158], rax
0x140008519  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008520  movups  [rsp+1B0h+var_178], xmm0
0x140008525  mov     dword ptr [rsp+1B0h+var_178], 38h ; '8'
0x14000852d  mov     dword ptr [rsp+1B0h+var_168+0Ch], r12d
0x140008532  mov     rax, [rax+68h]
0x140008536  call    _guard_dispatch_icall
0x14000853b  mov     ebx, eax
0x14000853d  test    eax, eax
0x14000853f  jns     short loc_14000855D
0x140008541  mov     rcx, cs:WPP_GLOBAL_Control
0x140008548  cmp     rcx, r15
0x14000854b  jz      short loc_1400085BE
0x14000854d  cmp     byte ptr [rcx+29h], 2
0x140008551  jb      short loc_1400085BE
0x140008553  mov     edx, 20h ; ' '
0x140008558  jmp     loc_1400082E8
0x14000855d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008564  mov     rdx, [rdi]
0x140008567  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000856e  mov     rax, [rax+0D8h]
0x140008575  call    _guard_dispatch_icall
0x14000857a  xor     ebx, ebx
0x14000857c  jmp     short loc_1400085BE
0x14000857e  mov     ebx, 0C000000Dh
0x140008583  xor     edx, edx; Tag
0x140008585  call    cs:__imp_ExFreePoolWithTag
0x14000858c  nop     dword ptr [rax+rax+00h]
0x140008591  jmp     short loc_140008598
0x140008593  mov     ebx, 0C0000017h
0x140008598  mov     rcx, cs:WPP_GLOBAL_Control
0x14000859f  cmp     rcx, r15
0x1400085a2  jz      short loc_1400085BE
0x1400085a4  cmp     byte ptr [rcx+29h], 2
0x1400085a8  jb      short loc_1400085BE
0x1400085aa  mov     edx, 1Ch
0x1400085af  mov     r9d, ebx
0x1400085b2  mov     rcx, [rcx+18h]
0x1400085b6  mov     r8, r13
0x1400085b9  call    WPP_SF_d
0x1400085be  mov     eax, ebx
0x1400085c0  mov     rcx, [rbp+0B0h+var_40]
0x1400085c4  xor     rcx, rsp; StackCookie
0x1400085c7  call    __security_check_cookie
0x1400085cc  add     rsp, 188h
0x1400085d3  pop     r15
0x1400085d5  pop     r13
0x1400085d7  pop     r12
0x1400085d9  pop     rdi
0x1400085da  pop     rbx
0x1400085db  pop     rbp
0x1400085dc  retn
```
