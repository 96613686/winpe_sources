# PgmReadRegistryParameters

- ea: `0x1400381ac`
- end: `0x140038399`
- name: `PgmReadRegistryParameters`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14003775c`

## callees

- `0x140005038`
- `0x140005068`
- `0x14000a18c`
- `0x14000a2f8`
- `0x14000a434`
- `0x1400381ac`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140038341`
- `ntoskrnl!ZwClose` at `0x140038352`
- `ntoskrnl!ZwClose` at `0x140038341`
- `ntoskrnl!ZwClose` at `0x140038352`
- `ntoskrnl!ExAllocatePool2` at `0x1400381e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400381e0`

## pseudocode

```c
__int64 __fastcall PgmReadRegistryParameters(struct _UNICODE_STRING *a1, __int64 *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rbx
  int v7; // eax
  unsigned __int64 v8; // r9
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF
  HANDLE v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  Handle = 0;
  Pool2 = ExAllocatePool2(64, 32, 812476240);
  v5 = Pool2;
  if ( Pool2 )
  {
    *a2 = Pool2;
    v7 = PgmOpenRegistryParameters(a1, &v10, &Handle);
    if ( v7 >= 0 )
    {
      if ( (int)ReadRegistryStringValue(Handle) >= 0 )
        *(_DWORD *)(v5 + 4) |= 1u;
      if ( (int)ReadRegistryDwordValue(Handle) >= 0 )
      {
        if ( *(_DWORD *)(v5 + 24) > 0x6DDD00u )
          *(_DWORD *)(v5 + 24) = 7200000;
      }
      else
      {
        *(_DWORD *)(v5 + 24) = 300000;
      }
      if ( (int)ReadRegistryDwordValue(Handle) >= 0 )
      {
        v8 = (unsigned __int64)(unsigned int)ConfiguredMaxPacketSize << 10;
        if ( v8 > 0xFFFFFFFF )
          v8 = 0xFFFF;
        ConfiguredMaxPacketSize = v8;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, v8);
        }
      }
      ZwClose(Handle);
      ZwClose(v10);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids,
        (unsigned int)v7);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids, 32);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400381ac  mov     rax, rsp
0x1400381af  mov     [rax+8], rbx
0x1400381b3  mov     [rax+10h], rsi
0x1400381b7  push    rdi
0x1400381b8  sub     rsp, 20h
0x1400381bc  mov     rdi, rdx
0x1400381bf  mov     qword ptr [rax+20h], 0
0x1400381c7  mov     edx, 20h ; ' '
0x1400381cc  mov     qword ptr [rax+18h], 0
0x1400381d4  mov     rsi, rcx
0x1400381d7  mov     r8d, 306D6750h
0x1400381dd  lea     ecx, [rdx+20h]
0x1400381e0  call    cs:__imp_ExAllocatePool2
0x1400381e7  nop     dword ptr [rax+rax+00h]
0x1400381ec  mov     rbx, rax
0x1400381ef  test    rax, rax
0x1400381f2  jnz     short loc_140038231
0x1400381f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381fb  lea     rbx, WPP_GLOBAL_Control
0x140038202  cmp     rcx, rbx
0x140038205  jz      short loc_140038227
0x140038207  mov     eax, [rcx+2Ch]
0x14003820a  test    al, 2
0x14003820c  jz      short loc_140038227
0x14003820e  mov     rcx, [rcx+18h]
0x140038212  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140038219  mov     edx, 13h
0x14003821e  lea     r9d, [rdx+0Dh]
0x140038222  call    WPP_SF_d
0x140038227  mov     eax, 0C000009Ah
0x14003822c  jmp     loc_140038388
0x140038231  lea     r8, [rsp+28h+Handle]
0x140038236  mov     [rdi], rbx
0x140038239  lea     rdx, [rsp+28h+arg_18]
0x14003823e  mov     rcx, rsi
0x140038241  call    PgmOpenRegistryParameters
0x140038246  test    eax, eax
0x140038248  jns     short loc_14003828A
0x14003824a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038251  lea     rbx, WPP_GLOBAL_Control
0x140038258  cmp     rcx, rbx
0x14003825b  jz      loc_140038386
0x140038261  mov     edx, [rcx+2Ch]
0x140038264  test    dl, 2
0x140038267  jz      loc_140038386
0x14003826d  mov     rcx, [rcx+18h]
0x140038271  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140038278  mov     edx, 14h
0x14003827d  mov     r9d, eax
0x140038280  call    WPP_SF_d
0x140038285  jmp     loc_140038386
0x14003828a  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x14003828f  lea     r8, [rbx+8]
0x140038293  call    ReadRegistryStringValue
0x140038298  test    eax, eax
0x14003829a  js      short loc_1400382A0
0x14003829c  or      dword ptr [rbx+4], 1
0x1400382a0  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x1400382a5  lea     r8, [rbx+18h]
0x1400382a9  lea     rdx, aMaxspminterval; "MaxSPMInterval"
0x1400382b0  call    ReadRegistryDwordValue
0x1400382b5  test    eax, eax
0x1400382b7  jns     short loc_1400382C2
0x1400382b9  mov     dword ptr [rbx+18h], 493E0h
0x1400382c0  jmp     short loc_1400382CF
0x1400382c2  mov     eax, 6DDD00h
0x1400382c7  cmp     [rbx+18h], eax
0x1400382ca  jbe     short loc_1400382CF
0x1400382cc  mov     [rbx+18h], eax
0x1400382cf  mov     rcx, [rsp+28h+Handle]; KeyHandle
0x1400382d4  lea     r8, ConfiguredMaxPacketSize
0x1400382db  lea     rdx, aMaxpacketsize; "MaxPacketSize"
0x1400382e2  call    ReadRegistryDwordValue
0x1400382e7  lea     rbx, WPP_GLOBAL_Control
0x1400382ee  test    eax, eax
0x1400382f0  js      short loc_14003833C
0x1400382f2  mov     r9d, cs:ConfiguredMaxPacketSize
0x1400382f9  mov     eax, 0FFFFFFFFh
0x1400382fe  shl     r9, 0Ah
0x140038302  cmp     r9, rax
0x140038305  jbe     short loc_14003830D
0x140038307  mov     r9d, 0FFFFh
0x14003830d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038314  mov     cs:ConfiguredMaxPacketSize, r9d
0x14003831b  cmp     rcx, rbx
0x14003831e  jz      short loc_14003833C
0x140038320  mov     eax, [rcx+2Ch]
0x140038323  test    al, 10h
0x140038325  jz      short loc_14003833C
0x140038327  mov     rcx, [rcx+18h]
0x14003832b  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x140038332  mov     edx, 15h
0x140038337  call    WPP_SF_d
0x14003833c  mov     rcx, [rsp+28h+Handle]; Handle
0x140038341  call    cs:__imp_ZwClose
0x140038348  nop     dword ptr [rax+rax+00h]
0x14003834d  mov     rcx, [rsp+28h+arg_18]; Handle
0x140038352  call    cs:__imp_ZwClose
0x140038359  nop     dword ptr [rax+rax+00h]
0x14003835e  mov     rcx, cs:WPP_GLOBAL_Control
0x140038365  cmp     rcx, rbx
0x140038368  jz      short loc_140038386
0x14003836a  mov     eax, [rcx+2Ch]
0x14003836d  test    al, 10h
0x14003836f  jz      short loc_140038386
0x140038371  mov     rcx, [rcx+18h]
0x140038375  lea     r8, WPP_bb5b95a879423dd016b151292c2a25e4_Traceguids
0x14003837c  mov     edx, 16h
0x140038381  call    WPP_SF_
0x140038386  xor     eax, eax
0x140038388  mov     rbx, [rsp+28h+arg_0]
0x14003838d  mov     rsi, [rsp+28h+arg_8]
0x140038392  add     rsp, 20h
0x140038396  pop     rdi
0x140038397  retn
```
