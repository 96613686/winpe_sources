# _anonymous_namespace_::uwfCfgApiBreakpoint

- ea: `0x18001aa08`
- end: `0x18001aa8e`
- name: `_anonymous_namespace_::uwfCfgApiBreakpoint`
- size: `134`
- prototype: `__int64(void)`
- caller_count: `54`
- callee_count: `4`
- tags: ``

## callers

- `0x180017d50`
- `0x180017df0`
- `0x180017e90`
- `0x180017fa0`
- `0x180018080`
- `0x1800181a0`
- `0x180018240`
- `0x1800182e0`
- `0x180018390`
- `0x180018430`
- `0x1800184b0`
- `0x180018540`
- `0x1800185f0`
- `0x180018720`
- `0x1800187b0`
- `0x180018830`
- `0x1800188d0`
- `0x180018950`
- `0x180018bf0`
- `0x180018c70`
- `0x180018cf0`
- `0x180018d90`
- `0x180018e40`
- `0x180018f50`
- `0x180018fe0`
- `0x180019070`
- `0x180019110`
- `0x1800191a0`
- `0x180019260`
- `0x180019310`
- `0x1800193c0`
- `0x180019600`
- `0x180019690`
- `0x180019730`
- `0x1800197d0`
- `0x1800198d0`
- `0x180019940`
- `0x1800199b0`
- `0x180019a30`
- `0x180019d70`
- `0x180019df0`
- `0x180019e70`
- `0x180019fa0`
- `0x18001a010`
- `0x18001a080`
- `0x18001a110`
- `0x18001a1a0`
- `0x18001a240`
- `0x18001a2d0`
- `0x18001a4e0`

## callees

- `0x180013100`
- `0x1800139f0`
- `0x1800147d0`
- `0x18001aa08`

## pseudocode

```c
__int64 anonymous_namespace_::uwfCfgApiBreakpoint()
{
  signed int v0; // ebx
  _QWORD v2[2]; // [rsp+40h] [rbp-28h] BYREF
  char v3; // [rsp+50h] [rbp-18h]

  v2[1] = -1;
  v2[0] = &CDevice::`vftable';
  v3 = 0;
  v0 = CDevice::Initialize((CDevice *)v2, L"\\\\.\\UwfvolControl");
  if ( v0 >= 0 )
    v0 = CDevice::SendIOCTL((CDevice *)v2, 0x2249C3u, 0, 0, 0, 0, 0);
  v2[0] = &CDevice::`vftable';
  CDevice::Close((CDevice *)v2);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18001aa08  mov     rax, rsp
0x18001aa0b  mov     [rax+8], rbx
0x18001aa0f  push    rsi
0x18001aa10  sub     rsp, 60h
0x18001aa14  lea     rsi, ??_7CDevice@@6B@; const CDevice::`vftable'
0x18001aa1b  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFFh
0x18001aa23  lea     rdx, aUwfvolcontrol; "\\\\.\\UwfvolControl"
0x18001aa2a  mov     [rax-28h], rsi
0x18001aa2e  lea     rcx, [rax-28h]; this
0x18001aa32  mov     byte ptr [rax-18h], 0
0x18001aa36  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x18001aa3b  mov     ebx, eax
0x18001aa3d  test    eax, eax
0x18001aa3f  js      short loc_18001AA72
0x18001aa41  mov     [rsp+68h+var_38], 0; unsigned int *
0x18001aa4a  lea     rcx, [rsp+68h+var_28]; this
0x18001aa4f  mov     [rsp+68h+var_40], 0; DWORD
0x18001aa57  xor     r9d, r9d; unsigned int
0x18001aa5a  xor     r8d, r8d; void *
0x18001aa5d  mov     [rsp+68h+var_48], 0; void *
0x18001aa66  mov     edx, 2249C3h; unsigned int
0x18001aa6b  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x18001aa70  mov     ebx, eax
0x18001aa72  lea     rcx, [rsp+68h+var_28]; this
0x18001aa77  mov     [rsp+68h+var_28], rsi
0x18001aa7c  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x18001aa81  mov     eax, ebx
0x18001aa83  mov     rbx, [rsp+68h+arg_0]
0x18001aa88  add     rsp, 60h
0x18001aa8c  pop     rsi
0x18001aa8d  retn
```
