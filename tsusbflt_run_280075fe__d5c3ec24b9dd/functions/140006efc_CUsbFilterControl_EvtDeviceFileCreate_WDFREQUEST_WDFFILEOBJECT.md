# CUsbFilterControl::EvtDeviceFileCreate(WDFREQUEST__ *,WDFFILEOBJECT__ *)

- ea: `0x140006efc`
- end: `0x140007115`
- name: `?EvtDeviceFileCreate@CUsbFilterControl@@QEAAXPEAUWDFREQUEST__@@PEAUWDFFILEOBJECT__@@@Z`
- size: `537`
- prototype: `void __fastcall(CUsbFilterControl *__hidden this, struct WDFREQUEST__ *, struct WDFFILEOBJECT__ *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140009440`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x14000620c`
- `0x140006efc`
- `0x1400085e4`
- `0x140008ad8`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000b020`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x140006fba`
- `ntoskrnl!ExUuidCreate` at `0x140006fba`

## pseudocode

```c
void __fastcall CUsbFilterControl::EvtDeviceFileCreate(
        CUsbFilterControl *this,
        struct WDFREQUEST__ *a2,
        struct WDFFILEOBJECT__ *a3)
{
  int UsbEnableMode; // eax
  _DWORD *v7; // rdx
  __int64 *v8; // r9
  __int64 v9; // rcx
  UUID *p_Uuid; // rbx
  UUID *v11; // r15
  __int64 v12; // rax
  CUsbFilterControlFile *v13; // rdi
  int v14; // ebx
  unsigned int *v15; // rsi
  __int64 v16; // rdi
  unsigned int v17; // ebp
  UUID Uuid; // [rsp+20h] [rbp-58h] BYREF

  if ( *((_DWORD *)this + 10) == 3 )
  {
    UsbEnableMode = CUsbFilterControl::QueryUsbEnableMode();
    *((_DWORD *)this + 10) = UsbEnableMode;
    if ( UsbEnableMode == 3 )
    {
      *((_DWORD *)this + 10) = 0;
LABEL_5:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      goto LABEL_8;
    }
    if ( !UsbEnableMode )
      goto LABEL_5;
  }
LABEL_8:
  v7 = (_DWORD *)*((_QWORD *)this + 4);
  v8 = qword_14000D7A0;
  v9 = 0;
  Uuid = 0;
  if ( !*v7 )
    goto LABEL_13;
  while ( *((_BYTE *)v7 + v9 + 4) )
  {
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= *v7 )
      goto LABEL_13;
  }
  *((_BYTE *)v7 + v9 + 4) = 1;
  p_Uuid = (UUID *)&qword_14000D7A0[2 * (unsigned int)v9];
  if ( !p_Uuid )
  {
LABEL_13:
    if ( ExUuidCreate(&Uuid) < 0 )
    {
      v14 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      goto LABEL_31;
    }
    p_Uuid = &Uuid;
  }
  v11 = p_Uuid;
  v12 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFFILEOBJECT__ *, __int64 *, __int64 *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a3,
          off_14000F178,
          v8,
          *(_QWORD *)&Uuid.Data1,
          *(_QWORD *)Uuid.Data4);
  v13 = (CUsbFilterControlFile *)v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    *(_QWORD *)(v12 + 8) = 0;
    *(_BYTE *)(v12 + 32) = 0;
    v14 = CUsbFilterControlFile::Initialize((CUsbFilterControlFile *)v12, p_Uuid);
    if ( v14 >= 0 )
    {
      v14 = 0;
      goto LABEL_31;
    }
    CUsbFilterControlFile::~CUsbFilterControlFile(v13);
  }
  else
  {
    v14 = -1073741801;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, (unsigned int)v14);
  v15 = (unsigned int *)*((_QWORD *)this + 4);
  v16 = 0;
  v17 = *v15;
  if ( *v15 )
  {
    while ( memcmp(v11, &qword_14000D7A0[2 * (unsigned int)v16], 0x10u) )
    {
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= v17 )
        goto LABEL_31;
    }
    *((_BYTE *)v15 + v16 + 4) = 0;
  }
LABEL_31:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)v14);
}

```

## disassembly

```asm
0x140006efc  push    rbx
0x140006efe  push    rbp
0x140006eff  push    rsi
0x140006f00  push    rdi
0x140006f01  push    r12
0x140006f03  push    r14
0x140006f05  push    r15
0x140006f07  sub     rsp, 40h
0x140006f0b  mov     rax, cs:__security_cookie
0x140006f12  xor     rax, rsp
0x140006f15  mov     [rsp+78h+var_48], rax
0x140006f1a  cmp     dword ptr [rcx+28h], 3
0x140006f1e  lea     r14, WPP_GLOBAL_Control
0x140006f25  mov     rdi, r8
0x140006f28  mov     r12, rdx
0x140006f2b  mov     rsi, rcx
0x140006f2e  mov     bpl, 2
0x140006f31  jnz     short loc_140006F74
0x140006f33  call    ?QueryUsbEnableMode@CUsbFilterControl@@AEAA?AW4_USB_MODE@@XZ; CUsbFilterControl::QueryUsbEnableMode(void)
0x140006f38  mov     [rsi+28h], eax
0x140006f3b  cmp     eax, 3
0x140006f3e  jnz     short loc_140006F49
0x140006f40  mov     dword ptr [rsi+28h], 0
0x140006f47  jmp     short loc_140006F4D
0x140006f49  test    eax, eax
0x140006f4b  jnz     short loc_140006F74
0x140006f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f54  cmp     rcx, r14
0x140006f57  jz      short loc_140006F74
0x140006f59  cmp     [rcx+29h], bpl
0x140006f5d  jb      short loc_140006F74
0x140006f5f  mov     rcx, [rcx+18h]
0x140006f63  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006f6a  mov     edx, 24h ; '$'
0x140006f6f  call    WPP_SF_
0x140006f74  mov     rdx, [rsi+20h]
0x140006f78  lea     r9, qword_14000D7A0
0x140006f7f  xor     ebx, ebx
0x140006f81  xor     ecx, ecx
0x140006f83  xorps   xmm0, xmm0
0x140006f86  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x140006f8b  mov     r8d, [rdx]
0x140006f8e  test    r8d, r8d
0x140006f91  jz      short loc_140006FB5
0x140006f93  mov     eax, ecx
0x140006f95  cmp     [rcx+rdx+4], bl
0x140006f99  jz      short loc_140006FA4
0x140006f9b  inc     ecx
0x140006f9d  cmp     ecx, r8d
0x140006fa0  jb      short loc_140006F93
0x140006fa2  jmp     short loc_140006FB5
0x140006fa4  add     rax, rax
0x140006fa7  mov     byte ptr [rcx+rdx+4], 1
0x140006fac  lea     rbx, [r9+rax*8]
0x140006fb0  test    rbx, rbx
0x140006fb3  jnz     short loc_140006FCF
0x140006fb5  lea     rcx, [rsp+78h+Uuid]; Uuid
0x140006fba  call    cs:__imp_ExUuidCreate
0x140006fc1  nop     dword ptr [rax+rax+00h]
0x140006fc6  test    eax, eax
0x140006fc8  js      short loc_140007029
0x140006fca  lea     rbx, [rsp+78h+Uuid]
0x140006fcf  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006fd6  mov     rdx, rdi
0x140006fd9  mov     r8, cs:off_14000F178
0x140006fe0  mov     r15, rbx
0x140006fe3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006fea  mov     rax, [rax+650h]
0x140006ff1  call    _guard_dispatch_icall
0x140006ff6  mov     rdi, rax
0x140006ff9  test    rax, rax
0x140006ffc  jz      short loc_14000706E
0x140006ffe  mov     rdx, rbx; struct _GUID *
0x140007001  mov     qword ptr [rax], 0
0x140007008  mov     rcx, rax; this
0x14000700b  mov     qword ptr [rax+8], 0
0x140007013  mov     byte ptr [rax+20h], 0
0x140007017  call    ?Initialize@CUsbFilterControlFile@@AEAAJPEBU_GUID@@@Z; CUsbFilterControlFile::Initialize(_GUID const *)
0x14000701c  mov     ebx, eax
0x14000701e  test    eax, eax
0x140007020  js      short loc_140007064
0x140007022  xor     ebx, ebx
0x140007024  jmp     loc_1400070D8
0x140007029  test    rbx, rbx
0x14000702c  jnz     short loc_140006FCF
0x14000702e  mov     ebx, 0C000009Ah
0x140007033  mov     rcx, cs:WPP_GLOBAL_Control
0x14000703a  cmp     rcx, r14
0x14000703d  jz      loc_1400070D8
0x140007043  cmp     [rcx+29h], bpl
0x140007047  jb      loc_1400070D8
0x14000704d  mov     rcx, [rcx+18h]
0x140007051  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140007058  mov     edx, 25h ; '%'
0x14000705d  call    WPP_SF_
0x140007062  jmp     short loc_1400070D8
0x140007064  mov     rcx, rdi; this
0x140007067  call    ??1CUsbFilterControlFile@@QEAA@XZ; CUsbFilterControlFile::~CUsbFilterControlFile(void)
0x14000706c  jmp     short loc_140007073
0x14000706e  mov     ebx, 0C0000017h
0x140007073  mov     rcx, cs:WPP_GLOBAL_Control
0x14000707a  cmp     rcx, r14
0x14000707d  jz      short loc_14000709D
0x14000707f  cmp     [rcx+29h], bpl
0x140007083  jb      short loc_14000709D
0x140007085  mov     rcx, [rcx+18h]
0x140007089  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140007090  mov     edx, 26h ; '&'
0x140007095  mov     r9d, ebx
0x140007098  call    WPP_SF_d
0x14000709d  mov     rsi, [rsi+20h]
0x1400070a1  xor     edi, edi
0x1400070a3  mov     ebp, [rsi]
0x1400070a5  test    ebp, ebp
0x1400070a7  jz      short loc_1400070D8
0x1400070a9  lea     rax, qword_14000D7A0
0x1400070b0  mov     edx, edi
0x1400070b2  shl     rdx, 4
0x1400070b6  mov     r8d, 10h; Size
0x1400070bc  add     rdx, rax; Buf2
0x1400070bf  mov     rcx, r15; Buf1
0x1400070c2  call    memcmp
0x1400070c7  test    eax, eax
0x1400070c9  jz      short loc_1400070D3
0x1400070cb  inc     edi
0x1400070cd  cmp     edi, ebp
0x1400070cf  jb      short loc_1400070A9
0x1400070d1  jmp     short loc_1400070D8
0x1400070d3  mov     byte ptr [rdi+rsi+4], 0
0x1400070d8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400070df  mov     r8d, ebx
0x1400070e2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400070e9  mov     rdx, r12
0x1400070ec  mov     rax, [rax+838h]
0x1400070f3  call    _guard_dispatch_icall
0x1400070f8  mov     rcx, [rsp+78h+var_48]
0x1400070fd  xor     rcx, rsp; StackCookie
0x140007100  call    __security_check_cookie
0x140007105  add     rsp, 40h
0x140007109  pop     r15
0x14000710b  pop     r14
0x14000710d  pop     r12
0x14000710f  pop     rdi
0x140007110  pop     rsi
0x140007111  pop     rbp
0x140007112  pop     rbx
0x140007113  retn
```
