# SDB_POOL_CONFIG::PickDrive(SDB_EXTENT *,uchar,uchar,SDB_EXTENT *)

- ea: `0x14000c840`
- end: `0x14000cbc9`
- name: `?PickDrive@SDB_POOL_CONFIG@@QEAAJPEAVSDB_EXTENT@@EE0@Z`
- size: `905`
- prototype: `__int64 __usercall@<rax>(SDB_POOL_CONFIG *__hidden this@<rcx>, struct SDB_EXTENT *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct SDB_EXTENT *)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c6b0`
- `0x140063d50`
- `0x140064320`
- `0x140064b64`

## callees

- `0x14000ba20`
- `0x14000c840`
- `0x14000cbd0`
- `0x14000cc80`
- `0x14000cd20`
- `0x14000d280`
- `0x14000d2b0`
- `0x14000d300`
- `0x14000d460`
- `0x14001ccf0`
- `0x140026860`
- `0x140026e90`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000ca49`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbac`

## pseudocode

```c
int __fastcall SDB_POOL_CONFIG::PickDrive(
        __int64 **this,
        struct SDB_EXTENT *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        struct SDB_EXTENT *a5)
{
  int v5; // r15d
  struct SDB_RECORD *Tier; // rax
  unsigned int v11; // ebx
  struct SDB_RECORD *Space; // rax
  __int64 v13; // rdx
  struct SDB_RECORD *v14; // rax
  int *v15; // rdx
  int v16; // r8d
  int v17; // edi
  int v18; // eax
  __int64 *RecordByType; // r14
  int result; // eax
  __int64 v21; // rax
  int v22; // ecx
  unsigned __int8 IsColumnPackingEnabled; // di
  struct SP_RESILIENCY_INFO *v24; // rbx
  __int64 v25; // rcx
  _QWORD *Pool2; // rax
  _QWORD *v27; // rbx
  int v28; // edi
  _QWORD *v29; // rdx
  __int64 v30; // r8
  unsigned int i; // ecx
  __int64 v32; // rax
  struct SDB_RECORD *TopLevelSpace; // rax
  struct SDB_RECORD *v34; // rax
  int v35; // edx
  _QWORD *FaultDomainId; // rax
  unsigned int v37; // [rsp+20h] [rbp-A8h]
  int v38; // [rsp+24h] [rbp-A4h]
  __int64 v39; // [rsp+28h] [rbp-A0h]
  __int64 v40; // [rsp+30h] [rbp-98h]
  __int64 v41; // [rsp+40h] [rbp-88h] BYREF
  __int64 v42; // [rsp+48h] [rbp-80h]
  int v43; // [rsp+50h] [rbp-78h]
  struct _SP_PROVISIONING_INFO *v44; // [rsp+58h] [rbp-70h]
  struct SP_RESILIENCY_INFO *v45; // [rsp+60h] [rbp-68h]
  int v46; // [rsp+68h] [rbp-60h]
  _QWORD *v47; // [rsp+70h] [rbp-58h]
  unsigned __int8 v48; // [rsp+78h] [rbp-50h]

  v5 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  Tier = SDB_EXTENT::GetTier(a2);
  if ( Tier )
  {
    v32 = *((_QWORD *)Tier + (*((_WORD *)Tier + 15) & 1) + 4);
    v11 = *(_DWORD *)(v32 + 140);
    v39 = *(_QWORD *)(v32 + 152);
    v37 = *(_DWORD *)(v32 + 144);
  }
  else
  {
    v37 = 0;
    v11 = 0;
    v39 = 0;
  }
  Space = SDB_EXTENT::GetSpace(a2);
  if ( !v11 )
  {
    v13 = *((_QWORD *)Space + (*((_WORD *)Space + 15) & 1) + 4);
    if ( *(_DWORD *)(v13 + 188) )
    {
      TopLevelSpace = SDB_POOL_CONFIG::FindTopLevelSpace((SDB_POOL_CONFIG *)this, Space);
      v13 = *((_QWORD *)TopLevelSpace + (*((_WORD *)TopLevelSpace + 15) & 1) + 4);
    }
    v11 = *(_DWORD *)(v13 + 200);
    v37 = *(_DWORD *)(v13 + 204);
    v39 = *(_QWORD *)(v13 + 208);
  }
  if ( SDB_EXTENT::GetTier(a2) )
  {
    v34 = SDB_EXTENT::GetTier(a2);
    v15 = (int *)(*((_QWORD *)v34 + (*((_WORD *)v34 + 15) & 1) + 4) + 88LL);
  }
  else
  {
    v14 = SDB_EXTENT::GetSpace(a2);
    v15 = (int *)(*((_QWORD *)v14 + (*((_WORD *)v14 + 15) & 1) + 4) + 112LL);
  }
  v16 = *v15;
  v17 = 0;
  if ( v11 )
  {
    if ( v11 == 1 && v16 == 3 )
    {
      v17 = 4;
      v11 = 0;
    }
  }
  else
  {
    v18 = 1;
    if ( v16 == 3 )
      v18 = 4;
    v17 = v18;
  }
  RecordByType = this[35];
  if ( RecordByType == (__int64 *)(this + 35) || !RecordByType )
    return -1073740703;
  do
  {
    v21 = RecordByType[(*((_WORD *)RecordByType + 15) & 1) + 4];
    v40 = v21;
    *(_DWORD *)(v21 + 252) &= ~1u;
    v22 = *(_DWORD *)(v21 + 252);
    v38 = v22;
    if ( !v17 || (v35 = *(_DWORD *)(v21 + 68), v35 == v17) || v17 == 1 && v35 == 5 )
    {
      if ( v11 )
      {
        FaultDomainId = (_QWORD *)SDB_DRIVE::GetFaultDomainId(v21, v11);
        if ( FaultDomainId )
        {
          for ( i = 0; i < v37; ++i )
          {
            v29 = (_QWORD *)(v39 + 16LL * i);
            v30 = *v29 - *FaultDomainId;
            if ( *v29 == *FaultDomainId )
              v30 = v29[1] - FaultDomainId[1];
            if ( !v30 )
            {
              v21 = v40;
              v22 = v38;
              goto LABEL_22;
            }
          }
        }
      }
      else
      {
LABEL_22:
        *(_DWORD *)(v21 + 252) = v22 | 1;
        ++v5;
      }
    }
    RecordByType = SDB_POOL_CONFIG::GetRecordByType((__int64)this, 2, RecordByType);
  }
  while ( RecordByType );
  if ( !v5 )
    return -1073740703;
  result = SDB_POOL_CONFIG::IgnoreDrives((SDB_POOL_CONFIG *)this, a2, a3, a4);
  if ( result >= 0 )
  {
    IsColumnPackingEnabled = SC_ENV::IsColumnPackingEnabled();
    v24 = SDB_EXTENT::Resiliency(a2);
    v44 = SDB_EXTENT::Provisioning(a2);
    v45 = v24;
    v46 = 1;
    v42 = *((_QWORD *)v44 + 1);
    v25 = 256;
    v48 = IsColumnPackingEnabled;
    if ( !*((_BYTE *)WPP_MAIN_CB.DeviceExtension + 442) )
      v25 = 64;
    Pool2 = (_QWORD *)ExAllocatePool2(v25, 96, 1698852947);
    if ( Pool2 && (v27 = Pool2 + 1, *Pool2 = 1, SDB_EXTENT::SDB_EXTENT((SDB_EXTENT *)(Pool2 + 1)), (v47 = v27) != 0) )
    {
      v41 = *((_QWORD *)a2 + 5);
      v28 = SDB_POOL_CONFIG::PickDrive((SDB_POOL_CONFIG *)this, (struct SC_PICK_CONTEXT *)&v41);
      if ( v28 >= 0 )
      {
        *((_QWORD *)a5 + 1) = v27[1];
        *((_QWORD *)a5 + 2) = v27[2];
        *((_BYTE *)a5 + 24) = *((_BYTE *)v27 + 24);
        *((_BYTE *)a5 + 25) = *((_BYTE *)v27 + 25);
        *((_DWORD *)a5 + 7) = *((_DWORD *)v27 + 7);
        *((_QWORD *)a5 + 4) = v27[4];
        *((_QWORD *)a5 + 5) = v27[5];
        *((_QWORD *)a5 + 6) = v27[6];
        *((_DWORD *)a5 + 14) = *((_DWORD *)v27 + 14);
        *((_DWORD *)a5 + 14) = *((_DWORD *)v27 + 14);
        *((_DWORD *)a5 + 15) = *((_DWORD *)v27 + 15);
        *((_DWORD *)a5 + 16) = *((_DWORD *)v27 + 16);
        *((_DWORD *)a5 + 17) = *((_DWORD *)v27 + 17);
        *((_DWORD *)a5 + 18) = *((_DWORD *)v27 + 18);
        *((_WORD *)a5 + 38) = *((_WORD *)v27 + 38);
        *((_WORD *)a5 + 39) = *((_WORD *)v27 + 39);
        *((_QWORD *)a5 + 10) = v27[10];
      }
      if ( *(v27 - 1) )
        (*(void (__fastcall **)(_QWORD *, __int64))*v27)(v27, 3);
      else
        ExFreePoolWithTag(v27 - 1, 0);
      return v28;
    }
    else
    {
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c840  push    rbx
0x14000c842  push    rbp
0x14000c843  push    rsi
0x14000c844  push    rdi
0x14000c845  push    r12
0x14000c847  push    r13
0x14000c849  push    r14
0x14000c84b  push    r15
0x14000c84d  sub     rsp, 88h
0x14000c854  xor     r15d, r15d
0x14000c857  mov     rbp, rcx
0x14000c85a  mov     rcx, rdx; this
0x14000c85d  mov     [rsp+0C8h+var_88], r15
0x14000c862  mov     [rsp+0C8h+var_80], r15
0x14000c867  movzx   r12d, r9b
0x14000c86b  mov     [rsp+0C8h+var_78], r15d
0x14000c870  movzx   r13d, r8b
0x14000c874  mov     [rsp+0C8h+var_70], r15
0x14000c879  mov     rsi, rdx
0x14000c87c  mov     [rsp+0C8h+var_68], r15
0x14000c881  mov     [rsp+0C8h+var_60], r15d
0x14000c886  mov     [rsp+0C8h+var_58], r15
0x14000c88b  call    ?GetTier@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetTier(void)
0x14000c890  test    rax, rax
0x14000c893  jnz     loc_14000CAF3
0x14000c899  mov     [rsp+0C8h+var_A8], r15d
0x14000c89e  mov     ebx, r15d
0x14000c8a1  mov     [rsp+0C8h+var_A0], r15
0x14000c8a6  mov     rcx, rsi; this
0x14000c8a9  call    ?GetSpace@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetSpace(void)
0x14000c8ae  test    ebx, ebx
0x14000c8b0  jnz     short loc_14000C8E7
0x14000c8b2  movzx   ecx, word ptr [rax+1Eh]
0x14000c8b6  and     ecx, 1
0x14000c8b9  mov     rdx, [rax+rcx*8+20h]
0x14000c8be  cmp     [rdx+0BCh], r15d
0x14000c8c5  jnz     loc_14000CB20
0x14000c8cb  mov     eax, [rdx+0CCh]
0x14000c8d1  mov     ebx, [rdx+0C8h]
0x14000c8d7  mov     [rsp+0C8h+var_A8], eax
0x14000c8db  mov     rax, [rdx+0D0h]
0x14000c8e2  mov     [rsp+0C8h+var_A0], rax
0x14000c8e7  mov     rcx, rsi; this
0x14000c8ea  call    ?GetTier@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetTier(void)
0x14000c8ef  mov     rcx, rsi; this
0x14000c8f2  test    rax, rax
0x14000c8f5  jnz     loc_14000CB3C
0x14000c8fb  call    ?GetSpace@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetSpace(void)
0x14000c900  movzx   ecx, word ptr [rax+1Eh]
0x14000c904  and     ecx, 1
0x14000c907  mov     rdx, [rax+rcx*8+20h]
0x14000c90c  add     rdx, 70h ; 'p'
0x14000c910  mov     r8d, [rdx]
0x14000c913  mov     edi, r15d
0x14000c916  test    ebx, ebx
0x14000c918  jnz     short loc_14000C95B
0x14000c91a  mov     edi, 4
0x14000c91f  cmp     r8d, 3
0x14000c923  mov     eax, 1
0x14000c928  cmovz   eax, edi
0x14000c92b  mov     edi, eax
0x14000c92d  lea     rax, [rbp+118h]
0x14000c934  mov     r14, [rax]
0x14000c937  cmp     r14, rax
0x14000c93a  jz      short loc_14000C941
0x14000c93c  test    r14, r14
0x14000c93f  jnz     short loc_14000C970
0x14000c941  mov     eax, 0C0000461h
0x14000c946  add     rsp, 88h
0x14000c94d  pop     r15
0x14000c94f  pop     r14
0x14000c951  pop     r13
0x14000c953  pop     r12
0x14000c955  pop     rdi
0x14000c956  pop     rsi
0x14000c957  pop     rbp
0x14000c958  pop     rbx
0x14000c959  retn
0x14000c95b  cmp     ebx, 1
0x14000c95e  jnz     short loc_14000C92D
0x14000c960  cmp     r8d, 3
0x14000c964  jnz     short loc_14000C92D
0x14000c966  mov     edi, 4
0x14000c96b  mov     ebx, r15d
0x14000c96e  jmp     short loc_14000C92D
0x14000c970  movzx   eax, word ptr [r14+1Eh]
0x14000c975  and     eax, 1
0x14000c978  mov     rax, [r14+rax*8+20h]
0x14000c97d  mov     [rsp+0C8h+var_98], rax
0x14000c982  and     dword ptr [rax+0FCh], 0FFFFFFFEh
0x14000c989  mov     ecx, [rax+0FCh]
0x14000c98f  mov     [rsp+0C8h+var_A4], ecx
0x14000c993  test    edi, edi
0x14000c995  jnz     loc_14000CB56
0x14000c99b  test    ebx, ebx
0x14000c99d  jnz     loc_14000CB78
0x14000c9a3  or      ecx, 1
0x14000c9a6  mov     [rax+0FCh], ecx
0x14000c9ac  inc     r15d
0x14000c9af  mov     r8, r14
0x14000c9b2  mov     dl, 2
0x14000c9b4  mov     rcx, rbp
0x14000c9b7  call    ?GetRecordByType@SDB_POOL_CONFIG@@UEAAPEAVSDB_RECORD@@W4_SDB_RECORD_TYPE@@PEAV2@@Z; SDB_POOL_CONFIG::GetRecordByType(_SDB_RECORD_TYPE,SDB_RECORD *)
0x14000c9bc  mov     r14, rax
0x14000c9bf  test    rax, rax
0x14000c9c2  jnz     short loc_14000C970
0x14000c9c4  test    r15d, r15d
0x14000c9c7  jz      loc_14000C941
0x14000c9cd  movzx   r9d, r12b; unsigned __int8
0x14000c9d1  movzx   r8d, r13b; unsigned __int8
0x14000c9d5  mov     rdx, rsi; struct SDB_EXTENT *
0x14000c9d8  mov     rcx, rbp; this
0x14000c9db  call    ?IgnoreDrives@SDB_POOL_CONFIG@@QEAAJPEAVSDB_EXTENT@@EE@Z; SDB_POOL_CONFIG::IgnoreDrives(SDB_EXTENT *,uchar,uchar)
0x14000c9e0  test    eax, eax
0x14000c9e2  js      loc_14000C946
0x14000c9e8  call    ?IsColumnPackingEnabled@SC_ENV@@SAEXZ; SC_ENV::IsColumnPackingEnabled(void)
0x14000c9ed  mov     rcx, rsi; this
0x14000c9f0  movzx   edi, al
0x14000c9f3  call    ?Resiliency@SDB_EXTENT@@QEAAPEAVSP_RESILIENCY_INFO@@XZ; SDB_EXTENT::Resiliency(void)
0x14000c9f8  mov     rcx, rsi; this
0x14000c9fb  mov     rbx, rax
0x14000c9fe  call    ?Provisioning@SDB_EXTENT@@QEAAPEAU_SP_PROVISIONING_INFO@@XZ; SDB_EXTENT::Provisioning(void)
0x14000ca03  mov     [rsp+0C8h+var_70], rax
0x14000ca08  mov     edx, 40h ; '@'
0x14000ca0d  mov     r8d, 65427053h
0x14000ca13  mov     [rsp+0C8h+var_68], rbx
0x14000ca18  mov     [rsp+0C8h+var_60], 1
0x14000ca20  mov     rcx, [rax+8]
0x14000ca24  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000ca2b  mov     [rsp+0C8h+var_80], rcx
0x14000ca30  mov     ecx, 100h
0x14000ca35  mov     [rsp+0C8h+var_50], dil
0x14000ca3a  cmp     [rax+1BAh], r14b
0x14000ca41  cmovz   ecx, edx
0x14000ca44  mov     edx, 60h ; '`'
0x14000ca49  call    cs:__imp_ExAllocatePool2
0x14000ca50  nop     dword ptr [rax+rax+00h]
0x14000ca55  test    rax, rax
0x14000ca58  jz      loc_14000CBBF
0x14000ca5e  lea     rbx, [rax+8]
0x14000ca62  mov     qword ptr [rax], 1
0x14000ca69  mov     rcx, rbx; this
0x14000ca6c  call    ??0SDB_EXTENT@@QEAA@XZ; SDB_EXTENT::SDB_EXTENT(void)
0x14000ca71  mov     [rsp+0C8h+var_58], rbx
0x14000ca76  test    rbx, rbx
0x14000ca79  jz      loc_14000CBBF
0x14000ca7f  mov     rax, [rsi+28h]
0x14000ca83  lea     rdx, [rsp+0C8h+var_88]; struct SC_PICK_CONTEXT *
0x14000ca88  mov     rcx, rbp; this
0x14000ca8b  mov     [rsp+0C8h+var_88], rax
0x14000ca90  call    ?PickDrive@SDB_POOL_CONFIG@@QEAAJPEAVSC_PICK_CONTEXT@@@Z; SDB_POOL_CONFIG::PickDrive(SC_PICK_CONTEXT *)
0x14000ca95  mov     edi, eax
0x14000ca97  test    eax, eax
0x14000ca99  jns     loc_140069640
0x14000ca9f  cmp     qword ptr [rbx-8], 0
0x14000caa4  lea     rcx, [rbx-8]; P
0x14000caa8  jz      loc_14000CBAA
0x14000caae  mov     rax, [rbx]
0x14000cab1  mov     edx, 3
0x14000cab6  mov     rcx, rbx
0x14000cab9  mov     rax, [rax]
0x14000cabc  call    _guard_dispatch_icall
0x14000cac1  mov     eax, edi
0x14000cac3  jmp     loc_14000C946
0x14000cac8  mov     edx, ecx
0x14000caca  shl     rdx, 4
0x14000cace  add     rdx, [rsp+0C8h+var_A0]
0x14000cad3  mov     r8, [rdx]
0x14000cad6  sub     r8, [rax]
0x14000cad9  jnz     short loc_14000CAE3
0x14000cadb  mov     r8, [rdx+8]
0x14000cadf  sub     r8, [rax+8]
0x14000cae3  test    r8, r8
0x14000cae6  jz      loc_14000CB9C
0x14000caec  inc     ecx
0x14000caee  jmp     loc_14000CB8D
0x14000caf3  movzx   ecx, word ptr [rax+1Eh]
0x14000caf7  and     ecx, 1
0x14000cafa  mov     rax, [rax+rcx*8+20h]
0x14000caff  mov     ecx, [rax+90h]
0x14000cb05  mov     ebx, [rax+8Ch]
0x14000cb0b  mov     rax, [rax+98h]
0x14000cb12  mov     [rsp+0C8h+var_A0], rax
0x14000cb17  mov     [rsp+0C8h+var_A8], ecx
0x14000cb1b  jmp     loc_14000C8A6
0x14000cb20  mov     rdx, rax; struct SDB_RECORD *
0x14000cb23  mov     rcx, rbp; this
0x14000cb26  call    ?FindTopLevelSpace@SDB_POOL_CONFIG@@QEAAPEAVSDB_RECORD@@PEAV2@@Z; SDB_POOL_CONFIG::FindTopLevelSpace(SDB_RECORD *)
0x14000cb2b  movzx   ecx, word ptr [rax+1Eh]
0x14000cb2f  and     ecx, 1
0x14000cb32  mov     rdx, [rax+rcx*8+20h]
0x14000cb37  jmp     loc_14000C8CB
0x14000cb3c  call    ?GetTier@SDB_EXTENT@@QEAAPEAVSDB_RECORD@@XZ; SDB_EXTENT::GetTier(void)
0x14000cb41  movzx   ecx, word ptr [rax+1Eh]
0x14000cb45  and     ecx, 1
0x14000cb48  mov     rdx, [rax+rcx*8+20h]
0x14000cb4d  add     rdx, 58h ; 'X'
0x14000cb51  jmp     loc_14000C910
0x14000cb56  mov     edx, [rax+44h]
0x14000cb59  cmp     edx, edi
0x14000cb5b  jz      loc_14000C99B
0x14000cb61  cmp     edi, 1
0x14000cb64  jnz     loc_14000C9AF
0x14000cb6a  cmp     edx, 5
0x14000cb6d  jnz     loc_14000C9AF
0x14000cb73  jmp     loc_14000C99B
0x14000cb78  mov     edx, ebx
0x14000cb7a  mov     rcx, rax
0x14000cb7d  call    ?GetFaultDomainId@SDB_DRIVE@@QEAAPEAU_GUID@@W4_SC_FD_TYPE@@@Z; SDB_DRIVE::GetFaultDomainId(_SC_FD_TYPE)
0x14000cb82  test    rax, rax
0x14000cb85  jz      loc_14000C9AF
0x14000cb8b  xor     ecx, ecx
0x14000cb8d  cmp     ecx, [rsp+0C8h+var_A8]
0x14000cb91  jnb     loc_14000C9AF
0x14000cb97  jmp     loc_14000CAC8
0x14000cb9c  mov     rax, [rsp+0C8h+var_98]
0x14000cba1  mov     ecx, [rsp+0C8h+var_A4]
0x14000cba5  jmp     loc_14000C9A3
0x14000cbaa  xor     edx, edx; Tag
0x14000cbac  call    cs:__imp_ExFreePoolWithTag
0x14000cbb3  nop     dword ptr [rax+rax+00h]
0x14000cbb8  mov     eax, edi
0x14000cbba  jmp     loc_14000C946
0x14000cbbf  mov     eax, 0C000009Ah
0x14000cbc4  jmp     loc_14000C946
0x140069640  mov     rcx, [rbx+8]
0x140069644  mov     rdx, [rsp+0C8h+arg_20]
0x14006964c  mov     [rdx+8], rcx
0x140069650  mov     rcx, [rbx+10h]
0x140069654  mov     [rdx+10h], rcx
0x140069658  movzx   ecx, byte ptr [rbx+18h]
0x14006965c  mov     [rdx+18h], cl
0x14006965f  movzx   ecx, byte ptr [rbx+19h]
0x140069663  mov     [rdx+19h], cl
0x140069666  mov     ecx, [rbx+1Ch]
0x140069669  mov     [rdx+1Ch], ecx
0x14006966c  mov     rax, [rbx+20h]
0x140069670  mov     [rdx+20h], rax
0x140069674  mov     rax, [rbx+28h]
0x140069678  mov     [rdx+28h], rax
0x14006967c  mov     rax, [rbx+30h]
0x140069680  mov     [rdx+30h], rax
0x140069684  mov     eax, [rbx+38h]
0x140069687  mov     [rdx+38h], eax
0x14006968a  mov     eax, [rbx+38h]
0x14006968d  mov     [rdx+38h], eax
0x140069690  mov     eax, [rbx+3Ch]
0x140069693  mov     [rdx+3Ch], eax
0x140069696  mov     eax, [rbx+40h]
0x140069699  mov     [rdx+40h], eax
0x14006969c  mov     eax, [rbx+44h]
0x14006969f  mov     [rdx+44h], eax
0x1400696a2  mov     eax, [rbx+48h]
0x1400696a5  mov     [rdx+48h], eax
0x1400696a8  movzx   eax, word ptr [rbx+4Ch]
0x1400696ac  mov     [rdx+4Ch], ax
0x1400696b0  movzx   eax, word ptr [rbx+4Eh]
0x1400696b4  mov     [rdx+4Eh], ax
0x1400696b8  mov     rax, [rbx+50h]
0x1400696bc  mov     [rdx+50h], rax
0x1400696c0  jmp     loc_14000CA9F
```
