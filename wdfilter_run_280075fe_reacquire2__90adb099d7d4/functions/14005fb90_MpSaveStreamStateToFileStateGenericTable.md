# MpSaveStreamStateToFileStateGenericTable

- ea: `0x14005fb90`
- end: `0x140060232`
- name: `MpSaveStreamStateToFileStateGenericTable`
- size: `1698`
- prototype: `__int64 __fastcall(int, int, int, int, CLONG BufferSize, PVOID Buffer)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x14005fa00`
- `0x14005fa84`
- `0x14005fb08`

## callees

- `0x1400018a4`
- `0x140003d20`
- `0x1400049dc`
- `0x140009b14`
- `0x14000f604`
- `0x14000f6fc`
- `0x14000f808`
- `0x140011890`
- `0x1400118d0`
- `0x14005fb90`
- `0x1400603dc`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14005fe7b`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14005fe7b`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14005fd36`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14005fd36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060080`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008cb24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140060080`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008cb24`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060074`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008cb18`
- `ntoskrnl!ExReleaseResourceLite` at `0x140060074`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008cb18`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fcdd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fcdd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fcc8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fcc8`

## pseudocode

```c
void __fastcall MpSaveStreamStateToFileStateGenericTable(
        __int64 a1,
        unsigned int a2,
        char a3,
        unsigned __int8 (__fastcall *a4)(__int64, _QWORD, _DWORD *),
        CLONG BufferSize,
        _DWORD *Buffer)
{
  __int64 v9; // rdx
  int v10; // eax
  PDEVICE_OBJECT v11; // rcx
  unsigned int *v12; // r9
  unsigned int v13; // r15d
  char v14; // r8
  __int64 v15; // rdi
  __int64 v16; // rdi
  _QWORD *inserted; // rax
  int v18; // r8d
  _QWORD *v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  _QWORD *v27; // rsi
  __int64 v28; // r15
  _QWORD *v29; // rax
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  unsigned __int8 NewElement[8]; // [rsp+48h] [rbp-40h] BYREF

  NewElement[0] = 0;
  if ( !a4 || !a1 || !Buffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids);
    return;
  }
  v9 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v9 + 120) != a2 )
    return;
  v10 = *(_DWORD *)(a1 + 48);
  if ( (v10 & 0x40) == 0 )
  {
    if ( (v10 & 2) != 0 && (a3 & 1) != 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v32 = 20;
        goto LABEL_82;
      }
      return;
    }
    v12 = (unsigned int *)(a1 + 32);
    if ( a1 == -32 || !v9 )
      goto LABEL_69;
    if ( *v12 == 5 && (*(_DWORD *)(MpData + 868) & 0x8000) == 0 )
    {
      v13 = 5;
      goto LABEL_14;
    }
    if ( *(_DWORD *)(a1 + 36) == *(_DWORD *)(v9 + 144) )
      v13 = *v12;
    else
LABEL_69:
      v13 = 0;
LABEL_14:
    if ( v13 - 2 > 3 && v13 != 7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Di(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids,
          v13,
          *(_QWORD *)(a1 + 168));
      return;
    }
    if ( (a3 & 2) == 0 && v13 != 3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_iZDD(WPP_GLOBAL_Control->AttachedDevice, 22, a3, *(_QWORD *)(a1 + 168), a1 + 240, v13, a3);
      return;
    }
    _mm_lfence();
    *(_QWORD *)Buffer = *(_QWORD *)(a1 + 168);
    Buffer[6] = BufferSize;
    if ( !a4(a1, BufferSize, Buffer) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_iZDD(WPP_GLOBAL_Control->AttachedDevice, 23, v14, *(_QWORD *)(a1 + 168), a1 + 240, v13, a2);
      return;
    }
    v15 = *(_QWORD *)(a1 + 8);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v15 + 184), 1u);
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL)
      || (v16 = *(_QWORD *)(a1 + 8),
          *(_QWORD *)(v16 + 168) = MpAllocateAndInitFileStateGenericTable(),
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL)) )
    {
      _mm_lfence();
      inserted = RtlInsertElementGenericTable(
                   (PRTL_GENERIC_TABLE)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL) + 16LL),
                   Buffer,
                   BufferSize,
                   NewElement);
      v19 = inserted;
      if ( inserted )
      {
        if ( NewElement[0] )
        {
          ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 180LL);
          switch ( a2 )
          {
            case 0x1Bu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2928));
              break;
            case 0x1Cu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2964));
              break;
            case 2u:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2892));
              break;
          }
        }
        else
        {
          _mm_lfence();
          v29 = inserted + 1;
          v30 = *v29;
          v31 = (_QWORD *)v29[1];
          if ( *(_QWORD **)(*v29 + 8LL) != v29 || (_QWORD *)*v31 != v29 )
LABEL_26:
            __fastfail(3u);
          *v31 = v30;
          *(_QWORD *)(v30 + 8) = v31;
          switch ( a2 )
          {
            case 0x1Bu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2932));
              break;
            case 0x1Cu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2968));
              break;
            case 2u:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2896));
              break;
          }
        }
        v20 = v19 + 1;
        v21 = *(_QWORD *)(a1 + 8) + 152LL;
        v22 = *(_QWORD *)v21;
        if ( *(_QWORD *)(*(_QWORD *)v21 + 8LL) != v21 )
          goto LABEL_26;
        *v20 = v22;
        v19[2] = v21;
        *(_QWORD *)(v22 + 8) = v20;
        *(_QWORD *)v21 = v20;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_iZDDd(
            WPP_GLOBAL_Control->AttachedDevice,
            v22,
            v18,
            *v19,
            a1 + 240,
            v13,
            a2,
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 180LL));
        }
        while ( 1 )
        {
          v23 = *(_QWORD *)(a1 + 8);
          if ( *(_DWORD *)(v23 + 180) <= *(_DWORD *)(v23 + 176) )
            break;
          v24 = v23 + 152;
          v25 = *(_QWORD **)(v24 + 8);
          v26 = (_QWORD *)v25[1];
          if ( *v25 != v24 || (_QWORD *)*v26 != v25 )
            goto LABEL_26;
          *(_QWORD *)(v24 + 8) = v26;
          *v26 = v24;
          v27 = v25 - 1;
          --*(_DWORD *)(*(_QWORD *)(a1 + 8) + 180LL);
          v28 = *(v25 - 1);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_id(
              WPP_GLOBAL_Control->AttachedDevice,
              v26,
              *(unsigned int *)(*(_QWORD *)(a1 + 8) + 180LL),
              v28,
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 180LL));
          }
          if ( !RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 168LL) + 16LL), v27)
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids, v28);
          }
          switch ( a2 )
          {
            case 0x1Bu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2948));
              break;
            case 0x1Cu:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2984));
              break;
            case 2u:
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 2912));
              break;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_iZDD(WPP_GLOBAL_Control->AttachedDevice, 25, (_BYTE)v18, *(_QWORD *)(a1 + 168), a1 + 240, v13, a2);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids, a2);
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 8) + 184LL));
    KeLeaveCriticalRegion();
    return;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    v32 = 19;
LABEL_82:
    WPP_SF_q(v11->AttachedDevice, v32, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids, *(_QWORD *)(a1 + 168));
  }
}

```

## disassembly

```asm
0x14005fb90  mov     [rsp+arg_10], rbx
0x14005fb95  push    rsi
0x14005fb96  push    rdi
0x14005fb97  push    r12
0x14005fb99  push    r14
0x14005fb9b  push    r15
0x14005fb9d  sub     rsp, 60h
0x14005fba1  mov     rax, cs:__security_cookie
0x14005fba8  xor     rax, rsp
0x14005fbab  mov     [rsp+88h+var_38], rax
0x14005fbb0  mov     r10, r9
0x14005fbb3  mov     r14d, edx
0x14005fbb6  mov     rbx, rcx
0x14005fbb9  mov     [rsp+88h+var_48], rcx
0x14005fbbe  mov     r12d, [rsp+88h+BufferSize]
0x14005fbc6  mov     rsi, [rsp+88h+Buffer]
0x14005fbce  mov     [rsp+88h+NewElement], 0
0x14005fbd3  test    r9, r9
0x14005fbd6  jz      loc_1400600EE
0x14005fbdc  test    rcx, rcx
0x14005fbdf  jz      loc_1400600EE
0x14005fbe5  test    rsi, rsi
0x14005fbe8  jz      loc_1400600EE
0x14005fbee  mov     rdx, [rcx+8]
0x14005fbf2  cmp     [rdx+78h], r14d
0x14005fbf6  jnz     short loc_14005FC2A
0x14005fbf8  mov     eax, [rcx+30h]
0x14005fbfb  test    al, 40h
0x14005fbfd  jnz     loc_140060165
0x14005fc03  test    al, 2
0x14005fc05  setnz   cl
0x14005fc08  test    r8b, 1
0x14005fc0c  setnz   al
0x14005fc0f  test    al, cl
0x14005fc11  jz      short loc_14005FC4D
0x14005fc13  lea     rdi, WPP_GLOBAL_Control
0x14005fc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fc21  cmp     rcx, rdi
0x14005fc24  jnz     loc_1400601D1
0x14005fc2a  mov     rcx, [rsp+88h+var_38]
0x14005fc2f  xor     rcx, rsp; StackCookie
0x14005fc32  call    __security_check_cookie
0x14005fc37  mov     rbx, [rsp+88h+arg_10]
0x14005fc3f  add     rsp, 60h
0x14005fc43  pop     r15
0x14005fc45  pop     r14
0x14005fc47  pop     r12
0x14005fc49  pop     rdi
0x14005fc4a  pop     rsi
0x14005fc4b  retn
0x14005fc4d  lea     r9, [rbx+20h]
0x14005fc51  test    r9, r9
0x14005fc54  jz      loc_1400600E6
0x14005fc5a  test    rdx, rdx
0x14005fc5d  jz      loc_1400600E6
0x14005fc63  cmp     dword ptr [r9], 5
0x14005fc67  jz      loc_14006018E
0x14005fc6d  mov     ecx, [r9+4]
0x14005fc71  mov     eax, [rdx+90h]
0x14005fc77  cmp     ecx, eax
0x14005fc79  jnz     loc_1400600E6
0x14005fc7f  mov     r15d, [r9]
0x14005fc82  lea     eax, [r15-2]
0x14005fc86  cmp     eax, 3
0x14005fc89  ja      loc_140060091
0x14005fc8f  test    r8b, 2
0x14005fc93  jz      loc_14006012A
0x14005fc99  lfence
0x14005fc9c  mov     rax, [rbx+0A8h]
0x14005fca3  mov     [rsi], rax
0x14005fca6  mov     [rsi+18h], r12d
0x14005fcaa  mov     r8, rsi
0x14005fcad  mov     edx, r12d
0x14005fcb0  mov     rcx, rbx
0x14005fcb3  mov     rax, r10
0x14005fcb6  call    cs:__guard_dispatch_icall_fptr
0x14005fcbc  test    al, al
0x14005fcbe  jz      loc_14006020E
0x14005fcc4  mov     rdi, [rbx+8]
0x14005fcc8  call    cs:__imp_KeEnterCriticalRegion
0x14005fccf  nop     dword ptr [rax+rax+00h]
0x14005fcd4  mov     dl, 1; Wait
0x14005fcd6  lea     rcx, [rdi+0B8h]; Resource
0x14005fcdd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005fce4  nop     dword ptr [rax+rax+00h]
0x14005fce9  nop
0x14005fcea  mov     rax, [rbx+8]
0x14005fcee  cmp     qword ptr [rax+0A8h], 0
0x14005fcf6  jnz     short loc_14005FD19
0x14005fcf8  mov     rdi, rax
0x14005fcfb  call    MpAllocateAndInitFileStateGenericTable
0x14005fd00  mov     [rdi+0A8h], rax
0x14005fd07  mov     rax, [rbx+8]
0x14005fd0b  cmp     qword ptr [rax+0A8h], 0
0x14005fd13  jz      loc_14005FF68
0x14005fd19  lfence
0x14005fd1c  mov     rax, [rbx+8]
0x14005fd20  mov     rcx, [rax+0A8h]
0x14005fd27  add     rcx, 10h; Table
0x14005fd2b  lea     r9, [rsp+88h+NewElement]; NewElement
0x14005fd30  mov     r8d, r12d; BufferSize
0x14005fd33  mov     rdx, rsi; Buffer
0x14005fd36  call    cs:__imp_RtlInsertElementGenericTable
0x14005fd3d  nop     dword ptr [rax+rax+00h]
0x14005fd42  mov     r9, rax
0x14005fd45  test    rax, rax
0x14005fd48  jz      loc_14005FF03
0x14005fd4e  cmp     [rsp+88h+NewElement], 0
0x14005fd53  jz      loc_14005FFA7
0x14005fd59  mov     rax, [rbx+8]
0x14005fd5d  inc     dword ptr [rax+0B4h]
0x14005fd63  cmp     r14d, 1Bh
0x14005fd67  jz      loc_14005FEF0
0x14005fd6d  cmp     r14d, 1Ch
0x14005fd71  jz      loc_14005FF55
0x14005fd77  cmp     r14d, 2
0x14005fd7b  jnz     short loc_14005FD8B
0x14005fd7d  mov     rax, cs:MpData
0x14005fd84  lock inc dword ptr [rax+0B4Ch]
0x14005fd8b  lea     rcx, [r9+8]
0x14005fd8f  mov     rax, [rbx+8]
0x14005fd93  add     rax, 98h
0x14005fd99  mov     rdx, [rax]
0x14005fd9c  cmp     [rdx+8], rax
0x14005fda0  jz      short loc_14005FDA9
0x14005fda2  mov     ecx, 3
0x14005fda7  int     29h; Win8: RtlFailFast(ecx)
0x14005fda9  mov     [rcx], rdx
0x14005fdac  mov     [rcx+8], rax
0x14005fdb0  mov     [rdx+8], rcx
0x14005fdb4  mov     [rax], rcx
0x14005fdb7  lea     rdi, WPP_GLOBAL_Control
0x14005fdbe  mov     rax, cs:WPP_GLOBAL_Control
0x14005fdc5  cmp     rax, rdi
0x14005fdc8  jnz     short loc_14005FDE1
0x14005fdca  mov     rcx, [rbx+8]
0x14005fdce  mov     eax, [rcx+0B0h]
0x14005fdd4  cmp     [rcx+0B4h], eax
0x14005fdda  ja      short loc_14005FE24
0x14005fddc  jmp     loc_140060069
0x14005fde1  mov     eax, [rax+2Ch]
0x14005fde4  test    al, 4
0x14005fde6  jz      short loc_14005FDCA
0x14005fde8  lfence
0x14005fdeb  mov     rax, [rbx+8]
0x14005fdef  lea     rcx, [rbx+0F0h]
0x14005fdf6  mov     eax, [rax+0B4h]
0x14005fdfc  mov     [rsp+88h+var_50], eax
0x14005fe00  mov     [rsp+88h+var_58], r14d
0x14005fe05  mov     [rsp+88h+var_60], r15d
0x14005fe0a  mov     [rsp+88h+var_68], rcx
0x14005fe0f  mov     r9, [r9]
0x14005fe12  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe19  mov     rcx, [rcx+18h]
0x14005fe1d  call    WPP_SF_iZDDd
0x14005fe22  jmp     short loc_14005FDCA
0x14005fe24  add     rcx, 98h
0x14005fe2b  mov     rax, [rcx+8]
0x14005fe2f  mov     rdx, [rax+8]
0x14005fe33  cmp     [rax], rcx
0x14005fe36  jnz     loc_14005FDA2
0x14005fe3c  cmp     [rdx], rax
0x14005fe3f  jnz     loc_14005FDA2
0x14005fe45  mov     [rcx+8], rdx
0x14005fe49  mov     [rdx], rcx
0x14005fe4c  lea     rsi, [rax-8]
0x14005fe50  mov     rax, [rbx+8]
0x14005fe54  dec     dword ptr [rax+0B4h]
0x14005fe5a  mov     r15, [rsi]
0x14005fe5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005fe64  cmp     rcx, rdi
0x14005fe67  jnz     short loc_14005FEC8
0x14005fe69  mov     rax, [rbx+8]
0x14005fe6d  mov     rcx, [rax+0A8h]
0x14005fe74  add     rcx, 10h; Table
0x14005fe78  mov     rdx, rsi; Buffer
0x14005fe7b  call    cs:__imp_RtlDeleteElementGenericTable
0x14005fe82  nop     dword ptr [rax+rax+00h]
0x14005fe87  test    al, al
0x14005fe89  jz      loc_14006001E
0x14005fe8f  cmp     r14d, 1Bh
0x14005fe93  jnz     short loc_14005FEA8
0x14005fe95  mov     rax, cs:MpData
0x14005fe9c  lock inc dword ptr [rax+0B84h]
0x14005fea3  jmp     loc_14005FDCA
0x14005fea8  cmp     r14d, 1Ch
0x14005feac  jz      loc_140060056
0x14005feb2  cmp     r14d, 2
0x14005feb6  jnz     short loc_14005FEA3
0x14005feb8  mov     rax, cs:MpData
0x14005febf  lock inc dword ptr [rax+0B60h]
0x14005fec6  jmp     short loc_14005FEA3
0x14005fec8  mov     eax, [rcx+2Ch]
0x14005fecb  test    al, 4
0x14005fecd  jz      short loc_14005FE69
0x14005fecf  mov     rax, [rbx+8]
0x14005fed3  mov     r8d, [rax+0B4h]
0x14005feda  mov     dword ptr [rsp+88h+var_68], r8d
0x14005fedf  mov     r9, r15
0x14005fee2  mov     rcx, [rcx+18h]
0x14005fee6  call    WPP_SF_id
0x14005feeb  jmp     loc_14005FE69
0x14005fef0  mov     rax, cs:MpData
0x14005fef7  lock inc dword ptr [rax+0B70h]
0x14005fefe  jmp     loc_14005FD8B
0x14005ff03  lea     rdi, WPP_GLOBAL_Control
0x14005ff0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ff11  cmp     rcx, rdi
0x14005ff14  jz      loc_14005FDDC
0x14005ff1a  mov     eax, [rcx+2Ch]
0x14005ff1d  test    al, 1
0x14005ff1f  jz      loc_14005FDDC
0x14005ff25  lea     rax, [rbx+0F0h]
0x14005ff2c  mov     edx, 19h
0x14005ff31  mov     [rsp+88h+var_58], r14d
0x14005ff36  mov     [rsp+88h+var_60], r15d
0x14005ff3b  mov     [rsp+88h+var_68], rax
0x14005ff40  mov     r9, [rbx+0A8h]
0x14005ff47  mov     rcx, [rcx+18h]
0x14005ff4b  call    WPP_SF_iZDD
0x14005ff50  jmp     loc_14005FDDC
0x14005ff55  mov     rax, cs:MpData
0x14005ff5c  lock inc dword ptr [rax+0B94h]
0x14005ff63  jmp     loc_14005FD8B
0x14005ff68  lea     rdi, WPP_GLOBAL_Control
0x14005ff6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ff76  cmp     rcx, rdi
0x14005ff79  jz      loc_14005FDDC
0x14005ff7f  mov     eax, [rcx+2Ch]
0x14005ff82  test    al, 1
0x14005ff84  jz      loc_14005FDDC
0x14005ff8a  mov     edx, 18h
0x14005ff8f  mov     r9d, r14d
0x14005ff92  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x14005ff99  mov     rcx, [rcx+18h]
0x14005ff9d  call    WPP_SF_d
0x14005ffa2  jmp     loc_14005FDDC
0x14005ffa7  lfence
0x14005ffaa  add     rax, 8
0x14005ffae  mov     rdx, [rax]
0x14005ffb1  mov     rcx, [rax+8]
0x14005ffb5  cmp     [rdx+8], rax
0x14005ffb9  jnz     loc_14005FDA2
0x14005ffbf  cmp     [rcx], rax
0x14005ffc2  jnz     loc_14005FDA2
0x14005ffc8  mov     [rcx], rdx
0x14005ffcb  mov     [rdx+8], rcx
0x14005ffcf  cmp     r14d, 1Bh
0x14005ffd3  jnz     short loc_14005FFE8
0x14005ffd5  mov     rax, cs:MpData
0x14005ffdc  lock inc dword ptr [rax+0B74h]
0x14005ffe3  jmp     loc_14005FD8B
0x14005ffe8  cmp     r14d, 1Ch
0x14005ffec  jnz     short loc_140060001
0x14005ffee  mov     rax, cs:MpData
0x14005fff5  lock inc dword ptr [rax+0B98h]
0x14005fffc  jmp     loc_14005FD8B
0x140060001  cmp     r14d, 2
0x140060005  jnz     loc_14005FD8B
0x14006000b  mov     rax, cs:MpData
0x140060012  lock inc dword ptr [rax+0B50h]
0x140060019  jmp     loc_14005FD8B
0x14006001e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060025  cmp     rcx, rdi
0x140060028  jz      loc_14005FE8F
0x14006002e  mov     eax, [rcx+2Ch]
0x140060031  test    al, 1
0x140060033  jz      loc_14005FE8F
0x140060039  mov     edx, 1Ch
0x14006003e  mov     r9, r15
0x140060041  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x140060048  mov     rcx, [rcx+18h]
0x14006004c  call    WPP_SF_q
0x140060051  jmp     loc_14005FE8F
0x140060056  mov     rax, cs:MpData
0x14006005d  lock inc dword ptr [rax+0BA8h]
0x140060064  jmp     loc_14005FEA3
0x140060069  mov     rcx, [rbx+8]
0x14006006d  add     rcx, 0B8h; Resource
0x140060074  call    cs:__imp_ExReleaseResourceLite
0x14006007b  nop     dword ptr [rax+rax+00h]
0x140060080  call    cs:__imp_KeLeaveCriticalRegion
0x140060087  nop     dword ptr [rax+rax+00h]
0x14006008c  jmp     loc_14005FC2A
0x140060091  cmp     r15d, 7
0x140060095  jz      loc_14005FC8F
0x14006009b  lea     rdi, WPP_GLOBAL_Control
0x1400600a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400600a9  cmp     rcx, rdi
0x1400600ac  jz      loc_14005FC2A
0x1400600b2  mov     eax, [rcx+2Ch]
0x1400600b5  test    al, 4
0x1400600b7  jz      loc_14005FC2A
0x1400600bd  mov     edx, 15h
0x1400600c2  mov     rax, [rbx+0A8h]
0x1400600c9  mov     [rsp+88h+var_68], rax
0x1400600ce  mov     r9d, r15d
0x1400600d1  lea     r8, WPP_af6f19deb4b73a3756e7d98edd91e751_Traceguids
0x1400600d8  mov     rcx, [rcx+18h]
0x1400600dc  call    WPP_SF_Di
  ... truncated ...
```
