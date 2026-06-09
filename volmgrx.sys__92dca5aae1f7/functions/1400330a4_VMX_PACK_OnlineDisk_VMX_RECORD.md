# VMX_PACK::OnlineDisk(VMX_RECORD *)

- ea: `0x1400330a4`
- end: `0x1400331cb`
- name: `?OnlineDisk@VMX_PACK@@QEAAXPEAVVMX_RECORD@@@Z`
- size: `295`
- prototype: `void __fastcall(VMX_CONFIG **this, struct VMX_RECORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002f1e4`
- `0x14005dcc4`

## callees

- `0x14002a3f4`
- `0x14002fcfc`
- `0x140031648`
- `0x1400330a4`
- `0x1400331d4`
- `0x140033278`
- `0x14004350c`
- `0x14004a70c`
- `0x14004ae60`
- `0x14004b130`
- `0x14004bac0`
- `0x1400536d4`
- `0x1400537c4`
- `0x140054b2c`
- `0x14005781c`

## pseudocode

```c
void __fastcall VMX_PACK::OnlineDisk(VMX_CONFIG **this, struct VMX_RECORD *a2)
{
  struct VMX_PHYSICAL_DISK *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rax
  VMX_PACK *v7; // rcx

  v4 = *(struct VMX_PHYSICAL_DISK **)(*((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5) + 128LL);
  v5 = *((_QWORD *)v4 + 11);
  v6 = *(_QWORD *)(v5 + 244) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)(v5 + 252) - *(_QWORD *)GUID_NULL.Data4;
  if ( v6
    && (int)VMX_PHYSICAL_DISK::ChangeIdentityRevertPhase1(*(VMX_PHYSICAL_DISK **)(*((_QWORD *)a2
                                                                                  + (*((_WORD *)a2 + 32) & 1)
                                                                                  + 5)
                                                                                + 128LL)) < 0 )
  {
    VmxpOfflinePhysicalDisk(v4);
    VMX_PHYSICAL_DISK::InvalidateMetadata(v4);
  }
  else
  {
    VMX_PACK::OnlineConfigCopy(this, v4);
    if ( *((_BYTE *)this + 57) )
      goto LABEL_20;
    if ( VMX_PACK::QuorumInSync((VMX_PACK *)this) )
      VMX_PACK::OnlineConfig(v7);
    if ( *((_BYTE *)this + 57) )
    {
LABEL_20:
      if ( !VMX_PACK::QuorumInSync((VMX_PACK *)this) )
        *((_BYTE *)this + 57) = 0;
    }
    VMX_PACK::OnlineLogCopy((VMX_PACK *)this, v4);
    VMX_PACK::OnlineDiskVolumes((VMX_PACK *)this, a2);
    if ( (*(_DWORD *)(*((_QWORD *)a2 + (*((_WORD *)a2 + 32) & 1) + 5) + 96LL) & 0x20) != 0
      && (int)VMX_PACK::BeginTransaction((VMX_PACK *)this) >= 0 )
    {
      if ( VMX_PACK::AddVoterTransaction((VMX_PACK *)this, a2) < 0 )
        VMX_PACK::AbortTransaction((VMX_PACK *)this);
      else
        VMX_PACK::CommitTransaction(this, 0, 1);
    }
    VMX_PACK::AttemptGrowDisk((VMX_PACK *)this, a2);
    VMX_PACK::StampBootDiskSignature((VMX_PACK *)this, a2);
  }
}

```

## disassembly

```asm
0x1400330a4  mov     [rsp+arg_0], rbx
0x1400330a9  mov     [rsp+arg_8], rsi
0x1400330ae  push    rdi
0x1400330af  sub     rsp, 20h
0x1400330b3  movzx   eax, word ptr [rdx+40h]
0x1400330b7  mov     rbx, rcx
0x1400330ba  and     eax, 1
0x1400330bd  mov     rsi, rdx
0x1400330c0  mov     rax, [rdx+rax*8+28h]
0x1400330c5  mov     rdi, [rax+80h]
0x1400330cc  mov     rcx, [rdi+58h]
0x1400330d0  mov     rax, [rcx+0F4h]
0x1400330d7  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1400330de  jnz     short loc_1400330EE
0x1400330e0  mov     rax, [rcx+0FCh]
0x1400330e7  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x1400330ee  test    rax, rax
0x1400330f1  jz      short loc_140033114
0x1400330f3  mov     rcx, rdi; this
0x1400330f6  call    ?ChangeIdentityRevertPhase1@VMX_PHYSICAL_DISK@@QEAAJXZ; VMX_PHYSICAL_DISK::ChangeIdentityRevertPhase1(void)
0x1400330fb  test    eax, eax
0x1400330fd  jns     short loc_140033114
0x1400330ff  mov     rcx, rdi; this
0x140033102  call    ?VmxpOfflinePhysicalDisk@@YAXPEAVVMX_PHYSICAL_DISK@@@Z; VmxpOfflinePhysicalDisk(VMX_PHYSICAL_DISK *)
0x140033107  mov     rcx, rdi; this
0x14003310a  call    ?InvalidateMetadata@VMX_PHYSICAL_DISK@@QEAAXXZ; VMX_PHYSICAL_DISK::InvalidateMetadata(void)
0x14003310f  jmp     loc_1400331BA
0x140033114  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x140033117  mov     rcx, rbx; this
0x14003311a  call    ?OnlineConfigCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineConfigCopy(VMX_PHYSICAL_DISK *)
0x14003311f  cmp     byte ptr [rbx+39h], 0
0x140033123  jnz     short loc_14003313C
0x140033125  mov     rcx, rbx; this
0x140033128  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14003312d  test    al, al
0x14003312f  jz      short loc_140033136
0x140033131  call    ?OnlineConfig@VMX_PACK@@QEAAJXZ; VMX_PACK::OnlineConfig(void)
0x140033136  cmp     byte ptr [rbx+39h], 0
0x14003313a  jz      short loc_14003314B
0x14003313c  mov     rcx, rbx; this
0x14003313f  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x140033144  test    al, al
0x140033146  jnz     short loc_14003314B
0x140033148  mov     [rbx+39h], al
0x14003314b  mov     rdx, rdi; struct VMX_PHYSICAL_DISK *
0x14003314e  mov     rcx, rbx; this
0x140033151  call    ?OnlineLogCopy@VMX_PACK@@QEAAJPEAVVMX_PHYSICAL_DISK@@@Z; VMX_PACK::OnlineLogCopy(VMX_PHYSICAL_DISK *)
0x140033156  mov     rdx, rsi; struct VMX_RECORD *
0x140033159  mov     rcx, rbx; this
0x14003315c  call    ?OnlineDiskVolumes@VMX_PACK@@QEAAXPEAVVMX_RECORD@@@Z; VMX_PACK::OnlineDiskVolumes(VMX_RECORD *)
0x140033161  movzx   eax, word ptr [rsi+40h]
0x140033165  and     eax, 1
0x140033168  mov     rax, [rsi+rax*8+28h]
0x14003316d  mov     ecx, [rax+60h]
0x140033170  test    cl, 20h
0x140033173  jz      short loc_1400331A4
0x140033175  mov     rcx, rbx; this
0x140033178  call    ?BeginTransaction@VMX_PACK@@QEAAJXZ; VMX_PACK::BeginTransaction(void)
0x14003317d  test    eax, eax
0x14003317f  js      short loc_1400331A4
0x140033181  mov     rdx, rsi; struct VMX_RECORD *
0x140033184  mov     rcx, rbx; this
0x140033187  call    ?AddVoterTransaction@VMX_PACK@@QEAAJPEAVVMX_RECORD@@@Z; VMX_PACK::AddVoterTransaction(VMX_RECORD *)
0x14003318c  mov     rcx, rbx; this
0x14003318f  test    eax, eax
0x140033191  js      short loc_14003319F
0x140033193  mov     r8b, 1; unsigned __int8
0x140033196  xor     edx, edx; unsigned __int8
0x140033198  call    ?CommitTransaction@VMX_PACK@@QEAAJEE@Z; VMX_PACK::CommitTransaction(uchar,uchar)
0x14003319d  jmp     short loc_1400331A4
0x14003319f  call    ?AbortTransaction@VMX_PACK@@QEAAXXZ; VMX_PACK::AbortTransaction(void)
0x1400331a4  mov     rdx, rsi; struct VMX_RECORD *
0x1400331a7  mov     rcx, rbx; this
0x1400331aa  call    ?AttemptGrowDisk@VMX_PACK@@AEAAXPEAVVMX_RECORD@@@Z; VMX_PACK::AttemptGrowDisk(VMX_RECORD *)
0x1400331af  mov     rdx, rsi; struct VMX_RECORD *
0x1400331b2  mov     rcx, rbx; this
0x1400331b5  call    ?StampBootDiskSignature@VMX_PACK@@AEAAXPEAVVMX_RECORD@@@Z; VMX_PACK::StampBootDiskSignature(VMX_RECORD *)
0x1400331ba  mov     rbx, [rsp+28h+arg_0]
0x1400331bf  mov     rsi, [rsp+28h+arg_8]
0x1400331c4  add     rsp, 20h
0x1400331c8  pop     rdi
0x1400331c9  retn
```
