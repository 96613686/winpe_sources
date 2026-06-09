# SlbNatCreateExternalAddressForFamily

- ea: `0x14000975c`
- end: `0x140009a1a`
- name: `SlbNatCreateExternalAddressForFamily`
- size: `702`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400096fc`
- `0x140014b60`

## callees

- `0x14000820c`
- `0x14000975c`
- `0x140014dcc`
- `0x140015614`
- `0x14001f320`
- `0x14001f980`
- `0x140032228`
- `0x140034334`
- `0x140035948`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140009965`
- `ntoskrnl!IoAllocateWorkItem` at `0x140009965`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000989f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000989f`
- `ntoskrnl!ExAllocatePool2` at `0x1400098e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400098e6`
- `ntoskrnl!IoFreeWorkItem` at `0x14000988e`
- `ntoskrnl!IoFreeWorkItem` at `0x14000988e`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140009981`
- `NETIO!ConvertInterfaceLuidToIndex` at `0x140009981`

## string_xrefs

- `0x140009831`: `SlbNatCreateExternalAddressForFamily`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddressForFamily(__int64 a1, __int16 a2, __int64 a3, char a4, _QWORD *a5)
{
  __int128 v10; // xmm0
  unsigned int v11; // ebx
  char v12; // r12
  __int128 v13; // xmm1
  int v14; // eax
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  _QWORD *v18; // rdi
  int ExternalAddressWithLock; // ebx
  char *ExternalAddress; // rax
  __int64 v21; // rcx
  char **v22; // rdx
  struct _IO_WORKITEM *v23; // rcx
  __int64 Pool2; // rax
  PIO_WORKITEM WorkItem; // rax
  ULONG InterfaceIndex[4]; // [rsp+40h] [rbp-71h] BYREF
  _OWORD v27[6]; // [rsp+50h] [rbp-61h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-1h] BYREF
  __int64 v29; // [rsp+C0h] [rbp+Fh]

  memset(v27, 0, 0x54u);
  v29 = 0;
  InterfaceIndex[0] = 0;
  v28 = 0;
  if ( a2 != 2 )
    return 3221225659LL;
  v10 = *(_OWORD *)(a1 + 80);
  v11 = *(_DWORD *)(a1 + 256);
  v12 = 0;
  v13 = *(_OWORD *)(a1 + 96);
  LOWORD(v28) = 2;
  v14 = *(_DWORD *)(a3 + 8);
  v27[0] = v10;
  v15 = *(_OWORD *)(a1 + 112);
  DWORD1(v28) = v14;
  v27[1] = v13;
  v16 = *(_OWORD *)(a1 + 128);
  v27[2] = v15;
  v17 = *(_OWORD *)(a1 + 144);
  v27[3] = v16;
  v27[4] = v17;
  while ( SlbNatFindExternalAddress(a1, v11) )
  {
    if ( v11 == -1 )
    {
      v18 = 0;
      ExternalAddressWithLock = -1073741823;
      goto LABEL_8;
    }
    ++v11;
  }
  LODWORD(v27[5]) = v11;
  Pool2 = ExAllocatePool2(64, 144, 1634750035);
  v18 = (_QWORD *)Pool2;
  if ( !Pool2 )
    goto LABEL_19;
  *(_OWORD *)Pool2 = v27[0];
  *(_OWORD *)(Pool2 + 16) = v27[1];
  *(_OWORD *)(Pool2 + 32) = v27[2];
  *(_OWORD *)(Pool2 + 48) = v27[3];
  *(_OWORD *)(Pool2 + 64) = v27[4];
  *(_DWORD *)(Pool2 + 80) = v27[5];
  *(_OWORD *)(Pool2 + 84) = v28;
  *(_QWORD *)(Pool2 + 100) = v29;
  *(_DWORD *)(Pool2 + 108) = v11;
  *(_QWORD *)(Pool2 + 120) = *(_QWORD *)a3;
  *(_BYTE *)(Pool2 + 128) = a4;
  *(_DWORD *)(Pool2 + 136) = 1;
  WorkItem = IoAllocateWorkItem(deviceObject);
  v18[14] = WorkItem;
  if ( WorkItem )
  {
    ExternalAddressWithLock = ConvertInterfaceLuidToIndex((const NET_LUID *)a3, InterfaceIndex);
    if ( ExternalAddressWithLock >= 0 )
    {
      ExternalAddressWithLock = SlbNatCreateExternalAddressWithLock(
                                  (__int64)v27,
                                  (__int16 *)&v28,
                                  a1,
                                  0,
                                  InterfaceIndex[0]);
      if ( ExternalAddressWithLock >= 0 )
      {
        v12 = 1;
        ExternalAddressWithLock = SlbNatIpsAddInterfaceMapping(InterfaceIndex[0], 1, 1, *(_DWORD *)(a1 + 248));
        if ( ExternalAddressWithLock >= 0 )
        {
          if ( a5 )
            *a5 = v18;
          else
            SlbNatQueueWorkItem(v18[14], SlbNatAllocPortCallback, v18);
          return (unsigned int)ExternalAddressWithLock;
        }
      }
    }
  }
  else
  {
LABEL_19:
    ExternalAddressWithLock = -1073741670;
  }
LABEL_8:
  SlbNatInsertErrorEntry(
    InterfaceIndex[0],
    (unsigned int)ExternalAddressWithLock,
    L"SlbNatCreateExternalAddressForFamily");
  if ( v12 )
  {
    ExternalAddress = (char *)SlbNatFindExternalAddress(a1, LODWORD(v27[5]));
    if ( ExternalAddress )
    {
      v21 = *(_QWORD *)ExternalAddress;
      if ( *(char **)(*(_QWORD *)ExternalAddress + 8LL) != ExternalAddress
        || (v22 = (char **)*((_QWORD *)ExternalAddress + 1), *v22 != ExternalAddress) )
      {
        __fastfail(3u);
      }
      *v22 = (char *)v21;
      *(_QWORD *)(v21 + 8) = v22;
      SlbNatDeleteExternalAddress(ExternalAddress, a1);
    }
  }
  if ( v18 )
  {
    v23 = (struct _IO_WORKITEM *)v18[14];
    if ( v23 )
      IoFreeWorkItem(v23);
    ExFreePoolWithTag(v18, 0);
  }
  return (unsigned int)ExternalAddressWithLock;
}

```

## disassembly

```asm
0x14000975c  mov     [rsp-8+arg_18], rbx
0x140009761  push    rbp
0x140009762  push    rsi
0x140009763  push    rdi
0x140009764  push    r12
0x140009766  push    r13
0x140009768  push    r14
0x14000976a  push    r15
0x14000976c  lea     rbp, [rsp-1Fh]
0x140009771  sub     rsp, 0D0h
0x140009778  mov     rax, cs:__security_cookie
0x14000977f  xor     rax, rsp
0x140009782  mov     [rbp+4Fh+var_38], rax
0x140009786  mov     r14, [rbp+4Fh+arg_20]
0x14000978a  movzx   ebx, dx
0x14000978d  xor     edx, edx; Val
0x14000978f  mov     r15, r8
0x140009792  mov     rsi, rcx
0x140009795  mov     r13b, r9b
0x140009798  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14000979c  lea     r8d, [rdx+54h]; Size
0x1400097a0  call    memset
0x1400097a5  xor     eax, eax
0x1400097a7  xorps   xmm0, xmm0
0x1400097aa  mov     [rbp+4Fh+var_40], rax
0x1400097ae  mov     [rbp+4Fh+InterfaceIndex], eax
0x1400097b1  mov     eax, 2
0x1400097b6  movups  [rbp+4Fh+var_50], xmm0
0x1400097ba  cmp     bx, ax
0x1400097bd  jz      short loc_1400097C9
0x1400097bf  mov     eax, 0C00000BBh
0x1400097c4  jmp     loc_1400098AD
0x1400097c9  movups  xmm0, xmmword ptr [rsi+50h]
0x1400097cd  mov     ebx, [rsi+100h]
0x1400097d3  xor     r12b, r12b
0x1400097d6  movups  xmm1, xmmword ptr [rsi+60h]
0x1400097da  mov     word ptr [rbp+4Fh+var_50], ax
0x1400097de  mov     eax, [r15+8]
0x1400097e2  movaps  [rbp+4Fh+var_B0], xmm0
0x1400097e6  movups  xmm0, xmmword ptr [rsi+70h]
0x1400097ea  mov     dword ptr [rbp+4Fh+var_50+4], eax
0x1400097ed  movaps  [rbp+4Fh+var_A0], xmm1
0x1400097f1  movups  xmm1, xmmword ptr [rsi+80h]
0x1400097f8  movaps  [rbp+4Fh+var_90], xmm0
0x1400097fc  movups  xmm0, xmmword ptr [rsi+90h]
0x140009803  movaps  [rbp+4Fh+var_80], xmm1
0x140009807  movaps  [rbp+4Fh+var_70], xmm0
0x14000980b  mov     edx, ebx
0x14000980d  mov     rcx, rsi
0x140009810  call    SlbNatFindExternalAddress
0x140009815  test    rax, rax
0x140009818  jz      loc_1400098D5
0x14000981e  cmp     ebx, 0FFFFFFFFh
0x140009821  jz      short loc_140009827
0x140009823  inc     ebx
0x140009825  jmp     short loc_14000980B
0x140009827  xor     edi, edi
0x140009829  mov     ebx, 0C0000001h
0x14000982e  mov     ecx, [rbp+4Fh+InterfaceIndex]
0x140009831  lea     r8, aSlbnatcreateex; "SlbNatCreateExternalAddressForFamily"
0x140009838  mov     edx, ebx
0x14000983a  call    SlbNatInsertErrorEntry
0x14000983f  test    r12b, r12b
0x140009842  jz      short loc_140009880
0x140009844  mov     edx, [rbp+4Fh+var_60]
0x140009847  mov     rcx, rsi
0x14000984a  call    SlbNatFindExternalAddress
0x14000984f  test    rax, rax
0x140009852  jz      short loc_140009880
0x140009854  mov     rcx, [rax]
0x140009857  cmp     [rcx+8], rax
0x14000985b  jnz     loc_140009A13
0x140009861  mov     rdx, [rax+8]
0x140009865  cmp     [rdx], rax
0x140009868  jnz     loc_140009A13
0x14000986e  mov     [rdx], rcx
0x140009871  mov     [rcx+8], rdx
0x140009875  mov     rdx, rsi
0x140009878  mov     rcx, rax; P
0x14000987b  call    SlbNatDeleteExternalAddress
0x140009880  test    rdi, rdi
0x140009883  jz      short loc_1400098AB
0x140009885  mov     rcx, [rdi+70h]; IoWorkItem
0x140009889  test    rcx, rcx
0x14000988c  jz      short loc_14000989A
0x14000988e  call    cs:__imp_IoFreeWorkItem
0x140009895  nop     dword ptr [rax+rax+00h]
0x14000989a  xor     edx, edx; Tag
0x14000989c  mov     rcx, rdi; P
0x14000989f  call    cs:__imp_ExFreePoolWithTag
0x1400098a6  nop     dword ptr [rax+rax+00h]
0x1400098ab  mov     eax, ebx
0x1400098ad  mov     rcx, [rbp+4Fh+var_38]
0x1400098b1  xor     rcx, rsp; StackCookie
0x1400098b4  call    __security_check_cookie
0x1400098b9  mov     rbx, [rsp+100h+arg_18]
0x1400098c1  add     rsp, 0D0h
0x1400098c8  pop     r15
0x1400098ca  pop     r14
0x1400098cc  pop     r13
0x1400098ce  pop     r12
0x1400098d0  pop     rdi
0x1400098d1  pop     rsi
0x1400098d2  pop     rbp
0x1400098d3  retn
0x1400098d5  mov     edx, 90h
0x1400098da  mov     [rbp+4Fh+var_60], ebx
0x1400098dd  mov     r8d, 61704E53h
0x1400098e3  lea     ecx, [rdx-50h]
0x1400098e6  call    cs:__imp_ExAllocatePool2
0x1400098ed  nop     dword ptr [rax+rax+00h]
0x1400098f2  mov     rdi, rax
0x1400098f5  test    rax, rax
0x1400098f8  jnz     short loc_140009904
0x1400098fa  mov     ebx, 0C000009Ah
0x1400098ff  jmp     loc_14000982E
0x140009904  movaps  xmm0, [rbp+4Fh+var_B0]
0x140009908  movups  xmmword ptr [rax], xmm0
0x14000990b  movaps  xmm1, [rbp+4Fh+var_A0]
0x14000990f  movups  xmmword ptr [rax+10h], xmm1
0x140009913  movaps  xmm0, [rbp+4Fh+var_90]
0x140009917  movups  xmmword ptr [rax+20h], xmm0
0x14000991b  movaps  xmm1, [rbp+4Fh+var_80]
0x14000991f  movups  xmmword ptr [rax+30h], xmm1
0x140009923  movaps  xmm0, [rbp+4Fh+var_70]
0x140009927  movups  xmmword ptr [rax+40h], xmm0
0x14000992b  mov     eax, [rbp+4Fh+var_60]
0x14000992e  mov     [rdi+50h], eax
0x140009931  movups  xmm0, [rbp+4Fh+var_50]
0x140009935  movups  xmmword ptr [rdi+54h], xmm0
0x140009939  movsd   xmm1, [rbp+4Fh+var_40]
0x14000993e  movsd   qword ptr [rdi+64h], xmm1
0x140009943  mov     [rdi+6Ch], ebx
0x140009946  mov     rax, [r15]
0x140009949  mov     [rdi+78h], rax
0x14000994d  mov     [rdi+80h], r13b
0x140009954  mov     dword ptr [rdi+88h], 1
0x14000995e  mov     rcx, cs:deviceObject; DeviceObject
0x140009965  call    cs:__imp_IoAllocateWorkItem
0x14000996c  nop     dword ptr [rax+rax+00h]
0x140009971  mov     [rdi+70h], rax
0x140009975  test    rax, rax
0x140009978  jz      short loc_1400098FA
0x14000997a  lea     rdx, [rbp+4Fh+InterfaceIndex]; InterfaceIndex
0x14000997e  mov     rcx, r15; InterfaceLuid
0x140009981  call    cs:__imp_ConvertInterfaceLuidToIndex
0x140009988  nop     dword ptr [rax+rax+00h]
0x14000998d  mov     ebx, eax
0x14000998f  test    eax, eax
0x140009991  js      loc_14000982E
0x140009997  mov     eax, [rbp+4Fh+InterfaceIndex]
0x14000999a  lea     rdx, [rbp+4Fh+var_50]
0x14000999e  xor     r9d, r9d
0x1400099a1  mov     dword ptr [rsp+100h+var_E0], eax
0x1400099a5  mov     r8, rsi
0x1400099a8  lea     rcx, [rbp+4Fh+var_B0]
0x1400099ac  call    SlbNatCreateExternalAddressWithLock
0x1400099b1  mov     ebx, eax
0x1400099b3  test    eax, eax
0x1400099b5  js      loc_14000982E
0x1400099bb  mov     eax, [rsi+0F8h]
0x1400099c1  mov     r12b, 1
0x1400099c4  mov     r8d, [rsi+44h]
0x1400099c8  xor     r9d, r9d
0x1400099cb  mov     ecx, [rbp+4Fh+InterfaceIndex]; InterfaceIndex
0x1400099ce  mov     rdx, rsi
0x1400099d1  mov     [rsp+100h+var_D0], eax; int
0x1400099d5  mov     [rsp+100h+var_D8], r12b; char
0x1400099da  mov     [rsp+100h+var_E0], r12b; char
0x1400099df  call    SlbNatIpsAddInterfaceMapping
0x1400099e4  mov     ebx, eax
0x1400099e6  test    eax, eax
0x1400099e8  js      loc_14000982E
0x1400099ee  test    r14, r14
0x1400099f1  jnz     short loc_140009A0B
0x1400099f3  mov     rcx, [rdi+70h]
0x1400099f7  lea     rdx, SlbNatAllocPortCallback
0x1400099fe  mov     r8, rdi
0x140009a01  call    SlbNatQueueWorkItem
0x140009a06  jmp     loc_1400098AB
0x140009a0b  mov     [r14], rdi
0x140009a0e  jmp     loc_1400098AB
0x140009a13  mov     ecx, 3
0x140009a18  int     29h; Win8: RtlFailFast(ecx)
```
