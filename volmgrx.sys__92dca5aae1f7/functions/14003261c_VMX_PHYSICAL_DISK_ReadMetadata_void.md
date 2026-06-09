# VMX_PHYSICAL_DISK::ReadMetadata(void)

- ea: `0x14003261c`
- end: `0x14003292a`
- name: `?ReadMetadata@VMX_PHYSICAL_DISK@@QEAAXXZ`
- size: `782`
- prototype: `void __fastcall(VMX_PHYSICAL_DISK *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14002f1e4`

## callees

- `0x14001b960`
- `0x140031648`
- `0x14003261c`
- `0x140032930`
- `0x140033958`
- `0x140043340`
- `0x140045ed0`
- `0x1400462ec`
- `0x140047924`
- `0x140059528`
- `0x14005c600`
- `0x14005d40c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140032824`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032824`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400328fe`

## pseudocode

```c
void __fastcall VMX_PHYSICAL_DISK::ReadMetadata(VMX_PHYSICAL_DISK *this)
{
  __int64 v1; // r8
  unsigned __int64 v3; // rdi
  VMX_DISK_DEVICE *v4; // r8
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  _DWORD *v7; // r8
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // rax
  _DWORD *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  _DWORD *v19; // rax
  __int64 v20; // rax
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned int v23; // r9d
  __int64 v24; // rcx
  __int64 v25; // rax
  VMX_CONFIG_COPY *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  struct VMX_PACK *PackById; // rax
  unsigned __int64 v30; // [rsp+20h] [rbp-58h] BYREF
  PVOID P; // [rsp+28h] [rbp-50h] BYREF
  struct _GUID v32; // [rsp+30h] [rbp-48h] BYREF
  char v33[32]; // [rsp+40h] [rbp-38h] BYREF

  v1 = *((_QWORD *)this + 2);
  v30 = 0;
  P = 0;
  v32 = 0;
  v3 = *(unsigned int *)(v1 + 36);
  if ( !VmxpSupportedBytesPerSector(*(_DWORD *)(v1 + 36)) )
    return;
  if ( (int)VMX_DISK_DEVICE::GetLengthInfo(v4, &v30) < 0 )
    return;
  v5 = (unsigned int)v3;
  v6 = v30 / v3;
  if ( (int)VMX_DISK_DEVICE::GetDriveLayoutEx(
              *((VMX_DISK_DEVICE **)this + 2),
              (struct _DRIVE_LAYOUT_INFORMATION_EX **)&P) < 0 )
    return;
  v7 = P;
  *((_DWORD *)this + 6) = *(_DWORD *)P;
  if ( !*v7 )
  {
    v8 = 0;
    *((_DWORD *)this + 7) = v7[2];
    while ( (unsigned int)v8 < v7[1] )
    {
      v9 = LOBYTE(v7[36 * v8 + 20]);
      if ( (_BYTE)v9 != 0xA0 && (_BYTE)v9 != 0x84 && (_BYTE)v9 != 66 )
      {
        if ( (unsigned __int8)v9 > 0x27u || (v10 = 0x8000048021LL, !_bittest64(&v10, v9)) )
        {
          LOBYTE(v9) = v9 + 34;
          if ( (unsigned __int8)v9 > 0x20u )
            goto LABEL_48;
          v11 = 0x100000201LL;
          if ( !_bittest64(&v11, v9) )
            goto LABEL_48;
        }
      }
      v8 = (unsigned int)(v8 + 1);
    }
    v12 = v5 * v6;
    if ( v12 > 0x18000 )
    {
      *((_QWORD *)this + 10) = 6;
      v13 = (v12 - 98304) / v5;
      v14 = v12 - v5;
      goto LABEL_33;
    }
LABEL_48:
    ExFreePoolWithTag(v7, 0);
    return;
  }
  if ( *v7 != 1 )
    goto LABEL_48;
  v15 = 0;
  v16 = 0;
  *(_OWORD *)((char *)this + 28) = *(_OWORD *)(v7 + 2);
  while ( (unsigned int)v16 < v7[1] )
  {
    v17 = 36 * v16;
    v18 = *(_QWORD *)&v7[36 * v16 + 20] - *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
    if ( !v18 )
      v18 = *(_QWORD *)&v7[v17 + 22] - *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
    if ( v18 )
    {
      v20 = *(_QWORD *)&v7[v17 + 20] - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
      if ( !v20 )
        v20 = *(_QWORD *)&v7[v17 + 22] - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
      if ( !v20 )
        goto LABEL_48;
    }
    else
    {
      v19 = &v7[v17 + 12];
      if ( v15 )
        v19 = v15;
      v15 = v19;
    }
    v16 = (unsigned int)(v16 + 1);
  }
  if ( !v15 )
    goto LABEL_48;
  v21 = *((_QWORD *)v15 + 2);
  if ( v21 <= 0x18000 )
    goto LABEL_48;
  v22 = v21 + *((_QWORD *)v15 + 1);
  v13 = (v22 - 98304) / v5;
  v14 = v22 - v5;
LABEL_33:
  *((_QWORD *)this + 8) = v14 / v5;
  *((_QWORD *)this + 9) = v13;
  ExFreePoolWithTag(v7, 0);
  VMX_PHYSICAL_DISK::ReadHeader(this);
  if ( *((_QWORD *)this + 11) )
  {
    VMX_PHYSICAL_DISK::ReadToc(this);
    v24 = *((_QWORD *)this + 11);
    v25 = *(_QWORD *)(v24 + 244) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v25 )
      v25 = *(_QWORD *)(v24 + 252) - *(_QWORD *)GUID_NULL.Data4;
    if ( v25 )
    {
      v26 = (VMX_CONFIG_COPY *)*((_QWORD *)this + 13);
      if ( !v26 || !*((_BYTE *)v26 + 16) || (int)VMX_CONFIG_COPY::ReadPackIdentity(v26, &v32, v33, v23) < 0 )
        goto LABEL_47;
      v27 = *((_QWORD *)this + 11);
      v28 = *(_QWORD *)&v32.Data1 - *(_QWORD *)(v27 + 260);
      if ( *(_QWORD *)&v32.Data1 == *(_QWORD *)(v27 + 260) )
        v28 = *(_QWORD *)v32.Data4 - *(_QWORD *)(v27 + 268);
      if ( v28 )
      {
        PackById = VmxpFindPackById((struct _GUID *)(v27 + 260));
        if ( !PackById )
          return;
        if ( (int)VMX_RAW_CONFIG::MarkStale(
                    *(VMX_RAW_CONFIG **)(*((_QWORD *)PackById + 2) + 8LL),
                    *((struct VMX_CONFIG_COPY **)this + 13)) < 0 )
          goto LABEL_47;
      }
      if ( (int)VMX_PHYSICAL_DISK::ChangeIdentityPhase2(this) < 0 )
LABEL_47:
        VMX_PHYSICAL_DISK::InvalidateMetadata(this);
    }
  }
}

```

## disassembly

```asm
0x14003261c  mov     r11, rsp
0x14003261f  mov     [r11+10h], rbx
0x140032623  mov     [r11+18h], rsi
0x140032627  push    rdi
0x140032628  sub     rsp, 70h
0x14003262c  mov     rax, cs:__security_cookie
0x140032633  xor     rax, rsp
0x140032636  mov     [rsp+78h+var_18], rax
0x14003263b  mov     r8, [rcx+10h]
0x14003263f  mov     rbx, rcx
0x140032642  mov     qword ptr [r11-58h], 0
0x14003264a  xorps   xmm0, xmm0
0x14003264d  mov     qword ptr [r11-50h], 0
0x140032655  movups  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x14003265a  mov     edi, [r8+24h]
0x14003265e  mov     ecx, edi; unsigned int
0x140032660  call    ?VmxpSupportedBytesPerSector@@YAEK@Z; VmxpSupportedBytesPerSector(ulong)
0x140032665  test    al, al
0x140032667  jz      loc_14003290A
0x14003266d  lea     rdx, [rsp+78h+var_58]; PVOID
0x140032672  mov     rcx, r8; this
0x140032675  call    ?GetLengthInfo@VMX_DISK_DEVICE@@QEAAJPEAU_GET_LENGTH_INFORMATION@@@Z; VMX_DISK_DEVICE::GetLengthInfo(_GET_LENGTH_INFORMATION *)
0x14003267a  test    eax, eax
0x14003267c  js      loc_14003290A
0x140032682  mov     rax, [rsp+78h+var_58]
0x140032687  xor     edx, edx
0x140032689  mov     rcx, [rbx+10h]; this
0x14003268d  mov     esi, edi
0x14003268f  div     rdi
0x140032692  lea     rdx, [rsp+78h+P]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x140032697  mov     rdi, rax
0x14003269a  call    ?GetDriveLayoutEx@VMX_DISK_DEVICE@@QEAAJPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::GetDriveLayoutEx(_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14003269f  test    eax, eax
0x1400326a1  js      loc_14003290A
0x1400326a7  mov     r8, [rsp+78h+P]
0x1400326ac  mov     eax, [r8]
0x1400326af  mov     [rbx+18h], eax
0x1400326b2  mov     eax, [r8]
0x1400326b5  test    eax, eax
0x1400326b7  jnz     loc_140032759
0x1400326bd  mov     eax, [r8+8]
0x1400326c1  xor     r9d, r9d
0x1400326c4  mov     [rbx+1Ch], eax
0x1400326c7  mov     r10d, [r8+4]
0x1400326cb  cmp     r9d, r10d
0x1400326ce  jnb     short loc_140032726
0x1400326d0  lea     rcx, [r9+r9*8]
0x1400326d4  add     rcx, rcx
0x1400326d7  movzx   edx, byte ptr [r8+rcx*8+50h]
0x1400326dd  cmp     dl, 0A0h
0x1400326e0  jz      short loc_140032721
0x1400326e2  cmp     dl, 84h
0x1400326e5  jz      short loc_140032721
0x1400326e7  cmp     dl, 42h ; 'B'
0x1400326ea  jz      short loc_140032721
0x1400326ec  cmp     dl, 27h ; '''
0x1400326ef  ja      short loc_140032701
0x1400326f1  mov     rcx, 8000048021h
0x1400326fb  bt      rcx, rdx
0x1400326ff  jb      short loc_140032721
0x140032701  add     dl, 22h ; '"'
0x140032704  cmp     dl, 20h ; ' '
0x140032707  ja      loc_1400328F9
0x14003270d  mov     rcx, 100000201h
0x140032717  bt      rcx, rdx
0x14003271b  jnb     loc_1400328F9
0x140032721  inc     r9d
0x140032724  jmp     short loc_1400326CB
0x140032726  imul    rdi, rsi
0x14003272a  cmp     rdi, 18000h
0x140032731  jbe     loc_1400328F9
0x140032737  lea     rax, [rdi-18000h]
0x14003273e  mov     qword ptr [rbx+50h], 6
0x140032746  xor     edx, edx
0x140032748  div     rsi
0x14003274b  sub     rdi, rsi
0x14003274e  mov     r9, rax
0x140032751  mov     rax, rdi
0x140032754  jmp     loc_140032812
0x140032759  cmp     eax, 1
0x14003275c  jnz     loc_1400328F9
0x140032762  movups  xmm0, xmmword ptr [r8+8]
0x140032767  xor     ecx, ecx
0x140032769  xor     r9d, r9d
0x14003276c  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x140032771  mov     r10d, [r8+4]
0x140032775  cmp     r9d, r10d
0x140032778  jnb     short loc_1400327DC
0x14003277a  lea     rdx, [r9+r9*8]
0x14003277e  shl     rdx, 4
0x140032782  mov     rax, [rdx+r8+50h]
0x140032787  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x14003278e  jnz     short loc_14003279C
0x140032790  mov     rax, [rdx+r8+58h]
0x140032795  sub     rax, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x14003279c  test    rax, rax
0x14003279f  jnz     short loc_1400327B4
0x1400327a1  lea     rax, [r8+30h]
0x1400327a5  add     rax, rdx
0x1400327a8  test    rcx, rcx
0x1400327ab  cmovnz  rax, rcx
0x1400327af  mov     rcx, rax
0x1400327b2  jmp     short loc_1400327D7
0x1400327b4  mov     rax, [rdx+r8+50h]
0x1400327b9  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x1400327c0  jnz     short loc_1400327CE
0x1400327c2  mov     rax, [rdx+r8+58h]
0x1400327c7  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x1400327ce  test    rax, rax
0x1400327d1  jz      loc_1400328F9
0x1400327d7  inc     r9d
0x1400327da  jmp     short loc_140032775
0x1400327dc  test    rcx, rcx
0x1400327df  jz      loc_1400328F9
0x1400327e5  mov     rdx, [rcx+10h]
0x1400327e9  cmp     rdx, 18000h
0x1400327f0  jbe     loc_1400328F9
0x1400327f6  mov     rcx, [rcx+8]
0x1400327fa  add     rcx, rdx
0x1400327fd  xor     edx, edx
0x1400327ff  lea     rax, [rcx-18000h]
0x140032806  div     rsi
0x140032809  sub     rcx, rsi
0x14003280c  mov     r9, rax
0x14003280f  mov     rax, rcx
0x140032812  xor     edx, edx
0x140032814  mov     rcx, r8; P
0x140032817  div     rsi
0x14003281a  xor     edx, edx; Tag
0x14003281c  mov     [rbx+40h], rax
0x140032820  mov     [rbx+48h], r9
0x140032824  call    cs:__imp_ExFreePoolWithTag
0x14003282b  nop     dword ptr [rax+rax+00h]
0x140032830  mov     rcx, rbx; this
0x140032833  call    ?ReadHeader@VMX_PHYSICAL_DISK@@AEAAXXZ; VMX_PHYSICAL_DISK::ReadHeader(void)
0x140032838  cmp     qword ptr [rbx+58h], 0
0x14003283d  jz      loc_14003290A
0x140032843  mov     rcx, rbx; this
0x140032846  call    ?ReadToc@VMX_PHYSICAL_DISK@@AEAAXXZ; VMX_PHYSICAL_DISK::ReadToc(void)
0x14003284b  mov     rcx, [rbx+58h]
0x14003284f  mov     rax, [rcx+0F4h]
0x140032856  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14003285d  jnz     short loc_14003286D
0x14003285f  mov     rax, [rcx+0FCh]
0x140032866  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x14003286d  test    rax, rax
0x140032870  jz      loc_14003290A
0x140032876  mov     rcx, [rbx+68h]; this
0x14003287a  test    rcx, rcx
0x14003287d  jz      short loc_1400328EF
0x14003287f  cmp     byte ptr [rcx+10h], 0
0x140032883  jz      short loc_1400328EF
0x140032885  lea     r8, [rsp+78h+var_38]; char *
0x14003288a  lea     rdx, [rsp+78h+var_48]; struct _GUID *
0x14003288f  call    ?ReadPackIdentity@VMX_CONFIG_COPY@@QEAAJPEAU_GUID@@PEADK@Z; VMX_CONFIG_COPY::ReadPackIdentity(_GUID *,char *,ulong)
0x140032894  test    eax, eax
0x140032896  js      short loc_1400328EF
0x140032898  mov     rdx, [rbx+58h]
0x14003289c  mov     rcx, qword ptr [rsp+78h+var_48.Data1]
0x1400328a1  sub     rcx, [rdx+104h]
0x1400328a8  jnz     short loc_1400328B6
0x1400328aa  mov     rcx, qword ptr [rsp+78h+var_48.Data4]
0x1400328af  sub     rcx, [rdx+10Ch]
0x1400328b6  test    rcx, rcx
0x1400328b9  jnz     short loc_1400328C9
0x1400328bb  mov     rcx, rbx; this
0x1400328be  call    ?ChangeIdentityPhase2@VMX_PHYSICAL_DISK@@QEAAJXZ; VMX_PHYSICAL_DISK::ChangeIdentityPhase2(void)
0x1400328c3  test    eax, eax
0x1400328c5  js      short loc_1400328EF
0x1400328c7  jmp     short loc_14003290A
0x1400328c9  lea     rcx, [rdx+104h]; struct _GUID *
0x1400328d0  call    ?VmxpFindPackById@@YAPEAVVMX_PACK@@PEAU_GUID@@@Z; VmxpFindPackById(_GUID *)
0x1400328d5  test    rax, rax
0x1400328d8  jz      short loc_14003290A
0x1400328da  mov     rcx, [rax+10h]
0x1400328de  mov     rdx, [rbx+68h]; struct VMX_CONFIG_COPY *
0x1400328e2  mov     rcx, [rcx+8]; this
0x1400328e6  call    ?MarkStale@VMX_RAW_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_RAW_CONFIG::MarkStale(VMX_CONFIG_COPY *)
0x1400328eb  test    eax, eax
0x1400328ed  jns     short loc_1400328BB
0x1400328ef  mov     rcx, rbx; this
0x1400328f2  call    ?InvalidateMetadata@VMX_PHYSICAL_DISK@@QEAAXXZ; VMX_PHYSICAL_DISK::InvalidateMetadata(void)
0x1400328f7  jmp     short loc_14003290A
0x1400328f9  xor     edx, edx; Tag
0x1400328fb  mov     rcx, r8; P
0x1400328fe  call    cs:__imp_ExFreePoolWithTag
0x140032905  nop     dword ptr [rax+rax+00h]
0x14003290a  mov     rcx, [rsp+78h+var_18]
0x14003290f  xor     rcx, rsp; StackCookie
0x140032912  call    __security_check_cookie
0x140032917  lea     r11, [rsp+78h+var_8]
0x14003291c  mov     rbx, [r11+18h]
0x140032920  mov     rsi, [r11+20h]
0x140032924  mov     rsp, r11
0x140032927  pop     rdi
0x140032928  retn
```
