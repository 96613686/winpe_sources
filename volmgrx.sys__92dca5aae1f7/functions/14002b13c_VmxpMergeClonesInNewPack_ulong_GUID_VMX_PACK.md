# VmxpMergeClonesInNewPack(ulong,_GUID *,VMX_PACK * *)

- ea: `0x14002b13c`
- end: `0x14002b7b3`
- name: `?VmxpMergeClonesInNewPack@@YAJKPEAU_GUID@@PEAPEAVVMX_PACK@@@Z`
- size: `1655`
- prototype: `__int64 __fastcall(unsigned int, struct _GUID *, VMX_CONFIG ***)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140038d44`

## callees

- `0x140005f80`
- `0x140008d00`
- `0x140008d28`
- `0x140008dc8`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001b9a0`
- `0x14001be80`
- `0x14002b0c4`
- `0x14002b13c`
- `0x14002d3ec`
- `0x1400376f0`
- `0x14003d81c`
- `0x140040690`
- `0x140040de4`
- `0x140041d3c`
- `0x14004e3ac`
- `0x14004e950`
- `0x140051bdc`
- `0x14005d734`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002b40d`
- `ntoskrnl!ExAllocatePool2` at `0x14002b40d`
- `ntoskrnl!ExUuidCreate` at `0x14002b3c4`
- `ntoskrnl!ExUuidCreate` at `0x14002b513`
- `ntoskrnl!ExUuidCreate` at `0x14002b3c4`
- `ntoskrnl!ExUuidCreate` at `0x14002b513`

## pseudocode

```c
__int64 __fastcall VmxpMergeClonesInNewPack(unsigned int a1, struct _GUID *a2, VMX_CONFIG ***a3)
{
  __int64 v3; // rsi
  __int64 v4; // r13
  __int64 v5; // rbp
  struct _GUID *v6; // r9
  __int64 v7; // r14
  unsigned int i; // ebx
  struct _GUID *v9; // rdi
  unsigned int j; // r8d
  __int64 v11; // rcx
  struct VMX_PHYSICAL_DISK *PhysicalDiskByInvalidDiskId; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int64 *v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 *v18; // rcx
  int v19; // ebx
  _QWORD *v20; // rax
  VMX_PACK **v21; // rdi
  VMX_CONFIG *v22; // rcx
  _QWORD *v23; // rax
  unsigned int v24; // edx
  __int64 v25; // r12
  VMX_PACK *v26; // rax
  VMX_PACK *v27; // rsi
  VMX_PACK *v28; // rbx
  unsigned int v29; // edx
  char *v30; // r14
  const char *v31; // rbp
  struct VMX_CONFIG_COPY *v32; // rdx
  __int64 Pool2; // rax
  __int64 v34; // r15
  struct VMX_RECORD *DiskById; // rax
  _QWORD *v36; // rbp
  __int64 v37; // rax
  __int64 v38; // rbp
  UUID *v39; // rcx
  struct _GUID v40; // xmm0
  VMX_CONFIG **v41; // rax
  VMX_CONFIG **v42; // rdi
  VMX_CONFIG *v43; // rax
  VMX_GLOBAL_DATA **v44; // rcx
  VMX_CONFIG **v45; // r15
  VMX_CONFIG *v46; // rax
  __int64 v47; // rcx
  VMX_CONFIG *v48; // rax
  VMX_CONFIG *v49; // rax
  void **v50; // rcx
  unsigned int v51; // edx
  unsigned int v52; // r11d
  struct VMX_RECORD *v53; // rax
  int v54; // r11d
  __int64 v55; // rcx
  VMX_CONFIG *v56; // rax
  void **v57; // rcx
  _QWORD *v59; // [rsp+20h] [rbp-68h]
  __int64 v60; // [rsp+28h] [rbp-60h]
  struct _GUID *v61; // [rsp+30h] [rbp-58h]
  __int64 *v65; // [rsp+A8h] [rbp+20h]
  VMX_CONFIG **v66; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  v4 = a1;
  *a3 = 0;
  v5 = 0;
  v6 = a2;
  v7 = 0;
  for ( i = 0; i < (unsigned int)v4; ++i )
  {
    v9 = &v6[i];
    for ( j = 0; j < i; ++j )
    {
      v11 = *(_QWORD *)&v6[j].Data1 - *(_QWORD *)&v9->Data1;
      if ( !v11 )
        v11 = *(_QWORD *)v6[j].Data4 - *(_QWORD *)v9->Data4;
      if ( !v11 )
      {
        v19 = -1070071802;
        goto LABEL_87;
      }
    }
    PhysicalDiskByInvalidDiskId = VmxpFindPhysicalDiskByInvalidDiskId(&v6[i]);
    if ( !PhysicalDiskByInvalidDiskId || !*((_BYTE *)PhysicalDiskByInvalidDiskId + 120) )
    {
LABEL_29:
      v19 = -1070071759;
      goto LABEL_87;
    }
    v13 = *((_QWORD *)PhysicalDiskByInvalidDiskId + 11);
    if ( i )
    {
      v14 = v7 - *(_QWORD *)(v13 + 72);
      if ( v7 == *(_QWORD *)(v13 + 72) )
        v14 = v5 - *(_QWORD *)(v13 + 80);
      if ( v14 )
        goto LABEL_29;
    }
    else
    {
      v5 = *(_QWORD *)(v13 + 80);
      v7 = *(_QWORD *)(v13 + 72);
    }
    v15 = *((_QWORD *)PhysicalDiskByInvalidDiskId + 13);
    if ( v15 && *(_BYTE *)(v15 + 16) && !*(_BYTE *)(v15 + 18) && !*(_BYTE *)(v15 + 17) )
    {
      if ( !v3 )
        goto LABEL_26;
      v16 = (unsigned __int64 *)(v15 + 32);
      if ( *(_WORD *)(v15 + 20) != 3 )
        v16 = (unsigned __int64 *)(v15 + 24);
      v17 = *v16;
      v18 = (unsigned __int64 *)(v3 + 32);
      if ( *(_WORD *)(v3 + 20) != 3 )
        v18 = (unsigned __int64 *)(v3 + 24);
      if ( v17 > *v18 )
LABEL_26:
        v3 = v15;
    }
    v6 = a2;
    *v9 = *(struct _GUID *)(v13 + 40);
  }
  if ( v3 )
  {
    v20 = VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x6F436D56u);
    v21 = (VMX_PACK **)v20;
    if ( !v20 )
    {
      v19 = -1073741670;
      goto LABEL_87;
    }
    *v20 = 0;
    v20[1] = 0;
    v22 = (VMX_CONFIG *)v20;
    v20[4] = 0;
    v20[5] = 0;
    v23 = v20 + 2;
    v23[1] = v23;
    *v23 = v23;
    v21[6] = (VMX_PACK *)1;
    *(_BYTE *)(v3 + 19) = 0;
    v19 = VMX_CONFIG::Read(v22, (struct VMX_CONFIG_COPY *)v3);
    if ( v19 < 0 )
      goto LABEL_83;
    *((_BYTE *)v21 + 40) = 1;
    v19 = VMX_CONFIG::SanityCheck((VMX_CONFIG *)v21, *(struct VMX_PHYSICAL_DISK **)v3);
    if ( v19 < 0 )
    {
      *(_WORD *)(v3 + 18) = 1;
LABEL_83:
      VMX_CONFIG::`scalar deleting destructor'((VMX_CONFIG *)v21, v24);
LABEL_84:
      if ( v19 >= 0 )
        return (unsigned int)v19;
      goto LABEL_87;
    }
    v25 = 64;
    v26 = (VMX_PACK *)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x102u, 0x61506D56u);
    v27 = v26;
    if ( !v26 )
    {
      v19 = -1073741670;
      goto LABEL_83;
    }
    memset(v26, 0, 0x40u);
    *((_QWORD *)v27 + 2) = v21;
    v28 = v21[1];
    *v21 = v27;
    v30 = (char *)VMX_ALLOCATED_OBJECT::operator new(0xB8u, 0x102u, 0x78546D56u);
    if ( !v30 )
    {
      v19 = -1073741670;
      goto LABEL_81;
    }
    v31 = (char *)v28 + 24;
    *(_OWORD *)v30 = 0;
    *((_OWORD *)v30 + 1) = 0;
    *((_OWORD *)v30 + 2) = 0;
    *((_QWORD *)v30 + 6) = 0;
    *((_WORD *)v30 + 24) = 1;
    *((_DWORD *)v30 + 40) = 0;
    *((_QWORD *)v30 + 21) = 0;
    *((_WORD *)v30 + 88) = 0;
    *((_QWORD *)v30 + 7) = v27;
    *((_OWORD *)v30 + 4) = *(_OWORD *)((char *)v28 + 8);
    RtlStringCbCopyA(v30 + 80, 0x20u, (NTSTRSAFE_PCSTR)v28 + 24);
    v19 = ExUuidCreate((UUID *)v30 + 7);
    if ( v19 < 0 )
      goto LABEL_79;
    RtlStringCbCopyA(v30 + 128, 0x20u, v31);
    *((_DWORD *)v30 + 40) = v4;
    Pool2 = ExAllocatePool2(258, 48 * v4, 538996054);
    v65 = (__int64 *)(v30 + 168);
    *((_QWORD *)v30 + 21) = Pool2;
    if ( !Pool2 )
      goto LABEL_78;
    v34 = 0;
    while ( (unsigned int)v34 < (unsigned int)v4 )
    {
      v61 = &a2[(unsigned int)v34];
      DiskById = VMX_CONFIG::FindDiskById((VMX_CONFIG *)v21, v61);
      if ( !DiskById )
      {
        v19 = -1070071800;
        goto LABEL_79;
      }
      v36 = (_QWORD *)*((_QWORD *)DiskById + (*((_WORD *)DiskById + 32) & 1) + 5);
      v59 = v36;
      v37 = v36[16];
      v60 = v37;
      if ( !v37 )
      {
        v19 = -1070071791;
        goto LABEL_79;
      }
      v32 = *(struct VMX_CONFIG_COPY **)(v37 + 104);
      if ( !v32 || *((_BYTE *)v32 + 17) )
      {
        v19 = -1070071806;
        goto LABEL_79;
      }
      if ( !*((_BYTE *)v32 + 19) )
      {
        v19 = VMX_CONFIG::SynchronizeConfigCopy((VMX_CONFIG *)v21, v32);
        VMX_PACK::UpdateCounters(v27);
        if ( v19 < 0 )
          goto LABEL_79;
      }
      v19 = (*(__int64 (__fastcall **)(_QWORD *))(*v36 + 88LL))(v36);
      if ( v19 < 0 )
        goto LABEL_79;
      v38 = 16 * ((unsigned int)v34 + 2 * v34);
      v4 = *v65;
      v39 = (UUID *)(v38 + *v65 + 16);
      *(_OWORD *)(*v65 + v38) = *(_OWORD *)(v59 + 9);
      v19 = ExUuidCreate(v39);
      if ( v19 < 0 )
        goto LABEL_79;
      v34 = (unsigned int)(v34 + 1);
      v40 = *(struct _GUID *)(v4 + v38 + 16);
      *(_QWORD *)(v4 + v38 + 32) = v60;
      *(_BYTE *)(v4 + v38 + 40) = 0;
      LODWORD(v4) = a1;
      *v61 = v40;
    }
    v41 = (VMX_CONFIG **)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x102u, 0x61506D56u);
    v66 = v41;
    v42 = v41;
    if ( !v41 )
    {
LABEL_78:
      v19 = -1073741670;
      goto LABEL_79;
    }
    memset(v41, 0, 0x40u);
    v19 = VMX_PACK::CopyPack((VMX_PACK *)v42, v27);
    if ( v19 >= 0 )
    {
      v43 = (VMX_GLOBAL_DATA *)((char *)Global + 200);
      v44 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 26);
      if ( *v44 != (VMX_GLOBAL_DATA *)((char *)Global + 200) )
        goto LABEL_77;
      *v42 = v43;
      v45 = v42 + 2;
      v42[1] = (VMX_CONFIG *)v44;
      *v44 = (VMX_GLOBAL_DATA *)v42;
      *((_QWORD *)v43 + 1) = v42;
      v46 = v42[2];
      v42[6] = (VMX_CONFIG *)v30;
      v47 = *((_QWORD *)v46 + 1);
      if ( *(_WORD *)(v47 + 72) != 3 )
        v25 = 56;
      *(_QWORD *)v30 = *(_QWORD *)(v25 + v47) + 1LL;
      v48 = v42[6];
      *(_OWORD *)((char *)v48 + 8) = *(_OWORD *)(v47 + 144);
      *(_OWORD *)((char *)v48 + 20) = *(_OWORD *)(v47 + 156);
      v19 = VMX_PACK::MergeClonesInNewPackTargetTransaction((VMX_PACK *)v42);
      if ( v19 < 0 )
      {
        VMX_CONFIG::AbortRecords(*v45);
        v42[6] = 0;
      }
      else
      {
        v19 = VMX_PACK::CommitChangeIdentityTransaction((VMX_PACK *)v42);
        if ( v19 >= 0 )
        {
          if ( *((_DWORD *)v42 + 9) )
          {
            v52 = 0;
            if ( (_DWORD)v4 )
            {
              do
              {
                v53 = VMX_CONFIG::FindDiskById(*v45, &a2[v52]);
                if ( v53 )
                {
                  v55 = *(_QWORD *)(*((_QWORD *)v53 + (*((_WORD *)v53 + 32) & 1) + 5) + 128LL);
                  if ( v55 )
                    *(_BYTE *)(v55 + 120) = 0;
                }
                v52 = v54 + 1;
              }
              while ( v52 < (unsigned int)v4 );
              v42 = v66;
            }
            *((_BYTE *)*v45 + 40) = 0;
            *a3 = v42;
            goto LABEL_79;
          }
          v49 = *v42;
          if ( *((VMX_CONFIG ***)*v42 + 1) == v42 )
          {
            v50 = (void **)v42[1];
            if ( *v50 == v42 )
            {
              *v50 = v49;
              *((_QWORD *)v49 + 1) = v50;
              VmxpSendPackDepartNotifications((struct VMX_PACK *)v42);
              VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v42, v51);
              v19 = -1070071767;
LABEL_79:
              VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(
                (VMX_CHANGE_IDENTITY_TRANSACTION *)v30,
                (unsigned int)v32);
LABEL_81:
              VMX_PACK::`scalar deleting destructor'(v27, v29);
              goto LABEL_84;
            }
          }
LABEL_77:
          __fastfail(3u);
        }
      }
      v56 = *v42;
      if ( *((VMX_CONFIG ***)*v42 + 1) != v42 )
        goto LABEL_77;
      v57 = (void **)v42[1];
      if ( *v57 != v42 )
        goto LABEL_77;
      *v57 = v56;
      *((_QWORD *)v56 + 1) = v57;
    }
    VMX_PACK::`scalar deleting destructor'((VMX_PACK *)v42, (unsigned int)v32);
    goto LABEL_79;
  }
  v19 = -1070071806;
LABEL_87:
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      273,
      WPP_2f8af752156e3401cd435973c831895d_Traceguids,
      (unsigned int)v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14002b13c  mov     rax, rsp
0x14002b13f  mov     [rax+18h], r8
0x14002b143  mov     [rax+10h], rdx
0x14002b147  mov     [rax+8], ecx
0x14002b14a  push    rbx
0x14002b14b  push    rbp
0x14002b14c  push    rsi
0x14002b14d  push    rdi
0x14002b14e  push    r12
0x14002b150  push    r13
0x14002b152  push    r14
0x14002b154  push    r15
0x14002b156  sub     rsp, 48h
0x14002b15a  xor     esi, esi
0x14002b15c  mov     r13d, ecx
0x14002b15f  xorps   xmm0, xmm0
0x14002b162  mov     [r8], rsi
0x14002b165  movups  xmmword ptr [rax-58h], xmm0
0x14002b169  mov     rbp, [rax-50h]
0x14002b16d  mov     r9, rdx
0x14002b170  mov     r14, [rax-58h]
0x14002b174  lea     r15d, [rsi+1]
0x14002b178  lea     r12d, [rsi+3]
0x14002b17c  xor     ebx, ebx
0x14002b17e  cmp     ebx, r13d
0x14002b181  jnb     loc_14002B276
0x14002b187  mov     edi, ebx
0x14002b189  shl     rdi, 4
0x14002b18d  add     rdi, r9
0x14002b190  xor     r8d, r8d
0x14002b193  cmp     r8d, ebx
0x14002b196  jnb     short loc_14002B1BE
0x14002b198  mov     edx, r8d
0x14002b19b  add     rdx, rdx
0x14002b19e  mov     rcx, [r9+rdx*8]
0x14002b1a2  sub     rcx, [rdi]
0x14002b1a5  jnz     short loc_14002B1B0
0x14002b1a7  mov     rcx, [r9+rdx*8+8]
0x14002b1ac  sub     rcx, [rdi+8]
0x14002b1b0  test    rcx, rcx
0x14002b1b3  jz      loc_14002B262
0x14002b1b9  add     r8d, r15d
0x14002b1bc  jmp     short loc_14002B193
0x14002b1be  mov     rcx, rdi; struct _GUID *
0x14002b1c1  call    ?VmxpFindPhysicalDiskByInvalidDiskId@@YAPEAVVMX_PHYSICAL_DISK@@PEAU_GUID@@@Z; VmxpFindPhysicalDiskByInvalidDiskId(_GUID *)
0x14002b1c6  test    rax, rax
0x14002b1c9  jz      loc_14002B26C
0x14002b1cf  cmp     byte ptr [rax+78h], 0
0x14002b1d3  jz      loc_14002B26C
0x14002b1d9  mov     r8, [rax+58h]
0x14002b1dd  test    ebx, ebx
0x14002b1df  jnz     short loc_14002B1EB
0x14002b1e1  mov     rbp, [r8+50h]
0x14002b1e5  mov     r14, [r8+48h]
0x14002b1e9  jmp     short loc_14002B200
0x14002b1eb  mov     rcx, r14
0x14002b1ee  sub     rcx, [r8+48h]
0x14002b1f2  jnz     short loc_14002B1FB
0x14002b1f4  mov     rcx, rbp
0x14002b1f7  sub     rcx, [r8+50h]
0x14002b1fb  test    rcx, rcx
0x14002b1fe  jnz     short loc_14002B26C
0x14002b200  mov     rax, [rax+68h]
0x14002b204  test    rax, rax
0x14002b207  jz      short loc_14002B249
0x14002b209  cmp     byte ptr [rax+10h], 0
0x14002b20d  jz      short loc_14002B249
0x14002b20f  cmp     byte ptr [rax+12h], 0
0x14002b213  jnz     short loc_14002B249
0x14002b215  cmp     byte ptr [rax+11h], 0
0x14002b219  jnz     short loc_14002B249
0x14002b21b  test    rsi, rsi
0x14002b21e  jz      short loc_14002B246
0x14002b220  lea     rcx, [rax+20h]
0x14002b224  cmp     [rax+14h], r12w
0x14002b229  jz      short loc_14002B22F
0x14002b22b  lea     rcx, [rax+18h]
0x14002b22f  mov     rdx, [rcx]
0x14002b232  lea     rcx, [rsi+20h]
0x14002b236  cmp     [rsi+14h], r12w
0x14002b23b  jz      short loc_14002B241
0x14002b23d  lea     rcx, [rsi+18h]
0x14002b241  cmp     rdx, [rcx]
0x14002b244  jbe     short loc_14002B249
0x14002b246  mov     rsi, rax
0x14002b249  movups  xmm0, xmmword ptr [r8+28h]
0x14002b24e  mov     r9, [rsp+88h+arg_8]
0x14002b256  add     ebx, r15d
0x14002b259  movdqu  xmmword ptr [rdi], xmm0
0x14002b25d  jmp     loc_14002B17E
0x14002b262  mov     ebx, 0C0380006h
0x14002b267  jmp     loc_14002B767
0x14002b26c  mov     ebx, 0C0380031h
0x14002b271  jmp     loc_14002B767
0x14002b276  test    rsi, rsi
0x14002b279  jnz     short loc_14002B285
0x14002b27b  mov     ebx, 0C0380002h
0x14002b280  jmp     loc_14002B767
0x14002b285  mov     ebp, 102h
0x14002b28a  mov     r8d, 6F436D56h; unsigned int
0x14002b290  mov     edx, ebp; unsigned __int64
0x14002b292  mov     ecx, 38h ; '8'; unsigned __int64
0x14002b297  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002b29c  mov     rdi, rax
0x14002b29f  test    rax, rax
0x14002b2a2  jz      loc_14002B762
0x14002b2a8  mov     qword ptr [rax], 0
0x14002b2af  mov     rdx, rsi; struct VMX_CONFIG_COPY *
0x14002b2b2  mov     qword ptr [rax+8], 0
0x14002b2ba  mov     rcx, rdi; this
0x14002b2bd  mov     qword ptr [rax+20h], 0
0x14002b2c5  mov     qword ptr [rax+28h], 0
0x14002b2cd  add     rax, 10h
0x14002b2d1  mov     [rax+8], rax
0x14002b2d5  mov     [rax], rax
0x14002b2d8  mov     [rdi+30h], r15
0x14002b2dc  mov     byte ptr [rsi+13h], 0
0x14002b2e0  call    ?Read@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::Read(VMX_CONFIG_COPY *)
0x14002b2e5  mov     ebx, eax
0x14002b2e7  test    eax, eax
0x14002b2e9  js      loc_14002B754
0x14002b2ef  mov     [rdi+28h], r15b
0x14002b2f3  mov     rcx, rdi; this
0x14002b2f6  mov     rdx, [rsi]; struct VMX_PHYSICAL_DISK *
0x14002b2f9  call    ?SanityCheck@VMX_CONFIG@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_CONFIG::SanityCheck(VMX_PHYSICAL_DISK *)
0x14002b2fe  mov     ebx, eax
0x14002b300  test    eax, eax
0x14002b302  jns     short loc_14002B30E
0x14002b304  mov     [rsi+12h], r15w
0x14002b309  jmp     loc_14002B754
0x14002b30e  mov     r12d, 40h ; '@'
0x14002b314  mov     r8d, 61506D56h; unsigned int
0x14002b31a  mov     ecx, r12d; unsigned __int64
0x14002b31d  mov     rdx, rbp; unsigned __int64
0x14002b320  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002b325  mov     rsi, rax
0x14002b328  test    rax, rax
0x14002b32b  jz      loc_14002B74F
0x14002b331  mov     r8d, r12d; Size
0x14002b334  xor     edx, edx; Val
0x14002b336  mov     rcx, rax; void *
0x14002b339  call    memset
0x14002b33e  mov     [rsi+10h], rdi
0x14002b342  lea     ecx, [r12+78h]; unsigned __int64
0x14002b347  mov     rbx, [rdi+8]
0x14002b34b  mov     r8d, 78546D56h; unsigned int
0x14002b351  mov     rdx, rbp; unsigned __int64
0x14002b354  mov     [rdi], rsi
0x14002b357  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002b35c  mov     r14, rax
0x14002b35f  test    rax, rax
0x14002b362  jz      loc_14002B740
0x14002b368  xor     eax, eax
0x14002b36a  lea     rbp, [rbx+18h]
0x14002b36e  xorps   xmm0, xmm0
0x14002b371  lea     rcx, [r14+50h]; pszDest
0x14002b375  movups  xmmword ptr [r14], xmm0
0x14002b379  mov     r8, rbp; pszSrc
0x14002b37c  movups  xmmword ptr [r14+10h], xmm0
0x14002b381  movups  xmmword ptr [r14+20h], xmm0
0x14002b386  mov     [r14+30h], rax
0x14002b38a  mov     [r14+30h], r15w
0x14002b38f  lea     r15d, [r12-20h]
0x14002b394  mov     [r14+0A0h], eax
0x14002b39b  mov     edx, r15d; cbDest
0x14002b39e  mov     [r14+0A8h], rax
0x14002b3a5  mov     [r14+0B0h], ax
0x14002b3ad  mov     [r14+38h], rsi
0x14002b3b1  movups  xmm0, xmmword ptr [rbx+8]
0x14002b3b5  movdqu  xmmword ptr [r14+40h], xmm0
0x14002b3bb  call    RtlStringCbCopyA
0x14002b3c0  lea     rcx, [r14+70h]; Uuid
0x14002b3c4  call    cs:__imp_ExUuidCreate
0x14002b3cb  nop     dword ptr [rax+rax+00h]
0x14002b3d0  mov     ebx, eax
0x14002b3d2  test    eax, eax
0x14002b3d4  js      loc_14002B736
0x14002b3da  lea     rcx, [r14+80h]; pszDest
0x14002b3e1  mov     r8, rbp; pszSrc
0x14002b3e4  mov     edx, r15d; cbDest
0x14002b3e7  call    RtlStringCbCopyA
0x14002b3ec  lea     rdx, ds:0[r13*2]
0x14002b3f4  mov     [r14+0A0h], r13d
0x14002b3fb  add     rdx, r13
0x14002b3fe  mov     ecx, 102h
0x14002b403  shl     rdx, 4
0x14002b407  mov     r8d, 20206D56h
0x14002b40d  call    cs:__imp_ExAllocatePool2
0x14002b414  nop     dword ptr [rax+rax+00h]
0x14002b419  lea     rcx, [r14+0A8h]
0x14002b420  mov     [rsp+88h+arg_18], rcx
0x14002b428  mov     [rcx], rax
0x14002b42b  test    rax, rax
0x14002b42e  jz      loc_14002B731
0x14002b434  xor     r15d, r15d
0x14002b437  cmp     r15d, r13d
0x14002b43a  jnb     loc_14002B576
0x14002b440  mov     eax, r15d
0x14002b443  mov     rcx, rdi; this
0x14002b446  shl     rax, 4
0x14002b44a  add     rax, [rsp+88h+arg_8]
0x14002b452  mov     rdx, rax; struct _GUID *
0x14002b455  mov     r13d, r15d
0x14002b458  mov     [rsp+88h+var_58], rax
0x14002b45d  call    ?FindDiskById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindDiskById(_GUID *)
0x14002b462  test    rax, rax
0x14002b465  jz      loc_14002B56C
0x14002b46b  movzx   ecx, word ptr [rax+40h]
0x14002b46f  and     ecx, 1
0x14002b472  mov     rbp, [rax+rcx*8+28h]
0x14002b477  mov     [rsp+88h+var_68], rbp
0x14002b47c  mov     rax, [rbp+80h]
0x14002b483  mov     [rsp+88h+var_60], rax
0x14002b488  test    rax, rax
0x14002b48b  jz      loc_14002B562
0x14002b491  mov     rdx, [rax+68h]; struct VMX_CONFIG_COPY *
0x14002b495  test    rdx, rdx
0x14002b498  jz      loc_14002B558
0x14002b49e  cmp     byte ptr [rdx+11h], 0
0x14002b4a2  jnz     loc_14002B558
0x14002b4a8  cmp     byte ptr [rdx+13h], 0
0x14002b4ac  jnz     short loc_14002B4C8
0x14002b4ae  mov     rcx, rdi; this
0x14002b4b1  call    ?SynchronizeConfigCopy@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::SynchronizeConfigCopy(VMX_CONFIG_COPY *)
0x14002b4b6  mov     rcx, rsi; this
0x14002b4b9  mov     ebx, eax
0x14002b4bb  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14002b4c0  test    ebx, ebx
0x14002b4c2  js      loc_14002B736
0x14002b4c8  mov     rax, [rbp+0]
0x14002b4cc  mov     rcx, rbp
0x14002b4cf  mov     rax, [rax+58h]
0x14002b4d3  call    _guard_dispatch_icall
0x14002b4d8  mov     ebx, eax
0x14002b4da  test    eax, eax
0x14002b4dc  js      loc_14002B736
0x14002b4e2  mov     rax, [rsp+88h+arg_18]
0x14002b4ea  lea     rbp, ds:0[r15*2]
0x14002b4f2  add     rbp, r13
0x14002b4f5  shl     rbp, 4
0x14002b4f9  mov     r13, [rax]
0x14002b4fc  mov     rax, [rsp+88h+var_68]
0x14002b501  lea     rcx, [r13+10h]
0x14002b505  movups  xmm0, xmmword ptr [rax+48h]
0x14002b509  add     rcx, rbp; Uuid
0x14002b50c  movdqu  xmmword ptr [r13+rbp+0], xmm0
0x14002b513  call    cs:__imp_ExUuidCreate
0x14002b51a  nop     dword ptr [rax+rax+00h]
0x14002b51f  mov     ebx, eax
0x14002b521  test    eax, eax
0x14002b523  js      loc_14002B736
0x14002b529  mov     rax, [rsp+88h+var_60]
0x14002b52e  inc     r15d
0x14002b531  movups  xmm0, xmmword ptr [r13+rbp+10h]
0x14002b537  mov     [r13+rbp+20h], rax
0x14002b53c  mov     rax, [rsp+88h+var_58]
0x14002b541  mov     byte ptr [r13+rbp+28h], 0
0x14002b547  mov     r13d, [rsp+88h+arg_0]
0x14002b54f  movdqu  xmmword ptr [rax], xmm0
0x14002b553  jmp     loc_14002B437
0x14002b558  mov     ebx, 0C0380002h
0x14002b55d  jmp     loc_14002B736
0x14002b562  mov     ebx, 0C0380011h
0x14002b567  jmp     loc_14002B736
0x14002b56c  mov     ebx, 0C0380008h
0x14002b571  jmp     loc_14002B736
0x14002b576  mov     edx, 102h; unsigned __int64
0x14002b57b  mov     r8d, 61506D56h; unsigned int
0x14002b581  mov     rcx, r12; unsigned __int64
0x14002b584  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002b589  mov     [rsp+88h+arg_18], rax
0x14002b591  mov     rdi, rax
0x14002b594  test    rax, rax
0x14002b597  jz      loc_14002B731
0x14002b59d  mov     r8, r12; Size
0x14002b5a0  xor     edx, edx; Val
0x14002b5a2  mov     rcx, rax; void *
0x14002b5a5  call    memset
0x14002b5aa  mov     rdx, rsi; struct VMX_PACK *
0x14002b5ad  mov     rcx, rdi; this
0x14002b5b0  call    ?CopyPack@VMX_PACK@@QEAAJPEAV1@@Z; VMX_PACK::CopyPack(VMX_PACK *)
0x14002b5b5  mov     ebx, eax
0x14002b5b7  test    eax, eax
0x14002b5b9  js      loc_14002B722
0x14002b5bf  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002b5c6  mov     ebp, 3
0x14002b5cb  add     rax, 0C8h
0x14002b5d1  mov     rcx, [rax+8]
0x14002b5d5  cmp     [rcx], rax
0x14002b5d8  jnz     loc_14002B72C
0x14002b5de  mov     [rdi], rax
0x14002b5e1  lea     r15, [rdi+10h]
0x14002b5e5  mov     [rdi+8], rcx
0x14002b5e9  mov     [rcx], rdi
0x14002b5ec  mov     [rax+8], rdi
0x14002b5f0  mov     rax, [r15]
0x14002b5f3  mov     [rdi+30h], r14
0x14002b5f7  mov     rcx, [rax+8]
0x14002b5fb  lea     eax, [rbp+35h]
0x14002b5fe  cmp     [rcx+48h], bp
  ... truncated ...
```
