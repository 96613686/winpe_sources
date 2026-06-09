# CUwfStaticVolumeConfiguration::SetLooseBindingConfiguration(ushort const *)

- ea: `0x180009758`
- end: `0x180009842`
- name: `?SetLooseBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAJPEBG@Z`
- size: `234`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000bc90`

## callees

- `0x180009758`
- `0x18000bf00`
- `0x18000c590`
- `0x180013100`
- `0x1800139f0`
- `0x1800147d0`
- `0x18001b020`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::SetLooseBindingConfiguration(
        CUwfStaticVolumeConfiguration *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // esi
  unsigned int v4; // r14d
  int v5; // ebx
  _QWORD v7[2]; // [rsp+40h] [rbp-30h] BYREF
  char v8; // [rsp+50h] [rbp-20h]
  __int64 v9; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+60h] [rbp-10h]

  v7[1] = -1;
  v9 = 0;
  v3 = 0;
  v10 = 0;
  v8 = 0;
  v7[0] = &CDevice::`vftable';
  v4 = 0;
  v5 = CDevice::Initialize((CDevice *)v7, a2);
  if ( v5 >= 0 )
  {
    v5 = CDevice::SendIOCTL((CDevice *)v7, 0x2D1080u, 0, 0, &v9, 0xCu, 0);
    if ( v5 >= 0 )
    {
      v3 = HIDWORD(v9);
      v4 = v10;
    }
  }
  v7[0] = &CDevice::`vftable';
  CDevice::Close((CDevice *)v7);
  if ( v5 < 0
    || (v5 = CUwfStaticVolumeConfiguration::set_DiskNumber((CUwfConfiguration **)this, v3), v5 < 0)
    || (v5 = CUwfStaticVolumeConfiguration::set_PartitionNumber((CUwfConfiguration **)this, v4), v5 < 0) )
  {
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009758  mov     [rsp-28h+arg_10], rbx
0x18000975d  push    rbp
0x18000975e  push    rsi
0x18000975f  push    rdi
0x180009760  push    r14
0x180009762  push    r15
0x180009764  mov     rbp, rsp
0x180009767  sub     rsp, 70h
0x18000976b  mov     rax, cs:__security_cookie
0x180009772  xor     rax, rsp
0x180009775  mov     [rbp+var_8], rax
0x180009779  xor     eax, eax
0x18000977b  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x180009783  mov     rdi, rcx
0x180009786  mov     [rbp+var_18], rax
0x18000978a  xor     esi, esi
0x18000978c  mov     [rbp+var_10], eax
0x18000978f  lea     r15, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180009796  mov     [rbp+var_20], sil
0x18000979a  lea     rcx, [rbp+var_30]; this
0x18000979e  mov     [rbp+var_30], r15
0x1800097a2  xor     r14d, r14d
0x1800097a5  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x1800097aa  mov     ebx, eax
0x1800097ac  test    eax, eax
0x1800097ae  js      short loc_1800097E7
0x1800097b0  mov     [rsp+70h+var_40], rsi; unsigned int *
0x1800097b5  lea     rax, [rbp+var_18]
0x1800097b9  mov     [rsp+70h+var_48], 0Ch; DWORD
0x1800097c1  lea     rcx, [rbp+var_30]; this
0x1800097c5  xor     r9d, r9d; unsigned int
0x1800097c8  mov     [rsp+70h+var_50], rax; void *
0x1800097cd  xor     r8d, r8d; void *
0x1800097d0  mov     edx, 2D1080h; unsigned int
0x1800097d5  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x1800097da  mov     ebx, eax
0x1800097dc  test    eax, eax
0x1800097de  js      short loc_1800097E7
0x1800097e0  mov     esi, dword ptr [rbp+var_18+4]
0x1800097e3  mov     r14d, [rbp+var_10]
0x1800097e7  lea     rcx, [rbp+var_30]; this
0x1800097eb  mov     [rbp+var_30], r15
0x1800097ef  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x1800097f4  test    ebx, ebx
0x1800097f6  js      short loc_180009819
0x1800097f8  mov     edx, esi; unsigned int
0x1800097fa  mov     rcx, rdi; this
0x1800097fd  call    ?set_DiskNumber@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_DiskNumber(ulong)
0x180009802  mov     ebx, eax
0x180009804  test    eax, eax
0x180009806  js      short loc_180009819
0x180009808  mov     edx, r14d; unsigned int
0x18000980b  mov     rcx, rdi; this
0x18000980e  call    ?set_PartitionNumber@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_PartitionNumber(ulong)
0x180009813  mov     ebx, eax
0x180009815  test    eax, eax
0x180009817  jns     short loc_180009820
0x180009819  mov     rax, [rdi+18h]
0x18000981d  mov     [rax+10h], ebx
0x180009820  mov     eax, ebx
0x180009822  mov     rcx, [rbp+var_8]
0x180009826  xor     rcx, rsp; StackCookie
0x180009829  call    __security_check_cookie
0x18000982e  mov     rbx, [rsp+70h+arg_10]
0x180009836  add     rsp, 70h
0x18000983a  pop     r15
0x18000983c  pop     r14
0x18000983e  pop     rdi
0x18000983f  pop     rsi
0x180009840  pop     rbp
0x180009841  retn
```
