# StorChildAdapterPdoPnpIrp

- ea: `0x1401421e8`
- end: `0x140142455`
- name: `StorChildAdapterPdoPnpIrp`
- size: `621`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140023370`

## callees

- `0x14006d298`
- `0x14008482c`
- `0x1401421bc`
- `0x1401421e8`
- `0x14014245c`
- `0x140142774`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14014223b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14014223b`
- `ntoskrnl!IofCompleteRequest` at `0x1401422b9`
- `ntoskrnl!IofCompleteRequest` at `0x140142304`
- `ntoskrnl!IofCompleteRequest` at `0x140142423`
- `ntoskrnl!IofCompleteRequest` at `0x1401422b9`
- `ntoskrnl!IofCompleteRequest` at `0x140142304`
- `ntoskrnl!IofCompleteRequest` at `0x140142423`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142319`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142390`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142319`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142390`

## pseudocode

```c
__int64 __fastcall StorChildAdapterPdoPnpIrp(ULONG_PTR BugCheckParameter2, PIRP Irp)
{
  int v4; // ebp
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  unsigned int MinorFunction; // ebx
  int v7; // edx
  int v8; // ecx
  int v9; // eax
  char v10; // bp
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int IdIrp; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // rax
  __int128 v27; // [rsp+40h] [rbp-38h] BYREF

  v27 = 0;
  v4 = StorChildAdapterPdoAcquireRemoveLock();
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( StorEtwLoggingEnabled )
  {
    IoGetActivityIdIrp(Irp, &v27);
    if ( MinorFunction > 0x16 || (v9 = 4718720, !_bittest(&v9, MinorFunction)) )
    {
      if ( (byte_140177432 & 0x20) != 0 )
        McTemplateK0pddp_EtwWriteTransfer(
          v8,
          v7,
          (unsigned int)&v27,
          (_DWORD)Irp,
          MinorFunction,
          0,
          *(_QWORD *)(BugCheckParameter2 + 8));
    }
  }
  if ( v4 >= 0 )
  {
    v10 = 1;
  }
  else
  {
    if ( v4 != -1073741738 || MinorFunction != 2 && MinorFunction != 20 || *(_DWORD *)(BugCheckParameter2 + 60) != 5 )
    {
      Irp->IoStatus.Information = 0;
      Irp->IoStatus.Status = v4;
      IofCompleteRequest(Irp, 0);
      return (unsigned int)v4;
    }
    v10 = 0;
  }
  if ( MinorFunction > 7 )
  {
    v17 = MinorFunction - 8;
    if ( !v17 )
      goto LABEL_22;
    v18 = v17 - 1;
    if ( !v18 )
    {
      *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 4) &= 0xFFFFFFA7;
      goto LABEL_29;
    }
    v19 = v18 - 4;
    if ( !v19 )
      goto LABEL_22;
    v20 = v19 - 6;
    if ( !v20 )
    {
      IdIrp = StorChildAdapterPdoPnpQueryIdIrp(BugCheckParameter2, Irp);
LABEL_24:
      if ( v10 )
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 64));
      return IdIrp;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
LABEL_29:
      IdIrp = 0;
      goto LABEL_23;
    }
    v22 = v21 - 2;
    if ( v22 )
    {
      if ( v22 == 1 )
      {
        _InterlockedExchange((volatile __int32 *)(BugCheckParameter2 + 60), 5);
        v24 = *(_QWORD *)(BugCheckParameter2 + 72);
        v25 = **(_DWORD **)(*(_QWORD *)(v24 + 8) + 64LL);
        if ( v25 == 1094997074 )
        {
          v26 = v24 + 360;
        }
        else
        {
          v26 = 0;
          if ( v25 == 1314275652 )
            v26 = v24 + 176;
        }
        *(_DWORD *)(v26 + 248) &= ~0x100u;
        Irp->IoStatus.Status = 0;
        IofCompleteRequest(Irp, 0);
        IdIrp = 0;
        goto LABEL_24;
      }
      goto LABEL_37;
    }
LABEL_22:
    IdIrp = -1073741637;
LABEL_23:
    Irp->IoStatus.Status = IdIrp;
    IofCompleteRequest(Irp, 0);
    goto LABEL_24;
  }
  if ( MinorFunction == 7 )
    goto LABEL_22;
  if ( !MinorFunction )
  {
    _InterlockedExchange((volatile __int32 *)(BugCheckParameter2 + 60), 1);
    goto LABEL_29;
  }
  v12 = MinorFunction - 1;
  if ( !v12 )
    goto LABEL_22;
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( !v14 )
      goto LABEL_22;
    v15 = v14 - 1;
    if ( !v15 || v15 - 1 <= 1 )
      goto LABEL_22;
LABEL_37:
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 64));
    v10 = 0;
    if ( StorEtwLoggingEnabled && (byte_140177432 & 0x20) != 0 )
      McTemplateK0pd_EtwWriteTransfer(v23, EventPnpRequestComplete, &v27, Irp, Irp->IoStatus.Status);
    goto LABEL_22;
  }
  return (unsigned int)StorChildAdapterPdoRemoveDevice(BugCheckParameter2, Irp);
}

```

## disassembly

```asm
0x1401421e8  mov     [rsp+arg_10], rbx
0x1401421ed  mov     [rsp+arg_18], rbp
0x1401421f2  push    rsi
0x1401421f3  push    rdi
0x1401421f4  push    r14
0x1401421f6  sub     rsp, 60h
0x1401421fa  mov     rax, cs:__security_cookie
0x140142201  xor     rax, rsp
0x140142204  mov     [rsp+78h+var_28], rax
0x140142209  xorps   xmm0, xmm0
0x14014220c  mov     rdi, rdx
0x14014220f  movups  [rsp+78h+var_38], xmm0
0x140142214  mov     rsi, rcx
0x140142217  call    StorChildAdapterPdoAcquireRemoveLock
0x14014221c  cmp     cs:StorEtwLoggingEnabled, 0
0x140142223  mov     ebp, eax
0x140142225  mov     r14, [rdi+0B8h]
0x14014222c  movzx   ebx, byte ptr [r14+1]
0x140142231  jz      short loc_140142281
0x140142233  lea     rdx, [rsp+78h+var_38]
0x140142238  mov     rcx, rdi
0x14014223b  call    cs:__imp_IoGetActivityIdIrp
0x140142242  nop     dword ptr [rax+rax+00h]
0x140142247  cmp     ebx, 16h
0x14014224a  ja      short loc_140142256
0x14014224c  mov     eax, 480080h
0x140142251  bt      eax, ebx
0x140142254  jb      short loc_140142281
0x140142256  test    cs:byte_140177432, 20h
0x14014225d  jz      short loc_140142281
0x14014225f  mov     rax, [rsi+8]
0x140142263  lea     r8, [rsp+78h+var_38]
0x140142268  mov     [rsp+78h+var_48], rax
0x14014226d  mov     r9, rdi
0x140142270  mov     [rsp+78h+var_50], 0
0x140142278  mov     [rsp+78h+var_58], ebx
0x14014227c  call    McTemplateK0pddp_EtwWriteTransfer
0x140142281  mov     eax, 1
0x140142286  lea     ecx, [rax+4]
0x140142289  test    ebp, ebp
0x14014228b  jns     short loc_1401422C9
0x14014228d  cmp     ebp, 0C0000056h
0x140142293  jnz     short loc_1401422A9
0x140142295  cmp     ebx, 2
0x140142298  jz      short loc_14014229F
0x14014229a  cmp     ebx, 14h
0x14014229d  jnz     short loc_1401422A9
0x14014229f  cmp     [rsi+3Ch], ecx
0x1401422a2  jnz     short loc_1401422A9
0x1401422a4  xor     bpl, bpl
0x1401422a7  jmp     short loc_1401422CC
0x1401422a9  xor     edx, edx; PriorityBoost
0x1401422ab  mov     qword ptr [rdi+38h], 0
0x1401422b3  mov     rcx, rdi; Irp
0x1401422b6  mov     [rdi+30h], ebp
0x1401422b9  call    cs:__imp_IofCompleteRequest
0x1401422c0  nop     dword ptr [rax+rax+00h]
0x1401422c5  mov     eax, ebp
0x1401422c7  jmp     short loc_140142327
0x1401422c9  mov     bpl, al
0x1401422cc  cmp     ebx, 7
0x1401422cf  ja      loc_140142360
0x1401422d5  jz      short loc_1401422F7
0x1401422d7  test    ebx, ebx
0x1401422d9  jz      short loc_140142359
0x1401422db  sub     ebx, eax
0x1401422dd  jz      short loc_1401422F7
0x1401422df  sub     ebx, eax
0x1401422e1  jz      short loc_14014234A
0x1401422e3  sub     ebx, eax
0x1401422e5  jz      short loc_1401422F7
0x1401422e7  sub     ebx, eax
0x1401422e9  jz      short loc_1401422F7
0x1401422eb  sub     ebx, eax
0x1401422ed  jz      short loc_1401422F7
0x1401422ef  cmp     ebx, eax
0x1401422f1  jnz     loc_14014238C
0x1401422f7  mov     ebx, 0C00000BBh
0x1401422fc  xor     edx, edx; PriorityBoost
0x1401422fe  mov     [rdi+30h], ebx
0x140142301  mov     rcx, rdi; Irp
0x140142304  call    cs:__imp_IofCompleteRequest
0x14014230b  nop     dword ptr [rax+rax+00h]
0x140142310  test    bpl, bpl
0x140142313  jz      short loc_140142325
0x140142315  mov     rcx, [rsi+40h]; RunRefCacheAware
0x140142319  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140142320  nop     dword ptr [rax+rax+00h]
0x140142325  mov     eax, ebx
0x140142327  mov     rcx, [rsp+78h+var_28]
0x14014232c  xor     rcx, rsp; StackCookie
0x14014232f  call    __security_check_cookie
0x140142334  lea     r11, [rsp+78h+var_18]
0x140142339  mov     rbx, [r11+30h]
0x14014233d  mov     rbp, [r11+38h]
0x140142341  mov     rsp, r11
0x140142344  pop     r14
0x140142346  pop     rdi
0x140142347  pop     rsi
0x140142348  retn
0x14014234a  mov     rdx, rdi; Irp
0x14014234d  mov     rcx, rsi; BugCheckParameter2
0x140142350  call    StorChildAdapterPdoRemoveDevice
0x140142355  mov     ebx, eax
0x140142357  jmp     short loc_140142325
0x140142359  xchg    eax, [rsi+3Ch]
0x14014235c  xor     ebx, ebx
0x14014235e  jmp     short loc_1401422FC
0x140142360  sub     ebx, 8
0x140142363  jz      short loc_1401422F7
0x140142365  sub     ebx, eax
0x140142367  jz      loc_140142448
0x14014236d  sub     ebx, 4
0x140142370  jz      short loc_1401422F7
0x140142372  sub     ebx, 6
0x140142375  jz      loc_140142436
0x14014237b  sub     ebx, eax
0x14014237d  jz      short loc_14014235C
0x14014237f  sub     ebx, 2
0x140142382  jz      loc_1401422F7
0x140142388  cmp     ebx, eax
0x14014238a  jz      short loc_1401423D9
0x14014238c  mov     rcx, [rsi+40h]; RunRefCacheAware
0x140142390  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140142397  nop     dword ptr [rax+rax+00h]
0x14014239c  xor     bpl, bpl
0x14014239f  cmp     cs:StorEtwLoggingEnabled, bpl
0x1401423a6  jz      loc_1401422F7
0x1401423ac  test    cs:byte_140177432, 20h
0x1401423b3  jz      loc_1401422F7
0x1401423b9  mov     eax, [rdi+30h]
0x1401423bc  lea     r8, [rsp+78h+var_38]
0x1401423c1  mov     r9, rdi
0x1401423c4  mov     [rsp+78h+var_58], eax
0x1401423c8  lea     rdx, EventPnpRequestComplete
0x1401423cf  call    McTemplateK0pd_EtwWriteTransfer
0x1401423d4  jmp     loc_1401422F7
0x1401423d9  xchg    ecx, [rsi+3Ch]
0x1401423dc  mov     rdx, [rsi+48h]
0x1401423e0  mov     rax, [rdx+8]
0x1401423e4  mov     rcx, [rax+40h]
0x1401423e8  mov     r8d, [rcx]
0x1401423eb  cmp     r8d, 41445452h
0x1401423f2  jz      short loc_140142408
0x1401423f4  xor     eax, eax
0x1401423f6  cmp     r8d, 4E564144h
0x1401423fd  jnz     short loc_14014240F
0x1401423ff  lea     rax, [rdx+0B0h]
0x140142406  jmp     short loc_14014240F
0x140142408  lea     rax, [rdx+168h]
0x14014240f  btr     dword ptr [rax+0F8h], 8
0x140142417  xor     edx, edx; PriorityBoost
0x140142419  mov     rcx, rdi; Irp
0x14014241c  mov     dword ptr [rdi+30h], 0
0x140142423  call    cs:__imp_IofCompleteRequest
0x14014242a  nop     dword ptr [rax+rax+00h]
0x14014242f  xor     ebx, ebx
0x140142431  jmp     loc_140142310
0x140142436  mov     rdx, rdi
0x140142439  mov     rcx, rsi
0x14014243c  call    StorChildAdapterPdoPnpQueryIdIrp
0x140142441  mov     ebx, eax
0x140142443  jmp     loc_140142310
0x140142448  mov     rax, [r14+8]
0x14014244c  and     dword ptr [rax+4], 0FFFFFFA7h
0x140142450  jmp     loc_14014235C
```
