# CUsbBusFilter::GetHIDRawReportDescriptor(_DEVICE_OBJECT *,ulong,uchar * *)

- ea: `0x14000a0fc`
- end: `0x14000a2e0`
- name: `?GetHIDRawReportDescriptor@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@KPEAPEAE@Z`
- size: `484`
- prototype: `__int64 __fastcall(CUsbBusFilter *__hidden this, struct _DEVICE_OBJECT *, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009eb4`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x140005084`
- `0x140009134`
- `0x14000a0fc`
- `0x14000ab00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2ac`
- `ntoskrnl!ExAllocatePool2` at `0x14000a178`
- `ntoskrnl!ExAllocatePool2` at `0x14000a178`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::GetHIDRawReportDescriptor(
        CUsbBusFilter *this,
        struct _DEVICE_OBJECT *a2,
        unsigned int a3,
        unsigned __int8 **a4)
{
  __int64 v4; // r14
  unsigned int v6; // ebx
  void *Pool2; // rsi
  unsigned int i; // r15d
  int v9; // r9d
  int v10; // eax
  int v11; // ebp
  unsigned __int64 v13; // [rsp+28h] [rbp-A0h]
  struct _IO_STACK_LOCATION v14; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v15; // [rsp+D0h] [rbp+8h] BYREF
  struct _DEVICE_OBJECT *v16; // [rsp+D8h] [rbp+10h]

  v16 = a2;
  v15 = (unsigned __int64)this;
  v4 = a3;
  if ( a3 )
  {
    Pool2 = (void *)ExAllocatePool2(256, a3, 1917088324);
    if ( Pool2 )
    {
      for ( i = 0; i < 3; ++i )
      {
        v15 = 0;
        memset(&v14, 0, sizeof(v14));
        v14.MajorFunction = 15;
        v14.Parameters.Read.Length = v4;
        v14.Parameters.Read.ByteOffset.LowPart = 720903;
        v10 = IopSynchronousCall(v16, &v14, Pool2, v9, 0, v13, &v15);
        v11 = v10;
        if ( v10 >= 0 )
        {
          if ( v15 == v4 )
            goto LABEL_21;
          v11 = -1073741668;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            16,
            WPP_e71faac6a535323b68e48f556bf845d8_Traceguids,
            (unsigned int)v10);
        }
      }
      if ( v11 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
        return (unsigned int)v11;
      }
LABEL_21:
      v6 = 0;
      *a4 = (unsigned __int8 *)Pool2;
    }
    else
    {
      v6 = -1073741801;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids);
    }
  }
  else
  {
    v6 = -1073741668;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x14000a0fc  mov     [rsp+arg_10], rbx
0x14000a101  mov     [rsp+arg_8], rdx
0x14000a106  mov     [rsp+arg_0], rcx
0x14000a10b  push    rbp
0x14000a10c  push    rsi
0x14000a10d  push    rdi
0x14000a10e  push    r12
0x14000a110  push    r13
0x14000a112  push    r14
0x14000a114  push    r15
0x14000a116  sub     rsp, 90h
0x14000a11d  mov     r14d, r8d
0x14000a120  mov     r13, r9
0x14000a123  test    r8d, r8d
0x14000a126  jnz     short loc_14000A16A
0x14000a128  mov     ebx, 0C000009Ch
0x14000a12d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a134  lea     rdi, WPP_GLOBAL_Control
0x14000a13b  cmp     rcx, rdi
0x14000a13e  jz      loc_14000A2C2
0x14000a144  cmp     byte ptr [rcx+29h], 2
0x14000a148  jb      loc_14000A2C2
0x14000a14e  mov     rcx, [rcx+18h]
0x14000a152  lea     edx, [r8+0Eh]
0x14000a156  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x14000a15d  xor     r9d, r9d
0x14000a160  call    WPP_SF_d
0x14000a165  jmp     loc_14000A2C2
0x14000a16a  mov     r8d, 72447244h
0x14000a170  mov     rdx, r14
0x14000a173  mov     ecx, 100h
0x14000a178  call    cs:__imp_ExAllocatePool2
0x14000a17f  nop     dword ptr [rax+rax+00h]
0x14000a184  mov     rsi, rax
0x14000a187  test    rax, rax
0x14000a18a  jnz     short loc_14000A1CA
0x14000a18c  mov     ebx, 0C0000017h
0x14000a191  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a198  lea     rdi, WPP_GLOBAL_Control
0x14000a19f  cmp     rcx, rdi
0x14000a1a2  jz      loc_14000A2C2
0x14000a1a8  cmp     byte ptr [rcx+29h], 2
0x14000a1ac  jb      loc_14000A2C2
0x14000a1b2  mov     rcx, [rcx+18h]
0x14000a1b6  lea     edx, [rax+0Fh]
0x14000a1b9  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x14000a1c0  call    WPP_SF_
0x14000a1c5  jmp     loc_14000A2C2
0x14000a1ca  xor     r15d, r15d
0x14000a1cd  lea     rdi, WPP_GLOBAL_Control
0x14000a1d4  mov     ebx, 0C000009Ch
0x14000a1d9  xor     edx, edx; Val
0x14000a1db  mov     [rsp+0C8h+arg_0], 0
0x14000a1e7  lea     rcx, [rsp+0C8h+var_88]; void *
0x14000a1ec  lea     r8d, [rdx+48h]; Size
0x14000a1f0  call    memset
0x14000a1f5  mov     rcx, [rsp+0C8h+arg_8]; struct _DEVICE_OBJECT *
0x14000a1fd  lea     rax, [rsp+0C8h+arg_0]
0x14000a205  mov     [rsp+0C8h+var_98], rax; unsigned __int64 *
0x14000a20a  lea     rdx, [rsp+0C8h+var_88]; struct _IO_STACK_LOCATION *
0x14000a20f  mov     r8, rsi; void *
0x14000a212  mov     [rsp+0C8h+var_A8], 0; char
0x14000a217  mov     [rsp+0C8h+var_88.MajorFunction], 0Fh
0x14000a21c  mov     dword ptr [rsp+0C8h+var_88.Parameters], r14d
0x14000a221  mov     dword ptr [rsp+0C8h+var_88.Parameters+10h], 0B0007h
0x14000a229  call    ?IopSynchronousCall@@YAJPEAU_DEVICE_OBJECT@@PEAU_IO_STACK_LOCATION@@PEAXJE_KPEA_K@Z; IopSynchronousCall(_DEVICE_OBJECT *,_IO_STACK_LOCATION *,void *,long,uchar,unsigned __int64,unsigned __int64 *)
0x14000a22e  mov     ebp, eax
0x14000a230  test    eax, eax
0x14000a232  jns     short loc_14000A260
0x14000a234  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a23b  cmp     rcx, rdi
0x14000a23e  jz      short loc_14000A296
0x14000a240  cmp     byte ptr [rcx+29h], 2
0x14000a244  jb      short loc_14000A296
0x14000a246  mov     rcx, [rcx+18h]
0x14000a24a  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x14000a251  mov     edx, 10h
0x14000a256  mov     r9d, eax
0x14000a259  call    WPP_SF_d
0x14000a25e  jmp     short loc_14000A296
0x14000a260  mov     r9, [rsp+0C8h+arg_0]
0x14000a268  cmp     r9, r14
0x14000a26b  jz      short loc_14000A2BC
0x14000a26d  mov     ebp, ebx
0x14000a26f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a276  cmp     rcx, rdi
0x14000a279  jz      short loc_14000A296
0x14000a27b  cmp     byte ptr [rcx+29h], 2
0x14000a27f  jb      short loc_14000A296
0x14000a281  mov     rcx, [rcx+18h]
0x14000a285  lea     r8, WPP_e71faac6a535323b68e48f556bf845d8_Traceguids
0x14000a28c  mov     edx, 11h
0x14000a291  call    WPP_SF_i
0x14000a296  inc     r15d
0x14000a299  cmp     r15d, 3
0x14000a29d  jb      loc_14000A1D9
0x14000a2a3  test    ebp, ebp
0x14000a2a5  jns     short loc_14000A2BC
0x14000a2a7  xor     edx, edx; Tag
0x14000a2a9  mov     rcx, rsi; P
0x14000a2ac  call    cs:__imp_ExFreePoolWithTag
0x14000a2b3  nop     dword ptr [rax+rax+00h]
0x14000a2b8  mov     ebx, ebp
0x14000a2ba  jmp     short loc_14000A2C2
0x14000a2bc  xor     ebx, ebx
0x14000a2be  mov     [r13+0], rsi
0x14000a2c2  mov     eax, ebx
0x14000a2c4  mov     rbx, [rsp+0C8h+arg_10]
0x14000a2cc  add     rsp, 90h
0x14000a2d3  pop     r15
0x14000a2d5  pop     r14
0x14000a2d7  pop     r13
0x14000a2d9  pop     r12
0x14000a2db  pop     rdi
0x14000a2dc  pop     rsi
0x14000a2dd  pop     rbp
0x14000a2de  retn
```
