# VmxpReplacePlexMember(_IRP *)

- ea: `0x14003b600`
- end: `0x14003b8f8`
- name: `?VmxpReplacePlexMember@@YAJPEAU_IRP@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x1400099d8`
- `0x14002a3f4`
- `0x1400314e8`
- `0x14003acbc`
- `0x14003b600`
- `0x14003c244`
- `0x14003f51c`
- `0x14004a70c`
- `0x14004bac0`
- `0x14005628c`
- `0x14005abb4`

## pseudocode

```c
__int64 __fastcall VmxpReplacePlexMember(struct _IRP *a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  struct _IRP *MasterIrp; // rbp
  VMX_NOTIFICATION_QUEUE *v4; // rcx
  int v5; // esi
  __int64 v6; // rdx
  unsigned int Options; // ecx
  int v8; // eax
  __int64 v9; // r9
  struct VMX_PACK *v10; // r14
  struct VMX_RECORD *VolumeById; // r15
  char v13; // [rsp+70h] [rbp+8h] BYREF
  struct VMX_PACK *v14; // [rsp+78h] [rbp+10h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  v14 = 0;
  VMX_TASK_WRAPPER::VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v13, 0);
  if ( !*((_BYTE *)Global + 273) )
  {
    v4 = WPP_GLOBAL_Control;
    v5 = -1070071783;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_46;
    }
    v6 = 249;
    goto LABEL_44;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v5 = -1073741811;
  if ( Options < 0x60 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_46;
    }
    v6 = 250;
    goto LABEL_44;
  }
  if ( Options < LODWORD(MasterIrp->ThreadListEntry.Blink) + 40 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_46;
    }
    v6 = 251;
    goto LABEL_44;
  }
  if ( CurrentStackLocation->Parameters.Read.Length < 0x20 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_46;
    }
    v6 = 252;
    goto LABEL_44;
  }
  v8 = VmxpValidatePackIdInput((struct _GUID *)MasterIrp, &v14);
  v5 = v8;
  if ( v8 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      goto LABEL_46;
    }
    v6 = 253;
    v9 = (unsigned int)v8;
    goto LABEL_45;
  }
  while ( 1 )
  {
    v10 = v14;
    VolumeById = VMX_CONFIG::FindVolumeById(*((VMX_CONFIG **)v14 + 2), (struct _GUID *)&MasterIrp->Flags);
    if ( !VolumeById )
      break;
    v5 = VMX_PACK::BeginTransaction(v10);
    if ( v5 >= 0 )
    {
      v5 = VMX_PACK::ReplacePlexMemberTransaction(
             (struct VMX_TRANSACTION **)v10,
             VolumeById,
             (unsigned int)MasterIrp->ThreadListEntry.Flink,
             HIDWORD(MasterIrp->ThreadListEntry.Flink),
             (struct _VM_PLEX_MEMBER_LAYOUT *)&MasterIrp->ThreadListEntry.Blink);
      if ( v5 < 0 )
      {
        VMX_PACK::AbortTransaction(v10);
      }
      else
      {
        v5 = VMX_PACK::CommitTransaction((struct VMX_CONFIG **)v10, 0, 1);
        if ( v5 >= 0 )
        {
          *(_OWORD *)&MasterIrp->Type = *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 2) + 8LL) + 8LL);
          *(_OWORD *)&MasterIrp->Flags = *(_OWORD *)(*((_QWORD *)VolumeById + (*((_WORD *)VolumeById + 32) & 1) + 5)
                                                   + 232LL);
          a1->IoStatus.Information = 32;
          VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v13);
          return 0;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        255,
        WPP_2f8af752156e3401cd435973c831895d_Traceguids,
        (unsigned int)v5);
    }
    if ( v5 != -1070071728 && v5 != -1070071804 || VmxpRecoverPackConfigOnline(v10, &v14) < 0 )
      goto LABEL_46;
  }
  v4 = WPP_GLOBAL_Control;
  v5 = -1070071738;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v6 = 254;
LABEL_44:
    v9 = (unsigned int)v5;
LABEL_45:
    WPP_SF_d(*((_QWORD *)v4 + 3), v6, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v9);
  }
LABEL_46:
  VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER((VMX_TASK_WRAPPER *)&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003b600  mov     [rsp+arg_10], rbx
0x14003b605  push    rbp
0x14003b606  push    rsi
0x14003b607  push    rdi
0x14003b608  push    r12
0x14003b60a  push    r13
0x14003b60c  push    r14
0x14003b60e  push    r15
0x14003b610  sub     rsp, 30h
0x14003b614  mov     rbx, [rcx+0B8h]
0x14003b61b  mov     r13, rcx
0x14003b61e  mov     rbp, [rcx+18h]
0x14003b622  xor     edx, edx; unsigned __int8
0x14003b624  lea     rcx, [rsp+68h+arg_0]; this
0x14003b629  mov     [rsp+68h+arg_8], 0
0x14003b632  call    ??0VMX_TASK_WRAPPER@@QEAA@E@Z; VMX_TASK_WRAPPER::VMX_TASK_WRAPPER(uchar)
0x14003b637  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14003b63e  cmp     byte ptr [rax+111h], 0
0x14003b645  jnz     short loc_14003B683
0x14003b647  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b64e  lea     rdi, WPP_GLOBAL_Control
0x14003b655  mov     esi, 0C0380019h
0x14003b65a  cmp     rcx, rdi
0x14003b65d  jz      loc_14003B8D3
0x14003b663  mov     eax, [rcx+2Ch]
0x14003b666  mov     bl, 2
0x14003b668  test    bl, al
0x14003b66a  jz      loc_14003B8D3
0x14003b670  cmp     [rcx+29h], bl
0x14003b673  jb      loc_14003B8D3
0x14003b679  mov     edx, 0F9h
0x14003b67e  jmp     loc_14003B8C0
0x14003b683  mov     ecx, [rbx+10h]
0x14003b686  mov     esi, 0C000000Dh
0x14003b68b  cmp     ecx, 60h ; '`'
0x14003b68e  jnb     short loc_14003B6C7
0x14003b690  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b697  lea     rdi, WPP_GLOBAL_Control
0x14003b69e  cmp     rcx, rdi
0x14003b6a1  jz      loc_14003B8D3
0x14003b6a7  mov     eax, [rcx+2Ch]
0x14003b6aa  mov     bl, 2
0x14003b6ac  test    bl, al
0x14003b6ae  jz      loc_14003B8D3
0x14003b6b4  cmp     [rcx+29h], bl
0x14003b6b7  jb      loc_14003B8D3
0x14003b6bd  mov     edx, 0FAh
0x14003b6c2  jmp     loc_14003B8C0
0x14003b6c7  lea     r12, [rbp+28h]
0x14003b6cb  mov     eax, [r12]
0x14003b6cf  add     eax, 28h ; '('
0x14003b6d2  cmp     ecx, eax
0x14003b6d4  jnb     short loc_14003B70D
0x14003b6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b6dd  lea     rdi, WPP_GLOBAL_Control
0x14003b6e4  cmp     rcx, rdi
0x14003b6e7  jz      loc_14003B8D3
0x14003b6ed  mov     eax, [rcx+2Ch]
0x14003b6f0  mov     bl, 2
0x14003b6f2  test    bl, al
0x14003b6f4  jz      loc_14003B8D3
0x14003b6fa  cmp     [rcx+29h], bl
0x14003b6fd  jb      loc_14003B8D3
0x14003b703  mov     edx, 0FBh
0x14003b708  jmp     loc_14003B8C0
0x14003b70d  cmp     dword ptr [rbx+8], 20h ; ' '
0x14003b711  jnb     short loc_14003B74A
0x14003b713  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b71a  lea     rdi, WPP_GLOBAL_Control
0x14003b721  cmp     rcx, rdi
0x14003b724  jz      loc_14003B8D3
0x14003b72a  mov     eax, [rcx+2Ch]
0x14003b72d  mov     bl, 2
0x14003b72f  test    bl, al
0x14003b731  jz      loc_14003B8D3
0x14003b737  cmp     [rcx+29h], bl
0x14003b73a  jb      loc_14003B8D3
0x14003b740  mov     edx, 0FCh
0x14003b745  jmp     loc_14003B8C0
0x14003b74a  lea     rdx, [rsp+68h+arg_8]; struct VMX_PACK **
0x14003b74f  mov     rcx, rbp; struct _GUID *
0x14003b752  call    ?VmxpValidatePackIdInput@@YAJPEAU_GUID@@PEAPEAVVMX_PACK@@@Z; VmxpValidatePackIdInput(_GUID *,VMX_PACK * *)
0x14003b757  mov     esi, eax
0x14003b759  test    eax, eax
0x14003b75b  jns     short loc_14003B797
0x14003b75d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b764  lea     rdi, WPP_GLOBAL_Control
0x14003b76b  cmp     rcx, rdi
0x14003b76e  jz      loc_14003B8D3
0x14003b774  mov     edx, [rcx+2Ch]
0x14003b777  mov     bl, 2
0x14003b779  test    bl, dl
0x14003b77b  jz      loc_14003B8D3
0x14003b781  cmp     [rcx+29h], bl
0x14003b784  jb      loc_14003B8D3
0x14003b78a  mov     edx, 0FDh
0x14003b78f  mov     r9d, eax
0x14003b792  jmp     loc_14003B8C3
0x14003b797  lea     rdi, WPP_GLOBAL_Control
0x14003b79e  mov     bl, 2
0x14003b7a0  lea     rax, [rbp+10h]
0x14003b7a4  mov     r14, [rsp+68h+arg_8]
0x14003b7a9  mov     rdx, rax; struct _GUID *
0x14003b7ac  mov     rcx, [r14+10h]; this
0x14003b7b0  call    ?FindVolumeById@VMX_CONFIG@@QEAAPEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_CONFIG::FindVolumeById(_GUID *)
0x14003b7b5  mov     r15, rax
0x14003b7b8  test    rax, rax
0x14003b7bb  jz      loc_14003B89E
0x14003b7c1  mov     rcx, r14; this
0x14003b7c4  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14003b7c9  mov     esi, eax
0x14003b7cb  test    eax, eax
0x14003b7cd  js      short loc_14003B848
0x14003b7cf  mov     r9d, [rbp+24h]; unsigned int
0x14003b7d3  mov     rdx, r15; struct VMX_RECORD *
0x14003b7d6  mov     r8d, [rbp+20h]; unsigned int
0x14003b7da  mov     rcx, r14; this
0x14003b7dd  mov     [rsp+68h+var_48], r12; struct _VM_PLEX_MEMBER_LAYOUT *
0x14003b7e2  call    ?ReplacePlexMemberTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@KKPEAU_VM_PLEX_MEMBER_LAYOUT@@@Z; VMX_PACK::ReplacePlexMemberTransaction(VMX_RECORD *,ulong,ulong,_VM_PLEX_MEMBER_LAYOUT *)
0x14003b7e7  mov     esi, eax
0x14003b7e9  mov     rcx, r14; this
0x14003b7ec  test    eax, eax
0x14003b7ee  js      short loc_14003B843
0x14003b7f0  mov     r8b, 1; unsigned __int8
0x14003b7f3  xor     edx, edx; unsigned __int8
0x14003b7f5  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14003b7fa  mov     esi, eax
0x14003b7fc  test    eax, eax
0x14003b7fe  js      short loc_14003B848
0x14003b800  mov     rax, [r14+10h]
0x14003b804  mov     rcx, [rax+8]
0x14003b808  movups  xmm0, xmmword ptr [rcx+8]
0x14003b80c  lea     rcx, [rsp+68h+arg_0]; this
0x14003b811  movdqu  xmmword ptr [rbp+0], xmm0
0x14003b816  movzx   eax, word ptr [r15+40h]
0x14003b81b  and     eax, 1
0x14003b81e  mov     rax, [r15+rax*8+28h]
0x14003b823  movups  xmm0, xmmword ptr [rax+0E8h]
0x14003b82a  movdqu  xmmword ptr [rbp+10h], xmm0
0x14003b82f  mov     qword ptr [r13+38h], 20h ; ' '
0x14003b837  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x14003b83c  xor     eax, eax
0x14003b83e  jmp     loc_14003B8DF
0x14003b843  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x14003b848  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b84f  cmp     rcx, rdi
0x14003b852  jz      short loc_14003B878
0x14003b854  mov     eax, [rcx+2Ch]
0x14003b857  test    bl, al
0x14003b859  jz      short loc_14003B878
0x14003b85b  cmp     [rcx+29h], bl
0x14003b85e  jb      short loc_14003B878
0x14003b860  mov     rcx, [rcx+18h]
0x14003b864  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003b86b  mov     edx, 0FFh
0x14003b870  mov     r9d, esi
0x14003b873  call    WPP_SF_d
0x14003b878  cmp     esi, 0C0380050h
0x14003b87e  jz      short loc_14003B888
0x14003b880  cmp     esi, 0C0380004h
0x14003b886  jnz     short loc_14003B8D3
0x14003b888  lea     rdx, [rsp+68h+arg_8]; struct VMX_PACK **
0x14003b88d  mov     rcx, r14; struct VMX_PACK *
0x14003b890  call    ?VmxpRecoverPackConfigOnline@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z; VmxpRecoverPackConfigOnline(VMX_PACK *,VMX_PACK * *)
0x14003b895  test    eax, eax
0x14003b897  js      short loc_14003B8D3
0x14003b899  jmp     loc_14003B7A0
0x14003b89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8a5  mov     esi, 0C0380046h
0x14003b8aa  cmp     rcx, rdi
0x14003b8ad  jz      short loc_14003B8D3
0x14003b8af  mov     eax, [rcx+2Ch]
0x14003b8b2  test    bl, al
0x14003b8b4  jz      short loc_14003B8D3
0x14003b8b6  cmp     [rcx+29h], bl
0x14003b8b9  jb      short loc_14003B8D3
0x14003b8bb  mov     edx, 0FEh
0x14003b8c0  mov     r9d, esi
0x14003b8c3  mov     rcx, [rcx+18h]
0x14003b8c7  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14003b8ce  call    WPP_SF_d
0x14003b8d3  lea     rcx, [rsp+68h+arg_0]; this
0x14003b8d8  call    ??1VMX_TASK_WRAPPER@@QEAA@XZ; VMX_TASK_WRAPPER::~VMX_TASK_WRAPPER(void)
0x14003b8dd  mov     eax, esi
0x14003b8df  mov     rbx, [rsp+68h+arg_10]
0x14003b8e7  add     rsp, 30h
0x14003b8eb  pop     r15
0x14003b8ed  pop     r14
0x14003b8ef  pop     r13
0x14003b8f1  pop     r12
0x14003b8f3  pop     rdi
0x14003b8f4  pop     rsi
0x14003b8f5  pop     rbp
0x14003b8f6  retn
```
