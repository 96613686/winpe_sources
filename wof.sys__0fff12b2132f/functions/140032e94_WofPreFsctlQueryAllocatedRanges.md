# WofPreFsctlQueryAllocatedRanges

- ea: `0x140032e94`
- end: `0x14003316f`
- name: `WofPreFsctlQueryAllocatedRanges`
- size: `731`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400346f0`

## callees

- `0x14000da78`
- `0x14000dc88`
- `0x140011560`
- `0x140011590`
- `0x140011640`
- `0x140023150`
- `0x140032e94`
- `0x140034f50`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140032fed`
- `ntoskrnl!ProbeForRead` at `0x140032fed`
- `ntoskrnl!ProbeForWrite` at `0x140033005`
- `ntoskrnl!ProbeForWrite` at `0x140033005`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400330f4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033125`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400330f4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140033125`
- `FLTMGR!FltGetStreamContext` at `0x140032ef7`
- `FLTMGR!FltGetStreamContext` at `0x140032ef7`
- `FLTMGR!FltReleaseContext` at `0x140033108`
- `FLTMGR!FltReleaseContext` at `0x140033136`
- `FLTMGR!FltReleaseContext` at `0x140033108`
- `FLTMGR!FltReleaseContext` at `0x140033136`

## pseudocode

```c
__int64 __fastcall WofPreFsctlQueryAllocatedRanges(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // edi
  __int64 v6; // rax
  _QWORD *v7; // r14
  SIZE_T v8; // r15
  void *v9; // rdi
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  _BYTE v13[8]; // [rsp+30h] [rbp-68h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-60h] BYREF
  int v15; // [rsp+40h] [rbp-58h]
  PEX_RUNDOWN_REF RunRef; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v18; // [rsp+60h] [rbp-38h] BYREF

  v17[1] = a1;
  Context = 0;
  v13[0] = 0;
  v17[0] = 0;
  v18 = 0;
  RunRef = 0;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) < 0 )
    return 1;
  if ( (int)WofIsDataInFilesystemEx(Context, a2, v13, &RunRef) < 0 || v13[0] )
  {
    if ( RunRef )
      ExReleaseRundownProtection(RunRef);
    FltReleaseContext(Context);
    return 1;
  }
  *(_QWORD *)(a1 + 32) = 0;
  v5 = ((__int64 (__fastcall *)(char *, _QWORD *, _QWORD))qword_14001A280[53 * *((unsigned int *)Context + 3)])(
         (char *)Context + 64,
         v17,
         0);
  if ( v5 >= 0 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    v7 = *(_QWORD **)(v6 + 56);
    v8 = *(unsigned int *)(v6 + 24);
    v9 = *(void **)(v6 + 48);
    if ( *(_DWORD *)(v6 + 32) < 0x10u )
      goto LABEL_8;
    if ( *(_BYTE *)(a1 + 80)
      && (ProbeForRead(*(volatile void **)(v6 + 48), *(unsigned int *)(v6 + 32), 4u),
          ProbeForWrite(v7, v8, 4u),
          *(_BYTE *)(a1 + 80)) )
    {
      RtlCopyFromUser(&v18, v9, 0x10u);
    }
    else
    {
      RtlCopyVolatileMemory(&v18, v9, 0x10u);
    }
    if ( (__int64)v18 < 0
      || (v10 = *((_QWORD *)&v18 + 1), v18 < 0)
      || *((__int64 *)&v18 + 1) > 0x7FFFFFFFFFFFFFFFLL - (__int64)v18 )
    {
LABEL_8:
      v5 = -1073741811;
    }
    else if ( *((_QWORD *)&v18 + 1) && (__int64)v18 <= v17[0] )
    {
      if ( v17[0] - (_QWORD)v18 < *((__int64 *)&v18 + 1) )
        v10 = v17[0] - v18;
      *((_QWORD *)&v18 + 1) = v10;
      if ( (unsigned int)v8 >= 0x10 )
      {
        if ( *(_BYTE *)(a1 + 80) )
          RtlWriteULong64ToUser(v7, v18);
        else
          *v7 = v18;
        v11 = v7 + 1;
        if ( *(_BYTE *)(a1 + 80) )
          RtlWriteULong64ToUser(v11, *((_QWORD *)&v18 + 1));
        else
          *v11 = *((_QWORD *)&v18 + 1);
        *(_QWORD *)(a1 + 32) = 16;
        v5 = 0;
        v15 = 0;
      }
      else
      {
        v5 = -1073741789;
      }
    }
    else
    {
      v5 = 0;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      7,
      27,
      (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids,
      v5);
  }
  if ( RunRef )
    ExReleaseRundownProtection(RunRef);
  *(_DWORD *)(a1 + 24) = v5;
  FltReleaseContext(Context);
  return 4;
}

```

## disassembly

```asm
0x140032e94  mov     r11, rsp
0x140032e97  mov     [r11+18h], rsi
0x140032e9b  mov     [r11+20h], rdi
0x140032e9f  push    r12
0x140032ea1  push    r14
0x140032ea3  push    r15
0x140032ea5  sub     rsp, 80h
0x140032eac  mov     rax, cs:__security_cookie
0x140032eb3  xor     rax, rsp
0x140032eb6  mov     [rsp+98h+var_28], rax
0x140032ebb  mov     rdi, rdx
0x140032ebe  mov     rsi, rcx
0x140032ec1  mov     [rsp+98h+var_40], rcx
0x140032ec6  mov     qword ptr [r11-60h], 0
0x140032ece  mov     [rsp+98h+var_68], 0
0x140032ed3  mov     qword ptr [r11-48h], 0
0x140032edb  xorps   xmm0, xmm0
0x140032ede  movups  [rsp+98h+var_38], xmm0
0x140032ee3  mov     qword ptr [r11-50h], 0
0x140032eeb  lea     r8, [r11-60h]; Context
0x140032eef  mov     rdx, [rdx+20h]; FileObject
0x140032ef3  mov     rcx, [rdi+18h]; Instance
0x140032ef7  call    cs:__imp_FltGetStreamContext
0x140032efe  nop     dword ptr [rax+rax+00h]
0x140032f03  test    eax, eax
0x140032f05  js      loc_140033142
0x140032f0b  lea     r9, [rsp+98h+RunRef]
0x140032f10  lea     r8, [rsp+98h+var_68]
0x140032f15  mov     rdx, rdi
0x140032f18  mov     rcx, [rsp+98h+Context]
0x140032f1d  call    WofIsDataInFilesystemEx
0x140032f22  test    eax, eax
0x140032f24  js      loc_14003311B
0x140032f2a  cmp     [rsp+98h+var_68], 0
0x140032f2f  jnz     loc_14003311B
0x140032f35  mov     qword ptr [rsi+20h], 0
0x140032f3d  mov     rcx, [rsp+98h+Context]
0x140032f42  mov     eax, [rcx+0Ch]
0x140032f45  imul    rdx, rax, 1A8h
0x140032f4c  lea     rax, qword_14001A280
0x140032f53  add     rcx, 40h ; '@'
0x140032f57  mov     rax, [rdx+rax]
0x140032f5b  xor     r8d, r8d
0x140032f5e  lea     rdx, [rsp+98h+var_48]
0x140032f63  call    _guard_dispatch_icall
0x140032f68  mov     edi, eax
0x140032f6a  test    eax, eax
0x140032f6c  jns     short loc_140032FB3
0x140032f6e  lea     rax, WPP_RECORDER_INITIALIZED
0x140032f75  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032f7c  jz      loc_1400330EA
0x140032f82  mov     r9d, 1Bh
0x140032f88  mov     [rsp+98h+var_70], edi
0x140032f8c  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x140032f93  mov     [rsp+98h+var_78], rax
0x140032f98  lea     r8d, [r9-14h]
0x140032f9c  mov     dl, 2
0x140032f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fa5  mov     rcx, [rcx+40h]
0x140032fa9  call    WPP_RECORDER_SF_d
0x140032fae  jmp     loc_1400330EA
0x140032fb3  mov     rax, [rsi+10h]
0x140032fb7  mov     r14, [rax+38h]
0x140032fbb  mov     r15d, [rax+18h]
0x140032fbf  mov     rdi, [rax+30h]
0x140032fc3  mov     ecx, [rax+20h]
0x140032fc6  mov     r12d, 10h
0x140032fcc  cmp     ecx, r12d
0x140032fcf  jnb     short loc_140032FDB
0x140032fd1  mov     edi, 0C000000Dh
0x140032fd6  jmp     loc_1400330EA
0x140032fdb  cmp     byte ptr [rsi+50h], 0
0x140032fdf  jz      short loc_140033029
0x140032fe1  mov     rdx, rcx; Length
0x140032fe4  mov     r8d, 4; Alignment
0x140032fea  mov     rcx, rdi; Address
0x140032fed  call    cs:__imp_ProbeForRead
0x140032ff4  nop     dword ptr [rax+rax+00h]
0x140032ff9  mov     rdx, r15; Length
0x140032ffc  mov     r8d, 4; Alignment
0x140033002  mov     rcx, r14; Address
0x140033005  call    cs:__imp_ProbeForWrite
0x14003300c  nop     dword ptr [rax+rax+00h]
0x140033011  cmp     byte ptr [rsi+50h], 0
0x140033015  jz      short loc_140033029
0x140033017  mov     r8, r12; Size
0x14003301a  mov     rdx, rdi; Src
0x14003301d  lea     rcx, [rsp+98h+var_38]; void *
0x140033022  call    RtlCopyFromUser
0x140033027  jmp     short loc_14003303A
0x140033029  mov     r8, r12; Size
0x14003302c  mov     rdx, rdi; Src
0x14003302f  lea     rcx, [rsp+98h+var_38]; void *
0x140033034  call    RtlCopyVolatileMemory
0x140033039  nop
0x14003303a  mov     rcx, qword ptr [rsp+98h+var_38]
0x14003303f  test    rcx, rcx
0x140033042  js      short loc_140032FD1
0x140033044  mov     rdx, qword ptr [rsp+98h+var_38+8]
0x140033049  test    rdx, rdx
0x14003304c  js      short loc_140032FD1
0x14003304e  mov     rax, 7FFFFFFFFFFFFFFFh
0x140033058  sub     rax, rcx
0x14003305b  cmp     rdx, rax
0x14003305e  jg      loc_140032FD1
0x140033064  test    rdx, rdx
0x140033067  jz      short loc_1400330DC
0x140033069  mov     rax, [rsp+98h+var_48]
0x14003306e  cmp     rcx, rax
0x140033071  jg      short loc_1400330DC
0x140033073  sub     rax, rcx
0x140033076  cmp     rax, rdx
0x140033079  cmovl   rdx, rax
0x14003307d  mov     qword ptr [rsp+98h+var_38+8], rdx
0x140033082  cmp     r15d, r12d
0x140033085  jnb     short loc_14003308E
0x140033087  mov     edi, 0C0000023h
0x14003308c  jmp     short loc_1400330EA
0x14003308e  cmp     byte ptr [rsi+50h], 0
0x140033092  jz      short loc_1400330A1
0x140033094  mov     rdx, rcx
0x140033097  mov     rcx, r14
0x14003309a  call    RtlWriteULong64ToUser
0x14003309f  jmp     short loc_1400330A4
0x1400330a1  mov     [r14], rcx
0x1400330a4  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1400330a9  lea     rcx, [r14+8]
0x1400330ad  cmp     byte ptr [rsi+50h], 0
0x1400330b1  jz      short loc_1400330BD
0x1400330b3  mov     rdx, rax
0x1400330b6  call    RtlWriteULong64ToUser
0x1400330bb  jmp     short loc_1400330C0
0x1400330bd  mov     [rcx], rax
0x1400330c0  mov     [rsi+20h], r12
0x1400330c4  xor     edi, edi
0x1400330c6  mov     [rsp+98h+var_58], edi
0x1400330ca  jmp     short loc_1400330EA
0x1400330cc  mov     edi, 0C00000E8h
0x1400330d1  mov     [rsp+98h+var_58], edi
0x1400330d5  mov     rsi, [rsp+98h+var_40]
0x1400330da  jmp     short loc_1400330EA
0x1400330dc  xor     edi, edi
0x1400330de  jmp     short loc_1400330EA
0x1400330e0  mov     edi, 0C00000E8h
0x1400330e5  mov     rsi, [rsp+98h+var_40]
0x1400330ea  mov     rcx, [rsp+98h+RunRef]; RunRef
0x1400330ef  test    rcx, rcx
0x1400330f2  jz      short loc_140033100
0x1400330f4  call    cs:__imp_ExReleaseRundownProtection
0x1400330fb  nop     dword ptr [rax+rax+00h]
0x140033100  mov     [rsi+18h], edi
0x140033103  mov     rcx, [rsp+98h+Context]; Context
0x140033108  call    cs:__imp_FltReleaseContext
0x14003310f  nop     dword ptr [rax+rax+00h]
0x140033114  mov     eax, 4
0x140033119  jmp     short loc_140033147
0x14003311b  mov     rcx, [rsp+98h+RunRef]; RunRef
0x140033120  test    rcx, rcx
0x140033123  jz      short loc_140033131
0x140033125  call    cs:__imp_ExReleaseRundownProtection
0x14003312c  nop     dword ptr [rax+rax+00h]
0x140033131  mov     rcx, [rsp+98h+Context]; Context
0x140033136  call    cs:__imp_FltReleaseContext
0x14003313d  nop     dword ptr [rax+rax+00h]
0x140033142  mov     eax, 1
0x140033147  mov     rcx, [rsp+98h+var_28]
0x14003314c  xor     rcx, rsp; StackCookie
0x14003314f  call    __security_check_cookie
0x140033154  lea     r11, [rsp+98h+var_18]
0x14003315c  mov     rsi, [r11+30h]
0x140033160  mov     rdi, [r11+38h]
0x140033164  mov     rsp, r11
0x140033167  pop     r15
0x140033169  pop     r14
0x14003316b  pop     r12
0x14003316d  retn
```
