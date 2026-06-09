# CommitVideoBandwidth

- ea: `0x14000b57c`
- end: `0x14000b7f4`
- name: `CommitVideoBandwidth`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b260`

## callees

- `0x14000a4b4`
- `0x14000b57c`
- `0x1400166ac`
- `0x140016cd4`
- `0x14001709c`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14003a430`
- `0x14003a498`

## pseudocode

```c
__int64 __fastcall CommitVideoBandwidth(unsigned __int8 **a1)
{
  unsigned __int8 *v1; // r9
  __int64 v3; // r8
  unsigned __int8 *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // esi
  __int64 v11; // r8
  __int64 OptimalAltSetting; // rcx
  unsigned int v14; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+10h] BYREF

  v1 = a1[52];
  v3 = (__int64)a1[2];
  v5 = a1[53];
  v15 = 0;
  v6 = ProbeCommitSetHandler((int)v5, (__int64)a1, v3, *((_QWORD *)v1 + 12), 1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v9 = 100;
LABEL_35:
      WPP_SF_qD(v8->AttachedDevice, v9, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, v6);
      return v7;
    }
    return v7;
  }
  v10 = *(_DWORD *)((char *)a1 + 206);
  v14 = v10;
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v10 )
    {
      if ( !(*a1)[3] )
      {
        if ( v10 > 0x1800 )
          goto LABEL_11;
LABEL_14:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_qLdddddd(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            (*a1)[4],
            a1,
            v10,
            **a1,
            (*a1)[1],
            (*a1)[2],
            (*a1)[3],
            (*a1)[4],
            *((_DWORD *)*a1 + 2));
        goto LABEL_25;
      }
      if ( v10 <= 0xC000 )
        goto LABEL_14;
    }
LABEL_11:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_25;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, (*a1)[3], v11, a1, v10, (*a1)[3]);
    goto LABEL_14;
  }
  if ( v10 )
  {
    if ( (*a1)[3] )
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
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1, v10);
LABEL_25:
  LOBYTE(v11) = *((_BYTE *)a1 + 376);
  OptimalAltSetting = FindOptimalAltSetting(
                        (unsigned int)*a1,
                        *((_DWORD *)a1[52] + 6),
                        v11,
                        (unsigned int)&v14,
                        (__int64)&v15);
  if ( !OptimalAltSetting )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, a1);
    return (unsigned int)-1073741823;
  }
  *(_DWORD *)((char *)a1 + 206) = v14;
  if ( v15 > *((_DWORD *)a1 + 7) )
    return (unsigned int)-1073741823;
  *((_DWORD *)a1 + 7) = v15;
  *(_QWORD *)a1[2] = OptimalAltSetting;
  v6 = SelectInterface(*(PVOID *)a1[2]);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v9 = 105;
      goto LABEL_35;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000b57c  mov     rax, rsp
0x14000b57f  mov     [rax+18h], rbx
0x14000b583  push    rbp
0x14000b584  push    rsi
0x14000b585  push    rdi
0x14000b586  sub     rsp, 60h
0x14000b58a  mov     r9, [rcx+1A0h]
0x14000b591  mov     rdi, rcx
0x14000b594  mov     r8, [rcx+10h]
0x14000b598  mov     rdx, rcx
0x14000b59b  mov     rcx, [rcx+1A8h]; int
0x14000b5a2  mov     dword ptr [rax+10h], 0
0x14000b5a9  mov     r9, [r9+60h]
0x14000b5ad  mov     byte ptr [rax-58h], 1
0x14000b5b1  call    ProbeCommitSetHandler
0x14000b5b6  mov     ebx, eax
0x14000b5b8  test    eax, eax
0x14000b5ba  jns     short loc_14000B5E7
0x14000b5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5c3  lea     rbp, WPP_GLOBAL_Control
0x14000b5ca  cmp     rcx, rbp
0x14000b5cd  jz      loc_14000B7E1
0x14000b5d3  cmp     byte ptr [rcx+29h], 3
0x14000b5d7  jb      loc_14000B7E1
0x14000b5dd  mov     edx, 64h ; 'd'
0x14000b5e2  jmp     loc_14000B7CA
0x14000b5e7  mov     esi, [rdi+0CEh]
0x14000b5ed  mov     [rsp+78h+arg_0], esi
0x14000b5f4  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14000b5f9  lea     rbp, WPP_GLOBAL_Control
0x14000b600  test    eax, eax
0x14000b602  jz      loc_14000B6C2
0x14000b608  test    esi, esi
0x14000b60a  jz      short loc_14000B627
0x14000b60c  mov     rax, [rdi]
0x14000b60f  cmp     byte ptr [rax+3], 0
0x14000b613  jnz     short loc_14000B61F
0x14000b615  cmp     esi, 1800h
0x14000b61b  jbe     short loc_14000B658
0x14000b61d  jmp     short loc_14000B627
0x14000b61f  cmp     esi, 0C000h
0x14000b625  jbe     short loc_14000B658
0x14000b627  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b62e  cmp     rcx, rbp
0x14000b631  jz      loc_14000B70F
0x14000b637  cmp     byte ptr [rcx+29h], 3
0x14000b63b  jb      short loc_14000B658
0x14000b63d  mov     rax, [rdi]
0x14000b640  mov     r9, rdi
0x14000b643  mov     rcx, [rcx+18h]
0x14000b647  movzx   edx, byte ptr [rax+3]
0x14000b64b  mov     [rsp+78h+var_50], edx
0x14000b64f  mov     dword ptr [rsp+78h+var_58], esi
0x14000b653  call    WPP_SF_qLd
0x14000b658  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b65f  cmp     rcx, rbp
0x14000b662  jz      loc_14000B70F
0x14000b668  cmp     byte ptr [rcx+29h], 4
0x14000b66c  jb      loc_14000B70F
0x14000b672  mov     rax, [rdi]
0x14000b675  mov     edx, 66h ; 'f'
0x14000b67a  mov     rcx, [rcx+18h]
0x14000b67e  movzx   r9d, byte ptr [rax+3]
0x14000b683  movzx   r8d, byte ptr [rax+4]
0x14000b688  movzx   r10d, byte ptr [rax+2]
0x14000b68d  movzx   r11d, byte ptr [rax+1]
0x14000b692  movzx   ebx, byte ptr [rax]
0x14000b695  mov     eax, [rax+8]
0x14000b698  mov     [rsp+78h+var_28], eax
0x14000b69c  mov     [rsp+78h+var_30], r8d
0x14000b6a1  mov     [rsp+78h+var_38], r9d
0x14000b6a6  mov     r9, rdi
0x14000b6a9  mov     [rsp+78h+var_40], r10d
0x14000b6ae  mov     [rsp+78h+var_48], r11d
0x14000b6b3  mov     [rsp+78h+var_50], ebx
0x14000b6b7  mov     dword ptr [rsp+78h+var_58], esi
0x14000b6bb  call    WPP_SF_qLdddddd
0x14000b6c0  jmp     short loc_14000B70F
0x14000b6c2  test    esi, esi
0x14000b6c4  jz      short loc_14000B6E1
0x14000b6c6  mov     rax, [rdi]
0x14000b6c9  cmp     byte ptr [rax+3], 0
0x14000b6cd  jnz     short loc_14000B6D9
0x14000b6cf  cmp     esi, 0C00h
0x14000b6d5  jbe     short loc_14000B70F
0x14000b6d7  jmp     short loc_14000B6E1
0x14000b6d9  cmp     esi, 0C000h
0x14000b6df  jbe     short loc_14000B70F
0x14000b6e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6e8  cmp     rcx, rbp
0x14000b6eb  jz      short loc_14000B70F
0x14000b6ed  cmp     byte ptr [rcx+29h], 3
0x14000b6f1  jb      short loc_14000B70F
0x14000b6f3  mov     rcx, [rcx+18h]
0x14000b6f7  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000b6fe  mov     edx, 67h ; 'g'
0x14000b703  mov     dword ptr [rsp+78h+var_58], esi
0x14000b707  mov     r9, rdi
0x14000b70a  call    WPP_SF_qD
0x14000b70f  mov     rdx, [rdi+1A0h]
0x14000b716  lea     rax, [rsp+78h+arg_8]
0x14000b71e  mov     r8b, [rdi+178h]
0x14000b725  lea     r9, [rsp+78h+arg_0]
0x14000b72d  mov     rcx, [rdi]
0x14000b730  mov     [rsp+78h+var_58], rax
0x14000b735  mov     edx, [rdx+18h]
0x14000b738  call    FindOptimalAltSetting
0x14000b73d  mov     rcx, rax
0x14000b740  test    rax, rax
0x14000b743  jnz     short loc_14000B774
0x14000b745  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b74c  cmp     rcx, rbp
0x14000b74f  jz      short loc_14000B76D
0x14000b751  cmp     byte ptr [rcx+29h], 3
0x14000b755  jb      short loc_14000B76D
0x14000b757  mov     rcx, [rcx+18h]
0x14000b75b  lea     edx, [rax+68h]
0x14000b75e  mov     r9, rdi
0x14000b761  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000b768  call    WPP_SF_q
0x14000b76d  mov     ebx, 0C0000001h
0x14000b772  jmp     short loc_14000B7E1
0x14000b774  mov     eax, [rsp+78h+arg_0]
0x14000b77b  mov     [rdi+0CEh], eax
0x14000b781  mov     eax, [rsp+78h+arg_8]
0x14000b788  cmp     eax, [rdi+1Ch]
0x14000b78b  ja      short loc_14000B76D
0x14000b78d  mov     [rdi+1Ch], eax
0x14000b790  mov     rax, [rdi+10h]
0x14000b794  mov     [rax], rcx
0x14000b797  mov     rcx, [rdi+10h]
0x14000b79b  mov     r8, [rdi+1A0h]
0x14000b7a2  mov     rdx, [rdi]
0x14000b7a5  mov     rcx, [rcx]; StartPosition
0x14000b7a8  call    SelectInterface
0x14000b7ad  mov     ebx, eax
0x14000b7af  test    eax, eax
0x14000b7b1  jns     short loc_14000B7E1
0x14000b7b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7ba  cmp     rcx, rbp
0x14000b7bd  jz      short loc_14000B7E1
0x14000b7bf  cmp     byte ptr [rcx+29h], 3
0x14000b7c3  jb      short loc_14000B7E1
0x14000b7c5  mov     edx, 69h ; 'i'
0x14000b7ca  mov     rcx, [rcx+18h]
0x14000b7ce  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000b7d5  mov     r9, rdi
0x14000b7d8  mov     dword ptr [rsp+78h+var_58], eax
0x14000b7dc  call    WPP_SF_qD
0x14000b7e1  mov     eax, ebx
0x14000b7e3  mov     rbx, [rsp+78h+arg_10]
0x14000b7eb  add     rsp, 60h
0x14000b7ef  pop     rdi
0x14000b7f0  pop     rsi
0x14000b7f1  pop     rbp
0x14000b7f2  retn
```
