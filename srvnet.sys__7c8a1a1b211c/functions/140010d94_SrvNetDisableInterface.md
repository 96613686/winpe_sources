# SrvNetDisableInterface

- ea: `0x140010d94`
- end: `0x140011116`
- name: `SrvNetDisableInterface`
- size: `898`
- prototype: `__int64 __fastcall(void *Source2)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400478f0`
- `0x140052a3c`

## callees

- `0x14000d560`
- `0x14000e064`
- `0x14000e734`
- `0x140010d94`
- `0x1400133b8`
- `0x14001389c`
- `0x140015790`
- `0x14001ac0c`
- `0x14001ae14`
- `0x14001aecc`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140010e81`
- `ntoskrnl!RtlCompareMemory` at `0x140010e81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400110f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400110f0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010dd8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010ecc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010dd8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010ecc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010dc3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010dc3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400110d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400110e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400110d1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400110e4`

## pseudocode

```c
__int64 __fastcall SrvNetDisableInterface(void *Source2, char a2, char a3)
{
  int v6; // r15d
  char *v7; // rdi
  char *v8; // rdx
  unsigned int v9; // edx
  char *v10; // r9
  unsigned int v11; // esi
  __int64 v12; // rbx
  char v13; // r14
  bool v14; // bp
  char v15; // si
  void *v16; // rdx
  int v17; // r9d
  int v18; // eax
  bool v19; // zf
  int v20; // eax
  PERESOURCE v21; // rcx
  PVOID *p_Reserved2; // rax
  PVOID *Reserved2; // rbx
  PDEVICE_OBJECT v24; // rcx
  unsigned int v25; // ecx
  __int64 v26; // rax
  unsigned int v28; // [rsp+A8h] [rbp+20h] BYREF

  v28 = 0;
  v6 = SrvNetConvertInterfaceGuidToIndex(Source2, &v28);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
  v7 = 0;
  if ( v6 < 0 )
  {
    v11 = 0;
    if ( SrvNetInterfaces )
    {
      while ( 1 )
      {
        v12 = 32LL * v11;
        if ( *((_BYTE *)Src + v12 + 29) )
        {
          if ( RtlCompareMemory((char *)Src + v12 + 4, Source2, 0x10u) == 16 )
            break;
        }
        if ( ++v11 >= SrvNetInterfaces )
          goto LABEL_18;
      }
      v7 = (char *)Src + v12;
    }
  }
  else if ( v28 >= SrvNetInterfaces
         || (v8 = (char *)Src + 32 * v28, !v8[29])
         || *(_DWORD *)v8 != v28
         || (v7 = (char *)Src + 32 * v28, !v8) )
  {
    v9 = 0;
    if ( SrvNetInterfaces )
    {
      while ( 1 )
      {
        v10 = (char *)Src + 32 * v9;
        if ( v10[29] )
        {
          if ( *(_DWORD *)v10 == v28 )
            break;
        }
        if ( ++v9 >= SrvNetInterfaces )
          goto LABEL_18;
      }
      v7 = (char *)Src + 32 * v9;
    }
  }
LABEL_18:
  if ( v7 )
  {
    v13 = 1;
    v14 = 0;
    v15 = 0;
    ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
    if ( a2 )
    {
      if ( *((_DWORD *)v7 + 5) )
      {
        v18 = SrvNetCountInterfacesForUniversalEndpoints((ULONG_PTR)v7);
        v19 = *((_DWORD *)v7 + 5) == v18;
        *((_DWORD *)v7 + 5) -= v18;
        v14 = v19;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids, v28);
      }
    }
    if ( a3 )
    {
      if ( *((_DWORD *)v7 + 6) )
      {
        v20 = SrvNetCountInterfacesForUniversalEndpoints((ULONG_PTR)v7);
        v19 = *((_DWORD *)v7 + 6) == v20;
        *((_DWORD *)v7 + 6) -= v20;
        v15 = v19;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids, v28);
      }
    }
    v21 = SrvNetDeviceExtension;
    p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
    Reserved2 = (PVOID *)SrvNetDeviceExtension[3].Reserved2;
    while ( Reserved2 != p_Reserved2 )
    {
      if ( *((_BYTE *)Reserved2 + 120) )
      {
        if ( a2 )
          SrvNetFindAndFreeInterfaceTableEntry(Reserved2, v7, 0);
        if ( a3 )
          SrvNetFindAndFreeInterfaceTableEntry(Reserved2, v7, 1);
        if ( v14 || v15 )
        {
          if ( *((_BYTE *)Reserved2 + 148) )
          {
            LOBYTE(v17) = v14;
            v6 = SrvNetWskTwiddleInterface((_DWORD)Reserved2, v28, 30, v17, v15);
          }
          else
          {
            v6 = 0;
          }
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids);
          }
          SrvNetUpdateIPAddressList(v24, v16);
        }
        SrvNetRefreshRdmaStateOnInterface(v28);
        if ( *((_BYTE *)Reserved2 + 148) )
        {
          if ( *((_BYTE *)Reserved2 + 147) )
          {
            v25 = 0;
            if ( SrvNetInterfaces )
            {
              while ( 1 )
              {
                v16 = Src;
                v26 = 32LL * v25;
                if ( *((_BYTE *)Src + v26 + 29) )
                {
                  if ( *(_DWORD *)((char *)Src + v26 + 20) || *(_DWORD *)((char *)Src + v26 + 24) )
                    break;
                }
                if ( ++v25 >= SrvNetInterfaces )
                  goto LABEL_56;
              }
              v13 = 0;
            }
            else
            {
LABEL_56:
              if ( v13 )
                SrvNetDisableImplicitLoopbackInterface(Reserved2);
            }
          }
        }
      }
      v21 = SrvNetDeviceExtension;
      Reserved2 = (PVOID *)*Reserved2;
      p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
    }
    ExReleaseResourceLite((PERESOURCE)((char *)v21 + 288));
  }
  ExReleaseResourceLite(SrvNetDeviceExtension);
  KeLeaveCriticalRegion();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140010d94  mov     rax, rsp
0x140010d97  push    rbx
0x140010d98  push    rbp
0x140010d99  push    rsi
0x140010d9a  push    rdi
0x140010d9b  push    r12
0x140010d9d  push    r13
0x140010d9f  push    r14
0x140010da1  push    r15
0x140010da3  sub     rsp, 48h
0x140010da7  mov     r13b, dl
0x140010daa  mov     dword ptr [rax+20h], 0
0x140010db1  lea     rdx, [rax+20h]
0x140010db5  mov     r12b, r8b
0x140010db8  mov     rbp, rcx
0x140010dbb  call    SrvNetConvertInterfaceGuidToIndex
0x140010dc0  mov     r15d, eax
0x140010dc3  call    cs:__imp_KeEnterCriticalRegion
0x140010dca  nop     dword ptr [rax+rax+00h]
0x140010dcf  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140010dd6  mov     dl, 1; Wait
0x140010dd8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140010ddf  nop     dword ptr [rax+rax+00h]
0x140010de4  xor     edi, edi
0x140010de6  test    r15d, r15d
0x140010de9  js      short loc_140010E53
0x140010deb  mov     r8d, [rsp+88h+arg_18]
0x140010df3  mov     r10d, cs:SrvNetInterfaces
0x140010dfa  cmp     r8d, r10d
0x140010dfd  jnb     short loc_140010E24
0x140010dff  mov     edx, r8d
0x140010e02  shl     rdx, 5
0x140010e06  add     rdx, cs:Src
0x140010e0d  cmp     [rdx+1Dh], dil
0x140010e11  jz      short loc_140010E24
0x140010e13  cmp     [rdx], r8d
0x140010e16  jnz     short loc_140010E24
0x140010e18  mov     rdi, rdx
0x140010e1b  test    rdx, rdx
0x140010e1e  jnz     loc_140010EA9
0x140010e24  xor     edx, edx
0x140010e26  test    r10d, r10d
0x140010e29  jz      short loc_140010EA9
0x140010e2b  mov     r9d, edx
0x140010e2e  shl     r9, 5
0x140010e32  add     r9, cs:Src
0x140010e39  cmp     byte ptr [r9+1Dh], 0
0x140010e3e  jz      short loc_140010E45
0x140010e40  cmp     [r9], r8d
0x140010e43  jz      short loc_140010E4E
0x140010e45  inc     edx
0x140010e47  cmp     edx, r10d
0x140010e4a  jb      short loc_140010E2B
0x140010e4c  jmp     short loc_140010EA9
0x140010e4e  mov     rdi, r9
0x140010e51  jmp     short loc_140010EA9
0x140010e53  xor     esi, esi
0x140010e55  cmp     cs:SrvNetInterfaces, esi
0x140010e5b  jz      short loc_140010EA9
0x140010e5d  mov     rax, cs:Src
0x140010e64  mov     ebx, esi
0x140010e66  shl     rbx, 5
0x140010e6a  cmp     [rbx+rax+1Dh], dil
0x140010e6f  jz      short loc_140010E93
0x140010e71  lea     rcx, [rax+4]
0x140010e75  mov     r8d, 10h; Length
0x140010e7b  add     rcx, rbx; Source1
0x140010e7e  mov     rdx, rbp; Source2
0x140010e81  call    cs:__imp_RtlCompareMemory
0x140010e88  nop     dword ptr [rax+rax+00h]
0x140010e8d  cmp     rax, 10h
0x140010e91  jz      short loc_140010E9F
0x140010e93  inc     esi
0x140010e95  cmp     esi, cs:SrvNetInterfaces
0x140010e9b  jb      short loc_140010E5D
0x140010e9d  jmp     short loc_140010EA9
0x140010e9f  mov     rdi, cs:Src
0x140010ea6  add     rdi, rbx
0x140010ea9  test    rdi, rdi
0x140010eac  jz      loc_1400110DD
0x140010eb2  mov     rcx, cs:SrvNetDeviceExtension
0x140010eb9  mov     r14b, 1
0x140010ebc  add     rcx, 120h; Resource
0x140010ec3  mov     dl, r14b; Wait
0x140010ec6  xor     bpl, bpl
0x140010ec9  xor     sil, sil
0x140010ecc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140010ed3  nop     dword ptr [rax+rax+00h]
0x140010ed8  lea     rax, WPP_GLOBAL_Control
0x140010edf  test    r13b, r13b
0x140010ee2  jz      short loc_140010F3A
0x140010ee4  cmp     dword ptr [rdi+14h], 0
0x140010ee8  jz      short loc_140010EFD
0x140010eea  xor     edx, edx
0x140010eec  mov     rcx, rdi; Signature
0x140010eef  call    SrvNetCountInterfacesForUniversalEndpoints
0x140010ef4  sub     [rdi+14h], eax
0x140010ef7  setz    bpl
0x140010efb  jmp     short loc_140010F33
0x140010efd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010f04  cmp     rcx, rax
0x140010f07  jz      short loc_140010F3A
0x140010f09  mov     eax, [rcx+2Ch]
0x140010f0c  test    al, 10h
0x140010f0e  jz      short loc_140010F33
0x140010f10  cmp     byte ptr [rcx+29h], 2
0x140010f14  jb      short loc_140010F33
0x140010f16  mov     r9d, [rsp+88h+arg_18]
0x140010f1e  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140010f25  mov     rcx, [rcx+18h]
0x140010f29  mov     edx, 2Ah ; '*'
0x140010f2e  call    WPP_SF_d
0x140010f33  lea     rax, WPP_GLOBAL_Control
0x140010f3a  test    r12b, r12b
0x140010f3d  jz      short loc_140010F91
0x140010f3f  cmp     dword ptr [rdi+18h], 0
0x140010f43  jz      short loc_140010F5B
0x140010f45  mov     edx, 1
0x140010f4a  mov     rcx, rdi; Signature
0x140010f4d  call    SrvNetCountInterfacesForUniversalEndpoints
0x140010f52  sub     [rdi+18h], eax
0x140010f55  setz    sil
0x140010f59  jmp     short loc_140010F91
0x140010f5b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010f62  cmp     rcx, rax
0x140010f65  jz      short loc_140010F91
0x140010f67  mov     eax, [rcx+2Ch]
0x140010f6a  test    al, 10h
0x140010f6c  jz      short loc_140010F91
0x140010f6e  cmp     byte ptr [rcx+29h], 2
0x140010f72  jb      short loc_140010F91
0x140010f74  mov     r9d, [rsp+88h+arg_18]
0x140010f7c  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140010f83  mov     rcx, [rcx+18h]
0x140010f87  mov     edx, 2Bh ; '+'
0x140010f8c  call    WPP_SF_d
0x140010f91  mov     rcx, cs:SrvNetDeviceExtension
0x140010f98  lea     rax, [rcx+188h]
0x140010f9f  mov     rbx, [rax]
0x140010fa2  jmp     loc_1400110C1
0x140010fa7  cmp     byte ptr [rbx+78h], 0
0x140010fab  jz      loc_1400110B0
0x140010fb1  test    r13b, r13b
0x140010fb4  jz      short loc_140010FC4
0x140010fb6  xor     r8d, r8d
0x140010fb9  mov     rdx, rdi
0x140010fbc  mov     rcx, rbx
0x140010fbf  call    SrvNetFindAndFreeInterfaceTableEntry
0x140010fc4  test    r12b, r12b
0x140010fc7  jz      short loc_140010FDA
0x140010fc9  mov     r8d, 1
0x140010fcf  mov     rdx, rdi
0x140010fd2  mov     rcx, rbx
0x140010fd5  call    SrvNetFindAndFreeInterfaceTableEntry
0x140010fda  test    bpl, bpl
0x140010fdd  jnz     short loc_140010FE4
0x140010fdf  test    sil, sil
0x140010fe2  jz      short loc_14001104E
0x140010fe4  cmp     byte ptr [rbx+94h], 0
0x140010feb  jz      short loc_14001100F
0x140010fed  mov     edx, [rsp+88h+arg_18]
0x140010ff4  mov     r9b, bpl
0x140010ff7  mov     r8d, 1Eh
0x140010ffd  mov     [rsp+88h+var_68], sil
0x140011002  mov     rcx, rbx
0x140011005  call    SrvNetWskTwiddleInterface
0x14001100a  mov     r15d, eax
0x14001100d  jmp     short loc_140011012
0x14001100f  xor     r15d, r15d
0x140011012  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011019  lea     rax, WPP_GLOBAL_Control
0x140011020  cmp     rcx, rax
0x140011023  jz      short loc_140011049
0x140011025  test    dword ptr [rcx+2Ch], 2000h
0x14001102c  jz      short loc_140011049
0x14001102e  cmp     byte ptr [rcx+29h], 2
0x140011032  jb      short loc_140011049
0x140011034  mov     rcx, [rcx+18h]
0x140011038  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x14001103f  mov     edx, 2Ch ; ','
0x140011044  call    WPP_SF_
0x140011049  call    SrvNetUpdateIPAddressList
0x14001104e  mov     ecx, [rsp+88h+arg_18]
0x140011055  call    SrvNetRefreshRdmaStateOnInterface
0x14001105a  cmp     byte ptr [rbx+94h], 0
0x140011061  jz      short loc_1400110B0
0x140011063  cmp     byte ptr [rbx+93h], 0
0x14001106a  jz      short loc_1400110B0
0x14001106c  mov     r8d, cs:SrvNetInterfaces
0x140011073  xor     ecx, ecx
0x140011075  test    r8d, r8d
0x140011078  jz      short loc_1400110A3
0x14001107a  mov     rdx, cs:Src
0x140011081  mov     eax, ecx
0x140011083  shl     rax, 5
0x140011087  cmp     byte ptr [rax+rdx+1Dh], 0
0x14001108c  jz      short loc_14001109C
0x14001108e  cmp     dword ptr [rax+rdx+14h], 0
0x140011093  jnz     short loc_140011111
0x140011095  cmp     dword ptr [rax+rdx+18h], 0
0x14001109a  jnz     short loc_140011111
0x14001109c  inc     ecx
0x14001109e  cmp     ecx, r8d
0x1400110a1  jb      short loc_14001107A
0x1400110a3  test    r14b, r14b
0x1400110a6  jz      short loc_1400110B0
0x1400110a8  mov     rcx, rbx
0x1400110ab  call    SrvNetDisableImplicitLoopbackInterface
0x1400110b0  mov     rcx, cs:SrvNetDeviceExtension
0x1400110b7  mov     rbx, [rbx]
0x1400110ba  lea     rax, [rcx+188h]
0x1400110c1  cmp     rbx, rax
0x1400110c4  jnz     loc_140010FA7
0x1400110ca  add     rcx, 120h; Resource
0x1400110d1  call    cs:__imp_ExReleaseResourceLite
0x1400110d8  nop     dword ptr [rax+rax+00h]
0x1400110dd  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x1400110e4  call    cs:__imp_ExReleaseResourceLite
0x1400110eb  nop     dword ptr [rax+rax+00h]
0x1400110f0  call    cs:__imp_KeLeaveCriticalRegion
0x1400110f7  nop     dword ptr [rax+rax+00h]
0x1400110fc  mov     eax, r15d
0x1400110ff  add     rsp, 48h
0x140011103  pop     r15
0x140011105  pop     r14
0x140011107  pop     r13
0x140011109  pop     r12
0x14001110b  pop     rdi
0x14001110c  pop     rsi
0x14001110d  pop     rbp
0x14001110e  pop     rbx
0x14001110f  retn
0x140011111  xor     r14b, r14b
0x140011114  jmp     short loc_1400110B0
```
