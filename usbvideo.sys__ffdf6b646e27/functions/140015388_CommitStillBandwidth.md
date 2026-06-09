# CommitStillBandwidth

- ea: `0x140015388`
- end: `0x140015692`
- name: `CommitStillBandwidth`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400394cc`

## callees

- `0x140001544`
- `0x140015388`
- `0x1400166ac`
- `0x140016cd4`
- `0x14001709c`
- `0x14001d0cc`
- `0x140023c70`
- `0x14003a498`
- `0x14003a5b4`

## pseudocode

```c
__int64 __fastcall CommitStillBandwidth(__int64 a1, unsigned __int8 **a2, char a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // esi
  __int64 v11; // r8
  char v12; // al
  int v13; // edx
  __int64 OptimalAltSetting; // rax
  unsigned int v15; // ecx
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v18; // [rsp+A8h] [rbp+20h] BYREF

  v18 = 0;
  v6 = StillProbeCommitSetHandler((int)a2[53], 1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v9 = 108;
LABEL_44:
      WPP_SF_qqD(v8->AttachedDevice, v9, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, a2, v6);
      return v7;
    }
    return v7;
  }
  v10 = *(_DWORD *)((char *)a2 + 191);
  v17 = v10;
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v10 )
    {
      if ( (*a2)[3] )
      {
        if ( v10 <= 0xC000 )
        {
LABEL_14:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_qLdddddd(
              WPP_GLOBAL_Control->AttachedDevice,
              110,
              (*a2)[4],
              a2,
              v10,
              **a2,
              (*a2)[1],
              (*a2)[2],
              (*a2)[3],
              (*a2)[4],
              *((_DWORD *)*a2 + 2));
          goto LABEL_25;
        }
      }
      else if ( v10 <= 0x1800 )
      {
        goto LABEL_14;
      }
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qqLd(WPP_GLOBAL_Control->AttachedDevice, (*a2)[3], v11, a1, a2, v10, (*a2)[3]);
    goto LABEL_14;
  }
  if ( v10 )
  {
    if ( (*a2)[3] )
    {
      if ( v10 <= 0xC000 )
        goto LABEL_25;
    }
    else if ( v10 <= 0xC00 )
    {
      goto LABEL_25;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, a2, v10);
LABEL_25:
  v12 = *((_BYTE *)a2 + 377);
  if ( v12 == 2 )
  {
    v13 = *(_DWORD *)(136LL * *((unsigned int *)a2[52] + 6) + *((_QWORD *)*a2 + 93) + 8);
  }
  else
  {
    v13 = 0;
    if ( v12 == 3 )
      v13 = *((_DWORD *)a2[52] + 6);
  }
  LOBYTE(v11) = *((_BYTE *)a2 + 376);
  OptimalAltSetting = FindOptimalAltSetting((unsigned int)*a2, v13, v11, (unsigned int)&v17, (__int64)&v18);
  if ( !OptimalAltSetting )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, a2);
    return (unsigned int)-1073741823;
  }
  v15 = v18;
  *(_DWORD *)((char *)a2 + 191) = v17;
  if ( v15 > *((_DWORD *)a2 + 7) )
    return (unsigned int)-1073741823;
  *(_QWORD *)a2[2] = OptimalAltSetting;
  if ( a3 )
  {
    **(_QWORD **)(a1 + 16) = OptimalAltSetting;
    *((_DWORD *)a2 + 7) = v15;
    *(_DWORD *)(a1 + 28) = v15;
    v6 = SelectInterface(**(PVOID **)(a1 + 16));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 113;
        goto LABEL_44;
      }
    }
  }
  else
  {
    *((_DWORD *)a2 + 7) = v15;
    v6 = SelectInterface(*(PVOID *)a2[2]);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 114;
        goto LABEL_44;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140015388  mov     rax, rsp
0x14001538b  mov     [rax+8], rbx
0x14001538f  push    rsi
0x140015390  push    rdi
0x140015391  push    r13
0x140015393  push    r14
0x140015395  push    r15
0x140015397  sub     rsp, 60h
0x14001539b  mov     r13b, r8b
0x14001539e  mov     dword ptr [rax+20h], 0
0x1400153a5  mov     r8, [rdx+10h]
0x1400153a9  mov     r15, rcx
0x1400153ac  mov     rcx, [rdx+1A8h]; int
0x1400153b3  mov     rdi, rdx
0x1400153b6  mov     byte ptr [rax-68h], 1
0x1400153ba  call    StillProbeCommitSetHandler
0x1400153bf  mov     ebx, eax
0x1400153c1  test    eax, eax
0x1400153c3  jns     short loc_1400153F0
0x1400153c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153cc  lea     r14, WPP_GLOBAL_Control
0x1400153d3  cmp     rcx, r14
0x1400153d6  jz      loc_14001567A
0x1400153dc  cmp     byte ptr [rcx+29h], 3
0x1400153e0  jb      loc_14001567A
0x1400153e6  mov     edx, 6Ch ; 'l'
0x1400153eb  jmp     loc_14001565E
0x1400153f0  mov     esi, [rdi+0BFh]
0x1400153f6  mov     [rsp+88h+arg_8], esi
0x1400153fd  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x140015402  lea     r14, WPP_GLOBAL_Control
0x140015409  test    eax, eax
0x14001540b  jz      loc_1400154D0
0x140015411  test    esi, esi
0x140015413  jz      short loc_140015430
0x140015415  mov     rax, [rdi]
0x140015418  cmp     byte ptr [rax+3], 0
0x14001541c  jnz     short loc_140015428
0x14001541e  cmp     esi, 1800h
0x140015424  ja      short loc_140015430
0x140015426  jmp     short loc_140015466
0x140015428  cmp     esi, 0C000h
0x14001542e  jbe     short loc_140015466
0x140015430  mov     rcx, cs:WPP_GLOBAL_Control
0x140015437  cmp     rcx, r14
0x14001543a  jz      loc_140015522
0x140015440  cmp     byte ptr [rcx+29h], 3
0x140015444  jb      short loc_140015466
0x140015446  mov     rax, [rdi]
0x140015449  mov     r9, r15
0x14001544c  mov     rcx, [rcx+18h]
0x140015450  movzx   edx, byte ptr [rax+3]
0x140015454  mov     [rsp+88h+var_58], edx
0x140015458  mov     [rsp+88h+var_60], esi
0x14001545c  mov     [rsp+88h+var_68], rdi
0x140015461  call    WPP_SF_qqLd
0x140015466  mov     rcx, cs:WPP_GLOBAL_Control
0x14001546d  cmp     rcx, r14
0x140015470  jz      loc_140015522
0x140015476  cmp     byte ptr [rcx+29h], 4
0x14001547a  jb      loc_140015522
0x140015480  mov     rax, [rdi]
0x140015483  mov     edx, 6Eh ; 'n'
0x140015488  mov     rcx, [rcx+18h]
0x14001548c  movzx   r9d, byte ptr [rax+3]
0x140015491  movzx   r8d, byte ptr [rax+4]
0x140015496  movzx   r10d, byte ptr [rax+2]
0x14001549b  movzx   r11d, byte ptr [rax+1]
0x1400154a0  movzx   ebx, byte ptr [rax]
0x1400154a3  mov     eax, [rax+8]
0x1400154a6  mov     [rsp+88h+var_38], eax
0x1400154aa  mov     [rsp+88h+var_40], r8d
0x1400154af  mov     [rsp+88h+var_48], r9d
0x1400154b4  mov     r9, rdi
0x1400154b7  mov     [rsp+88h+var_50], r10d
0x1400154bc  mov     [rsp+88h+var_58], r11d
0x1400154c1  mov     [rsp+88h+var_60], ebx
0x1400154c5  mov     dword ptr [rsp+88h+var_68], esi
0x1400154c9  call    WPP_SF_qLdddddd
0x1400154ce  jmp     short loc_140015522
0x1400154d0  test    esi, esi
0x1400154d2  jz      short loc_1400154EF
0x1400154d4  mov     rax, [rdi]
0x1400154d7  cmp     byte ptr [rax+3], 0
0x1400154db  jnz     short loc_1400154E7
0x1400154dd  cmp     esi, 0C00h
0x1400154e3  ja      short loc_1400154EF
0x1400154e5  jmp     short loc_140015522
0x1400154e7  cmp     esi, 0C000h
0x1400154ed  jbe     short loc_140015522
0x1400154ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154f6  cmp     rcx, r14
0x1400154f9  jz      short loc_140015522
0x1400154fb  cmp     byte ptr [rcx+29h], 3
0x1400154ff  jb      short loc_140015522
0x140015501  mov     rcx, [rcx+18h]
0x140015505  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14001550c  mov     edx, 6Fh ; 'o'
0x140015511  mov     [rsp+88h+var_60], esi
0x140015515  mov     r9, r15
0x140015518  mov     [rsp+88h+var_68], rdi
0x14001551d  call    WPP_SF_qqD
0x140015522  mov     al, [rdi+179h]
0x140015528  cmp     al, 2
0x14001552a  jnz     short loc_14001554D
0x14001552c  mov     rax, [rdi+1A0h]
0x140015533  mov     ecx, [rax+18h]
0x140015536  mov     rax, [rdi]
0x140015539  imul    rdx, rcx, 88h
0x140015540  mov     rcx, [rax+2E8h]
0x140015547  mov     edx, [rdx+rcx+8]
0x14001554b  jmp     short loc_14001555D
0x14001554d  xor     edx, edx
0x14001554f  cmp     al, 3
0x140015551  jnz     short loc_14001555D
0x140015553  mov     rax, [rdi+1A0h]
0x14001555a  mov     edx, [rax+18h]
0x14001555d  mov     r8b, [rdi+178h]
0x140015564  lea     rax, [rsp+88h+arg_18]
0x14001556c  mov     rcx, [rdi]
0x14001556f  lea     r9, [rsp+88h+arg_8]
0x140015577  mov     [rsp+88h+var_68], rax
0x14001557c  call    FindOptimalAltSetting
0x140015581  mov     rdx, rax
0x140015584  test    rax, rax
0x140015587  jnz     short loc_1400155C0
0x140015589  mov     rcx, cs:WPP_GLOBAL_Control
0x140015590  cmp     rcx, r14
0x140015593  jz      short loc_1400155B6
0x140015595  cmp     byte ptr [rcx+29h], 3
0x140015599  jb      short loc_1400155B6
0x14001559b  mov     rcx, [rcx+18h]
0x14001559f  lea     edx, [rax+70h]
0x1400155a2  mov     r9, r15
0x1400155a5  mov     [rsp+88h+var_68], rdi
0x1400155aa  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400155b1  call    WPP_SF_qq
0x1400155b6  mov     ebx, 0C0000001h
0x1400155bb  jmp     loc_14001567A
0x1400155c0  mov     ecx, [rsp+88h+arg_18]
0x1400155c7  mov     eax, [rsp+88h+arg_8]
0x1400155ce  mov     [rdi+0BFh], eax
0x1400155d4  cmp     ecx, [rdi+1Ch]
0x1400155d7  ja      short loc_1400155B6
0x1400155d9  mov     rax, [rdi+10h]
0x1400155dd  mov     [rax], rdx
0x1400155e0  test    r13b, r13b
0x1400155e3  jz      short loc_140015628
0x1400155e5  mov     rax, [r15+10h]
0x1400155e9  mov     [rax], rdx
0x1400155ec  mov     [rdi+1Ch], ecx
0x1400155ef  mov     r8, [r15+1A0h]
0x1400155f6  mov     rdx, [r15]
0x1400155f9  mov     [r15+1Ch], ecx
0x1400155fd  mov     rcx, [r15+10h]
0x140015601  mov     rcx, [rcx]; StartPosition
0x140015604  call    SelectInterface
0x140015609  mov     ebx, eax
0x14001560b  test    eax, eax
0x14001560d  jns     short loc_14001567A
0x14001560f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015616  cmp     rcx, r14
0x140015619  jz      short loc_14001567A
0x14001561b  cmp     byte ptr [rcx+29h], 3
0x14001561f  jb      short loc_14001567A
0x140015621  mov     edx, 71h ; 'q'
0x140015626  jmp     short loc_14001565E
0x140015628  mov     r8, [rdi+1A0h]
0x14001562f  mov     rdx, [rdi]
0x140015632  mov     [rdi+1Ch], ecx
0x140015635  mov     rcx, [rdi+10h]
0x140015639  mov     rcx, [rcx]; StartPosition
0x14001563c  call    SelectInterface
0x140015641  mov     ebx, eax
0x140015643  test    eax, eax
0x140015645  jns     short loc_14001567A
0x140015647  mov     rcx, cs:WPP_GLOBAL_Control
0x14001564e  cmp     rcx, r14
0x140015651  jz      short loc_14001567A
0x140015653  cmp     byte ptr [rcx+29h], 3
0x140015657  jb      short loc_14001567A
0x140015659  mov     edx, 72h ; 'r'
0x14001565e  mov     rcx, [rcx+18h]
0x140015662  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140015669  mov     [rsp+88h+var_60], eax
0x14001566d  mov     r9, r15
0x140015670  mov     [rsp+88h+var_68], rdi
0x140015675  call    WPP_SF_qqD
0x14001567a  mov     eax, ebx
0x14001567c  mov     rbx, [rsp+88h+arg_0]
0x140015684  add     rsp, 60h
0x140015688  pop     r15
0x14001568a  pop     r14
0x14001568c  pop     r13
0x14001568e  pop     rdi
0x14001568f  pop     rsi
0x140015690  retn
```
