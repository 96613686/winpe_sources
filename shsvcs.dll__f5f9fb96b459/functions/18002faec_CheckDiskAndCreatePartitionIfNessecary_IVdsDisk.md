# CheckDiskAndCreatePartitionIfNessecary(IVdsDisk *)

- ea: `0x18002faec`
- end: `0x18002fbc7`
- name: `?CheckDiskAndCreatePartitionIfNessecary@@YAXPEAUIVdsDisk@@@Z`
- size: `219`
- prototype: `void __fastcall(struct IVdsDisk *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002fcc0`

## callees

- `0x18002faec`
- `0x18003025c`
- `0x18003032c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fbba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fbba`

## pseudocode

```c
void __fastcall CheckDiskAndCreatePartitionIfNessecary(struct IVdsDisk *a1)
{
  struct IVdsDiskVtbl *lpVtbl; // rax
  struct IVdsDiskVtbl *v3; // rax
  LPVOID pv[3]; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+50h] [rbp+18h] BYREF
  int v6; // [rsp+58h] [rbp+20h] BYREF
  struct IVdsAdvancedDisk *v7; // [rsp+60h] [rbp+28h] BYREF
  LPVOID v8; // [rsp+68h] [rbp+30h] BYREF

  lpVtbl = a1->lpVtbl;
  v8 = 0;
  v6 = 0;
  if ( ((int (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))lpVtbl->QueryExtents)(a1, &v8, &v6) >= 0 )
  {
    v3 = a1->lpVtbl;
    v7 = 0;
    if ( ((int (__fastcall *)(struct IVdsDisk *, GUID *, struct IVdsAdvancedDisk **))v3->QueryInterface)(
           a1,
           &IID_IVdsAdvancedDisk,
           &v7) >= 0 )
    {
      pv[0] = 0;
      v5 = 0;
      if ( ((int (__fastcall *)(struct IVdsAdvancedDisk *, LPVOID *, int *))v7->lpVtbl->QueryPartitions)(v7, pv, &v5) >= 0 )
      {
        if ( !v5 && (int)CreatePartition(v7, *((_QWORD *)v8 + 3), *((_QWORD *)v8 + 4)) >= 0 )
          FormatVolumeNTFS(v7);
        CoTaskMemFree(pv[0]);
      }
      ((void (__fastcall *)(struct IVdsAdvancedDisk *))v7->lpVtbl->Release)(v7);
    }
    CoTaskMemFree(v8);
  }
}

```

## disassembly

```asm
0x18002faec  push    rbp
0x18002faee  push    rbx
0x18002faef  mov     rbp, rsp
0x18002faf2  sub     rsp, 38h
0x18002faf6  mov     rax, [rcx]
0x18002faf9  lea     r8, [rbp+arg_8]
0x18002fafd  lea     rdx, [rbp+arg_18]
0x18002fb01  mov     [rbp+arg_18], 0
0x18002fb09  mov     rbx, rcx
0x18002fb0c  mov     [rbp+arg_8], 0
0x18002fb13  mov     rax, [rax+30h]
0x18002fb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb1c  test    eax, eax
0x18002fb1e  js      loc_18002FBC0
0x18002fb24  mov     rax, [rbx]
0x18002fb27  lea     r8, [rbp+arg_10]
0x18002fb2b  lea     rdx, IID_IVdsAdvancedDisk
0x18002fb32  mov     [rbp+arg_10], 0
0x18002fb3a  mov     rcx, rbx
0x18002fb3d  mov     rax, [rax]
0x18002fb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb45  test    eax, eax
0x18002fb47  js      short loc_18002FBB6
0x18002fb49  mov     rcx, [rbp+arg_10]
0x18002fb4d  lea     r8, [rbp+arg_0]
0x18002fb51  mov     [rbp+pv], 0
0x18002fb59  lea     rdx, [rbp+pv]
0x18002fb5d  mov     [rbp+arg_0], 0
0x18002fb64  mov     rax, [rcx]
0x18002fb67  mov     rax, [rax+20h]
0x18002fb6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb70  test    eax, eax
0x18002fb72  js      short loc_18002FBA6
0x18002fb74  cmp     [rbp+arg_0], 0
0x18002fb78  jnz     short loc_18002FB9C
0x18002fb7a  mov     rdx, [rbp+arg_18]
0x18002fb7e  mov     rcx, [rbp+arg_10]; struct IVdsAdvancedDisk *
0x18002fb82  mov     r8, [rdx+20h]; unsigned __int64
0x18002fb86  mov     rdx, [rdx+18h]; unsigned __int64
0x18002fb8a  call    ?CreatePartition@@YAJPEAUIVdsAdvancedDisk@@_K1@Z; CreatePartition(IVdsAdvancedDisk *,unsigned __int64,unsigned __int64)
0x18002fb8f  test    eax, eax
0x18002fb91  js      short loc_18002FB9C
0x18002fb93  mov     rcx, [rbp+arg_10]; struct IVdsAdvancedDisk *
0x18002fb97  call    ?FormatVolumeNTFS@@YAJPEAUIVdsAdvancedDisk@@@Z; FormatVolumeNTFS(IVdsAdvancedDisk *)
0x18002fb9c  mov     rcx, [rbp+pv]; pv
0x18002fba0  call    cs:__imp_CoTaskMemFree
0x18002fba6  mov     rcx, [rbp+arg_10]
0x18002fbaa  mov     rax, [rcx]
0x18002fbad  mov     rax, [rax+10h]
0x18002fbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbb6  mov     rcx, [rbp+arg_18]; pv
0x18002fbba  call    cs:__imp_CoTaskMemFree
0x18002fbc0  add     rsp, 38h
0x18002fbc4  pop     rbx
0x18002fbc5  pop     rbp
0x18002fbc6  retn
```
